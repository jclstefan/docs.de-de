### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="6fd93-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="6fd93-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6fd93-102">Details</span><span class="sxs-lookup"><span data-stu-id="6fd93-102">Details</span></span>|<span data-ttu-id="6fd93-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="6fd93-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="6fd93-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="6fd93-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="6fd93-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6fd93-105">Suggestion</span></span>|<span data-ttu-id="6fd93-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6fd93-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="6fd93-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="6fd93-107">Scope</span></span>|<span data-ttu-id="6fd93-108">Gering</span><span class="sxs-lookup"><span data-stu-id="6fd93-108">Minor</span></span>|
|<span data-ttu-id="6fd93-109">Version</span><span class="sxs-lookup"><span data-stu-id="6fd93-109">Version</span></span>|<span data-ttu-id="6fd93-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="6fd93-110">4.7.1</span></span>|
|<span data-ttu-id="6fd93-111">Typ</span><span class="sxs-lookup"><span data-stu-id="6fd93-111">Type</span></span>|<span data-ttu-id="6fd93-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6fd93-112">Runtime</span></span>|
