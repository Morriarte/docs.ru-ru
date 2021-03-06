---
title: Служебная программа клиента служб данных WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 3206947d06a1736116674b70e469c20f8f4fca86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364530"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Служебная программа клиента служб данных WCF (DataSvcUtil.exe)
DataSvcUtil.exe является средством командной строки, предоставляемые [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] , которые используют [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] канала и создает клиентские классы службы данных, которые необходимы для доступа к службе данных из клиентского приложения .NET Framework. Эта программа формирует классы данных с использованием следующих источников метаданных.  
  
-   Корневой URI службы данных. Эта программа запрашивает документ метаданных службы, в котором описывается модель данных, предоставленная службой данных. Дополнительные сведения см. в разделе [OData: документ метаданных службы](http://go.microsoft.com/fwlink/?LinkId=186070).  
  
-   Файл модели данных (с расширением CSDL), определенные с помощью языка определения концептуальной схемы (CSDL), как определено в [ \[MC-CSDL\]: формат файла определения концептуальной схемы](http://go.microsoft.com/fwlink/?LinkID=159072) спецификации.  
  
-   Файл EDMX, созданный при помощи программ для работы с моделью EDM, входящих в комплект Entity Framework. Дополнительные сведения см. в разделе [ \[MC-EDMX\]: модели EDM для формата упаковки служб данных](http://go.microsoft.com/fwlink/?LinkID=178833) спецификации.  
  
 Дополнительные сведения см. в разделе [как: вручную создавать клиентские классы службы данных](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
 Программа DataSvcUtil.exe установлена в каталоге [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Обычно это папка C:\Windows\Microsoft.NET\Framework\v4.0. Для 64-разрядных версий систем это папка C:\Windows\Microsoft.NET\Framework64\v4.0. Доступ к программе DataSvcUtil.exe можно также из командной строки Visual Studio (щелкните **запустить**, пункты **все программы**, пункты **Microsoft Visual Studio 2010**, пункты **набора средств Visual Studio**, а затем нажмите кнопку **Командная строка Visual Studio 2010**).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|------------|-----------------|  
|`/dataservicecollection`|Указывает, что будет также сформирован код, необходимый для привязки объектов к элементам управления.|  
|`/help`<br /><br /> -или-<br /><br /> `/?`|Отображает синтаксис команд и параметров программы.|  
|`/in:` *\<Файл >*|Указывает файл CSDL или EDMX либо каталог, в котором находится этот файл.|  
|`/language:`[VB&#124;c#]|Задает язык для сформированных файлов с исходным кодом. Язык по умолчанию — C#.|  
|`/nologo`|Отключает вывод сообщения об авторских правах.|  
|`/out:` *\<Файл >*|Задает имя файла с исходным кодом, в котором содержатся сформированные клиентские классы службы данных.|  
|`/uri:` *\<строка >*|URI [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала.|  
|`/version:`[1.0&#124;2.0]|Задает максимально принимаемую версию [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Версия определяется на основе `DataServiceVersion` атрибута элемента DataService в возвращаемых метаданных службы данных. Дополнительные сведения см. в разделе [управление версиями службы данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). При указании `/dataservicecollection` параметр, необходимо также указать `/version:2.0` для обеспечения привязки данных.|  
  
## <a name="see-also"></a>См. также  
 [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [Практическое руководство. Добавление ссылки на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
