---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 2 — Mapowanie modelu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3214ddb1e077d889fb7b785bee2554b96c3907ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681692"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER Używanie wymiarów finansowych jako źródła danych (Część 2 — Mapowanie modelu)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)”.


## <a name="add-required-data-sources-to-model-mapping"></a>Dodawanie wymaganych źródeł danych do mapowania modelu
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.
3. Kliknij przycisk Konstruktor.
4. Kliknij opcję Mapuj model na źródło danych.
5. Kliknij przycisk Nowy.
6. W polu Definicja zaznacz wartość Wpis.
7. W polu Nazwa wpisz „Mapowanie danych wymiarów”.
8. W polu Opis wpisz „Mapowanie danych wymiarów”.
9. Kliknij przycisk Zapisz.
10. Kliknij przycisk Konstruktor.
11. W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.
12. Kliknij opcję Dodaj element główny.
13. W polu Nazwa wpisz „Firma”.
14. W polu Tabela wpisz „CompanyInfo”.
15. Kliknij przycisk OK.
16. W drzewie zaznacz element „Funkcje\Szczegóły wymiarów finansowych”.
17. Kliknij opcję Dodaj element główny.
    * To źródło danych określa, jak zakres wymiarów finansowych zostanie zdefiniowany dla każdego raportu, który będzie używał tego modelu jako źródła danych.  
18. W polu Nazwa wpisz wartość.
19. W polu Zapytaj o wymiary wybierz opcję Tak.
    * Wybierz opcję Tak, aby umożliwić użytkownikowi wybieranie wymiarów w czasie wykonywania w formularzu Okno dialogowe użytkownika. Jeśli ustawisz wartość Nie, domyślnie będą używane wszystkie wymiary finansowe bieżącego wystąpienia.  
20. W polu Wybór wymiarów finansowych zaznacz wartość „Firma”.
    * Zaznacz opcję Wszystko, aby umożliwić użytkownikowi wybieranie żądanych wymiarów dla bieżącego wystąpienia w polu Wyszukiwanie.  Zaznacz opcję Firma, aby umożliwić użytkownikowi wybieranie wymiarów dla firmy w polu Wyszukiwanie.  Wybierz opcję Wymiar, aby umożliwić użytkownikowi wybieranie wymiarów przy użyciu jednego zestawu wymiarów.  
21. W polu Zapytaj o konto główne wybierz opcję Tak.
    * W ustawieniu „Zapytaj o konto główne” zaznacz wartość Tak, aby zezwolić użytkownikom na wybieranie konta głównego jako części listy wymiarów.   Jeśli zaznaczysz wartość Nie, konto główne nie zostanie włączone do listy wymiarów, a opcja „Czy konto główne jest obowiązkowe” zostanie włączona. Jeśli w opcji „Czy konto główne jest obowiązkowe” ustawisz wartość Tak, konto główne będzie umieszczane na liście wymiarów niezależnie od wyboru dokonanego przez użytkownika.  
22. Kliknij przycisk OK.
![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping1.png)
23. W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.
24. Kliknij opcję Dodaj element główny.
25. W polu Nazwa wpisz „LedgerJournal”.
26. W polu Monituj o zapytanie wybierz opcję Tak.
27. W polu Tabela wpisz „LedgerJournalTable”.
28. Kliknij przycisk OK.
![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping2.png)

## <a name="map-data-model-elements-to-added-data-sources"></a>Mapowanie elementów modelu danych na dodane źródła danych
1. W drzewie rozwiń węzeł „Arkusz”.
2. W drzewie rozwiń węzeł „Arkusz\Transakcja”.
3. W drzewie rozwiń węzeł „Arkusz\Transakcja\Dane wymiarów”.
4. W drzewie rozwiń węzeł „Ustawienie wymiarów”.
5. W drzewie rozwiń węzeł „LedgerJournal”.
6. W drzewie rozwiń węzeł „LedgerJournal\<Relacje”.
7. W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans”.
8. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Załącznik”.
9. W drzewie zaznacz element „Arkusz\Transakcja\Załącznik”.
10. Kliknij opcję Powiąż.
11. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.
    * Należy zauważyć, że dla każdego odwołania do wymiarów finansowych, na przykład, LedgerDimension, jest dostępny odpowiadający mu element źródła danych (LedgerDimension.Wymiar). Ten element źródła danych udostępnia wymiary finansowe tego zestawu wymiarów jako listę rekordu.  
12. W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)”.
13. W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.
14. W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość”.
15. W drzewie rozwiń węzeł „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja”.
16. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Definicja\Nazwa”.
17. W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Nazwa”.
18. Kliknij opcję Powiąż.
19. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Opis”.
20. W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Opis”.
21. Kliknij opcję Powiąż.
22. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary\Wartość\Kod”.
23. W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów\Kod”.
24. Kliknij opcję Powiąż.
25. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Konto.Wymiar(LedgerDimension.Wymiar)\Konto główne i wymiary”.
26. W drzewie zaznacz element „Arkusz\Transakcja\Dane wymiarów”.
27. Kliknij opcję Powiąż.
![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping3.png)
28. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Debet(AmountCurDebit)”.
29. W drzewie zaznacz element „Arkusz\Transakcja\Debet”.
30. Kliknij opcję Powiąż.
31. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Data(TransDate)”.
32. W drzewie zaznacz element „Arkusz\Transakcja\Data”.
33. Kliknij opcję Powiąż.
34. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Waluta(CurrencyCode)”.
35. W drzewie zaznacz element „Arkusz\Transakcja\Waluta”.
36. Kliknij opcję Powiąż.
37. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans\Kredyt(AmountCurCredit)”.
38. W drzewie zaznacz element „Arkusz\Transakcja\Kredyt”.
39. Kliknij opcję Powiąż.
40. W drzewie zaznacz element „LedgerJournal\<Relacje\LedgerJournalTrans”.
41. W drzewie zaznacz element „Arkusz\Transakcja”.
42. Kliknij opcję Powiąż.
43. W drzewie zaznacz element „LedgerJournal\Arkusz z numerem partii(JournalNum)”.
44. W drzewie zaznacz element „Arkusz\Partia”.
45. Kliknij opcję Powiąż.
46. W drzewie zaznacz element „LedgerJournal”.
47. W drzewie zaznacz element „Arkusz”.
48. Kliknij opcję Powiąż.
49. W drzewie rozwiń węzeł „Wymiary”.
50. W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary”.
51. W drzewie rozwiń węzeł „Wymiary\Konto główne i wymiary\Definicja”.
52. W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa”.
53. W drzewie zaznacz element „Ustawienie wymiarów\Kod”.
54. Kliknij opcję Powiąż.
55. W drzewie zaznacz element „Wymiary\Konto główne i wymiary\Definicja\Nazwa kolumny raportu”.
56. W drzewie zaznacz element „Ustawienie wymiarów\Nazwa”.
57. Kliknij opcję Powiąż.
58. W drzewie zaznacz element „Wymiary\Konto główne i wymiary”.
59. W drzewie zaznacz element „Ustawienie wymiarów”.
60. Kliknij opcję Powiąż.
61. W drzewie zaznacz element „Firma”.
62. Kliknij przycisk Edytuj.
63. W polu expressionAsStringText wpisz „Firma.'find()'.'name()'”.
    * Firma.'find()'.'name()'  
64. Kliknij przycisk Zapisz.
![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping4.png)
65. Zamknij stronę.
66. Kliknij przycisk Zapisz.
67. Zamknij stronę.

## <a name="complete-this-draft-models-version"></a>Finalizowanie tej wersji roboczej modelu
1. Zamknij stronę.
2. Zamknij stronę.
3. Kliknij przycisk Zmień stan.
4. Kliknij przycisk Wykonaj.
5. Kliknij przycisk OK.
![Strona projektanta mapowania modelu ER](../media/er-financial-dimensions-guides-model-mapping5.png)
