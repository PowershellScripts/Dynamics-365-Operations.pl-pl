---
title: Planowanie główne z uwzględnieniem prognoz popytu
description: W tym temacie opisano sposób uwzględniania prognoz popytu podczas planowania głównego z optymalizacją planowania.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8b47aee41494394a32ffc0ea0c42a512e5051532
ms.sourcegitcommit: b86576e1114e4125eba8c144d40c068025f670fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666729"
---
# <a name="master-planning-with-demand-forecasts"></a>Planowanie główne z uwzględnieniem prognoz popytu

[!include [banner](../../includes/banner.md)]

Prognozę popytu można stosować razem z optymalizacją planowania w celu uwzględnienia oczekiwanego popytu w planowaniu głównym. Można ręcznie utworzyć prognozę popytu, zaimportować ją lub wygenerować za pomocą funkcji prognozowania popytu w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji o prognozowaniu popytu, zapoznaj się z [omówieniem prognozowania popytu ](../introduction-demand-forecasting.md).

> [!NOTE]
> Osobne planowanie prognozy nie jest obsługiwane w przypadku optymalizacji planowania. Z tego względu **ustawienie bieżącego planu według prognozy** na **stronie parametrów planowania głównego** nie ma znaczenia w przypadku korzystania z optymalizacji planowania.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Konfigurowanie planu głównego w celu uwzględnienia prognozy popytu

Aby skonfigurować plan główny w celu uwzględnienia prognozy popytu, należy wykonać następujące kroki.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz istniejący plan lub utwórz nowy plan.
1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - W polu **Model prognozy** wybierz model prognozy. Ten model będzie brany pod uwagę podczas generowania sugestii dostaw dla bieżącego planu głównego.
    - **Uwzględnij prognozę popytu** — tę opcję należy określić jako *wartość tak*, aby uwzględnić prognozę popytu w bieżącym planie głównym. Jeśli zostanie ustawiona wartość *nie*, transakcje prognozy popytu nie będą uwzględniane w planie głównym.
    - **Metoda używana do redukowania zapotrzebowań prognozowanych** — umożliwia wybór metody, która ma zostać użyta do zmniejszenia prognozowanych zapotrzebowań. Aby uzyskać więcej informacji, zobacz sekcję [„Klucze redukcji w prognozie"](#reduction-keys) w dalszej części tego tematu.

1. Na karcie FastTab dla **horyzontu czasowego w dniach** można ustawić następujące pola, aby określić okres, w którym Prognoza popytu jest uwzględniana w czasie:

    - **Plan wg prognozy** — ustawienie tej opcji na *tak* powoduje zastąpienie horyzontu czasowego planu wg prognozy, który pochodzi z poszczególnych grup zapotrzebowania. Ustaw na *nie*, aby używać wartości z poszczególnych grup zapotrzebowania dla bieżącego planu głównego.
    - **Okres prognozy** — w przypadku ustawienia **opcji planu według prognozy** na wartość *tak* należy określić liczbę dni (od dzisiejszej daty), jaka powinna zostać zastosowana w prognozie popytu.

    > [!IMPORTANT]
    > Osobne **planowanie prognozy** nie jest obsługiwane w przypadku optymalizacji planowania.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Konfigurowanie grupy zapotrzebowania w celu uwzględnienia prognozy popytu

Aby skonfigurować grupę zapotrzebowania w celu uwzględnienia prognozy popytu, należy wykonać następujące kroki.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Plany \> Grupy zapotrzebowania**.
1. Wybierz istniejącą grupę zapotrzebowania lub Utwórz nową grupę.
1. Na skróconej karcie **Inne** ustaw następujące pola:

    - **Horyzont czasowy planu wg prognozy** — umożliwia wprowadzenie liczby dni (od daty dzisiejszej), dla których ma być stosowana Prognoza popytu. Tę wartość można zastąpić przy użyciu **planu według prognozy** w planie głównym, zgodnie z opisem w poprzedniej sekcji.
    - **Klucz redukcji** — umożliwia wybór klucza redukcji, który ma zostać zastosowany. Aby uzyskać więcej informacji, zajrzyj do opcji[Utwórz i Ustaw klucz redukcji prognozy](#create-reduction-key) i [Skorzystaj z sekcji klucza redukcji](#use-reduction-key) w dalszej części tego tematu.
    - **Zmniejszenie prognozy wg** — w przypadku planów głównych, w których **Metoda służąca do zmniejszania** wartości w polu prognozowane zapotrzebowania jest ustawiona na *transakcje — klucz redukcji* lub *transakcje — okres dynamiczny*, należy określić, które transakcje powinny obniżyć prognozę. Należy wybrać jedną z następujących opcji:

        - **Wszystkie transakcje** — wszystkie transakcje powinny zmniejszać prognozę.
        - **Zamówienia** — prognozy są redukowane tylko w przypadku zamówień sprzedaży.

        > [!NOTE]
        > W przypadku wybrania *wszystkich transakcji* transakcje, które mają zarówno zapotrzebowanie, jak i dostawę w tych samych wymiarach magazynowych, są uznawane za neutralne i zostaną zignorowane podczas obniżenia prognozy. Jeśli na przykład wymiar planowania ma wartość tylko oddział, nie magazyn, zlecenie przeniesienia między oddziałem 1, magazyn 11 i oddział 1, magazyn 13, zostanie zignorowane i nie zostanie zmniejszona pozostała Prognoza popytu.

    - **Uwzględnij zamówienia Międzyfirmowe** — tę opcję *należy ustawiać na wartość tak*, jeśli zamówienia Międzyfirmowe mają być uwzględniane podczas zmniejszania prognozy. W przeciwnym razie ustaw wartość *nie*.
    - **Uwzględnij prognozę odbiorców w prognozie popytu** — umożliwia określenie, czy Prognoza odbiorców ma być uwzględniana w całej prognozie. To ustawienie określa sposób, w jaki rzeczywisty popyt powoduje zmniejszenie prognozy popytu. To ustawienie służy do zapewnienia, że planowanie główne obejmuje dostawy towarów, które są kupowane przez określonych odbiorców.

        - Ustawienie tej opcji na *tak* powoduje uwzględnienie prognozy odbiorcy w całej prognozie. W tym przypadku rzeczywisty popyt odbiorcy redukuje zarówno prognozę odbiorców, jak i prognozę ogólną. Planowanie główne generuje zamówienia planowane w celu pokrycia wyłącznie całkowitej prognozowanej ilości.
        - Ustawienie tej opcji na *nie* powoduje nieuwzględnienie prognozy odbiorcy w całej prognozie. W takim przypadku rzeczywisty popyt odbiorcy zmniejsza tylko prognozę odbiorców. Planowanie główne generuje zamówienia planowane, aby pokryć zarówno łączną prognozowaną ilość, jak i prognozę ilości dla każdego odbiorcy.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>Klucze redukcji prognozy

W tej sekcji omówiono różne metody, które służą do zmniejszania prognozowanych zapotrzebowań. Zawiera przykłady wyników każdej z tych metod. Ponadto wyjaśniono, jak tworzyć, konfigurować i używać kluczy redukcji prognoz. Niektóre metody używają kluczy redukcji prognoz do zmniejszania prognozowanych zapotrzebowań.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Metody używane w celu zmniejszenia prognozowanych zapotrzebowań

Po dołączeniu prognozy do planu głównego można wybrać sposób redukowania prognozowanych zapotrzebowań, gdy rzeczywisty popyt jest uwzględniony. Należy zauważyć, że planowanie główne wyklucza prognozowane zapotrzebowania z przeszłości, co obejmuje wszystkie zapotrzebowania podlegające prognozie przed datą dzisiejszą.

Aby uwzględnić prognozę w planie głównym i wybrać metodę, która jest używana do zmniejszenia prognozowanych zapotrzebowań, przejdź do **Planowanie główne \> ustawienia \> Plany \> plany główne**. W polu **Model prognozy** wybierz model prognozy. W polu **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** wybierz metodę. Dostępne są następujące opcje:

- None
- Procent — klucz redukcji
- Transakcje — klucz redukcji (nieobsługiwany jeszcze w przypadku optymalizacji planowania)
- Transakcje — okres dynamiczny

Poniższe sekcje zawierają więcej informacji o każdej funkcji.

#### <a name="none"></a>Brak

Jeśli wybrana zostanie wartość **Brak**: Prognozowane zapotrzebowanie nie będzie redukowane podczas planowania głównego. W takim przypadku planowanie główne tworzy zamówienia planowane w celu dostarczania prognozy popytu (prognozowane zapotrzebowania). Planowane zamówienia zachowują sugerowaną ilość bez względu na inne typy popytu. Na przykład, jeśli zostaną złożone zamówienia sprzedaży, planowanie główne tworzy dodatkowe zamówienia planowane w celu dostarczenia zamówienia sprzedaży. Ilość prognozowanego zapotrzebowania nie jest zmniejszona.

#### <a name="percent--reduction-key"></a>Procent — klucz redukcji

Jeśli wybierzesz **Procent — klucz redukcji**, zmniejsza wymagania dotyczące prognozy popytu według wartości procentowych i okresów czasu, które są definiowane według klucza redukcji. W takim przypadku planowanie główne tworzy zamówienia planowane, gdzie ilość jest obliczana jako klucz redukcji × Prognozowana ilość w każdym okresie. Jeśli istnieją inne typy zapotrzebowania, planowanie główne tworzy również zamówienia planowane w celu zaspokojenia tego popytu.

##### <a name="example-percent--reduction-key"></a>Przykład: Procent — klucz redukcji

W tym przykładzie pokazano, jak klucz redukcji zmniejsza wymagania dotyczące prognozy popytu według wartości procentowych i okresów, które są definiowane według klucza redukcji.

Na przykład wprowadzono następującą prognozę sprzedaży w planie głównym.

| Miesiąc    | Prognoza popytu |
|----------|-----------------|
| Styczeń  | 1 000           |
| luty | 1 000           |
| marzec    | 1 000           |
| kwiecień    | 1 000           |

Na stronie **Klucz redukcji** ustaw następujące wiersze.

| Zmiana | Jednostka  | Procent |
|--------|-------|---------|
| 1      | Miesiąc | 100     |
| 2      | Miesiąc | 75      |
| 3      | Miesiąc | 50      |
| 4      | Miesiąc | 25      |

Przypisz klucz redukcji do grupy zapotrzebowania dla towaru. Następnie na stronie **plany główne** w polu **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** wybierz **procent — klucz redukcji**.

W tym przypadku uruchomienie planowania w dniu 1 stycznia spowoduje, że wymagania prognozy popytu zostaną zużyte według wartości procentowych ustawionych na stronie **Klucze redukcji**. Następujące ilości wymagania są przenoszone do planu głównego.

| Miesiąc                | Planowana ilość zamówienia | Obliczenie    |
|----------------------|------------------------|----------------|
| Styczeń              | 0                      | = 0% × 1,000   |
| luty             | 250                    | = 25% × 1,000  |
| marzec                | 500                    | = 50% × 1,000  |
| kwiecień                | 750                    | = 75% × 1,000  |
| Od maja do grudnia | 1 000                  | = 100% × 1,000 |

#### <a name="transactions--reduction-key"></a>Transakcje — klucz redukcji

Jeśli wybierzesz **Transakcje — klucz redukcji** zmniejsza wymagania dotyczące prognozy popytu według transakcji zachodzących w okresach czasu, które są definiowane według klucza redukcji.

##### <a name="example-transactions--reduction-key"></a>Przykład: Transakcje— klucz redukcji

W tym przykładzie pokazano, jak rzeczywiste zamówienia występujące w okresach zdefiniowanych przez klucz redukują wymagania prognozy popytu.

W tym przykładzie wybierasz **Transakcje — klucz redukcji** w **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** na stronie **Plany główne**.

1 stycznia istnieją następujące zamówienia sprzedaży.

| Miesiąc    | Zamówiona liczba sztuk |
|----------|--------------------------|
| Styczeń  | 956                      |
| Luty | 1,176                    |
| Marzec    | 451                      |
| Kwiecień    | 119                      |

Przy tej samej prognozie popytu dla 1000 sztuk na miesiąc do planu głównego przesyłane są następujące ilości wymagania.

| Miesiąc                | Wymagana liczba sztuk |
|----------------------|---------------------------|
| Styczeń              | 44                        |
| luty             | 0                         |
| marzec                | 549                       |
| kwiecień                | 881                       |
| Od maja do grudnia | 1 000                     |

#### <a name="transactions--dynamic-period"></a>Transakcje — okres dynamiczny

W przypadku wybrania **transakcje — okres dynamiczny**, prognozowane zapotrzebowania są redukowane zgodnie z rzeczywistymi transakcjami zamówień w okresie dynamicznym. Okres dynamiczny obejmuje aktualne daty prognozy i kończy się na początku kolejnej prognozy. W takim przypadku planowanie główne tworzy zamówienia planowane w celu dostarczania prognozy popytu (prognozowane zapotrzebowania). Jednak po zrealizowaniu rzeczywistych transakcji zamówień prognozowane wymagania są redukowane. Rzeczywiste transakcje zużywają część prognozowanego zapotrzebowania.

Ta opcja jest używana, występują następujące zachowania:

- Klucze redukcji nie są wymagane/używane. 
- Jeśli prognoza zostanie zmniejszona do zera, wymagania prognozy dla bieżącej prognozy przybierają wartość 0 (zero).
- Jeśli nie ma żadnej przyszłej prognozy, wymagania prognozy z ostatnio wprowadzonej prognozy są redukowane.
- Horyzonty czasowe są uwzględniane w obliczeniach redukcji prognozy.
- Dni pasywne są uwzględniane w obliczeniach redukcji prognozy.
- Jeśli transakcje rzeczywistego zamówienia przekraczają prognozowane zapotrzebowanie, pozostałe transakcje nie są przekazywane do następnego okresu prognozy.

##### <a name="example-1-transactions--dynamic-period"></a>Przykład 1: Transakcje — okres dynamiczny

Tutaj jest prosty przykład pokazujący sposób działania metody **transakcje — okres dynamiczny**.

Na przykład wprowadzono następującą prognozę sprzedaży w planie głównym.

| Data       | Prognoza popytu |
|------------|-----------------|
| 1 stycznia  | 1 000           |
| 1 lutego | 1 000             |

Można również utworzyć następujące zamówienia sprzedaży.

| Data        | Ilość dla zamówienia sprzedaży |
|-------------|----------------------|
| 15 stycznia  | 200                  |
| 15 lutego | 400                  |

W takim wypadku są tworzone następujące zamówienia planowane.

| Data prognozy popytu | Ilość | Wyjaśnienie                           |
|--------------------- |----------|---------------------------------------|
| 1 stycznia            | 800      | Prognozowane zapotrzebowanie (= 1000 – 200) |
| 15 stycznia           | 200      | Zapotrzebowanie w zamówieniach sprzedaży             |
| 1 lutego           | 600      | Prognozowane zapotrzebowanie (= 1000 – 400) |
| 15 lutego          | 400      | Zapotrzebowanie w zamówieniach sprzedaży             |

##### <a name="example-2-transactions--dynamic-period"></a>Przykład 2: Transakcje — okres dynamiczny

W większości przypadków systemy są skonfigurowane tak, aby transakcje zmniejszały prognozy popytu w określonych okresach prognozy: tygodnie, miesiąca itd. Te okresy są definiowane w kluczu redukcji. Jednak czas między dwoma wierszami popytu mogą również *implikować* okresu.

W tym przykładzie tworzymy prognozę popytu dla następujących dat i ilości.

| Data       | Prognoza popytu |
|------------|-----------------|
| 1 stycznia  | 1 000           |
| 5 stycznia  | 500             |
| 12 stycznia | 1 000           |

Należy zauważyć, że w tej prognozie, nie ma okresu pomiędzy datami prognoz. Między pierwszą a drugą datą jest czterodniowy odstęp, a między drugą a trzecią datą jest odstęp 7 dni. Te różne zakresy są okresami dynamicznymi.

Można również utworzyć następujące wiersze zamówienia sprzedaży.

| Data                             | Ilość dla zamówienia sprzedaży |
|----------------------------------|----------------------|
| 15 grudnia w poprzednim roku | 500                  |
| 3 stycznia                        | 100                  |
| 10 stycznia                       | 200                  |

W takim przypadku prognoza jest zmniejszana w następujący sposób:

- Ponieważ pierwsze zamówienie sprzedaży nie mieści się w żadnym okresie, więc nie ograniczy żadnej prognozy.
- Ponieważ drugie zamówienie sprzedaży mieści się w dniach 1-5 stycznia, więc ograniczy prognozę dla 1 stycznia o 100.
- Ponieważ trzecie zamówienie sprzedaży mieści się w dniach 5-12 stycznia, więc ograniczy prognozę dla 5 stycznia o 200.

W takim wypadku są tworzone następujące zamówienia planowane.

| Data prognozy popytu             | Ilość | Wyjaśnienie                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 grudnia w poprzednim roku | 500      | Zapotrzebowanie w zamówieniach sprzedaży                                            |
| 1 stycznia                        | 900      | Prognozowane zapotrzebowanie na okres od 1 stycznia do 5 stycznia (= 1000 – 100) |
| 3 stycznia                        | 100      | Zapotrzebowanie w zamówieniach sprzedaży                                            |
| 5 stycznia                        | 300      | Prognozowane zapotrzebowanie na okres od 5 stycznia do 10 stycznia (= 500 – 200)  |
| 12 stycznia                       | 1 000    | Prognozowane zapotrzebowanie na okres od 12 stycznia końca                      |

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>Tworzenie i konfigurowanie klucza redukcji prognoz

Klucz redukcji prognozy jest używany w metodach **transakcje — klucz redukcji** i **procent — klucz redukcji** redukcji prognozowanego zapotrzebowania. Wykonaj następujące kroki, aby utworzyć i skonfigurować klucz redukcji.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Klucze redukcji**.
2. Wybierz **nowy** lub naciśnij **Ctrl + N**, aby utworzyć klucz redukcji.
3. W polu **klucza redukcji** wprowadź unikatowy identyfikator klucza redukcji prognoz. Następnie w polu **Nazwa** nadaj nazwę. 
4. Definiowanie okresów i procenta klucza redukcji w każdym okresie:

    - Pole **Data wejścia w życie** wskazuje datę rozpoczęcia tworzenia okresów. Jeśli opcja **Użyj daty obowiązywania** jest ustawiona jako **Tak**, okresy zaczynają się zgodnie z datą wejścia w życie. Jeśli ta opcja jest ustawiona jako **Nie**, okresy zaczynają się w dniu uruchomienia planowania głównego.
    - Definiowanie okresów, w których powinna mieć miejsce redukcja prognozy.
    - W danym okresie należy określić wartości procentowe, o które powinno być zmniejszane prognozowane zapotrzebowanie. Można wprowadzić wartość dodatnią, aby zmniejszyć wymagania, lub wartość ujemną, aby zwiększyć zapotrzebowanie.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>Użyj Klucza redukcji

Klucz redukcji prognoz musi być przypisany do grupy zapotrzebowania towaru. Wykonaj następujące kroki, aby przypisać klucz redukcji do grupy zapotrzebowania dla towaru.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Grupy zapotrzebowania**.
2. Na skróconej karcie **Inne** w polu **Klucz redukcji** wybierz klucz redukcji, który zostanie przypisany do grupy zapotrzebowania. Klucz redukcji następnie stosuje się do wszystkich elementów, które należą do grupy zapotrzebowania.
3. Aby użyć klucza redukcji do obliczania redukcji prognozy w planowaniu głównym, to ustawienie należy zdefiniować w oknie ustawień planu głównego lub planu wg prognozy. Przejdź do jednej z następujących lokalizacji:

    - Planowanie główne \> Konfiguracja \> Plany \> Plany wg prognoz
    - Planowanie główne \> Ustawienia \> Plany \> Plany główne

4. Na stronie **planów wg prognozy** lub **planów głównych** na skróconej karcie **ogólne** w polu **metoda używana do zmniejszenia prognozowanych zapotrzebowań** wybierz opcję **procent — klucz redukcji** lub **transakcje — klucz redukcji**.

### <a name="reduce-a-forecast-by-transactions"></a>Redukcja prognoz według transakcji

Po wybraniu metody **Transakcje — klucz redukcji** lub **Transakcje — okres dynamiczny** do redukcji prognozowanego zapotrzebowania można wybrać, które transakcje będą uwzględniane w redukowaniu prognozy. Na stronie **Grupy zapotrzebowania** na skróconej karcie **Inne** w polu **Zmniejsz prognozę o** wybierz **Wszystkie transakcje**, jeśli wszystkie transakcje mają redukować prognozę, lub **Zamówienia**, jeśli tylko zamówienia sprzedaży mają redukować prognozę.
