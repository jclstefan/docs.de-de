### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="c0270-101">Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="c0270-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c0270-102">Details</span><span class="sxs-lookup"><span data-stu-id="c0270-102">Details</span></span>|<span data-ttu-id="c0270-103">Die Version von Entity Framework muss mit der Version von .NET Framework übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c0270-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="c0270-104">Für .NET Framework 4.5 wird Entity Framework 5 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c0270-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="c0270-105">Bei EF 4.x in einem .NET Framework 4.5-Projekt sind im Zusammenhang mit <xref:System.ComponentModel.DataAnnotations> mehrere Probleme bekannt.</span><span class="sxs-lookup"><span data-stu-id="c0270-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="c0270-106">In .NET 4.5 wurden diese in eine andere Assembly verschoben, daher gibt es Probleme mit der Bestimmung der zu verwendenden Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="c0270-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="c0270-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c0270-107">Suggestion</span></span>|<span data-ttu-id="c0270-108">Führen Sie bei Verwendung von .NET Framework 4.5 ein Upgrade auf Entity Framework 5 durch.</span><span class="sxs-lookup"><span data-stu-id="c0270-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="c0270-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="c0270-109">Scope</span></span>|<span data-ttu-id="c0270-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="c0270-110">Major</span></span>|
|<span data-ttu-id="c0270-111">Version</span><span class="sxs-lookup"><span data-stu-id="c0270-111">Version</span></span>|<span data-ttu-id="c0270-112">4.5</span><span class="sxs-lookup"><span data-stu-id="c0270-112">4.5</span></span>|
|<span data-ttu-id="c0270-113">Typ</span><span class="sxs-lookup"><span data-stu-id="c0270-113">Type</span></span>|<span data-ttu-id="c0270-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="c0270-114">Retargeting</span></span>|
