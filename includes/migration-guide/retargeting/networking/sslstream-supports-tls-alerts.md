### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="e4436-101">SslStream unterstützt TLS-Warnungen</span><span class="sxs-lookup"><span data-stu-id="e4436-101">SslStream supports TLS Alerts</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e4436-102">Details</span><span class="sxs-lookup"><span data-stu-id="e4436-102">Details</span></span>|<span data-ttu-id="e4436-103">Nach einem fehlgeschlagenen TLS-Handshake wird eine <xref:System.IO.IOException?displayProperty=name> mit einer inneren <xref:System.ComponentModel.Win32Exception?displayProperty=name> von dem ersten E/A-Lese-/Schreibvorgang ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e4436-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=name> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=name> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="e4436-104">Der <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=name>-Code für die <xref:System.ComponentModel.Win32Exception?displayProperty=name> kann mithilfe dieser [Kanaldokumentation](https://msdn.microsoft.com/library/windows/desktop/dd721886%28v=vs.85%29.aspx) der TLS-Warnung des Remoteanbieters zugeordnet werden. Weitere Informationen finden Sie unter [RFC 2246: Abschnitt 7.2.2, Fehlerwarnungen](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span><span class="sxs-lookup"><span data-stu-id="e4436-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=name> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=name> can be mapped to the TLS Alert from the remote party using this [Schannel documentation](https://msdn.microsoft.com/library/windows/desktop/dd721886%28v=vs.85%29.aspx).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="e4436-105">Das Verhalten in .NET Framework 4.6.2 und früheren Versionen besteht darin, dass für den Transportkanal (in der Regel eine TCP-Verbindung) ein Timeout während des Schreib- oder Lesevorgangs auftritt, wenn beim Handshake bei der anderen Partei ein Fehler aufgetreten ist und die Verbindung unmittelbar danach zurückgewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="e4436-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>|
|<span data-ttu-id="e4436-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e4436-106">Suggestion</span></span>|<span data-ttu-id="e4436-107">Anwendungen, die Netzwerk-E/A-APIs aufrufen (z.B. <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>) sollten <xref:System.IO.IOException> oder <xref:System.TimeoutException?displayProperty=name> verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e4436-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=name>.</span></span><br/><span data-ttu-id="e4436-108">Die TLS-Warnfunktion ist ab .NET Framework 4.7 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e4436-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="e4436-109">Für Anwendungen für Versionen von .NET Framework von 4.0 bis 4.6.2, die auf einem System mit .NET Framework 4.7 oder höher ausgeführt werden, ist diese Funktion deaktiviert, um die Kompatibilität zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e4436-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="e4436-110">Die folgende Konfigurations-API ist zum Aktivieren oder Deaktivieren des Features für .NET Framework 4.6- oder höhere Anwendungen, die unter .NET Framework 4.7 oder höher ausgeführt werden, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e4436-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span><ul><li><span data-ttu-id="e4436-111">Programmgesteuert:</span><span class="sxs-lookup"><span data-stu-id="e4436-111">Programmatically:</span></span></li></ul><span data-ttu-id="e4436-112">Die folgenden Methoden müssen unmittelbar nach dem Anwendungsstart aufgerufen werden, da ServicePointManager nur einmal initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="e4436-112">Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span><pre><code class="lang-csharp">AppContext.SetSwitch(&quot;TestSwitch.LocalAppContext.DisableCaching&quot;, true);&#13;&#10;AppContext.SetSwitch(&quot;Switch.System.Net.DontEnableTlsAlerts&quot;, true); // Set to &#39;false&#39; to enable the feature in .NET Framework 4.6 - 4.6.2.&#13;&#10;</code></pre><ul><li><span data-ttu-id="e4436-113">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="e4436-113">AppConfig:</span></span></li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableTlsAlerts=true&quot;/&gt;&#13;&#10;&lt;!-- Set to &#39;false&#39; to enable the feature in .NET Framework 4.6 - 4.6.2. --&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><ul><li><span data-ttu-id="e4436-114">Registrierungsschlüssel (globaler Wert für einen Computer):</span><span class="sxs-lookup"><span data-stu-id="e4436-114">Registry key (machine global):</span></span></li></ul><span data-ttu-id="e4436-115">Legen Sie den Wert auf <code>false</code> fest, um das Feature in .NET Framework 4.6 bis 4.6.2 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4436-115">Set the Value to <code>false</code> to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span><pre><code>Key = HKLM\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts&#13;&#10;Type = String&#13;&#10;Value = &quot;true&quot;&#13;&#10;</code></pre>|
|<span data-ttu-id="e4436-116">Bereich</span><span class="sxs-lookup"><span data-stu-id="e4436-116">Scope</span></span>|<span data-ttu-id="e4436-117">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e4436-117">Edge</span></span>|
|<span data-ttu-id="e4436-118">Version</span><span class="sxs-lookup"><span data-stu-id="e4436-118">Version</span></span>|<span data-ttu-id="e4436-119">4.7</span><span class="sxs-lookup"><span data-stu-id="e4436-119">4.7</span></span>|
|<span data-ttu-id="e4436-120">Typ</span><span class="sxs-lookup"><span data-stu-id="e4436-120">Type</span></span>|<span data-ttu-id="e4436-121">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="e4436-121">Retargeting</span></span>|
|<span data-ttu-id="e4436-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e4436-122">Affected APIs</span></span>|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.WebRequest?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.Http?displayProperty=nameWithType></li></ul>|
