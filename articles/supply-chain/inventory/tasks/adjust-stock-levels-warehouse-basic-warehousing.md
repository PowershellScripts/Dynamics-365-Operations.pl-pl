---
title: Korygowanie poziomów zapasów w magazynie (podstawowe magazynowanie)
description: Ta procedura prowadzi przez proces tworzenia i księgowania arkusza korekt zapasów w celu skorygowania poziomów zapasów produktów w magazynie.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9678dffd84e9e4032510811731a67da953b40431
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435494"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Korygowanie poziomów zapasów w magazynie (podstawowe magazynowanie)

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi przez proces tworzenia i księgowania arkusza korekt zapasów w celu skorygowania poziomów zapasów produktów w magazynie. Przed rozpoczęciem tego zadania trzeba mieć skonfigurowany arkusz zapasów dla korekt zapasów. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Te zadania zazwyczaj wykonuje pracownik magazynu.


## <a name="create-an-inventory-adjustment-journal"></a>Tworzenie arkusza korekt zapasów
1. Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Korekta zapasów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij nazwę arkusza korekty zapasów, który ma być używany.
    * Niektóre inne pola zostaną wypełnione zgodnie z ustawieniami wybranego arkusza korekty zapasów.  
5. Kliknij przycisk OK.

## <a name="create-journal-lines"></a>Tworzenie wierszy arkusza
1. Kliknij przycisk Nowy.
2. Na liście zaznacz pole numeru towaru.
3. W polu Numer towaru zaznacz towar. Jeśli używasz danych firmy demonstracyjnej USMF, wpisz „D0001”.
4. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście zaznacz oddział.
6. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście zaznacz magazyn.
    * Jeśli wybrano towar z lokalizacją jako wymaganym wymiarem, trzeba określić lokalizację w tym miejscu.  
8. Wprowadź liczbę w polu Ilość.
    * Pole kosztu własnego określa koszt jednostkowy dla przyjęć na magazyn. Jeśli koszt nie został określony dla danego numeru towaru lub musi zostać ręcznie zmodyfikowany, należy to zrobić w tym miejscu.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Sprawdzanie poprawności i księgowanie arkusza korekt zapasów
1. Kliknij przycisk Sprawdź poprawność.
2. Kliknij przycisk OK.
3. Kliknij przycisk Księguj.
    * Podczas księgowania arkusza tego rodzaju księgowane jest przyjęcie do magazynu lub wydanie z magazynu, zmieniane są poziom i wartość zapasów oraz generowane są transakcje finansowe.  
4. Kliknij przycisk OK.
5. Zamknij formularz.
6. Zamknij stronę.

