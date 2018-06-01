---
title: Gründe für die vorhandenen .NET apps für Cloud-optimierte Anwendungen zu aktualisieren.
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Gründe für die vorhandenen .NET apps für Cloud-optimierte Anwendungen zu aktualisieren.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: a874a742f6a5b32e15040ad0a237f0e0fa7908dc
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a><span data-ttu-id="b5129-103">Gründe für die vorhandenen .NET apps für Cloud-optimierte Anwendungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b5129-103">Reasons to modernize existing .NET apps to Cloud-Optimized applications</span></span>

<span data-ttu-id="b5129-104">Mit einer Cloud-optimierten Anwendung können Sie schnell und wiederholt zuverlässige für Ihre Kunden Anwendungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b5129-104">With a Cloud-Optimized application, you can rapidly and repeatedly deliver reliable applications to your customers.</span></span> <span data-ttu-id="b5129-105">Durch Verschieben großer die operative Komplexität Ihrer App für die Plattform erhalten Sie wichtige Flexibilität und Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="b5129-105">You gain essential agility and reliability by deferring much of the operational complexity of your app to the platform.</span></span>

<span data-ttu-id="b5129-106">Wenn Sie nicht Ihren Computer nach der Zeit schnell vermarkten Sie Ihrer app zu versenden wird der Markt anvisierten wurden entwickelt.</span><span class="sxs-lookup"><span data-stu-id="b5129-106">If you can't get your applications to market quickly, by the time you ship your app, the market you were targeting will have evolved.</span></span> <span data-ttu-id="b5129-107">Sie können möglicherweise zu spät, unabhängig davon, wie gut die Anwendung entworfen oder entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5129-107">You might be too late, no matter how well the application was architected or engineered.</span></span> <span data-ttu-id="b5129-108">Sie können fehlschlagen oder volle Potenzial nicht erreichen, da app-Bereitstellung mit den Anforderungen des Marktes nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5129-108">You might be failing or not reaching your full potential because you can't sync app delivery with the needs of the market.</span></span>

<span data-ttu-id="b5129-109">Die Notwendigkeit einer kontinuierlichen Business Innovation schiebt Entwicklungs- und Betriebsteams auf den Grenzwert.</span><span class="sxs-lookup"><span data-stu-id="b5129-109">The need for continuous business innovation pushes development and operations teams to the limit.</span></span> <span data-ttu-id="b5129-110">Die einzige Möglichkeit, die Flexibilität zu erzielen, fortlaufende Business Innovation benötigten wird durch Ihre Anwendungen mit Technologien wie Container und anwendungsspezifische Cloudoptimiertes Prinzipien Modernisierung.</span><span class="sxs-lookup"><span data-stu-id="b5129-110">The only way to achieve the agility you need in continuous business innovation is by modernizing your applications with technologies like containers and specific Cloud-Optimized application principles.</span></span>

<span data-ttu-id="b5129-111">Entscheidend ist, bei eine Organisation erstellt und verwaltet Anwendungen, die Cloud optimiert sind, fügen Sie Lösungen in die Hände von Kunden früher und können neue Ideen vermarkten, wenn sie relevant sind.</span><span class="sxs-lookup"><span data-stu-id="b5129-111">The bottom line is that when an organization builds and manages applications that are Cloud-Optimized, it can put solutions in the hands of customers sooner and bring new ideas to market when they are relevant.</span></span>

## <a name="cloud-optimized-application-principles-and-tenets"></a><span data-ttu-id="b5129-112">Cloud-optimierten Anwendung Prinzipien und Grundsätze</span><span class="sxs-lookup"><span data-stu-id="b5129-112">Cloud-Optimized application principles and tenets</span></span> 

<span data-ttu-id="b5129-113">Verbesserungen in der Cloud sind größtenteils konzentriert sich zwei Ziele zu erreichen: senken und die Wachstum verbessern, indem Sie die Flexibilität zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b5129-113">Improvements in the cloud are mostly focused on meeting two goals: Reduce costs and improve business growth by improving agility.</span></span> <span data-ttu-id="b5129-114">Diese Ziele werden erzielt, indem Prozesse vereinfacht und Unstimmigkeiten verringern, wenn freigeben und Applications anzubieten.</span><span class="sxs-lookup"><span data-stu-id="b5129-114">These goals are achieved by simplifying processes and reducing friction when you release and ship applications.</span></span>

<span data-ttu-id="b5129-115">Die Anwendung ist Cloud-optimiert, wenn Sie kann in eine agile app unabhängig von anderen lokalen apps Weise entwickeln, und lassen Sie anschließend, automatische Skalierung bereitstellen, überwachen und Problembehandlung für Ihre app in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="b5129-115">Your application is Cloud-Optimized if you can-in an agile manner-develop your app autonomously from other on-premises apps, and then release, deploy, auto-scale, monitor, and troubleshoot your app in the cloud.</span></span>

<span data-ttu-id="b5129-116">Der Schlüssel ist *Agilität*.</span><span class="sxs-lookup"><span data-stu-id="b5129-116">The key is *agility*.</span></span> <span data-ttu-id="b5129-117">Agilität kann nicht ausgeliefert werden, es sei denn, Sie jede Produktion Bereitstellung auf ein absolutes Minimum reduzieren sowie Dev/Test-Umgebungsprobleme.</span><span class="sxs-lookup"><span data-stu-id="b5129-117">You can't ship with agility unless you reduce to an absolute minimum any deployment-to-production issues and dev/test environment issues.</span></span> <span data-ttu-id="b5129-118">Container (insbesondere Docker als de facto Standard) und verwaltete Dienste wurden speziell für diesen Zweck entwickelt.</span><span class="sxs-lookup"><span data-stu-id="b5129-118">Containers (specifically, Docker, as a de facto standard) and managed services were designed specifically for this purpose.</span></span>

<span data-ttu-id="b5129-119">Um die Flexibilität zu erzielen, benötigen Sie auch automatisierte DevOps-Prozesse, die für CI-CD Pipelines basieren, die in der Cloud skalierbar Plattformen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="b5129-119">To achieve agility, you also need automated DevOps processes that are based on CI/CD pipelines that release to scalable platforms in the cloud.</span></span> <span data-ttu-id="b5129-120">CI-CD-Plattformen (z. B. Visual Studio Team Services oder Jenkins), die eine skalierbare und robuste Cloudplattform (z. B. Azure App Service, Azure Service Fabric oder Azure Kubernetes-Dienst) bereitstellen, sind wichtige Technologien für Flexibilität in der Cloud zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b5129-120">CI/CD platforms (like Visual Studio Team Services or Jenkins) that deploy to a scalable and resilient cloud platform (like Azure App Service, Azure Service Fabric or Azure Kubernetes Service) are key technologies for achieving agility in the cloud.</span></span>

<span data-ttu-id="b5129-121">Die folgende Liste beschreibt die wichtigsten Grundsätze oder Methoden für die Cloud optimierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b5129-121">The following list describes the main tenets or practices for Cloud-Optimized applications.</span></span> <span data-ttu-id="b5129-122">Beachten Sie, dass alle oder nur einige dieser Prinzipien durch, in einem progressiven oder inkrementellen Ansatz zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="b5129-122">Note that you can adopt all or only some of these principles, in a progressive or incremental approach:</span></span>

-   <span data-ttu-id="b5129-123">**Container**.</span><span class="sxs-lookup"><span data-stu-id="b5129-123">**Containers**.</span></span> <span data-ttu-id="b5129-124">Container bieten die Möglichkeit, die anwendungsabhängigkeiten mit der Anwendung selbst enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5129-124">Containers give you the ability to include application dependencies with the application itself.</span></span> <span data-ttu-id="b5129-125">Containerization reduziert erheblich die Anzahl der Probleme, die auftreten können, wenn Sie in produktionsumgebungen bereitstellen oder im staging-Umgebungen zu testen.</span><span class="sxs-lookup"><span data-stu-id="b5129-125">Containerization significantly reduces the number of issues you might encounter when you deploy to production environments or test in staging environments.</span></span> <span data-ttu-id="b5129-126">Letztlich zu Containern die Flexibilität von Anwendungen verbessern.</span><span class="sxs-lookup"><span data-stu-id="b5129-126">Ultimately, containers improve the agility of application delivery.</span></span>

-   <span data-ttu-id="b5129-127">**Robusten und skalierbaren Cloud**.</span><span class="sxs-lookup"><span data-stu-id="b5129-127">**Resilient and scalable cloud**.</span></span> <span data-ttu-id="b5129-128">Die Cloud bietet eine Plattform, die verwaltete, elastische, skalierbare und robuste ist.</span><span class="sxs-lookup"><span data-stu-id="b5129-128">The cloud provides a platform that is managed, elastic, scalable, and resilient.</span></span> <span data-ttu-id="b5129-129">Diese Merkmale werden grundlegende Kosten Verbesserungen erhalten und hoch verfügbar und zuverlässige Anwendungen in einer kontinuierlichen Bereitstellung ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="b5129-129">These characteristics are fundamental to gain cost improvements and ship highly available and reliable applications in a continuous delivery.</span></span> <span data-ttu-id="b5129-130">Verwaltete Dienste wie verwaltete Datenbanken, cache, wie ein Dienst (CaaS), und klicken Sie auf verwalteten Speicher fundamentale Teile in die Wartungskosten einer Anwendung aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5129-130">Managed services like managed databases, managed cache as a service (CaaS), and managed storage are fundamental pieces in alleviating the maintenance costs of your application.</span></span>

-   <span data-ttu-id="b5129-131">**Überwachung**.</span><span class="sxs-lookup"><span data-stu-id="b5129-131">**Monitoring**.</span></span> <span data-ttu-id="b5129-132">Sie können keine zuverlässigen Anwendung haben, ohne eine gute Möglichkeit zum Erkennen und zu diagnostizieren, Ausnahmen und Leistungsproblemen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b5129-132">You can't have a reliable application without having a good way to detect and diagnose exceptions and application performance issues.</span></span> <span data-ttu-id="b5129-133">In diesem Fall müssen Sie eine umsetzbare Erkenntnisse über die anwendungsverwaltung für die Leistung und sofortige Analysen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b5129-133">You need to get actionable insights through application performance management and instant analytics.</span></span>

-   <span data-ttu-id="b5129-134">**DevOps Kultur und der kontinuierlichen Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="b5129-134">**DevOps culture and continuous delivery**.</span></span> <span data-ttu-id="b5129-135">Einsetzen von DevOps-Methoden muss in der Teams nicht mehr in unabhängigen Silos funktioniert kulturellen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b5129-135">Adopting DevOps practices requires a cultural change in which teams no longer work in independent silos.</span></span> <span data-ttu-id="b5129-136">CI-CD-Pipelines sind möglich, nur, wenn eine erhöhte Zusammenarbeit zwischen Entwicklungs- und IT-Betriebsteams, die von Containern und CI-CD Tools unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5129-136">CI/CD pipelines are possible only when there is an increased collaboration between development and IT operations teams, supported by containers and CI/CD tools.</span></span>

<span data-ttu-id="b5129-137">Abbildung 4 – 2 zeigt die wichtigsten optionalen Säulen einer Cloud-optimierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b5129-137">Figure 4-2 shows the main optional pillars of a Cloud-Optimized application.</span></span> <span data-ttu-id="b5129-138">Weitere Säulen, die Sie implementieren, die readier Ihrer Anwendung aus, um die kundenerwartungen erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b5129-138">The more pillars you implement, the readier your application will be to succeed in meeting your customers' expectations.</span></span>

> ![Main Säulen einer Cloud-optimierten Anwendung](./media/image2.png)
>
> <span data-ttu-id="b5129-140">**Abbildung 4-2**.</span><span class="sxs-lookup"><span data-stu-id="b5129-140">**Figure 4-2.**</span></span> <span data-ttu-id="b5129-141">Main Säulen einer Cloud-optimierten Anwendung</span><span class="sxs-lookup"><span data-stu-id="b5129-141">Main pillars of a Cloud-Optimized application</span></span>

<span data-ttu-id="b5129-142">Kurz gesagt, ist eine Cloud-optimierten Anwendung eine Methode zum Erstellen und Verwalten von Anwendungen, die von der Cloud computing-Modell, beim Einsatz einer Kombination von Containern, verwaltete Cloudinfrastruktur, robusten anwendungstechniken nutzt, Überwachung, fortlaufende Übermittlung und DevOps, ohne die Notwendigkeit neu entwerfe und Ihre vorhandenen Anwendungen umgeschrieben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b5129-142">To summarize, a Cloud-Optimized application is an approach to building and managing applications that takes advantage of the cloud computing model, while using a combination of containers, managed cloud infrastructure, resilient application techniques, monitoring, continuous delivery, and DevOps, all without the need to rearchitect and recode your existing applications.</span></span>

<span data-ttu-id="b5129-143">Diese Technologien und Vorgehensweisen kann Ihrer Organisation schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5129-143">Your organization can adopt these technologies and approaches gradually.</span></span> <span data-ttu-id="b5129-144">Sie müssen nicht alle, alle auf einmal zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="b5129-144">You don't have to embrace all of them, all at once.</span></span> <span data-ttu-id="b5129-145">Sie können diese inkrementell übernehmen Enterprise Prioritäten und Anforderungen der Benutzer abhängig.</span><span class="sxs-lookup"><span data-stu-id="b5129-145">You can adopt them incrementally, depending on enterprise priorities and user needs.</span></span>

## <a name="benefits-of-a-cloud-optimized-application"></a><span data-ttu-id="b5129-146">Vorteile einer Cloud-optimierten Anwendung</span><span class="sxs-lookup"><span data-stu-id="b5129-146">Benefits of a Cloud-Optimized application</span></span>

<span data-ttu-id="b5129-147">Sie erhalten die folgenden Vorteile durch Konvertieren einer vorhandenen Anwendung zu einer Cloud-optimierten Anwendung (ohne Neuentwurf oder Schreiben von Code):</span><span class="sxs-lookup"><span data-stu-id="b5129-147">You can get the following benefits by converting an existing application to a Cloud-Optimized application (without rearchitecting or coding):</span></span>

-   <span data-ttu-id="b5129-148">**Kosten zu senken, da die verwaltete Infrastruktur vom Cloudanbieter gehandhabt wird**.</span><span class="sxs-lookup"><span data-stu-id="b5129-148">**Lower costs, because the managed infrastructure is handled by the cloud provider**.</span></span> <span data-ttu-id="b5129-149">Cloud-optimierte Anwendungen profitieren Sie von der Cloud mithilfe der Out-of-Box-Flexibilität der Cloud, automatische Skalierung und hohe Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="b5129-149">Cloud-Optimized applications get the benefits of the cloud by using the cloud's out-of-the-box elasticity, autoscale, and high availability.</span></span> <span data-ttu-id="b5129-150">Vorteile beziehen sich nicht nur auf die Compute-Funktionen (VMs und Containern), aber auch Ressourcen in der Cloud abhängig wie DBaaS, CaaS und jede Infrastruktur eine Anwendung möglicherweise benötigt.</span><span class="sxs-lookup"><span data-stu-id="b5129-150">Benefits are related not only to the compute features (VMs and containers), but also depend on resources in the cloud, like DBaaS, CaaS, and any infrastructure an application might needed.</span></span>

-   <span data-ttu-id="b5129-151">**Robuste Anwendung und Infrastruktur**.</span><span class="sxs-lookup"><span data-stu-id="b5129-151">**Resilient application and infrastructure**.</span></span> <span data-ttu-id="b5129-152">Wenn Sie in die Cloud migrieren, müssen Sie vorübergehende Fehler zu nutzen; Fehler werden in der Cloud auftreten.</span><span class="sxs-lookup"><span data-stu-id="b5129-152">When you migrate to the cloud, you need to embrace transient failures; failures will occur in the cloud.</span></span> <span data-ttu-id="b5129-153">Darüber hinaus sind Cloudinfrastruktur und Hardwareressourcen "ersetzt" Verkaufschancen für vorübergehende Downtime zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b5129-153">Also, cloud infrastructure and hardware are "replaceable," which increases opportunities for transient downtime.</span></span> <span data-ttu-id="b5129-154">Zur gleichen Zeit erleichtern innere Cloudfunktionen und bestimmte Anwendung Entwicklungstechniken, die resilienz zu implementieren und Automatisieren von unerwarteten Fehlern in der Cloud wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b5129-154">At the same time, inner cloud capabilities and certain application development techniques that implement resiliency and automate recovery make it much easier to recover from unexpected failures in the cloud.</span></span>

-   <span data-ttu-id="b5129-155">**Tiefere Einblicke in die Leistung der Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="b5129-155">**Deeper insights into application performance**.</span></span> <span data-ttu-id="b5129-156">Cloud-Überwachungstools wie Azure Application Insights Visualisierung für Systemüberwachung, Protokollierung und Benachrichtigungen angeben.</span><span class="sxs-lookup"><span data-stu-id="b5129-156">Cloud monitoring tools like Azure Application Insights provide visualization for health management, logging, and notifications.</span></span> <span data-ttu-id="b5129-157">Überwachungsprotokolle können Anwendungen einfach Debuggen und zu überwachen, grundlegende für eine zuverlässige Cloudanwendung.</span><span class="sxs-lookup"><span data-stu-id="b5129-157">Audit logs make applications easy to debug and audit, fundamental for a reliable cloud application.</span></span>

-   <span data-ttu-id="b5129-158">**Anwendungsportabilität mit agile Bereitstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b5129-158">**Application portability, with agile deployments**.</span></span> <span data-ttu-id="b5129-159">(Basierend auf den Docker-Modul Linux- oder Windows-Container)-Container bieten die beste Lösung zum Vermeiden von einer Anwendung Cloud gesperrt.</span><span class="sxs-lookup"><span data-stu-id="b5129-159">Containers (either Linux or Windows containers based on Docker Engine) offer the best solution to avoiding a cloud-locked application.</span></span> <span data-ttu-id="b5129-160">Mithilfe von Container und Docker-Hosts mit mehreren Cloud Orchestrators können problemlos zwischen Umgebungen verschieben oder zu einem anderen cloud.</span><span class="sxs-lookup"><span data-stu-id="b5129-160">By using containers, Docker hosts, and multi-cloud orchestrators, you can easily move from one environment or cloud to another.</span></span> <span data-ttu-id="b5129-161">Container vermeiden, die Unstimmigkeiten, die in der Regel in Bereitstellungen auf eine beliebige Umgebung (Phase/Test/Produktionsserver) auftritt.</span><span class="sxs-lookup"><span data-stu-id="b5129-161">Containers eliminate the friction that typically occurs in deployments to any environment (stage/test/production).</span></span>

<span data-ttu-id="b5129-162">All diese Vorteile bieten letztlich Reduzierung der Kosten für Schlüssel für den End-to-End-Anwendungslebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="b5129-162">All of these benefits ultimately provide key cost reductions for your end-to-end application lifecycle.</span></span>

<span data-ttu-id="b5129-163">In den folgenden Abschnitten diese Vorteile ausführlicher erläutert werden, und mit spezieller Technologien verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="b5129-163">In the following sections, these benefits are explained in more detail, and are linked to specific technologies.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b5129-164">[Zurück](index.md)
[Weiter](microsoft-technologies-in-cloud-optimized-applications.md)</span><span class="sxs-lookup"><span data-stu-id="b5129-164">[Previous](index.md)
[Next](microsoft-technologies-in-cloud-optimized-applications.md)</span></span>