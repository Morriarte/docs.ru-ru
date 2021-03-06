---
title: Практическое руководство. Анимация положения или цвета ограничения градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: 2eb528127c8aa66976788ec1f4e5362ca3a1ef26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558672"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Практическое руководство. Анимация положения или цвета ограничения градиента
В этом примере демонстрируется анимация <xref:System.Windows.Media.GradientStop.Color%2A> и <xref:System.Windows.Media.GradientStop.Offset%2A> из <xref:System.Windows.Media.GradientStop> объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере анимируется три градиента внутри <xref:System.Windows.Media.LinearGradientBrush>. В примере три анимации, каждый из которых выполняет анимацию различных градиента:  
  
-   Первая анимация <xref:System.Windows.Media.Animation.DoubleAnimation>, анимирует первого градиента <xref:System.Windows.Media.GradientStop.Offset%2A> от 0,0 до 1,0, а затем снова 0,0. В результате первый цвет градиента перемещается из левой части правую сторону прямоугольника и обратно на левую сторону.  
  
-   Вторая анимация <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует второй градиента <xref:System.Windows.Media.GradientStop.Color%2A> из <xref:System.Windows.Media.Colors.Purple%2A> для <xref:System.Windows.Media.Colors.Yellow%2A> и обратно <xref:System.Windows.Media.Colors.Purple%2A>. В результате Средний цвет градиента изменяет с фиолетовым, желтый и обратно.  
  
-   Третья анимация другой <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует непрозрачность третий градиента <xref:System.Windows.Media.GradientStop.Color%2A> -1, а затем снова. В результате исчезает третий цвет градиента и затем снова становится непрозрачным.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Media.LinearGradientBrush>, процесс одинаков для анимации <xref:System.Windows.Media.GradientStop> объектов внутри <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Дополнительные примеры см. в разделе [образец кисти](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.GradientStop>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
