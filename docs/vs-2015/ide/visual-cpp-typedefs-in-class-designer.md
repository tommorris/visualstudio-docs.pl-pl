---
title: Definicje typów Visual C++ w Projektancie klas | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.classdesigner.typedef
- vs.classdesigner.aliasofline
helpviewer_keywords:
- Class Designer [Visual Studio], typedefs
ms.assetid: c1984108-71fc-4d3a-b4d4-3eac2c6b4ebf
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ba8987abf608d7f8d83a77c2e946f34941c1bec6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681135"
---
# <a name="visual-c-typedefs-in-class-designer"></a>Definicje typów Visual C++ w Projektancie klas
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [definicje typów Visual C++ w Projektancie klas](https://docs.microsoft.com/visualstudio/ide/visual-cpp-typedefs-in-class-designer).  
  
TypeDef — instrukcje utworzyć jedną lub więcej warstw pośredników między nazwą jej typ podstawowy. Projektant klas obsługuje C++ typedef typy, które są zadeklarowane za pomocą słowa kluczowego `typedef`, na przykład:  
  
```  
typedef class coord  
{  
   void P(x,y);  
   unsigned x;  
   unsigned y;  
} COORD;  
```  
  
 Tego typu można następnie użyć do deklarowania wystąpienie:  
  
 `COORD OriginPoint;`  
  
 Mimo że można zadeklarować element typedef bez nazwy, Projektant klas nie będzie używać nazwa tagu, który określisz; Nazwa która generuje widoku klasy zostanie użyty. Na przykład następująca deklaracja jest prawidłowy, ale będzie ono wyświetlane w widoku klas i projektanta klas jako obiekt o nazwie **__unnamed**:  
  
```  
typedef class coord  
{  
   void P(x,y);  
   unsigned x;  
   unsigned y;  
};  
```  
  
 Aby uzyskać więcej informacji o korzystaniu z `typedef` typu, zobacz [specyfikator typedef (NOTINBUILD)](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1).  
  
 Kształt typu C++ ma kształt z typem określonym w definicji typu. Na przykład, jeśli źródło deklaruje `typedef class`, kształt ma zaokrąglone rogi i etykiety **klasy**. Aby uzyskać `typedef struct`, kształt ma ostre rogi i etykieta **struktury**.  
  
 Klasy i struktury może mieć zagnieżdżonych definicje typów zadeklarowane wewnątrz nich. w związku z tym kształty klasy i struktury można pokazać deklaracje typedef zagnieżdżonych jako kształtów zagnieżdżonych.  
  
 Element TypeDef kształty pomocy technicznej **wyświetlić jako skojarzenie** i **pokazać jako skojarzenia kolekcji** poleceń w menu kontekstowym.  
  
 Poniżej przedstawiono kilka przykładów typów typdef, których Projektant klasy obsługuje:  
  
 `typedef type name`  
  
 *Nazwa* : *typu*  
  
 — klasa typedef  
  
 Rysuje linię skojarzenia nawiązywania połączenia z typu *nazwa*, jeśli to możliwe.  
  
 `typedef void (*func)(int)`  
  
 `func: void (*)(int)`  
  
 — klasa typedef  
  
 Element TypeDef dla wskaźników funkcji. Linia skojarzenia, nie jest rysowane.  
  
 Projektant klas nie jest wyświetlany element typedef, jeśli jego typ źródła jest wskaźnik funkcji.  
  
```  
typedef int MyInt;  
class A {  
   MyInt I;  
};  
```  
  
 `MyInt: int`  
  
 — klasa typedef  
  
 `A`  
  
 Class  
  
 Rysuje linię skojarzenia wskazuje źródło kształt typu kształt typu docelowego.  
  
 `Class B {};`  
  
 `typedef B MyB;`  
  
 `B`  
  
 Class  
  
 `MyB : B`  
  
 — klasa typedef  
  
 Kliknij prawym przyciskiem myszy kształt typu, a następnie klikając polecenie **Pokaż jako skojarzenie** Wyświetla element typedef lub klasy i **Alias** linię łączącą dwa kształty, które (podobnie jak linia skojarzenia).  
  
 `typedef B MyB;`  
  
 `typedef MyB A;`  
  
 `MyBar : Bar`  
  
 — klasa typedef  
  
 Wartość taka sama jak powyżej.  
  
```  
Class B {};  
typedef B MyB;  
  
class A {  
   MyB B;  
};  
```  
  
 `B`  
  
 Class  
  
 `MyB : B`  
  
 — klasa typedef  
  
 `A`  
  
 Class  
  
 `MyB` jest kształtem zagnieżdżony typedef.  
  
 `#include <vector>`  
  
 `...`  
  
 `using namespace std;`  
  
 `...`  
  
 `typedef vector<int> MyIntVect;`  
  
 `vector<T>`Klasa  
  
 `MyIntVect : vector<int>`  
  
 — klasa typedef  
  
 `class B {};`  
  
 `typedef B MyB;`  
  
 `class A : MyB {};`  
  
 `MyB : B`  
  
 — klasa typedef  
  
 -> B  
  
 `B`  
  
 `A`  
  
 Class  
  
 -> MyB  
  
 Projektant klas nie obsługuje wyświetlania tego rodzaju relacji za pomocą polecenia menu kontekstowego.  
  
 `#include <vector>`  
  
 `Typedef MyIntVect std::vector<int>;`  
  
 `Class MyVect : MyIntVect {};`  
  
 `std::vector<T>`  
  
 Class  
  
 `MyIntVect : std::vector<int>`  
  
 — klasa typedef  
  
 `MyVect`  
  
 Class  
  
 -> MyIntVect  
  
## <a name="see-also"></a>Zobacz też  
 [Praca z kodem Visual C++ (Projektant klas)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Specyfikator typedef (NOTINBUILD)](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)



