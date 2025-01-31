---
title: NUMSEQVALUE, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji NUMSEQVALUE w module Raportowanie elektroniczne (ER).
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
ms.openlocfilehash: b513d04bfeb3a37aa0b1703d0fdde040885a5159
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680597"
---
# <a name="numseqvalue-er-function"></a>NUMSEQVALUE, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `NUMSEQVALUE` zwraca wartość typu *Ciąg*, która reprezentuje nową wygenerowaną wartość sekwencji numerów na podstawie określonej sekwencji numerów, zakres i identyfikatora zakresu. Identyfikator zakresu jest równy kodowi firmy podawanemu przez kontekst, w którym jest uruchamiany format modułu Raportowanie elektroniczne (ER).

## <a name="syntax-1"></a>Składnia 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Składnia 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Składnia 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Argumenty

`number sequence code`: *Ciąg*

Wartość tekstowa reprezentująca kod sekwencji numerów, w którym jest wymagana nowa wartość.

`number sequence record ID`: *Int64*

Wartość *Int64* reprezentująca identyfikator rekordu w tabeli NumberSequenceTable zawierającej definicję sekwencji numerów, w której jest wymagana nowa wartość.

`scope type`: *Wartość wyliczenia*

Wartość wyliczenia **ERExpressionNumberSequenceScopeType**, która definiuje zakres sekwencji numerów, w której jest wymagana nowa wartość. Dostępne typy zakresów to **Udostępnione**, **Podmiot prawny** i **Firma**.

`scope ID`: *Ciąg*

Wartość typu *Ciąg*, która identyfikuje zakres na podstawie określonego typu zakresu.

## <a name="return-values"></a>Wartości zwracane

*Ciąg*

Wynikowa wartość tekstowa.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Dla typu zakresu **Udostępnione** należy określić pusty ciąg jako identyfikator zakresu.

Dla typów zakresów **Firma** i **Podmiot prawny** należy podać kod firmy jako identyfikatora zakresu. Jeśli pusty ciąg jako identyfikator zakresu dla tych typów zakresów, zostanie użyty bieżący kod firmy.

Gdy używana jest składnia 1, jest wymagana sekwencja numerów dla typu zakresu **Firma**, a kod firmy jest dostarczany przez kontekst, w którym jest uruchomiony format ER.

## <a name="example-1"></a>Przykład 1

W formacie ER definiujesz źródło danych **AskNumSeq** typu *Parametr wejściowy użytkownika*. To źródło danych odwołuje się do rozszerzonego typu danych (EDT) **Opis**. Następnie definiujesz źródło danych **NumSeq** typu *Pole obliczeniowe*. To źródło danych zawiera wyrażenie `NUMSEQVALUE (AskNumSeq)`. Gdy następuje wywołanie źródła danych **NumSeq**, jest zwracana nowa wygenerowana wartość sekwencji numerów, która została określona w czasie wykonywania przez wprowadzenie kodu w oknie dialogowym. Sekwencja numerów jest wymagana dla typu zakresu **Firma**. Kod firmy jest dostarczany przez kontekst, w którym jest uruchamiany format ER.

## <a name="example-2"></a>Przykład 2

W mapowaniu modelu są definiowane następujące źródła danych:

- Źródło danych **LedgerParms** typu *Tabela*. To źródło danych odnosi się do tabeli LedgerParameters.
- Źródło danych **NumSeq** typu *Pole obliczeniowe*. To źródło danych zawiera wyrażenie `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.

Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji skonfigurowanej w oknie Parametry księgi głównej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego. Ta numeracja jednoznacznie identyfikuje arkusze i dostarcza numer partii, który łączy transakcje ze sobą.

## <a name="example-3"></a>Przykład 3

W mapowaniu modelu są definiowane następujące źródła danych:

- Źródło danych **enumScope** w aplikacji Microsoft Dynamics 365 Finance typu *wyliczenie*. To źródło danych odwołuje się do wyliczenia **ERExpressionNumberSequenceScopeType**.
- Źródło danych **NumSeq** typu *Pole obliczeniowe*. To źródło danych zawiera wyrażenie `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.

Gdy zostanie wywołane źródło danych **NumSeq**, zwróci nowo wygenerowaną wartość numeracji **Gene\_1** skonfigurowanej dla firmy dostarczającej kontekst, w którym jest wykonywany format raportowania elektronicznego.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inne funkcje (specyficzne dla domeny biznesowej)](er-functions-category-other.md)
