---
title: Привязки do (F#)
description: 'Узнайте, как выполнить привязку F # используется для выполнения кода без определения функции или значения.'
ms.date: 05/16/2016
ms.openlocfilehash: 6fd084090a204beab0da1c2deb5b5ae2a86281c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562340"
---
# <a name="do-bindings"></a>Привязки do

Привязка `do` используется для выполнения кода без определения функции или значения. Кроме того, привязки `do` можно использовать в классах см [привязки `do` в классах](../members/do-bindings-in-classes.md).


## <a name="syntax"></a>Синтаксис

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Примечания
Используйте привязки `do`, если требуется выполнить код независимо от определения функции или значения. Выражение в привязке `do` должно возвращать значение `unit`. Код в привязке `do` верхнего уровня выполняется при инициализации модуля. Ключевое слово `do` является необязательным.

Атрибуты могут быть применены к привязке `do` верхнего уровня. Например, если программа использует COM-взаимодействия, может потребоваться применить в программе атрибут `STAThread`. Это можно сделать с помощью атрибута привязки `do`, как показано в следующем коде.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a>См. также
[Справочник по языку F#](../index.md)

[Функции](index.md)

