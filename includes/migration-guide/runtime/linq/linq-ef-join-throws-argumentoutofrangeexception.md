### <a name="linq-to-ef-join-throws-argumentoutofrangeexception"></a><span data-ttu-id="241d8-101">Запросы Linq к EF Join вызывают исключение ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="241d8-101">Linq to EF Join throws ArgumentOutOfRangeException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="241d8-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="241d8-102">Details</span></span>|<span data-ttu-id="241d8-103">Перечислимые объекты или запросы Linq, которые обращаются к Join в сущностях Entity Framework, могут вызывать исключение <xref:System.ArgumentOutOfRangeException?displayProperty=name> в .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="241d8-103">Linq queries or enumerables that call &#39;Join&#39; on Entity Framework entities can cause an <xref:System.ArgumentOutOfRangeException?displayProperty=name>  in .NET Framework 4.5</span></span>|
|<span data-ttu-id="241d8-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="241d8-104">Suggestion</span></span>|<span data-ttu-id="241d8-105">Эта проблема была исправлена в обновлении обслуживания.</span><span class="sxs-lookup"><span data-stu-id="241d8-105">This issue was fixed in a servicing update.</span></span> <span data-ttu-id="241d8-106">Чтобы устранить эту проблему, обновите .NET Framework 4.5 или выполните обновление до .NET Framework 4.5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="241d8-106">Please update the .NET Framework 4.5, or upgrade to .NET Framework 4.5.1 or later, to fix this issue.</span></span>|
|<span data-ttu-id="241d8-107">Область</span><span class="sxs-lookup"><span data-stu-id="241d8-107">Scope</span></span>|<span data-ttu-id="241d8-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="241d8-108">Minor</span></span>|
|<span data-ttu-id="241d8-109">Версия</span><span class="sxs-lookup"><span data-stu-id="241d8-109">Version</span></span>|<span data-ttu-id="241d8-110">4.5</span><span class="sxs-lookup"><span data-stu-id="241d8-110">4.5</span></span>|
|<span data-ttu-id="241d8-111">Тип</span><span class="sxs-lookup"><span data-stu-id="241d8-111">Type</span></span>|<span data-ttu-id="241d8-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="241d8-112">Runtime</span></span>|
|<span data-ttu-id="241d8-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="241d8-113">Affected APIs</span></span>|<ul><li><xref:System.Linq.Enumerable.Join%60%604(System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.Enumerable.Join%60%604(System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.ParallelEnumerable.Join%60%604(System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.ParallelEnumerable.Join%60%604(System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.ParallelEnumerable.Join%60%604(System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Linq.ParallelQuery%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.ParallelEnumerable.Join%60%604(System.Linq.ParallelQuery%7B%60%600%7D%2CSystem.Linq.ParallelQuery%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.Queryable.Join%60%604(System.Linq.IQueryable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Linq.Expressions.Expression%7BSystem.Func%7B%60%600%2C%60%602%7D%7D%2CSystem.Linq.Expressions.Expression%7BSystem.Func%7B%60%601%2C%60%602%7D%7D%2CSystem.Linq.Expressions.Expression%7BSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%7D)?displayProperty=nameWithType></li><li><xref:System.Linq.Queryable.Join%60%604(System.Linq.IQueryable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Linq.Expressions.Expression%7BSystem.Func%7B%60%600%2C%60%602%7D%7D%2CSystem.Linq.Expressions.Expression%7BSystem.Func%7B%60%601%2C%60%602%7D%7D%2CSystem.Linq.Expressions.Expression%7BSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D)?displayProperty=nameWithType></li></ul>|
