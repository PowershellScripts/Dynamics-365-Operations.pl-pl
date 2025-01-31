---
title: Konfigurowanie ksiąg amortyzacji
description: Ta procedura prowadzi proces tworzenia nowej księgi amortyzacji i kojarzy ją z grupą środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03f915fa91e0eeff2f26ab9a60bbd5118317e853
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446871"
---
# <a name="set-up-depreciation-books"></a>Konfigurowanie ksiąg amortyzacji 

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi proces tworzenia nowej księgi amortyzacji i kojarzy ją z grupą środków trwałych. 

## <a name="create-a-depreciation-book"></a>Tworzenie księgi amortyzacji
1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Księgi amortyzacji.
2. Kliknij przycisk Nowy.
3. W polu Księga amortyzacji wpisz wartość.
4. Wypełnij pole Opis.
5. Zaznacz pole wyboru Oblicz amortyzację lub usuń jego zaznaczenie.
6. W polu Profil amortyzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni profil amortyzacji.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Amortyzacja alternatywna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście zaznacz odpowiedni profil amortyzacji.
11. Na liście kliknij łącze w wybranym wierszu.
    * Profil Amortyzacja dodatkowa będzie używany na potrzeby dodatkowej amortyzacji składnika aktywów w nadzwyczajnych okolicznościach. Na przykład może to służy do zarejestrowania amortyzacji powstałej w wyniku klęski żywiołowej.  
12. Zaznacz lub wyczyść pole wyboru Tworzenie korekt amortyzacji przy korektach podstawy.
13. W polu Kalendarz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Na liście kliknij łącze w wybranym wierszu.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Kojarzenie księgi amortyzacji z grupą środków trwałych
1. Kliknij opcję Grupy środków trwałych.
2. W polu Grupa środków trwałych kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Konwencja amortyzacji wybierz opcję.
6. W polu Okres użytkowania wpisz liczbę.
    * Należy zauważyć, że wartość pola Okresy amortyzacji jest obliczana po ustawieniu okresu użytkowania.  

