---
title: Inicjowanie poziomów zapasów w magazynie
description: W tej procedurze pokazano, jak ręcznie zaktualizować dostępne zapasy przy użyciu arkusza przesunięć zapasów (można również aktualizować dostępne zapasy przez importowanie transakcji w jednostkach danych).
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03481ddc5bd12b3459b69d65b1cfaeb23c60dfd4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435485"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a>Inicjowanie poziomów zapasów w magazynie

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak ręcznie zaktualizować dostępne zapasy przy użyciu arkusza przesunięć zapasów (można również aktualizować dostępne zapasy przez importowanie transakcji w jednostkach danych). (Można również aktualizować dostępne zapasy, importując transakcje w jednostkach danych). Zadania z przewodnika można wykonać na danych firmy demonstracyjnej USMF, gdzie wszystkie warunki wstępne, takie jak nazwa arkusza, ustawienia towaru, profile księgowania i konta, są dostępne. Przewodnik proponuje określone wartości dla używanego towaru i wymiarów. Jeśli wybierzesz inny towar, może być konieczne wprowadzenie wartości dla innych wymiarów.

1. Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Przesunięcie.
2. Kliknij przycisk Nowy.
3. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Wybierz opcję IMov.
    * Najlepiej korzystać z różnych szablonów nazw arkuszy do różnych celów służbowych.  
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Konto przeciwstawne wpisz wartość „140200”.
    * To jest konto przeciwstawne, które będzie kontem domyślnym w wierszach arkusza. Istnieje możliwość zastąpienia wartości domyślnej, aby przypisać różne konta przeciwstawne poszczególnym wierszom.  
7. Kliknij przycisk OK.
8. Kliknij przycisk Nowy.
9. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Wybierz towar A0001.
11. Na liście kliknij łącze w wybranym wierszu.
12. Kliknij kartę Wymiary magazynowe.
13. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Wybierz oddział 1.
15. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
16. Wybierz magazyn 13.
17. Na liście kliknij łącze w wybranym wierszu.
18. W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. Wybierz lokalizację 13.
20. Wprowadź liczbę w polu Ilość.
21. Kliknij przycisk Zapisz.
22. Kliknij przycisk Księguj.
23. Zaznacz lub usuń zaznaczenie pola wyboru Przenoszenie wszystkich błędów księgowania do nowego arkusza.
    * Jeśli ta opcja jest włączona, wszystkie wiersze, których księgowanie się nie powiedzie, będą kopiowane do nowego arkusza. Informacje w dzienniku mogą służyć do rozwiązywania problemów i ponownego księgowania wierszy.  
24. Kliknij przycisk OK.
25. Zamknij stronę.
26. Zamknij stronę.

