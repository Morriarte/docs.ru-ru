---
title: Возможности языка XAML 2009
ms.date: 03/30/2017
helpviewer_keywords:
- XAML 2009 [XAML Services]
- XAML [XAML Services], XAML 2009
ms.assetid: f6bb18d8-c86a-4549-8862-323e6b32a8dd
ms.openlocfilehash: ed0f638975c232638de4a46db5db82bb1e85668c
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207473"
---
# <a name="xaml-2009-language-features"></a>Возможности языка XAML 2009
XAML 2009 — это сокращение для новых компонентов языка XAML, которые расширяют существующую спецификацию языка XAML. XAML 2009 содержит ряд новых директив и конструкций. К ним относятся [директива x: Arguments](../../../docs/framework/xaml-services/x-arguments-directive.md); [директива x: FactoryMethod](../../../docs/framework/xaml-services/x-factorymethod-directive.md); [расширение разметки x: Reference](../../../docs/framework/xaml-services/x-reference-markup-extension.md); [директива x: TypeArguments ](../../../docs/framework/xaml-services/x-typearguments-directive.md); встроенные типы общих примитивов языка (например `x:Char`).  
  
<a name="xaml_2009_support_in_wpf_and_visual_studio"></a>   
## <a name="xaml-2009-support-in-wpf-and-visual-studio"></a>Поддержка XAML 2009 в WPF и Visual Studio  
 В WPF можно использовать возможности XAML 2009, но только для кода XAML, не скомпилированного с разметкой WPF. Скомпилированный XAML с разметкой и форма BAML кода XAML пока не поддерживают ключевые слова языка и компоненты XAML 2009.  
  
 Обратите внимание, что существующие методы для загрузки свободного XAML в WPF также могут иметь ограничения по безопасности и доступу для типов CLR и системы типов, являющихся более строгими по сравнению со скомпилированным XAML с разметкой. Дополнительные сведения см. в разделе [Безопасность (WPF)](../../../docs/framework/wpf/security-wpf.md) или [Стратегия безопасности WPF — безопасность платформы](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
 В XAML 2009 также реализованы дополнительные функции, изменяющие прежние конструкции XAML 2006 и основные формы разметки.  
  
### <a name="xkey-as-an-object-element"></a>x:Key как объектный элемент  
 XAML 2009 может поддерживать `x:Key` как объект (элемент свойства, значением которого является элемент объекта), но в XAML 2006 `x:Key` поддерживался только как атрибут. См. раздел "XAML 2009" в статье [x:Key Directive](../../../docs/framework/xaml-services/x-key-directive.md).  
  
### <a name="xmlns-on-property-elements"></a>xmlns для свойств элементов  
 XAML 2009 может поддерживать определения пространств имен (xmlns) XAML для свойств элементов, а в XAML 2006 определения xmlns поддерживались только для элементов объектов.  
  
### <a name="event-attributes"></a>Атрибуты событий  
 Для атрибутов, связанных с событиями, в XAML 2006 предполагается, что используется компиляция разметки, поэтому события подаются на компиляцию разметки. XAML 2009 поддерживает форму разметки, схожую с расширением разметки. Она дает возможность откладывать связывание событий до анализа и загрузки XAML. При этом приложения WPF и сценарии XAML для пользовательского интерфейса WPF обычно не используют эту возможность. WPF и его реализация в XAML 2006 используют сочетание связывания обработчика событий для перенаправленных событий, определенных на уровне <xref:System.Windows.UIElement> , и этап компилятора разметки для основной обработки атрибутов событий. Компилятор разметки также выполняет предварительную обработку всех атрибутов событий, найденных в XAML, где действия сборки объявляют, что используется компилятор разметки.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
