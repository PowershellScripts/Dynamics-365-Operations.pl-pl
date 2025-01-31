---
title: TRANSLATE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji TRANSLATE w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: c5d192b8679d6df2c44a0038fe4ffc181a6a54df
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685310"
---
# <a name="translate-er-function"></a>TRANSLATE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `TRANSLATE` zwraca wartość typu *Ciąg*, która zawiera wynik zastąpienia znaków określonego tekstu w znakach dla innego dostarczonego zbioru.

## <a name="syntax"></a>Składnia

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argumenty

`text`: *Ciąg*

Prawidłowa ścieżka elementu źródła danych o typie *Ciąg*.

`pattern`: *Ciąg*

Tekst, który musi zostać zastąpiony.

`replacement`: *Ciąg*

Tekst używany jako zastępczy.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Funkcja `TRANSLATE` zastępuje jeden znak na raz. Funkcja zastępuje pierwszy znak argumentu `text` wartością pierwszego znaku argumentu `pattern`, a następnie drugi znak i podąża za tym samym przepływem do zakończenia operacji. Jeśli znak z argumentów `text` i `pattern` jest zgodny, jest on zastępowany znakiem z argumentu `replacement` znajdującego się w tym samym położeniu, co znak z argumentu `pattern`. Jeśli w argumencie `pattern` występuje wiele razy znak, zostanie użyte mapowanie argumentu `replacement` odpowiadające pierwszemu wystąpieniu tego znaku.

## <a name="example-1"></a>Przykład 1

`TRANSLATE ("abcdef", "cd", "GH")` zastępuje znak **„c”** określonego tekstu **„abcdef** „ znakiem **„G”** tekstu `replacement`, ze względu na nastepujące:
-   Znak **„c”** jest przedstawiony w tekście `pattern` na pierwszym miejscu.
-   Pierwsza pozycja tekstu `replacement` zawiera znak **„G”**.

## <a name="example-2"></a>Przykład 2

Funkcja `TRANSLATE ("abcdef", "ccd", "GH")` zwraca wartość **"abGdef"**.

## <a name="example-3"></a>Przykład 3

Funkcja `TRANSLATE ("abccba", "abc", "123")` zwraca wartość **"123321"**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje tekstowe](er-functions-category-text.md)
