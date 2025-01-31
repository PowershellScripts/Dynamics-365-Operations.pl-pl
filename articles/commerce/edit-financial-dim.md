---
title: Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej
description: W tym temacie opisano sposób edytowania wymiarów finansowych dla transakcji sprzedaży detalicznej w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: e26bd4eb53fa44330f15c7cda004cb3d19dfec6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459751"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób edytowania wymiarów finansowych dla transakcji sprzedaży detalicznej w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Edytowanie wymiarów finansowych

Aby edytować wymiary finansowe dla transakcji sprzedaży detalicznej w centrali Commerce, wykonaj kroki opisane poniżej.

1. Otwórz stronę **Konfiguracja wymiarów finansowych dla aplikacji integrujących**.
1. Wybierz aktywny rekord **Integracja wymiarów domyślnych**.
1. Upewnij się, że na skróconej karcie **Wymiary finansowe** wszystkie wymiary, które chcesz edytować w arkuszu programu Excel, znajdują się na liście **Wybrane**. Aby uzyskać więcej informacji, zobacz [Jednostki danych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).
1. Pobierz i otwórz plik programu Excel ze strony **Zestawienia** lub **Transakcje sprzedaży detalicznej** albo kafelka **Weryfikacje transakcji zakończone niepowodzeniem** w obszarze roboczym **Finanse sklepu**.
1. Aby zmienić wymiar finansowy transakcji, wybierz pozycję **Projekt**, a następnie wybierz symbol ołówka obok wiersza **Transakcja (podlegająca inspekcji)**.
1. Znajdź i wybierz pole **FinancialDimensionDisplayValue**, zaznacz komórkę w części nagłówka arkusza programu Excel, a następnie wybierz pozycję **Dodaj etykietę**.
1. Zaznacz komórkę pod komórką wybraną w poprzednim kroku, wybierz opcję **Dodaj wartość**, a następnie wybierz opcję **Odśwież**. Wymiary finansowe zostaną dodane do arkusza programu Excel, po czym będzie można je edytować i publikować.
1. Aby zmienić wymiary w wierszach transakcji, zaznacz wiersz **Transakcje sprzedaży (podlegające inspekcji)**, wybierz symbol ołówka, a następnie powtórz kroki 6 i 7.
1. Aby zmienić wymiary w wierszach płatności, zaznacz wiersz **Transakcje płatności (podlegające inspekcji)**, wybierz symbol ołówka, a następnie powtórz kroki 6 i 7.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką](edit-cash-trans.md)

[Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy](edit-order-trans.md)

[Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych](create-excel-edit.md)

[Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych](add-fields-excel.md)
