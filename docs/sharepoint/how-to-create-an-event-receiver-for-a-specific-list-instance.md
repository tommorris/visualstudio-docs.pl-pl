---
title: 'Porady: tworzenie obsługiwanego odbiornika dla wystąpienia określonej listy | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 950eeec82d7b7c49f0bbd76b13114f80f023a6dd
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120321"
---
# <a name="how-to-create-an-event-receiver-for-a-specific-list-instance"></a>Porady: tworzenie obsługiwanego odbiornika dla określonej listy formularzy
  Odbiornik zdarzeń wystąpienia listy reaguje na zdarzenia występujące w żadnym wystąpieniu definicji listy. Mimo że szablonu odbiorcy zdarzeń nie obsługuje wartości docelowej określonej listy formularzy, można zmodyfikować odbiorcy zdarzeń, które są ograniczone do definicji listy w celu reagowania na zdarzenia w wystąpieniu określonej listy.  
  
 Pod kątem określonej listy formularzy w *Elements.xml* odbiornika zdarzeń, Zastąp `ListTemplateId` z `ListUrl` i Dodaj adres URL wystąpienia listy.  
  
## <a name="create-a-list-instance-event-receiver"></a>Tworzenie odbiornika zdarzeń wystąpienia listy  
 Poniższe kroki przedstawiają sposób zmodyfikować odbiornik zdarzeń elementu listy, aby odpowiadać tylko na zdarzenia występujące w wystąpieniu niestandardowe listy anonsów.  
  
#### <a name="to-modify-an-event-receiver-to-respond-to-a-specific-list-instance"></a>Aby zmodyfikować obsługiwanego odbiornika odpowiedzieć na określonej listy formularzy  
  
1.  W przeglądarce otwórz witrynę programu SharePoint.  
  
2.  W okienku nawigacji **wymieniono** łącza.  
  
3.  W **całą zawartość lokacji** wybierz pozycję **Utwórz** łącza.  
  
4.  W **Utwórz** okna dialogowego wybierz **anonsów** typu, nazwy anonsu **TestAnnouncements**, a następnie wybierz pozycję **Utwórz**przycisku.  
  
5.  W [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], Utwórz projekt odbiorcy zdarzeń.  
  
6.  W **odbiornika zdarzeń typ?** wybierz **zdarzenia elementu listy**.  
  
    > [!NOTE]  
    >  Możesz też wybrać inny rodzaj odbiornik zdarzeń zakresów do definicji listy, na przykład **listy zdarzeń E-mail** lub **listy zdarzeń przepływu pracy**.  
  
7.  W **elementu powinien być źródło zdarzenia?** wybierz **anonsów**.  
  
8.  W **obsługi następujących zdarzeń** listy, wybierz **jest dodawany element** pole wyboru, a następnie wybierz pozycję **Zakończ** przycisku.  
  
9. W **Eksploratora rozwiązań**, w obszarze EventReceiver1, otwórz *Elements.xml*.  
  
     Odbiorcy zdarzeń obecnie odwołuje się do definicji listy anonsów przy użyciu następującego wiersza:  
  
    ```xml  
    <Receivers ListTemplateId="104">  
    ```  
  
     Zmień ten wiersz na następujący tekst:  
  
    ```xml  
    <Receivers ListUrl="Lists/TestAnnouncements">  
    ```  
  
     Dzięki temu odbiornik zdarzeń, aby odpowiadać tylko na zdarzenia występujące w nowym **TestAnnouncements** listy anonsów, który został właśnie utworzony. Możesz zmienić `ListURL` atrybutów ma dotyczyć odwołanie wystąpienie listy na serwerze programu SharePoint.  
  
10. Otwórz plik kodu dla odbiornika zdarzeń i umieść punkt przerwania w metodzie ItemAdding.  
  
11. Wybierz **F5** klawisz, aby skompilować i uruchomić rozwiązanie.  
  
12. W programie SharePoint, wybierz **TestAnnouncements** łącze w okienku nawigacji.  
  
13. Wybierz **Dodaj nowy anons** łącza.  
  
14. Wprowadź tytuł powiadomienia, a następnie wybierz pozycję **zapisać** przycisku.  
  
     Zwróć uwagę, że punkt przerwania zostaje trafiony po dodaniu nowego elementu do listy niestandardowe anonsów.  
  
15. Wybierz **F5** klawisz, aby wznowić.  
  
16. W okienku nawigacji wybierz **wymieniono** łącza, a następnie wybierz pozycję **anonsów** łącza.  
  
17. Dodaj nowe powiadomienie.  
  
     Należy zauważyć, że odbiorcy zdarzeń nie spowoduje wyzwolenia na nowy anons, ponieważ odbiornika jest skonfigurowany do odpowiadać tylko na zdarzenia w wystąpienia listy niestandardowe anons, **TestAnnouncements**.  
  
## <a name="see-also"></a>Zobacz także
 [Porady: tworzenie obsługiwanego odbiornika](../sharepoint/how-to-create-an-event-receiver.md)   
 [Tworzenie rozwiązań programu SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
