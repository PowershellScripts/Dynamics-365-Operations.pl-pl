---
title: Planowanie zlecenia pracy według konkretnej daty i godziny
description: W tym temacie opisano sposób zaplanować zlecenie pracy na określony dzień i czas w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e81ea13a3463965c6e4785dac32f536d2e94a7ba
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435125"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Planowanie zlecenia pracy według konkretnej daty i godziny

[!include [banner](../../includes/banner.md)]

 

Jeśli zlecenie pracy musi być zaplanowane w określonym dniu *i* o określonej godzinie, można zastąpić standardowy proces planowania w module Zarządzanie składnikami majatku i utworzyć określony harmonogram dla zlecenia pracy.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Na liście zleceń pracy kliknij identyfikator zlecenia pracy w kolumnie **Zlecenie pracy**.

3. Kliknij przycisk **Edytuj**.

4. Na karcie skróconej **Nagłówek zlecenia pracy** wstaw daty rozpoczęcia i zakończenia oraz godziny w polach **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie**.

    ![Rysunek 1](media/05-work-order-scheduling.png)

5. Na karcie **Ogólne** kliknij opcję **Planowanie**, aby użyć standardowego procesu planowania, lub kliknij przycisk **Wysyłanie**, jeśli chcesz przypisać zlecenie pracy dla określonego pracownika.

6. W celu zastąpienia istniejących rezerwacji zdolności produkcyjnych w celu zapewnienia, że zlecenie pracy jest planowane w oczekiwanym okresie, należy wybrać opcje tak, jak to pokazano na poniższym rysunku w oknie dialogowym **Planowanie zlecenia pracy** > sekcja **Ograniczone zdolności produkcyjne**. Oznacza to, że proces planowania ignoruje istniejące rezerwacje zdolności produkcyjnych, ponieważ zlecenie pracy musi rozpocząć się w oczekiwanej godzinie rozpoczęcia.

    ![Rysunek 2](media/06-work-order-scheduling.png)

7. Kliknij przycisk **OK**, aby rozpocząć planowanie.

8. Jeśli proces planowania powoduje utworzenie podwójnych rezerwacji, na ekranie pojawi się komunikat i można dostosować powiązane z nim zlecenia pracy.

>[!NOTE]
>Aby zaplanować pracownika obsługi dla zlecenia pracy, pracownik obsługi musi być dostępny w oczekiwanej dacie i godzinie rozpoczęcia. Dostępność pracownika jest ustawiana w [kalendarzu pracownika](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 

