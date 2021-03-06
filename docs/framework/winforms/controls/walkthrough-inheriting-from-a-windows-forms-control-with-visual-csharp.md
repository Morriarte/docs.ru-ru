---
title: Пример. Наследование элементов управления форм Windows Forms с помощью Visual C#
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: 1e9231065369640fa49e04a491b92ebfb1e91912
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541513"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a>Пример. Наследование элементов управления форм Windows Forms с помощью Visual C# #
С помощью [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)] можно создавать эффективные настраиваемые элементы управления путем *наследования*. Наследование позволяет создавать элементы управления, сохраняющие все унаследованные функциональные возможности элементов управления Windows Forms и в то же время обладающие дополнительными функциями. В этом пошаговом руководстве вы создадите простой производный элемент управления с именем `ValueButton`. Эта кнопка наследует функциональные возможности стандартных форм Windows <xref:System.Windows.Forms.Button> управления и предоставляет настраиваемое свойство `ButtonValue`.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Создание проекта  
 Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>Создание библиотеки элементов управления ValueButtonLib и элемента управления ValueButton  
  
1.  В меню **Файл** наведите указатель мыши на пункт **Создать** и выберите **Проект**, чтобы открыть диалоговое окно **Создание проекта**.  
  
2.  Выберите **Библиотека элементов управления Windows Forms** шаблон проекта из списка проектов Visual C#, а также тип `ValueButtonLib` в **имя** поле.  
  
     Имя проекта, `ValueButtonLib`, по умолчанию также назначается корневому пространству имен. Корневое пространство имен используется для определения имен компонентов в сборке. Например, если в двух сборках содержатся компоненты с именем `ValueButton`, можно указать компонент `ValueButton`, используя `ValueButtonLib.ValueButton`. Дополнительные сведения см. в разделе [Пространства имен](../../../csharp/programming-guide/namespaces/index.md).  
  
3.  В **обозревателе решений** щелкните правой кнопкой мыши **UserControl1.cs** и выберите в контекстном меню команду **Переименовать**. Измените имя файла на `ValueButton.cs`. Чтобы переименовать все ссылки на элемент кода '`UserControl1`', в соответствующем запросе нажмите кнопку **Да**.  
  
4.  В **обозревателе решений** щелкните правой кнопкой мыши файл **ValueButton.cs** и выберите команду **Просмотреть код**.  
  
5.  Найдите `class` строка инструкции `public partial class ValueButton`и измените тип, от которого наследует этот элемент управления <xref:System.Windows.Forms.UserControl> для <xref:System.Windows.Forms.Button>. Это позволит элементу управления могут наследовать все функциональные возможности <xref:System.Windows.Forms.Button> элемента управления.  
  
6.  В **обозревателе решений** откройте узел **ValueButton.cs**, чтобы отобразить сформированный конструктором файл кода **ValueButton.Designer.cs**. Откройте этот файл в **редакторе кода**.  
  
7.  Найдите `InitializeComponent` метод и удалите строку, которая присваивает <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> свойство. Это свойство не существует в <xref:System.Windows.Forms.Button> элемента управления.  
  
8.  Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.  
  
    > [!NOTE]
    >  Визуальный конструктор больше не доступен. Поскольку <xref:System.Windows.Forms.Button> управления обладает своим собственным оформлением, их нельзя изменить в конструкторе. Визуальное представление будет иметь точно таким же, что он наследуется от класса (то есть, <xref:System.Windows.Forms.Button>), если в коде. В область конструктора по-прежнему можно добавлять компоненты, не имеющие элементов пользовательского интерфейса.  
  
## <a name="adding-a-property-to-your-inherited-control"></a>Добавление свойства в наследуемый элемент управления  
 Один из возможных способов использования наследуемых элементов управления форм Windows Forms — это создание элементов управления, имеющих такой же внешний вид и функции, как у стандартных элементов управления Windows Forms, но предоставляющих настраиваемые свойства. В этом разделе вы добавите в элемент управления свойство с именем `ButtonValue`.  
  
#### <a name="to-add-the-value-property"></a>Добавьте значение свойства  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши **ValueButton.cs** и выберите в контекстном меню пункт **Просмотреть код**.  
  
2.  Найдите оператор `class`. Сразу после `{` введите следующий код.  
  
    ```csharp  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     Этот код определяет методы хранения и извлечения свойства `ButtonValue`. Оператор `get` определяет значение, возвращаемое значению, которое хранится в закрытой переменной `varValue`, а оператор `set` задает значение закрытой переменной с помощью ключевого слова `value`.  
  
3.  Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.  
  
## <a name="testing-your-control"></a>Тестирование элемента управления  
 Элементы управления не являются автономными проектами и должны размещаться в контейнере. Чтобы протестировать элемент управления, необходимо предоставить тестовый проект, в котором он будет выполняться. Кроме того, нужно сделать элемент управления доступным для тестового проекта, выполнив сборку (компиляцию). В этом разделе вы выполните сборку элемента управления и протестируете его в Windows Forms.  
  
#### <a name="to-build-your-control"></a>Сборка элемента управления  
  
1.  В меню **Сборка** выберите **Собрать решение**.  
  
     Сборка должна быть выполнена без ошибок компилятора и предупреждений.  
  
#### <a name="to-create-a-test-project"></a>Создание тестового проекта  
  
1.  В меню **Файл** наведите указатель мыши на пункт **Добавить** и выберите **Проект**, чтобы открыть диалоговое окно **Добавление нового проекта**.  
  
2.  Выберите узел **Windows** под узлом **Visual C#** и выберите **приложение Windows Forms**.  
  
3.  В поле **Имя** введите `Test`.  
  
4.  В **обозревателе решений** щелкните узел **Ссылки** для тестового проекта правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.  
  
5.  Выберите вкладку **Проекты**. Проект `ValueButtonLib` будет указан под полем **Имя проекта**. Дважды щелкните проект, чтобы добавить ссылку на тестовый проект.  
  
6.  В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите пункт **Построить**.  
  
#### <a name="to-add-your-control-to-the-form"></a>Добавление элемента управления в форму  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши файл **Form1.cs** и выберите в контекстном меню пункт **Конструктор представлений**.  
  
2.  На **панели элементов** выберите **Компоненты ValueButtonLib**. Дважды щелкните **ValueButton**.  
  
     Объект **ValueButton** появится в форме.  
  
3.  Щелкните **ValueButton** правой кнопкой мыши и выберите в контекстном меню пункт **Свойства**.  
  
4.  В окне **Свойства** проверьте свойства этого элемента управления. Обратите внимание, что они идентичны свойствам стандартной кнопки, кроме дополнительного свойства `ButtonValue`.  
  
5.  Задайте для свойства `ButtonValue` значение `5`.  
  
6.  В **все формы Windows Forms** вкладке **элементов**, дважды щелкните **метка** добавление <xref:System.Windows.Forms.Label> форму элемента управления.  
  
7.  Переместите метку в центр формы.  
  
8.  Дважды щелкните файл `valueButton1`.  
  
     В **редакторе кода** откроется событие `valueButton1_Click`.  
  
9. Вставьте следующую строку кода.  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите в контекстном меню команду **Назначить автозагружаемым проектом**.  
  
11. В меню **Отладка** выберите пункт **Начать отладку**.  
  
     Появится `Form1`.  
  
12. Нажмите кнопку `valueButton1`.  
  
     В `label1` появится цифра 5, показывающая, что свойство `ButtonValue` унаследованного элемента управления передано `label1` с помощью метода `valueButton1_Click`. Таким образом, ваш элемент управления `ValueButton` наследует функциональные возможности стандартной кнопки Windows Forms и при этом предоставляет дополнительное настраиваемое свойство.  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием компонентов](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)  
 [Примеры создания компонентов](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 [Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [Пошаговое руководство. Создание составного элемента управления с помощью C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
