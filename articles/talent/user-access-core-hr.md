---
title: Użytkownik ma dostęp do aplikacji Human Resources, ale nie do aplikacji Onboard albo Attract
description: W tym temacie opisano, jak rozwiązać ten problem polegający na tym, że użytkownik może uzyskać dostęp do Microsoft Dynamics 365 Talent — Human Resources, ale nie ma dostępu do Attract lub aplikacji Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462216"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a>Użytkownik ma dostęp do aplikacji Human Resources, ale nie do aplikacji Onboard albo Attract

[!include [banner](includes/banner.md)]

**Szczegóły środowiska**

- Wdrożenie programu Microsoft Dynamics Lifecycle Services (LCS) zostało przeprowadzone przez użytkownika A.
- Użytkownik A dodał użytkownika B jako użytkownika do Microsoft Dynamics 365 Human Resources.

**Wystawienie**

Użytkownik B ma dostęp do aplikacji Human Resources, ale nie ma dostępu do Talent: Attract ani aplikacji Talent: Onboard. Kiedy użytkownik próbuje przejść do **aplikacji Experience**, jest zamiast tego kierowany do środowiska wersji próbnej.

**Rozwiązanie**

Użytkownik B musi mieć przypisane uprawnia wyświetlenia środowiska Microsoft Power Apps utworzonego przez użytkownika A w procesie przypisywania.

Aby uzyskać informacje, zobacz sekcję „Przyznawanie dostępu do środowiska” w [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Rozwiązanie długoterminowe**

Microsoft rozważa automatyczne przypisywanie odpowiednich praw do Onboard i Attract podczas dodawania użytkownika do Human Resources.
