---
title: 'CA1054: Parametry identyfikatora URI nie powinny być ciągami'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 96ec91d9b5ccae66b7b84505d81b95a60e5991d4
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549696"
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: Parametry identyfikatora URI nie powinny być ciągami

|||
|-|-|
|TypeName|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna

Typ deklaruje metodę z parametrem ciągu, którego nazwa zawiera "uri", "Uri", "urn", "Urn", "url" lub "Url" i typ nie deklaruje odpowiadające przeciążenie, która przyjmuje <xref:System.Uri?displayProperty=fullName> parametru.

## <a name="rule-description"></a>Opis reguły

Ta reguła dzieli nazwę parametru na tokeny oparte na Konwencji camelcase i sprawdza, czy każdy token jest równa "uri", "Uri", "urn", "Urn", "url" lub "Url". Jeśli istnieje dopasowanie, reguła zakłada, że parametr reprezentuje identyfikator uniform resource identifier (URI). Reprezentacja ciągu identyfikatora URI jest podatna na analizowanie i kodowanie błędów i może prowadzić do powstawania luk w zabezpieczeniach. Jeśli metoda pobiera reprezentację ciągu identyfikatora URI, odpowiadające przeciążenie powinien być podany, pobierające wystąpienie z <xref:System.Uri> klasy, która udostępnia te usługi w bezpieczny sposób.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia

Aby naprawić naruszenie tej zasady, Zmień parametr <xref:System.Uri> wpisz; to jest zmianą przerywającą. Alternatywnie, zapewnienia przeciążenia metody, która przyjmuje <xref:System.Uri> parameter; to zmian niepowodujących niezgodności.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia

Jest bezpieczne pominąć ostrzeżenie od tej reguły, jeśli parametr nie reprezentuje identyfikator URI.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano typem `ErrorProne`, który narusza tę regułę, a typem `SaferWay`, odpowiadającej reguły.

[!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
[!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
[!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>Powiązane reguły

[CA1056: Właściwości identyfikatora URI nie powinny być ciągami](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

[CA1055: Wartości zwracane identyfikatora URI nie powinny być ciągami](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

[CA2234: Przekaż obiekty System.Uri zamiast ciągów](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

[CA1057: Przeciążenia identyfikatora URI w postaci ciągu wywołują przeciążenia metody System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)