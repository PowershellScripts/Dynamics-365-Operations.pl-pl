---
title: Konfigurowanie w module Raportowanie elektroniczne (ER) ściągania danych do usługi Power BI
description: W tym temacie wyjaśniono sposób wykorzystania konfiguracji raportowania elektronicznego (ER) do organizowania przesyłania danych do usług Power BI.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 34d4ad9106b2751c77db4fd03d83932e587a5332
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680127"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Konfigurowanie w module Raportowanie elektroniczne (ER) ściągania danych do usługi Power BI

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób wykorzystania konfiguracji raportowania elektronicznego (ER) do organizowania przesyłania danych do usług Power BI. Na potrzeby przykładu użyto transakcji Intrastat jako danych biznesowych, które muszą zostać przesłane. Funkcja wizualizacja mapy w programie Power BI wykorzystuje te dane transakcji Intrastat do przedstawienia widoku umożliwiającego analizę działań importowych/eksportowych firmy w raporcie programu Power BI.

## <a name="overview"></a>Przegląd

Microsoft Power BI to zbiór usług oprogramowania, aplikacji i łączników, które wspólnie wydobywają z zewnętrznych źródeł danych spójne, realistyczne wizualnie i interaktywne wnioski. Raportowanie elektroniczne (ER) pozwala użytkownikom łatwo konfigurować źródła danych i zaplanować transfer danych z aplikacji do Power BI. Dane są przesyłane jako pliki w formacie arkusza OpenXML (plik skoroszytu programu Microsoft Excel). Przesłane pliki są przechowywane na serwerze programu Microsoft SharePoint, który został skonfigurowany do tego celu. Przechowywane pliki są używane w programie Power BI do tworzenia raportów zawierających wizualizacje (tabele, wykresy, mapy i tak dalej). Raporty programu Power BI są udostępniane użytkownikom programu Power BI i można je otwierać w pulpitach nawigacyjnych programu Power BI i na stronach aplikacji. W tym temacie wyjaśniono następujące zadania:

- Konfigurowanie rozwiązania Dynamics 365 Finance Microsoft.
- Przygotowywanie konfiguracji formatu ER do pobierania danych z aplikacji Finance.
- Skonfigurowanie środowiska ER do przesyłania danych do programu Power BI.
- Używanie przesłanych danych do tworzenia raportu programu Power BI.
- Udostępnianie raportów programu Power BI w Finance.

## <a name="prerequisites"></a>Wymagania wstępne
Aby wykonać przykład opisany w tym temacie, musisz mieć następujące uprawnienia dostępu:

- Dostęp do jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Konsultant funkcjonalny raportowania elektronicznego
    - Administrator systemu

- Dostęp do wystąpienia serwera SharePoint, który jest skonfigurowany do współpracy z aplikacją.
- Dostęp do struktury Power BI

## <a name="configure-document-management-parameters"></a>Konfigurowanie parametrów zarządzania dokumentami
1. Na stronie **Parametry zarządzania dokumentami** skonfiguruj dostęp do serwera programu SharePoint, który będzie używany w firmie, do której się logujesz (w tym przykładzie jest to firma DEMF).
2. Przetestuj połączenie z serwerem programu SharePoint, aby się upewnić, że przyznano Ci dostęp.

    [![Strona Parametry zarządzania dokumentami](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. Otwórz skonfigurowaną witrynę programu SharePoint. Utwórz nowy folder, gdzie moduł ER będzie przechowywał pliki programu Excel zawierające dane biznesowe, których raporty programu Power BI wymagają jako źródła zestawów danych Power BI.
4. Na stronie **Typy dokumentów** utwórz nowy typ dokumentu, który będzie używany w celu uzyskiwania dostępu do nowo utworzonego folderu programu SharePoint. Wpisz **Plik** w polu **Grupa** i **SharePoint** w polu **Lokalizacja**, a następnie wprowadź adres folderu programu SharePoint.

    [![Strona Typy dokumentów](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER
1. W obszarze roboczym **Raportowanie elektroniczne** kliknij łącze **Parametry raportowania elektronicznego**.
2. Na karcie **Załączniki** wybierz typ dokumentu **Plik** we wszystkich polach.
3. W obszarze roboczym **Raportowanie elektroniczne** uaktywnij wymaganego dostawcę przez kliknięcie przycisku **Ustaw jako aktywny**. Aby uzyskać więcej informacji, odtwórz przewodnik po zadaniu **ER Wybór dostawcy usług**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Używanie modelu danych raportowania elektronicznego jako źródła danych
Model danych ER musi być źródłem danych biznesowych, które będą używane w raportach programu Power BI. Ten model danych jest wczytywany z repozytorium konfiguracji raportowania elektronicznego. Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](download-electronic-reporting-configuration-lcs.md) lub odtwórz przewodnik po zadaniu **ER Importowanie konfiguracji z usługi Lifecycle Services**. Wybierz **Intrastat** jako modelu danych, który zostanie wczytany z wybranego repozytorium konfiguracji modułu ER. (W tym przykładzie jest używana wersja 1 modelu). Następnie można uzyskać dostęp do konfiguracji **Intrastat** modelu ER na stronie **Konfiguracje**.

[![Strona Konfiguracje](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Projektowanie konfiguracji formatu raportowania elektronicznego
Należy utworzyć nową konfigurację formatu modułu ER używającą modelu danych **Intrastat** jako źródła danych biznesowych. Ta konfiguracja formatu musi generować dane wyjściowe w postaci dokumentów elektronicznych w formacie OpenXML (pliku programu Excel). Aby uzyskać więcej informacji, odtwórz przewodnik po zadaniu **ER Tworzenie konfiguracji dla raportów w formacie OPENXML**. Nazwij nową konfigurację **Działania importu/eksportu**, jak pokazano na poniższej ilustracji. Użyj pliku programu Excel [Dane ER — szczegóły importu i eksportu](https://go.microsoft.com/fwlink/?linkid=845208) jako szablonu podczas projektowania formatu ER. (Aby uzyskać więcej informacji o importowaniu szablonu formatu, odtwórz przewodnik po zadaniu).

[![Konfiguracja Działania importu/eksportu](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

Aby zmodyfikować konfigurację formatu **Działania importu/eksportu**, należy wykonać następujące kroki.

1. Kliknij przycisk **Konstruktor**.
2. Na karcie **Format** nazwij plikowy element tego formatu jako **Plik wyjściowy programu Excel**.

    [![Element Plik wyjściowy programu Excel](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. Na karcie **Mapowanie** określ nazwę pliku programu Excel, który będzie generowany przy każdym uruchomieniu tego formatu. Skonfiguruj pokrewne wyrażenie, aby zwracało wartość **Szczegóły importu i eksportu** (rozszerzenie nazwy pliku .xlsx zostanie dodane automatycznie).

    [![Projektant formatów](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. Dodaj nowy element źródła danych dla tego formatu. (Ten element stałotekstowy będzie wymagany przy dalszym wiązaniu danych).

    1. Nazwij źródło danych **direction\_enum**.
    2. Jako typ źródła danych wybierz **Wyliczenie modeli danych**.
    3. Utwórz odwołanie do elementu stałotekstowego modelu danych **Kierunek**.

    [![direction_enum](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. Wykonaj powiązanie elementów modelu danych **Intrastat** z elementami zaprojektowanego formatu, jak pokazano na poniższej ilustracji.

    [![Wykonywanie powiązania](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

Po uruchomieniu format modułu ER wygeneruje dane wyjściowe w formacie programu Excel. Wyśle szczegóły transakcji Intrastat do danych wyjściowych i oddzieli je jako transakcje, które opisują działania importu lub eksportu. Kliknij przycisk **Uruchom**, aby przetestować nowy format ER listy transakcji Intrastat na stronie **Intrastat** (**Podatek** &gt; **Deklaracje** &gt; **Handel zagraniczny** &gt; **Intrastat**).

[![Strona Intrastat](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

Zostaną wygenerowane następujące dane wyjściowe. Plik nosi nazwę **Szczegóły importu i eksportu.xlsx**, jak określono w ustawieniach formatu.

[![Szczegóły importu i eksportu.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Konfigurowanie miejsca docelowego raportowania elektronicznego
Należy skonfigurować środowisko modułu ER do wysyłania danych wyjściowych nowej konfiguracji formatu ER w specjalny sposób.

- Dane wyjściowe należy wysłać do folderu wybranego serwera programu SharePoint.
- Każde wykonanie konfiguracji formatu musi tworzyć nową wersję tego samego pliku programu Excel.

Na stronie **Raportowanie elektroniczne** (**Administrowanie organizacją** &gt; **Raportowanie elektroniczne**) kliknij element **Aplikacja docelowa raportowania elektronicznego** i dodaj nowe miejsce docelowe. W polu **Odwołanie** zaznacz utworzoną wcześniej konfigurację formatu **Działania importu/eksportu**. Wykonaj następujące kroki, aby dodać nowy rekord plikowego miejsca docelowego dla odwołania.

1. W polu **Nazwa** wprowadź tytuł plikowego miejsca docelowego.
2. W polu **Nazwa pliku** wybierz nazwę **Plik wyjściowy programu Excel** dla składnika formatu pliku programu Excel.

Kliknij przycisk **Ustawienia** dla nowego rekordu miejsca docelowego. Następnie w oknie dialogowym **Ustawienia aplikacji docelowej** wykonaj następujące kroki.

1. Na karcie **Power BI** w opcji **Włączone** ustaw wartość **Tak**.
2. W polu **SharePoint** zaznacz utworzony wcześniej typu dokumentu **Współdzielony**.

## <a name="schedule-execution-of-the-configured-er-format"></a>Planowanie wykonywania skonfigurowanego formatu raportowania elektronicznego
1. Na stronie **Konfiguracje** (**Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Konfiguracje**) w drzewie konfiguracji wybierz utworzoną wcześniej konfigurację **Działania importu/eksportu**.
2. Zmień stan wersji 1.1 z **Robocza** na **Ukończono**, co spowoduje udostępnienie tego formatu do użytku.

    [![Strona Konfiguracje](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. Wybierz ukończoną wersję konfiguracji **Działania importu/eksportu**, a następnie kliknij przycisk **Uruchom**. Należy zwrócić uwagę, ze skonfigurowane miejsce docelowe będzie stosowane do danych wyjściowych wygenerowanych w formacie programu Excel.
4. W opcji **Przetwarzanie wsadowe** ustaw wartość **Tak**, aby generować ten raport w trybie nienadzorowanym.
5. Kliknij opcję **Cykl**, aby zaplanować wymagane cykliczne wykonywanie tego przetwarzania wsadowego. Cykl określa, jak często zaktualizowane dane będą przesyłane do programu Power BI.

    [![Okno dialogowe Parametry raportu elektronicznego](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. Po skonfigurowaniu zadania wykonywania raportu ER można je znaleźć na stronie **Zadania wsadowe** (**Administrowanie systemem &gt; Zapytania &gt; Zadania wsadowe**).

    [![Strona zadania wsadowe](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. Gdy to zadanie jest wykonywane po raz pierwszy, aplikacja docelowa tworzy nowy plik programu Excel o skonfigurowanej nazwie w wybranym folderze programu SharePoint. Podczas każdego kolejnego wykonywania zadania aplikacja docelowa tworzy nową wersję tego pliku programu Excel.

    [![Nowa wersja pliku programu Excel](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Tworzenie zestawu danych programu Power BI za pomocą danych wyjściowych formatu raportowania elektronicznego
1. Zaloguj się w programie Power BI i otwórz istniejącą grupę (obszar roboczy) programu Power BI lub utwórz nową grupę. Kliknij łącze **Dodaj** w obszarze **Pliki** w sekcji **Importuj lub połącz z danymi** lub kliknij znak plusa (**+**) obok opcji **Zestawy danych** w lewym okienku.

    [![Tworzenie zestawu danych](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. Zaznacz opcję **SharePoint — witryny zespołu**, a następnie wprowadź ścieżkę do używanego serwera programu SharePoint (w omawianym przykładzie jest to `https://ax7partner.litware.com`).
3. Przejdź do folderu **/Shared Documents/GER data/PowerBI** i wybierz utworzony plik programu Excel jako źródło danych dla nowego zestawu danych programu Power BI.

    [![Wybieranie pliku programu Excel](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. Kliknij kolejno przyciski **Połącz** i **Importuj**. Zostanie utworzony nowy zestaw danych oparty na wybranym pliku programu Excel. Zestaw danych może być również dodawany automatycznie do nowo tworzonego pulpitu nawigacyjnego.

    [![Zestaw danych w pulpicie nawigacyjnym](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. Skonfiguruj harmonogram odświeżania tego zestawu danych, aby wymusić okresowe aktualizacje. Okresowe aktualizacje umożliwiają wykorzystywanie nowych danych biznesowych pochodzących poprzez okresowe generowanie raportu modułu ER przy użyciu nowych wersji pliku programu Excel, które są tworzone na serwerze programu SharePoint.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Tworzenie raportu programu Power BI przy użyciu nowego zestawu danych
1. Kliknij utworzony zestaw danych programu Power BI o nazwie **Szczegóły importu i eksportu**.
2. Skonfiguruj wizualizację. Na przykład zaznacz wizualizację **Wypełniona mapa** i skonfiguruj ją w następujący sposób:

    - Przypisz pole **CountryOrigin** zestawu danych do pola **Lokalizacja** w wizualizacji mapy.
    - Przypisz pole **Kwota** zestawu danych do pola **Nasycenie kolorów** w wizualizacji mapy.
    - Dodaj pola **Działanie** i **Rok** zestawu danych do kolekcji pól **Filtry** w wizualizacji mapy.

3. Zapisz raport programu Power BI pod nazwą **Raport o szczegółach importu i eksportu**.

    [![Raport o szczegółach importu i eksportu](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    Należy zauważyć, że mapa przedstawia kraje/regiony, które są wymienione w pliku programu Excel (w tym przykładzie Austria i Szwajcaria). Te kraje/regiony są pokolorowane w celu pokazania proporcji kwot zafakturowanych dla każdego z nich.

4. Zaktualizuj listę transakcji Intrastat. Zostanie dodana transakcja eksportu pochodząca z Włoch.

    [![Lista transakcji Intrastat](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. Poczekaj na kolejne zaplanowane generowanie raportu ER i następną zaplanowaną aktualizację zestawu danych programu Power BI. Następnie przejrzyj raport programu Power BI (zaznacz opcję wyświetlania tylko transakcji importu). Zaktualizowana mapa pokazuje obecnie Włochy.

    [![Zaktualizowana mapa](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>Dostęp Power BI do raportu w Finance
Konfigurowanie integracji z modułem Power BI. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji Power BI dla przestrzeni roboczych](configure-power-bi-integration.md).

1. Na stronie obszaru roboczego **Raportowanie elektroniczne**, która obsługuje integrację z programem Power BI (**Administrowanie organizacją** &gt; **Obszary robocze** &gt; **Obszar roboczy Raportowanie elektroniczne**) kliknij kolejno przyciski **Opcje** &gt; **Otwórz wykaz raportów**.
2. Zaznacz utworzony raport programu Power BI zatytułowany **Szczegóły importu i eksportu**, a zostanie on wyświetlony jako element akcji na wybranej stronie.
3. Kliknij element akcji, a zostanie otwarta strona pokazująca raport zaprojektowany w programie Power BI.

    [![Raport o szczegółach importu i eksportu](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lokalizacje docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)

[Omówienie raportowania elektronicznego (RE)](general-electronic-reporting.md)
