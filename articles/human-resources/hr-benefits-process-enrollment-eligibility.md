---
title: Przetwórz uprawnienia do świadczeń
description: W tym artykule opisano sposób uruchamiania procesu uprawnień do rejestracji.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfb7f13dce48f33c111af491918702763f7e3b8a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420021"
---
# <a name="process-enrollment-eligibility"></a>Przetwórz uprawnienia do świadczeń

W tym artykule opisano sposób uruchamiania procesu uprawnień do rejestracji.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie uprawnień do świadczeń**.

2. W oknie dialogowym **Uruchamianie procesu uprawnień do rejestracji świadczenia** określ wartości następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Okres rejestracji** | Okres rejestracji służący do przetworzenia uprawnień do rejestracji. |
   | **Firma** | Jednostka prawna służąca do przetworzenia uprawnień do rejestracji. |
   | **Pracownik** | Pracownik służący do przetworzenia uprawnień do rejestracji. Jeśli to pole pozostanie puste, uprawnienia do rejestracji będą przetwarzane dla wszystkich pracowników. |
   | **Plan świadczeń** | Plan świadczeń służący do przetworzenia uprawnień do rejestracji.

3. Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Umożliwia wprowadzanie informacji o przetwarzaniu.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces będzie uruchamiany z parametrami określonymi przez użytkownika.

4. Kliknij przycisk **OK**.

## <a name="view-process-results"></a>Wyświetlanie wyników procesu

W tym artykule opisano sposób wyświetlania wyników procesu.

1.  W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Wyniki procesu**.

2.  W formularzu **Wyniki procesu** są określone następujące pola:

   | Pole | opis |
   | --- | --- |
   | **Identyfikator procesu** | Unikatowy identyfikator połączony Pracownika, Firmy i przebiegu procesu. |
   | **Typ procesu** | Identyfikuje proces, który został uruchomiony. Na przykład:  Rejestracja. |
   | **Sygnatura czasowa** | Godzina, o której ma być uruchomiony proces kwalifikowania. |
   | **Firma** | Firma określona w procesie rejestracji. |
   | **Pracownik** | Pracownik, który został przetworzony. |
   | **Plan | Plan świadczeń, dla którego podjęto próbę rejestracji. |
   | **Reguła uprawnienia** | Przetworzona reguła uprawnień. Jeśli wystąpił błąd przed uruchomieniem uprawnień, to pole będzie puste. Na przykład: Jeśli wynagrodzenie nie zostało zdefiniowane dla pracownika, proces kwalifikowania nie zostanie uruchomiony, a to pole zostanie pozostawione puste. |
   | **Stan wyniku** | Ta opcja będzie Uprawniona lub Niekwalifikująca się. Stan wyniku jest nieuprawniony, jeśli pracownik nie spełnił kryteriów reguły uprawnień, jeśli pracownik nie dostarczył wymaganych informacji, takich jak częstotliwość płac lub stałe wynagrodzenie, lub jeśli w planie świadczeń brakuje informacji, co uniemożliwia zarejestrowanie się pracowników. |
   | **Komunikat wyniku** | Wskazuje, dlaczego pracownik nie kwalifikuje się do planu świadczeń lub jeśli została przekazana reguła uprawnienia. |

