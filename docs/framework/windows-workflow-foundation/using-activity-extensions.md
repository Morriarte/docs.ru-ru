---
title: Использование модулей действий
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 32c465ae42a1f0238fab7bba5ea795486db3b562
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517229"
---
# <a name="using-activity-extensions"></a>Использование модулей действий
Действия могут взаимодействовать с расширениями приложений рабочих процессов. Благодаря этому узел может предоставлять дополнительные возможности, которые не были явно смоделированы в рабочем процессе.  В этом разделе описывается создание расширений для подсчета количества выполнений действия.  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a>Использования расширения действия для подсчета выполнений  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]. Выберите **новый**, **проекта**. В разделе **Visual C#** выберите **рабочего процесса**.  Выберите **консольное приложение рабочего процесса** из списка шаблонов. Задайте для проекта имя `Extensions`. Нажмите кнопку **ОК**, чтобы создать проект.  
  
2.  Добавить `using` инструкции в файл Program.cs для **System.Collections.Generic** пространства имен.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  В файле Program.cs создайте новый класс с именем **ExecutionCountExtension**. Следующий код создает расширение рабочего процесса, отслеживающее идентификаторы экземпляра при его **зарегистрировать** вызывается метод.  
  
    ```  
    // This extension collects a list of workflow Ids  
    public class ExecutionCountExtension  
    {  
        IList<Guid> instances = new List<Guid>();  
  
        public int ExecutionCount  
        {  
            get  
            {  
                return this.instances.Count;  
            }  
        }  
  
        public IEnumerable<Guid> InstanceIds  
        {  
            get  
            {  
                return this.instances;  
            }  
        }  
  
        public void Register(Guid activityInstanceId)  
        {  
            if (!this.instances.Contains<Guid>(activityInstanceId))  
            {  
                instances.Add(activityInstanceId);  
            }  
        }  
    }  
    ```  
  
4.  Создать действие, использующее **ExecutionCountExtension**. В следующем коде определяется действие, извлекающее **ExecutionCountExtension** из среды выполнения и вызывающее его **зарегистрировать** метод при выполнении действия.  
  
    ```  
    // Activity that consumes an extension provided by the host. If the extension is available  
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)  
    public class MyActivity: CodeActivity  
    {  
        protected override void Execute(CodeActivityContext context)  
        {  
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();  
            if (ext != null)  
            {  
                ext.Register(context.WorkflowInstanceId);                         
            }  
  
        }  
    }  
    ```  
  
5.  Реализуйте действие в **Main** метод файла program.cs. В следующем коде содержатся методы для создания двух различных рабочих процессов, выполнения всех процессов по несколько раз и отображения полученных данных, содержащихся в расширении.  
  
    ```  
    class Program  
    {  
        // Creates a workflow that uses the activity that consumes the extension  
        static Activity CreateWorkflow1()  
        {  
            return new Sequence  
            {  
                Activities =  
                {  
                    new MyActivity()  
                }  
            };  
        }  
  
        // Creates a workflow that uses two instances of the activity that consumes the extension  
        static Activity CreateWorkflow2()  
        {  
            return new Sequence  
            {  
                Activities =  
                {  
                    new MyActivity(),  
                    new MyActivity()  
                }  
            };  
        }  
  
        static void Main(string[] args)  
        {  
            // create the extension   
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();  
  
            // configure the first invoker and execute 3 times  
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());  
            invoker.Extensions.Add(executionCountExt);                          
            invoker.Invoke();  
            invoker.Invoke();  
            invoker.Invoke();  
  
            // configure the second invoker and execute 2 times  
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());  
            invoker2.Extensions.Add(executionCountExt);  
            invoker2.Invoke();  
            invoker2.Invoke();  
  
            // show the data in the extension  
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);  
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));  
        }  
    }  
    ```
