---
title: "Доступ к службе из веб-браузера (краткое руководство по службам WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Доступ к службе из веб-браузера (краткое руководство по службам WCF Data Services)
В этой задаче необходимо запустить [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] из [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] и отключить чтение потока в веб\-браузере.  Затем мы извлечем документ определения службы, а также обратимся к ресурсам службы данных, отправляя запросы HTTP GET к предоставляемым ресурсам через веб\-браузер.  
  
> [!NOTE]
>  По умолчанию [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] автоматически задает номер порта URI `localhost` на локальном компьютере.  В данной задаче в примерах URI используется порт номер `12345`.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] том, как задать конкретный номер порта в проекте [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], см. в разделе [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
### Запрос сервисного документа по умолчанию с помощью Internet Explorer  
  
1.  В обозревателе Internet Explorer выберите в меню **Сервис** команду **Свойства обозревателя**, щелкните вкладку **Содержание**, нажмите кнопку **Параметры** и снимите флажок **Включить показ ленты чтения веб\-каналов**.  
  
     При этом чтение каналов будет отключено.  Если не выключить эту функцию, то веб\-браузер будет рассматривать документ в формате AtomPub в качестве канала XML, а не отображать необработанные данные XML.  
  
    > [!NOTE]
    >  Если браузер не может отобразить канал в виде необработанных XML\-данных, его все равно можно просмотреть в виде исходного кода страницы.  
  
2.  В [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] нажмите клавишу F5 для запуска отладки приложения.  
  
3.  Откройте веб\-браузер на локальном компьютере.  В адресной строке введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     При этом будет возвращен сервисный документ по умолчанию, в котором содержится список наборов сущностей, предоставляемых службой данных.  
  
### Доступ к ресурсам набора сущностей из веб\-браузера  
  
1.  В адресной строке веб\-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     При этом будет возвращен набор всех клиентов из образца базы данных Northwind.  
  
2.  В адресной строке веб\-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     При этом возвращается экземпляр сущности для конкретного клиента `ALFKI`.  
  
3.  В адресной строке веб\-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     При этом произойдет переход по связи между клиентами и заказами для возвращения набора всех заказов для конкретного клиента `ALFKI`.  
  
4.  В адресной строке веб\-браузера введите следующий URI:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     При этом будут отфильтрованы заказы, принадлежащие конкретному клиенту `ALFKI`, в результате чего будет возвращен только конкретный заказ на основе переданного значения `OrderID`.  
  
## Следующие действия  
 Итак, мы успешно обратились к службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] из веб\-браузера, отправляя через браузер запросы HTTP GET к указанным ресурсам.  Веб\-браузер предоставляет простой способ проведения экспериментов с синтаксисом адресации запросов и просмотра результатов.  Однако к производственной службе данных таким способом обычно не обращаются.  Как правило, приложения взаимодействуют со службой данных через код приложения или языки скриптов. Далее мы создадим клиентское приложение, в котором используются клиентские библиотеки для доступа к ресурсам службы данных, как если бы они представляли собой объекты общей языковой среды выполнения \(CLR\):  
  
 [Создание клиентского приложения .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## См. также  
 [Доступ к ресурсам службы данных](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)