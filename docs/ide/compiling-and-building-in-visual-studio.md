---
title: Kompilowanie i tworzenie w programie Visual Studio
ms.date: 07/14/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- builds [Visual Studio], about building in Visual Studio
- custom build steps, types of builds
ms.assetid: c7958821-285f-4e28-9e7a-b5d8b40336a1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c1e911dad2b4abe2fb092b2adb221c4aebec136
ms.sourcegitcommit: 3dd15e019cba7d35dbabc1aa3bf55842a59f5278
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46370773"
---
# <a name="compile-and-build-in-visual-studio"></a>Skompilować i utworzyć w programie Visual Studio

Uruchamianie kompilacji tworzy zestawów i aplikacji wykonywalnych z kodu źródłowego w dowolnym momencie podczas cyklu rozwoju. Ogólnie rzecz biorąc proces kompilacji jest bardzo podobne w wielu różnych typach projektów, takich jak Windows, ASP.NET, aplikacje mobilne i inne. Proces kompilacji jest również bardzo podobne w językach programowania, takich jak C#, Visual Basic, C++ i F #.

Przez kompilacjom kodu, można szybko zidentyfikować błędy kompilacji, takie jak niepoprawna składnia, błędnie napisane słowa kluczowe i wpisz niezgodności. Można również szybko wykryć i poprawić błędy czasu wykonywania, takie jak błędy logiczne i semantyczne, dzięki częstym kompilacjom i uruchamianiu wersji debugowania kodu.

Pomyślnej kompilacji jest zasadniczo weryfikacji, że kod źródłowy aplikacji zawiera poprawną składnię i wszystkie statyczne odwołania do bibliotek, zespoły i inne składniki zostały rozwiązane. To tworzy plik wykonywalny aplikacji, który można następnie pod kątem prawidłowego działania w obu [debugowania środowiska](../debugger/index.md) i przy użyciu różnych ręcznych i automatycznych testów [weryfikować jakość kodu](../test/improve-code-quality.md). Po w pełni przetestowano aplikację można skompilować wydaną wersję do wdrażania na klientach. Aby zapoznać się z wprowadzeniem do tego procesu, zobacz [przewodnik: budowanie aplikacji](../ide/walkthrough-building-an-application.md).

Używasz jednej z następujących metod do tworzenia aplikacji: środowiska IDE programu Visual Studio, narzędzia wiersza polecenia programu MSBuild i potoków usługi Azure:

| Metoda kompilacji | Zalety |
| --- |--- | --- |
| IDE |-Kompilacji od razu utworzyć i Testuj je w debugerze.<br />— Uruchamianie kompilację na wielu procesorach dla projektów C++ i C#.<br />— Dostosowywanie różne aspekty systemu kompilacji. |
| Wiersz polecenia programu MSBuild| -Kompilować projekty bez konieczności instalowania programu Visual Studio.<br />-Tworzy wykonywania wielu procesorach dla wszystkich typów projektów.<br />-Dostosować większość obszarów systemu kompilacji.|
| Potoki usługi Azure | — Automatyzowanie procesu kompilacji w ramach potoku ciągłej integracji/ciągłego dostarczania.<br />-Zastosować testy automatyczne z każdą kompilacją.<br />-Zatrudniać praktycznie nieograniczona liczba zasobów w chmurze dla procesów kompilacji.<br />-Modyfikować przepływ kompilacji oraz tworzyć aktywności kompilacji, aby wykonywać zadania wysoce niestandardowe.|

Dokumentacja w tej sekcji przechodzi w stan więcej szczegółowych informacji z procesu kompilacji oparte na środowisku IDE. Aby uzyskać więcej informacji o innych metodach, zobacz [MSBuild](../msbuild/msbuild.md) i [potoki Azure](/azure/devops/pipelines/index?view=vsts)odpowiednio.

## <a name="overview-of-building-from-the-ide"></a>Omówienie tworzenia z poziomu środowiska IDE

Podczas tworzenia projektu Visual Studio stworzył domyślne konfiguracje kompilacji dla projektu i rozwiązania, które zawiera projekt.  Te konfiguracje definiują sposób rozwiązania i projekty są zbudowane i wdrażane. W szczególności, konfiguracje projektu są unikatowe dla platformy docelowej (na przykład Windows lub Linux) i typ (na przykład debug i release) kompilacji. Te konfiguracje można edytować, jednak, a także mogą tworzyć własne konfiguracje, zgodnie z potrzebami.

Pierwszy wprowadzenie do tworzenia w środowisku IDE, zobacz [przewodnik: budowanie aplikacji](walkthrough-building-an-application.md).

Następnie możesz zapoznać się [kompilowanie oraz Oczyszczanie projektów i rozwiązań w programie Visual Studio](building-and-cleaning-projects-and-solutions-in-visual-studio.md) Aby dowiedzieć się więcej o dostosowywaniu różne aspekty można wprowadzić do procesu. Możliwe modyfikacje obejmują [zmiany katalogu danych wyjściowych](how-to-change-the-build-output-directory.md), [Określanie niestandardowych zdarzeń kompilacji](specifying-custom-build-events-in-visual-studio.md), [Zarządzanie zależności projektu](how-to-create-and-remove-project-dependencies.md), [Zarządzanie rejestr kompilacji pliki](how-to-view-save-and-configure-build-log-files.md), i [pomijanie ostrzeżeń kompilatora](how-to-suppress-compiler-warnings.md).

Z tego miejsca możesz zapoznać się z wielu innych zadań:
- [O konfiguracjach kompilacji](understanding-build-configurations.md)
- [Omówienie platformy kompilacji](understanding-build-platforms.md)
- [Zarządzaj właściwościami projektu i rozwiązania](managing-project-and-solution-properties.md).
- Określanie zdarzeń kompilacji w [C#](how-to-specify-build-events-csharp.md) i [języka Visual Basic](how-to-specify-build-events-visual-basic.md).
- [Ustawianie opcji kompilacji](reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Tworzenie wielu projektów w sposób równoległy](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).

## <a name="see-also"></a>Zobacz także

- [(Kompilacja) kompilowanie projektów witryny sieci Web](http://msdn.microsoft.com/Library/a9cbb88c-8fff-4c67-848b-98fbfd823193)
