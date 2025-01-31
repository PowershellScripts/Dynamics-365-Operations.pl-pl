---
title: Obliczony podatek dla ogólnych wierszy arkuszy finansowych
description: W tym temacie objaśniono, w jaki sposób podatki są obliczane dla różnych typów kont (dostawca, odbiorca, Księga i projekt) w wierszach arkusza finansowego.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
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
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 51d43c8e6d16201e1f8c392c13ead20287782dcc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446652"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Obliczony podatek dla ogólnych wierszy arkuszy finansowych
[!include [banner](../includes/banner.md)]

W tym temacie objaśniono, w jaki sposób podatki są obliczane dla różnych typów kont (dostawca, odbiorca, Księga i projekt) w wierszach arkusza finansowego.

Ten proces można podzielić na trzy etapy:

- Określ kierunek podatku.

- Umożliwia określenie kwoty podatku, która będzie przechowywaną tymczasową tabelą podatku od sprzedaży.

- Umożliwia określenie kwoty i konta podatku w załączniku.

## <a name="determine-the-sales-tax-direction"></a>Określ kierunek podatku

Sposób ustalania kierunku podatku zależy od typu konta w załączniku. Kierunek podatku jest określony przez kombinację typu konta i kodu podatku. Bardziej szczegółowe informacje podano w poniższych sekcjach. 

### <a name="account-type-is-project"></a>Konto typu Projekt

Jeśli załącznik ma wiersz arkusza, w którym typem konta jest **Projekt**, to ten sam kierunek podatku jest stosowany w odniesieniu do wszystkich wierszy arkusza w załączniku. Na ilustracji poniżej widać regułę. W poniższych punktach przedstawiono możliwe kierunki podatku dla kont projektów.

• Jeśli kod podatku jest używany jako podatek, kierunek podatku jest używany jako podatek.

• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.

• Jeśli kod podatku jest używany jako VAT między firmami, kierunek podatku jest używany jako Podatek należny.

• Jeśli kod podatku jest używany jako odwrotne obciążenie, kierunek podatku jest używany jako Podatek należny.

W przeciwnym razie kierunek podatku jest naliczony od sprzedaży.

Na poniższym diagramie przedstawiono regułę graficznie.

![Możliwości podatkowe dla kont projektu](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>Konto typu Dostawca

Jeśli załącznik ma wiersz arkusza, w którym typem konta jest **Dostawca**, to ten sam kierunek podatku jest stosowany w odniesieniu do wszystkich wierszy arkusza w załączniku. W poniższych punktach przedstawiono możliwe kierunki podatku dla kont dostawców. 

• Jeśli kod podatku jest używany jako podatek, kierunek podatku jest używany jako podatek.

• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.

• Jeśli kod podatku jest używany jako VAT między firmami, kierunek podatku jest używany jako Podatek należny.

• Jeśli kod podatku jest używany jako odwrotne obciążenie, kierunek podatku jest używany jako Podatek należny.

W przeciwnym razie kierunek podatku jest naliczony od sprzedaży.

Na poniższym diagramie przedstawiono regułę graficznie.

![Możliwości podatkowe dla kont dostawców](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>Konto typu Odbiorca

Jeśli załącznik ma wiersz arkusza, w którym typem konta jest **Odbiorca**, to ten sam kierunek podatku jest stosowany w odniesieniu do wszystkich wierszy arkusza w załączniku. W poniższych punktach przedstawiono możliwe kierunki podatku dla kont odbiorców.

• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.

• Jeśli kod podatku jest używany jako VAT między firmami, kierunek podatku jest używany jako Podatek naliczony.

• Jeśli kod podatku jest używany jako odwrotne obciążenie, kierunek podatku jest używany jako Podatek naliczony.

W przeciwnym razie kierunek podatku jest podatek naliczony.

Na poniższym diagramie przedstawiono regułę graficznie.

![Możliwości podatkowe dla kont odbiorców](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>Konto typu Księga

Na poniższej ilustracji przedstawiono regułę, która ma zastosowanie, gdy załącznik ma tylko wiersze arkusza, w których typem konta jest **Księga**. W poniższych punktach przedstawiono możliwe kierunki podatku dla kont księgi.

• Jeśli kod podatku jest używany jako podatek, kierunek podatku jest używany jako podatek.

• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.

W przeciwnym razie, jeśli kwota arkusza ma wartość debet (dodatnia), kierunek podatku jest podatek naliczony; jeśli kwota arkusza to kredyt (ujemny), kierunek podatku jest naliczony.

Na poniższym diagramie przedstawiono regułę graficznie.

![Możliwości podatkowe dla kont księgi](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Zastąp kierunek podatku

Kierunek podatku można zastąpić, jeśli załącznik zawiera tylko wiersze, dla których typem konta jest **Księga.**

Umożliwia przejście **Księga główna \> Plan kont \> Konta \> Główne konta** i na karcie skróconej wybierz **Firma zastępuje**.

## <a name="determine-the-sales-tax-amount"></a>Określ kwotę podatku

W tej sekcji opisano sposób obliczania znaku kwoty podatku od sprzedaży.

![Strona transakcji podatku](media/sales-tax-amount-sign.jpg)

W poniższej tabeli przedstawiono regułę rodzajową służącą do określania znaku kwot podatku w tabeli tymczasowych podatków od sprzedaży.

| Liczba wierszy w arkuszu | Kierunek podatku  | Kwota podatku — podpisz |
|---------------------|----------------------|-----------------------|
| Dodatni            | Podatek naliczony | Dodatni              |
| Dodatni            | Podatek należny    | Ujemny              |
| Ujemny            | Podatek naliczony | Ujemny              |
| Ujemny            | Podatek należny    | Dodatni              |

Istnieje specjalna reguła dla załączników, które mają tylko wiersze **projektu** lub **księgi**, jeśli w wierszu **księgi** wybrano grupę podatków lub grupę podatków dla danego towaru. Ta reguła jest kontrolowana przez włączenie funkcji niezależnego obliczania podatku dla arkuszy finansowych. Gdy ta funkcja jest wyłączona, kwota podatku w wierszu **Księgi** używa kierunku debetu/kredytu wiersza **Projektu**. Gdy ta funkcja jest wyłączona, kwota podatku w wierszu **księgi** używa kierunku debetu/kredytu wiersza projektu. W poniższych tabelach przedstawiono reguły dla każdego scenariusza. 

**Reguła, gdy funkcja jest włączona.**

| Kwota wiersza arkusza dla projektu | Kierunek podatku  | Kwota podatku — podpisz |
|--------------------------------|----------------------|-----------------------|
| Dodatni                       | Podatek naliczony | Dodatni              |
| Ujemny                       | Podatek naliczony | Ujemny              |

**Reguła, gdy funkcja jest wyłączona**

| Kwota wiersza arkusza dla księgi  | Kierunek podatku  | Kwota podatku — podpisz |
|--------------------------------|----------------------|-----------------------|
| Dodatni                       | Podatek naliczony | Dodatni              |
| Ujemny                       | Podatek naliczony | Ujemny              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Umożliwia określenie kwoty i konta podatku w załączniku

Podczas księgowania podatków konto główne jest pobierane z profilu grupy księgowania w księdze. W przypadku podatku należnego system używa konta podatku należnego określonego w profilu. W przypadku podatku należnego system używa konta podatku należnego określonego w profilu.

Poniższa tabela przedstawia ogólną regułę.

| Kierunek podatku  | Kwota podatku — podpisz | Konto podatku      | Kwota w załączniku |
|----------------------|-----------------------|------------------------|-------------------|
| Podatek naliczony | Dodatni              | Konto podatku naliczonego | Dodatnie (Debet)  |
| Podatek naliczony | Ujemny              | Konto podatku naliczonego | Ujemne (kredyt)  |
| Podatek należny    | Dodatni              | Konto podatku należnego    | Ujemne (kredyt)  |
| Podatek należny    | Ujemny              | Konto podatku należnego    | Dodatnie (Debet)  |
