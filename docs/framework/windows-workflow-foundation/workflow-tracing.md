---
title: Отслеживание рабочих процессов
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: f4ce25efae0e42fa7c95ce5dffe8da8e31db05a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518181"
---
# <a name="workflow-tracing"></a>Отслеживание рабочих процессов
Трассировка рабочего процесса позволяет получать сведения диагностики при помощи прослушивателей трассировки .NET Framework. Трассировку можно включить при обнаружении проблемы в работе приложения, а затем снова отключить после разрешения проблемы. Существует два способа включения трассировки отладки для рабочих процессов. Можно настроить отслеживание в средстве просмотра трассировки событий либо использовать <xref:System.Diagnostics> для отправки событий трассировки в файл.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Включение трассировки отладки в ETW  
 Для включения трассировки при помощи ETW включите канал отладки в средстве просмотра событий.  
  
1.  Перейдите в узел аналитики и журналов отладки в средстве просмотра событий.  
  
2.  В представлении дерева в средстве просмотра событий перейдите к **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения**. Щелкните правой кнопкой мыши **сервер приложений-приложения** и выберите **Просмотр -> Отобразить аналитический и отладочный журналы**. Щелкните правой кнопкой мыши **отладки** и выберите **включить журнал**.  
  
3.  Когда рабочий процесс запускает отладку и трассы событий выдаются в канал отладки ETW, их можно просмотреть в средстве просмотра событий. Перейдите к **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения**. Щелкните правой кнопкой мыши **отладки** и выберите **обновление**.  
  
4.  Размер буфера аналитической трассировки по умолчанию составляет всего 4 килобайта (КБ). Рекомендуется увеличить этот размер до 32 КБ. Для этого выполните следующие действия.  
  
    1.  Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  Изменение \<bufferSize > значение в файле Windows.ApplicationServer.Applications.man 32.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  Если вы используете клиентский профиль .NET Framework 4, необходимо сначала зарегистрировать ETW-манифест, выполнив следующую команду из каталога .NET Framework 4: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Включение трассировки отладки при помощи System.Diagnostics  
 Эти прослушиватели можно настроить в файле App.config приложения рабочего процесса либо в файле Web.config для службы рабочего процесса. В этом примере [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) настроен для сохранения данных трассировки в файле MyTraceLog.txt в текущем каталоге.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Наблюдение за Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Мониторинг приложений с](http://go.microsoft.com/fwlink/?LinkId=201275)
