---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (31 października 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4851c62a19bb562c7f5f578aecbae99cfcdb982f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462247"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-31-2018"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (31 października 2018 r.)

**Kompilacja 8.1.2031**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="create-links-from-talent-to-finance"></a>Tworzenie łączy z rozwiązania Talent do rozwiązania Finance
Ta nowa funkcja nawigacji pozwala utworzyć łącze z aplikacji Talent do aplikacji Finance, co umożliwi bezpośrednie przechodzenie do stron aplikacji Finance. Podczas konfigurowania łączy można określić nazwę i grupę łącza, miejsce wyświetlania łącza w aplikacji Talent oraz stronę docelową otwieraną w aplikacji Finance.

#### <a name="coming-soon"></a>Wkrótce
W przyszłości zostanie dodany kontekst pola, aby umożliwić bezpośrednie przechodzenie do odpowiednich rekordów w aplikacji Finance. Na przykład można użyć opcji **Łącze do pola**, aby dostarczyć kontekst umożliwiający przechodzenie bezpośrednio do określonego pracownika lub stanowiska w aplikacji Finance.

### <a name="configure-target-systems"></a>Konfigurowanie systemów docelowych

W aplikacji Talent administratorzy systemu mogą definiować łącza, które będą widoczne w obszarze roboczym Administrowanie systemem. Częścią konfiguracji jest środowisko aplikacji Finance, do którego chcesz przejść jako do „lokalizacji docelowej” łącza. W tym celu trzeba nadać systemowi docelowemu nazwę oraz podać adres URL środowiska aplikacji Finance. Oto przykładowy adres URL prowadzący do środowiska Finance, który należałoby podać: https://devax00124aos.cloud.test.dynamics.com/. Po skonfigurowaniu systemów docelowych można zdefiniować łącza.

### <a name="configure-links"></a>Konfiguruj łącza

Każde tworzone łącze będzie miało zdefiniowane następujące informacje.

- Łącze — nazwa łącza, używana tylko do identyfikacji.

- Włącz to łącze — ustaw wartość **Tak**, jeśli łącze ma być wyświetlane użytkownikom aplikacji Talent.

- Nazwa wyświetlana — podaj nazwę, która ma być wyświetlana jako łącze do aplikacji Finance. Te dane obecnie nie są tłumaczone.

- Pokaż łącze na wierzchu w formularzu — wybierz stronę, na której łącze ma być wyświetlane.

- Grupa — grupy nie są wymagane, ale jeśli chcesz uporządkować łącza w grupy, zaznacz istniejącą grupę lub utwórz nową przy użyciu pola **Grupa**.

- System docelowy — wybierz docelowy system, który został utworzony za pomocą opcji **Konfiguruj system docelowy**. Jest to środowisko programu Finance, które będzie używane podczas nawigowania przy użyciu tego łącza.

- Użyj bieżącej firmy użytkownika — wybierz wartość **Tak**, jeśli chcesz używać kontekstu bieżącej firmy użytkownika przy przechodzeniu do aplikacji Finance. Jeśli zaznaczysz wartość **Nie**, to można wybrać firmę, która ma być używana.

- Element menu docelowego — wprowadź element menu z aplikacji Finance, którego łącze ma używać podczas nawigowania. Dostępne są elementy menu, do których można przechodzić bezpośrednio. Aby znaleźć wymagany element menu, otwórz aplikację Finance, a następnie otwórz stronę będącą lokalizacją docelową nawigacji. Skopiuj element menu z adresu URL. Na przykład jeśli chcesz, aby łącze prowadziło do listy pracowników etatowych w aplikacji Finance and Operations, wprowadź wartość widoczną po elemencie „&mi” w adresie URL. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. Elementem menu powodującym przejście do strony z listą pracowników w tym przykładzie jest HcmWorkerListPage_Employees.

- Łącze do źródła danych — wybierz źródło danych, do którego odwołuje się łącze. Dostępne są najczęściej używane źródła, takie jak **Pracownik** i **Stanowisko**.

- Łącze do pola — (wkrótce) To pole umożliwi bezpośrednie przejście z jednego rekordu w aplikacji Talent do jednego rekordu w aplikacji Finance.

### <a name="access-to-links"></a>Dostęp do łączy

Administratorzy systemu będą widzieć nowo utworzone łącza na wskazanych stronach nawet wtedy, gdy opcja **Włącz to łącze** jest ustawiona na **Nie**. Ten mechanizm może służyć do testowania łączy przed ich udostępnieniem innym pracownikom. Posiadacze wszystkich pozostałych ról będą widzieć skonfigurowane łącza tylko wtedy, gdy opcja **Włącz to łącze** jest ustawiona na **Tak**. Pracownicy mający dostęp do stron, w których łącza są wyświetlane, będą mogli używać tych łączy.

Użytkownicy mogą również mieć zdefiniowane w aplikacji Finance prawa zabezpieczeń umożliwiające dostęp do stron wewnątrz aplikacji Finance and Operations. Jeśli tak nie jest, po kliknięciu łącza pojawi się okno dialogowe mówiące o zabezpieczeniach.


## <a name="other-changesfixes"></a>Inne zmiany/poprawki

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>Nowym pracownikom nie można przypisywać stanowisk z przyszłą datą rozpoczęcia

Wprowadzono zmiany mające umożliwić przypisywanie pracowników do stanowisk z datą przyszłą. Teraz można wybierać stanowiska z datą rozpoczęcia przypadającą w przyszłości, a przypisanie pracownika zostanie dokonane po zapisaniu lub ukończeniu przepływu pracy (jeśli funkcjonalność przepływu pracy jest włączona).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>Nowych pracowników nie można przypisywać do istniejących stanowisk

Wprowadzono zmiany, tak aby nowych pracowników można było przypisywać do istniejących stanowisk.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>Pole Data stażu pracy/Lokalizacja biura znika po zapisaniu rekordu, gdy data rozpoczęcia zatrudnienia przypada w przeszłości

Wprowadzono zmiany poprawiające widoczność pól **Data stażu pracy** i **Lokalizacja biura** podczas zapisywania zmian dla byłych pracowników.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>Na stronie pracownika nie można wprowadzić danych dla zatrudnienia z datą przyszłą

Na stronie głównej pracownika wyłączono funkcjonalność danych dla zatrudnienia rozpoczynającego się w przyszłości. Dane dotyczące zatrudnienia można wprowadzić na stronach **Menedżera dat**. W przyszłych wersjach zostaną wprowadzone dodatkowe zmiany pozwalające wprowadzać dane zatrudnienia bezpośrednio w przepływie pracy.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>Dodanie pól ValidFrom i ValidTo do jednostki HcmPersonalContactPersonEntity

W programie Data Management Framework (DMF) w jednostce HcmPersonalContactPersonEntity dodano pola dat „ważne od” i „ważne do”, aby umożliwić realizację pewnych scenariuszy integracji świadczeń. 

## <a name="known-issue"></a>Znany problem
- **Problem**: Podczas dodawania nowego załącznika do pracownika przyciski **Nowy** i **Edytuj** są wyszarzone. 
- **Obejście:** Przed otwarciem strony załącznika upewnij się, że pola informacji na stronie **Pracownik** są zamknięte. Jeśli pola informacji są zamknięte podczas wczytywania strony **Pracownik**, przyciski złączników będą włączone. (Ten problem zostanie rozwiązany w następnej aktualizacji platformy).
