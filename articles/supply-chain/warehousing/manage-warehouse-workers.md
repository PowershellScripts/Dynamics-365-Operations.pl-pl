---
title: Zarządzanie pracownikami magazynu
description: Ten artykuł opisuje sposób korzystania z aplikacji magazynowej do zwiększania kontroli i monitorowania pracy, która jest wykonywana przez pracowników w magazynach.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage, WHSResetUserPassword
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2156b5de6abc3751cae1822b3825acbbd0b9a712
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435540"
---
# <a name="manage-warehouse-workers"></a>Zarządzanie pracownikami magazynu

[!include [banner](../includes/banner.md)]

Ten artykuł opisuje sposób korzystania z aplikacji magazynowej do zwiększania kontroli i monitorowania pracy, która jest wykonywana przez pracowników w magazynach.

Jeśli używasz funkcji zarządzania magazynem, wszystkie operacje pracownika magazynu są określane jako *praca*. Praca, taka jak pobieranie, przenoszenie i zliczanie dostępnych zapasów, jest rejestrowana przy użyciu urządzeń przenośnych. Zanim pracownik magazynu będzie mógł wykonać pracę, musi być powiązany z pracownikiem w dziale Zasoby ludzkie. Każde konto **pracownika** może mieć wielu powiązanych użytkowników pracy w magazynie. Ci użytkownicy pracy mogą pracować w różnych magazynach i mieć różne poziomy dostępu do rozmaitych menu urządzeń przenośnych. Użytkowników pracy w magazynie można traktować jak logowanie wielokrotne dla wybranego pracownika. Każdy użytkownik pracy w magazynie ma domyślny magazyn i określone przepływy pracy są używane w pozycjach menu dostępnych dla danego użytkownika pracy. 

Aby utworzyć nowego użytkownika pracy, kliknij **Pracownik** na stronie **Pracownicy** na karcie **Ogólne** w sekcji **Magazyny**. Trzeba określić identyfikator użytkownika, jego nazwę, domyślny magazyn oraz nazwę menu. To menu jest ładowane, gdy użytkownik zaloguje się w Portalu urządzeń przenośnych używanych w magazynie. Możesz zdefiniować, które elementy menu są dostępne dla użytkownika. 

W ramach konfiguracji dla każdego użytkownika pracy można również zdefiniować przepływy pracy dla określonego procesu. Na przykład można użyć pola **Jest kierownikiem ds. inwentaryzacji ciągłej**, aby określić, czy użytkownik może korygować rozbieżności inwentaryzacji ciągłej podczas liczenia lub czy te korekty muszą najpierw zostać przejrzane przez inną osobę.

## <a name="defining-labor-standards"></a>Definiowanie norm robocizny
Na stronie **Normy robocizny** można określić metody obliczania szacowanego czasu potrzebnego na wykonanie danego typu pracy. Tę definicję można ustawić na poziomie ogólnym lub szczegółowym. Można na przykład zdefiniować czas wymagany do odebrania zamówienia sprzedaży według wagi dla określonej definicji jednostki w konkretnym procesie odbierania. Jednocześnie można rejestrować czas na podstawie innej metody obliczania dla operacji odkładania dostępnych towarów, które są odbierane 

Aby włączyć zdefiniowane normy robocizny, trzeba wybrać opcję **Zezwalaj na normy robocizny** dla każdego magazynu w którym norm robocizny będą używane.

## <a name="monitoring-and-controlling-warehouse-work"></a>Monitorowanie i kontrolowanie pracy w magazynie
Na stronie **Cała praca** można monitorować i obsługiwać całą pracę, która została zaplanowana, jest w toku lub została ukończona. Na tej stronie można aktualizować różne procesy, takie jak przypisania pracowników do prac w magazynie i priorytety prac. Można też wyświetlać informacje szczegółowe związane z nagłówkiem i wierszami pracy w celu analizy oczekiwanych lub ukończonych procesów pracy. 

Po włączeniu opcji **Normy robocizny** można wyświetlić obliczoną prognozę czasu pracy. Następnie podczas przetwarzania pracy rzeczywisty czas będzie również wyświetlany dla każdej operacji pracy. W ten sposób można porównać prognozy obliczeń czasu z rzeczywistym czasem. 

Oprócz tego prognozę czasu można wykorzystać w regułach automatycznego dzielenia pracy podczas tworzenia pracy. W ten sposób można równoważyć obciążenia na podstawie spodziewanego czasu ukończenia zadań. 

Analiza czasu potrzebnego na wykonanie poszczególnych procesów pracy może ułatwić wprowadzanie usprawnień i poprawę wydajności pracy w magazynie. W tej analizie pomagają następujące raporty:

-   **Praca wg użytkownika** — pokazuje wydajność pracowników na podstawie rzeczywistych czasów względem oczekiwanych godzin.
-   **Praca wg typu transakcji pracy** — analizuje nieefektywność w procesach określonego magazynu. Na przykład zauważasz, że w danym tygodniu pobrania zamówień przeniesienia zajmują dłużej niż w poprzednich tygodniach. Na podstawie tej informacji możesz dalej zbadać to zjawisko.




