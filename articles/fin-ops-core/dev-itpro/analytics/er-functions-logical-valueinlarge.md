---
title: Funkcja VALUEINLARGE ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji VALUEIN ER w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686913"
---
# <a name="valueinlarge-er-function"></a>Funkcja VALUEINLARGE ER

[!include [banner](../includes/banner.md)]

Funkcja `VALUEINLARGE` określa, czy podane dane wejściowe typu *Int64* lub *Integer* pasują do którejkolwiek wartości określonego elementu na podanej liście. Zwraca ona *wartość logiczną* **TRUE**, jeśli określone dane wejściowe pasują do wyniku uruchamiania określonego wyrażenia dla co najmniej jednego rekord z danej listy. W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. Aby zrozumieć różnicę związaną z funkcją `VALUEIN`, zapoznaj się z sekcją [Wskazówki użycia](#usage_note), znajdującą się w dalszej części tego tematu.

## <a name="syntax"></a>Składnia

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>Argumenty

`input`: *Pole*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*. To z wartością tego elementu będzie dokonywane porównanie.

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`list item expression`: *Wyrażenie*

Prawidłowe wyrażenie warunkowe, które wskazuje na albo zawiera pojedyncze pole określonej listy, która ma być używana do porównania.

## <a name="return-values"></a>Wartości zwracane

*Wartość logiczna*

Wyjściowa *wartość logiczna*.

## <a name=""></a><a name="usage_note">Uwagi dotyczące użytkowania</a>

Jeśli określone dane reprezentują typ elementu źródła danych taki jak *Int64* lub *Integer*, do którego wywołanie jest możliwe do przetłumaczenia na bezpośrednią instrukcję SQL, określona lista jest konwertowana na tabelę tymczasową SQL, a w bazie danych dokonywane jest dopasowanie przez wykonanie pojedynczej kwerendy `EXISTS JOIN`. W przeciwnym razie funkcja działa jako funkcja [`VALUEIN`](er-functions-logical-valuein.md).

Gdy określone dane wejściowe reprezentują element źródła danych zaprojektowany jako element inny niż *Int64* i *Integer*, błąd występuje w czasie projektowania, informując o tym, że funkcja `VALUEINLARGE` nie ma zastosowania dla skonfigurowanego wyrażenia encji.

Gdy jest wykonywane wyrażenie funkcyjne `VALUEINLARGE` i w zakresie tej operacji jest używana więcej niż jedna tabela tymczasowa, wystąpi błąd środowiska uruchomieniowego.

## <a name="example"></a>Przykład

Definiuje się następujące źródła danych w mapowaniu modelu:

- Źródło danych **In** typu *Rekordy tabeli*.
    - To źródło danych odnosi się do tabeli **Intrastat**.
    - Opcja **Międzyfirmowe** jest ustawiona na wartość **Nie**.
- Źródło danych **InMemory** typu *Pole obliczeniowe*.
    - To źródło danych zawiera wyrażenie `WHERE (In, In.Port <> "")`.
- Źródło danych **InFiltered** typu *Pole obliczeniowe*.
    - To źródło danych zawiera wyrażenie `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.

Jeśli źródło danych **InFiltered** jest wywoływane w kontekście firmy **DEMF**, w bazie danych aplikacji zostanie utworzona nowa tabela tymczasowa, a w tabeli zostanie wstawiona lista kodów identyfikacyjnych rekordów z kodami identyfikującymi rekordy, a w celu zwrócenia filtrowanych rekordów generowana jest instrukcja SQL tabeli **Intrastat**.

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje logiczne](er-functions-category-logical.md)

[funkcje VALUEIN](er-functions-logical-valuein.md)
