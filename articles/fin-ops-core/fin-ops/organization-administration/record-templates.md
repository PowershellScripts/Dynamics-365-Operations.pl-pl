---
title: Omówienie szablonów rekordów
description: Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0b55046e6c523398b4a30e674dc9f77bb6fedf3
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693215"
---
# <a name="record-templates-overview"></a>Omówienie szablonów rekordów

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje.

Szablony rekordów ułatwiają szybkie tworzenie rekordów, jednak można tworzyć szablony rekordów dla niektórych typów rekordów.

Na przykład załóżmy, że wprowadzasz dane wynajmu dla wypożyczali samochodów w San Francisco. Ponieważ większość klientów będzie prawdopodobnie pochodziła z San Francisco, byłoby dobrze, gdy pola **Stan**, **Kraju** i **Miasto** na formularzu wynajmu mogły wypełniać się automatycznie

> [!NOTE]
> Użytkownicy mogą stosować szablony wyłącznie w odniesieniu do segmentów, do których mają dostęp. Jednak wszystkie tytuły szablonów są dla Ciebie widoczne podczas tworzenia nowego rekordu, a także dla innych użytkowników w przypadku tworzenia szablonów, które będą dostępne dla wszystkich użytkowników. Należy to wziąć pod uwagę podczas nadawania nazw szablonom. Na przykład należy unikać nazw zawierających słowo „prowizja”, jeśli poufną informacją jest to, że wynagrodzenia niektórych pracowników mają charakter prowizyjny.

Gdy jeden lub więcej szablonów, do których masz dostęp, istnieje dla określonego formularza i próbujesz utworzyć nowy rekord w formularzu, wyświetlany jest strona **Wybierz szablon dla...**. Po wybraniu szablonu z listy jest tworzony nowy rekord, zawierający domyślne informacje utworzone na podstawie wybranego szablonu. Jeśli nie chcesz używać szablonów podczas tworzenia nowych rekordów, zaznacz pole wyboru **Nie pytaj ponownie** na stronie **Wybierz szablon dla**. Aby ponownie wyświetlić okno dialogowe wyboru szablonu, kliknij prawym przyciskiem myszy dowolny rekord, kliknij opcję **Informacje o rekordzie**, a następnie kliknij przycisk **Pokaż zaznaczenie szablonów**.
