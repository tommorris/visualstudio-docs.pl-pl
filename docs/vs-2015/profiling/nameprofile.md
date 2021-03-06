---
title: NameProfile | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NameProfile
- NameProfileA
ms.assetid: 1bb05441-c4ff-4323-9fef-f3924fba4430
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 966a3557c4436a625c7b8cd07ce850216085f194
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628998"
---
# <a name="nameprofile"></a>NameProfile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [NameProfile](https://docs.microsoft.com/visualstudio/profiling/nameprofile).  
  
`NameProfile` Funkcja przypisuje ciągu określonego procesu lub wątku.  
  
 Interfejs API NameProfile jest dostępna tylko w przypadku profilowania instrumentacji. Interfejs API NameProfile nie jest obsługiwane dla pobierania próbek profilowania.  
  
## <a name="syntax"></a>Składnia  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI NameProfile(  
                                   LPCTSTR pszName,   
                                   PROFILE_CONTROL_LEVEL Level,  
                                   unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszName`  
  
 Nazwa elementu profilowania. Nazwa jest nieprawidłowa, (co powoduje zwrotu NAME_ERROR_INVALID_NAME NameProfileA), jeśli:  
  
-   Wskaźnik, który został przekazany do NameProfileA jest wartość NULL  
  
-   Dane ciągu pszName zaczyna się od numeru  
  
-   Dane ciągu pszName zawiera spację  
  
-   Dane ciągu pszName zawiera dowolny z następujących znaków:,. ' ~! @# $% ^ & * () = []{}&#124;\\? / <>  
  
 `Level`  
  
 Wskazuje poziom profilu do wydajności, które mogą być stosowane zbierania danych. Następujące **PROFILE_CONTROL_LEVEL** wartości może służyć do wskazania jednego z trzech poziomów wydajności, które zbieranie danych można stosować:  
  
|Moduł wyliczający|Opis|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Globalne ustawienie poziomie ma wpływ na wszystkie procesy i wątki podczas uruchomienia profilowania.|  
|PROFILE_PROCESSLEVEL|Ustawienie poziomie proces wpływają na wszystkie wątki, które są dostępne w ramach określonego procesu.|  
|PROFILE_THREADLEVEL|Wątek ustawienie poziomie profilowania dotyczy określonego wątku.|  
  
 `dwId`  
  
 Profilowanie identyfikator poziomu. Użyj proces lub wątek identyfikator, który jest generowany przez system.  
  
## <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość  
 Funkcja wskazuje powodzenie lub niepowodzenie, za pomocą **PROFILE_COMMAND_STATUS** wyliczenia. Zwracana wartość może być jedną z następujących czynności:  
  
|Moduł wyliczający|Opis|  
|----------------|-----------------|  
|NAME_ERROR_ID_NOEXIST|Określony element profilowania nie istnieje.|  
|NAME_ERROR_INVALID_NAME|Nazwa jest nieprawidłowa.|  
|NAME_ERROR_LEVEL_NOEXIST|Poziom określony profil nie istnieje.|  
|NAME_ERROR_NO_SUPPORT|Określona operacja nie jest obsługiwana.|  
|NAME_ERROR_OUTOFMEMORY|Pamięć nie jest dostępny do rejestrowania zdarzenia.|  
|NAME_ERROR_REDEFINITION|Nazwa już została przypisana do elementu profilu. Nazwa tej funkcji jest ignorowana.|  
|NAME_ERROR_TEXTTRUNCATED|Tekst nazwa przekracza 32 znaków, łącznie ze znakiem null i dlatego została obcięta.|  
|NAME_OK|Nazwa została pomyślnie zarejestrowana.|  
  
## <a name="remarks"></a>Uwagi  
 Tylko jedną nazwę można przypisać do każdego proces lub wątek. Po nazwie elementu profilowania kolejnych wywołań NameProfile dla tego elementu są ignorowane.  
  
 Jeśli w tej samej nazwie znajduje się w różnych wątkach lub procesach, w raporcie zostaną uwzględnione dane ze wszystkich elementów na tym samym poziomie o tej nazwie.  
  
 Jeśli określisz, proces lub wątek innego niż bieżący, upewnij się, że została zainicjowana i został uruchomiony przed nadaj mu nazwę. W przeciwnym razie metoda NameProfile kończy się niepowodzeniem.  
  
> [!IMPORTANT]
>  Funkcje CreateProcess() i CreateThread() interfejsu API może zwrócić przed wątku lub proces został zainicjowany.  
  
## <a name="net-framework-equivalent"></a>Odpowiednik w programie .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informacje o funkcji  
  
|||  
|-|-|  
|**Nagłówek**|Obejmują VSPerf.h|  
|**Biblioteka**|Użyj VSPerf.lib|  
|**Unicode**|Zaimplementowane jako `NameProfileW` (Unicode) i `NameProfileA` (ANSI).|  
  
## <a name="example"></a>Przykład  
 Poniższy kod ilustruje NameProfile wywołania funkcji. W przykładzie założono użycie makra ciągu Win32 i ustawienia kompilatora standardu ANSI ustalić, czy kod wywołuje ANSI jest włączona funkcja.  
  
```  
void ExerciseNameProfile()  
{  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Create and initialize variables to pass to   
    // ExerciseNameProfile.  The value of this   
    // parameter is based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variable is assigned an arbitrary value.  
    TCHAR * profileName = TEXT("ExerciseNameProfile");  
  
    // Declare enumeration to hold result of call to   
    // ExerciseNameProfle.  
    PROFILE_COMMAND_STATUS nameResult;  
  
    nameResult =  NameProfile(  
        profileName,  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("NameProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, nameResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Dokumentacja interfejsu API Profiler programu Visual Studio (Native)](../profiling/visual-studio-profiler-api-reference-native.md)



