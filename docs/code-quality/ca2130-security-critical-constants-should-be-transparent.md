---
title: 'CA2130: Krytyczne stałe zabezpieczeń powinny być przezroczyste'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 212bd1bc9f1f5b66fa8ddb485c5ec287ff39c754
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551354"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Krytyczne stałe zabezpieczeń powinny być przezroczyste
|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Pole stałe lub elementu członkowskiego wyliczenia jest oznaczona za pomocą <xref:System.Security.SecurityCriticalAttribute>.

## <a name="rule-description"></a>Opis reguły
 Wymuszanie przezroczystości nie jest wymuszane dla wartości stałych, ponieważ kompilatory wbudowują stałe wartości, tak aby nie było wymagane żadne wyszukiwanie w czasie wykonywania. Stałe pola powinny być przezroczyste dla zabezpieczeń, tak aby recenzenci kodu nie zakładali, że przezroczysty kod nie może uzyskać dostępu do stałej.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, usuń atrybut SecurityCritical z pól lub wartości.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 W poniższych przykładach wartości wyliczenia `EnumWithCriticalValues.CriticalEnumValue` i stałą `CriticalConstant` podnieść to ostrzeżenie. Aby rozwiązać problemy, Usuń [`SecurityCritical`] atrybutu, aby zwiększyć ich bezpieczeństwo przezroczysty.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]