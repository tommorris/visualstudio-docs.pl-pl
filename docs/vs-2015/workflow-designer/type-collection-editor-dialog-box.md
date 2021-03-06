---
title: Okno dialogowe Edytor kolekcji typów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 34b8129b5a0b1fe27a7e4e6c178ddace638e5ffc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677773"
---
# <a name="type-collection-editor-dialog-box"></a>Edytor kolekcji typów, okno dialogowe
**Editor typu Kolekce** okno dialogowe służy do dodawania znanych typów do **wysyłania** i **Receive** działań. To okno dialogowe umożliwia również dodawać argumenty typu generycznego **InvokeMethod** działania. Gdy jest używana dla **wysyłania** i **Receive** działań do dodania znane typy **Editor typu Kolekce** okno dialogowe wymaga dodatki typu, aby była unikatowa. Jeśli zduplikowany typ zostanie dodany, a zmiana jest zatwierdzona, klikając **OK**, zwracany jest komunikat o błędzie. Gdy jest używana dla **InvokeMethod** działanie, aby dodać argumenty typu generycznego **Editor typu Kolekce** okno dialogowe umożliwia dodanie typy zduplikowanych.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../includes/crabout-md.md)] znanych typów, zobacz [znane typy kontraktu danych](http://msdn.microsoft.com/library/1a0baea1-27b7-470d-9136-5bbad86c4337).  
  
 W poniższej tabeli opisano elementy interfejsu użytkownika **kolekcji typów** okno dialogowe.  
  
|Element interfejsu użytkownika|Opis|  
|----------------|-----------------|  
|**Lista typów**|Lista typów, które zostały dodane lub usunięte.|  
  
## <a name="to-bring-up-the-type-collection-editor"></a>Aby wyświetlić się Edytor kolekcji typów  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Aby przełączyć się Edytor kolekcji typów do wysyłania i odbierania działań  
  
1.  Wybierz **wysyłania** lub **Receive** działania w widoku Projekt.  
  
2.  Naciśnij klawisz **F4** aby przywołać **właściwości** okna.  
  
3.  W **właściwości** , kliknij przycisk wielokropka znajdujący się obok **element KnownTypes** właściwości.  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Aby wyświetlić się Edytor kolekcji typów dla działania InvokeMethod  
  
1.  Wybierz **InvokeMethod** działania w widoku Projekt.  
  
2.  Naciśnij klawisz **F4** aby przywołać **właściwości** okna.  
  
3.  W **właściwości** , kliknij przycisk wielokropka znajdujący się obok **GenericTypeArguments** właściwości.