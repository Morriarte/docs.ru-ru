---
title: Работа с языком описания данных DDL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: c6b3151a95f949100e10e630da848e34ebbf1187
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764402"
---
# <a name="working-with-data-definition-language"></a>Работа с языком описания данных DDL
Начиная с [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] версии 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поддерживает язык описания данных (DDL). Это позволяет создавать и удалять экземпляры базы данных с использованием строки подключения и метаданных модели хранения (SSDL).  
  
 В следующих методах в <xref:System.Data.Objects.ObjectContext> с помощью строки соединения и содержимого SSDL выполняются следующие задачи: создание базы данных, удаление базы данных, проверка наличия базы данных и просмотр сформированного скрипта DDL.  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  Предполагается наличие достаточных разрешений для выполнения команд DDL.  
  
 Ранее указанные методы делегируют большую часть работы базовому поставщику данных ADO.NET. Поставщик отвечает за соблюдение соглашения об именах, применяемых при создании объектов базы данных, в соответствии с правилами, используемыми для запросов и обновлений.  
  
 В следующем примере показано, как создать базу данных по существующей модели. Кроме того, новый объект сущности добавляется в контекст объекта, а затем сохраняется в базе данных.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a>Определение базы данных по существующей модели  
  
1.  Создайте консольное приложение.  
  
2.  Добавьте существующую модель в приложение.  
  
    1.  Добавьте пустую модель с именем `SchoolModel`. Чтобы создать пустую модель, см. [как: Создание нового .edmx файл](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) раздела.  
  
     В проект будет добавлен файл SchoolModel.edmx.  
  
    1.  Скопируйте концептуальные, хранения и сопоставления содержимого для модели School из [модели School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) раздела.  
  
    2.  Откройте файл SchoolModel.edmx и вставьте нужное содержимое в тегах `edmx:Runtime`.  
  
3.  Добавьте следующий код в функцию main. Этот код инициализирует строку подключения с сервером базы данных, просматривает скрипт DDL, создает базу данных, добавляет новую сущность в контекст и сохраняет изменения в базе данных.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
