---
title: "Vorgehensweise: Erstellen eines grundlegenden RS-Feeds | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Vorgehensweise: Erstellen eines grundlegenden RS-Feeds
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ermöglicht Ihnen die Erstellung eines Diensts, der einen Syndication\-Feed verfügbar macht.In diesem Thema wird erläutert, wie ein Syndication\-Dienst, der einen RSS Syndication\-Feed verfügbar macht, erstellt wird.  
  
### So erstellen Sie einen grundlegenden Syndication\-Dienst  
  
1.  Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut gekennzeichnet ist.Jeder Vorgang, der als Syndication\-Feed verfügbar gemacht wird, sollte ein <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>\-Objekt zurückgeben.  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  Alle Dienstvorgänge, die das <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut übernehmen, werden HTTP GET\-Anforderungen zugeordnet.Wenn Sie den Vorgang einer anderen HTTP\-Methode zuordnen möchten, verwenden Sie stattdessen <xref:System.ServiceModel.Web.WebInvokeAttribute>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Erstellen eines grundlegenden WCF\-Web\-HTTP\-Diensts](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).  
  
2.  Implementieren Sie den Dienstvertrag.  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3.  Erstellen Sie ein <xref:System.ServiceModel.Syndication.SyndicationFeed>\-Objekt, und fügen Sie einen Autor, eine Kategorie und eine Beschreibung hinzu.  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4.  Erstellen Sie mehrere <xref:System.ServiceModel.Syndication.SyndicationItem>\-Objekte.  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5.  Fügen Sie dem Feed das <xref:System.ServiceModel.Syndication.SyndicationItem> hinzu  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6.  Geben Sie den Feed zurück.  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### So hosten Sie einen Dienst  
  
1.  Erstellen Sie ein <xref:System.ServiceModel.Web.WebServiceHost>\-Objekt.  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2.  Öffnen Sie den Diensthost, und warten Sie, bis der Benutzer die EINGABETASTE drückt.  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### So rufen Sie GetBlog\(\) mit HTTP GET auf  
  
1.  Öffnen Sie den Internet Explorer, geben Sie die folgende URL ein, und drücken Sie die EINGABETASTE: http:\/\/localhost:8000\/BlogService\/GetBlogDie URL enthält die Basisadresse des Diensts \(http:\/\/localhost:8000\/BlogService\), die relative Adresse des Endpunkts und den aufzurufenden Dienstvorgang.  
  
### So rufen Sie GetBlog\(\) aus dem Code auf  
  
1.  Erstellen Sie einen <xref:System.Xml.XmlReader> mit der Basisadresse und der Methode, die Sie aufrufen.  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2.  Rufen Sie die statische <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>\-Methode auf, und übergeben Sie dabei den gerade erstellten <xref:System.Xml.XmlReader>.  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     Dies ruft einen Dienstvorgang auf und füllt einen neuen <xref:System.ServiceModel.Syndication.SyndicationFeed> mit dem vom Dienstvorgang zurückgegebenen Formatierungsprogramm auf.  
  
3.  Greifen Sie auf das Feedobjekt zu.  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## Beispiel  
 Nachfolgend ist die vollständige Codeauflistung für dieses Beispiel angegeben.  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## Kompilieren des Codes  
 Verweisen Sie beim Kompilieren des obigen Codes auf System.ServiceModel.dll und System.ServiceModel.Web.dll.  
  
## Siehe auch  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Web.WebGetAttribute>