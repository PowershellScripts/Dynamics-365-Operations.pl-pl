---
title: Potwierdzenie produktu na potrzeby pobierania dla grupy
description: W tym temacie opisano, jak skonfigurować weryfikowanie towarów w połączeniu z pobieraniem dla grupy.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272c3a13b68e2b862faf20cc269ca790322b61de
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435262"
---
# <a name="product-confirmation-for-cluster-picking"></a>Potwierdzenie produktu na potrzeby pobierania dla grupy

[!include [banner](../includes/banner.md)]

Funkcjonalność pobierania dla grupy umożliwia pobieranie towarów równocześnie dla kilku zamówień. W przypadku stosowania pobierania dla grupy bardzo ważne jest potwierdzanie towarów dodawanych do grup. Weryfikowanie może się odbywać w trakcie procesu pobierania dla grup.

## <a name="where-it-applies"></a>Zastosowanie

Weryfikacja towarów w pobieraniu dla grupy działa tak samo, jak w zwykłych procesach pobierania. Konfiguracja zależy od ustawień kodów kreskowych produktów.

## <a name="set-up-item-verification-with-cluster-picking"></a>Konfigurowanie weryfikowania towarów w trakcie pobierania dla grupy

1. Na urządzeniu przenośnym w menu otwórz formularz ustawień potwierdzenia pracy: **Zarządzanie magazynem** > **Zarządzanie magazynem** > **Ustawienia** > **Urządzenie przenośne** > **Elementy menu urządzenia przenośnego**.
1. Na urządzeniu przenośnym w menu otwórz pozycję **Konfiguracja potwierdzenia pracy**.

|        Opcja        |                                    opis                                    |
|----------------------|-----------------------------------------------------------------------------------|
| Potwierdzenie produktu | Umożliwia weryfikowanie każdego artykułu w zapasach z urządzenia przenośnego podczas skanowania. |
