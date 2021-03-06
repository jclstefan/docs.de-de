---
title: 'Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 1cb8f8b7d2f86125736c08cd9eadf4eee30063bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533957"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms
Sie können konfigurieren, wie Werte in Windows Forms angezeigt werden <xref:System.Windows.Forms.NumericUpDown> Steuerelement. Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft bestimmt, wie viele Ziffern nach dem Dezimaltrennzeichen angezeigt werden; der Standard ist 0. Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> -Eigenschaft bestimmt, ob eine Trennzeichen zwischen allen drei Dezimalstellen eingefügt wird; der Standardwert ist `false`. Das Steuerelement kann Werte im Hexadezimalformat statt Dezimalformat anzeigen, wenn die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> -Eigenschaftensatz auf `true`; der Standardwert ist `false`.  
  
### <a name="to-format-the-numeric-value"></a>So formatieren Sie den numerischen Wert  
  
-   Zeigen Sie einen Dezimalwert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft auf eine ganze Zahl und das Festlegen der <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Eigenschaft, um `true` oder `false`.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     - oder -   
  
-   Anzeigen von einem hexadezimalen Wert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> Eigenschaft `true`.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  Auch wenn der Wert auf das Formular als eine Hexadezimalzeichenfolge angezeigt wird, alle Tests ausführen auf der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft Tests einen Dezimalwert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Übersicht über das NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
