---
title: Obsługa zamówień planowanych
description: Ten temat zawiera informacje o metodach zarządzania zamówienia planowanymi. Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.
author: roxanadiaconu
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f62381ca212e711fd61e12c9ec8f066ec124a933
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435463"
---
# <a name="maintain-planned-orders"></a>Obsługa zamówień planowanych

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o metodach zarządzania zamówienia planowanymi. Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.

Można zarządzać planowanymi zamówieniami z obszaru roboczego **Planowanie główne**, listy **Zamówienie planowane** lub list **Planowane zamówienia zakupu**, **Planowane zlecenia produkcyjne** i **Planowane przeniesienie**. 

## <a name="planned-order-status"></a>Stan zamówienia planowanego
Pole **Stan** pomaga w śledzeniu postępu zamówień. Używane są następujące wartości:

-   Zamówienia planowane generowane podczas planowania głównego mają stan **Nieprzetworzone**.
-   Jeżeli nie chcesz ustalać zamówienia planowanego, możesz nadać mu stan **Zakończone**.
-   Aby ustalić zamówienie planowane, można zmienić stan na **zatwierdzone**. Zamówienia planowane ze stanem **zatwierdzonym** są przestrzegane w planowaniu głównym, więc nie można ich modyfikować ani usuwać podczas późniejszego przebiegu planowania głównego. Aby to osiągnąć, logika planowania kopiuje **zatwierdzone** zamówienia planowane ze starej wersji planu do nowej wersji planu podczas planowania głównego.

## <a name="firming-planned-orders"></a>Akceptacja planowanych zamówień 
Podczas ustalania zamówień planowanych tworzone są rzeczywiste zamówienia. Są one również znane jako zamówienia *zwolnione* lub *otwarte*. Po ustaleniu zamówienie planowane zostanie przesunięte do sekcji zamówień w odpowiednim module.

Na stronie **zamówienia planowane** można wybrać dwie opcje ustalania:

-   **Akceptowane** — umożliwia ustalenie jednego lub wielu wybranych zamówień planowanych.
-   **Zaakceptuj wszystko** — spowoduje to ustalenie wszystkich zamówień planowanych w filtrze. Używanie **zaakceptuj wszystko** nie musisz wybierać planowanego zamówienia, wszystkie planowane zamówienia w ramach filtru zostaną ustalone. Ta opcja może być przydatna w przypadku ustalania dużej liczby zamówień planowanych.

> [!NOTE]
> Istnieje możliwość śledzenia planowanego zamówienia, które zostało ustalone z **Historia akceptacji** pod **Planowane formularze zamówień > Zobacz > Historia akceptacji**.

## <a name="parallelize-firming"></a>Zrównoleglenie akceptacji
Jeśli planujesz ustalać wiele zamówień w tym samym czasie, parallelizing przebieg może poprawić czas działania lub wydajność. Ta opcja jest dostępna podczas ustalania wielu zamówień planowanych z **Zaakceptuj** lub **Zaakceptuj wszystko**. Dostępne są następujące parametry:

-   **Równoległa akceptacja** — Jeśli **tak**, proces ustalania będzie równoległy do liczby wątków zdefiniowanych w **liczbie wątków.**
-   **Liczba wątków** — określa liczbę wątków używanych do parallelize procesu ustalania. Parametr jest wyświetlany tylko wtedy, gdy ustawienie **Równoległa akceptacja** ma wartość **tak**.

> [!NOTE]
> Opcja **równoległej akceptacji** jest wyświetlana tylko wtedy, gdy wybrano więcej niż jedno zamówienie planowane do akceptacji.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie planów głównych](master-plans.md)



