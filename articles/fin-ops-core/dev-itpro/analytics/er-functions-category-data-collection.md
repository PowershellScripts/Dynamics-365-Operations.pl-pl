---
title: Lista funkcji modułu ER w kategorii kolekcji danych
description: Ten temat zawiera ogólne informacje o funkcjach kolekcji danych obsługiwanych w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 0ec6092f2992df91433bb8aaa4212fca2a0abf7c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686300"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Lista funkcji modułu ER w kategorii kolekcji danych

[!include [banner](../includes/banner.md)]

Funkcje kolekcji danych w module Raportowanie elektroniczne (ER) służą do zliczania i sumowania w uruchamianym formacie ER na podstawie danych wyjściowych, które zostały już wygenerowane w formacie **Tekst** lub **XML**. To podejście umożliwia poprawę wydajności uruchamianego formatu ER w celu wprowadzenia wartości sum bieżących w wygenerowanych dokumentach i dla innych celów. Ten temat zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja | Opis |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Ta funkcja zwraca wartość typu *Lista rekordów*, która zawiera listę wartości zwróconych przez właściwość **Zebrane dane wartości klucza** elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza. |
| [CountIF](er-functions-datacollection-countif.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek. Warunek składa się z zakresu kluczy i wartości klucza. |
| [CountIFs](er-functions-datacollection-countifs.md) | Ta funkcja zwraca wartość *Liczba całkowita* reprezentującą liczbę elementów formatu, które zostały zebrane, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Ta funkcja zwraca wartość typu *Ciąg* reprezentującą nazwę bieżącego elementu formatu ER. |
| [SumIF](er-functions-datacollection-sumif.md) | Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określony warunek. Warunek składa się z zakresu kluczy i wartości klucza. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Ta funkcja zwraca wartość *rzeczywistą* reprezentującą sumę wartości zwróconych przez powiązania elementów formatu oraz zebranych, gdy elementy formatu były używane do generowania podczas uruchamiania formatu dokumentu wychodzącego, który spełnia określone warunki. Każdy warunek składa się z zakresu kluczy i wartości klucza. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)
