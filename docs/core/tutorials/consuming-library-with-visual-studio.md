---
title: Verarbeiten einer Klassenbibliothek mit .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie die Elemente in einer Klassenbibliothek mit Visual Studio 2017 aufrufen.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.openlocfilehash: 0a7002f2a5dba5a5aad32a83a43a933cd2cc5722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a>Verarbeiten einer Klassenbibliothek mit .NET Core in Visual Studio 2017

Nachdem Sie eine Klassenbibliothek anhand der unter [Building a C# class library with .NET Core in Visual Studio 2017 (Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017)](./library-with-visual-studio.md) oder [Building a Visual Basic class library with .NET Core in Visual Studio 2017 (Erstellen einer Visual Basic-Klassenbibliothek mit .NET Core in Visual Studio 2017)](vb-library-with-visual-studio.md) beschriebenen Schritte erstellt und Sie in [Testing a class library with .NET Core in Visual Studio 2017 (Testen einer Klassenbibliothek mit .NET Core in Visual Studio 2017)](testing-library-with-visual-studio.md) getestet und eine Releaseversion der Bibliothek erstellt haben, können Sie sie im nächsten Schritt für Aufrufer verfügbar machen. Dazu gibt es zwei Möglichkeiten:

* Wenn die Bibliothek von einer einzelnen Projektmappe verwendet wird (wenn es sich z.B. um eine Komponente in einer großen Einzelanwendung handelt), können Sie die Bibliothek als Projekt in Ihre Projektmappe einfügen.

* Wenn die Bibliothek allgemein verfügbar sein soll, können Sie sie als NuGet-Paket verteilen.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Einschließen einer Bibliothek als Projekt in einer Projektmappe

Ebenso wie Sie Komponententests in dieselbe Projektmappe eingeschlossen haben wie Ihre Klassenbibliothek, können Sie Ihre Anwendung als Teil dieser Projektmappe einschließen. Angenommen, Sie können Ihre Klassenbibliothek in einer Konsolenanwendung verwenden, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen ein Großbuchstabe ist:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Öffnen Sie die Projektmappe `ClassLibraryProjects`, die Sie im Thema [Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017](./library-with-visual-studio.md). Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen**, erweitern Sie den Knoten **Visual C#**, und klicken Sie auf den Knoten .**NET Core** und anschließend auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie im Textfeld **Name** „ShowCase“ ein, und klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Neues Projekt hinzufügen“](./media/consuming-library-with-visual-studio/addnewproject.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus. 

   ![Kontextmenü „ShowCase“](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek. Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Kontextmenü „ShowCase-Abhängigkeiten“](./media/consuming-library-with-visual-studio/addreference.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.

   ![Verweis-Manager](./media/consuming-library-with-visual-studio/referencemanager.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.cs* den gesamten Code durch diesen:

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   Der Code verwendet die Eigenschaft [Console.WindowHeight](xref:System.Console.WindowHeight), um die Anzahl der Zeilen im Konsolenfenster zu ermitteln. Immer dann, wenn die Eigenschaft [Console.CursorTop](xref:System.Console.CursorTop) größer oder gleich der Anzahl von Zeilen im Konsolenfenster ist, löscht der Code das Konsolenfenster und zeigt dem Benutzer eine Meldung an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird das Konsolenfenster geschlossen, und die Anwendung wird beendet.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Bild](./media/consuming-library-with-visual-studio/toolbar.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Öffnen Sie die Projektmappe `ClassLibraryProjects`, die Sie im Thema [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017 (Erstellen einer C#-Klassenbibliothek mit Visual Basic und .NET Core in Visual Studio 2017)](vb-library-with-visual-studio.md). Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen**, erweitern Sie den Knoten **Visual Basic**, und klicken Sie auf den Knoten .**NET Core** und anschließend auf die Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie im Textfeld **Name** „ShowCase“ ein, und klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Neues Projekt hinzufügen“](./media/consuming-library-with-visual-studio/vb-addnewproject.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus. 

   ![Kontextmenü „ShowCase“](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek. Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Kontextmenü „ShowCase-Abhängigkeiten“](./media/consuming-library-with-visual-studio/addreference.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.

   ![Verweis-Manager](./media/consuming-library-with-visual-studio/referencemanager.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.vb* den gesamten Code durch diesen:

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Der Code verwendet die Eigenschaft [Console.WindowHeight](xref:System.Console.WindowHeight), um die Anzahl der Zeilen im Konsolenfenster zu ermitteln. Immer dann, wenn die Eigenschaft [Console.CursorTop](xref:System.Console.CursorTop) größer oder gleich der Anzahl von Zeilen im Konsolenfenster ist, löscht der Code das Konsolenfenster und zeigt dem Benutzer eine Meldung an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird das Konsolenfenster geschlossen, und die Anwendung wird beendet.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Bild](./media/consuming-library-with-visual-studio/toolbar.png)
---

Sie können die Anwendung, die diese Bibliothek verwendet, debuggen und schließlich veröffentlichen, indem Sie die Schritte in [Debuggen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017](debugging-with-visual-studio.md) und [Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017](publishing-with-visual-studio.md) ausführen.

## <a name="distributing-the-library-in-a-nuget-package"></a>Verteilen der Bibliothek in einem NuGet-Paket

Sie können Ihre Klassenbibliothek allgemein verfügbar machen, indem Sie sie als NuGet-Paket veröffentlichen. Visual Studio bietet keine Unterstützung für das Erstellen von NuGet-Paketen. Um ein NuGet-Paket zu erstellen, verwenden Sie das [`dotnet`-Befehlszeilenprogramm ](../../core/tools/dotnet.md):

1. Öffnen Sie ein Konsolenfenster. Geben Sie z.B. im Textfeld **Frag mich etwas** in der Windows-Taskleiste `Command Prompt` (oder `cmd` als Abkürzung) ein, und öffnen Sie ein Konsolenfenster, indem Sie entweder die Desktopanwendung **Eingabeaufforderung** auswählen oder die EINGABETASTE drücken, wenn die Anwendung in den Suchergebnissen angezeigt wird.

1. Navigieren Sie zum Projektverzeichnis Ihrer Bibliothek. Sofern Sie nicht den typischen Dateispeicherort neu konfiguriert haben, befindet sich dieser im Verzeichnis *Dokumente\Visual Studio 2017\Projekte\ClassLibraryProjects\StringLibrary*. Das Verzeichnis enthält Ihren Quellcode und eine Projektdatei, *StringLibrary.csproj*.

1. Führen Sie den Befehl `dotnet pack --no-build` aus. Das Hilfsprogramm `dotnet` generiert ein Paket mit der Erweiterung *.nupkg*.

   > [!TIP]
   > Wenn sich das Verzeichnis, das die Datei *dotnet.exe* enthält, nicht in Ihrem Pfad befindet, können Sie ihren Speicherort ermitteln, indem Sie im Konsolenfenster `where dotnet.exe` eingeben.

Weitere Informationen zum Erstellen von NuGet-Paketen finden Sie unter [Erstellen eines NuGet-Pakets mit plattformübergreifenden Tools](../../core/deploying/creating-nuget-packages.md).
