---
title: SPLITLISTBYLIMIT, funkcja ER
description: Ten temat zawiera ogólne informacje o używaniu funkcji SPLITLISTBYLIMIT w module Raportowanie elektroniczne (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 1e6a4638cd32cb253261cc7fbaacb45b47f52c62
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683706"
---
# <a name="splitlistbylimit-er-function"></a>SPLITLISTBYLIMIT, funkcja ER

[!include [banner](../includes/banner.md)]

Funkcja `SPLITLISTBYLIMIT` dzieli określoną listę na nową listę list podrzędnych (partii). Liczba rekordów w każdej partii jest obliczana dynamicznie. Funkcja zwraca wynik jako nową wartość typu *Lista rekordów*, która składa się z partii.

## <a name="syntax"></a>Składnia

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Argumenty

`list`: *Lista rekordów*

Prawidłowa ścieżka elementu źródła danych o typie danych *Lista rekordów*.

`limit value`: *Liczba całkowita* lub *Liczba rzeczywista*

Maksymalna wartość limitu, który jest używany do dzielenia oryginalnej listy na partie.

`limit source`: *Pole*

Prawidłowa ścieżka pola typu *Liczba całkowita* lub *Liczba rzeczywista* na określonej liście. Wartość tego pola określa krok, w którym całkowita suma jest zwiększana.

## <a name="return-values"></a>Wartości zwracane

*Lista rekordów*

Wynikowa lista rekordów.

## <a name="usage-notes"></a>Uwagi dotyczące użytkowania

Zwracana jest lista partii zawierająca następujące elementy:

- **Value**: *Lista*

    Lista rekordów należących do bieżącej partii.

- **BatchNumber**: *Liczba całkowita*

    Numer bieżącej partii na zwróconej liście.

Limit nie jest stosowany do pojedynczego elementu oryginalnej listy, jeżeli źródło limitu przekracza zdefiniowany limit.

## <a name="example"></a>Przykład

Na poniższej ilustracji przedstawiono format raportowania elektronicznego (ER).

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

Na poniższej ilustracji pokazano źródła danych używane dla formatu.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

Na ilustracji poniżej widać wynik uruchomienia formatu. W tym przypadku danymi wyjściowymi jest niezhierarchizowana lista towarów asortymentowych.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

Na poniższej ilustracji ten sam format został skorygowany w taki sposób, aby pokazywał listę towarów asortymentowych w partiach, jeśli jedna partia musi zawierać towary o łącznej wadze nieprzekraczającej limitu 9.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

Na ilustracji poniżej widać wynik uruchomienia zmodyfikowanego formatu.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> Limit nie obowiązuje do ostatniej pozycji oryginalnej listy, ponieważ wartość (**11**) jej źródła limitu (**waga**) przekracza zdefiniowany limit (**9**). Aby zignorować listy podrzędne podczas generowania raportu, w razie potrzeby użyj funkcji `WHERE` albo wyrażenia **Enabled** odpowiedniego elementu formatu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Lista funkcji](er-functions-category-list.md)
