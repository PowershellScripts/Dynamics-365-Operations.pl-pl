---
title: Amortyzacja czynnikowa
description: Ten artykuł zawiera omówienie metody amortyzacji współczynnikowej.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446737"
---
# <a name="factor-depreciation"></a>Amortyzacja czynnikowa

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji współczynnikowej.

Czynniki to wartości procentowe używane do amortyzacji środków. Po konfiguracji profilu amortyzacji środka trwałego i wybraniu wartości **Współczynnik** w polu **Metoda** na stronie **Profile amortyzacji** można skonfigurować amortyzację progresywną, degresywną lub liniową:

-   W przypadku wybrania amortyzacji progresywnej kwota wzrasta z każdym okresem amortyzacji.
-   W przypadku wybrania amortyzacji degresywnej kwota amortyzacji na okres systematycznie spada.
-   W przypadku wybrania amortyzacji liniowej amortyzacja jest taka sama w każdym okresie.

Poniższe reguły i przykłady wskazują, jak można skonfigurować czynniki dla każdego typu amortyzacji. 

> [!NOTE] 
> Po wybraniu opcji **Współczynnik** w polu **Metoda** zostaną wyświetlone pola **Współczynnik** i **Interwał**.

## <a name="progressive-depreciation"></a>Amortyzacja progresywna
Wartość w polu **Współczynnik** jest większa niż **50**.

### <a name="example"></a>Przykład

Cena nabycia wynosi 100,000, współczynnik wynosi 70, okres użytkowania to 10 lat, a data początkowa amortyzacji to 1 stycznia. Kwoty amortyzacji i kwoty wartości księgowej netto będą wyświetlane tylko przez pierwsze sześć lat okresu użytkowania.

| Rok | Okres      | Kwota amortyzacji | Kwota wartości księgowej netto |
|------|-------------|---------------------|-----------------------|
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa    | 31 grudnia | 307,69              | 99692,31             |
| 2    | 31 grudnia | 1447,21            | 98,245.10             |
| 3    | 31 grudnia | 3104,50            | 95,140.60             |
| 4    | 31 grudnia | 5150,21            | 89,990.39             |
| 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych    | 31 grudnia | 7522,95            | 82,467.44             |
| 6    | 31 grudnia | 10184,06           | 72,283.38             |

## <a name="digressive-depreciation"></a>Amortyzacja degresywna
Wartość w polu **Współczynnik** jest mniejsza niż **50**.

### <a name="example"></a>Przykład

Cena nabycia wynosi 100,000, współczynnik wynosi 20, okres użytkowania to 10 lat, a data początkowa amortyzacji to 1 stycznia. Kwoty amortyzacji i kwoty wartości księgowej netto będą wyświetlane tylko przez pierwsze sześć lat okresu użytkowania.

| Rok | Okres      | Kwota amortyzacji | Kwota wartości księgowej netto |
|------|-------------|---------------------|-----------------------|
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa    | 31 grudnia | 56080,43           | 43,919.57             |
| 2    | 31 grudnia | 10665,70           | 33,253.87             |
| 3    | 31 grudnia | 7156,22            | 26,097.65             |
| 4    | 31 grudnia | 5538,06            | 20,559.59             |
| 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych    | 31 grudnia | 4579,89            | 15,979.70             |
| 6    | 31 grudnia | 3937,36            | 12,042.34             |

## <a name="straight-line-depreciation"></a>Amortyzacja liniowa
Wartość w polu **Współczynnik** jest równa **50**. W tym przypadku amortyzacja jest taka sama w każdym okresie i powinno się uwzględnić w innych polach wybrane wartości, zgodnie z informacjami zawartymi w temacie [Amortyzację za liniowy okres użytkowania](straight-line-service-life-depreciation.md).



