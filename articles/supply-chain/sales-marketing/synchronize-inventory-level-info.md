---
title: Synchronizowanie informacji na poziomie zapasów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435106"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Synchronizowanie informacji na poziomie zapasów z rozwiązania Supply Chain Management do rozwiązania Field Service 

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania stanu dostepnych zasobów między rozwiązaniami Supply Chain Management i Field Service.

**Mapowanie szablonu w integracji danych**
- Zasoby produktu (rozwiązanie Supply Chain Management do rozwiązania Field Service)
  
**Zadani w projekcie integracji danych**
- Zapasy produktu

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować poziomy zapasów:
- Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service) 
- Synchronizowanie produktów Field Service z jednostką magazynową (z rozwiązania Supply Chain Management do rozwiązania Sales) 

## <a name="entity-set"></a>Zestaw jednostek

| Field Service                      | Zarządzanie łańcuchem dostaw                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | CDS Dostępne zapasy według magazynu     |

## <a name="entity-flow"></a>Przepływ jednostek
Informacje poziomu zapasów z Finance and Operations są wysyłane do Field Service dla wybranych produktów. Informacje poziomu zapasów obejmują: 
- Dostępna ilość (aktualnie zarejestrowana fizyczna ilość znajdująca się w magazynie)
- Ilość na zamówieniach (łączna ilość na zamówieniach sprzedaży)
- Zamówiona ilość (łączna ilość na zamówieniach zakupu)

Te informacje są rejestrowane według zwalnianych produktów dla każdego magazynu i synchronizowane w oparciu o śledzenie zmian, gdy poziomy zapasów się zmieniają.

W Field Service rozwiązanie integracji tworzy arkusze magazynowe dla różnicy, aby dopasować w Field Service z poziomami w Supply Chain Management.

Supply Chain Management będzie działać jako wzorzec poziomów zapasów. Dlatego ważne jest skonfigurowanie integracji dla zleceń, przeniesień i korekt z Field Service do Supply Chain Management, jeśli ta funkcja jest używana w Field Service, razem z synchronizacją poziomów zapasów z Supply Chain Management.

Produkty i magazyny, w których poziomy zapasów są wzorowane na Supply Chain Management mogą być kontrolowane za pomocą funkcji Zaawansowane zapytania i filtrowanie (Zapytanie zaawansowane).

> [!NOTE]
> Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie = Nie**), a następnie mapowania ich na jeden magazyn w Supply Chain Management z funkcją zaawansowanych zapytań i filtrów. Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Supply Chain Management. W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Supply Chain Management. Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
**Jednostka magazynowa Produkt zewnętrzny** jest używana tylko do integracji w systemach zaplecza. Ta jednostka odbiera wartości poziomu zapasów z Supply Chain Management w ramach integracji, a następnie przekształca te wartości na ręczne arkusze magazynowe, które następnie zmieniają produkty zapasów w magazynie.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="data-integration"></a>Integracja danych
Aby projekt działał, należy upewnić się, że klucz integracji został zaktualizowany dla msdynce_externalproductinventories.
1.  Przejdź do **Integracja danych > Zbiory połączeń**.
2.  Wybierz używany zbiór połączeń.
3.  Na karcie **klucz integracji** upewnij się, że następujące klucze zostały dodane do msdynce_externalproductinventories:
      - msdynce_productnumber (numer produktu)
      - msdynce_warehouseid (Identyfikator magazynu)
      
### <a name="data-integration-project"></a>Projekt integracji danych
Można zastosować filtry za pomocą funkcji Zaawansowane zapytanie i filtrowanie, aby tylko niektóre produkty i magazyny wysyłały informacji o poziomie zapasów z Supply Chain Management do Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Zapasy produkt (z rozwiązania Supply Chain Management do rozwiązania Field Service): Zapasy produktu

[![Mapowanie szablonu w integracji danych](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
