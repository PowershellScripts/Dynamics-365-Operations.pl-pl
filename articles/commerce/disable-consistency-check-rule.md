---
title: Wyłącz reguły w sprawdzaniu spójności transakcji sprzedaży detalicznej
description: W tym temacie opisano funkcje wyłączania reguł sprawdzania spójności transakcji sprzedaży wprowadzone w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 37209f1c1de19335f5f9fa6636ab55dd8b2fccc1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459719"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Wyłącz reguły w sprawdzaniu spójności transakcji sprzedaży detalicznej 

[!include [banner](../includes/banner.md)]

Sieci handlowe mogą mieć unikatowe dla nich scenariusze i procesy biznesowe. Z tego względu nie wszystkie domyślnie zainstalowane w sprawdzaniu spójności transakcji handlowych reguły są dostępne dla wszystkich sieci handlowych. W celu uwzględnienia różnic rozwiązanie Microsoft Dynamics 365 Commerce oferuje funkcje, których można użyć do wyłączenia nie mających zastosowania reguł.

Aby wyświetlić listę reguł dostępnych w sprawdzaniu spójności transakcji sprzedaży detalicznej w swoim środowisku i zobaczyć stan każdej reguły, przejdź do pozycji **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce** i wybierz kartę **Weryfikacja transakcji**.

Domyślnie stan każdej reguły jest ustawiony na **Włączone**. Z tego względu wszystkie reguły są używane do weryfikacji transakcji przed pobraniem ich do zestawień handlowych. Aby wyłączyć regułę, zmień jej stan na **Wyłączone**. Wyłączone reguły nie są brane pod uwagę, gdy transakcje są weryfikowane w trakcie procesu obliczania zestawień.

Aby pominąć cały proces weryfikacji bez względu na włączone reguły, przejdź do **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry Commerce**, a następnie w karcie **Weryfikacja transakcji** ustaw opcję **Wyłącz sprawdzanie spójności transakcji Commerce** na wartość **Tak**. Po ustawieniu tej opcji na **Nie** nie można ponownie ustawić jej na **Tak** w interfejsie użytkownika.
