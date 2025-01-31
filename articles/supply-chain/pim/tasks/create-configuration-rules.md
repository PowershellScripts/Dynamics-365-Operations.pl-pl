---
title: Tworzenie reguł konfiguracji
description: W tej procedurze zostaną utworzone reguły konfiguracji, które mogą być używane w konfiguracjach opartych na wymiarach do wymuszania lub blokowania niektórych kombinacji wierszy BOM.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bc0af4d95e9430d0b5c8b7fc9a4ade076802044
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435227"
---
# <a name="create-configuration-rules"></a>Tworzenie reguł konfiguracji

[!include [banner](../../includes/banner.md)]

W tej procedurze zostaną utworzone reguły konfiguracji, które mogą być używane w konfiguracjach opartych na wymiarach do wymuszania lub blokowania niektórych kombinacji wierszy BOM. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to siódma z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach.

1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Listy składowe (BOM) i formuły > BOM.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Znajdź i zaznacz listę składową konfiguracji opartej na wymiarach.  
3. W okienku akcji kliknij pozycję Opcje.
4. Kliknij przycisk Zmień widok.
5. Kliknij opcję Widok nagłówka.
    * Otwórz widok nagłówka, aby przejść do skróconej karty Marszruta konfiguracji.  
6. Rozwiń lub zwiń sekcję Marszruta konfiguracji.
    * Skrócona karta Marszruta konfiguracji musi być w trybie rozwiniętym.  
7. Kliknij opcję Reguły konfiguracji.
8. Kliknij przycisk Nowy.
9. Na liście oznacz wybrany wiersz.
10. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Są wyświetlane towary należące do bieżącej grupy konfiguracji. Wybierz ten, który reprezentuje warunek w regule.  
11. Na liście kliknij łącze w wybranym wierszu.
12. W polu Metoda wybierz opcję.
    * Istnieje możliwość wymuszenia wyboru lub anulowania wyboru towaru z innej grupy konfiguracji.  
13. W polu Grupa pochodna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz żądaną grupę konfiguracji.  
16. W polu Pochodny kod towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
17. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz numer towaru, który zostanie zaznaczony lub którego zaznaczenie zostanie anulowane, zależnie od wybranej metody.  
18. Zamknij stronę.

