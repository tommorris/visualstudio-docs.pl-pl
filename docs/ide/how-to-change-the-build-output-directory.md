---
title: 'Porady: zmiana katalogu wyjściowego kompilacji'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aebb4603d32f61c2d4b50355a550a1a932336962
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379692"
---
# <a name="how-to-change-the-build-output-directory"></a>Porady: zmiana katalogu wyjściowego kompilacji

Należy określić lokalizację danych wyjściowych, na podstawie — konfiguracja (w przypadku debugowania, wersji lub obie) wygenerowany przez projekt.

> [!NOTE]
> Jeśli masz **Instalatora** projektu, zobacz uwagę na końcu tego artykułu.

## <a name="change-the-build-output-directory"></a>Zmiana katalogu wyjściowego kompilacji

1.  Na pasku menu wybierz **projektu** > **\<nazwa_aplikacji > właściwości**. Również kliknięciu prawym przyciskiem myszy węzeł projektu w **Eksploratora rozwiązań** i wybierz **właściwości**.

2.  Jeśli masz projekt języka Visual Basic, wybierz **skompilować** kartę. Jeśli masz projekt C#, wybierz opcję **kompilacji** kartę. Jeśli masz projekt języka C++ lub projektu w języku JavaScript, wybierz opcję **ogólne** kartę.

3.  W konfiguracji listy rozwijanej u góry wybierz konfigurację, której dane wyjściowe pliku lokalizacji, aby zmienić (debugowanie, wydanie lub wszystkie).

     Znajdź pozycję Ścieżka danych wyjściowych (**ścieżkę wyjściową kompilacji** w języku Visual Basic **katalog wyjściowy** w programie Visual C++ **ścieżkę wyjściową** w języku JavaScript i C#). Określ nowy katalog danych wyjściowych kompilacji względem katalogu projektu.

> [!NOTE]
> W projekcie programu Instalatora **nazwę pliku wyjściowego** okno zmienia tylko lokalizacja *Setup.exe* pliku nie lokalizację plików projektu. Aby uzyskać więcej informacji, zobacz **kompilacji, właściwości konfiguracji, okno dialogowe właściwości projektu wdrożenia**.

## <a name="see-also"></a>Zobacz także

- [Strona kompilacji, Projektant projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Strona właściwości ogólnych (projekt)](/cpp/ide/general-property-page-project)
- [Kompilowanie i tworzenie kompilacji](../ide/compiling-and-building-in-visual-studio.md)