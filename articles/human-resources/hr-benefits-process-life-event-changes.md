---
title: Przetwarzanie wybranych zmian sytuacji życiowej
description: W programie Microsoft Dynamics 365 Human Resources można przetwarzać zmiany sytuacji życiowej.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39d1e94347809a1756fc4f66e5edc345c70eaf39
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420018"
---
# <a name="process-life-event-changes"></a>Przetwarzanie wybranych zmian sytuacji życiowej

W programie Microsoft Dynamics 365 Human Resources można przetwarzać dwa rodzaje zmian sytuacji życiowej:

- Zmiany związane z narodzinami
- Zmiany wygaśnięcia zastąpienia reguły uprawnienia 

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie zmian zdarzeń sytuacji życiowej**.

2. W oknie dialogowym **Uruchom proces zmian zdarzenia zmiany sytuacji życiowej** określ wartości następujących pól:

   | Pole | Opis |
   | --- | --- |
   | Okres rejestracji | Okres rejestracji, dla którego mają być przetwarzane zmiany sytuacji życiowej. |
   | Firma | Firma, dla której mają być przetwarzane zmiany sytuacji życiowej. |

3. Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:

   1. Umożliwia wprowadzanie informacji o przetwarzaniu.

   2. Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.

   3. Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.

   4. Kliknij przycisk **OK**. Proces będzie uruchamiany z parametrami określonymi przez użytkownika.

4. Kliknij przycisk **OK**.
