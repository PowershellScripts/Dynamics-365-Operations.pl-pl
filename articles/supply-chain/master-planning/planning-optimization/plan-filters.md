---
title: Stosowanie filtrów do planu
description: W tym temacie wyjaśniono, jak używać filtrów w planie, gdy używana jest funkcja optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 9ddf9934965bd06ec805731a1cc1a667846fa180
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435193"
---
# <a name="apply-filters-to-a-plan"></a>Stosowanie filtrów do planu

[!include [banner](../../includes/banner.md)]

Po użyciu funkcji optymalizacji planowania można zastosować filtr do planu. **Filtr planu** będzie zawsze stosowany podczas procesu planowania głównego. **Filtr planu** jest przydatny, gdy chce się ograniczyć plan do konkretnej grupy towarów i upewnić się, że nie są uwzględniane żadne inne towary jako część wynikowego planowania głównego.

Jeśli zastosowano **filtr planu**, a filtr środowiska uruchomieniowego jest również stosowany podczas procesu planowania głównego, w procesie planowania będzie uwzględniany tylko przecięcie dwóch filtrów.

**Filtr planu** można uzyskać dostęp z **planów głównych** podczas planowania optymalizacji.

## <a name="example-scenario"></a>Przykładowy scenariusz

Filtr planu jest skonfigurowany z pozycjami A, B i C. Następnie uruchamiane są przebiegi planowania głównego dla tego samego planu, ale stosowane są różne filtry czasu wykonywania:

- **Filtr środowiska uruchomieniowego zawierający element D**. Nie są planowane żadne elementy, ponieważ nie istnieje przecięcie między filtrem planu a filtrem środowiska uruchomieniowego.
- **Filtr środowiska uruchomieniowego zawierający element A i D:** w przebiegu planowania uwzględniono tylko element a, ponieważ pozycja D nie jest częścią filtru planu.
- **Filtr środowiska uruchomieniowego zawierający element B:** w przebiegu planowania i poprzednim rezultacie planowania uwzględniono tylko element A.
- **Filtr środowiska uruchomieniowego zawierający wszystkie elementy (pusty filtr):** pozycje A, B i C są uwzględnione w procesie planowania i poprzednie dane wyjściowe planowania dla pozycji a i B są zastępowane.

> [!NOTE]
> Należy unikać ustawiania filtru planu w planie wybranym jako **bieżący dynamiczny plan główny** na stronie **parametrów planowania głównego**. W przeciwnym razie funkcje dynamicznego planu głównego będą ograniczone do elementów filtrowanych. Jeśli na przykład zapotrzebowanie netto jest aktualizowane dla towaru, który nie jest częścią filtru planu, wynik nie zostanie wygenerowany.

## <a name="related-resources"></a>Powiązane zasoby

[Omówienie planowania optymalizacji](planning-optimization-overview.md)

[Rozpocznij pracę z optymalizacją planowania](get-started.md)

[Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)

[Wyświetlanie dzienników historii i planowania planów](plan-history-logs.md)

[Anuluj planowanie pracy](cancel-planning-job.md)
