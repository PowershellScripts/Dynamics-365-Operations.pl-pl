---
title: Konfigurowanie procesu importu zaawansowanego uzgadniania konta bankowego
description: Funkcja Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych, a następnie ich automatyczne uzgadnianie z transakcjami bankowymi w Microsoft Dynamics 365 Finance. W tym artykule wyjaśniono, jak skonfigurować funkcję importu wyciągów bankowych.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45f997a91701e3fc63278cdba3479dec9dc7a467
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446797"
---
# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Konfigurowanie procesu importu zaawansowanego uzgadniania konta bankowego

[!include [banner](../includes/banner.md)]

Funkcja Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych, a następnie ich automatyczne uzgadnianie z transakcjami bankowymi w programie Dynamics 365 Finance. W tym artykule wyjaśniono, jak skonfigurować funkcję importu wyciągów bankowych. 

Konfiguracja importu wyciągów bankowych różni się i zależy od formatu elektronicznych wyciągów bankowych. Program Finance obsługuje standardowo trzy formaty wyciągów bankowych: ISO20022, MT940 i BAI2.

## <a name="set-time-zone-preference"></a>Preferowana strefa czasowa
Podczas konfigurowania ustawień importu wyciągu bankowego ważne jest, aby uwzględnić strefę czasową danych dotyczących daty i godziny w plikach wyciągów bankowych, które zostaną zaimportowane. Domyślnie wszystkie wartości daty i godziny są już w formacie UTC (Coordinated Universal Time) i dlatego podczas importowania danych konwersja strefy czasowej nie zostanie zastosowana 

Dostępna jest opcja określająca strefę czasową, która ma być użyta do importowania danych. Ta opcja jest availble w polu **preferencja dotycząca strefy czasowej** na każdej stronie **szczegółów formatu danych źródłowych** (**obszar roboczy zarządzanie danymi > skonfigurować źródła danych > Wybierz format danych > ustawień regionalnych** na skróconej karcie). Wprowadzona preferencja czasu zostanie zastosowana do wszystkich operacji importowania, w których jest używany ten format danych źródłowych. Można utworzyć tyle formatów źródła danych, ile jest potrzebnych do importowania danych z wielu stref czasowych.  

Ta strefa czasowa może nie być taka sama jak strefa czasowa użytkownika lub firmy, dlatego należy objaśnić strefę czasową używaną przez dane daty i godziny. Zaleca się, aby podczas ustawiania preferencji dotyczących strefy czasowej wziąć pod uwagę następujące kwestie 

 - Wprowadzona preferencja czasu zostanie zastosowana do wszystkich operacji importowania, w których jest używany ten format danych źródłowych. Można utworzyć tyle formatów źródła danych, ile jest potrzebnych do importowania danych z wielu stref czasowych. 
 
 - Preferencja dotycząca strefy czasowej powinna być lokalną strefą czasową dla danych daty i godziny w pliku importu. 
 
 - Strefa czasowa danych daty i godziny może być taka sama jak strefa czasowa użytkownika lub firmy.
 
 - Użytkownicy mogą dostosowywać swoją strefę czasową, korzystając z **opcji użytkownika**.

Należy zauważyć, że poniższe akcje ułatwiają minimalizowanie potencjalnych konfliktów dat i godzin podczas importowania wyciągów bankowych. 

 - Unikaj zmiany preferencji dotyczących stref czasowych dla wszystkich kont bankowych, dla których zaimportowano już zestawienia Zmiana preferencji dotyczących strefy czasowej może mieć wpływ na kolejność nowych zestawień w odniesieniu do istniejących zestawień z powodu korekty strefy czasowej. 
 
 - Umożliwia przejrzenie wszystkich importów, w których jest używany wybrany format źródła danych. Preferencja dotycząca strefy czasowej określona dla formatu będzie dotyczyć wszystkich projektów importowanych korzystających z tego formatu. Potwierdzenie preferencji dotyczącej strefy czasowej określonej dla formatu będzie dotyczyć wszystkich projektów importowanych korzystających z tego formatu.

## <a name="sample-files"></a>Przykładowe pliki
We wszystkich trzech formatach są niezbędne pliki, które dokonują translacji wyciągu elektronicznego z oryginalnego formatu na format, którego można używać w Finance. Konieczne pliki zasobów znajdują się w węźle **Zasoby** w Eksploratorze aplikacji w programie Microsoft Visual Studio. Po znalezieniu plików skopiuj je do jednej znanej lokalizacji, co ułatwi ich przekazywanie na serwer w trakcie procesu konfigurowania.

| Nazwa zasobu                                           | Nazwa pliku                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Przykłady formatów i układów technicznych i wyciągów bankowych
Poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Definicja układu technicznego                             | Przykładowy plik wyciągu bankowego          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |



## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Konfigurowanie importowanie wyciągów bankowych w formacie ISO20022
Najpierw należy zdefiniować grupę przetwarzania formatu wyciągów bankowych ISO20022, używając do tego struktury jednostek danych.

1.  Kliknij kolejno opcje **Obszary robocze** &gt; **Zarządzanie danymi**.
2.  Kliknij przycisk **Importuj**.
3.  Nadaj formatowi nazwę, np. **ISO20022**.
4.  W polu **Format danych źródłowych** ustaw wartość **Element XML**.
5.  W polu **Nazwa jednostki** ustaw wartość **Wyciągi bankowe**.
6.  Aby przekazać pliki importu, kliknij przycisk **Przekaż** i przejdź do pliku **SampleBankCompositeEntity.xml**, który został wcześniej zapisany.
7.  Po przekazaniu jednostki Wyciągi bankowe i utworzeniu mapowania kliknij operację **Wyświetl mapę** dla tej jednostki.
8.  Jednostka Wyciągi bankowe jest jednostką złożoną, który składa się z czterech odrębnych jednostek. Na liście zaznacz pozycję **BankStatementDocumentEntity** i kliknij operację **Wyświetl mapę**.
9.  Na karcie **Przekształcenia** kliknij przycisk **Nowy**.
10. Dla numeru kolejnego 1 kliknij przycisk **Przekaż plik** i wybierz plik **ISO20022XML-to-Reconciliation.xslt**, który został wcześniej zapisany. **Uwaga:** Pliki przekształceń są skonstruowane dla standardowego formatu. Ponieważ banki często odbiegają od tego formatu, może być konieczne zaktualizowanie pliku przekształcenia, aby był dokładnie zmapowany na formatu wyciągów bankowych używany przez firmę. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Kliknij przycisk **Nowy**.
12. Dla numeru kolejnego 2 kliknij przycisk **Przekaż plik** i wybierz plik **BankReconciliation-to-Composite.xslt**, który został wcześniej zapisany.
13. Kliknij przycisk **Zastosuj przekształcenia**.

Po skonfigurowaniu grupy przetwarzania formatu następnym krokiem jest zdefiniowanie reguł formatu wyciągów bankowych ISO20022.

1.  Kliknij kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Ustawienia zaawansowanego uzgodnienia konta bankowego** &gt; **Format wyciągu bankowego**.
2.  Kliknij przycisk **Nowy**.
3.  Określ format wyciągu, np. **ISO20022**.
4.  Nadaj formatowi nazwę.
5.  W polu **Grupa przetwarzania** ustaw grupę, która została zdefiniowana wcześniej, np. **ISO20022**.
6.  Grupa przetwarzania **Plik XML**.

Ostatnim krokiem jest włączenie funkcji Zaawansowane uzgadnianie konta bankowego i ustawienie formatu wyciągów dla konta bankowego.

1.  Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Konta bankowe**.
2.  Zaznacz konto bankowe i otwórz je, aby wyświetlić szczegóły.
3.  Na karcie **Uzgodnienie** w opcji **Zaawansowane uzgadnianie konta bankowego** zaznacz wartość **Tak**.
4.  W polu **Format wyciągu** ustaw format, który został utworzony wcześniej, np. **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Konfigurowanie importowanie wyciągów bankowych w formacie MT940
Najpierw należy zdefiniować grupę przetwarzania formatu wyciągów bankowych MT940, używając do tego struktury jednostek danych.

1.  Kliknij kolejno opcje **Obszary robocze** &gt; **Zarządzanie danymi**.
2.  Kliknij przycisk **Importuj**.
3.  Nadaj formatowi nazwę, np. **MT940**.
4.  W polu **Format danych źródłowych** ustaw wartość **Element XML**.
5.  W polu **Nazwa jednostki** ustaw wartość **Wyciągi bankowe**.
6.  Aby przekazać pliki importu, kliknij przycisk **Przekaż** i przejdź do pliku **SampleBankCompositeEntity.xml**, który został wcześniej zapisany.
7.  Po przekazaniu jednostki Wyciągi bankowe i utworzeniu mapowania kliknij operację **Wyświetl mapę** dla tej jednostki.
8.  Jednostka Wyciągi bankowe jest jednostką złożoną, który składa się z czterech odrębnych jednostek. Na liście zaznacz pozycję **BankStatementDocumentEntity** i kliknij operację **Wyświetl mapę**.
9.  Na karcie **Przekształcenia** kliknij przycisk **Nowy**.
10. Dla numeru kolejnego 1 kliknij przycisk **Przekaż plik** i wybierz plik **MT940TXT-to-MT940XML.xslt**, który został wcześniej zapisany.
11. Kliknij przycisk **Nowy**.
12. Dla numeru kolejnego 2 kliknij przycisk **Przekaż plik** i wybierz plik **MT940XML-to-Reconciliation.xslt**, który został wcześniej zapisany. **Uwaga:** Pliki przekształceń są skonstruowane dla standardowego formatu. Ponieważ banki często odbiegają od tego formatu, może być konieczne zaktualizowanie pliku przekształcenia, aby był dokładnie zmapowany na formatu wyciągów bankowych używany przez firmę. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Kliknij przycisk **Nowy**.
14. Dla numeru kolejnego 3 kliknij przycisk **Przekaż plik** i wybierz plik **BankReconciliation-to-Composite.xslt**, który został wcześniej zapisany.
15. Kliknij przycisk **Zastosuj przekształcenia**.

Po skonfigurowaniu grupy przetwarzania formatu następnym krokiem jest zdefiniowanie reguł formatu wyciągów bankowych MT940.

1.  Kliknij kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Ustawienia zaawansowanego uzgodnienia konta bankowego** &gt; **Format wyciągu bankowego**.
2.  Kliknij przycisk **Nowy**.
3.  Określ format wyciągu, np. **MT940**.
4.  Nadaj formatowi nazwę.
5.  W polu **Grupa przetwarzania** ustaw grupę, która została zdefiniowana wcześniej, np. **MT940**.
6.  W polu **Typ pliku** ustaw wartość **txt**.

Ostatnim krokiem jest włączenie funkcji Zaawansowane uzgadnianie konta bankowego i ustawienie formatu wyciągów dla konta bankowego.

1.  Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Konta bankowe**.
2.  Zaznacz konto bankowe i otwórz je, aby wyświetlić szczegóły.
3.  Na karcie **Uzgodnienie** w opcji **Zaawansowane uzgadnianie konta bankowego** zaznacz wartość **Tak**.
4.  Kiedy zostanie wyświetlony monit o potwierdzenie wyboru i włączenie funkcji Zaawansowane uzgadnianie konta bankowego, kliknij przycisk **OK**.
5.  W polu **Format wyciągu** ustaw format, który został utworzony wcześniej, np. **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Konfigurowanie importowanie wyciągów bankowych w formacie BAI2
Najpierw należy zdefiniować grupę przetwarzania formatu wyciągów bankowych BAI2, używając do tego struktury jednostek danych.

1.  Kliknij kolejno opcje **Obszary robocze** &gt; **Zarządzanie danymi**.
2.  Kliknij przycisk **Importuj**.
3.  Nadaj formatowi nazwę, np. **BAI2**.
4.  W polu **Format danych źródłowych** ustaw wartość **Element XML**.
5.  W polu **Nazwa jednostki** ustaw wartość **Wyciągi bankowe**.
6.  Aby przekazać pliki importu, kliknij przycisk **Przekaż** i przejdź do pliku **SampleBankCompositeEntity.xml**, który został wcześniej zapisany.
7.  Po przekazaniu jednostki Wyciągi bankowe i utworzeniu mapowania kliknij operację **Wyświetl mapę** dla tej jednostki.
8.  Jednostka Wyciągi bankowe jest jednostką złożoną, który składa się z czterech odrębnych jednostek. Na liście zaznacz pozycję **BankStatementDocumentEntity** i kliknij operację **Wyświetl mapę**.
9.  Na karcie **Przekształcenia** kliknij przycisk **Nowy**.
10. Dla numeru kolejnego 1 kliknij przycisk **Przekaż plik** i wybierz plik **BAI2CSV-to-BAI2XML.xslt**, który został wcześniej zapisany.
11. Kliknij przycisk **Nowy**.
12. Dla numeru kolejnego 2 kliknij przycisk **Przekaż plik** i wybierz plik **BAI2XML-to-Reconciliation.xslt**, który został wcześniej zapisany. **Uwaga:** Pliki przekształceń są skonstruowane dla standardowego formatu. Ponieważ banki często odbiegają od tego formatu, może być konieczne zaktualizowanie pliku przekształcenia, aby był dokładnie zmapowany na formatu wyciągów bankowych używany przez firmę. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Kliknij przycisk **Nowy**.
14. Dla numeru kolejnego 3 kliknij przycisk **Przekaż plik** i wybierz plik **BankReconciliation-to-Composite.xslt**, który został wcześniej zapisany.
15. Kliknij przycisk **Zastosuj przekształcenia**.

Po skonfigurowaniu grupy przetwarzania formatu następnym krokiem jest zdefiniowanie reguł formatu wyciągów bankowych BAI2.

1.  Kliknij kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Ustawienia zaawansowanego uzgodnienia konta bankowego** &gt; **Format wyciągu bankowego**.
2.  Kliknij przycisk **Nowy**.
3.  Określ format wyciągu, np. **BAI2**.
4.  Nadaj formatowi nazwę.
5.  W polu **Grupa przetwarzania** ustaw grupę, która została zdefiniowana wcześniej, np. **BAI2**.
6.  W polu **Typ pliku** ustaw wartość **txt**.

Ostatnim krokiem jest włączenie funkcji Zaawansowane uzgadnianie konta bankowego i ustawienie formatu wyciągów dla konta bankowego.

1.  Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Konta bankowe**.
2.  Zaznacz konto bankowe i otwórz je, aby wyświetlić szczegóły.
3.  Na karcie **Uzgodnienie** w opcji **Zaawansowane uzgadnianie konta bankowego** zaznacz wartość **Tak**.
4.  Kiedy zostanie wyświetlony monit o potwierdzenie wyboru i włączenie funkcji Zaawansowane uzgadnianie konta bankowego, kliknij przycisk **OK**.
5.  W polu **Format wyciągu** ustaw format, który został utworzony wcześniej, np. **BAI2**.

## <a name="test-the-bank-statement-import"></a>Test działania importu wyciągu z konta
Ostatnim krokiem jest sprawdzenie, czy faktycznie jest możliwe zaimportowanie wyciągu bankowego.

1.  Wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Konta bankowe**.
2.  Zaznacz konto bankowe, dla którego jest włączona funkcja Zaawansowane uzgadnianie konta bankowego.
3.  Na karcie **Uzgodnij** kliknij opcję **Wyciągi bankowe**.
4.  Na stronie **Wyciąg bankowy** kliknij opcję **Importowanie wyciągu**.
5.  W polu **Konto bankowe** ustaw żądane konto bankowe. Pole **Formatu wyciągu** zostanie ustawione automatycznie na podstawie ustawienia konta bankowego.
6.  Kliknij przycisk **Przeglądaj** i wybierz plik elektronicznych wyciągów bankowych.
7.  Kliknij przycisk **Przekaż**.
8.  Kliknij przycisk **OK**

Jeśli import się powiedzie, otrzymasz komunikat z potwierdzeniem. Jeżeli import się nie powiedzie, w obszarze roboczym **Zarządzanie danymi** w sekcji **Historia zadań** odszukaj zadanie. Kliknij przycisk **Szczegóły wykonania** dotyczący zadania, aby otworzyć stronę **Podsumowanie wykonania**, a następnie kliknij przycisk **Wyświetl dziennik wykonywania**, aby wyświetlić błędy importu.



