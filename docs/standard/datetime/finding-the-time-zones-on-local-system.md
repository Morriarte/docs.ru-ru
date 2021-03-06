---
title: Поиск часового пояса, заданного в локальной системе
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], local
- time zones [.NET Framework], finding local system time zones
- time zone identifiers [.NET Framework]
- local time zone access
- time zones [.NET Framework], retrieving
- UTC times, finding local system time zones
- time zones [.NET Framework], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4196ff53a5c26be7c46a8168a30044836af2cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572766"
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Поиск часового пояса, заданного в локальной системе

Класс <xref:System.TimeZoneInfo> не предоставляет открытый конструктор. В результате ключевое слово `new` невозможно использовать для создания нового объекта <xref:System.TimeZoneInfo>. Вместо этого экземпляры объектов <xref:System.TimeZoneInfo> создаются либо путем извлечения информации о предопределенных часовых поясах из реестра, либо путем создания пользовательского часового пояса. В этом разделе описывается создание экземпляра часового пояса из данных, хранимых в реестре. Кроме того, свойства `static` (`shared` в Visual Basic) класса <xref:System.TimeZoneInfo> предоставляют доступ к часовому поясу UTC и местному часовому поясу.

> [!NOTE]
> Для часовых поясов, которые не определены в реестре, можно создать пользовательские часовые пояса путем вызова перегрузок метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Создание пользовательского часового пояса описано в [как: создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) и [как: создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) разделы. Кроме того, можно создать экземпляр объекта <xref:System.TimeZoneInfo>, восстановив его из сериализованной строки с использованием метода <xref:System.TimeZoneInfo.FromSerializedString%2A>. Сериализация и десериализация <xref:System.TimeZoneInfo> объект рассматривается в [как: сохранение часовых поясов во внедренный ресурс](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) и [как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) разделы.

## <a name="accessing-individual-time-zones"></a>Доступ к отдельным часовым поясам

Класс <xref:System.TimeZoneInfo> предоставляет два предопределенных объекта часовых поясов, которые представляют собой время UTC и местный часовой пояс. Они доступны из свойств <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A> соответственно. Инструкции по доступу к часовому поясу UTC или местному часовому поясу см. в разделе [как: доступ к предварительно определенных зоны объектам UTC и местным временем](../../../docs/standard/datetime/access-utc-and-local.md).

Можно также создать экземпляр объекта <xref:System.TimeZoneInfo>, который представляет любой часовой пояс, определенный в реестре. Инструкции по созданию объекта конкретного часового пояса см. в разделе [как: создание объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Идентификаторы часовых поясов

Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс. Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный. В большинстве случаев его значение соответствует свойству <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>, которое используется для предоставления имени стандартному времени часового пояса. Однако существуют исключения. Лучшим способом убедиться, что предоставлен действительный идентификатор, является выполнение перечисления доступных в системе часовых поясов и отслеживание связанных с ними идентификаторов.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[как: доступ к предварительно определенных зоны объектам UTC и местным временем](../../../docs/standard/datetime/access-utc-and-local.md)
[как: создание объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md) 
 [Преобразование времени из одного часового пояса](../../../docs/standard/datetime/converting-between-time-zones.md)
