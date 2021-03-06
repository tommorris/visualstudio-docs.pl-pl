---
title: Dostosowywanie funkcji IntelliSense dla RequireJS | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2be07ef8-9c08-444b-a21a-22a4fe6386a3
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fbc4d9b85a3eb8e0fe5f3a890a76bae4695912e4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628063"
---
# <a name="customizing-intellisense-for-requirejs"></a>Dostosowywanie funkcji IntelliSense dla RequireJS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [dokumentacja programu Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/).  
  
Począwszy od programu Visual Studio 2013 Update 4, obsługę popularnych plik RequireJS JavaScript i modularnej modułu ładującego jest obsługiwane. RequireJS ułatwia definiowanie zależności między modułami kodu i załadować dynamicznie modułów tylko wtedy, gdy jest to wymagane. Podczas pisania kodu JavaScript, który używa RequireJS, sugestie funkcji IntelliSense zostanie podana dla modułów już przywoływany z definicji modułu lub odwoływać się za pomocą wywołania `require()` z w obrębie kodu.  
  
 Domyślnie program Visual Studio obsługuje bardzo podstawową konfigurację do obsługi RequireJS, ale jest powszechną praktyką, aby skonfigurować własne niestandardowe ustawienia konfiguracji (oznacza to, aby zdefiniować aliasów dla bibliotek). W tym temacie opisano różne sposoby, które można dostosować Visual Studio do pracy z projektu Instalatora unikatowy.  
  
 W tym temacie opisano sposób:  
  
-   Dostosowywanie RequireJS w projektach programu ASP.NET  
  
-   Dostosowywanie RequireJS w projektach JSProj, które są używane do tworzenia aplikacji Apache Cordova, aplikacje Windows Store i aplikacji LightSwitch HTML  
  
## <a name="customize-requirejs-in-aspnet-projects"></a>Dostosowywanie RequireJS w projektach programu ASP.NET  
 Obsługa RequireJS automatycznie jest włączona, gdy plik o nazwie require.js odwołuje się do bieżącego pliku JavaScript (Aby uzyskać więcej informacji, zobacz sekcję Określanie kontekstu IntelliSense w [JavaScript IntelliSense](../ide/javascript-intellisense.md)). W projektach programu ASP.NET, odwołuje się do require.js odbywa się zwykle przy użyciu / / / \<odwołania / > dyrektywy w pliku _references.js.  
  
### <a name="configure-the-data-main-attribute-in-an-aspnet-project"></a>Skonfigurowanie atrybutu main danych w projektach programu ASP.NET  
 Do końca dokładnie symulować, jak aplikacja będzie działać po uruchomieniu, Edytor kodu JavaScript musi wiedzieć, jakiego pliku, można najpierw załadować, podczas konfigurowania require.js. Jest to zazwyczaj konfigurowane w swojej aplikacji HTML plików za pomocą `data-main` atrybutu elementu skryptu, który odwołuje się do require.js, jak pokazano poniżej.  
  
```html  
<script src="js/require.js" data-main="js/app.js"></script>  
```  
  
 W tym przykładzie skrypt odwołuje się danych main (js/app.js) jest ładowany natychmiast po require.js. Plik, który jest ładowany natychmiast jest najlepszym miejscem, aby najpierw skonfigurować użycie RequireJS (przy użyciu `require.config()`). Sprawdzić Edytor kodu JavaScript, jakiego pliku na potrzeby `data-main` w aplikacji Dodaj `data-main` atrybutu, a następnie zmodyfikuj / / / \<odwołania / > dyrektywę, który odwołuje się do require.js w aplikacji. Na przykład można użyć tej dyrektywy:  
  
```javascript  
/// <reference path="js/require.js" data-main="js/app.js" />  
```  
  
### <a name="configure-the-application-start-page-in-an-aspnet-project"></a>Konfigurowanie strony początkowej aplikacji w projektach programu ASP.NET  
 Po uruchomieniu aplikacji, RequireJS założono, że względnych ścieżek do plików (na przykład, ".. \\"ścieżki) są względne wobec plik HTML, który załadowana biblioteka require.js. Podczas pisania kodu w edytorze programu Visual Studio dla projektu programu ASP.NET, ta strona początkowa jest nieznany i musisz poinformować edytora, co uruchomić stronę, aby użyć w przypadku użycia względne ścieżki do pliku. Aby to zrobić, Dodaj `start-page` atrybutu użytkownika / / / \<odwołania / > dyrektywy.  
  
```javascript  
/// <reference path="js/require.js" data-main="js/app.js" start-page="/app/index.html" />  
```  
  
 `start-page` Atrybut określa adres URL strony, jak go w przeglądarce podczas uruchamiania aplikacji.  
  
## <a name="customize-requirejs-in-jsproj-projects"></a>Dostosowywanie RequireJS w projektach JSProj  
 Projekty JSProj (pliki projektu kończące się na rozszerzenie .jsproj) są używane podczas tworzenia aplikacji dla aplikacji Apache Cordova, oparty na języku HTML aplikacji Windows Store Apps lub LightSwitch HTML. W przeciwieństwie do projektów programu ASP.NET te projekty odczytać odwołania do plików .js z plików HTML, które istnieje w projekcie. W związku z tym podczas edytowania kodu JavaScript w projekcie JSProj, zostanie wyświetlony, pomocy technicznej dla RequireJS jest włączona, jeśli plik JavaScript aktualnie edytowanym odwołuje się do innego pliku HTML, który odwołuje się require.js.  
  
 Kroki dostosowywania niezbędne dla projektów programu ASP.NET nie są potrzebne w pliku JSProj projektu. Oznacza to, że skrypt pliki używane przez `data-main` atrybut w tagu skryptu, który odwołuje się do require.js są ładowane automatycznie skonfigurować require.js. Plik HTML, odwołuje się do require.js służy również jako stronę startową dla aplikacji.  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcja IntelliSense dla języka JavaScript](../ide/javascript-intellisense.md)



