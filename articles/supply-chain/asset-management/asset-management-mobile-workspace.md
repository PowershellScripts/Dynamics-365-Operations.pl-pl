---
title: Mobilny obszar roboczy zarządzania składnikami majątku
description: Ten temat zawiera informacje o mobilnym obszarze roboczym zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 525f21d076027f1bf339e59fd0e346706044839c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435051"
---
# <a name="asset-management-mobile-workspace"></a>Mobilny obszar roboczy zarządzania składnikami majątku

[!include [banner](../../includes/banner.md)]


Ten temat zawiera informacje o mobilnym obszarze roboczym zarządzanie składnikami majątku. Ten obszar roboczy umożliwia użytkownikom wyświetlanie i tworzenie żądań konserwacji i zleceń pracy. Użytkownicy mogą również wyświetlać przypisane zadania dotyczące zleceń pracy w widoku kalendarza lub listy. Można również wyświetlać i wyszukiwać zasoby i lokalizacje czynności konserwacyjnych.


## <a name="overview"></a>Przegląd

Zarządzanie składnikami majątku to zaawansowany moduł do zarządzania składnikami majątku i zadań zleceń pracy w Dynamics 365 Supply Chain Management. Mobilny obszar roboczy **Zarządzania składnikami majątku** umożliwia użytkownikom szybkie przeglądanie przydzielonych zadań zlecenia produkcyjnego na wybranym urządzeniu przenośnym. Użytkownicy mogą również tworzyć i zarządzać żądaniami konserwacji, aktualizować stan cyklu życia oraz wyświetlać szczegóły dotyczące składników majatku i lokalizacji czynności konserwacyjnych przy użyciu urządzeń przenośnych.

W szczególności mobilny obszar roboczy **Zarządzanie składnikami majatku** pozwala użytkownikom wykonywać następujące zadania:

- Umożliwia tworzenie, wyświetlanie i edytowanie żądań konserwacji, sporządzanie fotografii lub dołączanie istniejącego obrazu do żądania konserwacji, zmiana stanu cyklu obsługi żądania konserwacji. 
- Umożliwia tworzenie, wyświetlanie i edytowanie zleceń pracy, sporządzanie fotografii lub dołączanie istniejącego obrazu do zlecenia pracy, zmiana stanu cyklu obsługi zlecenia pracy, wyświetlanie zadań zlecenia pracy.
- Umożliwia wyświetlenie przypisanych zadań zlecenia pracy w widoku kalendarza.
- Służy do tworzenia, wyświetlania i edytowania zadania zlecenia pracy, aktualizowania liczników składników majątku, wyświetlania listy kontrolnej konserwacji, wyświetlania i edytowania notatek o zadaniach zleceń pracy, wyświetlania narzędzi wymaganych dla zadania zlecenia pracy.
- Służy do wyświetlania lub wyszukiwania określonego składnika majątku lub lokalizacji czynności konserwacyjnych.


## <a name="prerequisites"></a>Wymagania wstępne

Wymagania wstępne różnią się w zależności od wersji programu Dynamics 365 Supply Chain Management wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a>Warunki wstępne w przypadku korzystania z Microsoft Dynamics 365 Supply Chain Management 
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 Supply Chain Management, administrator systemu musi opublikować mobilny obszar roboczy **Zarządzanie składnikami majątku**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej
Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

- [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej
1. Uruchom aplikację na urządzeniu komórkowym.

2. Wprowadź adres URL usługi Dynamics 365.

3. Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.

4. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, należy odświeżyć listę mobilnych obszarów roboczych.

![Rysunek 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Umożliwia wyświetlenie przypisanych zadań zlecenia pracy w widoku kalendarza

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Kalendarz zadań zlecenia pracy**

3. Wybierz datę, dla której mają zostać wyświetlone zadania zlecenia pracy. Na liście widoczny jest identyfikator składnika majatku i identyfikator lokalizacji czynności konserwacyjnych dla każdego zadania zlecenia produkcyjnego.

4. Wybierz zadanie zlecenia pracy na liście, aby wyświetlić szczegóły zadania: szczegóły dotyczące składnika majątku i lokalizacji czynności konserwacyjnych oraz inne łącza nawigacji, które umożliwiają wyświetlanie **Załączników**, **List kontrolnych**, **Narzędzi**, **Liczników składników majatku**, **Notatek**, **Arkuszy**.

![Rysunek 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a>Tworzenie zadania zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

3. Wybierz zlecenie pracy, dla którego chcesz utworzyć nowe zadanie zlecenia pracy.

4. Wybierz przycisk **Dodaj wiersz**.

5. Wybierz **Składnik majątku**, dla którego chcesz utworzyć nowe zadanie zlecenia pracy.

6. Wybierz **Typ zadania konserwacji**, **Wariant typu zadania konserwacji** i **Profesja**.

7. Wybierz opcję **Gotowe**.

![Rysunek 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a>Dodawanie załącznika do zadania zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

3. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz dodać załącznik.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **Szczegóły zadania zlecenia pracy**.

4. Wybierz **Załączniki** na stronie **Szczegóły zadania zlecenia pracy**.

5. Zostaną wyświetlone istniejące załączniki dla zadania zlecenia pracy Wybierz **Dodaj załącznik**.

6. Wprowadź **Nazwę** i **Notatki** dotyczące załącznika.

7. Wybierz **Wybierz obraz**, aby wybrać zdjęcie z galerii mobilnej, lub **Zrób zdjęcie**, aby zrobić zdjęcie.

8. Wybierz opcję **Gotowe**.

![Rysunek 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Przeglądanie listy kontrolnej konserwowanego składnika majątku w zadaniu zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

3. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz zobaczyć listę kontrolną.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **szczegóły zadania zlecenia pracy**.

4. Wybierz **Listy kontrolne** na stronie **Szczegóły zadania zlecenia pracy**.

5. Zostanie wyświetlona lista wierszy listy kontrolnej powiązanych z zadaniem zlecenia pracy. Wybierz wiersz listy kontrolnej w celu wyświetlenia **Instrukcji** i dodania **Notatek**.

6. Kliknij przycisk wstecz (**<**), aby wrócić do poprzedniej strony.

![Rysunek 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Wyświetlanie i aktualizowanie liczników składników majątku w zadaniu zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

3. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz zobaczyć licznik składników majątku.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **szczegóły zadania zlecenia pracy**.

4. Wybierz **Liczniki składników majątku** na stronie **Szczegóły zadania zlecenia pracy**.

5. Zostanie wyświetlona lista liczników składników majątku powiązanych z zadaniem zlecenia pracy. Wybierz ikonę ołówek w wierszu licznika składników majątku, aby zaktualizować wartość licznika.

6. Wprowadź nową wartość licznika i wybierz **Gotowe**.

![Rysunek 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a>Rejestrowanie zużycia w zadaniu zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

3. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz zobaczyć rejestrację zużycia.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **szczegóły zadania zlecenia pracy**.

4. Wybierz **Arkusze** na stronie **Szczegóły zadania zlecenia pracy**.

5. Wybierz opcję **Dodaj godziny**, aby utworzyć rejestracje godzin pracy.
    1. Wybierz **Kategoria** w polu wyszukiwania.
    2. W polu **Godziny** wprowadź liczbę godzin pracy, jaka przypada na zadanie zlecenia pracy.
    3. Wybierz odpowiednią **Właściwość wiersza**.
    4. Wybierz opcję **Gotowe**.

6. Wybierz opcję **Dodaj pozycje**, aby utworzyć rejestracje pozycji.
    1. Wybierz **Kod towaru** w polu wyszukiwania.
    2. Wybierz **Lokalizacja** w polu wyszukiwania.
    3. Wprowadź **Ilość** zużytych towarów.
    4. Wybierz opcję **Gotowe**.

7. Wybierz opcję **Dodaj wydatek**, aby utworzyć rejestracje wydatków.
    1. Wybierz **Kategoria** w polu wyszukiwania.
    2. Umożliwia wprowadzenie ilości dla rejestracji wydatków.
    3. Wybierz **Waluta sprzedaży** w polu wyszukiwania.
    4. Umożliwia wprowadzenie **Kosztu własnego** dla rejestracji wydatków.
    5. Wybierz opcję **Gotowe**.

![Rysunek 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a>Aktualizuj stan cyklu życia zlecenia pracy.

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

3. Wybierz zlecenie pracy, dla którego chcesz aktualizować stan cyklu życia.

4. Wybierz przycisk **Aktualizuj stan** w dolnej części ekranu.

5. Wybierz nowy stan cyklu życia z listy.

6. Wybierz opcję **Gotowe**.

![Rysunek 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a>Tworzenie żądania konserwacji

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie żądania konserwacji**.

3. Wybierz **Akcje** u dołu ekranu i wybierz opcję **Utwórz żądanie konserwacji**.

4. Jeśli dla żądań konserwacji w module **Zarządzanie składnikami majątku** jest włączona sekwencja numerów, pole **Żądanie konserwacji** jest ukryte, ponieważ jest ono wypełniane automatycznie. Jeśli pole **Żądanie konserwacji** jest widoczne, należy wprowadzić identyfikator żądania konserwacji.

5. Wybierz **Typ żądania konserwacji**.

6. Wprowadź **Opis** żądania konserwacji.

7. Wybierz **Składnik majątku**, dla którego mają być tworzone żądania.

8. Wybierz **Poziom usług** dla żądania konserwacji.

9. Wybierz opcję **Gotowe**.

![Rysunek 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a>Dodaj załącznik do żądania konserwacji

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

2. Wybierz **Wszystkie żądania konserwacji**.

3. Wybierz żądanie konserwacji, do którego chcesz dodać załącznik.

4. Wybierz **Załączniki** w dolnej części ekranu.

5. Wybierz **Dodaj załączniki**.

6. Wprowadź **Nazwę** i **Notatki** dotyczące załącznika.

7. Wybierz **Wybierz obraz**, aby wybrać zdjęcie z galerii mobilnej, lub **Zrób zdjęcie**, aby zrobić zdjęcie.

8. Wybierz opcję **Gotowe**.

![Rysunek 10](media/am-mobile-10.png)

