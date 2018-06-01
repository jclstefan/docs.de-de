### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="4d322-101">RFC 3986 kann jetzt verwendet werden, um System.Uri mit Escapezeichen zu versehen</span><span class="sxs-lookup"><span data-stu-id="4d322-101">System.Uri escaping now supports RFC 3986</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4d322-102">Details</span><span class="sxs-lookup"><span data-stu-id="4d322-102">Details</span></span>|<span data-ttu-id="4d322-103">URI-Escapezeichen in .NET Framework 4.5 wurden geändert, um [RFC 3986](http://tools.ietf.org/html/rfc3986) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4d322-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](http://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="4d322-104">Die speziellen Änderungen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4d322-104">Specific changes include:</span></span><ul><li><span data-ttu-id="4d322-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> versieht reservierte Zeichen basierend auf RFC 3986 mit Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="4d322-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="4d322-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> versieht reservierte Zeichen nicht mit Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="4d322-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> does not escape reserved characters.</span></span></li><li><span data-ttu-id="4d322-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> löst keine Ausnahme aus, wenn eine ungültige Escapesequenz gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="4d322-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="4d322-108">Bei nicht reservierten Zeichen mit Escapezeichen werden letztere entfernt.</span><span class="sxs-lookup"><span data-stu-id="4d322-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>|
|<span data-ttu-id="4d322-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4d322-109">Suggestion</span></span>|<ul><li><span data-ttu-id="4d322-110">Aktualisieren Sie die Anwendungen, um nicht auf <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> angewiesen zu sein, wenn Sie bei einer ungültigen Escapesequenz eine Ausnahme auslösen möchten.</span><span class="sxs-lookup"><span data-stu-id="4d322-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="4d322-111">Derartige Sequenzen müssen jetzt direkt erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="4d322-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="4d322-112">Erwarten Sie zudem, dass URI- und Datenzeichenfolgen mit und ohne Escapezeichen zwischen .NET Framework 4.0 und .NET Framework 4.5 möglicherweise abweichen und für .NET-Versionen nicht direkt verglichen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="4d322-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="4d322-113">Stattdessen sollten sie in einer einzelnen .NET-Version analysiert und normalisiert werden, bevor Vergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4d322-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>|
|<span data-ttu-id="4d322-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="4d322-114">Scope</span></span>|<span data-ttu-id="4d322-115">Gering</span><span class="sxs-lookup"><span data-stu-id="4d322-115">Minor</span></span>|
|<span data-ttu-id="4d322-116">Version</span><span class="sxs-lookup"><span data-stu-id="4d322-116">Version</span></span>|<span data-ttu-id="4d322-117">4.5</span><span class="sxs-lookup"><span data-stu-id="4d322-117">4.5</span></span>|
|<span data-ttu-id="4d322-118">Typ</span><span class="sxs-lookup"><span data-stu-id="4d322-118">Type</span></span>|<span data-ttu-id="4d322-119">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4d322-119">Runtime</span></span>|
|<span data-ttu-id="4d322-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4d322-120">Affected APIs</span></span>|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
