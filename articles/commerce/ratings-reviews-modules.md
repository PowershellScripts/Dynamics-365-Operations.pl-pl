---
title: Moduły ocen i recenzji
description: W tym temacie opisano moduły ocen i recenzji używane na stronach szczegółów produktów w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 85fb1272103eed7d6e44635b7c20438471d96b34
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415042"
---
# <a name="ratings-and-reviews-modules"></a>Moduły ocen i recenzji

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły ocen i recenzji używane na stronach szczegółów produktów (PDP) w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Oceny i Recenzje w witrynach e-Commerce umożliwiają klientom zapoznanie się z produktami przed podjęciem decyzji o zakupie oraz stanowią mechanizm zbierania danych o opiniach klientów o tych produktach.. 

Oceny są wyświetlane na stronach list produktów, na stronach list kategorii, na stronach wyników wyszukiwania oraz na innych stronach witryny. 

Histogramy ocen i recenzje produktów są wyświetlane na stronach PDP. Przez naciśnięcie przycisku **Napisz recenzję** klienci mogą przesyłać oceny i recenzje produktu. Te funkcje PDP są kontrolowane przez moduły ocen i recenzji.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Moduły ocen i recenzji na stronach PDP 

Na stronach PDP w trzech modułach są wyświetlane podsumowania ocen i recenzji:
- Napisz moduł recenzji
- Moduł listy recenzji produktów
- Moduł histogramu ocen
 
Na poniższej ilustracji przedstawiono jak moduły ocen i recenzji wyglądają na stronach PDP.

![Moduły ocen i recenzji na stronach PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Aby uzyskać informacje na temat optymalizowania szablonów i układów PDP, tak aby można było udostępniać konfiguracje dla modułów ocen i recenzji na wielu stronach PDP w witrynie e-Commerce, należy zapoznać się z [Omówienie szablonów i układów](templates-layouts-overview.md).

Na poniższej ilustracji pokazano, jak w oknie dialogowym **Dodaj moduł** są prezentowane moduły ocen i recenzji w Dynamics 365 Commerce.
![Dodaj moduł okna dialogowego](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Napisz moduł recenzji

Moduł zapisu recenzji zawiera przycisk **Napisz recenzję**, który pozwala użytkownikom zalogować się, przypisać ocenę i napisać recenzję produktu. Moduł ten pozwala również edytować wcześniej przesłane oceny lub recenzje. Ten moduł zazwyczaj pojawia się nad histogramem ocen i modułami listy recenzji produktów na PDP.
Poniższa ilustracja pokazuje okno dialogowe **Napisz recenzję**, które pojawia się, gdy klient wybierze **Napisz recenzję**. Odbiorca może użyć tego okna dialogowego do przesłania ocen i recenzji.
![Napisz okno dialogowe recenzji](media/rnr-eCommerce-write-review-module.png) W poniższej tabeli przedstawiono właściwość modułu pisania recenzji, którą należy skonfigurować w narzędziu do tworzenia treści.
| Nazwa właściwości | Wartość        | Opis właściwości                 |
|---------------|--------------|--------------------------------------|
| Nazwisko          | Napisz recenzję | Nazwa modułu pisania recenzji. |

### <a name="ratings-histogram-module"></a>Moduł histogramu ocen

W module histogramu ocen jest wyświetlany histogram klasyfikacji. Ten moduł zwykle pojawia się między modułem recenzji zapisu a modułem listy recenzji produktów na PDP.
Moduł histogramu ocen nie wymaga konfiguracji. Wystarczy dodać moduł do szablonu PDP. Poniższe ilustracje pokazują, jak wygląda szablon PDP w Dynamics 365 Commerce, gdy moduły ocen i recenzji są skonfigurowane do wyświetlania na PDP.
![Szablon PDP, gdy oceny i recenzje są skonfigurowane do wyświetlania na PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Moduł listy recenzji produktów

Moduł listy recenzji produktów pokazuje listę recenzji produktów wraz z opcjami sortowania, filtrowania i paginacji. Ten moduł zazwyczaj znajduje się po module histogramu ocen na PDP.
Poniższa tabela pokazuje właściwości modułu listy recenzji produktów, które należy skonfigurować w narzędziu do tworzenia treści.

| Nazwa właściwości              | Wartość | Opis właściwości |
|----------------------------|-------| ---------------------|
| Recenzje pokazywane na każdej stronie | 10    | Liczba recenzji, które powinny być pokazywane jednocześnie na PDP. Przyciski **Następne** i **Poprzednie** są dołączone, dzięki czemu użytkownicy mogą poruszać się po stronach recenzji. |

#### <a name="ratings-histogram--summary-view"></a>Histogram ocen — Widok podsumowania

Moduł listy recenzji produktów zawiera miejsce, w którym można dodać moduł histogramu ocen. Poniższa ilustracja pokazuje, jak można dodać moduł histogramu ocen w module listy recenzji produktów w Dynamics 365 Commerce.

![Dodawanie modułu histogramu ocen w module listy recenzji produktów](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
