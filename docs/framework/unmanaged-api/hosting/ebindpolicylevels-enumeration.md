---
title: "Перечисление EBindPolicyLevels"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e55fdb58129cd530bb63f26fab0be471b133d62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="f09d7-102">Перечисление EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="f09d7-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="f09d7-103">Предоставляет флаги, чтобы задать уровень, на котором следует применять или изменять политику сборки.</span><span class="sxs-lookup"><span data-stu-id="f09d7-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f09d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f09d7-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="f09d7-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f09d7-105">Members</span></span>  
  
|<span data-ttu-id="f09d7-106">Член</span><span class="sxs-lookup"><span data-stu-id="f09d7-106">Member</span></span>|<span data-ttu-id="f09d7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f09d7-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="f09d7-108">Включение применения политики на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="f09d7-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="f09d7-109">Включение применения политики на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="f09d7-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="f09d7-110">Включение применения политики на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="f09d7-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="f09d7-111">Задает флаги не уровня политики.</span><span class="sxs-lookup"><span data-stu-id="f09d7-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="f09d7-112">Включение применения политики на уровне издателя.</span><span class="sxs-lookup"><span data-stu-id="f09d7-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="f09d7-113">Указывает, что политика должна быть применимо на уровнях переменной.</span><span class="sxs-lookup"><span data-stu-id="f09d7-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="f09d7-114">Указывает, что политика должен поддерживать переносимости между реализациями сборки платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f09d7-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="f09d7-115">В разделе [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) элемент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f09d7-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="f09d7-116">Указывает, что политика должна соответствовать политике среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f09d7-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f09d7-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f09d7-117">Remarks</span></span>  
 <span data-ttu-id="f09d7-118">Это перечисление передается методам [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) интерфейс для выполнения изменений в политике приложения.</span><span class="sxs-lookup"><span data-stu-id="f09d7-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f09d7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="f09d7-119">Requirements</span></span>  
 <span data-ttu-id="f09d7-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f09d7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f09d7-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f09d7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f09d7-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f09d7-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f09d7-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f09d7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f09d7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f09d7-124">See Also</span></span>  
 [<span data-ttu-id="f09d7-125">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f09d7-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="f09d7-126">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="f09d7-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)