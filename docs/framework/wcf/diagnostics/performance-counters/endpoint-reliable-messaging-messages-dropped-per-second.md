---
title: 'Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: a87e5fef0c13e239959a386f108af3c4cebae7f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472288"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
Имя счетчика: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>Описание  
 Общее количество сообщений системы надежного обмена сообщениями, которое было отброшено в данной конечной точке в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
