---
title: Przetwarzanie alokacji
description: Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania w Microsoft Dynamics 365 Finance oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c8216ebdd1f26601743e6b35849be0813d06b4a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446806"
---
# <a name="process-allocations"></a>Przetwarzanie alokacji

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.

Ten proces obsługuje następujące możliwości:

-   Ręczne przydzielanie kwot transakcji przy użyciu akcji Podział w zasadach podziału księgowań lub poprzez zastosowanie względem dokumentu domyślnych szablonów wymiaru finansowego. Aby uzyskać więcej informacji, zobacz [Zasady podziału księgowań](../accounts-payable/accounting-distributions.md).
-   Automatyczne przydzielanie kwot transakcji na podstawie warunków alokacji zdefiniowanych na poszczególnych kontach głównych. Zapisy na koncie alokacji zostaną wygenerowane dla każdego arkusza według wartości procentowej i docelowego konta księgowego zawsze gdy zapis księgowy spełnia kryteria określone jako konto księgowe źródła. Aby uzyskać więcej informacji, zobacz [Warunki alokacji konta głównego](../general-ledger/main-account-allocation-terms.md)
-   Automatyczne przydzielanie sald księgi lub stałych kwot na podstawie reguł alokacji księgi. Reguły alokacji księgi są przetwarzane w regularnych odstępach przy użyciu arkuszy alokacji. Aby uzyskać więcej informacji, zobacz temat [Reguły alokacji](../general-ledger/ledger-allocation-rules.md).

###  <a name="allocations-in-budget-planning"></a>Alokacje w planowaniu budżetu

Reguły alokacji księgi mogą służyć do obsługi planów budżetowych. Korzystając z reguł alokacji księgi do planowania budżetu, reguły alokacji działają tak samo jak w księdze, ale źródło danych oraz miejsce docelowe danych pochodzi z planu budżetu. Można ręcznie wybrać reguły alokacji księgi do użycia dla planów budżetu. Można także użyć harmonogramu alokacji, który jest uruchamiany jako część procesu przepływu pracy.

> [!NOTE]
> Nie można użyć międzyfirmowych reguł alokacji księgi dla planów budżetu.

