---
title: Obsługa podwójnej waluty dla podatku
description: W tym temacie opisano sposób rozszerzania funkcji księgowania podwójnej waluty w domenie podatkowej oraz wpływu na potrzeby obliczania i księgowania podatku
author: EricWang
manager: Ann Beebe
ms.date: 12/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 9e5db8e4bbd14aa30196e3be617cdfcb72c091fd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446756"
---
# <a name="dual-currency-support-for-sales-tax"></a>Obsługa podwójnej waluty dla podatku
[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak rozszerzyć rozliczanie w dwóch walutach dla podatków od sprzedaży oraz wpływ na obliczenia, księgowanie i rozliczenia podatku od sprzedaży.

Funkcja podwójnej waluty w Dynamics 365 Finance została wprowadzona w wersji 8.1 (październik 2018). Zmienia sposób obliczania wpisów księgowych w walucie raportowania.

W poprzednich wersjach transakcje zostały przekształcone w walutę raportowania w następującej kolejności: 

- Suma transakcji została obliczona w walucie transakcji > kwota transakcji została przekonwertowana na walutę rozliczeniową > kwota w walucie rozliczeniowej została przekonwertowana na walutę raportowania

Po włączeniu funkcji podwójnej waluty transakcje zostały przekonwertowane na walutę raportowania w następującej kolejności:

- Kwota w walucie transakcji > Kwota w walucie raportowania

Aby uzyskać więcej informacji na temat podwójnej waluty, zobacz [Dwie waluty](dual-currency.md).

W związku z obsługą dwóch walut w zarządzaniu funkcjami są dostępne dwie nowe funkcje: 

- Konwersja podatku (wydanie w wersji 10.0.9)
- Automatyczne saldo rozliczeń podatkowych w walucie raportowania (wydanie w wersji 10.0.11)

Obsługa podwójnej waluty dla podatków gwarantuje, że podatki są obliczane dokładnie w walucie podatkowej, a saldo rozliczenia podatku jest dokładnie obliczane w walucie rozliczeniowej i walucie raportowania. 

## <a name="sales-tax-conversion"></a>Konwersja podatku

Parametr **Konwersja podatku** umożliwia dostęp do dwóch opcji konwersji kwoty podatku z waluty transakcji na walutę podatkową. 

- Waluta rozliczeniowa: Ścieżka będzie następująca: „Kwota w walucie transakcji > Kwota w walucie rozliczeniowej > Kwota w walucie podatku”. W konwersji walut zostanie użyta metoda obliczania kursu wymiany waluty rozliczeniowej (skonfigurowanej w ustawieniach księgi).
- Waluta raportowania: Ścieżka będzie następująca: „Kwota w walucie transakcji > Kwota w walucie raportowania > Kwota w walucie podatku”. W konwersji walut zostanie użyta metoda obliczania kursu wymiany waluty raportowania (skonfigurowanej w ustawieniach księgi).

### <a name="example"></a>Przykład

Prosty przykład demonstrujący to działanie:

Ustawienia waluty dla księgi i podatku

| Waluta transakcji | Waluta rozliczeniowa | Waluta raportowania | Waluta podatku |
| -------------------- | ------------------- | ------------------ | ------------ |
| EUR                  | USD                 | GBP                | GBP          |

Kurs wymiany

| Z waluty | Na walutę | Współczynnik | Kurs wymiany |
| ------------- | ----------- | ------ | ------------- |
| EUR           | USD         | 1      | 1.11          |
| EUR           | GBP         | 1      | 0.83          |
| USD           | GBP         | 1      | 0.75          |

Obliczanie kwoty podatku w różnych opcjach parametrów

Kwota podatku = 100 EUR

| Parametry konwersji podatku | Waluta transakcji (EUR) | Waluta rozliczeniowa (USD) | Waluta raportowania (GBP) | Waluta podatku (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Waluta rozliczeniowa             | 100                        | 111                       | 83                       | **83.25**          |
| Waluta raportowania              | 100                        | 111                       | 83                       | **83**             |

Ten parametr można skonfigurować w zależności od potrzeby zgodności z urzędu skarbowego.


### <a name="upgrade-consideration"></a>Uwagi dotyczące uaktualnienia

Ta funkcja jest stosowana tylko w przypadku nowych transakcji. W przypadku transakcji podatkowej zapisanej już w tabeli TAXTRANS, ale jeszcze nie rozliczonej, system nie obliczy ponownie kwoty podatku w walucie podatku, ponieważ brak kursu wymiany w czasie księgowania podatku.

Aby zapobiec poprzedzającym scenariuszom, zalecamy zmianę tej wartości parametru w nowym (czystym) okresie rozliczania podatku, który nie zawiera żadnych nierozstrzygniętych transakcji podatkowych. Aby zmienić tę wartość w środku okresu rozliczania podatku, przed zmianą tej wartości parametru uruchom program „Rozlicz i zasięguj podatek” dla bieżącego okresu rozliczania podatku.


## <a name="track-reporting-currency-tax-amount"></a>Śledź raportowaną kwotę waluty podatku

Trzy nowe pola zostały dodane do tabel związanych z podatkami w celu śledzenia kwot w walucie raportowania. Pola te znajdują się w tabelach TAXUNCOMMITTED i TAXTRANS:

- TaxAmountRep: kwota podatku w walucie raportowania
- TaxBaseAmountRep: kwota bazowa w walucie raportowania
- TaxInCostPriceRep: kwota niepodlegająca odliczeniu w walucie raportowania

Dla podatku zapisanego w tabeli TAXUNCOMMITTED, ale nie zostały jeszcze zaksięgowane, system ponownie obliczy kwotę podatku w walucie raportowania w momencie księgowania i zapisze w tabeli TAXTRANS.

W tej wersji nie będą uwzględniane zmiany w raportach i formularzach, w których kwota podatku jest wyświetlana w walucie raportowania. Zmiany w raportach i formularzach będą dostarczane w przyszłym wydaniu.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Automatyczne saldo rozliczeń podatkowych w walucie raportowania

Jeśli rozliczenie podatkowe nie jest zrównoważone w walucie raportowania z pewnych powodów, takich jak ścieżka konwersji podatku od sprzedaży to „Waluta rozliczeniowa” lub zmiana kursu walutowego w jednym okresie rozliczeniowym, a system automatycznie wygeneruje zapisy księgowe w celu dostosowania wariacji kwoty podatku i wyrównania jej z kontem dodatniej/ujemnej różnicy kursowej, która jest skonfigurowana w ustawieniach Księgi.

Korzystając z poprzedniego przykładu w celu zademonstrowania tej funkcji, załóżmy, że dane w tabeli TAXTRANS w momencie księgowania są następujące:

| Parametry konwersji podatku | Waluta transakcji (EUR) | Waluta rozliczeniowa (USD) | Waluta raportowania (GBP) | Waluta podatku (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Waluta rozliczeniowa             | 100                        | 111                       | 83                       | **83.25**          |
| Waluta raportowania              | 100                        | 111                       | 83                       | **83**             |

Po uruchomieniu programu rozliczania podatków po upływie miesiąca wpis księgowy będzie następujący:
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Scenariusz: przeliczenie podatku od sprzedaży = „Waluta rozliczeniowa”

| Konto główne           | Waluta transakcji (GBP) | Waluta rozliczeniowa (USD) | Waluta raportowania (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Podatek należny/naliczony | -83.25                     | -111                      | -83.25                   |
| Rozliczenie podatku         | 83.25                      | 111                       | 83.25                    |
| Niezrealizowana dodatnia/ujemna różnica kursowa     | 0                          | 0                         | -0.25                    |
| Podatek należny/naliczony | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Scenariusz: przeliczenie podatku od sprzedaży = „Waluta raportowania”


| Konto główne           | Waluta transakcji (GBP) | Waluta rozliczeniowa (USD) | Waluta raportowania (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Podatek należny/naliczony | -83                        | -110.67                   | -83                      |
| Rozliczenie podatku         | 83                         | 110.67                    | 83                       |
| Niezrealizowana dodatnia/ujemna różnica kursowa     | 0                          | 0.33                      | 0                        |
| Podatek należny/naliczony | 0                          | -0.33                     | 0                        |



Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Dwie waluty](dual-currency.md)
- [Omówienie podatku](indirect-taxes-overview.md)

