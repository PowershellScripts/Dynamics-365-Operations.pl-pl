---
title: Aktualizacja kosztów standardowych w środowisku produkcyjnym
description: Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku produkcyjnym.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea810daab0ecdee59aba703f38d0001e2965f936
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434964"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Aktualizacja kosztów standardowych w środowisku produkcyjnym

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku produkcyjnym. 

Aktualizacje mogą odzwierciedlać nowe towary, kategorie kosztów lub wzory obliczania kosztów pośrednich. Mogą także wynikać z korekt i zmian kosztów. Typ aktualizacji wpływa na czynności, jakie trzeba wykonać w celu aktualizacji kosztów standardowych, co przedstawiono w poniższych przypadkach:

-   Wprowadzenie oczekiwanych zmian kosztów standardowych dla kupowanych towarów, a następnie w odpowiednim dniu zmiana stanu rekordów kosztów tych towarów na **Aktywne**. Nie obliczono jednak ponownie kosztów wytwarzanych towarów, które zużywają kupowane towary.
-   Wprowadzenie kosztów standardowych dla nowo kupowanych towarów bez ponownego obliczenia kosztów produkowanych towarów mających wersję listy składowej (BOM), w której nowo kupowane towary są składnikami.
-   Korekta lub zmiana kosztu kupowanego towaru albo zmiana grupy kosztów przypisanej do kupowanego towaru, a następnie obliczenie kosztu wszystkich produkowanych towarów mających wersję BOM, w której kupowany towar jest składnikiem.
-   Zmiana kosztu lub kategorii kosztu, a następnie obliczenie kosztu wszystkich produkowanych towarów mających wersję marszruty z operacjami marszruty wykorzystującymi kategorię kosztów.
-   Zmiana kategorii kosztów przypisanych do operacji marszruty albo grupy kosztów przypisanej do kategorii kosztów. Następnie obliczono koszt wszystkich produkowanych towarów mających wersję marszruty z operacjami marszruty wykorzystującymi kategorię kosztów.
-   Zmiana wzoru obliczania kosztów pośrednich i obliczenie kosztu wszystkich wyprodukowanych towarów, na które wpłynęła zmiana.
-   Zmiana lub dodanie oddziału, w którym wytworzono towar, i obliczenie kosztu wytworzenia dla określonego oddziału.
-   Obliczenie (lub ponowne obliczenie) kosztu produkowanego towaru, a następnie ponowne obliczenie kosztu wszystkich produkowanych towarów mających wersję BOM, w której kupowany towar jest składnikiem.
-   Obliczenie kosztów nowo produkowanego towaru na podstawie zdefiniowanej, zatwierdzonej i aktywnej listy BOM oraz informacji o marszrucie.

Każdy przykład wymaga specyficznego sposobu aktualizacji kosztów standardowych.



