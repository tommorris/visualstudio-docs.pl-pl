---
title: 'CA2001: Unikaj wywoływania problematycznych metod | Dokumentacja firmy Microsoft'
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
- CA2001
- AvoidCallingProblematicMethods
helpviewer_keywords:
- CA2001
- AvoidCallingProblematicMethods
ms.assetid: 19db8edb-31ce-441c-b0de-a0f2746155b7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3a62259f0c0d4de701cba9619ba8a067926a99e6
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900376"
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: Unikaj wywoływania problematycznych metod
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [CA2001: Unikaj wywoływania problematycznych metod](https://docs.microsoft.com/visualstudio/code-quality/ca2001-avoid-calling-problematic-methods).

|||
|-|-|
|TypeName|AvoidCallingProblematicMethods|
|CheckId|CA2001|
|Kategoria|Microsoft.Reliability|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Element członkowski wywołuje potencjalnie niebezpieczną lub problematyczną metodę.

## <a name="rule-description"></a>Opis reguły
 Unikaj niepotrzebnych i potencjalnie niebezpiecznych metody wywołań.

 Naruszenie tej reguły występuje, gdy element członkowski wywołuje jedną z następujących metod.

|Metoda|Opis|
|------------|-----------------|
|<xref:System.GC.Collect%2A?displayProperty=fullName>|Wywoływanie GC. Zbierz może znacząco wpłynąć na wydajność aplikacji i jest niepotrzebna. Aby uzyskać więcej informacji, zobacz [kąski: wydajność Rico Mariani](http://go.microsoft.com/fwlink/?LinkId=169256) wpis w blogu w witrynie MSDN.|
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Thread.Suspend i Thread.Resume zostały wycofane z powodu ich nieprzewidywalne zachowanie.  Użyj innych klas w <xref:System.Threading> przestrzeni nazw, takich jak <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex>, i <xref:System.Threading.Semaphore> do synchronizacji wątków lub chronić zasoby.|
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|Metoda DangerousGetHandle stanowi zagrożenie bezpieczeństwa, ponieważ może zwracać uchwyt, który jest nieprawidłowy. Zobacz <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> i <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> metody, aby uzyskać więcej informacji o tym, jak użyć tej metody DangerousGetHandle bezpiecznie.|
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|Te metody mogą ładować zestawów z nieoczekiwanych lokalizacjach. Na przykład zobacz wpisy w blogu .NET CLR uwagi Suzanne Cooka [funkcję LoadFile programu vs. LoadFrom —](http://go.microsoft.com/fwlink/?LinkId=164450) i [Wybieranie kontekstu powiązania](http://go.microsoft.com/fwlink/?LinkId=164451) informacji o metodach, które ładują zestawy w witrynie MSDN w sieci Web.|
|[CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [Funkcję CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|Przy uruchomieniu kodu użytkownika wykonywane w procesie zarządzanego jest za późno niezawodny sposób będą wywoływać CoSetProxyBlanket. Środowisko uruchomieniowe języka wspólnego (CLR) ma akcje inicjowania, które mogą uniemożliwić pomyślne wykonanie użytkowników P/Invoke.<br /><br /> W przypadku wywołania CoSetProxyBlanket zarządzanej aplikacji, zalecamy rozpocząć proces przy użyciu pliku wykonywalnego kod natywny (C++), wywołania CoSetProxyBlanket w kodzie natywnym, a następnie uruchom aplikację z kodu zarządzanego w procesie. (Pamiętaj określić numer wersji środowiska uruchomieniowego.)|

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, usuń lub Zastąp wywołanie niebezpieczną lub problematyczną metodę.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Wiadomości od tej reguły ma pomijać tylko wtedy, gdy nie alternatywy dla problematycznego metody są dostępne.

## <a name="see-also"></a>Zobacz też
 [Ostrzeżenia dotyczące niezawodności](../code-quality/reliability-warnings.md)



