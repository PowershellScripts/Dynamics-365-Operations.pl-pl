---
title: Pakiet zawartości usługi Power BI Wydajność magazynu
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Wydajność magazynu. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: Mirzaab
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: WHSWarehousePerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.region: Global
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4594c6c09abdac72a03ac1338701d2291b234106
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687408"
---
# <a name="warehouse-performance-power-bi-content"></a>Pakiet zawartości usługi Power BI Wydajność magazynu

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Wydajność magazynu**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości **Wydajność magazynu** dla usługi Power BI został utworzony, aby kierownicy magazynów i kierownicy ds. operacyjnych mogli monitorować ważne wskaźniki dotyczące towarów przychodzących, wychodzących i zapasów. Wykorzystuje dane modułu Zarządzanie magazynem, informacje o produktach i inne dane transakcyjne z firmowego systemu oraz przedstawia zarówno zagregowany widok parametrów działania magazynu, jak i podział według dostawców, grup produktów, produktów, oddziałów i magazynów.

Pakiet zawartości usługi Power BI **Wydajność magazynu** umożliwia kierownikom magazynów pomiar trzech następujących obszarów:

- **Wydajność operacji przychodzących** — Mierzenie, na ile dobrze dostawca spełnia wymagania odbiorcy (innymi słowy mierzenie wydajności dostaw), oraz mierzenie wydajności odkładania, dzięki czemu można identyfikować problemy z udziałem pracowników lub towarów w wybranym okresie. Ważna jest wiedza, czy dostawcy dostarczają na czas, przed terminem czy z opóźnieniem, co pozwala określić, jak parametry działania dostawcy wpływają na ogólną wydajność odkładania. Dostawca, który dostarcza poza uzgodnionym zakresem dat, może wywierać dodatkowy nacisk na magazyn z powodu nieoczekiwanej pracy i w ten sposób wydłużać średni czas odłożenia.
- **Wydajność wysyłki** — Mierzenie, czy magazyn wysyła w całości i w terminie do odbiorców (innymi słowy mierzenie wydajności wysyłek i dostaw towarów wychodzących), dzięki czemu można identyfikować wszelkie problemy z produktami, oddziałami, magazynami lub dedykowanymi odbiorcami. Jeśli się okaże, że wysyłasz z opóźnieniem do określonych regionów lub miejscowości, należy zwrócić większą uwagę na zarządzanie transportem lub klientami.
- **Dokładność zapasów w lokalizacji** — Dokładność zapasów jest ważnym wewnętrznym parametrem analizy biznesowej (BI) w magazynie. Jest bardzo ważne, aby określić, na ile dokładnie liczysz (inwentaryzujesz) towary. Jednak ważne jest także określenie, na ile dokładnie przechowujesz towary w prawidłowych lokalizacjach, oraz wyróżnianie danych o rozbieżnościach, dzięki czemu można znaleźć lepsze miejsca dla towarów lub inicjować całkowitą inwentaryzację określonych towarów. (Obecnie nowa funkcja inwentaryzacji opartej na towarach jest dostępna jako poprawka). Jeśli używasz tego pakietu zawartości usługi Power BI do weryfikowania poprawności danych o dostępnych zapasach w poszczególnych lokalizacjach, możesz także identyfikować kradzieże w sklepach swojej sieci. Można też określić, czy w którejkolwiek lokalizacji istnieją ilości dostępnych zapasów, które różnią się od danych w systemie planowania zasobów przedsiębiorstwa (ERP). Być może te lokalizacje są zbyt duże albo nie da się w nich przeprowadzić inwentaryzacji. Ewentualnie niektóre fizyczne umiejscowienia mogą być błędne, wskutek czego trudno jest synchronizować określone rodzaje towarów z danymi o dostępności.

## <a name="accessing-the-power-bi-content-pack"></a>Przechodzenie do pakietu zawartości usługi Power BI
Pakiet zawartości usługi Power BI **Wydajność magazynu** jest wyświetlany na stronie **Wydajność magazynu** (**Zarządzanie magazynem** \> **Zapytania i raporty** \> **Analiza wydajności magazynu** \> **Wydajność magazynu**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
Pakiet zawartości **Wydajność magazynu** dla usługi Power BI. Raport zawiera zestaw wskaźników, które są wizualizowane jako wykresy, kafelki i tabele. Poniższa tabela zawiera omówienie wizualizacji dostępnych w pakiecie zawartości usługi Power BI **Wydajność magazynu**.

| Strona raportu                 | Wykresy                                   | opis |
|-----------------------------|------------------------------------------|-------------|
| Wydajność operacji przychodzących         | Suma odłożeń                          | Liczba wierszy pracy odłożenia, które są przetwarzane w danym przedziale czasu. |
| Wydajność operacji przychodzących         | Średni czas odłożenia                    | Średni czas trwania (w godzinach) dla wszystkich przetworzonych wierszy odłożenia w zamówieniach zakupu — od zarejestrowania towarów do przetworzenia ostatniego odłożenia. |
| Wydajność operacji przychodzących         | Odbiór wcześniejszy                           | Liczba wierszy zamówień zakupu, z których towary otrzymano wcześniej. |
| Wydajność operacji przychodzących         | Odbiór terminowy                         | Liczba wierszy zamówień zakupu, z których towary otrzymano punktualnie. |
| Wydajność operacji przychodzących         | Odbiór późniejszy                            | Liczba wierszy zamówień zakupu, z których towary otrzymano z opóźnieniem. |
| Wydajność operacji przychodzących         | Punktualnie wg dostawców                        | Widok procentu wierszy zamówień zakupu, z których towary otrzymano od dostawców lub grup dostawców wcześniej, na czas lub z opóźnieniem. |
| Wydajność operacji przychodzących         | Średni czas odłożenia dok-zapasy (godziny) | Średni czas odłożenia (w godzinach) między przybyciem do doku a umieszczeniem w zapasach w wybranym okresie. |
| Wydajność operacji przychodzących         | Średnie odłożenie wg pracowników               | Średni czas odłożenia (w godzinach), jaki pracownik poświęcał na przetwarzanie odłożeń wierszy zamówień zakupu. |
| Wydajność operacji przychodzących         | Średnie odłożenie wg dostawców (godziny)          | Średni czas odłożenia (w godzinach) z podziałem na dostawców lub grupy dostawców. |
| Wydajność operacji przychodzących         | Średnie odłożenie wg produktów (godziny)         | Średni czas odłożenia (w godzinach) z podziałem na dostawców lub grupy dostawców. |
| Dokładność zapasów w lokalizacji | Suma                              | Liczba wierszy pracy inwentaryzacji, które są przetwarzane w wybranym okresie. |
| Dokładność zapasów w lokalizacji | Wskaźnik rozbieżności                         | Łączny wskaźnik rozbieżności jako procent wszystkich wierszy inwentaryzowanych w wybranym okresie. |
| Dokładność zapasów w lokalizacji | Inwentaryzacja bez rozbieżności                | Wśród łącznej liczby przetworzonych wierszy pracy inwentaryzacji jest to liczba wierszy, które zostały przetworzone bez jakichkolwiek rozbieżności. |
| Dokładność zapasów w lokalizacji | Towary zliczone w czasie                  | Procent towarów, które w wybranym przedziale czasu zostały zinwentaryzowane z rozbieżnościami i bez rozbieżności. |
| Dokładność zapasów w lokalizacji | Rozbieżność ilości towarów większa niż % | Widok tabelaryczny wierszy inwentaryzacji z rozbieżnościami przekraczającymi określoną wartość procentową. Tabela zawiera informacje o lokalizacjach, towarach, średniej rozbieżności, łącznej liczbie policzonych wierszy pracy inwentaryzacji, łącznej liczbie wierszy inwentaryzacji mających rozbieżności w lokalizacji, średniej zliczanej ilości, oczekiwanej łącznej liczonej ilości i rzeczywistej policzonej ilości towarów. |
| Dokładność zapasów w lokalizacji | Liczba towarów wg pracowników                     | Wydajność, z jaką pracownicy zliczają towary. Wydajność jest wyrażona jako procent wierszy pracy inwentaryzacji, w których są i nie ma rozbieżności. |
| Dokładność zapasów w lokalizacji | Liczba towarów wg magazynów/oddziałów           | Wydajność inwentaryzacji wyrażona liczbą przetworzonych wierszy pracy zliczania z podziałem na oddziały lub magazyny, w których wystąpiły i nie wystąpiły rozbieżności. |
| Dokładność zapasów w lokalizacji | Wskaźnik rozbieżności wg produktów              | Wskaźnik rozbieżności w inwentaryzacji. Wskaźnik jest wyrażony jako procent przetworzonych wierszy pracy inwentaryzacji z podziałem na towary lub grupy towarów. |
| Wydajność wysyłki        | Wiersze wysłane                            | Łączna liczba wierszy wysyłki, z których towary zostały wysłane w wybranym okresie. |
| Wydajność wysyłki        | Wcześnie                                    | Procent wierszy wysyłki, z których towary zostały wysłane wcześniej. |
| Wydajność wysyłki        | Na czas                                  | Procent wierszy wysyłki, z których towary zostały wysłane punktualnie. |
| Wydajność wysyłki        | Późno                                     | Procent wierszy wysyłki, z których towary zostały wysłane z opóźnieniem. |
| Wydajność wysyłki        | Wysyłki w czasie                      | Procent wierszy wysyłki, z których towary zostały wysłane na czas, przed terminem lub z opóźnieniem w wybranym okresie. Linia trendu przedstawia tendencję dla wierszy, które są wysyłane na czas. |
| Wydajność wysyłki        | Wysłane z opóźnieniem wg miejscowości                     | Mapa przedstawiająca miejscowości i regiony, do których wysyłki następują z opóźnieniem. |
| Wydajność wysyłki        | Wysłane wg produktów                       | Procent towarów wysłanych wcześniej, punktualnie lub z opóźnieniem z podziałem na towary lub grupy towarów. |
| Wydajność wysyłki        | Wysłane wg odbiorców                      | Procent towarów wysłanych wcześniej, punktualnie lub z opóźnieniem z podziałem na odbiorców lub grupy odbiorców. |
| Wydajność wysyłki        | Wysłane wg oddziałów/magazynów              | Procent towarów wysłanych wcześniej, punktualnie lub z opóźnieniem z podziałem na oddziały lub magazyny. |

## <a name="understanding-the-data-model-and-calculations"></a>Opis modelu danych i obliczeń
Następujące dane są używane do wypełniania stron raportów w pakiecie zawartości **Wydajność magazynu** dla usługi Power BI. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md).

Następujące najważniejsze zagregowane miary są używane jako podstawa w pakiecie zawartości:

| Strona raportu                 | Wykresy                                   | Tabele                                | Opisy obliczeń |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Wydajność operacji przychodzących         | Suma odłożeń                          | WHSWorkLine                           | Liczba wierszy pracy, gdzie typem pracy jest **odkładanie**. |
| Wydajność operacji przychodzących         | Średni czas odłożenia                    | WHSWorkLine                           | Suma maksymalnych czasów wierszy pracy podzielona przez liczbę maksymalnych czasów wierszy pracy, gdzie maksymalny czas wiersza pracy jest maksymalną różnicą między datami utworzenia i zamknięcia pracy. |
| Wydajność operacji przychodzących         | Odbiór wcześniejszy                           | WHSWorkLine                           | Liczba wierszy pracy, gdzie data utworzenia pracy jest wcześniejsza niż używana data dostawy. Jeżeli potwierdzona data dostawy nie została ustawiona, jest używana domyślna datą dostawy. |
| Wydajność operacji przychodzących         | Odbiór terminowy                         | WHSWorkLine                           | Liczba wierszy pracy, gdzie data utworzenia pracy jest taka sama, jak używana data dostawy. Jeżeli potwierdzona data dostawy nie została ustawiona, jest używana domyślna datą dostawy. |
| Wydajność operacji przychodzących         | Odbiór późniejszy                            | WHSWorkLine                           | Liczba wierszy pracy, gdzie data utworzenia pracy jest późniejsza niż używana data dostawy. Jeżeli potwierdzona data dostawy nie została ustawiona, jest używana domyślna datą dostawy. |
| Wydajność operacji przychodzących         | Punktualnie wg dostawców                        | WHSWorkLine                           | Odbiór wcześniejszy, Odbiór terminowy i Odbiór późniejszy (zobacz opisy we wcześniejszej części tej tabeli). |
| Wydajność operacji przychodzących         | Średni czas odłożenia dok-zapasy (godziny)   | WHSWorkLine                           | Średni czas odłożenia (zobacz opis we wcześniejszej części tej tabeli). |
| Wydajność operacji przychodzących         | Średnie odłożenie wg pracowników               | WHSWorkLine                           | Średni czas odłożenia (zobacz opis we wcześniejszej części tej tabeli). |
| Wydajność operacji przychodzących         | Średnie odłożenie wg dostawców (godziny)          | WHSWorkLine                           | Średni czas odłożenia (zobacz opis we wcześniejszej części tej tabeli). |
| Wydajność operacji przychodzących         | Średnie odłożenie wg produktów (godziny)         | WHSWorkLine                           | Średni czas odłożenia (zobacz opis we wcześniejszej części tej tabeli). |
| Dokładność zapasów w lokalizacji | Suma                              | WHSWorkLineCycleCount                 | Inwentaryzacje ciągłe, gdzie bezwzględna ilość rozbieżności jest równa lub większa niż 0 (zero). |
| Dokładność zapasów w lokalizacji | Wskaźnik rozbieżności                         | WHSWorkLineCycleCount                 | Inwentaryzacje ciągłe mające rozbieżności podzielone przez łączną liczbę. Uznaje się, że inwentaryzacja ciągła ma rozbieżności, jeśli ilość bezwzględna rozbieżności jest większa niż 0 (zero). |
| Dokładność zapasów w lokalizacji | Inwentaryzacja bez rozbieżności                | WHSWorkLineCycleCount                 | Inwentaryzacje ciągłe, gdzie bezwzględna ilość rozbieżności jest większa niż 0 (zero). |
| Dokładność zapasów w lokalizacji | Inwentaryzacja z rozbieżnościami                   | WHSWorkLineCycleCount                 | Inwentaryzacje ciągłe, gdzie bezwzględna ilość rozbieżności jest równa 0 (zero). |
| Dokładność zapasów w lokalizacji | Towary zliczone w czasie                  | WHSWorkLineCycleCount                 | Inwentaryzacja bez rozbieżności i Inwentaryzacja z rozbieżnościami (zobacz opisy we wcześniejszej części tej tabeli). |
| Dokładność zapasów w lokalizacji | Rozbieżność ilości towarów większa niż % | WHSWorkLineCycleCount                 | Średnia rozbieżność to bezwzględna ilość rozbieżności podzielona przez ilość przewidywaną, gdzie bezwzględna ilość rozbieżności jest większa niż 0 (zero). Średnia ilość rozbieżności to średnia bezwzględna ilość rozbieżności, gdzie bezwzględna ilość rozbieżności jest większa niż 0 (zero). Inwentaryzacja z rozbieżnościami, Suma, Oczekiwana ilość i Zliczona ilość, gdzie cała ilość jest pogrupowana według towarów i lokalizacji (zobacz opisy we wcześniejszej części tej tabeli). |
| Dokładność zapasów w lokalizacji | Liczba towarów wg pracowników                     | WHSWorkLineCycleCount                 | Inwentaryzacja bez rozbieżności i Inwentaryzacja z rozbieżnościami (zobacz opisy we wcześniejszej części tej tabeli). |
| Dokładność zapasów w lokalizacji | Liczba towarów wg magazynów/oddziałów           | WHSWorkLineCycleCount                 | Inwentaryzacja bez rozbieżności i Inwentaryzacja z rozbieżnościami (zobacz opisy we wcześniejszej części tej tabeli). |
| Dokładność zapasów w lokalizacji | Wskaźnik rozbieżności wg produktów              | WHSWorkLineCycleCount                 | Wskaźnik rozbieżności (zobacz opis we wcześniejszej części tej tabeli). |
| Wydajność wysyłki        | Wiersze wysłane                            | SalesLine               | Liczba wierszy sprzedaży, z których towary zostały wysłane. |
| Wydajność wysyłki        | Wcześnie                                    | CustPackingSlipOnTimeStatus           | Wiersze sprzedaży, w których stan daty wysyłki ma wartość **1 (wcześnie)**. „Wcześnie” oznacza, że data wysyłki na dokumencie dostawy jest wcześniejsza, niż potwierdzona data wysyłki w wierszu sprzedaży. Jeśli nie ustawiono potwierdzonej daty wysyłki, jest używana żądana data wysyłki. |
| Wydajność wysyłki        | Na czas                                  | CustPackingSlipOnTimeStatus           | Wiersze sprzedaży, w których stan daty wysyłki ma wartość **2 (Na czas)**. „Na czas” oznacza, że data wysyłki na dokumencie dostawy jest taka sama, jak potwierdzona data wysyłki w wierszu sprzedaży. Jeśli nie ustawiono potwierdzonej daty wysyłki, jest używana żądana data wysyłki. |
| Wydajność wysyłki        | Późno                                     | CustPackingSlipOnTimeStatus           | Wiersze sprzedaży, w których stan daty wysyłki ma wartość **3 (Późno)**. „Późno” oznacza, że data wysyłki na dokumencie dostawy jest późniejsza, niż potwierdzona data wysyłki w wierszu sprzedaży. Jeśli nie ustawiono potwierdzonej daty wysyłki, jest używana żądana data wysyłki. |
| Wydajność wysyłki        | Wysyłki w czasie                      | SalesLine CustPackingSlipOnTimeStatus | Zamówienia wysłane w całości, gdzie została wysłana cała ilość z wiersza sprzedaży, plus towary o statusie wysyłki Wcześnie, Na czas i Późno (zobacz opisy we wcześniejszej części tej tabeli). |
| Wydajność wysyłki        | Wysłane z opóźnieniem wg miejscowości                     | CustPackingSlipOnTimeStatus           | Późno (zobacz opisy we wcześniejszej części tej tabeli). |
| Wydajność wysyłki        | Wysłane wg produktów                       | CustPackingSlipOnTimeStatus           | Wcześnie, Na czas i Późno (zobacz opisy we wcześniejszej części tej tabeli). |
| Wydajność wysyłki        | Wysłane wg odbiorców                      | CustPackingSlipOnTimeStatus           | Wcześnie, Na czas i Późno (zobacz opisy we wcześniejszej części tej tabeli). |
| Wydajność wysyłki        | Wysłane wg oddziałów/magazynów              | CustPackingSlipOnTimeStatus           | Wcześnie, Na czas i Późno (zobacz opisy we wcześniejszej części tej tabeli). |
