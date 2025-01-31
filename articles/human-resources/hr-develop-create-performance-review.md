---
title: Tworzenie przeglądów wydajności
description: W tym temacie pokazano sposób utworzenia przeglądu wydajności oraz opisano przeznaczenie każdej sekcji przeglądu.
author: andreabichsel
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99825dd580d617bb47b4f0ece784afbf6573ae8a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420061"
---
# <a name="create-performance-reviews"></a>Tworzenie przeglądów wydajności


W tym temacie pokazano sposób utworzenia przeglądu wydajności oraz opisano przeznaczenie każdej sekcji przeglądu. Procedurę utworzono przy użyciu danych firmy demonstracyjnej USMF.

1. Na stronie głównej wybierz obszar roboczy **Samoobsługa pracownika etatowego**.
2. Wybierz przycisk **Nowy przegląd**, aby utworzyć nowy przegląd.
3. W polu **Typ przeglądu** wprowadź lub wybierz wartość.
4. Wprowadź lub wybierz wartość w polu **Okres wydajności**.
5. W polu **Data końcowa** wprowadź datę.
6. Kliknij przycisk **OK**. Można również utworzyć przegląd na podstawie szablonu. Jest to najlepszy sposób tworzenie przeglądu, ponieważ każda sekcja będzie zawierać informacje potrzebne do rozpoczęcia przeglądu.  
7. Karty, takie jak karta załączniki, można wyświetlać i ukrywać:

    1. W okienku akcji wybierz pozycję **Pokaż sekcje**, aby otworzyć menu okna dialogowego.
    1. Wybierz opcję **Tak** lub **Nie** w polu **Pokaż załączniki**, aby wyświetlić lub ukryć kartę załączniki
    1. Wybierz opcję **Zapisz**.

8. Wybierz **Dodaj cel do przeglądu**, aby dodać cel. Po zakończeniu wybierz **OK**.
9. Wybierz przycisk **Dodaj wymagania**, aby otworzyć rozwijane okno dialogowe.
10. W polu **Tytuł** wpisz wartość.
11. W polu **Opis** wpisz `Increase customer skills by working with the support team`.
12. Kliknij przycisk **OK**.
13. Wybierz **Zwiń wszystkie**.
14. Wybierz **Rozwiń wszystkie**.
15. Wybierz opcję **Dodaj komentarz**.
16. Wybierz opcję **Zaksięguj**.
17. Wybierz kartę **Miary**.
18. Wybierz pozycję **Dodaj miarę**, aby otworzyć menu okna dialogowego.
19. Wprowadź lub wybierz wartość w polu **Miara**.
26. W polu **Kwota docelowa** wpisz liczbę.
20. Kliknij przycisk **OK**.
21. Kliknij kartę **Działania**.
22. Wybierz opcję **Dodaj**.
23. W polu **Tytuł** wpisz wartość.
24. W polu **Opis** wpisz wartość.
25. W polu **Data początkowa** wprowadź datę.
26. W polu **Data ukończenia** wprowadź datę.
27. W polu **Plan rozwoju** wybierz opcję **Tak**.
28. W polu **Słowa kluczowe** wpisz wartość.
29. Wybierz opcję **Zapisz**.
30. Kliknij kartę **Wyniki oceny**.  

    - Skrócona karta **Szczegóły oceny** umożliwia pracownikom ocenianie samych siebie, a kierownikom ocenianie pracowników. Jeśli są używane wagi, wartość wagi wyniku będzie obliczana automatycznie.  
    - Aby wyświetlić tę sekcję, należy włączyć ustawienia parametrów wyświetlania ocen pracowników.  

31. Wybierz kartę **Podpisy**. Jeśli przegląd używa przepływu pracy, podpisy pojawią się dopiero po zakończeniu przepływu pracy. Jeśli nie jest używany przepływ pracy, są tutaj wyświetlani zarówno pracownik, jak i kierownik. Wymagane pole wyboru jest zaznaczone na podstawie ustawień typu przeglądu.  
32. Kliknij kartę **Ogólne**.

    - Okres wydajności tworzy domyślne daty rozpoczęcia i zakończenia. Te daty są edytowalne.  
    - Stany kontrolują dostęp do przeglądu. Stan **Nie rozpoczęto** umożliwia wszystkim osobom edytowanie przeglądu. Stan **W toku** umożliwia wyświetlania i edytowanie przeglądu tylko konkretnemu pracownikowi. Stan **Gotowe do przeglądu** umożliwia wyświetlanie i edytowanie przeglądu tylko kierownikowi. Stan **Ostateczny przegląd** umożliwia pracownikowi i kierownikowi wyświetlanie przeglądu oraz edytowanie go, jeśli pozwala na to konfiguracja typu przeglądu. Stany **Zakończono** i **Anulowano** powodują, że przegląd jest tylko do odczytu. Jeśli przegląd zostanie **odrzucony** i odesłany do pracownika etatowego, pracownik etatowy i kierownik mogą dokonać niezbędnych zmian, aby pracownik etatowy mógł ponownie go przesłać.

33. W polu **Przegląd** wpisz wartość.
34. Wybierz kartę **Przegląd**. Gdy przegląd przechodzi przez kolejne stany, pracownik i kierownik mogą dodawać komentarze do każdego celu lub kompetencji.  
35. Wybierz kartę **Podpisy**. Pracownik i Menedżer mogą wyrejestrować się z przeglądu. Po złożeniu wszystkich wymaganych podpisów stan zmienia się na **Zakończono** i nie można wprowadzać więcej zmian.  

