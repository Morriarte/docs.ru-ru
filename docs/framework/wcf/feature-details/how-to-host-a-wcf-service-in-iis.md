---
title: Практическое руководство. Размещение службы WCF в IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: a1759434d259cdffe1dac6b19a6582bfb83784bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492489"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Практическое руководство. Размещение службы WCF в IIS
В этом разделе описаны основные шаги, необходимые для создания службы Windows Communication Foundation (WCF), размещенного в Internet Information Services (IIS). Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями. Дополнительные сведения о службах IIS см [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449). Службы WCF, которая выполняется в среде IIS пользуется всеми преимуществами возможности IIS, такие как перезапуск процессов, бездействует завершения работы, мониторинг работоспособности процессов и активацию с помощью сообщений. Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения. Размещение в службах IIS возможно только при использовании транспорта HTTP.  
  
 Дополнительные сведения о том, как WCF и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] взаимодействия см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md). Дополнительные сведения о настройке параметров безопасности см. в разделе [безопасности](../../../../docs/framework/wcf/feature-details/security.md).  
  
 Исходная копия в этом примере в разделе [IIS размещения с использованием встроенного кода](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>Создание службы, размещенной в IIS  
  
1.  Убедитесь, что службы IIS установлены и выполняются на компьютере. Дополнительные сведения об установке и настройке служб IIS в разделе [Установка и настройка служб IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)  
  
2.  Создайте новую папку с именем IISHostedCalcService для файлов приложения, убедитесь, что [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] имеет доступ к содержимому этой папки, и воспользуйтесь средством управления IIS для создания нового приложения служб IIS, которое физически расположено в каталоге этого приложения. Создайте для каталога приложения псевдоним «IISHostedCalc».  
  
3.  Создайте в каталоге приложения новый файл с именем «service.svc». Изменить этот файл, добавив следующий код @ServiceHost элемента.  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  В каталоге приложения создайте подкаталог App_Code.  
  
5.  Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.  
  
6.  Добавьте следующие операторы using в начало файла Service.cs.  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  Добавьте следующее объявление пространства имен после операторов using.  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации. Во время выполнения инфраструктура WCF использует сведения для создания клиентских приложений для взаимодействия с конечной точки.  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     В этом примере конечные точки явно задаются в файле конфигурации. Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию. Дополнительные сведения о конечных точек по умолчанию, привязок и поведений см. в разделе [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
11. Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.  
  
## <a name="example"></a>Пример  
 Далее представлен полный код службы калькулятора, размещаемой в IIS.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>См. также  
 [Размещение в службах IIS](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Размещение служб](../../../../docs/framework/wcf/hosting-services.md)  
 [Службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
