---
title: "Метод ICorProfilerCallback3::ProfilerAttachComplete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerAttachComplete Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0bf1e535c6270660797554c38a0b031df82f0925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="66d72-102">Метод ICorProfilerCallback3::ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="66d72-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="66d72-103">Вызывается средой CLR (CLR), чтобы указать, что теперь профилировщик может вызвать [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) и [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="66d72-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66d72-104">Syntax</span></span>  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="66d72-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="66d72-105">Remarks</span></span>  
 <span data-ttu-id="66d72-106">`ProfilerAttachComplete` Обратного вызова выдается после [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="66d72-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="66d72-107">Он указывает следующее.</span><span class="sxs-lookup"><span data-stu-id="66d72-107">It indicates the following:</span></span>  
  
-   <span data-ttu-id="66d72-108">Обратные вызовы, которые были запрошены профилировщиком в `InitializeForAttach`, были активированы.</span><span class="sxs-lookup"><span data-stu-id="66d72-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
-   <span data-ttu-id="66d72-109">Профилировщик теперь может выполнять захват в связанных идентификаторах, не заботясь об отсутствующих уведомлениях.</span><span class="sxs-lookup"><span data-stu-id="66d72-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="66d72-110">Среда CLR игнорирует возвращаемое значение из этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="66d72-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d72-111">Требования</span><span class="sxs-lookup"><span data-stu-id="66d72-111">Requirements</span></span>  
 <span data-ttu-id="66d72-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d72-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d72-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66d72-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66d72-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66d72-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66d72-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d72-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d72-116">См. также</span><span class="sxs-lookup"><span data-stu-id="66d72-116">See Also</span></span>  
 [<span data-ttu-id="66d72-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="66d72-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="66d72-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="66d72-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="66d72-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="66d72-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="66d72-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="66d72-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)