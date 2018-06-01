### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="112df-101">In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt</span><span class="sxs-lookup"><span data-stu-id="112df-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="112df-102">Details</span><span class="sxs-lookup"><span data-stu-id="112df-102">Details</span></span>|<span data-ttu-id="112df-103">Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte.</span><span class="sxs-lookup"><span data-stu-id="112df-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="112df-104">Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="112df-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="112df-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="112df-105">Suggestion</span></span>|<span data-ttu-id="112df-106">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="112df-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="112df-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="112df-107">Scope</span></span>|<span data-ttu-id="112df-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="112df-108">Edge</span></span>|
|<span data-ttu-id="112df-109">Version</span><span class="sxs-lookup"><span data-stu-id="112df-109">Version</span></span>|<span data-ttu-id="112df-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="112df-110">4.6.2</span></span>|
|<span data-ttu-id="112df-111">Typ</span><span class="sxs-lookup"><span data-stu-id="112df-111">Type</span></span>|<span data-ttu-id="112df-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="112df-112">Runtime</span></span>|
