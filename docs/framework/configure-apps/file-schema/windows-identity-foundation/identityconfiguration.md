---
title: '&lt;identityConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5070d9e886b8f5a8a0abf27593d40df8b5281267
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759001"
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
Указывает параметры уровня службы удостоверений.  
  
 \<system.identityModel >  
\<identityConfiguration >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Имя раздела конфигурации удостоверений. Это имя можно использовать для ссылки на определенный раздел конфигурации. Если не `name` атрибут указан, раздел определяет конфигурацию по умолчанию. Конфигурация по умолчанию всегда используется в сценариях с пассивной федерацией. Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.|  
|saveBootstrapContext|Указывает, следует ли включать в токен сеанса начальной загрузки маркеры. Значение также может быть задана для коллекции обработчика токенов, задав `saveBootstrapContext` атрибут [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемента. Значение, заданное в коллекцию обработчиков токенов переопределяет значение, заданное для службы.|  
|maximumClockSkew|Объект <xref:System.TimeSpan> , указывающее максимально допустимое время отклонения. Определяет максимально допустимое время отклонения при выполнении операций, зависящих от времени, например для проверки истечения срока действия сеанса входа в систему. Значение по умолчанию — 5 минут «00: 05:00». Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Также можно задать максимальную расфазировку синхронизирующих импульсов на коллекцию обработчика токенов, задав `maximumClockSkew` атрибут [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемента. Значение, заданное в коллекцию обработчиков токенов переопределяет значение, заданное для службы.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<кэширует >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэши, используемый для маркеров сеансов и обнаружение воспроизведения токенов. Можно указать на уровне службы или в коллекцию обработчика токенов безопасности. Необязательный.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Управляет параметрами обработчиков токенов, используемых для проверки сертификатов. Можно указать на уровне службы или в коллекцию обработчика токенов безопасности. Необязательный.|  
|[\<claimsAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Регистрирует диспетчер проверки подлинности утверждений входящие утверждения. Необязательный.|  
|[\<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Регистрирует диспетчера авторизации утверждений для входящих утверждений. Необязательный.|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Указывает набор утверждений, необходимых для входящих токенов безопасности. Необязательный.|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Задает коллекцию обработчиков токенов безопасности. Можно указать ноль или более коллекциях обработчиков токенов безопасности. Необязательный.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Включает обнаружение воспроизведения токенов и определяет время жизни токенов. Можно указать на уровне службы или в коллекцию обработчика токенов безопасности. Необязательный.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Обеспечивает настройку для включения параметров Windows Identity Foundation (WIF) в приложениях.|  
  
## <a name="remarks"></a>Примечания  
 Несколько удостоверений, которые могут быть определены конфигурации, каждый с уникальным именем. Поведение выглядит следующим образом:  
  
1.  Если не `<identityConfiguration>` указанный элемент. Конфигурацию удостоверения по умолчанию создается во время выполнения и заполняется значениями по умолчанию.  
  
2.  Если один `<identityConfiguration>` указанный элемент. Это конфигурация по умолчанию удостоверений. Неважно с именем или без имени.  
  
3.  При наличии нескольких `<identityConfiguration>` указаны элементы. Безымянный элемент указывает конфигурацию удостоверения по умолчанию. Рекомендуется, если задано несколько `<identityConfiguration>` элементов, один из них должен быть неименованным.  
  
> [!WARNING]
>  Если задано несколько `<identityConfiguration>` элементов, один из них должен быть неименованным. Безымянный элемент будет конфигурацию удостоверения по умолчанию.  
  
 Некоторые параметры, указанные в `<identityConfiguration>` элемент могут переопределяться параметрами на коллекцию обработчика токенов безопасности или параметры на обработчики токенов безопасности.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде, на который ссылается конфигурация удостоверений `<federationConfiguration>` элемент настраивает диспетчера авторизации утверждений и политики, которая используется, чтобы сделать решения об авторизации. Это верно даже в случаях, не пассивный сценариях веб-, например приложений Windows Communication Foundation (WCF) или приложение, которое не является веб сервера. Если приложение не пассивное веб-приложение [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) элемент (и политики его дочерние элементы, если он имеется) указанное удостоверение конфигурации являются только параметры, применяемые. Все остальные параметры игнорируются. Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.  
  
 `<identityConfiguration>` Представлен <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> класса. Раздел конфигурации удостоверения представляется <xref:System.IdentityModel.Configuration.IdentityConfiguration> класса.  
  
> [!IMPORTANT]
>  Указание следующие элементы в качестве дочерних элементов `<identityConfiguration>` элемент является устаревшим, несмотря на то, что поведение по-прежнему поддерживается для обеспечения обратной совместимости. Эти элементы вместо этого указывается в разделе [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемента.  
>   
>  -   [\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>Пример  
 В следующем примере создается конфигурация удостоверений, с именем «alternateConfiguration». Конфигурацию удостоверения указывает параметры по умолчанию.  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
