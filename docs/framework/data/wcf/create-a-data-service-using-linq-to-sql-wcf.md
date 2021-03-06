---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 5769ff5296d096df41b59104ad0581f0e816c648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362246"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht Entitätsdaten als Datendienst verfügbar. Der reflektionsanbieter ermöglicht es Ihnen, ein Datenmodell zu definieren, die auf einer Klasse basiert, die Member verfügbar macht zurückgegebene ein <xref:System.Linq.IQueryable%601> Implementierung. Damit diese Klassen Aktualisierungen an Daten in der Datenquelle vornehmen können, müssen sie auch die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md). In diesem Thema wird gezeigt, wie LINQ to SQL-Klassen erstellt werden, die mit dem Reflektionsanbieter auf die Northwind-Beispieldatenbank zugreifen, und wie der Datendienst erstellt wird, der auf diesen Datenklassen basiert.  
  
### <a name="to-add-linq-to-sql-classes-to-a-project"></a>So fügen Sie einem Projekt LINQ to SQL-Klassen hinzu  
  
1.  Von in einer Visual Basic- oder c#-Anwendung auf die **Projekt** Menü klicken Sie auf **neues Element hinzufügen**.  
  
2.  Klicken Sie auf die **LINQ to SQL-Klassen** Vorlage.  
  
3.  Ändern Sie den Namen in **Northwind.dbml**.  
  
4.  Klicken Sie auf **Hinzufügen**.  
  
     Die Datei Northwind.dbml wird dem Projekt hinzugefügt, und der Object Relational Designer (O/R-Designer) wird geöffnet.  
  
5.  In **Server**/**Datenbank-Explorer**, erweitern Sie unter Northwind **Tabellen** , und ziehen Sie die `Customers` Tabelle auf den Object Relational Designer (O/R -Designer).  
  
     Eine `Customer`-Entitätsklasse wird erstellt und auf der Entwurfsoberfläche angezeigt.  
  
6.  Wiederholen Sie Schritt 6 für die Tabellen `Orders`, `Order_Details` und `Products`.  
  
7.  Mit der rechten Maustaste in der neue DBML-Datei, die die LINQ to SQL-Klassen, und klicken Sie auf darstellt **Code anzeigen**.  
  
     Dadurch wird die neue Code-Behind-Seite Northwind.cs erstellt, die eine partielle Klassendefinition für die Klasse enthält, die von der <xref:System.Data.Linq.DataContext>-Klasse erbt, in diesem Fall `NorthwindDataContext`.  
  
8.  Ersetzen Sie den Inhalt der Codedatei Northwind.cs durch folgenden Code. Dieser Code implementiert den Reflektionsanbieter, indem er den <xref:System.Data.Linq.DataContext> und von LINQ to SQL generierte Datenklassen erweitert:  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>So erstellen Sie einen Datendienst mit einem LINQ to SQL-basierten Datenmodell  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **neues Element hinzufügen**.  
  
2.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.  
  
3.  Geben Sie einen Namen für den Dienst, und klicken Sie dann auf **OK**.  
  
     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.  
  
4.  Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindDataContext`.  
  
5.  Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     Dies ermöglicht es berechtigten Clients, auf Ressourcen für die drei angegebenen Entitätenmengen zuzugreifen.  
  
6.  Um den Datendienst Northwind.svc mithilfe eines Webbrowsers zu testen, führen Sie die Anweisungen im Thema [Zugriff auf den Dienst über einen Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)  
 [: Erstellen eines Datendiensts mit dem Reflektionsanbieter](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
