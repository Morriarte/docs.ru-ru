---
title: "Метод ICLRRuntimeHost::GetCLRControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4072c21ea002523fe8086151a40c4e17b775ebbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="d405d-102">Метод ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="d405d-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="d405d-103">Получает указатель интерфейса типа [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d405d-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d405d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d405d-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d405d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d405d-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="d405d-106">[out] Указатель на интерфейс типа [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , позволяет узлам настраивать дополнительные параметры среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d405d-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d405d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d405d-107">Return Value</span></span>  
  
|<span data-ttu-id="d405d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d405d-108">HRESULT</span></span>|<span data-ttu-id="d405d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d405d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d405d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d405d-110">S_OK</span></span>|<span data-ttu-id="d405d-111">`GetCLRControl`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d405d-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="d405d-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d405d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d405d-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d405d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d405d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d405d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d405d-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d405d-115">The call timed out.</span></span>|  
|<span data-ttu-id="d405d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d405d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d405d-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d405d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d405d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d405d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d405d-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d405d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d405d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d405d-120">E_FAIL</span></span>|<span data-ttu-id="d405d-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d405d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d405d-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d405d-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d405d-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d405d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d405d-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d405d-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d405d-125">Среда CLR уже запущена.</span><span class="sxs-lookup"><span data-stu-id="d405d-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d405d-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d405d-126">Remarks</span></span>  
 <span data-ttu-id="d405d-127">`ICLRControl`предоставляет [getclrmanager-метод](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод, который позволяет ведущему приложению получить указатель интерфейса на один из типов manager.</span><span class="sxs-lookup"><span data-stu-id="d405d-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d405d-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d405d-128">Requirements</span></span>  
 <span data-ttu-id="d405d-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d405d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d405d-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d405d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d405d-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d405d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d405d-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d405d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d405d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d405d-133">See Also</span></span>  
 [<span data-ttu-id="d405d-134">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d405d-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="d405d-135">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d405d-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)