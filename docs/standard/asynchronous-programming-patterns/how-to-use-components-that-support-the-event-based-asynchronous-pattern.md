---
title: Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
ms.openlocfilehash: a96641e6dd42e033f2d28b847fc071dfc514912d
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937001"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях
Многие компоненты предоставляют возможность выполнять работу асинхронно. Например, компоненты <xref:System.Media.SoundPlayer> и <xref:System.Windows.Forms.PictureBox> позволяют загружать звуки и изображения в фоновом режиме, не прерывая работу основного потока.  
  
 Чтобы применить асинхронные методы для класса, поддерживающего [асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md), зачастую достаточно присоединить обработчик события к событию *имя_метода***Completed** нужного компонента, как для любого другого события. При вызове метода *имя_метода***Async** приложение будет работать без прерывания, пока не будет создано событие *имя_метода***Completed**. В обработчике событий вы можете проверить параметр <xref:System.ComponentModel.AsyncCompletedEventArgs>, чтобы определить, была ли асинхронная операция выполнена успешно или отменена.  
  
 Дополнительные сведения об обработчиках событий см. в статье [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md) (Общие сведения об обработчиках событий).  
  
 Следующая процедура демонстрирует, как использовать возможность асинхронной загрузки изображений в элементе управления <xref:System.Windows.Forms.PictureBox>.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Асинхронная загрузка изображений для элемента управления PictureBox  
  
1.  Создайте в форме экземпляр компонента <xref:System.Windows.Forms.PictureBox>.  
  
2.  Назначьте обработчик событий для события <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
     Проверьте в нем наличие ошибок, которые могли произойти во время асинхронной загрузки. Также здесь нужно проверить, не запрошена ли отмена.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Добавьте в форму две кнопки с именами `loadButton` и `cancelLoadButton`. Добавьте обработчики событий <xref:System.Windows.Forms.Control.Click> для запуска и отмены загрузки.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Запустите приложение.  
  
     В процессе загрузки изображения вы сможете свободно перемещаться по форме, сворачивать ее и разворачивать.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Многопоточность в Visual Basic](../../../docs/visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
