---
title: Zgłaszanie zleceń produkcyjnych jako gotowych
description: Zgłoszenie wyrobów gotowych to etap produkcji. Na tym etapie produkt gotowy jest zgłaszany i przenoszony ze zlecenia produkcyjnego do zapasów.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87e5d4f46a2ae34a2bc114a92ed4e037875dde43
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435156"
---
# <a name="report-production-orders-as-finished"></a>Zgłaszanie zleceń produkcyjnych jako gotowych

[!include [banner](../includes/banner.md)]

Zgłoszenie wyrobów gotowych to etap produkcji. Na tym etapie produkt gotowy jest zgłaszany i przenoszony ze zlecenia produkcyjnego do zapasów.

Kiedy ilości wyprodukowanych towarów zostanie zgłoszona jako ukończona w zleceniu produkcyjnym, jest ona aktualizowana w magazynie. Ilości częściowe pierwotnie zaplanowanego zamówienia mogą być zgłaszane jako gotowe. Można też zgłaszać błędne ilości razem ze skojarzonym powodem błędu podczas raportowania ilości jako gotowych. Gdy zlecenie produkcyjne osiągnie etap „Zgłoszone jako gotowe”, wskazuje ono, że dalsze ilości nie będą zgłaszane w zleceniu produkcyjnym.
Z procesem **zgłaszania gotowych wyrobów** wiążą się następujące właściwości:
-   Można ustawić zużycie surowców i czas proporcjonalnie do zgłoszonych ilości (kalkulacja zużycia wstecz)
-   Można generować odłożenia dla towarów, które są włączone dla procesów magazynu.
-   Planowana lub standardowa wartość koszty wyrobów gotowych można skonfigurować w taki sposób, by były zgłaszane na kontach księgowych.
-   Można utworzyć zlecenie kontroli jakości dla zgłoszonej ilości na podstawie konfiguracji skojarzenia jakości.

Ilość jest zgłaszana do lokalizacji wyjściowej. Następnie generowana jest praca magazynowa w celu przeniesienia ilości z lokalizacji wyjściowej do miejsca docelowego zdefiniowanego przez dyrektywę lokalizacji dla odłożeń.

-   Zlecenie kontroli jakości może być utworzone podczas zgłaszania zlecenia produkcyjnego jako zakończonego, jeśli skojarzenie jakości zostało skonfigurowane.

## <a name="set-a-production-order-to-reporting-as-finished"></a>Ustawianie stanu zlecenia produkcyjnego na Zgłoszenie wyrobów gotowych
Można ustawić stan zlecenia produkcyjnego na **Zgłoszenie wyrobów gotowych** a pomocą standardowej funkcji aktualizacji zlecenia produkcyjnego lub za pomocą arkusza marszruty i karty karta zadań albo za pomocą arkusza **Zgłoszenie wyrobów gotowych**. Można także zaktualizować etap na **Zgłoszenie wyrobów gotowych** za pomocą stron terminalu karty zadań i urządzenia karty zadań podczas zgłaszania ostatniego zadania zlecenia produkcyjnego. Wreszcie można włączyć opcję **Zgłoszenie wyrobów gotowych** jako proces dla rozwiązania urządzenia podręcznego magazynu.  



