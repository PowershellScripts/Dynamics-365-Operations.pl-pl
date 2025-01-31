---
title: CASE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji CASE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: 69b76a06bcd3ba002d9543447e60afa14d5a6ce6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687033"
---
# <a name="case-er-function"></a>CASE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `CASE` oblicza wartość określonego wyrażenia względem określonych alternatywnych opcji i zwraca wynik pierwszej opcji, która jest równa wartości określonego wyrażenia. W przeciwnym razie zwraca ona domyślny wynik opcjonalny, jeśli domyślny wynik jest określony jako ostatni argument wywołanej funkcji, który nie jest poprzedzony opcją. Wartość zwracana może być wartością dowolnego z obsługiwanych typów danych.

## <a name="syntax"></a>Składnia

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Argumenty

`expression`: *Typ danych pierwotnych* (wartość logiczna, numeryczna lub tekst)

Prawidłowe wyrażenie, które zwraca wartość typu danych pierwotnych.

`option 1`: *Typ danych pierwotnych* (wartość logiczna, numeryczna lub tekst)

Prawidłowe wyrażenie, które zwraca wartość tego samego typu danych pierwotnych jako argument `expression` wywołanej funkcji. Ten argument jest wymagany.

`result 1`: *Dowolny z obsługiwanych typów danych*

Zwrócony wynik, który odpowiada poprzedniej opcji. Ten argument jest wymagany.

`option N`: *Typ danych pierwotnych* (wartość logiczna, numeryczna lub tekst)

Prawidłowe wyrażenie, które zwraca wartość tego samego typu danych pierwotnych jako argument `expression` wywołanej funkcji. Ten argument jest opcjonalny.

`result N`: *Dowolny z obsługiwanych typów danych*

Zwrócony wynik, który odpowiada poprzedniej opcji. Ten argument jest opcjonalny.

`default result`: *Dowolny z obsługiwanych typów danych*

Wynik, który powinien zostać zwrócony, jeśli nie ma dopasowania. Ten argument jest opcjonalny.

## <a name="return-values"></a>Wartości zwracane

*Dowolny z obsługiwanych typów danych*

Wynikowa wartość dowolnego z obsługiwanych typów danych.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Wyjątek jest generowany w czasie wykonywania, jeśli nie ma dopasowania i opcjonalny domyślny wynik nie został zdefiniowany.

Wszystkie wyniki muszą być określone przy użyciu tego samego typu danych. Wyjątek jest zgłaszany w czasie projektowania, jeśli typy danych skonfigurowanych wyników nie są zgodne.

Jeśli pierwsza wartość wyniku i *N*-ta wartość wyniku są wartościami o typie danych *Kontener (rekord)* lub *Lista rekordów*, wynik ma tylko pola, które istnieją w obu wartościach.

## <a name="example"></a>Przykład

Funkcja `CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` zwraca ciąg **„WINTER”**, jeśli bieżąca data sesji aplikacji przypada w miesiącach od października do grudnia. W przeciwnym razie zwraca ciąg pusty.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)
