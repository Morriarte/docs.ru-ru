---
title: Перегрузка членов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573559"
---
# <a name="member-overloading"></a>Перегрузка членов
Перегрузка членов означает создание двух или более элементов в рамках одного типа, отличающихся только число или тип параметров, но имеют одинаковое имя. Например, в следующих `WriteLine` перегруженный метод:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Так как только методы, конструкторы и индексированных свойств могут содержать параметры, только тех элементов, могут быть перегружены.  
  
 Перегрузка является одним из наиболее важных способы улучшения удобства использования, производительность и удобство чтения повторно используемых библиотек. Перегрузка на число параметров позволяет предоставлять более простой версии конструкторы и методы. Перегрузка в параметре-типе дает возможность использовать одно и то же имя члена для идентичных операций с выбранным набором различных типов элементов.  
  
 **✓ DO** попробуйте использовать описательные имена параметров, чтобы указать значение по умолчанию использовать более короткие перегрузки.  
  
 **X AVOID** произвольного изменения имен параметров в перегрузках. Если параметр в одной перегрузке представляет одного входного параметра в другую перегрузку, должен иметь то же имя.  
  
 **X AVOID** Несогласованная в порядок параметров в перегруженных членов. Параметры с тем же именем, должны отображаться в той же позиции в все перегрузки.  
  
 **✓ DO** сделать виртуальной только самую длинную перегрузку (если требуется расширяемость). Более короткие перегрузки должны просто вызвать через более.  
  
 **X DO NOT** использовать `ref` или `out` модификаторы для перегрузки членов.  
  
 В некоторых языках не может разрешить вызовы перегрузки следующим образом. Кроме того таких перегрузок обычно имеют совершенно разные семантики и, возможно, не должно быть перегрузки, но два отдельных метода вместо.  
  
 **X DO NOT** имеют перегрузки с параметрами в одной позиции и похожих, но различную семантику.  
  
 **✓ DO** Разрешить `null` для передачи дополнительных аргументов.  
  
 **✓ DO** использовать член перегрузка предпочтительнее, чем определение членов с аргументами по умолчанию.  
  
 Аргументы по умолчанию не являются CLS-совместимыми.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Правила разработки членов](../../../docs/standard/design-guidelines/member.md)  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
