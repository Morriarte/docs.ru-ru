---
title: Пример регулярного выражения. Изменение форматов даты
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8d2d5bf67368e445123fce43afe07065a31b1f30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568073"
---
# <a name="regular-expression-example-changing-date-formats"></a>Пример регулярного выражения. Изменение форматов даты
В следующем примере кода метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> используется для замены дат в формате *мм*/*дд*/*гг* на даты в формате *дд*-*мм*-*гг*.  
  
## <a name="example"></a>Пример  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 В следующем коде показано, как можно вызывать метод `MDYToDMY` в приложении.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a>Комментарии  
 Возможные интерпретации шаблона регулярного выражения `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`(?<month>\d{1,2})`|Совпадение с одной или двумя десятичными цифрами. Это записанная группа `month`.|  
|`/`|Совпадение с косой чертой.|  
|`(?<day>\d{1,2})`|Совпадение с одной или двумя десятичными цифрами. Это записанная группа `day`.|  
|`/`|Совпадение с косой чертой.|  
|`(?<year>\d{2,4})`|Совпадение с двумя-четырьмя десятичными цифрами. Это записанная группа `year`.|  
|`\b`|Совпадение должно заканчиваться на границе слова.|  
  
 Шаблон `${day}-${month}-${year}` определяет строку замены, как показано в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`$(day)`|Добавляет строку, которая записана захватываемой группой `day`.|  
|`-`|Добавляет символ дефиса.|  
|`$(month)`|Добавляет строку, которая записана захватываемой группой `month`.|  
|`-`|Добавляет символ дефиса.|  
|`$(year)`|Добавляет строку, которая записана захватываемой группой `year`.|  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
