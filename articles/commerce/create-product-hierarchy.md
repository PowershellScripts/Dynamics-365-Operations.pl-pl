---
title: Utwórz nową hierarchię produktu
description: W tym temacie opisano, jak dodać utworzyć nową hierarchię produktu w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 724ec2e5af7837d574298d662911cd9c6ee9e9f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414866"
---
# <a name="create-a-new-product-hierarchy"></a>Utwórz nową hierarchię produktu


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać utworzyć nową hierarchię produktu w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej. Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi). Każdy kanał sklepu detalicznego ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel. Wszystkie te elementy kanału sklepu detalicznego należy skonfigurować przed jego utworzeniem. 

Hierarchia produktów Commerce pozwala zdefiniować ogólną hierarchę produktów dla Twojej organizacji. Hierarchia produktu Commerce sprawdza się w merchandisingu, wycenach i promocjach, raportowaniu i planowaniu asortymentu. Dla każdej organizacji można przypisać tylko jedną hierarchię produktów Commerce.

## <a name="create-and-configure-a-product-hierarchy"></a>Tworzenie i konfiguracja hierarchii klasyfikacji produktów

Aby utworzyć i skonfigurować hierarchię produktów w Commerce, wykonaj następujące kroki.

1. W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Produkty i kategorie \> Hierarchia produktu w Commerce**.
1. Jeśli jeszcze nie hierachy, w **okienku akcji** wybierz opcję **nowy**, aby utworzyć katalog główny hierarchii.
1. W **Ogólne**:
    1. W polu **Nazwa** wprowadź nazwę.
    1. W polu **Opis** wprowadź opis.
    1. W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.
    1. Ustaw wartość **Aktywni** na **Tak**.

## <a name="add-hierarchy-nodes"></a>Dodaj węzły hierarchii

Aby dodać węzły hierarchii, wykonaj następujące kroki.

1. W okienku akcji kliknij pozycję **Edytuj hierarchię kategorii**.
1. Wybierz węzeł nadrzędny, do którego chcesz dodać nowy węzeł, a następnie wybierz **Nowa węzeł kategorii**.
1. W sekcji **Ogólne** należy podać **Nazwę**, **Opis**, **Wyświetlaną nazwę** i **Słowa kluczowe**.
1. W **Ogólne**:
    1. W polu **Nazwa** wprowadź nazwę.
    1. W polu **Opis** wprowadź opis.
    1. W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.
    1. W polu **Słowa kluczowe** wprowadź odpowiednie słowa kluczowe.
    1. W polu **Kolejność wyświetlania** wprowadź numer kolejności wyświetlania (opcjonalnie).
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Powtórz powyższe kroki, aby dodać kolejne węzły.

Poniższy rysunek przedstawia utworzenie nowego węzła hierarchii produktu.

![Utwórz hierarchię produktu](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Inne ustawienia

Grupy atrybutów kategorii można również przypisać do każdej grupy w zależności od potrzeb.  

## <a name="additional-resources"></a>Dodatkowe zasoby

[Hierarchie handlu](retail-hierarchies.md)

[Zarządzanie kategoriami produktów i produktami ](category-management-product-creation.md)

[Zmiana porządku sortowania dla podmiotów merchandisingowych](custom-order-categories-nav-retail-prod-hierarchy.md)
