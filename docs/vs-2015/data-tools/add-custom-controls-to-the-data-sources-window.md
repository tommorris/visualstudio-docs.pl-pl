---
title: Dodawanie niestandardowych formantów do okna źródeł danych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.datasource.howtoaddcustomcontrol
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- Data Sources Window, adding controls
- controls [Visual Studio], adding to Data Sources Window
- DefaultBindingPropertyAttribute class, using
- LookupBindingPropertiesAttribute class, using
- ComplexBindingPropertiesAttribute class, using
- Data Sources Window, selecting controls
ms.assetid: 8c43e7d2-ba94-4d9b-96de-3aa971955afd
caps.latest.revision: 45
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: acdab62754a8cbbe7b97ea9723fba202d5078ac0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678682"
---
# <a name="add-custom-controls-to-the-data-sources-window"></a>Dodawanie kontrolek niestandardowych do okna źródeł danych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Dodawanie niestandardowych formantów do okna źródeł danych](https://docs.microsoft.com/visualstudio/data-tools/add-custom-controls-to-the-data-sources-window).  
  
  
Podczas przeciągania elementu z **źródeł danych** okna do powierzchni projektu, aby utworzyć formant powiązany z danymi, można wybrać typ kontrolki, którą tworzysz. Każdy element w oknie ma listy zawiera formanty, które można wybierać. Zestaw mechanizmów kontrolnych, związane z każdym elementem jest określana przez typ danych elementu. Jeśli formant, który ma zostać utworzona, nie ma na liście, możesz wykonać instrukcje przedstawione w tym temacie, aby dodać formant do listy.  
  
 Aby uzyskać więcej informacji o wybieraniu formantów powiązanych z danymi można utworzyć dla elementów w **źródeł danych** okna, zobacz [Ustawianie formantu do utworzenia podczas przeciągania z okna źródeł danych](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
> [!NOTE]
>  Polecenia menu i okien dialogowych mogą różnić się od tych opisanych w pomocy, w zależności od ustawień aktywnych lub wersji. Aby zmienić swoje ustawienia na **narzędzia** menu, wybierz opcję **Import i eksport ustawień**. Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska deweloperskiego, w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
##  <a name="customizinglist"></a> Dostosuj listę możliwej do wiązania kontrolki typu danych  
 Aby dodać lub usunąć formanty z listy dostępnych kontrolek dla elementów w **źródeł danych** okno, które mają na określony typ danych, wykonaj następujące kroki.  
  
#### <a name="to-select-the-controls-to-be-listed-for-a-data-type"></a>Aby wybrać formanty był wyświetlany dla typu danych  
  
1.  Upewnij się, że projektant WPF lub projektanta Windows Forms jest otwarty.  
  
2.  W **źródeł danych** , kliknij element, który jest częścią źródła danych dodane do okna, a następnie kliknij przycisk menu rozwijanej dla elementu.  
  
3.  W menu rozwijanym kliknij **Dostosuj**. Jedną z następujących okien dialogowych zostanie otwarta:  
  
    -   Jeśli program Windows Forms Designer jest otwarty, **Dostosowywanie danych interfejsu użytkownika** strony **opcje** zostanie otwarte okno dialogowe.  
  
    -   Jeśli projektant WPF jest otwarty, **Dostosuj powiązania kontrolki** zostanie otwarte okno dialogowe.  
  
4.  W oknie dialogowym Wybierz typ danych z **— typ danych** listy rozwijanej.  
  
    -   Aby dostosować listę formantów dla tabeli lub obiektu, wybierz opcję **[lista]**.  
  
    -   Aby dostosować listę formantów dla kolumny tabeli lub właściwości obiektu, wybierz typ danych kolumny lub właściwości w podstawowym magazynie danych.  
  
    -   Aby dostosować listę formantów do wyświetlania obiektów danych, które mają kształty zdefiniowane przez użytkownika, wybierz opcję **(inne)**. Na przykład wybierz **(inne)** Jeśli aplikacja ma formant niestandardowy, który wyświetla dane z więcej niż jedną właściwość określonego obiektu.  
  
5.  W **ane kontrolki** wybierz każdy formant, który ma być dostępna dla wybranego typu danych lub wyczyść zaznaczenie formantów, które chcesz usunąć z listy.  
  
    > [!NOTE]
    >  Jeśli formant, który ma zostać wybrana, nie jest widoczna w **ane kontrolki** pole, należy dodać formant do listy. Aby uzyskać więcej informacji, zobacz [dodawanie formantów do listy z skojarzonych formantów dla typu danych](#addingcontrols).  
  
6.  Kliknij przycisk **OK**.  
  
7.  W **źródeł danych** , kliknij element danych, wpisz tylko skojarzony co najmniej jednej kontrolki, a następnie kliknij menu rozwijanej dla elementu.  
  
     Formanty został wybrany w **ane kontrolki** pola pojawiają się w menu rozwijanej dla elementu.  
  
##  <a name="addingcontrols"></a> Addcontrols do listy skojarzonych formantów dla typu danych  
 Jeśli chcesz skojarzyć formantu o typie danych, ale formant nie jest wyświetlana w **ane kontrolki** pole, należy dodać formant do listy. Kontrolka musi być znajduje się w bieżącym rozwiązaniu lub w zestawie odwołania. Również musi być dostępny w **przybornika**, a ma atrybut, który określa zachowanie wiązania danych formantu.  
  
#### <a name="to-add-controls-to-the-list-of-associated-controls"></a>Aby dodać formanty do listy skojarzonych formantów  
  
1.  Dodaj żądaną kontrolkę do **przybornika** przez kliknięcie prawym przyciskiem myszy **przybornika** i wybierając polecenie **wybierz elementy**.  
  
     Kontrolka musi mieć jedną z następujących atrybutów.  
  
    |Atrybut|Opis|  
    |---------------|-----------------|  
    |<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Implementowanie tego atrybutu na proste formanty, zawierające jedną kolumnę (lub właściwości) dane, takie jak <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Implementowanie tego atrybutu formanty, które wyświetlają list (lub tabele) dane, takie jak <xref:System.Windows.Forms.DataGridView>.|  
    |<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Implementowanie tego atrybutu formanty, które wyświetlają list (lub tabele) z danych, ale także przedstawiania pojedynczej kolumny lub właściwości, takie jak <xref:System.Windows.Forms.ComboBox>.|  
  
2.  W przypadku formularzy Windows w **opcje** po otwarciu okna dialogowego **Dostosowywanie danych interfejsu użytkownika** strony. WPF, można otworzyć **Dostosuj powiązania kontrolki** okno dialogowe. Aby uzyskać więcej informacji, zobacz [Dostosowywanie listy możliwej do wiązania kontrolki typu danych](#customizinglist).  
  
3.  W **ane kontrolki** polu formant, który właśnie został dodany do **przybornika** powinna teraz zostać wyświetlona.  
  
    > [!NOTE]
    >  Tylko formanty, które znajdują się w obrębie bieżącego rozwiązania, lub w zestawie odwołania można dodać do listy skojarzonych formantów. (Kontrolki musi także implementować jeden z atrybutów powiązania danych w poprzedniej tabeli.) Aby powiązać dane z kontrolką niestandardową, która nie jest dostępna w **źródeł danych** okna, przeciągnij formant z **przybornika** na powierzchni projektowej, a następnie przeciągnij element można powiązać z **danych Źródła** okna w formancie.  
  
## <a name="see-also"></a>Zobacz też  
 [Powiązywanie kontrolek z danymi w programie Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)

