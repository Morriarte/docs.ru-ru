---
title: Предложение orderby (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 1fd0036e8bd3c838fe92ca27635cd7638d59ef1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268060"
---
# <a name="orderby-clause-c-reference"></a>Предложение orderby (Справочник по C#)
В выражении запроса предложение `orderby` задает сортировку возвращаемой последовательности или вложенной последовательности (группы) в порядке возрастания или убывания. Для выполнения одной или нескольких операций последующей сортировки можно указать несколько ключей. Сортировка выполняется с помощью функции сравнения по умолчанию для соответствующего типа элемента. По умолчанию используется порядок сортировки по возрастанию. Также можно указать настраиваемую функцию сравнения. Тем не менее сделать это можно только с использованием синтаксиса на основе метода. Дополнительные сведения см. в разделе [Сортировка данных](../../programming-guide/concepts/linq/sorting-data.md).  
  
## <a name="example"></a>Пример  
 В следующем примере первый запрос сортирует слова в алфавитном порядке, начиная с A. Второй запрос сортирует эти же слова в порядке убывания. (Ключевое слово `ascending` определяет порядок сортировки по умолчанию и может быть опущено.)  
  
 [!code-csharp[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется первичная сортировка списка студентов по фамилиям, а затем дополнительная сортировка по именам.  
  
 [!code-csharp[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a>Примечания  
 Во время компиляции предложение `orderby` преобразуется в вызов метода <xref:System.Linq.Enumerable.OrderBy%2A>. Если в предложении `orderby` используется несколько ключей, они преобразуются в вызовы метода <xref:System.Linq.Enumerable.ThenBy%2A>.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [предложение group](../../../csharp/language-reference/keywords/group-clause.md)  
 [Приступая к работе с LINQ в C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
