---
title: Analizowanie dokumentów przychodzących w formacie JSON
description: W tym temacie opisano sposób konfigurowania formatów modułu raportowania elektronicznego (ER) w celu analizy dokumentów przychodzących w formacie notacji obiektów JavaScript (JavaScript).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b4ed81bb5527ea8e02caaa1262a57960dd7cdf29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685770"
---
# <a name="parse-incoming-documents-in-json-format"></a>Analizowanie dokumentów przychodzących w formacie JSON

[!include[banner](../includes/banner.md)]

Istnieje możliwość zaprojektowania formatów sprawozdawczości elektronicznej (ER) w celu przeanalizowania przychodzących dokumentów elektronicznych reprezentujących dane w formacie tekstowym opartym na języku JavaScript (innymi słowy — pliki w JavaScript Object Notation w formacie notacji \[JSON\] ).

Aby dowiedzieć się więcej o tej funkcji, pobierz pliki w poniższej tabeli, a następnie odtwórz ER Utwórz konfigurację formatu w celu zaimportowania danych z zewnętrznego przewodnika zadań pliku JSON. W tym podręczniku zadań pokazano, w jaki sposób można użyć formatu ER do przeanalizowania przychodzącego pliku JSON w celu zaktualizowania danych aplikacji.

| Nazwa                                  | Nazwa pliku |
|----------------------------------------|-----------|
| ER format konfiguracji                | [Format importowania dostawców trans_JSON. XML](https://go.microsoft.com/fwlink/?linkid=874111) |
| Przykład pliku przychodzącego w formacie .csv | [1099entries_JSON. txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Wymagania

Przed ukończeniem modułu ER Utwórz konfigurację formatu w celu zaimportowania danych z zewnętrznego przewodnika zadań pliku JSON należy spełnić następujące wymagania:

- Elementy nadrzędne w pliku JSON mogą być tylko elementami obiektowymi.
- Zagnieżdżone elementy obiektu powinny być elementami właściwości, dzięki czemu tworzona jest prawidłowa struktura JSON.
- Tablice JSON mogą być tylko elementami zagnieżdżonymi elementów właściwości obiektu.
- Tablice JSON mogą zawierać tylko obiekty JSON. Nie mogą zawierać bezpośrednich wartości ciągów/liczb i tablic zagnieżdżonych. Elementy w tych tablicach zostaną przeanalizowane w kolejności, w jakiej zostały określone w formacie. Zostaną uwzględnione ustawienia wielokrotności dla każdego obiektu JSON.

Ponadto, należy wypełnić [ER Utwórz wymagane konfiguracje do zaimportowania danych z zewnętrznego pliku](tasks/er-required-configurations-import-data.md) przewodnik po zadaniach, jeśli jeszcze tego nie wykonano. Aby ukończyć przewodnik zadań należy pobrać następujący plik.

| Nazwa                  | Nazwa pliku |
|------------------------|-----------|
| Konfiguracja modelu ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
