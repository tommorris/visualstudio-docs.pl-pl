---
title: 'CA2003: Nie traktuj włókien jako wątków'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3322b968266ad6fdfe1be2e5bdaac73aad32b9c7
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551915"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Nie traktuj włókien jako wątków

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Kategoria|Microsoft.Reliability|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna

Zarządzane zarządzalny wątek jest traktowany jako wątek Win32.

## <a name="rule-description"></a>Opis reguły

Nie należy zakładać, że wątków zarządzanych jest wątek Win32; jest włókien. Środowisko uruchomieniowe języka wspólnego (CLR) jest uruchamiany w zarządzanych wątkach jako włókien w kontekście rzeczywistych wątki, które są własnością SQL. Te wątki mogą być współużytkowane przez nawet baz danych i domen aplikacji w procesie programu SQL Server. Za pomocą programu managed działa lokalny magazyn wątków, ale nie możesz użyć pamięci lokalnej wątku niezarządzanym lub przyjęto założenie, że Twój kod zostaną ponownie uruchomione w bieżącym wątku systemu operacyjnego. Nie należy zmieniać ustawienia, takie jak ustawienia regionalne wątku. Nie należy wywoływać CreateCriticalSection lub Funkcja CreateMutex za pośrednictwem metody P/Invoke, ponieważ wymagają one, wątek, który wprowadzi blokadę należy również zamknąć blokady. Ponieważ wątku, który wprowadzi blokady nie zakończyć blokadę, gdy używasz włókien, sekcje krytyczne Win32 i Muteksy są bezużyteczne w języku SQL. Większość stanu może być bezpiecznie korzystać na zarządzanej <xref:System.Threading.Thread> obiektu, łącznie z lokalnego magazynu zarządzanych wątków i bieżącej kultury interfejsu użytkownika wątku. Jednak podczas programowania modelu przyczyny, będzie można zmienić bieżącej kultury wątku, gdy używasz programu SQL. To ograniczenie, będą wymuszane za pośrednictwem nowego uprawnienia.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia

Sprawdź użycie wątków i odpowiednio zmień swój kod.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia

Nie pomijaj tej reguły.