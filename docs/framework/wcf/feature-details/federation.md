---
title: Verbund
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation [WCF]
ms.assetid: 2f1e646f-8361-48d4-9d5d-1b961f31ede4
ms.openlocfilehash: d69de8c01a23eff5314220a10a51f6487080df41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496755"
---
# <a name="federation"></a>Verbund
Dieses Thema enthält eine kurze Übersicht über den Begriff Verbundsicherheit. Darüber hinaus wird die Windows Communication Foundation (WCF)-Unterstützung für die Bereitstellung von verbundsicherheitsarchitekturen beschrieben. Eine beispielanwendung, Verbund veranschaulicht, finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
## <a name="definition-of-federated-security"></a>Definition von Verbundsicherheit  
 Verbundsicherheit ermöglicht eine saubere Trennung zwischen dem Dienst, auf den ein Client zugreift, und den dazugehörigen Authentifizierungs- und Autorisierungsvorgängen. Darüber hinaus aktiviert Verbundsicherheit die Zusammenarbeit über mehrere Systeme, Netzwerke und Organisationen in anderen Vertrauensbereichen.  
  
 WCF bietet Unterstützung für die Erstellung und Bereitstellung von verteilten Systemen, die verbundsicherheit verwenden.  
  
### <a name="elements-of-a-federated-security-architecture"></a>Elemente einer Verbundsicherheitsarchitektur  
 Die Verbundsicherheitsarchitektur verfügt über drei Hauptelemente (siehe Beschreibung in der folgenden Tabelle).  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Domäne/Bereich|Eine einzelne Einheit von Sicherheitsverwaltung oder -vertrauen. Eine typische Domäne könnte eine einzelne Organisation einschließen.|  
|Verbund|Eine Auflistung von Domänen, die Vertrauenswürdigkeit bewiesen haben. Die Ebene der Vertrauenswürdigkeit ändert sich möglicherweise, schließt aber in der Regel die Authentifizierung und fast immer die Autorisierung ein. Zu einem typischen Verbund kann eine Anzahl an Organisationen gehören, die Vertrauen für einen gemeinsamen Zugriff auf Ressourcen aufgebaut haben.|  
|Sicherheitstokendienst (STS; Security Token Service)|Hierbei handelt es sich um einen Webdienst, der Sicherheitstoken herausgibt, d. h. es werden basierend auf Beweisen, die als vertrauenswürdig eingestuft werden, Assertionen erstellt. Dies bildet die Grundlage für die Vertrauensvermittlung zwischen Domänen.|  
  
### <a name="example-scenario"></a>Beispielszenario  
 Die folgende Abbildung zeigt ein Beispiel für Verbundsicherheit.  
  
 ![Verbund](../../../../docs/framework/wcf/feature-details/media/typicalfederatedsecurityscenario.gif "TypicalFederatedSecurityScenario")  
  
 Dieses Szenario enthält zwei Organisationen: A und B. Organisation B hat eine Webressource (einen Webdienst), die einige Benutzer in der Organisation A als wertvoll betrachten.  
  
> [!NOTE]
>  In diesem Abschnitt sind die verwendeten Begriffe *Ressource*, *Service*, und *-Webdienst* austauschbar.  
  
 Üblicherweise fordert Organisation B, dass ein Benutzer der Organisation A eine gültige Form der Authentifizierung bereitstellt, bevor der Zugriff auf den Dienst gewährt wird. Darüber hinaus kann die Organisation verlangen, dass der Benutzer für den Zugriff auf die spezifische Ressource autorisiert wird. Eine Art der Problemlösung und Ermöglichung des Zugriffs auf die Ressource in der Organisation B durch die Benutzer in der Organisation A ist folgendermaßen:  
  
-   Benutzer von Organisation A registrieren Ihre Anmeldeinformationen (Benutzername und Kennwort) bei der Organisation B.  
  
-   Während des Zugriffs auf die Ressource geben Benutzer der Organisation A Ihre Anmeldeinformationen an die Organisation B weiter und werden vor Zugriff auf die Ressource authentifiziert.  
  
 Dieser Ansatz hat drei bedeutende Nachteile:  
  
-   Zusätzlich zur Verwaltung der Anmeldeinformationen der lokalen Benutzer muss die Organisation B die Anmeldeinformationen für Benutzer der Organisation A verwalten.  
  
-   Benutzer der Organisation A müssen, abgesehen von den Anmeldeinformationen, die sie sonst für den Zugriff auf die Ressourcen innerhalb der Organisation verwenden, zusätzliche Anmeldeinformationen pflegen (d. h. einen zusätzlichen Benutzernamen und ein zusätzliches Kennwort). Es wird daher empfohlen, denselben Benutzernamen und dasselbe Kennwort für unterschiedliche Dienstsites zu verwenden, wobei es sich um eine anfällige Sicherheitsmaßnahme handelt.  
  
-   Die Architektur nimmt keine Skalierung vor, während weitere Organisationen die Ressource bei Organisation B als wertvoll betrachten.  
  
 Ein alternativer Ansatz, der die zuvor erwähnten Nachteile berücksichtigt, ist die Bereitstellung von Verbundsicherheit. In diesem Ansatz bauen die Organisationen A und B eine Vertrauensbeziehung auf und verwenden STS (Security Token Service), um die Vermittlung des aufgebauten Vertrauens zu ermöglichen.  
  
 In einer Verbundsicherheitsarchitektur wissen Benutzer der Organisation A, dass sie einen gültigen Sicherheitstoken aus STS bei der Organisation vorlegen müssen, der ihren Zugang zum entsprechenden Dienst authentifiziert und autorisiert, wenn sie auf den Webdienst in Organisation B zugreifen möchten.  
  
 Durch die Kontaktaufnahme mit dem STS B erhalten die Benutzer eine andere Dereferenzierungsebene aus der zum STS gehörenden Richtlinie. Sie müssen einen gültigen Sicherheitstoken aus STS A (d. h. den Clientvertrauensbereich) vorweisen, bevor der STS B einen Sicherheitstoken an sie ausgeben kann. Hierbei handelt es sich um eine Folgeerscheinung aus der zwischen den beiden Organisationen aufgebauten Vertrauensbeziehung, wobei impliziert wird, dass Organisation B die Identitäten für Benutzer aus der Organisation A nicht verwalten muss. In der Praxis verfügt der STS B üblicherweise über eine Null-`issuerAddress` und eine `issuerMetadataAddress`. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md). In diesem Fall konsultiert der Client eine lokale Richtlinie STS A. Suchen Diese Konfiguration wird aufgerufen, *home Realm Verbund* und skaliert eine bessere Leistung, da STS B keine Informationen über STS A. verwalten  
  
 Die Benutzer kontaktieren nun den STS bei Organisation A und erhalten einen Sicherheitstoken, indem sie Authentifizierungsanmeldeinformationen vorlegen, die sie normalerweise für den Zugang zu anderen Ressourcen innerhalb der Organisation A verwenden. Hierdurch wird auch das Problem gemindert, dass Benutzer mehrere Sätze an Anmeldeinformationen pflegen müssen oder den gleichen Satz an Anmeldeinformationen für mehrere Dienstsites verwenden.  
  
 Nachdem die Benutzer einen Sicherheitstoken vom STS A erhalten haben, legen Sie den Token dem STS B vor. Organisation B führt die Autorisierung der Benutzeranfragen durch und gibt an die Benutzer einen Sicherheitstoken aus ihrem eigenen Satz an Sicherheitstoken heraus. Die Benutzer können dann ihren Token bei der Ressource bei Organisation B vorlegen und auf den Dienst zugreifen.  
  
## <a name="support-for-federated-security-in-wcf"></a>Unterstützung für Verbundsicherheit in WCF  
 WCF bietet sofort verwendbare Unterstützung für die Bereitstellung von verbundsicherheitsarchitekturen durch die [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
 Die [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) -Element stellt für eine sichere, zuverlässige und interoperable Bindung, die die Verwendung von HTTP als den zugrunde liegenden Transportmechanismus für Anforderung-Antwort-Kommunikation-Format umfasst bereit. Einsatz von Text- und XML als Übertragungsformate für die Codierung.  
  
 Die Verwendung von [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) in einem verbundenen Szenario in zwei Phasen logisch unabhängig, entkoppelt werden, wie in den folgenden Abschnitten beschrieben.  
  
### <a name="phase-1-design-phase"></a>Phase 1: Entwurfsphase  
 Während der Entwurfsphase der Client verwendet die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , die Richtlinie zu lesen, die Dienstendpunkt verfügbar macht, und Anforderungen an den Dienst-Authentifizierung und Autorisierung zu sammeln. Die entsprechenden Proxys werden erzeugt, um das folgende Verbundsicherheitskommunikationsmuster beim Client zu erstellen:  
  
-   Erhalt eines Sicherheitstoken vom STS im Clientvertrauensbereich.  
  
-   Präsentation des Token vor dem STS im Dienstvertrauensbereich.  
  
-   Erhalt eines Sicherheitstoken vom STS im Dienstvertrauensbereich.  
  
-   Präsentation des Token vor dem Dienst für den Zugriff auf den Dienst.  
  
### <a name="phase-2-run-time-phase"></a>Phase 2: Laufzeitphase  
 Während der Phase zur Laufzeit wird der Client instanziiert ein Objekt des WCF-Clientklasse, und führt einen Aufruf mithilfe des WCF-Clients. Das zugrunde liegende Framework von WCF behandelt die zuvor genannten Schritte in der verbundsicherheitskommunikationsmuster und ermöglicht dem Client den Dienst nahtlos zu nutzen.  
  
## <a name="sample-implementation-using-wcf"></a>Beispielimplementierung mithilfe von WCF  
 Die folgende Abbildung zeigt eine beispielimplementierung für eine verbundsicherheitsarchitektur mit systemeigener Unterstützung von WCF.  
  
 ![Verbundsicherheit in WCF](../../../../docs/framework/wcf/feature-details/media/federatedsecurityinwcf.gif "FederatedSecurityInWCF")  
  
### <a name="example-myservice"></a>Beispiel MyService  
 Der Dienst `MyService` macht durch `MyServiceEndpoint` einen einzelnen Endpunkt verfügbar. Die folgende Abbildung zeigt Adresse, Bindung und Vertrag an, die zum Endpunkt gehören.  
  
 ![Verbund](../../../../docs/framework/wcf/feature-details/media/myservice.gif "MyService")  
  
 Der Dienstendpunkt `MyServiceEndpoint` verwendet die [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) und erfordert ein gültiges Security Assertions Markup Language (SAML)-Token mit einer `accessAuthorized` von STS B. ausgestellten Anspruchs Dies wird deklarativ in der Dienstkonfiguration angegeben.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.MyService"      
        behaviorConfiguration='MyServiceBehavior'>  
        <endpoint address=""  
            binding=" wsFederationHttpBinding"  
            bindingConfiguration='MyServiceBinding'  
            contract="Federation.IMyService" />  
   </service>  
  </services>  
  
  <bindings>  
    <wsFederationHttpBinding>  
    <!-- This is the binding used by MyService. It redirects   
    clients to STS-B. -->  
      <binding name='MyServiceBinding'>  
        <security mode="Message">  
           <message issuedTokenType=  
"http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
           <issuer address="http://localhost/FederationSample/STS-B/STS.svc" />  
            <issuerMetadata   
           address=  
"http://localhost/FederationSample/STS-B/STS.svc/mex" />  
         <requiredClaimTypes>  
            <add claimType="http://tempuri.org:accessAuthorized" />  
         </requiredClaimTypes>  
        </message>  
      </security>  
      </binding>  
    </wsFederationHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <behavior name='MyServiceBehavior'>  
      <serviceAuthorization   
operationRequirementType="FederationSample.MyServiceOperationRequirement, MyService" />  
       <serviceCredentials>  
         <serviceCertificate findValue="CN=FederationSample.com"  
         x509FindType="FindBySubjectDistinguishedName"  
         storeLocation='LocalMachine'  
         storeName='My' />  
      </serviceCredentials>  
    </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
> [!NOTE]
>  Ein Punkt über die für `MyService` erforderlichen Ansprüche sollte beachtet werden. Die zweite Abbildung zeigt, dass `MyService` ein SAML-Token mit einem `accessAuthorized`-Anspruch erfordert. Genauer gesagt gibt dies den Anspruchstyp an, den `MyService` erfordert. Der vollständig qualifizierte Name der dieser Anspruchstyp ist http://tempuri.org:accessAuthorized (zusammen mit dem zugehörigen Namespace), der in der Konfigurationsdatei des Diensts verwendet wird. Der Wert dieses Anspruchs zeigt das Vorhandensein dieses Anspruchs an und wird als von STS B auf `true` festgelegt angenommen.  
  
 Zur Laufzeit wird diese Richtlinie von der `MyServiceOperationRequirement`-Klasse erzwungen, die als Teil von `MyService` implementiert ist.  
  
 [!code-csharp[C_Federation#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#0)]
 [!code-vb[C_Federation#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#0)]  
[!code-csharp[C_Federation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#1)]
[!code-vb[C_Federation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#1)]  
  
#### <a name="sts-b"></a>STS B  
 Die folgende Abbildung zeigt den STS B. Wie zuvor erwähnt, ist ein STS (Security Token Service) auch ein Webdienst und kann über zugehörige Endpunkte, Richtlinien usw. verfügen.  
  
 ![Verbund](../../../../docs/framework/wcf/feature-details/media/msservicestsb.gif "MsServiceSTSB")  
  
 STS B macht einen einzelnen Endpunkt namens `STSEndpoint` verfügbar, der verwendet werden kann, um das Sicherheitstoken anzufordern. STS B gibt insbesondere SAML-Token mit `accessAuthorized`-Anspruch heraus, die der `MyService`-Dienstsite vorgelegt werden können, um Zugriff auf den Dienst zu erhalten. Allerdings erfordert STS B, dass Benutzer ein gültiges SAML-Token vorlegen, das von STS A herausgegeben wurde und den `userAuthenticated`-Anspruch enthält. Dies wird deklarativ in der STS-Konfiguration angegeben.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.STS_B" behaviorConfiguration=  
     "STS-B_Behavior">  
    <endpoint address=""  
              binding="wsFederationHttpBinding"  
              bindingConfiguration='STS-B_Binding'  
      contract="FederationSample.ISts" />  
    </service>  
  </services>  
  <bindings>  
    <wsFederationHttpBinding>  
    <!-- This is the binding used by STS-B. It redirects clients to   
         STS-A. -->  
      <binding name='STS-B_Binding'>  
        <security mode='Message'>  
          <message issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
          <issuer address='http://localhost/FederationSample/STS-A/STS.svc' />  
          <issuerMetadata address='http://localhost/FederationSample/STS-A/STS.svc/mex'/>  
          <requiredClaimTypes>  
            <add claimType='http://tempuri.org:userAuthenticated'/>  
          </requiredClaimTypes>  
          </message>  
        </security>  
    </binding>  
   </wsFederationHttpBinding>  
  </bindings>  
  <behaviors>  
  <behavior name='STS-B_Behavior'>  
    <serviceAuthorization   operationRequirementType='FederationSample.STS_B_OperationRequirement, STS_B' />  
    <serviceCredentials>  
      <serviceCertificate findValue='CN=FederationSample.com'  
      x509FindType='FindBySubjectDistinguishedName'  
       storeLocation='LocalMachine'  
       storeName='My' />  
     </serviceCredentials>  
   </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
> [!NOTE]
>  In diesem Fall die `userAuthenticated` Anspruch ist der Typ des Anspruchs, der vom STS B. benötigt wird Der vollständig qualifizierte Name der dieser Anspruchstyp ist http://tempuri.org:userAuthenticated (zusammen mit dem zugehörigen Namespace), der in der STS-Konfigurationsdatei verwendet wird. Der Wert dieses Anspruchs zeigt das Vorhandensein dieses Anspruchs an und wird als von STS A auf `true` festgelegt angenommen.  
  
 Zur Laufzeit erzwingt die `STS_B_OperationRequirement`-Klasse diese Richtlinie, die als Teil von STS B implementiert ist.  
  
 [!code-csharp[C_Federation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#2)]
 [!code-vb[C_Federation#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#2)]  
  
 Wenn die Zugriffsprüfung klar ist, gibt STS B ein SAML-Token mit dem `accessAuthorized`-Anspruch aus.  
  
 [!code-csharp[C_Federation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#3)]
 [!code-vb[C_Federation#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#3)]  
  
#### <a name="sts-a"></a>STS A  
 Die folgende Abbildung zeigt den STS A.  
  
 ![Verbund](../../../../docs/framework/wcf/feature-details/media/sts-b.gif "STS_B")  
  
 Ähnlich wie beim STS B ist auch der STS A ein Webdienst, der Sicherheitstoken herausgibt und einen einzelnen Endpunkt für diesen Zweck zur Verfügung stellt. Allerdings verwendet er eine andere Bindung (`wsHttpBinding`) und erfordert, dass Benutzer eine gültige [!INCLUDE[infocard](../../../../includes/infocard-md.md)] mit `emailAddress`-Anspruch vorlegen. Als Antwort gibt er SAML-Token mit dem `userAuthenticated`-Anspruch heraus. Dies wird deklarativ in der Dienstkonfiguration angegeben.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="FederationSample.STS_A" behaviorConfiguration="STS-A_Behavior">  
      <endpoint address=""  
                binding="wsHttpBinding"  
                bindingConfiguration="STS-A_Binding"  
                contract="FederationSample.ISts">  
       <identity>  
       <certificateReference findValue="CN=FederationSample.com"    
                       x509FindType="FindBySubjectDistinguishedName"  
                       storeLocation="LocalMachine"   
                       storeName="My" />  
       </identity>  
    <endpoint>  
  </service>  
</services>  
  
<bindings>  
  <wsHttpBinding>  
  <!-- This is the binding used by STS-A. It requires users to present  
   a CardSpace. -->  
    <binding name='STS-A_Binding'>  
      <security mode='Message'>  
        <message clientCredentialType="CardSpace" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
  
<behaviors>  
  <behavior name='STS-A_Behavior'>  
    <serviceAuthorization operationRequirementType=  
     "FederationSample.STS_A_OperationRequirement, STS_A" />  
      <serviceCredentials>  
  <serviceCertificate findValue="CN=FederationSample.com"  
                     x509FindType='FindBySubjectDistinguishedName'  
                     storeLocation='LocalMachine'  
                     storeName='My' />  
      </serviceCredentials>  
    </behavior>  
  </behaviors>  
</system.serviceModel>  
```  
  
 Zur Laufzeit erzwingt die `STS_A_OperationRequirement`-Klasse diese Richtlinie, die als Teil von STS A implementiert ist.  
  
 [!code-csharp[C_Federation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#4)]
 [!code-vb[C_Federation#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#4)]  
  
 Ist der Zugang `true`, gibt STS A ein SAML-Token mit `userAuthenticated`-Anspruch heraus.  
  
 [!code-csharp[C_Federation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federation/cs/source.cs#5)]
 [!code-vb[C_Federation#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federation/vb/source.vb#5)]  
  
### <a name="client-at-organization-a"></a>Client bei Organisation A  
 Die folgende Abbildung zeigt den Client bei Organisation A sowie die Schritte zur Durchführung eines `MyService`-Dienstaufrufs. Der Vollständigkeit halber sind auch die anderen funktionalen Komponenten aufgeführt.  
  
 ![Verbund](../../../../docs/framework/wcf/feature-details/media/federationclienta.gif "FederationClientA")  
  
## <a name="summary"></a>Zusammenfassung  
 Verbundsicherheit liefert eine klare Trennung der Verantwortungsbereiche und unterstützt den Aufbau einer sicheren und skalierbaren Dienstarchitektur. WCF bietet als Plattform für die Erstellung und Bereitstellung von verteilten Anwendungen die systemeigene Unterstützung für die Implementierung von verbundsicherheit.  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)
