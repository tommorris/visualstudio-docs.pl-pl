---
title: Stan, Projektant działań | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.State.UI
ms.assetid: 9455ab37-93a0-4c46-9eb8-b6611ca23167
caps.latest.revision: 5
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 3c1d0019179d0a8e3f82001c371e760172251c2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692423"
---
# <a name="state-activity-designer"></a>State, projektant działań
A <xref:System.Activities.Statements.State> reprezentuje stan, w którym mogą mieć automatu stanów.  
  
## <a name="using-the-state-activity-designer"></a>Za pomocą State, Projektant działań  
 Aby dodać <xref:System.Activities.Statements.State> do przepływu pracy, przeciągnij **stanu** projektanta działań z **automatu stanów** części **przybornika** i upuść je na <xref:System.Activities.Statements.StateMachine> działanie na [!INCLUDE[wfd1](../includes/wfd1-md.md)] powierzchni. A <xref:System.Activities.Statements.State> działanie może być upuszczone na <xref:System.Activities.Statements.StateMachine> i przejść, dodane później; lub przejścia mogą być tworzone jako <xref:System.Activities.Statements.State> działanie zostało porzucone. Aby dodać <xref:System.Activities.Statements.State> działania i Utwórz przejścia w jednym kroku, a następnie przeciągnij **stanu** działanie z **automatu stanów** części **przybornika** i zatrzymaj wskaźnik myszy nad innym Stan w Projektancie przepływu pracy. Gdy przeciąganego <xref:System.Activities.Statements.State> znajduje się nad innym <xref:System.Activities.Statements.State>, cztery trójkąty pojawi się wokół drugiego <xref:System.Activities.Statements.State>. Jeśli <xref:System.Activities.Statements.State> został upuszczony na jeden z czterech trójkątów, jest ona dodawana do automatu stanów i utworzeniu przejścia ze źródła <xref:System.Activities.Statements.State> do lokalizacji docelowej porzuconych <xref:System.Activities.Statements.State>. Aby uzyskać więcej informacji, zobacz [przejścia](../workflow-designer/transition-activity-designer.md).  
  
### <a name="state-activity-properties-in-the-workflow-designer"></a>Właściwości stanu działania w Projektancie przepływu pracy  
 W poniższej tabeli przedstawiono <xref:System.Activities.Statements.State> właściwości, które można ustawić za pomocą projektanta przepływów pracy i w tym artykule opisano, jak są używane w projektancie. Niektóre z tych właściwości można edytować w siatce właściwości, a niektóre z nich mogą być edytowane na powierzchni projektowej.  
  
|Nazwa właściwości|Wymagane|Użycie|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Określa przyjazną nazwę <xref:System.Activities.Statements.State> projektanta działań w nagłówku. Wartość domyślna to **stanu**. Wartość można edytować w siatce właściwości lub bezpośrednio w nagłówku projektanta działań. <xref:System.Activities.Statements.State.DisplayName%2A> Jest używany w nadrzędnych, która jest wyświetlana w górnej części projektanta przepływów pracy.<br /><br /> Mimo że <xref:System.Activities.Statements.State.DisplayName%2A> nie jest bezwzględnie konieczne jest najlepszym rozwiązaniem, aby użyć jednego.|  
|<xref:System.Activities.Statements.State.Entry%2A>|False|Określa akcję, która występuje, gdy ten stan jest przenoszone do. Gdy <xref:System.Activities.Statements.State> działania jest rozwinięta, tę wartość można ustawić, przeciągając działanie w **przybornika** i upuszczając go na **wpis** sekcja stanu.|  
|<xref:System.Activities.Statements.State.Exit%2A>|False|Określa akcję, która występuje, gdy ten stan jest przenoszone z. Gdy <xref:System.Activities.Statements.State> działania jest rozwinięta, tę wartość można ustawić, przeciągając działanie w **przybornika** i upuszczając go na **zakończenia** sekcja stanu.|  
|<xref:System.Activities.Statements.State.Transitions%2A>|False|Zawiera listę możliwych przejść, które pochodzą z <xref:System.Activities.Statements.State>. Każdy element na liście zawiera link do powiązanych <xref:System.Activities.Statements.Transition> i miejsce docelowe <xref:System.Activities.Statements.State>. Kliknięcie łącza spowoduje przełączenie projektanta rozwinięty widok <xref:System.Activities.Statements.Transition> lub <xref:System.Activities.Statements.State>.|  
  
## <a name="see-also"></a>Zobacz też  
 [Automat stanów](../workflow-designer/statemachine-activity-designer.md)   
 [Stan końcowy](../workflow-designer/finalstate-activity-designer.md)   
 [przejścia](../workflow-designer/transition-activity-designer.md)