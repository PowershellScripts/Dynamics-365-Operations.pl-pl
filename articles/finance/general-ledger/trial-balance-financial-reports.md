---
title: Raporty finansowe bilansu próbnego
description: W tym artykule opisano domyślne raporty o bilansach próbnych. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami oraz sposoby modyfikowania raportów w celu dostosowania ich do wymagań biznesowych.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b48510febf5a5f9f4a01728b242d9750b3c62c2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446648"
---
# <a name="trial-balance-financial-reports"></a>Raporty finansowe bilansu próbnego

[!include [banner](../includes/banner.md)]

W tym artykule opisano domyślne raporty o bilansach próbnych. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami oraz sposoby modyfikowania raportów w celu dostosowania ich do wymagań biznesowych. 

<a name="default-trial-balance-reports"></a>Domyślne raporty finansowe bilansu próbnego
-----------------------------

W module Raporty finansowe są dostępne trzy raporty bilansu próbnego.

| Raport domyślny                                 | Działanie                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szczegółowy bilans próbny — domyślne               | Oferuje informacje dla wszystkich kont i obejmuje wszystkie salda po stronie debetowej i kredytowej, oraz ich wartości netto, wraz z datą transakcji, załącznikiem i opisem arkusza.                  |
| Sumaryczny bilans próbny — domyślny                | Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto.                                        |
| Sumaryczny bilans próbny rok do roku — domyślny | Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto dla bieżącego roku i roku ubiegłego. |

## <a name="building-blocks"></a>Podstawowe elementy
Raporty finansowe bilansu próbnego wykorzystują następujące podstawowe elementy.

| Raport domyślny                                 | Definicja wiersza          | Definicja kolumny                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Szczegółowy bilans próbny — domyślne               | Bilans próbny — domyślny | Szczegółowy bilans próbny — domyślne               |
| Sumaryczny bilans próbny — domyślny                | Bilans próbny — domyślny | Sumaryczny bilans próbny — domyślny                |
| Sumaryczny bilans próbny rok do roku — domyślny | Bilans próbny — domyślny | Sumaryczny bilans próbny rok do roku — domyślny |

### <a name="row-definition"></a>Definicja wiersza

Definicja wiersza Bilans próbny — domyślny zawiera pojedynczy wiersz, który pobiera informacje ze wszystkich kont głównych. Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian. Podczas przeglądania raportu można przejść do pojedynczego wiersza, aby wyświetlić szczegóły dotyczące poszczególnych kont. Można zmodyfikować definicję wiersza, tak aby zawierała więcej szczegółów. Aby zmodyfikować definicję wiersza Bilans próbny — domyślny, by zawierał wiesze dla wszystkich kont, należy wykonać następujące kroki.

1.  Kliknij **Edycja**, a następnie kliknij **Wstaw wiersze z wymiarów**. Polecenie **Wstaw wiersze z wymiarów** pozwala wybrać wymiary, które mają znaleźć się w definicji wiersza. Dla tej definicji wiersza użyjesz **Konta głównego**.
2.  Upewnij się, że **Konto główne** zawiera wszystkie znaki „&”, a następnie kliknij przycisk **OK**.

Teraz definicja wiersza zawiera wszystkie konta główne dla Twojej domyślnej firmy.

### <a name="column-definition"></a>Definicja kolumny

Każdy raport bilansu próbnego używa innej definicji kolumny. Te definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.

-   **Szczegółowy bilans próbny — domyślne typy kolumn:**
    -   **DESC** — opis z definicji wiersza
    -   **ACCT** — kody konta
    -   **ATTR (3)** — atrybuty:
        -   Data transakcji
        -   Załącznik
        -   Opis arkusza
    -   **FD** — dane finansowe zawierające tylko debety
    -   **FD** — dane finansowe zawierające tylko kredyty
    -   **CALC** — różnica netto
-   **Sumaryczny bilans próbny — domyślne typy kolumn:**
    -   **ACCT** — kody konta
    -   **DESC** — opis z definicji wiersza
    -   **ATTR** – atrybut:
        -   Załącznik
    -   **FD** — dane finansowe salda początkowego
    -   **FD** — dane finansowe zawierające tylko debety
    -   **FD** — dane finansowe zawierające tylko kredyty
    -   **CALC** — różnica netto
    -   **CALC** — saldo zamknięcia
-   **Sumaryczny bilans próbny rok do roku — domyślny:**
    -   **ACCT** — kody konta
    -   **DESC** — opis z definicji wiersza
    -   **ATTR** – atrybut
        -   Załącznik
    -   **FD** — dane finansowe salda początkowego dla bieżącego roku
    -   **FD** — dane finansowe zawierające tylko debety dla bieżącego roku
    -   **FD** — dane finansowe zawierające tylko kredyty dla bieżącego roku
    -   **CALC** — różnica netto
    -   **CALC** — saldo zamknięcia
    -   **FD** — dane finansowe zawierające tylko debety dla ostatniego roku
    -   **FD** — dane finansowe zawierające tylko kredyty dla ostatniego roku



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie raportowania finansowego](financial-reporting-getting-started.md)

[Wyświetlanie raportów finansowych](view-financial-reports.md)

[Blog o sprawozdawczości finansowej w systemie Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)



