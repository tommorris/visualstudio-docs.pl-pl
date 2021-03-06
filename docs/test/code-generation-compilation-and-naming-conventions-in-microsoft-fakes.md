---
title: Generowanie kodu, kompilowania i nazywania w Microsoft Fakes dla programu Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 93aec7e83ba5af9bab8da351624df861b46e475c
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282109"
---
# <a name="code-generation-compilation-and-naming-conventions-in-microsoft-fakes"></a>Konwencje dotyczące generowania, kompilowania i nazywania w Microsoft Fakes

W tym artykule omówiono w nim elementów sztucznych Generowanie i kompilacja kodu opcje i zagadnienia i opisano konwencje nazewnictwa dla typów elementów sztucznych wygenerowane, członków i parametry.

**Wymagania**

-   Visual Studio Enterprise
-   Projekt .NET Framework

> [!NOTE]
> .NET standard projekty nie są obsługiwane.

## <a name="code-generation-and-compilation"></a>Generowanie i kompilacja kodu

### <a name="configure-code-generation-of-stubs"></a>Konfiguruj generowanie kodu klas zastępczych

Generowanie typy szkieletu jest skonfigurowany w pliku XML, który ma *.fakes* rozszerzenia pliku. Framework elementów sztucznych integruje w procesie kompilacji za pomocą niestandardowego zadania programu MSBuild i wykrywa te pliki w czasie kompilacji. Generator kodu elementów sztucznych kompiluje typy stub do zestawu i dodaje odwołanie do projektu.

Poniższy przykład przedstawia stub typów zdefiniowanych w *FileSystem.dll*:

```xml
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">
    <Assembly Name="FileSystem"/>
</Fakes>
```

### <a name="type-filtering"></a>Typ filtrowania

Filtry można ustawić w *.fakes* plik, aby ograniczyć typy, które powinny być zastąpić jej metodą zastępczą. Możesz dodać niepowiązany liczba Wyczyść, dodawanie, usuwanie elementów w elemencie StubGeneration do kompilacji na liście wybranych typów.

Na przykład następująca *.fakes* klas zastępczych dla typów w przestrzeni nazw systemu i System.IO generuje plik, ale nie obejmuje dowolnego typu zawierającego "Obsługi" w systemie:

```xml
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">
  <Assembly Name="mscorlib" />
  <!-- user code -->
  <StubGeneration>
    <Clear />
    <Add Namespace="System!" />
    <Add Namespace="System.IO!"/>
    <Remove TypeName="Handle" />
  </StubGeneration>
  <!-- /user code -->
</Fakes>
```

Ciągach filtru Użyj prostego gramatyki do definiowania sposobu dopasowywania należy zrobić:

-   Filtry są bez uwzględniania wielkości liter domyślnie; filtry wykonać dopasowywanie podciągów:

     `el` Dopasowuje "tekst hello"

-   Dodawanie `!` w celu filtrowania ułatwia dokładne dopasowanie uwzględniające:

     `el!` "tekst hello" jest niezgodna

     `hello!` Dopasowuje "tekst hello"

-   Dodawanie `*` w celu filtrowania ułatwia zgodny prefiks ciągu:

     `el*` "tekst hello" jest niezgodna

     `he*` Dopasowuje "tekst hello"

-   Wiele filtrów w Rozdzielana średnikami lista są łączone rozłączenia:

     `el;wo` "tekst hello" i "world"

### <a name="stub-concrete-classes-and-virtual-methods"></a>Stub konkretnych klas i metod wirtualnych

Domyślnie dla wszystkich klas niezapieczętowaną są generowane typy stub. Istnieje możliwość ograniczenia typu klasy zastępczej do klas abstrakcyjnych za pośrednictwem *.fakes* pliku konfiguracji:

```xml
<Fakes xmlns="http://schemas.microsoft.com/fakes/2011/">
  <Assembly Name="mscorlib" />
  <!-- user code -->
  <StubGeneration>
    <Types>
      <Clear />
      <Add AbstractClasses="true"/>
    </Types>
  </StubGeneration>
  <!-- /user code -->
</Fakes>
```

### <a name="internal-types"></a>Wewnętrzne typy

Generator kodu elementów sztucznych generuje typy podkładek i klasy zastępczej dla typów, które są widoczne dla wygenerowanego zestawu elementów sztucznych. Aby wewnętrzne typy zestawu zastąpionym podkładką widoczne dla elementów sztucznych i z zestawu testowego, Dodaj <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atrybuty do kodu zastąpionym podkładką zestawu, który zapewnia widoczność do wygenerowanego zestawu elementów sztucznych i do zestawu testowego. Oto przykład:

```csharp
// FileSystem\AssemblyInfo.cs
[assembly: InternalsVisibleTo("FileSystem.Fakes")]
[assembly: InternalsVisibleTo("FileSystem.Tests")]
```

 **Wewnętrzny typów w zestawach o silnej nazwie**

 Jeśli zastąpionym podkładką zestawu ma silnej nazwy, a chcesz uzyskiwać dostęp do wewnętrznych typy zestawu:

-   Zarówno z zestawu testowego i zestawu elementów sztucznych musi być silna.

-   Dodawanie kluczy publicznych i zestawu elementów sztucznych do badania **InternalsVisibleToAttribute** atrybutów w zestawach zastąpionym podkładką. Oto przykład atrybutów w kodzie zestawu zastąpionym podkładką wyglądu podczas zastąpionym podkładką zestawu ma silnej nazwy:

    ```csharp
    // FileSystem\AssemblyInfo.cs
    [assembly: InternalsVisibleTo("FileSystem.Fakes",
        PublicKey=<Fakes_assembly_public_key>)]
    [assembly: InternalsVisibleTo("FileSystem.Tests",
        PublicKey=<Test_assembly_public_key>)]
    ```

Jeśli silna zastąpionym podkładką zestawu elementów sztucznych framework automatycznie silnie podpisuje wygenerowanego zestawu elementów sztucznych. Masz strong podpisać zestawu testów. Zobacz [zestawy o silnych nazwach](/dotnet/framework/app-domains/strong-named-assemblies).

Platforma elementów sztucznych korzysta z tego samego klucza do podpisywania wszystkich wygenerowanych zestawów, dzięki czemu można używać ta Wstawka kodu jako punkt początkowy, aby dodać **InternalsVisibleTo** atrybutu dla zestawu elementów sztucznych kodu zastąpionym podkładką zestawu.

```csharp
[assembly: InternalsVisibleTo("FileSystem.Fakes, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e92decb949446f688ab9f6973436c535bf50acd1fd580495aae3f875aa4e4f663ca77908c63b7f0996977cb98fcfdb35e05aa2c842002703cad835473caac5ef14107e3a7fae01120a96558785f48319f66daabc862872b2c53f5ac11fa335c0165e202b4c011334c7bc8f4c4e570cf255190f4e3e2cbc9137ca57cb687947bc")]
```

Można określić inny klucz publiczny zestawu elementów sztucznych, takie jak klucz utworzonym dla zestawu zastąpionym podkładką, określając pełną ścieżkę do *.snk —* pliku, który zawiera klucz alternatywny jako `KeyFile` atrybutu wartości w `Fakes` \\ `Compilation` elementu *.fakes* pliku. Na przykład:

```xml
<-- FileSystem.Fakes.fakes -->
<Fakes ...>
  <Compilation KeyFile="full_path_to_the_alternate_snk_file" />
</Fakes>
```

Następnie trzeba użyć klucza publicznego alternatywnego *.snk —* pliku jako drugiego parametru atrybutu InternalVisibleTo dla zestawu elementów sztucznych w kodzie zastąpionym podkładką zestawu:

```csharp
// FileSystem\AssemblyInfo.cs
[assembly: InternalsVisibleTo("FileSystem.Fakes",
    PublicKey=<Alternate_public_key>)]
[assembly: InternalsVisibleTo("FileSystem.Tests",
    PublicKey=<Test_assembly_public_key>)]
```

W przykładzie powyżej wartości `Alternate_public_key` i `Test_assembly_public_key` może być taka sama.

### <a name="optimize-build-times"></a>Optymalizuj czas kompilacji

Kompilacja zestawów elementów sztucznych może znacznie zwiększyć czas kompilacji. Aby zminimalizować czas kompilacji, generowanie zestawów elementów sztucznych dla zestawów platformy .NET systemu i innych zestawów w oddzielny projekt scentralizowane. Ponieważ takie zestawy rzadko zmieniać na tym komputerze, można użyć ponownie wygenerowanego zestawów elementów sztucznych w innych projektach.

Z Twojego projektów testów jednostkowych Dodaj odwołanie do skompilowane zestawy elementów sztucznych, które są objęte FakesAssemblies w folderze projektu.

1.  Tworzenie nowej biblioteki klas z wersją środowiska uruchomieniowego .NET dopasowania projektów testów. Teraz wywołać ją Fakes.Prebuild. Usuń *class1.cs* plik z projektu nie jest wymagane.

2.  Dodaj odwołanie do systemu i zestawy innych firm, potrzebnych elementów sztucznych dla.

3.  Dodaj *.fakes* pliku dla każdego z zestawów i kompilacji.

4.  Z projektu testowego

    -   Upewnij się, że odwołanie do środowiska wykonawczego elementów sztucznych biblioteki DLL:

         *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PublicAssemblies\Microsoft.QualityTools.Testing.Fakes.dll*

    -   Dla każdego zestawu, który został utworzony substytutów dla, Dodaj odwołanie do odpowiedniego pliku biblioteki DLL w *Fakes.Prebuild\FakesAssemblies* folderu projektu.

### <a name="avoid-assembly-name-clashing"></a>Unikaj konfliktowe nazwy zestawu

W środowisku Team Build wszystkie dane wyjściowe kompilacji są scalane w jeden katalog. Wiele projektów, użyj elementów sztucznych, może się zdarzyć, zestawów elementów sztucznych z różnych wersji zastępują siebie nawzajem. Na przykład elementów sztucznych TestProject1 *mscorlib.dll* z substytutami .NET Framework 2.0 i TestProject2 *mscorlib.dll* dla programu .NET Framework 4 zarówno ważnością do *mscorlib. Fakes.dll* zestaw Substytuowany.

 Aby uniknąć tego problemu, elementów sztucznych automatycznie utworzyć nazwy zestawu elementów sztucznych wersji kwalifikowana dla odwołania do projektu z systemem innym niż podczas dodawania *.fakes* plików. Określona wersja nazwy zestawu elementów sztucznych osadza numer wersji, podczas tworzenia nazwy zestawu elementów sztucznych:

 Podany zestaw MyAssembly i wersji 1.2.3.4 nazwy zestawu elementów sztucznych jest MyAssembly.1.2.3.4.Fakes.

 Możesz zmienić lub usunąć, edytując atrybut Version elementu zestawu w tej wersji *.fakes*:

```xml
attribute of the Assembly element in the .fakes:
<Fakes ...>
  <Assembly Name="MyAssembly" Version="1.2.3.4" />
  ...
</Fakes>
```

## <a name="fakes-naming-conventions"></a>Konwencje nazewnictwa elementów sztucznych

### <a name="shim-type-and-stub-type-naming-conventions"></a>Typ podkładki i stub typ konwencje nazewnictwa

 **Przestrzenie nazw**

-   . Substytuty sufiks zostanie dodany do przestrzeni nazw.

     Na przykład `System.Fakes` przestrzeń nazw zawiera typy podkładek przestrzeni nazw systemu.

-   Global.Fakes zawiera typ podkładki pustej przestrzeni nazw.

 **Nazwy typów**

-   Prefiks podkładki jest dodawany do Nazwa typu nazwa typu podkładki kompilacji.

     Na przykład ShimExample jest typu podkładki typu przykład.

-   Prefiks stub jest dodawany do nazwy typu do tworzenia szkieletu nazwy typu.

     Na przykład StubIExample jest typ klasy zastępczej typu IExample.

 **Argumenty typu i struktur typu zagnieżdżonego**

-   Argumenty typu ogólnego są kopiowane.

-   Dla typów podkładek jest kopiowany struktura typu zagnieżdżonego.

### <a name="shim-delegate-property-or-stub-delegate-field-naming-conventions"></a>Podkładki delegata właściwość skrótowa delegata pola lub konwencje nazewnictwa

**Podstawowe reguły** pola nazw, zaczynając od pustej nazwy:

-   Nazwa metody jest dołączany.

-   Nazwa metody jest jawnej implementacji interfejsu, usunięcie punktów.

-   Jeśli metody jest rodzajowy, `Of` *n* jest dołączana w przypadku gdy *n* jest liczbą argumentów metody rodzajowej.

 **Nazwy metody specjalnej** takie jak właściwości metody pobierającej lub metody ustawiające są traktowane jak opisano w poniższej tabeli:

|Jeśli metoda jest...|Przykład|Nazwa metody dołączone|
|-------------------|-------------|--------------------------|
|A **— Konstruktor**|`.ctor`|`Constructor`|
|Statycznego **— Konstruktor**|`.cctor`|`StaticConstructor`|
|**Akcesor** metodą nazwa składa się z dwóch części oddzielone "_", (na przykład pobierających właściwości)|*kind_name* (typowe case, ale nie jest wymuszone przez ECMA)|*NameKind*, gdy oba składniki zostały kapitalizacji i zamiany|
||Metoda pobierająca właściwości `Prop`|`PropGet`|
||Metoda ustawiająca właściwości `Prop`|`PropSet`|
||Obiekt dodający zdarzenia|`Add`|
||Obiekt usuwający zdarzenia|`Remove`|
|**Operator** składa się z dwóch części|`op_name`|`NameOp`|
|Na przykład: + — operator|`op_Add`|`AddOp`|
|Aby uzyskać **operatora konwersji**, zwracany typ jest dołączany.|`T op_Implicit`|`ImplicitOpT`|

> [!NOTE]
> - **Indeksatory metod ustawiających i pobierających** traktuje się podobnie do właściwości. Domyślna nazwa dla indeksatora jest `Item`.
> - **Typ parametru** nazwy są przetwarzane i połączone.
> - **Zwracany typ** jest ignorowana, chyba że istnieje niejednoznaczność przeciążenia. W przypadku amiguity przeciążenia, zwracany typ jest dołączany na końcu nazwy.

### <a name="parameter-type-naming-conventions"></a>Konwencje nazewnictwa typu parametru

|Podane|Ciąg dołączany jest...|
|-----------|-------------------------|
|A **typu**`T`|T<br /><br /> Przestrzeń nazw, zagnieżdżone struktury i rodzajowy e są usuwane.|
|**Parametru out**`out T`|`TOut`|
|A **parametru ref** `ref T`|`TRef`|
|**Typu tablicy**`T[]`|`TArray`|
|A **tablicy wielowymiarowej** typu `T[ , , ]`|`T3`|
|A **wskaźnika** typu `T*`|`TPtr`|
|A **typu ogólnego**`T<R1, ...>`|`TOfR1`|
|A **argumentu typu ogólnego** `!i` typu `C<TType>`|`Ti`|
|A **argumentu metody ogólnej** `!!i` metody `M<MMethod>`|`Mi`|
|A **typu zagnieżdżonego**`N.T`|`N` jest dołączany następnie `T`|

### <a name="recursive-rules"></a>Reguły cykliczne

Następujące reguły są stosowane rekursywnie:

-   Ponieważ elementów sztucznych używa języka C#, aby wygenerować zestawów Subtytuowanych, dowolny znak, który zwróci nieprawidłowy token C# została zmieniona na "_" (podkreślenie).

-   Jeśli wynikowa nazwa powoduje konflikt z dowolnego członka typu deklarującego, schemat numeracji jest używany przez dodanie licznika dwóch cyfr, zaczynając od 01.

## <a name="see-also"></a>Zobacz także

- [Izolowanie testowanego z Microsoft Fakes kodu](../test/isolating-code-under-test-with-microsoft-fakes.md)
