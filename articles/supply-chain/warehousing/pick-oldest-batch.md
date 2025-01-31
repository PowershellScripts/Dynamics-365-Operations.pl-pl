---
title: Pobieranie najstarszej partii na urządzeniu przenośnym
description: W tym temacie opisano sposób konfigurowania i stosowania opcji pobierania najstarszej partii z urządzenia przenośnego.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f235c34d6369c6f0584a7bac1c1be75f3d84c9c0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435103"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>Pobieranie najstarszej partii na urządzeniu przenośnym

[!include [banner](../includes/banner.md)]

Dostęp do konfiguracji **Pobierz z najstarszej partii** można uzyskać z menu urządzenia przenośnego, a następnie ustawić w niej wymuszanie lub ostrzeganie pracowników magazynu, aby pobierali najstarszą partia w swojej obecnej lokalizacji.  

## <a name="where-it-applies"></a>Zastosowanie
Funkcjonalność pobierania najstarszej partii jest konfigurowana w menu urządzenia przenośnego i wpływa na pobieranie towarów w partiach poniżej.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Konfigurowanie pobierania najstarszej partii 
Dla towarów skonfigurowanych do wykorzystywania istniejącej pracy w opcji **Pobierz z najstarszej partii** na urządzeniu komórkowym można ustawić wartość **Brak**, **Ostrzegaj** lub **Wymuszaj**.

**Brak**: Pracownicy nie będą dostawać żadnych komunikatów i mogą pobierać dowolne partie w swoich lokalizacjach.

**Ostrzegaj** i **Wymuszaj**: Gdy pracownik zaznaczy partię, nad formantem partii będzie wyświetlana lista partii z najstarszymi datami ważności. Jeśli lokalizacja jest kontrolowana przez numer identyfikacyjny, nad formantem numeru identyfikacyjnego zostanie wyświetlona lista numerów identyfikacyjnych z najstarszymi partiami. 
-   **Ostrzeganie**: Jeśli pracownik wybierze numer identyfikacyjny lub partię, która nie znajduje się na wyświetlanej liście, formant będzie wygaszony i pojawi się ostrzeżenie, że istnieje starsza partia do wybrania. Aby móc kontynuować pracę, pracownik może ponownie wybrać ten sam numer identyfikacyjny lub partię.  
-   **Wymuszaj**: Pracownicy będą cały czas otrzymywać komunikat, że istnieje starsza partia do pobrania.
