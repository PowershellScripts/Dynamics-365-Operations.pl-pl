---
title: Poręczenia
description: Ten artykuł zawiera informacje o poręczeniach. W poręczeniu bank zgadza się zapłacić określoną kwotę pieniędzy osobie, jeśli jeden z klientów banku nie ureguluje wobec tej osoby zobowiązania pieniężnego lub innego.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3dbf08679c165258a4a4027bf1cf73484d9efd3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446846"
---
# <a name="letters-of-guarantee"></a>Poręczenia

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o poręczeniach. W poręczeniu bank zgadza się zapłacić określoną kwotę pieniędzy osobie, jeśli jeden z klientów banku nie ureguluje wobec tej osoby zobowiązania pieniężnego lub innego. 

Poręczenie to zobowiązanie się banku (gwaranta) do zapłaty określonej kwoty pieniędzy określonej osobie (beneficjentowi), jeśli bank odbiorca (podmiot zabezpieczeń) nie wywiąże się z realizacji płatności lub zobowiązania względem beneficjenta. Poręczenia są niezbywalne. Dotyczą one tylko beneficjenta wskazanego w umowie. Podmiot zabezpieczeń może wnioskować o zwiększenie lub zmniejszenie wartości poręczenia, zgodnie z warunkami umowy. 

Aby zrealizować poręczenie, beneficjent musi przed upływem daty ważności przesłać oryginalne poręczenie i poinformować bank obsługujący zobowiązania podmiotu zabezpieczeń. Bank następnie wypłaca kwotę należności na konto beneficjenta zgodnie z ustaleniami określonymi w poręczeniu. Bank zatrzymuje procent płatności jako marżę. Wartość procentowa jest uzgodniona z góry i zapisana w warunkach umowy. 

Można utworzyć kod do śledzenia celu poręczenia. Można również określić przyczyny, które będą skojarzone z poręczeniem w przypadku jego anulowania. Kody celów i przyczyny podane przez bank można wyświetlać na stronach **Kody celów płatności** i **Przyczyny transakcji bankowych**. 

Na stronie **poręczenia** można wykonać następujące zadania:

-   Tworzenie poprawnych pozycji księgowania i eliminacja wprowadzania ręcznego.
-   Rejestrowanie wszystkich powiązanych transakcji pieniężnych i niepieniężnych i śledzenie sald poręczeń.
-   Rejestrowanie i śledzenie stanu i dat wygaśnięcia poręczenia.
-   Generowanie raportu, który zawiera listę banków posiadających poręczenia.

W poniższej tabeli opisano akcje, które można wykonywać w związku z poręczeniem.

| Akcja              | Cel                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Prześlij do banku      | Przesłanie do banku wniosku o wystawienie poręczenia.                                                                       |
| Otrzymaj z banku   | Gdy bank wyrazi zgodę na przesłany wniosek, można odebrać poręczenie.                            |
| Przekaż beneficjentowi | Po otrzymaniu poręczenia z banku można je przekazać beneficjentowi.              |
| Zwiększ wartość      | Jeśli beneficjent i podmiot zabezpieczeń wyrażą zgodę, można zwiększyć wartość pieniężną.                                                  |
| Zmniejsz wartość      | Jeśli beneficjent i podmiot zabezpieczeń wyrażą zgodę, można zmniejszyć wartość pieniężną.                                                  |
| Rozszerz              | Po przedstawieniu beneficjentowi poręczenia można wydłużyć okres ważności, jeśli jego wydłużenie jest konieczne. |
| Anuluj              | Jeśli cel poręczenia nie ma już zastosowania, można anulować umowę.                  |
| Zlikwiduj           | Kiedy beneficjent okaże w banku poręczenie, można je spłacić.                      |


Aby uzyskać więcej informacji, zobacz następujące tematy:

[Transakcja poręczenia](tasks/letter-guarantee-transaction.md)

[Konfigurowanie instrumentów bankowych i profilów księgowania dla poręczeń](tasks/set-up-bank-facilities-posting-profiles.md)


