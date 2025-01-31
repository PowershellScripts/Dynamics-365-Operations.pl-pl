---
title: Konsolidacje finansowe online
description: W tym temacie opisano funkcje konsolidacji finansowych online dostępne w księdze głównej.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 86be6d4cc0af3f2fd92523d4ecd3825f2383fc48
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446793"
---
# <a name="online-financial-consolidations"></a>Konsolidacje finansowe online

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje konsolidacji finansowych online dostępne w księdze głównej. Przed przeczytaniem tego tematu należy koniecznie przeczytać temat [Omówienie konsolidacji finansowych i przeliczania walut](financial-consolidations-currency-translation.md).

Po ukończeniu konfigurowania wprowadź informacje o konsolidacji na stronie **Konsolidacja [Online]**. Po zakończeniu można kliknąć przycisk **OK** lub **Zadanie wsadowe**, aby wykonać przetwarzanie konsolidacji.

## <a name="criteria"></a>Kryterium
Na karcie **Kryteria** na stronie **Konsolidacja [Online]** zdefiniuj konta, okresy i typ konsolidowanych danych.

![Karta Kryteria](./media/criteria-consolidate-online.png "Karta Kryteria")

Poniżej znajduje się objaśnienie różnych pól umieszczonych na tej stronie:

- **Opis** — służy do wprowadzania precyzyjnego opisu konsolidowanego okresu.
- **Konto główne** — pola w tej sekcji służą do definiowania kont głównych, które będą przetwarzane.

    - **Od** i **Do** — określ zakres kont, które mają być przetwarzane. Jeśli te pola pozostaną puste, wszystkie konta ze wszystkich firm zostaną przeniesione do konsolidowanej firmy. W związku z tym jeśli konsolidujesz cztery firmy, a każda firma ma inny plan kont, wszystkie konta ze wszystkich czterech firm zostaną utworzone w konsolidowanej firmie.
    - **Użyj konta konsolidacji** — po ustawieniu tej opcji na **Tak** staje się dostępne pole **Wybierz konto konsolidacji z**. W tym polu należy określić, czy wszystkie konta mają być konsolidowane na koncie konsolidacyjnym ustawionym na stronie **Konta główne**, czy też chcesz wybrać konto w jednej z grup kont konsolidacyjnych.
    - **Grupa kont konsolidacji** — umożliwia wybór grupy, która zostanie użyta w celu zamapowania konta głównego w konsolidacji.

- **Okres konsolidacji** — pola w tej sekcji służą do definiowania okresu konsolidacji.

    - **Od** i **Do** — umożliwia określenie zakresu dat konsolidacji. Jeśli te pola pozostaną puste, konsolidacja będzie przetwarzana dla wszystkich okresów zdefiniowanych w kalendarzu księgi dla firmy. Zalecane jest niepozostawianie tych pól pustych.
    - **Uwzględnij kwoty rzeczywiste** — ustaw tę opcję na **Tak**, aby konsolidować dane rzeczywiste.
    - **Uwzględnij kwoty budżetu** — ustaw tę opcję na **Tak**, aby konsolidować dane z rejestru budżetu.
    - **Przebudowa sald w trakcie konsolidacji** — nie zaleca się ustawiania tej opcji na **Tak**. Zamiast tego salda należy odbudowywać jako osobne zadanie wsadowe.

- **Modele budżetu** — jeśli wybrano konsolidowanie danych budżetu, pola w tej sekcji służą do definiowania modeli budżetu.

    - **Od** i **Do** — określ zakres modeli, które mają być używane.
    - **Typ kursu budżetowego** — umożliwia wybór typu kursu budżetowego, który ma być używany w przeliczaniu walut w danych budżetu.

## <a name="financial-dimensions"></a>Wymiary finansowe
Na karcie **Wymiary finansowe** określ wymiary, które mają być uwzględniane w konsolidowanej firmie. Aby wybrać wymiar, należy ustawić w polu **Specyfikacja** wartość **Wymiar**, a następnie określić kolejność wymiarów w konsolidowanej firmie.

![Karta wymiary finansowe](./media/financial-dimensions-cons.png "Karta wymiary finansowe")

Bez względu na zdefiniowaną kolejność zawsze pierwszym segmentem jest **Konto główne**.

## <a name="legal-entities"></a>Firmy
Na karcie **Firmy** określ firmy, które mają być uwzględniane w konsolidowanej firmie. Można także zdefiniować procentowy udział własności w tych firmach. Jeśli określisz udział własnościowy niższy niż 100 procent, ta wartość zostanie skumulowana do konsolidowanej firmy. Dla wszelkich rozbieżności przeliczania pole **Typ konta rozbieżności konwersji** służy do wybierania konta głównego z konfiguracji na stronie **Konta dla transakcji automatycznych**.

![Karta firm](./media/legal-entities-cons.png "Karta firm")

![Strona Konta dla transakcji automatycznych](./media/accounts-for-automatic-cons.png "Strona Konta dla transakcji automatycznych")

## <a name="elimination"></a>Eliminacja
Na karcie **Eliminacja** masz trzy opcje przetwarzania eliminacji:

- Wybierz regułę eliminacji, a następnie w polu **Opcje propozycji** zaznacz opcję **Tylko propozycja**. Ta opcja spowoduje przetwarzanie eliminacji w procesie konsolidacji, ale nie wszystkie zdarzenia zostaną zaksięgowane w jednym kroku. Arkusz można zaksięgować później.
- Wybierz regułę eliminacji, a następnie w polu **Opcje propozycji** zaznacz opcję **Tylko księgowanie**. Ta opcja spowoduje przetwarzanie eliminacji w procesie konsolidacji i wszystkie zdarzenia zostaną zaksięgowane w jednym kroku.
- Korzystając z arkusza eliminacji, można wygenerować propozycję eliminacji niezależnie od procesu konsolidacji.

![Karta Eliminacja](./media/elimination-cons-onl.png "Karta Eliminacja")

Aby uzyskać więcej informacji o eliminacjach, zobacz [Reguły eliminacji](./elimination-rules.md).

## <a name="currency-translation"></a>Tłumaczenie waluty
Na karcie **Przeliczanie walut** zdefiniuj firmę, konto, typ kursu wymiany i kurs wymiany. W polu **Zastosuj kurs wymiany od** są dostępne trzy opcje:

- **Data konsolidacji** — data konsolidacji będzie używana do pobrania kursu wymiany. Jest to kurs kasowy lub z końca miesiąca. Zobaczysz podgląd kursu, ale nie można go edytować.
- **Data transakcji** — data każdej transakcji będzie używana do wybrania kursu wymiany. Ta opcja jest najczęściej używana dla środków trwałych, a kurs często nazywa się „kursem historycznym”. Nie zobaczysz podglądu kursu, ponieważ będzie wiele kursów dla różnych transakcji w zakresie kont.
- **Kurs zdefiniowany przez użytkownika** — po wybraniu tej opcji można wprowadzić dowolny kurs wymiany. Opcja może być przydatna dla średnich kursów wymiany lub jeśli konsolidujesz na podstawie stałego kursu wymiany.

![Karta Typ przeliczania waluty](./media/currency-translation-cons-online.png "Karta Typ przeliczania waluty")

## <a name="additional-resources"></a>Dodatkowe zasoby

Aby uzyskać więcej informacji o konsolidacjach i przeliczaniu walut, zobacz temat nadrzędny tego tematu — [Omówienie konsolidacji finansowych i przeliczania walut](./financial-consolidations-currency-translation.md).

Aby uzyskać informacje o scenariuszach, w których mogą być tworzone skonsolidowane sprawozdania finansowe, zobacz [Generowanie skonsolidowanych sprawozdań finansowych](./generating-consolidated-financial-statements.md).
