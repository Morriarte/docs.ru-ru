---
title: "Связь между языковым компонентам и библиотеки типов | Документы Microsoft"
description: "Библиотека типов для реализации часто используют возможности языка. Понимание этой связи."
keywords: "C# конструкции языка стандартной библиотеки"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a><span data-ttu-id="e3443-105">Связи между языковым компонентам и библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="e3443-105">Relationships between language features and library types</span></span>

<span data-ttu-id="e3443-106">Определение языка C# требует стандартной библиотеки для определенных типов, а также некоторые доступные члены этих типов.</span><span class="sxs-lookup"><span data-stu-id="e3443-106">The C# language definition requires a standard library to have certain types and certain accessible members on those types.</span></span> <span data-ttu-id="e3443-107">Компилятор создает код, который использует эти необходимые типы и члены для реализации многих функций на другом языке.</span><span class="sxs-lookup"><span data-stu-id="e3443-107">The compiler generates code that uses these required types and members for many different language features.</span></span> <span data-ttu-id="e3443-108">При необходимости, существуют пакеты NuGet, которые содержат типы, необходимые для более новые версии языка при написании кода для сред, где эти типы или члены имеют еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="e3443-108">When necessary, there are NuGet packages that contain types needed for newer versions of the language when writing code for environments where those types or members have not been deployed yet.</span></span>

<span data-ttu-id="e3443-109">Эта зависимость от функциональных возможностей стандартной библиотеки был частью языка C# с самой первой версии.</span><span class="sxs-lookup"><span data-stu-id="e3443-109">This dependency on standard library functionality has been part of the C# language since its first version.</span></span> <span data-ttu-id="e3443-110">В эту версию включены примеры:</span><span class="sxs-lookup"><span data-stu-id="e3443-110">In that version, examples included:</span></span>

* <span data-ttu-id="e3443-111"><xref:System.Exception>-используется для всех исключений, создаваемый компилятором.</span><span class="sxs-lookup"><span data-stu-id="e3443-111"><xref:System.Exception> - used for all compiler generated exceptions.</span></span>
* <span data-ttu-id="e3443-112"><xref:System.String>-C# `string` тип является синонимом для <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e3443-112"><xref:System.String> - the C# `string` type is a synonym for <xref:System.String>.</span></span>
* <span data-ttu-id="e3443-113"><xref:System.Int32>— синоним `int`.</span><span class="sxs-lookup"><span data-stu-id="e3443-113"><xref:System.Int32> - synonym of `int`.</span></span>

<span data-ttu-id="e3443-114">Эта первая версия была простой: компилятора и стандартной библиотеки поставляемом вместе друг с другом, и только одна версия.</span><span class="sxs-lookup"><span data-stu-id="e3443-114">That first version was simple: the compiler and the standard library shipped together, and there was only one version of each.</span></span>

<span data-ttu-id="e3443-115">Последующие версии C# иногда добавлены новые типы или члены зависимостям.</span><span class="sxs-lookup"><span data-stu-id="e3443-115">Subsequent versions of C# have occasionally added new types or members to the dependencies.</span></span> <span data-ttu-id="e3443-116">Примеры: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> и <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e3443-116">Examples include: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> and <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>.</span></span> <span data-ttu-id="e3443-117">C# 7.0 продолжается это путем добавления зависимость на <xref:System.ValueTuple> реализовать [кортежей](../tuples.md) функции языка.</span><span class="sxs-lookup"><span data-stu-id="e3443-117">C# 7.0 continues this by adding a dependency on <xref:System.ValueTuple> to implement the [tuples](../tuples.md) language feature.</span></span>

<span data-ttu-id="e3443-118">Чтобы уменьшить контактную зону, типов и членов соответствует стандартной библиотеки работает группа разработки языка.</span><span class="sxs-lookup"><span data-stu-id="e3443-118">The language design team works to minimize the surface area of the types and members required in a compliant standard library.</span></span> <span data-ttu-id="e3443-119">Соответствие чистой структуре, где новых возможностей библиотеки включены без проблем в язык равномерно этой цели.</span><span class="sxs-lookup"><span data-stu-id="e3443-119">That goal is balanced against a clean design where new library features are incorporated seamlessly into the language.</span></span> <span data-ttu-id="e3443-120">Будет существовать новые функции в будущих версиях C#, требующих новых типов и членов в стандартную библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e3443-120">There will be new features in future versions of C# that require new types and members in a standard library.</span></span> <span data-ttu-id="e3443-121">Важно понять, как управлять эти зависимости свою работу.</span><span class="sxs-lookup"><span data-stu-id="e3443-121">It's important to understand how to manage those dependencies in your work.</span></span>

## <a name="managing-your-dependencies"></a><span data-ttu-id="e3443-122">Управление зависимостями</span><span class="sxs-lookup"><span data-stu-id="e3443-122">Managing your dependencies</span></span>

<span data-ttu-id="e3443-123">Средства компилятора C# теперь лишается цикла выпуска библиотек .NET на поддерживаемых платформах.</span><span class="sxs-lookup"><span data-stu-id="e3443-123">C# compiler tools are now decoupled from the release cycle of the .NET libraries on supported platforms.</span></span> <span data-ttu-id="e3443-124">В действительности различных библиотеках .NET содержат различные жизненного цикла: .NET Framework в Windows является relesed как Центр обновления Windows, .NET Core поставляется на отдельное расписание и Xamarin версии библиотеки отгрузки обновлений с помощью средства Xamarin для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="e3443-124">In fact, different .NET libraries have different release cycles: the .NET Framework on Windows is relesed as a Windows Update, .NET Core ships on a separate schedule, and the Xamarin versions of library updates ship with the Xamarin tools for each target platform.</span></span>

<span data-ttu-id="e3443-125">Большую часть времени, можно не заметить, эти изменения.</span><span class="sxs-lookup"><span data-stu-id="e3443-125">The majority of time, you won't notice these changes.</span></span> <span data-ttu-id="e3443-126">Однако при работе с более новой версии, языка, который не требуются возможности, но в библиотеках .NET на этой платформе будет ссылаться на пакеты NuGet, чтобы добавить эти новые типы.</span><span class="sxs-lookup"><span data-stu-id="e3443-126">However, when you are working with a newer version of the language that requires features not yet in the .NET libraries on that platform, you'll reference the NuGet packages to provide those new types.</span></span>
<span data-ttu-id="e3443-127">Как платформы вашего приложения поддерживает обновляются с помощью новых установок framework можно удалить лишние ссылки.</span><span class="sxs-lookup"><span data-stu-id="e3443-127">As the platforms your app supports are updated with new framework installations, you can remove the extra reference.</span></span>

<span data-ttu-id="e3443-128">Такое разделение означает, что даже в том случае, если вы используете машины, которые могут не иметь соответствующего framework можно использовать новые возможности языка.</span><span class="sxs-lookup"><span data-stu-id="e3443-128">This separation means you can use new language features even when you are targeting machines that may not have the corresponding framework.</span></span>