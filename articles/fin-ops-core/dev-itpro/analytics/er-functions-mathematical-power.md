---
title: POWER, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji POWER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 858f59cf0bc6387b09cbb6f0c59f58ba8107582c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683336"
---
# <a name="power-er-function"></a>POWER, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `POWER` zwraca wartość *rzeczywistą* reprezentującą wynik podniesienia określonej liczby dodatniej do określonej potęgi.

## <a name="syntax"></a>Składnia

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argumenty

`number`: *Liczba rzeczywista* lub *Liczba całkowita*

Wartość numeryczna, którą należy podnieść do określonej potęgi.

`power`: *Liczba rzeczywista* lub *Liczba całkowita*

Wartość numeryczna reprezentują określoną potęgę.

## <a name="return-values"></a>Wartości zwracane

*Rzeczywisty*

Wynikowa wartość numeryczna.

## <a name="example-1"></a>Przykład 1

Funkcja `POWER (10, 2)` zwraca wartość **100**.

## <a name="example-2"></a>Przykład 2

Funkcja `POWER (4, 0.5)` zwraca wartość **2**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje matematyczne](er-functions-category-mathematical.md)
