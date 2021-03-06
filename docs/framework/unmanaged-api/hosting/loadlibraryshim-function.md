---
title: Функция LoadLibraryShim
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8936fa3d22cfde4c2536fccf9d46c1990133db1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445316"
---
# <a name="loadlibraryshim-function"></a>Функция LoadLibraryShim
Загружает заданную версию библиотеки DLL, которая включается в распространяемый пакет платформы .NET Framework.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Используйте [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) метод вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szDllName`  
 [in] Нулем строка, представляющая имя библиотеки DLL, загружаемой библиотеки .NET Framework.  
  
 `szVersion`  
 [in] Нулем строка, представляющая версию библиотеки DLL для загрузки. Если `szVersion` равен null, выбранной для загрузки последней версии, указанной библиотеки DLL, которая меньше, чем версия 4 версии. То есть, все версии меньше, чем версия 4 учитываются, если `szVersion` имеет значение null, и если установлен без версии меньше, чем версии 4, не загружается. Это гарантирует, что установка [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] не влияет на существующие приложения или компоненты. См. в записи [SxS незавершенного и быстрый запуск миграции](http://go.microsoft.com/fwlink/?LinkId=200329) в блоге команды среды CLR.  
  
 `pvReserved`  
 Зарезервировано для будущего использования.  
  
 `phModDll`  
 [out] Указатель на дескриптор модуля.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|CLR_E_SHIM_RUNTIMELOAD|Загрузка `szDllName` требует загрузки не удается загрузить необходимую версию среды CLR и общеязыковой среды выполнения (CLR).|  
  
## <a name="remarks"></a>Примечания  
 Эта функция используется для загрузки библиотек DLL, включенных в распространяемый пакет платформы .NET Framework. Она не загружает библиотеки DLL, созданного пользователем.  
  
> [!NOTE]
>  Начиная с .NET Framework версии 2.0, загрузка Fusion.dll среда CLR для загрузки. Это так, как функции в Fusion.dll теперь являются оболочками, в реализации которых предоставляются средой выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
