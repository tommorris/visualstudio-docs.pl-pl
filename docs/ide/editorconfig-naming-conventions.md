---
title: .NET nazewnictwa konwencje dla plików EditorConfig
ms.date: 11/20/2017
ms.topic: reference
helpviewer_keywords:
- naming conventions [EditorConfig]
- EditorConfig naming conventions
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: df74252361e330ac992f8f3e852d9c33006d18e7
ms.sourcegitcommit: 6672a1e9d135d7e5cca3cceea07c6fe5a0871475
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2018
ms.locfileid: "47443587"
---
# <a name="net-naming-conventions-for-editorconfig"></a>Konwencje nazewnictwa platformy .NET dla wtyczki EditorConfig

Konwencje nazewnictwa dotyczą nazewnictwa elementów kodu, takich jak klasy, właściwości i metody. Na przykład można określić, czy publiczne elementy Członkowskie musi być napisane wielkimi literami oraz że metod asynchronicznych może kończyć się "Async". Te zasady można wymusić, określając je w [pliku .editorconfig](../ide/create-portable-custom-editor-options.md). Naruszeń zasady nazewnictwa są wyświetlane w **lista błędów** lub jako sugestię w obszarze nazwy, w zależności od ważności można wybrać dla tej reguły. Nie ma potrzeby do skompilowania projektu, aby można było wyświetlić naruszenia.

Konwencje nazewnictwa powinny być uporządkowane od najbardziej specyficznych do najmniej specyficznych w *.editorconfig* pliku. Pierwszą regułę napotkano, które mogą być stosowane jest tylko reguła, która jest stosowana.

Dla każdego konwencji nazewnictwa należy określić symbole, których on obowiązuje, styl nazewnictwa i ważność wymuszania Konwencji, za pomocą właściwości opisanych poniżej. Kolejność właściwości nie jest ważna.

Aby rozpocząć, wybierz tytuł dla tej reguły nazewnictwa, która będzie używana we wszystkich właściwości, które są potrzebne do w pełni opisu reguły. Na przykład `public_members_must_be_capitalized` jest dobrą nazwę opisową dla reguły nazewnictwa. Będziemy się odwoływać do tytułu, wybierz jako **< namingRuleTitle\>**  w kolejnych sekcjach.

## <a name="symbols"></a>Symbole

Najpierw należy zidentyfikować grupy symbole, aby zastosować regułę nazewnictwa. Ta właściwość ma następujący format:

`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`

Nadaj nazwę grupie symbole, zastępując **< symbolTitle\>**  wartością opisowy tytuł, na przykład `public_symbols`. Użyjesz **< symbolTitle\>**  wartości w nazwach trzy właściwości, które opisują, która symboli reguła jest stosowana do (rodzaje symboli, poziomów ułatwień dostępu i Modyfikatory).

### <a name="kinds-of-symbols"></a>Rodzaje symboli

Aby opisać rodzaj symbole, aby zastosować regułę nazewnictwa, należy określić właściwość w następującym formacie:

`dotnet_naming_symbols.<symbolTitle>.applicable_kinds = <values>`

Na poniższej liście przedstawiono dopuszczalne wartości i można określić wiele wartości, rozdzielając je przecinkami.

- \* (Użyj tej wartości, aby określić wszystkie symbole)
- — przestrzeń nazw
- class
- struktura 
- interface
- enum
- property
- — metoda
- pole
- zdarzenie
- delegate
- parametr
- type_parameter
- local
- local_function

### <a name="accessibility-levels-of-symbols"></a>Poziomy ułatwień dostępu symboli

Aby opisać poziomów ułatwień dostępu symboli ma być stosowana reguła nazewnictwa, należy określić nazwę właściwości w następującym formacie:

`dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities = <values>`

Na poniższej liście przedstawiono dopuszczalne wartości i można określić wiele wartości, rozdzielając je przecinkami.

- \* (Ta wartość służy do określenia wszystkich poziomów ułatwień dostępu)
- public
- wewnętrzny lub friend
- private
- protected
- chronione\_wewnętrznego lub protected_friend
- local

> [!NOTE]
> Nie należy określać poziomem ułatwień dostępu w ramach konwencji nazewnictwa, jeśli ułatwień dostępu nie ma zastosowania do typu symboli, które są przeznaczone dla. Na przykład parametry mają poziomów ułatwień dostępu. Jeśli określisz poziom dostępności dla parametru konwencji nazewnictwa, reguły nazewnictwa nie będą działać poprawnie.

### <a name="symbol-modifiers"></a>Modyfikatory symboli

Aby opisać modyfikatorów symbole ma być stosowana reguła nazewnictwa, należy określić nazwę właściwości w następującym formacie:

`dotnet_naming_symbols.<symbolTitle>.required_modifiers = <values>`

Na poniższej liście przedstawiono dopuszczalne wartości i można określić wiele wartości, rozdzielając je przecinkami.

- `abstract` lub `must_inherit`
- `async`
- `const`
- `readonly`
- `static` lub `shared`

   > [!NOTE]
   > Jeśli masz regułę nazewnictwa dla `static` lub `shared` symboli, zostanie ono również zastosowane do `const` symboli, ponieważ są one niejawnie statyczne. Jeśli nie chcesz `static` nazewnictwa reguła była stosowana do `const` symbole, Utwórz oddzielne regułę nazewnictwa `const` symboli.

`required_modifiers` jest opcjonalną właściwością. Jeśli pominiesz tę właściwość, reguły nazewnictwa będą dotyczyć wszystkich modyfikatorów.

## <a name="style"></a>Styl

Teraz, stwierdziliśmy grupy symbole, aby zastosować regułę nazewnictwa opisujemy musi stylu nazewnictwa. Styl może być, czy nazwa ma niektórych prefiks lub sufiks określonych, lub że poszczególnych wyrazów w nazwie są rozdzielone znakiem niektórych. Można również określić styl wielkość liter. Właściwości stylu ma następujący format:

`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`

Nadaj nazwę stylu, zastępując **< styleTitle\>**  wartością opisowy tytuł, na przykład `first_word_upper_case_style`. Użyjesz **< styleTitle\>**  wartości nazw właściwości, które opisują styl nazewnictwa (prefiks, sufiks, znak separatora słowa i wielkości liter). Użyj co najmniej jeden z tych właściwości w celu opisania własnego stylu.

### <a name="require-a-prefix"></a>Wymagany prefiks

Aby określić, że nazwy symboli musi zaczynać się niektórych znaków, należy użyć tej właściwości:

`dotnet_naming_style.<styleTitle>.required_prefix = <prefix>`

### <a name="require-a-suffix"></a>Wymagaj sufiks

Aby określić, czy nazwy symboli musi się kończyć niektórych znaków, należy użyć tej właściwości:

`dotnet_naming_style.<styleTitle>.required_suffix = <suffix>`

### <a name="require-a-certain-word-separator"></a>Wymagaj separator wyrazów

Aby określić, że poszczególne wyrazy w nazwy symboli muszą być oddzielone znakiem niektórych, użyj tej właściwości:

`dotnet_naming_style.<styleTitle>.word_separator = <separator character>`

### <a name="require-a-capitalization-style"></a>Wymagaj styl wielkość liter

Aby określić styl określonego wielkość liter nazwy symboli, użyj tej właściwości:

`dotnet_naming_style.<styleTitle>.capitalization = <value>`

Dopuszczalne wartości dla tej właściwości to:

- pascal_case
- camel_case
- pierwszy\_word_upper
- wszystkie\_górny
- all_lower

> [!NOTE]
> Należy określić stylu pisania wielkimi jako część usługi nazewnictwa styl, w przeciwnym razie własnego stylu nazewnictwa może być ignorowane.

## <a name="severity"></a>Ważność

Aby opisać ważność naruszenie reguły nazewnictwa, należy określić właściwość w następującym formacie:

`dotnet_naming_rule.<namingRuleTitle>.severity = <value>`

W poniższej tabeli przedstawiono wartości dozwoloną ważności i ich znaczenie:

Ważność | Efekt
------------ | -------------
Brak lub silent | Gdy nie trwa występuje ten styl, nie pokazuj żadnych dla użytkownika; jednak automatycznie wygenerowany kod poniżej tego stylu.
Sugestia | Gdy nie trwa występuje ten styl, wyświetlane użytkownikowi jako sugestię jako bazowego kropki na pierwszych dwóch znaków. Nie ma ona wpływu w czasie kompilacji.
ostrzeżenie | Gdy nie trwa występuje ten styl, Pokaż ostrzeżenia kompilatora w **lista błędów**.
Błąd | Gdy nie trwa występuje ten styl, Pokaż błąd kompilatora w **lista błędów**.

> [!NOTE]
> Nie masz do kompilowania projektu, aby można było wyświetlić naruszenia reguły nazewnictwa. Pojawiają się jako edycji kodu w **lista błędów** lub sugestię.

## <a name="example"></a>Przykład

Następujące *.editorconfig* plik zawiera konwencji nazewnictwa, która określa, czy właściwości publiczne, metody, pola, zdarzenia i delegatów musi być napisane wielkimi literami. Należy zauważyć, że tę konwencję nazewnictwa określa wiele rodzajów symbolu, aby zastosować regułę, użyj przecinka, aby oddzielić wartości.

```EditorConfig
# Public members must be capitalized (public_members_must_be_capitalized)
[*.{cs,vb}]
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

Poniższy zrzut ekranu przedstawia efekt tę konwencję nazewnictwa w edytorze. Dwie zmienne publicznych zostały nazwane bez użycia wielkich liter w pierwszej litery. Jeden jest `const`, a jeden jest `readonly`. Ponieważ nazewnictwa reguła ma zastosowanie tylko do `readonly` symbole tylko `readonly` zmienna zawiera sugestię reguły nazewnictwa.

![Sugestia reguły nazewnictwa](media/editorconfig-naming-rule-suggestion.png)

Teraz zmienimy ważności naruszenia można `warning`:

```EditorConfig
dotnet_naming_rule.public_members_must_be_capitalized.severity = warning
```

Po zamknięciu i ponownym otwarciu pliku kodu, zamiast wyświetlanie sugestii w obszarze naruszenie nazwy zostanie wyświetlony zielony falista i ostrzeżenia w **lista błędów**:

![Ostrzeżenie reguły nazewnictwa](media/editorconfig-naming-rule-warning.png)

## <a name="see-also"></a>Zobacz także

- [Konwencje dotyczące formatowania i języka .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Tworzenie przenośnych niestandardowy Edytor opcji](../ide/create-portable-custom-editor-options.md)
- [Platforma kompilatora .NET pliku .editorconfig](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
