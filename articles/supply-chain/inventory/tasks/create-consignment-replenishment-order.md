---
title: Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych
description: Ten temat pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych.
author: mkirknel
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e993190150e2d82088390d8db4b7c5ada2b0161
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435629"
---
# <a name="create-a-consignment-replenishment-order"></a>Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych

[!include [banner](../../includes/banner.md)]

Ten temat pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych. Prezentuje także sposób rejestrowania przyjęcia produktów, tak aby zapasy konsygnacyjne zostały zarejestrowane jako zapasy dostępne będące własnością dostawcy. Zazwyczaj procedurę wykonuje pracownik działu zaopatrzenia. Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.

## <a name="create-a-consignment-replenishment-order"></a>Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych
1. W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Konsygnacja > Zamówienia uzupełnienia zapasów konsygnacyjnych**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto dostawcy** wybierz dostawca **US-104** (należy wybrać dostawcę, który jest zarejestrowany jako właściciel na stronie **właściciele zapasów**). 
4. Kliknij przycisk **OK**.
5. Wybierz **Dodaj wiersz**.
6. W polu **Kod pozycji** wpisz typ `M9211CI` (należy wybrać towar skonfigurowany dla zapasów konsygnacyjnych).
7. W polu **Ilość** wpisz liczbę.
8. W polu **Wymagana data dostawy** wpisz datę. Daty wymagalności i potwierdzona są używane przez aparat systemu MRP dla planowanego przybycia towarów.  
9. W polu **Potwierdzona data dostawy** wpisz datę.
10. Rozwiń sekcję **Szczegóły wiersza**.
11. Wybierz kartę **Wymiary magazynowe**.
12. Aby pokazać właściciela w polu **Właściciel wymiarów magazynowych**, odśwież stronę. Dostawca US-104 jest teraz wymieniony jako właściciel.  

## <a name="check-the-inventory-transaction-status"></a>Sprawdzanie stanu transakcji magazynowej
1. Wybierz **Zapasy**.
2. Wybierz **transakcje**.
3. W pożądanym wierszu, należy zauważyć, że pole **Przyjęcie** jest ustawione na **Zamówione**.  
4. Zamknij stronę.

## <a name="receive-items"></a>Odbierz pozycje
1. Wybierz pozycję **Przyjęcie produktu**.
2. W polu **Zewnętrzny dokument przyjęcia** produktów wpisz wartość.
3. W polu **Ilość** wprowadź liczbę, która jest niższa niż liczba wyświetlana w tym miejscu. 
4. Kliknij przycisk **OK**.

## <a name="check-the-on-hand-inventory"></a>Sprawdzanie dostępnych zapasów
1. Wybierz **Zapasy**.
2. Wybierz **Dostępne**.
3. Wybierz **Przegląd**. Towary, które zostały przyjęte jako zapasy konsygnacyjne będące własnością dostawcy, są dostępne. Pozostała ilość w zamówieniu uzupełnienia zapasów konsygnacyjnych jest wyświetlana w polu **Zamówione w sumie**.  
4. Zamknij stronę.

