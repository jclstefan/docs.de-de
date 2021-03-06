---
title: Hierarchisches Konfigurationsmodell
ms.date: 03/30/2017
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
ms.openlocfilehash: 233a8d4ba36835ab26e0c4a8cd044cf60d497a0b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806629"
---
# <a name="hierarchical-configuration-model"></a>Hierarchisches Konfigurationsmodell
In diesem Beispiel wird veranschaulicht, wie eine Hierarchie von Konfigurationsdateien für Dienste implementiert wird. Es wird auch gezeigt, wie Bindungen, Dienstverhalten und Endpunktverhalten von höheren Ebenen in der Hierarchie geerbt werden.  
  
## <a name="sample-details"></a>Beispieldetails  
 Eine der Funktionen für WCF in entwickelten [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] ist die Verbesserung des hierarchischen Konfigurationsmodells. Ein hierarchisches Konfigurationsmodell ist z. B. das Modell, das von Machine.config -> Rootweb.config -> Web.config definiert wurde. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] werden die Bindungen und Verhaltensweisen, die in den oberen Ebenen der Konfigurationshierarchie definiert werden, zum Dienst ohne explizite Konfiguration hinzugefügt. In diesem Beispiel wird gezeigt, wie die Dienstkonfiguration basierend auf Konfigurationselementen vereinfacht werden kann, die auf Computer- oder Anwendungsebene definiert sind.  
  
 Dieses Beispiel umfasst neun Dienste, die in drei Hierarchieebenen definiert sind. `Service1` befindet sich auf der Stammebene. `Service2` und `Service3` erben die Standardelemente von `Service1`. `Service4`, `Service5`, `Service6` und `Service7` werden auf einer dritten Ebene der Hierarchie definiert und erben die Standardelemente von `Service3`. `Service10` und `Service11` befinden sich schließlich auf einer vierten Ebene der Hierarchie.  
  
 Alle Dienste implementieren den `IDesc`-Vertrag. Nachfolgend wird die Definition der `IDesc`-Schnittstelle mit den in dieser Schnittstelle verfügbar gemachten Methoden anzeigt. Die `IDesc`-Schnittstelle wird in Service1.cs definiert.  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 Die Implementierung dieser Methoden durch die Dienste ist einfach. `ListEndpoints` durchläuft alle Dienstendpunkte und gibt eine Liste aller Endpunkte des Diensts zurück. `ListServiceBehaviors` durchläuft alle dem Dienst hinzugefügten Verhaltensweisen und gibt eine Liste mit allen dem Dienst zugeordneten Dienstverhaltensweisen zurück. `ListEndpointBehaviors` verhält sich ähnlich wie `ListServiceBehaviors`, gibt jedoch eine Liste mit Verhaltensweisen von Endpunkten zurück.  
  
 Diese Implementierung ermöglicht es, dass der Client die Anzahl der vom Dienst verfügbar gemachten Endpunkte und die dem Dienst hinzugefügten Verhaltensweisen und Endpunktverhaltensweisen kennt. Der Client, der als Teil des Beispiels implementiert wurde, fügt allen Diensten in der Projektmappe einen Dienstverweis hinzu und zeigt diese Elemente für jeden der Dienste an.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
#### <a name="to-run-the-client"></a>So führen Sie den Client aus  
  
1.  Öffnen Sie die Datei ConfigHierarchicalModel.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Wenn das Clientprojekt nicht bereits als Startprojekt eingerichtet ist, führen Sie folgende Schritte aus.  
  
    1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, und wählen Sie dann **Eigenschaften**.  
  
    2.  In **allgemeine Eigenschaften**Option **Startprojekt**, und klicken Sie dann auf **einzelnes Startprojekt**.  
  
    3.  Aus der **einzelnes Startprojekt** Dropdownliste, wählen **Client**.  
  
    4.  Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
3.  Drücken Sie STRG+UMSCHALT+B, um das Beispiel zu erstellen.  
  
4.  Drücken Sie STRG + F5, um den Client auszuführen.  
  
> [!NOTE]
>  Wenn diese Schritte nicht funktionieren, stellen Sie mithilfe der folgenden Schritte sicher, dass die Umgebung ordnungsgemäß eingerichtet wurde.  
>   
>  1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
> 2.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
> 3.  Um das Beispiel in einer einzelnen oder Konfigurationen mit mehreren Computern ausführen, befolgen Sie die Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele für AppFabric-Management](http://go.microsoft.com/fwlink/?LinkId=193960)
