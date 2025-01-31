---
title: Mobilny obszar roboczy Kontrola kosztów
description: Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Kontrola kosztów. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4fc35feb4f3a67ba9c8c70c2d2f8c07cb944b0f6
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4447021"
---
# <a name="cost-controlling-mobile-workspace"></a>Mobilny obszar roboczy Kontrola kosztów

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego **Kontrola kosztów**. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie.

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji mobilnej Finance and Operations.

## <a name="overview"></a>Omówienie
Mobilny obszar roboczy **Kontrola kosztów** zapewnia natychmiastowy podgląd wyników działania centrów kosztów poprzez porównanie kosztów rzeczywistych z kosztami budżetowymi. W widoku można przechodzić do stanów poszczególnych składników kosztów.

Na przykład pracownik otrzymuje zaproszenie na międzynarodową konferencję, ale organizacja musi pokryć wszystkie wydatki na podróż. Pracownik pyta przełożonego, czy może wziąć udział w konferencji. Przełożony otwiera mobilny obszar roboczy **Kontrola kosztów** na swoim telefonie komórkowym i sprawdza, czy ma budżet na pokrycie kosztów udziału pracownika w konferencji.

### <a name="data-security"></a>Bezpieczeństwo danych
Dane w komórkowym obszarze roboczym **Kontrola kosztów** są zabezpieczone poświadczeniami użytkownika. Menedżerowie centrów kosztów mają pozwolenie na wgląd tylko w dane swoich centrów kosztów. Zabezpieczenia na poziomie dostępu są administrowane w module **Rachunek kosztów**.

Księgowi kosztów definiują konfigurację mobilnego obszaru roboczego **Kontrola kosztów** w module **Rachunek kosztów**. Po opublikowaniu obszaru roboczego w aplikacji komórkowej jest on dostępny w tej aplikacji. Dzięki temu menedżerowie centrów kosztów w organizacji mogą wyświetlać dane w tym samym formacie.

### <a name="actions-views-and-links"></a>Akcje, widoki i łącza
Mobilny obszar roboczy **Kontrola kosztów** oferuje następujące czynności, widoki i łącza:

-   **Akcje:**

    -   Użyj **Wybierz konfigurację**, aby wybrać układ.
    -   Użyj **Wybierz obiekt kosztu**, aby wybrać centra kosztów, według których mają zostać wyfiltrowane dane.
    
        > [!NOTE]
        > Centra kosztów wyświetlane na liście zależą od dostępu udzielonego w module **Rachunek kosztów**.

-   **Widoki:** Zależnie od wybranych akcji oraz konfiguracji w module **Rachunek kosztów** można przeglądać poniższe informacje na kartach:

    -   Rzeczywisty a budżetowy (bieżący okres)
    -   Rzeczywisty a skorygowany budżetowy (bieżący okres)
    -   Wartości rzeczywiste a budżet (poprzedni okres)
    -   Wartości rzeczywiste a skorygowany budżet (poprzedni okres)
    -   Wartości rzeczywiste a budżet (od początku roku)
    -   Wartości rzeczywiste a skorygowany budżet (od początku roku)

    Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie i % odchylenia.

-   **Linki:**

    -   Szczegóły bieżącego okresu
    -   Szczegóły poprzedniego okresu
    -   Szczegóły okresu od początku roku

    Po wybraniu łącza jest wyświetlana karta dla każdego składnika kosztów. Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie budżetu, % odchylenia budżetu, skorygowany budżet, odchylenie skorygowanego budżetu i % odchylenia skorygowanego budżetu.
    
    [![Karta składnika kosztu ](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>Warunki wstępne w przypadku korzystania z Microsoft Dynamics 365 Finance
Jeśli w organizacji wdrożono rozwiązanie Finance, administrator systemu musi opublikować mobilny obszar roboczy **Kontrola kosztów**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>Warunki wstępne, jeśli jest używana jest wersja 1611 z aktualizacją platformy 3. lub nowszą
Jeśli w organizacji wdrożono rozwiązanie Finance w wersji 1611 z aktualizacją platformy 3. lub nowszą, administrator systemu musi wykonać następujące zadania wstępne.

<table>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zainstalowanie poprawki KB 4013633.</td>
<td>Administrator systemu</td>

<td>KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Kontrola kosztów</strong>. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Kontrola kosztów</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej
Pobieranie i instalowanie aplikacji mobilnej Finance and Operations:

-   [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej

1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Dynamics 365.
3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Wyświetlanie wyników działania centrum kosztów przy użyciu mobilnego obszaru roboczego Kontrola kosztów

1.  Na urządzeniu przenośnym wybierz obszar roboczy **Kontrola kosztów**.
2.  Wybierz opcję **Kontrola obiektów kosztów**.
3.  Wybierz opcję **Akcje**.
4.  Wybierz opcję **Wybierz konfigurację** i wybierz układ kontroli kosztów.
5.  Wybierz opcję **Gotowe**.
6.  Wybierz opcję **Akcje**.
7.  Wybierz opcję **Wybierz obiekt kosztu** i zaznacz centra kosztów, do których przyznano Ci uprawnienie dostępu.
8.  Wybierz opcję **Gotowe**.
9.  Wyświetl całościowe wyniki działania centrum kosztów.
10. Kliknij łącze **Szczegóły bieżącego okresu**.
11. Wyświetl wyniki działania poszczególnych składników kosztów.
12. Można także wyszukiwać konkretne składniki kosztów.

