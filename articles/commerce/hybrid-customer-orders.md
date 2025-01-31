---
title: Hybrydowe zamówienia odbiorców
description: Hybrydowe zamówienie odbiorcy to pojedyncze zamówienie zawierające produkty, które mogą być wyniesione ze sklepu przez odbiorcę, a także produktów, które zostaną odebrane lub wysłane później.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1c2105aa99e0489d7643d076e84123eec628679e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415027"
---
# <a name="hybrid-customer-orders"></a>Hybrydowe zamówienia odbiorców

[!include [banner](includes/banner.md)]

Hybrydowe zamówienie odbiorcy to pojedyncze zamówienie zawierające produkty, które mogą być wyniesione ze sklepu przez odbiorcę, a także produktów, które zostaną odebrane lub wysłane później.

W programie Commerce można wybrać opcję wyniesienia wszystkich produktów lub wyniesienia tylko wybranych produktów dla zamówienia odbiorcy. Wiersze produktów oznaczone jako wynoszone są automatycznie fakturowane po utworzeniu zamówienia, podobnie jak w innym zamówieniu, którego towary mają być odbierane bezpośrednio po utworzeniu zamówienia. Wysokość kwoty należnej w zamówieniach hybrydowych jest określana przez dodanie procentu wpłaty do wierszy pobrania i wysłania produktów, a pełna kwota jest dodawana do wierszy wynoszonych produktów. W zamówieniach hybrydowych system przełącza się między trybami zamówienia odbiorcy i wyniesienia w następujący sposób:

- Jeżeli wszystkie produkty w koszyku są ustawione jako **Dostawa przez wyniesienie**, zamówienie będzie realizowane jako transakcja zapłaty przy kasie i wychodzenia z produktami ze sklepu.
- Jeśli wszystkie lub którekolwiek wiersze w koszyku są ustawiony na **Pobieranie** lub **Dostawa przez wysyłkę**, zamówienie będzie obsługiwane jako transakcja zamówienia odbiorcy.

Po zaznaczeniu wiersza koszyka i wybraniu opcji **Wybierz zaznaczone**, **Wyślij wybrane** lub **Wynieś wybrane** tylko wskazany wiersz koszyka będzie miał ustawianą określoną metodę dostawy. W takim przypadku dalszy przepływ operacji jest kontynuowany w zwykły sposób. Jednak jeśli opcja **Wybierz zaznaczone**, **Wyślij wybrane** lub **Wynieś wybrane** zostanie wybrana bez zaznaczenia wiersza koszyka, zostanie otwarta nowa strona z listą wszystkich wierszy koszyka. Na tym ekranie można wybrać wiele wierszy na raz i ustawić im metodę dostawy. Użycie tej metody do wybierania wierszy spowoduje zastąpienie wszystkich poprzednich metod dostawy przypisany do wierszy.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zamówienia odbiorców w aplikacji Modern POS (MPOS)](customer-orders-overview.md)
