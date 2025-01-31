---
title: Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań
description: Ten temat skupia się na planowaniu zlecenia pracy przy użyciu funkcji planowania operacji i planowania zadań.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a69339bc678de8343dbf2646a4d6fe0ace9964c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435182"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań

[!include [banner](../../includes/banner.md)]

Ten temat skupia się na planowaniu zlecenia pracy przy użyciu funkcji planowania operacji i planowania zadań. Funkcja planowania operacji nie powoduje utworzenia żadnych zadań, natomiast zadania są tworzone przy użyciu funkcji planowania zadań. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla kierownika produkcji, planisty produkcji lub kierownika zakładu produkcyjnego w środowisku wytwarzania dyskretnego.


## <a name="create-a-production-order"></a>Tworzenie zlecenia produkcyjnego
1. W okienku nawigacji przejdź po **Moduły > Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne**.
2. Wybierz **Nowe zlecenie produkcyjne**.
3. W polu **Kod towaru** wpisz lub wprowadź wartość. Wybierz towar o numerze **D0001**.  
4. Wybierz opcję **Utwórz**.

## <a name="schedule-operations-for-the-production-order"></a>Planowanie operacji dla zlecenia produkcyjnego
1. Umożliwia oznaczenie nowo utworzonego wiersza.      
2. W okienku akcji wybierz **Harmonogram**.
3. Wybierz **Planowanie operacji**.
4. W polu **Kierunek planowania** wybierz opcję **W przód od daty planowania**.
5. W polu **Data planowania** wprowadź datę. Wybierz przyszłą datę, na przykład dziś plus jeden tydzień. Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.  
6. Kliknij przycisk **OK**.
7. Na liście oznacz wybrany wiersz. Zwróć uwagę, że stan zmienił się na **Zaplanowane**. 
8. Wybierz **Wszystkie zadania**. Należy zauważyć, że planowanie operacji nie powoduje tworzenia żadnych zadań.  
9. Zamknij stronę.

## <a name="schedule-jobs-for-the-production-order"></a>Planowanie zadań dla zlecenia produkcyjnego
1. W okienku akcji wybierz **Harmonogram**.
2. Wybierz **Planowanie zadań**.
3. W polu **Kierunek planowania** wybierz opcję **W przód od daty planowania**.
4. W polu **Data planowania** wprowadź datę. Wybierz datę w przyszłości, na przykład dziś plus jeden tydzień. Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.  
5. Kliknij przycisk **OK**.
6. W okienku akcji kliknij opcję **Zlecenie produkcyjne**.
7. Wybierz **Wszystkie zadania**. Należy zauważyć, że na podstawie aktywnej marszruty planowanie zadań tworzy 5 zadań.  

