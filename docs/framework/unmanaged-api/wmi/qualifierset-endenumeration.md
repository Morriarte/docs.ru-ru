---
title: "Функция QualifierSet_EndEnumeration (Справочник по неуправляемым API)"
description: "Функция QualifierSet_EndEnumeration завершает перечисления."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="2a9b4-103">Функция QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="2a9b4-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="2a9b4-104">Завершается перечисление начался вызовом [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2a9b4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a9b4-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="2a9b4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a9b4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2a9b4-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="2a9b4-108">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="2a9b4-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a9b4-109">Return value</span></span>

<span data-ttu-id="2a9b4-110">Следующее значение, возвращаемое этой функцией, определенные в *WbemCli.h* файла заголовка, или можно задавать как константа в коде:</span><span class="sxs-lookup"><span data-stu-id="2a9b4-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="2a9b4-111">Константа</span><span class="sxs-lookup"><span data-stu-id="2a9b4-111">Constant</span></span>  |<span data-ttu-id="2a9b4-112">Значение</span><span class="sxs-lookup"><span data-stu-id="2a9b4-112">Value</span></span>  |<span data-ttu-id="2a9b4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2a9b4-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2a9b4-114">0</span><span class="sxs-lookup"><span data-stu-id="2a9b4-114">0</span></span> | <span data-ttu-id="2a9b4-115">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2a9b4-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a9b4-116">Remarks</span></span>

<span data-ttu-id="2a9b4-117">Эта функция создает оболочку для вызова [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2a9b4-118">Этот вызов рекомендуется, но не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-118">This call is recommended, but not required.</span></span> <span data-ttu-id="2a9b4-119">Он немедленно освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="2a9b4-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a9b4-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2a9b4-120">Requirements</span></span>  

<span data-ttu-id="2a9b4-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a9b4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="2a9b4-122">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2a9b4-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="2a9b4-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9b4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9b4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2a9b4-124">See also</span></span>  
[<span data-ttu-id="2a9b4-125">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2a9b4-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)