---
title: Wyświetlanie wpisów w arkuszu i transakcji
description: W tym artykule wyjaśniono różne sposoby, za pomocą których można przeglądać zapisy w arkuszu i transakcje.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 79329b60f0aa7ce196b55a1483b07f8b9ea7e3cf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446801"
---
# <a name="view-journal-entries-and-transactions"></a>Wyświetlanie wpisów w arkuszu i transakcji

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono różne sposoby, za pomocą których można przeglądać zapisy w arkuszu i transakcje. 

Użytkownicy, którzy chcą wyświetlać arkusze i transakcje, mają wiele możliwości uzyskania dostępu do tych danych. Mogą korzystać ze stron zapytania, które oferują możliwość przechodzenia na bardziej szczegółowe poziomy, a także używać różnych opcji raportów w księdze głównej.

## <a name="voucher-transactions"></a>Transakcje na załączniku
**Transakcje na załączniku** to strona zapytania, na której można wybierać różne tabele i pola do określenia kryteriów szukanych sald lub transakcji. Na przykład można wyświetlić wszystkie transakcje z określonego dnia lub konta, albo wszystkie transakcje typu **operacyjnego** znajdujące się w warstwie księgowania. Domyślnie strona ta zawiera numer arkusza, załącznik, datę i konto główne, ale można dodać kolejne tabele, pola i kryteria w celu zawężenia kryteriów wyszukiwania.

## <a name="audit-trail"></a>Dziennik inspekcji
**Dziennik inspekcji** to strona zapytania, która pokazuje typy transakcji, opisy, informacje o tym, kto utworzył transakcje i kiedy zostały utworzone. Ze strony zapytania **dziennika inspekcji** można wyświetlić transakcje na załączniku.

## <a name="financial-reports"></a>Raporty finansowe
Można także przeglądać i analizować transakcje księgi głównej za pomocą raportów finansowych. Ze względu na to, że projekt raportów finansowych może być oparty na kontach, wymiarach, kategoriach kont lub kombinacji tych elementów, można wyświetlać transakcje poprzez przechodzenie na bardziej szczegółowe poziomy. Aby wyświetlić więcej informacji o transakcjach księgi głównej, można także uwzględnić wiele właściwości transakcji w projekcie raportu. Ponadto, jeśli chcesz wyświetlić transakcje składające się na saldo księgi głównej, możesz przechodzić na bardziej szczegółowe poziomy do transakcji konta, tak samo jak ze strony listy **bilansu próbnego**.

## <a name="ledger-reports"></a>Raporty księgi
Oprócz raportów finansowych można używać następujących raportów księgowych w celu wyświetlania transakcji księgi głównej:

-   **Zestawienie wymiarów** — ten raport pokazuje transakcje według dnia i kont; można także wyświetlić transakcje według wymiaru i okresu.
-   **Lista transakcji księgi** — ten raport pokazuje transakcje w walutach transakcji, księgowania i raportowania dla danego konta.
-   **Drukowanie arkusza** — W tym raporcie widać wynik opublikowanego arkusza. Można wygenerować raport według typu arkusza lub arkusza z numerem partii, albo dodać nowe pola.
-   **Transakcje zaksięgowane według arkusza** — raport ten zawiera transakcje, które zostały zaksięgowane w arkuszu, pogrupowane według załącznika.
-   **Wykaz transakcji wg daty** — ten raport zawiera wszystkie transakcje według dat, łącznie z numerem arkusza, załącznikiem i kontem księgowym. Ponadto pokazuje transakcje w walutach transakcji, księgowania i raportowania.
-   **Podstawa transakcji** — ten raport pokazuje konta według arkusza, transakcji, księgowania i waluty raportowania. Pokazuje także każdy wiersz arkusza, który został użyty jako konto przeciwstawne.


## <a name="additional-resources"></a>Dodatkowe zasoby
- [Salda kont księgi głównej](general-ledger-account-balances.md) 
- [Eksplorator źródeł księgowania](../accounts-payable/accounting-source-explorer.md)
- [Omówienie raportowania finansowego](financial-reporting-getting-started.md)
- [Wyświetlanie wpisów w arkuszu lub transakcji](tasks/view-journal-entries-or-transactions.md)



