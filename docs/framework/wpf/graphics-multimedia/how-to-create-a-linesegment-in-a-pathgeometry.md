---
title: 'Gewusst wie: Erstellen eines LineSegment in einer PathGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: 1cfa9275a2a4508c153cf6ab7ed1c6126b1ee92c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559668"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a>Gewusst wie: Erstellen eines LineSegment in einer PathGeometry
Dieses Beispiel zeigt, wie ein Liniensegment erstellt wird. Verwenden Sie zum Erstellen eines Liniensegments die <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.LineSegment> Klassen.  
  
## <a name="example"></a>Beispiel  
 Zeichnen Sie in den folgenden Beispielen ein <xref:System.Windows.Media.LineSegment> aus (10, 50), (200, 70). Die folgende Abbildung zeigt die resultierenden <xref:System.Windows.Media.LineSegment>; eine Rasterhintergrund wurde hinzugefügt, um das Koordinatensystem anzuzeigen.  
  
 ![Ein LineSegment in einer PathFigure](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "Graphicsmm_pathgeometrylinesegment")  
Ein LineSegment, das von (10,50) bis (200,70) gezeichnet wurde  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie zum Beschreiben eines Pfads Attributsyntax verwenden.  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 [xaml]  
  
 (Beachten Sie, die diese Attributsyntax tatsächlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, einer helleren Gewichtung-Version von einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)  
  
 Zudem können Sie in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] XAML ein Liniensegment mithilfe von Objektelementsyntax zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1">  
  <Path.Data>  
    <PathGeometry>  
      <PathFigure StartPoint="10,50">  
        <LineSegment Point="200,70" />  
      </PathFigure>  
    </PathGeometry>  
  </Path.Data>  
</Path>  
```  
  
```csharp  
PathFigure myPathFigure = new PathFigure();  
myPathFigure.StartPoint = new Point(10, 50);  
  
LineSegment myLineSegment = new LineSegment();  
myLineSegment.Point = new Point(200, 70);  
  
PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();  
myPathSegmentCollection.Add(myLineSegment);  
  
myPathFigure.Segments = myPathSegmentCollection;  
  
PathFigureCollection myPathFigureCollection = new PathFigureCollection();  
myPathFigureCollection.Add(myPathFigure);  
  
PathGeometry myPathGeometry = new PathGeometry();  
myPathGeometry.Figures = myPathFigureCollection;  
  
Path myPath = new Path();  
myPath.Stroke = Brushes.Black;  
myPath.StrokeThickness = 1;  
myPath.Data = myPathGeometry;  
```  
  
```vb  
Dim myPathFigure As New PathFigure()  
            myPathFigure.StartPoint = New Point(10, 50)  
  
            Dim myLineSegment As New LineSegment()  
            myLineSegment.Point = New Point(200, 70)  
  
            Dim myPathSegmentCollection As New PathSegmentCollection()  
            myPathSegmentCollection.Add(myLineSegment)  
  
            myPathFigure.Segments = myPathSegmentCollection  
  
            Dim myPathFigureCollection As New PathFigureCollection()  
            myPathFigureCollection.Add(myPathFigure)  
  
            Dim myPathGeometry As New PathGeometry()  
            myPathGeometry.Figures = myPathFigureCollection  
  
            Dim myPath As New Path()  
            myPath.Stroke = Brushes.Black  
            myPath.StrokeThickness = 1  
            myPath.Data = myPathGeometry  
```  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.PathFigure>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.GeometryDrawing>  
 <xref:System.Windows.Shapes.Path>  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
