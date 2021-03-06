---
title: 'CA1065: Nie zgłaszaj wyjątków w nieoczekiwanych lokalizacjach | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1065
- DoNotRaiseExceptionsInUnexpectedLocations
helpviewer_keywords:
- DoNotRaiseExceptionsInUnexpectedLocations
- CA1065
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 93be7e14bd095fb7f25c7dcce90eba3d724b05f0
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900949"
---
# <a name="ca1065-do-not-raise-exceptions-in-unexpected-locations"></a>CA1065: Nie należy wyrzucać wyjątków w nieoczekiwanych lokalizacjach
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA1065: Nie zgłaszaj wyjątków w nieoczekiwanych lokalizacjach](https://docs.microsoft.com/visualstudio/code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations).

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|
|CheckId|CA1065|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Metoda, od której nie oczekiwano zgłaszania wyjątków, zgłasza wyjątek.

## <a name="rule-description"></a>Opis reguły
 Metody, nie oczekiwano zgłaszania wyjątków, które mogą zostać podzielone w następujący sposób:

-   Właściwości metod Get

-   Metody dostępu zdarzeń

-   Metody Equals

-   Metody GetHashCode

-   Metody ToString

-   Konstruktory statyczne

-   Finalizatory

-   Metody Dispose

-   Operatory równości

-   Operatory rzutowania niejawnego

 W poniższych sekcjach omówiono te typy metody.

### <a name="property-get-methods"></a>Właściwości metod Get
 Właściwości są po prostu inteligentne pola. W związku z tym ich powinny zachowywać się jak możliwie pola. Pola nie zgłaszają wyjątki, a żadna z nich nie powinien właściwości. Jeśli właściwość, która zgłosiła wyjątek, należy wziąć pod uwagę co metody.

 Następujące wyjątki mogą być generowane metody get właściwości:

-   <xref:System.InvalidOperationException?displayProperty=fullName> oraz wszystkie pochodne (w tym <xref:System.ObjectDisposedException?displayProperty=fullName>)

-   <xref:System.NotSupportedException?displayProperty=fullName> oraz wszystkie pochodne

-   <xref:System.ArgumentException?displayProperty=fullName> (tylko z indeksowanej get)

-   <xref:System.Collections.Generic.KeyNotFoundException> (tylko z indeksowanej get)

### <a name="event-accessor-methods"></a>Metody dostępu zdarzeń
 Metod dostępu zdarzeń powinny być proste operacje, które nie zgłaszają wyjątki. Zdarzenie nie powinien zgłosić wyjątek, gdy użytkownik próbuje dodać lub usunąć program obsługi zdarzeń.

 Następujące wyjątki mogą być wyrzucanych z accesor zdarzeń:

-   <xref:System.InvalidOperationException?displayProperty=fullName> oraz wszystkie pochodne (w tym <xref:System.ObjectDisposedException?displayProperty=fullName>)

-   <xref:System.NotSupportedException?displayProperty=fullName> oraz wszystkie pochodne

-   <xref:System.ArgumentException> i pochodne

### <a name="equals-methods"></a>Metody Equals
 Następujące **jest równa** metody nie powinna zgłaszać wyjątków:

-   <xref:System.Object.Equals%2A?displayProperty=fullName>

-   [M:IEquatable.Equals](http://go.microsoft.com/fwlink/?LinkId=113472)

 **Jest równa** metoda powinna zwrócić `true` lub `false` zamiast zgłaszać wyjątek. Na przykład, jeśli jest równa przechodzi przez dwa typy niezgodne powinna tylko zwrócić `false` zamiast zgłaszać <xref:System.ArgumentException>.

### <a name="gethashcode-methods"></a>Metody GetHashCode
 Następujące **GetHashCode** metody zazwyczaj powinien nie generuje wyjątków:

-   <xref:System.Object.GetHashCode%2A>

-   [M:IEqualityComparer.GetHashCode(T)](http://go.microsoft.com/fwlink/?LinkId=113477)

 **GetHashCode** zawsze powinna zwrócić wartość. W przeciwnym razie może utracić elementów w tabeli wyznaczania wartości skrótu.

 Wersje **GetHashCode** które trwają argument może zgłosić <xref:System.ArgumentException>. Jednak **Object.GetHashCode** powinno nigdy nie zgłasza wyjątku.

### <a name="tostring-methods"></a>Metody ToString
 Debuger używa <xref:System.Object.ToString%2A?displayProperty=fullName> ułatwia wyświetlanie informacji o obiektach w formacie ciągu. W związku z tym **ToString** nie należy zmieniać stan obiektu i nie powinno się zgłaszać wyjątki.

### <a name="static-constructors"></a>Konstruktory statyczne
 Zgłaszanie wyjątków z konstruktora statycznego powoduje, że typ bezużyteczne w bieżącej domenie aplikacji. Dla zostanie zgłoszony wyjątek w konstruktorze statycznym, powinny mieć bardzo dobre powodu (na przykład problem z zabezpieczeniami).

### <a name="finalizers"></a>Finalizatory
 Zostanie zgłoszony wyjątek z finalizatora powoduje, że CLR szybkie, nie powiedzie się, które zniszczy procesu. W związku z tym zgłaszanie wyjątków w finalizator zawsze należy unikać.

### <a name="dispose-methods"></a>Metody Dispose
 A <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metody nie powinien zgłosić wyjątek. Dispose jest często określane jako część logiki czyszczenia `finally` klauzuli. W związku z tym, jawnie zostanie zgłoszony wyjątek od metody Dispose wymusza użytkownikowi dodanie obsługi wewnątrz wyjątków `finally` klauzuli.

 **Dispose(false)** ścieżka kodu powinno nigdy nie zgłaszają wyjątki, ponieważ to prawie zawsze jest wywoływany z finalizatora.

### <a name="equality-operators--"></a>Operatory równości (==,! =)
 Takie jak metody Equals, operatory równości powinna zwracać albo `true` lub `false` i nie powinna zgłaszać wyjątków.

### <a name="implicit-cast-operators"></a>Operatory rzutowania niejawnego
 Ponieważ użytkownik jest często świadomości, operator rzutowania niejawne został wywołany, wyjątek zgłoszony przez operator niejawne rzutowanie jest zupełnie nieoczekiwane. W związku z tym bez wyjątków powinny być wyrzucanych z operatorów rzutowania niejawnego.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Dla metody pobierające albo zmień logikę, tak, aby nie ma już zgłoszenie wyjątku lub zmień wartość właściwości do metody.

 Dla wszystkich innych metoda typów wymienionych powyżej Zmień logikę, tak, aby już nie należy go zgłosić wyjątek.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Jest bezpieczne pominąć ostrzeżenie od tej reguły, jeśli naruszenie zostało spowodowane przez deklaracji wyjątku zamiast zgłoszony wyjątek.

## <a name="related-rules"></a>Powiązane reguły
 [CA2219: Nie zgłaszaj wyjątków w klauzulach wyjątku](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)

## <a name="see-also"></a>Zobacz też
 [Ostrzeżenia dotyczące projektu](../code-quality/design-warnings.md)



