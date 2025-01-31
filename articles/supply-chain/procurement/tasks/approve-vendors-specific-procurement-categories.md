---
title: Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia
description: W tym temacie opisano sposób zatwierdzania dostawców dla poszczególnych kategorii zaopatrzenia w programie Dynamics 365 Supply Chain Management.
author: mkirknel
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e53102d732e9befcaca183adfd2a756c12e0162b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435168"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób zatwierdzania dostawców dla poszczególnych kategorii zaopatrzenia w programie Dynamics 365 Supply Chain Management. Podczas tworzenia zapotrzebowania na zakup może istnieć konieczność wybrania preferowanego lub zatwierdzonego dostawcy, w zależności od konfiguracji zasad zakupów. W tej procedurze pokazano sposób określania, że dostawca jest zatwierdzony lub preferowany dla określonej kategorii zaopatrzenia. To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.

1. W okienku nawigacji przejdź do **Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy**.
2. Zaznacz dostawcę, którego chcesz ustawić jako preferowanego lub zatwierdzonego dla kategorii.
3. W okienku akcji wybierz pozycję **Ogólne**.
4. Wybierz **Kategorie**.
5. Wybierz **Dodaj kategorię**.
6. W polu **Kategoria** wybierz pozycję **AKCESORIA BIUROWE I TECHNICZNE (AKCESORIA BIUROWE I TECHNICZNE)**.
7. W polu **Stan kategorii dostawcy** wybierz wartość **Preferowany**. Istnieje możliwość określenia więcej niż jednego preferowanego dostawcy dla kategorii.  
8. Wybierz opcję **Zapisz**.
9. W okienku nawigacji, wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Kategorie zaopatrzenia**.
10. W drzewie zaznacz element **KATEGORIE ZAOPATRZENIA W FIRMIE\AKCESORIA BIUROWE I TECHNICZNE**.
11. Rozwiń sekcję **Dostawcy**. Sprawdź, czy wybrany dostawca jest wyświetlany jako preferowany dostawca dla kategorii Akcesoria biurowe i techniczne. Jeżeli wykonujesz procedurę jako przewodnik zadania, może być konieczne kliknięcie przycisku **Odblokuj**, aby przewinąć w dół do listy dostawców.  Na tej stronie można również dodawać preferowanych i zatwierdzonych dostawców.  
12. W drzewie rozwiń **AKCESORIA BIUROWE I TECHNICZNE** i wybierz **Nożyczki**.
13. Zaznacz wartość **Nie** w polu **Dziedzicz dostawców po kategorii nadrzędnej:**.
14. Zaznacz wartość **Tak** w polu **Dziedzicz dostawców po kategorii nadrzędnej:**.

