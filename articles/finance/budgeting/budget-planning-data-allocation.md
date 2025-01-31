---
title: Alokacja danych na potrzeby planowania budżetu
description: W tym temacie opisano różne metody alokacji dostępne w Microsoft Dynamics 365 Finance oraz sposoby ich wykorzystywania.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceddeda5760d961568d58e7e4805955ea972c586
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446926"
---
# <a name="budget-planning-data-allocation"></a>Alokacja danych na potrzeby planowania budżetu

[!include [banner](../includes/banner.md)]

W tym temacie opisano różne metody alokacji dostępne w Microsoft Dynamics 365 Finance oraz sposoby ich wykorzystywania.  

Dane planu budżetu można dystrybuować na wiele sposobów, by dokładnie odzwierciedlić przewidywane kwoty.

## <a name="allocation-methods"></a>Metody alokacji
Za pomocą trzech metod alokacji (Alokuj między okresami, Alokuj do wymiarów i Użyj reguł alokacji księgi) można utworzyć wiersze planu budżetu oparte na wierszach w tym samym planie budżetu. Za pomocą trzech innych metod (Agreguj, Dystrybuuj i Kopiuj z planu budżetu) można utworzyć wiersze planu budżetu w innych planach budżetu. We wszystkich sześciu metodach alokacji można określić scenariusza docelowy. Scenariusz docelowy może być albo taki sam jak scenariusz źródłowy lub inny od scenariusza źródłowego. Ponadto można określić, czy nowe wiersze są dołączane do planu budżetu czy zastępują bieżące wiersze planu budżetu.

> [!NOTE] 
> W celu agregacji, który jest inny niż scenariusz używany do dystrybucji lub innych modyfikacji wykonanych wcześniej w planie nadrzędnym, należy używać unikatowego scenariusza.  

[![Alokacja między okresami metodą alokacji](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Alokuj między okresami** — Kategoria alokacji okresu jest używana do alokacji wierszy planu budżetu ze źródłowego scenariusza planu budżetu między okresy w scenariuszu docelowym. Kwota źródłowa jest przypisywana do wielu wierszy w scenariuszu docelowym na podstawie wartości procentowej i danych zdefiniowanych w kategorii alokacji okresu.         

[![Alokacja do wymiarów metodą alokacji](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Alokuj do wymiarów** — wiersze planu budżetu są alokowane ze scenariusza źródłowego planowania budżetu do jednego lub kilku wierszy w scenariuszu docelowym na podstawie wartości procentowych i wymiarów finansowych, które są zdefiniowane w wybranym warunku alokacji budżetu.           

![Agregowanie wykresu](./media/aggregatechart-300x230.png)
**Agreguj** — agregowanie wierszy planu budżetu następuje ze źródłowego scenariusza planu budżetu w powiązanych (podrzędnych) planach budżetu do docelowego scenariusza w nadrzędnym planie budżetu. Ta metoda umożliwia konsolidowanie z wyższym poziomem kwot budżetowych przygotowywanych na niższym poziomie organizacji.          

[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Dystybuowanie wykresu** — wiersze planu budżetu są rozdzielane ze scenariusza źródłowego planowania budżetu w nadrzędnym planie budżetu do scenariusza docelowego w skojarzonych planach budżetu (podrzędnych) na podstawie wymiarów finansowych jednostek organizacyjnych skojarzonych planów. Ta metoda umożliwia rozkładanie do kontroli lokalnej kwot budżetowych przygotowywanych na wyższym poziomie organizacji.           

[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Reguły alokacji księgi** — rozdzielanie wierszy planu budżetu następuje ze źródłowego scenariusza planowania budżetu do docelowego scenariusza planu budżetu na podstawie wybranej reguły alokacji księgi. 

[![Kopiuj z planu budżetowego](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Kopiuj z planu budżetu** — tak jak w metodzie dystrybucji alokacji wiersze planu budżetu są tworzone w lokalizacji docelowej na podstawie wierszy w powiązanym planie budżetu. Jednak w tej metodzie źródłowy plan budżetu nie musi być elementem nadrzędnym, ale może być na dowolnym wyższym poziomie w hierarchii planów budżetu. Ta metoda alokacji jest użyteczna, jeśli skonsolidowane kwoty są pierwotnie budżetowane na dużo wyższym poziomie, i muszą być przekazywane na niższy poziom organizacji do szczegółowego sprawdzenia i korekty, zanim będą mogły zostać zatwierdzone na wyższym poziomie.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Korzystanie z metod alokacji w planie budżetu
Aby wykonać alokacje na stronie plan budżetu, wybierz wiersze do alokowania, a następnie kliknij przycisk **Alokuj budżet**.

[![Przycisk alokowania budżetu](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

Następnie wybierz metodę alokacji. Pozostałe pola są następnie ustawiane na podstawie wybranej metody. Te pola uwzględniają źródło i lokalizację docelową danych planu budżetu oraz opcję mnożenia źródeł przez określony współczynnik podczas tworzenia kwoty docelowej, aby uprościć korekty wsadowe. Można również ustawić opcję **Dołącz do planu**. Wybierz **Nie**, aby zastąpić istniejące wiersze planu budżetu lub wybierz **Tak**, aby zachować istniejące wiersze planu budżetu i dodać nowe wiersze dla alokowanych kwot.

## <a name="automating-allocations-during-a-workflow"></a>Automatyzacja alokacji podczas przepływu pracy
Jedna zaawansowana funkcja pozwala wykonywać alokacje automatycznie w ramach przepływu pracy planowania budżetu. W miarę realizacji przepływu pracy planu budżetu zautomatyzowane zadania mogą wywoływać alokację na określonym etapie planowania budżetu. 

Aby skonfigurować automatyczne alokacje, należy najpierw utworzyć harmonogram alokacji na stronie **Konfiguracja planowania budżetu**. Harmonogram alokacji definiuje metodę alokacji, która będzie używana podczas automatycznego alokowania oraz wartości różnych opcji alokacji (opisy znajdują się w poprzedniej sekcji). 

Następnie należy utworzyć alokację etapu na stronie **Konfiguracja planowania budżetu**. Alokacja etapu przypisuje harmonogram alokacji do przepływu pracy i etapu planowania budżetu. 

Na koniec należy dodać zautomatyzowane zadanie dla alokacji etapu planowania budżetu na wybranych etapie przepływu pracy. W poniższym przykładzie dwie alokacje etapu planowania budżetu (wyróżnione na czerwono) zostały wstawione do przepływu pracy.

[![Alokacje etapu planowania budżetu](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)



