---
title: 'CA1014: Oznacz zestawy za pomocą CLSCompliantAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3375d3a88a9776190887252cff7c2f9accb5fd4e
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547282"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Oznacz zestawy za pomocą CLSCompliantAttribute

|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Zestaw nie ma <xref:System.CLSCompliantAttribute?displayProperty=fullName> zastosowany do niego.

## <a name="rule-description"></a>Opis reguły
 The Common Language Specification (CLS) definiuje ograniczenia nazw, typów danych i reguł, z którymi muszą być zgodne zestawy, jeśli zostaną użyte w językach programowania. Zasada dobrego projektowania nakazuje, aby wszystkie zestawy jawnie wskazywały zgodność ze specyfikacją CLS przy użyciu <xref:System.CLSCompliantAttribute>. Jeśli ten atrybut nie jest obecny w zestawie, zestaw nie jest zgodne.

 Istnieje możliwość zgodne ze specyfikacją CLS zestawu zawierają typy lub elementy członkowskie, które nie są zgodne typu.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, Dodaj atrybut do zestawu. Zamiast Oznaczanie całego zestawu jako niezgodne, należy określić, które typów lub elementów członkowskich typu nie są zgodne i oznaczyć te elementy w związku z tym. Jeśli to możliwe należy podać zgodny ze specyfikacją CLS alternatywę dla członków niezgodnych tak, aby najszerszych możliwych odbiorców mogą uzyskiwać dostęp do wszystkich funkcji zestawu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły. Jeśli nie chcesz zestawie, który ma być zgodne, zastosuj atrybut i ustawić jej wartość na `false`.

## <a name="example"></a>Przykład
 W poniższym przykładzie przedstawiono zestaw, który ma <xref:System.CLSCompliantAttribute?displayProperty=fullName> atrybut zastosowany, która deklaruje na zgodny ze specyfikacją CLS.

 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>Zobacz także

- <xref:System.CLSCompliantAttribute?displayProperty=fullName>
- [Niezależność od języka i składniki niezależne od języka](/dotnet/standard/language-independence-and-language-independent-components)