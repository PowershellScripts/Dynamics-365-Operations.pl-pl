---
title: Omówienie sekwencji identyfikatorów
description: Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory.
author: MargoC
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2460d8c641a7e7b98b4fa5511636a1f0a47d372
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693985"
---
# <a name="number-sequences-overview"></a>Omówienie sekwencji identyfikatorów

[!include [banner](../includes/banner.md)]

Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory. Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do *odwołania*.

Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem. Zaleca się użycie stron w **Administrowaniu organizacją** do ustawiania sekwencji numerów. Jeśli wymagane są ustawienia zależne od modułu, można użyć strony parametrów w module do określania sekwencji numerów dla odwołań w module. Na przykład w **Rozrachunkach z odbiorcami** i **Rozrachunki z dostawcami**, aby przydzielić odpowiednie sekwencje numerów określonym odbiorcom lub dostawcom można skonfigurować grupy sekwencji numerów.

Podczas konfigurowania sekwencji numerów, należy wyznaczyć zakres określający, która organizacja używa sekwencji numerów. Zakres może mieć wartość **Współdzielony**, **Firma**, **Podmiot prawny** lub **Jednostka operacyjna**. Zakresy **Podmiot prawny** i **Jednostka** można łączyć z **Okresem kalendarza obrachunkowego** w celu tworzenia bardziej odpowiednich sekwencji numerów.

Formaty sekwencji numerów składają się z segmentów. Sekwencje numerów o zakresie innym niż **Współdzielony** mogą mieć segmenty odpowiadające ich zakresowi. Na przykład sekwencja numerów z zakresem **Firma** może zawierać segment firmy. Dołączając segment zakresu do formatu sekwencji numerów, można określić zakres określonego rekordu, sprawdzając jego numer.

Oprócz segmentów, które odpowiadają zakresom, formaty sekwencji numerów mogą zawierać segmenty **Stałe** i **Alfanumeryczne**. Segment **Stałe** zawiera zbiór litery, cyfry i symboli, który nie jest zmieniany. Segment **Alfanumeryczne** zawiera zestaw liter lub cyfr, które przyrastają przy każdym użyciu numeru. Użyj znaku cyfry (\#), aby przedstawić numery rosnąco, i znaku handlowego „i” (&), aby przedstawić litery rosnąco. Na przykład format \#\#\#\#\#\_2017 tworzy sekwencję 00001\_2017, 00002\_2017 i tak dalej.

## <a name="number-sequence-examples"></a>Przykłady sekwencji numerów

Poniższe przykłady przedstawiają metody korzystania z segmentów do tworzenia formatów sekwencji numerów. W szczególności w przykładach tych przedstawiono efekty użycia segmentów zakresu.

### <a name="expense-report-numbers"></a>Numery raportu wydatków.

W poniższym przykładzie numery raportu wydatków są ustawiane dla firmy oznaczonej jako **CS**.

- **Obszar:** Wyjazdy i wydatki
- **Odwołanie:** Numer raportu wydatków
- **Zakres:** Firma
- **Firma:** CS

| Segmenty  | Typ segmentów | Wartość     |
|-----------|--------------|-----------|
| Segment 1 | Firma | CS        |
| Segment 2 | Stała     | -WYDATEK- |
| Segment 3 | Alfanumeryczne | \#\#\#\#  |

**Przykład sformatowanego numeru**: CS-WYDATKI-0039

Można skonfigurować podobny format sekwencji numerów dla innych firm. Na przykład dla firmy zwanej **RW**, jeśli zmienisz tylko wartość segmentu firmy, sformatowanym numerem będzie RW-wydatki-0039. Można też zmienić cały format sekwencji numerów dla innych firm. Na przykład można pominąć segment zakresu firmy przy tworzeniu sformatowanej liczby, na przykład Wyd-0001.

### <a name="sales-order-numbers"></a>Numery zamówienia sprzedaży

W poniższym przykładzie numery zamówienia sprzedaży są konfigurowane dla Identyfikatora firmy **CEU**.

- **Obszar:** Sprzedaż
- **Odwołanie:** Zamówienie sprzedaży
- **Zakres:** Firma
- **Firma:** CEU

| Segmenty  | Typ segmentu | Wartość    |
|-----------|--------------|----------|
| Segment 1 | Stała     | SO-      |
| Segment 2 | Alfanumeryczne | \#\#\#\# |

**Przykład sformatowanego numeru**: SO-0029

Mimo że segment zakresu nie jest uwzględniony w formacie, numerowanie zostaje ponownie uruchamiane dla każdego identyfikatora firmy. Jeśli korzysta się z tego samego formatu dla wszystkich identyfikatorów firm, w każdej firmie są używane te same numery. Na przykład numer zamówienia sprzedaży SO-0029 jest używany w każdej firmie. Można też zmienić cały format sekwencji numerów dla innych identyfikatorów firm.

### <a name="purchase-requisition-numbers"></a>Numery zapotrzebowania na zakup

W poniższym przykładzie numery zapotrzebowań na zakup są stosowane na poziomie organizacji.

- **Obszar:** Zakup
- **Odwołanie:** Zapotrzebowanie na zakup
- **Zakres:** Współdzielony

| Segmenty  | Typ segmentu | Wartość    |
|-----------|--------------|----------|
| Segment 1 | Stała     | Ilość      |
| Segment 2 | Alfanumeryczne | \#\#\#\# |

**Przykład sformatowanego numeru**: Req0052

Ponieważ zakres ma wartość **Współdzielony**, format numeracji jest używany w całej organizacji. Nie można ustawić różnych formatów sekwencji numerów dla różnych części organizacji.

## <a name="performance-considerations-for-number-sequences"></a>Zagadnienia dotyczące wydajności dla sekwencji numerów

Należy wziąć pod uwagę następujące informacje na temat sposobu, w jaki konfiguracja sekwencji numerów może wpłynąć na wydajność systemu przed ustawieniem sekwencji numerów.

### <a name="continuous-and-non-continuous-number-sequences"></a>Ciągle i nieciągłe sekwencje numerów

Sekwencje numerów mogą być ciągle lub nieciągłe. Ciągła sekwencja numerów nie powoduje pominięcia żadnych liczby, ale numery nie mogą być używane po kolei. Numery z nieciągłej sekwencji numerów używane są sekwencyjne, ale może następować pomijanie numerów sekwencji. Na przykład jeśli użytkownik anuluje transakcję, numer jest generowany, ale nie jest używany. W ciągłej sekwencji numerów numer ten zostanie ponownie wykorzystany później. W nieciągłej sekwencji numerów numer ten nie zostanie ponownie wykorzystany.

Zazwyczaj ciągłe sekwencje numerów są wymagane dla zewnętrznych dokumentów, takich jak zamówienia zakupu, zamówienia sprzedaży i faktury. Jednak ciągłe sekwencje numerów mogą negatywnie wpływać na czas reakcji systemu, ponieważ system musi żądać numeru z bazy danych przy każdym tworzeniu nowego dokumentu lub rekordu.

Jeśli używasz nieciągłej sekwencji numerów, możesz włączyć **Wstępne przydzielanie** na skróconej karcie **Wydajność** na stronie **Sekwencja numerów**. Kiedy określasz liczbę numerów do wstępnego przydzielenia, system wybiera te numery i przechowuje je w pamięci. Nowe numery są pobierane z bazy danych tylko wtedy, gdy zostały użyte ilości przydzielone wstępnie.

Jeśli przepisy nie nakazują używania ciągłej sekwencji numerów, zaleca się używanie nieciągłej sekwencji numerów w celu uzyskania lepszej wydajności.

### <a name="automatic-cleanup-of-number-sequences"></a>Automatyczne oczyszczanie sekwencji numerów

W przypadku awarii zasilania, błędu aplikacji lub innego nieoczekiwanego problemu system nie może automatycznie odtworzyć numerów dla ciągłych sekwencji numerów. Proces oczyszczania można uruchomić ręcznie lub automatycznie w celu odzyskania zagubionych numerów.

Należy dokładnie rozważyć zużycie serwera podczas planowania procesu oczyszczania. Zalecane jest przeprowadzanie oczyszczania jako zadania wsadowego w godzinach poza szczytem.
