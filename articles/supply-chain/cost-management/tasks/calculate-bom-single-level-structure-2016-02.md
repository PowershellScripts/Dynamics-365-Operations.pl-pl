---
title: Obliczanie BOM przy użyciu struktury jednopoziomowej (luty 2016)
description: W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu jednopoziomowego rozłożenia opartego na arkuszu wyceny.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83a62966e343a9b1c073c2d6ec1c1b69b1daddbb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435301"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Obliczanie BOM przy użyciu struktury jednopoziomowej (luty 2016)

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu jednopoziomowego rozłożenia opartego na arkuszu wyceny. Jest to szóste zadanie w serii zadań obliczania BOM. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.

1. Przejdź do okna Zwolnione produkty.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz produkt BOM_1.  
3. W okienku akcji kliknij pozycję Zarządzanie kosztami.
4. Kliknij opcję Cena pozycji.
5. Kliknij opcję Oblicz koszt pozycji.
    * Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.  
6. W polu Wersja wyceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * W tej demonstracji wybierz opcję 10. Jest to ta sama wersja wyceny, jak używana w celu dodania kosztu własnego do składników.  
7. Kliknij przycisk OK.
8. Kliknij opcję Wyświetl szczegóły obliczeń.
    * Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.    Oto elementy składowe kosztu:  *   10 pochodzi z opcji ITEM_A, 10 z opcji ITEM_B i 10 z opcji BOM_2. W tym przypadku opcja BOM_2 nie ma żadnych szczegółów, ponieważ tę wartość ręcznie wpisano jako koszt standardowy 10, tzn. nie jest to wynik obliczenia.  *  Wartość 7 została ustalona na podstawie czasu przezbrajania i jest kosztem stałym, a dodatkowa wartość 7 została ustalona na podstawie czasu procesu (wykonywania operacji).  *   Istnieją również inne kwoty, które odpowiadają kosztom pośrednim.  
9. @SysTaskRecorder:_RequestClose

