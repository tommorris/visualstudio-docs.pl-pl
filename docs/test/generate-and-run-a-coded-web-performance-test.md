---
title: "Kodowane testy wydajności sieci web w programie Visual Studio | Dokumentacja firmy Microsoft"
ms.date: 10/03/2016
ms.topic: article
helpviewer_keywords:
- Web performance tests, walkthroughs
- Web performance tests, creating
- code, Web performance tests
- Web performance tests, coded
ms.assetid: 169e48f9-52fd-4d0b-83d9-54913bde506b
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 7eb493667719b41d8014c1d9106328600a4aff0a
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2018
---
# <a name="generate-and-run-a-coded-web-performance-test"></a>Generowanie i uruchamianie kodowanego testu wydajności sieci Web

Testy wydajności sieci Web są rejestrowane przez przeglądanie aplikacji sieci web. Testy znajdują się w testach obciążenia do pomiaru wydajności aplikacji sieci web mocno obciążony wielu użytkowników. Test wydajności sieci web może zostać przekonwertowany do opartej na kodzie skryptu, który można edytować i dostosować podobnie jak inne kodu źródłowego. Na przykład można dodać konstrukcji pętli i gałęzi.

## <a name="generate-a-coded-web-performance-test"></a>Generowanie kodowanego testu sieci web wydajności

1.  Jeśli nie utworzono testu wydajności sieci web, zobacz [rejestrowania testu wydajności sieci web](/vsts/load-test/run-performance-tests-app-before-release#create-a-web-performance-and-load-test-project).

2.  Generowanie kodowanego testu.

     ![Generowanie kodowanego testu sieci web wydajności](../test/media/web_test_coded_generate.png)

3.  Nazwa testu.

     ![Wprowadź nazwę dla testów wydajności sieci web kodowane](../test/media/web_test_coded_generate_nametest.png)

     Nowe kodowanego testu zostanie otwarty w edytorze kodu.

     W zależności od tego, które wydajności sieci web i szablon projektu testu obciążenia dodany do rozwiązania zostanie wygenerowany kod w języku Visual Basic lub Visual C#.

     ![Nowe kodowanego testu zostanie otwarty w edytorze kodu](../test/media/web_test_coded_generate_opencodeeditor.png)

     W kodzie widać, że metoda GetRequestEnumerator() w języku C# lub w języku Visual Basic metody Run() zawiera każdego żądania sprawdzenia poprawności reguły i w sieci web w teście recoded.

4.  Aby zademonstrować, Dodawanie prostego kodu, przewiń w dół do zakończenia metody i po kod ostatniego żądania sieci web i Dodaj następujący kod:

    ```c#
    if (DateTime.Today.DayOfWeek == DayOfWeek.Wednesday)
    {
        WebTestRequest customRequest = new WebTestRequest("http://weather.msn.com/");
        yield return customRequest;
    }
    else
    {
        WebTestRequest customRequest = new WebTestRequest("http://msdn.microsoft.com/");
        yield return customRequest;
    }
    ```

    ```vb
    If DateTime.Today.DayOfWeek = DayOfWeek.Wednesday Then
        Dim customRequest As WebTestRequest = New WebTestRequest("http://weather.msn.com/")
        MyBase.Send(customRequest)
    Else
        Dim customRequest As WebTestRequest = New WebTestRequest("http://msdn.microsoft.com/")
        MyBase.Send(customRequest)
    End If
    ```

5.  Tworzenie rozwiązania, aby sprawdzić, czy skompilowanie niestandardowego kodu.

6.  Uruchom test.

     ![Uruchamianie testu wydajności sieci web kodowane](../test/media/web_test_coded_generate_run.png "Web_Test_Coded_Generate_Run")

     Ponieważ dnia, to był uruchamiany się stało się środę...

     ![Kodowany wyników testu wydajności sieci web](../test/media/web_test_coded_generate_results.png "Web_Test_Coded_Generate_Results")

## <a name="qa"></a>FUNKCJA PYTANIA I ODPOWIEDZI

### <a name="q-can-i-run-more-than-one-test-at-a-time"></a>Pytanie: czy można uruchamiać więcej niż jeden test w czasie?
 **Odpowiedź:** tak, użyj menu kontekstowego w Eksploratorze rozwiązań.

### <a name="q-should-i-add-a-data-source-before-or-after-i-generate-a-coded-test"></a>Pytanie: źródło danych należy dodać przed lub po I Generowanie kodowanego testu?
 **A:** łatwiej [źródła danych](../test/add-a-data-source-to-a-web-performance-test.md), aby wygenerować kodowanego testu, ponieważ kod będą automatycznie generowane automatycznie.

 Po uruchomieniu kodowanego testu ze źródłem danych, mogą pojawić się następujący komunikat o błędzie:

 **Nie można uruchomić testu \<nazwę testu > na agencie \<nazwa komputera >: obiekt odwołania nie jest ustawione na wystąpienie obiektu.**

 Może to wystąpić, ponieważ ma DataSourceAttribute zdefiniowanej dla klasy testowej bez odpowiedniego DataBindingAttribute. Aby rozwiązać ten problem, Dodaj odpowiednie DataBindingAttribute, usuń go lub go komentarzy z kodu.

### <a name="q-should-i-add-validation-and-extraction-rules-before-or-after-i-generate-a-coded-test"></a>Pytanie: reguły walidacji i wyodrębniania należy dodać przed lub po I Generowanie kodowanego testu?
 **A:** łatwiej reguł sprawdzania poprawności i reguły wyodrębniania przed wygenerowaniem kodowanego testu; jednak firma Microsoft zaleca użycie [kodowanych testów interfejsu użytkownika](../test/use-ui-automation-to-test-your-code.md) do celów weryfikacji.