---
title: 'Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 6d6c87443b26663da20b94835f1fd6c1fb926ae4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560533"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.TransformGroup> Gruppe zwei oder mehr <xref:System.Windows.Media.Transform> Objekte in einem einzigen zusammengesetzten <xref:System.Windows.Media.Transform>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TransformGroup> Anwenden einer <xref:System.Windows.Media.ScaleTransform> und ein <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Media.TransformGroup>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Beispiel für 2D-Transformationen](http://go.microsoft.com/fwlink/?LinkID=158252)
