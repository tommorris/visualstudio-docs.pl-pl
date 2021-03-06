---
title: Wpisy rejestru dotyczące dodatków narzędzi VSTO
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- LoadBehavior entry
- add-ins [Office development in Visual Studio], registry entries
- registry keys [Office development in Visual Studio]
- application-level add-ins [Office development in Visual Studio], registry entries
- registry entries [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e2aaec6df10a39d9f07938502a30eaa0a5d4ee9d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692899"
---
# <a name="registry-entries-for-vsto-add-ins"></a>Wpisy rejestru dotyczące dodatków narzędzi VSTO
  Określony zbiór wpisów rejestru należy utworzyć podczas wdrażania dodatków VSTO, które są tworzone za pomocą programu Visual Studio. Te wpisy rejestru zawierają informacje, które umożliwia aplikacji Microsoft Office odnaleźć i załadować dodatku VSTO.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Podczas kompilowania projektu programu Visual Studio tworzy te wpisy rejestru na komputerze dewelopera, dzięki czemu można łatwo uruchomić i debugowania dodatku VSTO. Jeśli używasz ClickOnce do wdrażania dodatku VSTO z wpisy rejestru są tworzone automatycznie na komputerze użytkownika końcowego. Wdrażanie dodatek VSTO za pomocą Instalatora Windows, należy skonfigurować projekt InstallShield Limited Edition można utworzyć wpisów rejestru na komputerze użytkownika końcowego.  
  
 Aby uzyskać więcej informacji o sposobie używania wpisy rejestru podczas procesu obciążenia dla dodatków VSTO, zobacz [dodatki architektura VSTO](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  W tym temacie, tekst *identyfikator dodatku* reprezentuje unikatowy identyfikator dla użytkownika dodatku VSTO. Domyślnie identyfikator jest nazwą zestawu dodatku VSTO.  
  
## <a name="register-vsto-add-ins-for-the-current-user-vs-all-users"></a>Zarejestruj dodatków narzędzi VSTO dla bieżącego użytkownika, a wszyscy użytkownicy  
 Dodatku VSTO jest zainstalowany, możesz go zarejestrować na dwa sposoby:  
  
-   Dla bieżącego użytkownika (czyli jest dostępne tylko dla użytkownika, który jest zalogowany na komputerze jest zainstalowany dodatek VSTO). W takim przypadku wpisy rejestru są tworzone w obszarze **HKEY_CURRENT_USER**.  
  
-   Dla wszystkich użytkowników (każdy użytkownik, który loguje się do komputera można używać dodatku VSTO). W takim przypadku wpisy rejestru są tworzone w obszarze **HKEY_LOCAL_MACHINE**.  
  
 Wszystkie VSTO dodatki utworzone przy użyciu programu Visual Studio może być zarejestrowany dla bieżącego użytkownika. Jednak można zarejestrować dodatków narzędzi VSTO dla wszystkich użytkowników tylko w niektórych scenariuszach. Te scenariusze są zależne od wersji pakietu Microsoft Office na komputerze i jak wdrożyć dodatku VSTO.  
  
### <a name="microsoft-office-version"></a>Wersja programu Microsoft Office  
 Aplikacje pakietu Office można załadować dodatków VSTO, które są zarejestrowane w obszarze **HKEY_LOCAL_MACHINE** lub **HKEY_CURRENT_USER**.  
  
 Można załadować dodatków VSTO, które są zarejestrowane w obszarze **HKEY_LOCAL_MACHINE**, komputery muszą mieć pakiet aktualizacji 976477 zainstalowane. Aby uzyskać więcej informacji, zobacz [http://go.microsoft.com/fwlink/?LinkId=184923](http://go.microsoft.com/fwlink/?LinkId=184923).  
  
### <a name="deployment-type"></a>Typ wdrożenia  
 Jeśli używasz ClickOnce do wdrażania dodatku VSTO dodatku VSTO można zarejestrować tylko dla bieżącego użytkownika. Jest to spowodowane ClickOnce obsługuje tylko tworzenie kluczy w obszarze **HKEY_CURRENT_USER**. Jeśli chcesz zarejestrować dodatku VSTO dla wszystkich użytkowników na komputerze, musi użyć Instalatora systemu Windows do wdrażania dodatku VSTO. Aby uzyskać więcej informacji o typach wdrożenia, zobacz [wdrażania rozwiązania do pakietu Office przy użyciu technologii ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md) i [wdrażania rozwiązania do pakietu Office przy użyciu Instalatora Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
## <a name="registry-entries"></a>Wpisy rejestru  
 Wymagane dodatku VSTO wpisy rejestru znajdują się w następującym kluczu rejestru dla wszystkich aplikacji, z wyjątkiem programu Visio, gdzie *głównego* jest **HKEY_CURRENT_USER** lub **HKEY_LOCAL_MACHINE** .  
  
 **Wszystkie aplikacje z wyjątkiem programu Visio**  
  
|Wersja pakietu Office|Ścieżka konfiguracji:|  
|--------------------|------------------------|  
|32-bitowa|*Główny*\Software\Microsoft\Office\\*Nazwa aplikacji*\Addins\\*identyfikator dodatku*|  
|64-bitowy|*Główny*\Software\Wow6432Node\Microsoft\Office\\*Nazwa aplikacji*\Addins\\*identyfikator dodatku*|  
  
 **Visio**  
  
|Wersja pakietu Office|Ścieżka konfiguracji:|  
|--------------------|------------------------|  
|32-bitowa|*Główny*\Software\Microsoft\Visio\Addins\\*identyfikator dodatku*|  
|64-bitowy|*Główny*\Software\Wow6432Node\Visio\Addins\\*identyfikator dodatku*|  
  
 W poniższej tabeli wymieniono wpisy w tym kluczu rejestru.  
  
|Wpis|Typ|Wartość|  
|-----------|----------|-----------|  
|**Opis**|REG_SZ|Wymagana. Krótki opis dodatku VSTO.<br /><br /> Ten opis jest wyświetlany, gdy użytkownik wybierze dodatku VSTO w **Add-Ins** okienku **opcje** okno dialogowe w aplikacji pakietu Microsoft Office.|  
|**friendlyName**|REG_SZ|Wymagana. Opisowa nazwa dodatku VSTO, która jest wyświetlana w **dodatki COM** okno dialogowe w aplikacji pakietu Microsoft Office. Wartość domyślna to identyfikator dodatku narzędzi VSTO|  
|**LoadBehavior**|REG_DWORD|Wymagana. Wartość, która określa, kiedy aplikacja próbuje załadować dodatku VSTO i bieżący stan dodatku VSTO (załadowany lub zwalnianie).<br /><br /> Domyślnie ten wpis jest ustawiony na 3, który określa, czy dodatku VSTO są ładowane podczas uruchamiania. Aby uzyskać więcej informacji, zobacz [wartości LoadBehavior](#LoadBehavior). **Uwaga:** Jeśli użytkownik wyłączy dodatku VSTO, ta akcja modyfikuje **LoadBehavior** wartość w **HKEY_CURRENT_USER** gałęzi rejestru. Dla każdego użytkownika, wartość **LoadBehavior** wartość w gałęzi HKEY_CURRENT_USER zastępuje domyślną **LoadBehavior** zdefiniowane w **HKEY_LOCAL_MACHINE** hive.|  
|**Manifest**|REG_SZ|Wymagana. Pełna ścieżka manifest wdrażania dodatku VSTO. Ścieżka może być lokalizacji na komputerze lokalnym, udziału sieciowego (UNC) lub serwera sieci Web (HTTP).<br /><br /> Jeśli używasz Instalatora systemu Windows do wdrożenia rozwiązania, należy dodać prefiks **file:///** do **manifestu** ścieżki. Należy także dołączyć ciąg  **&#124;vstolocal** (to znaczy znaku kreski pionowej **&#124;** następuje **vstolocal**) na końcu tej ścieżki. Pozwala to zagwarantować, że rozwiązanie jest ładowany z folderu instalacji, a nie pamięci podręcznej ClickOnce. Aby uzyskać więcej informacji, zobacz [wdrażania rozwiązania do pakietu Office przy użyciu Instalatora Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md). **Uwaga:** podczas kompilowania dodatku VSTO na komputerze dewelopera Visual Studio automatycznie dołącza  **&#124;vstolocal** ciąg do tego wpisu rejestru.|  
  
###  <a name="OutlookEntries"></a> Wpisy rejestru dotyczące regionów formularzy programu Outlook  
 Jeśli tworzysz regionu formularza niestandardowego w dodatku VSTO dla programu Outlook, wpisy rejestru dodatkowe są używane do rejestrowania regionu formularza z programu Outlook. Te wpisy są tworzone w kluczu rejestru różnych dla każdej klasy wiadomości, który obsługuje regionu formularza. Te klucze rejestru znajdują się w następującej lokalizacji, gdzie *głównego* jest **HKEY_CURRENT_USER** lub **HKEY_LOCAL_MACHINE**.  
  
 *Główny*\Software\Microsoft\Office\Outlook\FormRegions\\*message — klasa*  
  
 Podobnie jak inne wpisy rejestru współużytkowane przez wszystkie dodatki VSTO Visual Studio tworzy formularz regionu, wpisów rejestru na komputerze dewelopera podczas kompilowania projektu. Jeśli używasz ClickOnce do wdrażania dodatku VSTO z wpisy rejestru są tworzone automatycznie na komputerze użytkownika końcowego. Wdrażanie dodatek VSTO za pomocą Instalatora Windows, należy skonfigurować projekt InstallShield Limited Edition można utworzyć wpisów rejestru na komputerze użytkownika końcowego.  
  
 Aby uzyskać więcej informacji na temat wpisów rejestru regionu formularza, zobacz [Określ lokalizację regionów formularzy w niestandardowym formularzu](http://msdn.microsoft.com/library/office/ff868998.aspx). Aby uzyskać więcej informacji o regionach formularzy programu Outlook, zobacz [regionów formularzy Outlook utwórz](../vsto/creating-outlook-form-regions.md).  
  
##  <a name="LoadBehavior"></a> Wartości LoadBehavior  
 **LoadBehavior** wpis w *głównego*\Software\Microsoft\Office\\*Nazwa aplikacji*\Addins\\*dodatku Identyfikator* klucz zawiera bitowe połączenie wartości, które określają zachowanie czas wykonywania dodatku VSTO. Najniższy bit kolejności (wartości 0 i 1) wskazuje, czy dodatku VSTO jest obecnie zwalnianie lub załadować. Inne usługi bits sygnalizującego, kiedy aplikacja próbuje załadować dodatku VSTO.  
  
 Zazwyczaj **LoadBehavior** wpis ma być ustawiony na 0, 3 lub 16 (w dziesiętna) Jeśli dodatku VSTO jest zainstalowane na komputerach użytkowników końcowych. Domyślnie program Visual Studio ustawia **LoadBehavior** wpisu użytkownika dodatku VSTO z 3 podczas tworzenia lub opublikować go.  
  
 W poniższej tabeli wymieniono wszystkie możliwe wartości **LoadBehavior** wpisu. Opisy w tej tabeli odnoszą się do ładowania dodatku VSTO ręcznie lub programowo. Aby załadować dodatku VSTO ręcznie, zaznacz pole wyboru obok dodatku VSTO w **dodatki COM** okno dialogowe w aplikacji. Aby załadować dodatku VSTO programowo, ustaw <xref:Microsoft.Office.Core.COMAddIn.Connect%2A> właściwość <xref:Microsoft.Office.Core.COMAddIn> obiekt, który reprezentuje dodatku VSTO do **true**.  
  
|Wartość (dziesiętna)|Stan dodatku narzędzi VSTO|VSTO dodatku zachowania obciążenia|Opis|  
|--------------------------|-------------------------|--------------------------------|-----------------|  
|0|Zwolniono|Nie są ładowane automatycznie|Aplikacja nigdy nie próbuje załadować dodatku VSTO automatycznie. Użytkownik może próbować ręcznie załadować dodatku VSTO lub dodatku VSTO mogą być ładowane programowo.<br /><br /> Jeśli dodatku VSTO zostanie pomyślnie załadowana, **LoadBehavior** wartość pozostaje 0, ale stan dodatku VSTO w **dodatki COM** okno dialogowe jest aktualizowana w celu wskazują, że VSTO dodatek jest załadowany.|  
|1|załadowano|Nie są ładowane automatycznie|Aplikacja nigdy nie próbuje załadować dodatku VSTO automatycznie. Użytkownik może próbować ręcznie załadować dodatku VSTO lub dodatku VSTO mogą być ładowane programowo.<br /><br /> Mimo że **dodatki COM** okno dialogowe wskazuje, że dodatek VSTO jest załadowany po uruchomieniu aplikacji dodatku VSTO nie został załadowany do czasu załadowania ręcznie lub programowo.<br /><br /> Jeśli pomyślnie ładowania aplikacji dodatku VSTO **LoadBehavior** wartość zmienia się na 0 i pozostanie w lokalizacji 0, po zamknięciu aplikacji.|  
|2|Zwolniono|Ładowanie przy uruchamianiu|Aplikacja nie będzie próbował załadować dodatku VSTO automatycznie. Użytkownik może próbować ręcznie załadować dodatku VSTO lub dodatku VSTO mogą być ładowane programowo.<br /><br /> Jeśli pomyślnie ładowania aplikacji dodatku VSTO **LoadBehavior** wartość zmienia się na 3 i pozostanie w 3 po zamknięciu aplikacji.|  
|3|załadowano|Ładowanie przy uruchamianiu|Aplikacja próbuje załadować dodatku VSTO podczas uruchamiania aplikacji. Jest to wartość domyślna, gdy kompilacji lub publikowanie dodatków VSTO w programie Visual Studio.<br /><br /> Jeśli pomyślnie ładowania aplikacji dodatku VSTO **LoadBehavior** wartość pozostaje 3. Jeśli wystąpi błąd podczas ładowania dodatku VSTO **LoadBehavior** wartość zmieni się na 2 i pozostanie w 2 po zamknięciu aplikacji.|  
|8|Zwolniono|Ładuj na żądanie|Aplikacja nie będzie próbował załadować dodatku VSTO automatycznie. Użytkownik może próbować ręcznie załadować dodatku VSTO lub dodatku VSTO mogą być ładowane programowo.<br /><br /> Jeśli pomyślnie ładowania aplikacji dodatku VSTO **LoadBehavior** zmiany wartości na 9.|  
|9|załadowano|Ładuj na żądanie|Dodatku VSTO będą ładowane tylko wtedy, gdy aplikacja wymaga, takie jak po kliknięciu elementu interfejsu użytkownika używającą funkcji w dodatku VSTO (na przykład przycisk niestandardowe na Wstążce).<br /><br /> Jeśli pomyślnie ładowania aplikacji dodatku VSTO **LoadBehavior** wartość pozostaje 9, ale stan dodatku VSTO w **dodatki COM** okno dialogowe jest aktualizowana do wskazywania dodatku narzędzi VSTO obecnie załadowane. Jeśli wystąpi błąd podczas ładowania dodatku VSTO **LoadBehavior** zmiany wartości na 8.|  
|16|załadowano|Ładowanie po raz pierwszy, a następnie załaduj na żądanie|Ta wartość ma dodatek VSTO mają zostać załadowane na żądanie. Dodatku VSTO ładowania aplikacji, gdy użytkownik uruchomi aplikację po raz pierwszy. Następnym razem, gdy użytkownik uruchomi aplikację, wszelkie elementy interfejsu użytkownika, zdefiniowane przez dodatku VSTO ładowania aplikacji, ale dodatku VSTO nie został załadowany, dopóki nie zostanie kliknięty element interfejsu użytkownika, który jest skojarzony z dodatku VSTO.<br /><br /> Po pomyślnym ładowania aplikacji dodatku VSTO po raz pierwszy, **LoadBehavior** wartość pozostaje 16, gdy jest ładowany dodatku VSTO. Po zamknięciu aplikacji **LoadBehavior** zmiany wartości na 9.|  
  
## <a name="see-also"></a>Zobacz także  
 [Architektura rozwiązań pakietu Office w Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Architektura dodatków narzędzi VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Tworzenie rozwiązań pakietu Office](../vsto/building-office-solutions.md)   
 [Wdrażanie rozwiązania do pakietu Office](../vsto/deploying-an-office-solution.md)  
  
  