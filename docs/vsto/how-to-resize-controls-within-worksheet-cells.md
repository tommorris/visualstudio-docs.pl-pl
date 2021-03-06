---
title: 'Porady: zmiana rozmiaru formantów w komórkach arkusza'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- managed controls, resizing
- worksheets, resizing
- Windows Forms controls [Office development in Visual Studio], resizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 91a7e66e085408b35f0ce1d8f7d4783e0c4715a8
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677285"
---
# <a name="how-to-resize-controls-within-worksheet-cells"></a>Porady: zmiana rozmiaru formantów w komórkach arkusza
  Podczas zmiany rozmiaru kolumn lub wierszy w arkuszu, wszystkie kontrolki hosta w komórkach automatycznie Zmień rozmiar na wysokość lub szerokość komórki, który został zmieniony. Kontrolek formularzy Windows Forms nie rozmiar zmienia się automatycznie domyślnie.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Jeśli dodasz kontrolki w czasie projektowania, należy ustawić opcje dla każdego formantu położenia.  
  
 Jeśli programowo dodać formant programu Windows Forms i podać argument zakres kontrolki automatycznie zmienia rozmiar, gdy zmieniany jest rozmiar komórek w zakresie. Aby uzyskać więcej informacji, zobacz [dodawanie formantów do dokumentów pakietu Office w środowisku uruchomieniowym](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="resize-controls-at-design-time"></a>Zmiana rozmiaru formantów w czasie projektowania  
  
### <a name="to-make-controls-resize-with-cells-at-design-time"></a>Aby wyświetlić zmiany rozmiaru komórek w czasie projektowania formanty  
  
1.  Z **przybornika**, przeciągnij formant programu Windows Forms do arkusza.  
  
2.  Kliknij prawym przyciskiem myszy formant, a następnie kliknij przycisk **kontroli formatu**.  
  
3.  W **kontroli formatu** okno dialogowe, kliknij przycisk **właściwości** kartę.  
  
4.  W obszarze **Pozycjonowanie obiektu**, wybierz opcję **wraz z komórkami jej rozmiaru i przenoszenie** opcji, a następnie kliknij przycisk **OK**.  
  
     Podczas zmiany rozmiaru komórkę zawierającą formant do rozmiaru komórki zmienia rozmiar kontrolki.  
  
## <a name="resize-controls-at-runtime"></a>Zmiana rozmiaru formantów w czasie wykonywania  
 Możesz dodać formant programu Windows Forms w czasie wykonywania i przekazać <xref:Microsoft.Office.Interop.Excel.Range> jako lokalizację dla formantu, formant będzie automatycznie zmieniać rozmiar przy zmianie rozmiaru komórkę arkusz zawierający zakres.  
  
### <a name="to-make-controls-resize-with-cells-at-run-time"></a>Aby wyświetlić formanty, zmiana rozmiaru komórek w czasie wykonywania  
  
1.  Dodawanie kontrolki do zakresu A1.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#5)]  
  
     Podczas zmiany rozmiaru komórkę zawierającą formant do rozmiaru komórki zmienia rozmiar kontrolki.  
  
## <a name="reset-control-placement"></a>Resetuj położenie formantu  
 Można przywrócić położenia i rozmiaru formantu przez ustawienie `Placement` jedną z następujących właściwości <xref:Microsoft.Office.Interop.Excel.XlPlacement> wartości:  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMove>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMoveAndSize>  
  
### <a name="to-change-the-behavior-of-a-control-so-that-it-does-not-resize-or-move-with-the-cell"></a>Aby zmienić zachowanie kontrolki tak, aby zmienić rozmiar lub nie przenieść przy użyciu komórki  
  
1.  Wywoływanie w właściwości umieszczania formantu, a następnie ustaw wartość <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#6)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#6)]  
  
## <a name="see-also"></a>Zobacz także  
 [Formanty w dokumentach pakietu Office](../vsto/controls-on-office-documents.md)   
 [Porady: Dodawanie kontrolek formularzy Windows Forms do dokumentów pakietu Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Porady: ukrywanie kontrolek w arkuszu podczas drukowania](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [Dodawanie formantów do dokumentów pakietu Office w czasie wykonywania](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Ograniczenia kontrolek Windows Forms w dokumentach pakietu Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  