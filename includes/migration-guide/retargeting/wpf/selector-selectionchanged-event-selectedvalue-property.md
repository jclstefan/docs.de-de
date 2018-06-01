### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="22f00-101">Selector-Klasse – SelectionChanged-Ereignis und SelectedValue-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="22f00-101">Selector SelectionChanged event and SelectedValue property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="22f00-102">Details</span><span class="sxs-lookup"><span data-stu-id="22f00-102">Details</span></span>|<span data-ttu-id="22f00-103">Ab .NET Framework 4.7.1 aktualisiert ein <xref:System.Windows.Controls.Primitives.Selector>-Objekt immer den Wert der zugehörigen <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft, bevor das Ereignis <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> ausgelöst wird, wenn die Auswahl geändert wird.</span><span class="sxs-lookup"><span data-stu-id="22f00-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="22f00-104">Dadurch wird die „SelectedValue“-Eigenschaft mit den anderen Auswahleigenschaften (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> und <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>) in Einklang gebracht, die vor dem Auslösen des Ereignisses aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="22f00-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="22f00-105">In .NET Framework 4.7 und früheren Versionen wurde „SelectValue“ in den meisten Fällen vor der Auslösung des Ereignisses aktualisiert. Wenn die Änderung der Auswahl durch Ändern der <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft ausgelöst wurde, fand die Aktualisierung jedoch nach dem Auslösen des Ereignisses statt.</span><span class="sxs-lookup"><span data-stu-id="22f00-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>|
|<span data-ttu-id="22f00-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="22f00-106">Suggestion</span></span>|<span data-ttu-id="22f00-107">Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="22f00-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the <code>&lt;runtime&gt;</code> section of the application configuration file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="22f00-108">Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="22f00-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the <code>&lt;runtime&gt;</code> section of the application .configuration file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="22f00-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="22f00-109">Scope</span></span>|<span data-ttu-id="22f00-110">Gering</span><span class="sxs-lookup"><span data-stu-id="22f00-110">Minor</span></span>|
|<span data-ttu-id="22f00-111">Version</span><span class="sxs-lookup"><span data-stu-id="22f00-111">Version</span></span>|<span data-ttu-id="22f00-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="22f00-112">4.7.1</span></span>|
|<span data-ttu-id="22f00-113">Typ</span><span class="sxs-lookup"><span data-stu-id="22f00-113">Type</span></span>|<span data-ttu-id="22f00-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="22f00-114">Retargeting</span></span>|
|<span data-ttu-id="22f00-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="22f00-115">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
