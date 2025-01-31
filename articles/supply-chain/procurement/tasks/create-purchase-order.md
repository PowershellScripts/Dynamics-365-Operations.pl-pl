---
title: Tworzenie zamówienia zakupu
description: W tym temacie pokazano sposób ręcznego tworzenia zamówienia sprzedaży.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec91174f291bcfa7027a93ca344823561cc29e3f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435617"
---
# <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób ręcznego tworzenia zamówienia sprzedaży. Najczęściej zamówienia zakupu są tworzone automatycznie jako rezultat planowania głównego, dostawy bezpośredniej i innych procesów. W przypadku tworzenia ręcznego najczęściej robi to pracownik działu zakupów. W pokazanym tutaj przykładzie można użyć firmy demonstracyjnych USMF, podstawiając wartości sugerowane w notatkach do poszczególnych kroków.


## <a name="create-the-purchase-order-header"></a>Tworzenie nagłówka zamówienia zakupu
1. Wybierz kolejno **okienko nawigacji> Moduły > Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu**.
2. Wybierz pozycję **Nowy**.
3. Wybierz konto dostawcy **US-101**. Kiedy wybierzesz dostawcę, szczegóły z jego rekordu, takie jak adres, konto płatnika, warunki dostawy i metoda dostawy, zostaną skopiowane jako wartości domyślne do nagłówka zamówienia. Wartości te można zmienić w dowolnym momencie.  
4. Rozwiń sekcję **Ogólne**.

    - Pole **Oddział** wraz z polem **Magazyn** określa, dokąd należy dostarczyć kupowane towary lub usługi. Domyślnym adresem dostawy jest oddział. Oba pola mogą być wypełnione wartościami skonfigurowanymi dla wybranego dostawcy lub można je określić ręcznie.  
    - Pole **Data dostawy** jest używane do określenia, kiedy kupione towary i usługi muszą zostać dostarczone. Można określić jedną datę dostawy dla całego zamówienia lub unikatowe daty dostawy dla poszczególnych wierszy zamówienia. Jeśli data dostawy określona w tym polu nie może zostać dotrzymana dla określonych produktów lub usług, ponieważ mają one dłuższe czasy realizacji, te wiersze zostaną utworzone z odpowiednimi późniejszymi datami dostawy.  

5. Rozwiń sekcję **Administracja**. Pole **Zamawiający** może służyć do określania, kto składa zamówienie. Może być wygodne udostępnienie tej informacji dostawcy w przypadku, gdy musi się on skontaktować z tą osobą. Wartość w polu może być przypisywana automatycznie, jeśli konto bieżącego użytkownika jest skojarzone z nazwą na stronie **Użytkownicy**.  
6. Kliknij przycisk **OK**. Został utworzony nagłówek zamówienia. Podczas pracy z wierszami zamówienia zakupu jest wyświetlane tylko podsumowanie informacji nagłówka. Aby wyświetlić pozostałe informacje, wybierz **Nagłówek**.  

## <a name="add-a-purchase-order-line"></a>Dodawanie wiersza zamówienia zakupu
1. Wybieranie **Wiersz zamówienia zakupu**.
2. Wybierz ​**Wymiary**. Produkty mogą być w wariantach zróżnicowanych według wymiarów, takich jak kolor, rozmiar lub styl. Produkty mogą być również skonfigurowane do używania wymiarów magazynowania, takich jak oddział i magazyn. Istnieją również opcjonalne wymiary śledzenia, takie jak numery partii i numery seryjne. Aby zwiększyć efektywność wprowadzania zamówień, można dodać pola często używanych wymiarów bezpośrednio do siatki zamówień.  
3. Zaznacz pole wyboru **Kolor**. Opcjonalnie: Jeśli zaznaczysz pole **Zapisz ustawienia**, przy następnym otwarciu strony zamówienia zakupu wybrane wymiary będą wyświetlane również w siatce wierszy zamówienia.  
4. Kliknij przycisk **OK**.
5. W polu **Numer pozycji** wybierz wartość **T0004**.

    - Wiersze zamówienia są tworzone dla produktów i usług przez określenie numeru towaru lub jako koszty przez określenie kategorii zaopatrzenia. 
    - Pole kategorii **Zaopatrzenie** służy do dodawania wierszy, gdzie kupowane towary są zaliczane w koszty bezpośrednio, a nie kierowane do zapasów. Oznacza to, że jeśli trzeba zaliczyć zamówienie zakupu w koszty, można to zrobić przez utworzenie wiersza zamówienia zakupu określającego kategorię zaopatrzenia zamiast przez tworzenie wiersza z numerem towaru. Towary mogą być także skojarzone z kategorią zaopatrzenia i w takim przypadku kategoria zaopatrzenia jest wyświetlana tylko informacyjnie.  

6. W polu **Kolor** wprowadź lub wybierz wartość. Pola **Oddział** i **Magazynu** zazwyczaj są wypełniane wartościami z nagłówka zamówienia, ale można zastąpić te wartości, jeśli pozycje niektórych wierszy muszą zostać dostarczone do innych lokalizacji.  
7. W polu **Ilość** wpisz liczbę.

    - Zaznacz ilość, jaką chcesz kupić. W polu **Ilość** jest automatycznie wpisywana minimalna ilość zamówienia na produkt, jeśli ją skonfigurowano lub wartość 1.  
    - Pole **Jednostka** wskazuje jednostkę miary zamówionej ilości. Zazwyczaj jednostka jest wprowadzana automatycznie na podstawie jednostki zakupu z danych głównych produktu, ale można ją zmienić.  
    - Pole **Cena jednostkowa** zazwyczaj zawiera wartości z umowy zakupu lub umowy handlowej. Istnieje możliwość zmiany ceny jednostkowej w poszczególnych wierszach zamówienia, na przykład jeśli specjalna cena została wynegocjowana z dostawcą.  
    - Pole **Rabat** zawiera kwotę rabatu na jednostkę. O ten rabat jest pomniejszana cena jednostkowa. Rabat zazwyczaj jest wstawiany automatycznie z umów zakupu lub umów handlowych, ale istnieje możliwość ręcznego zastąpienia wartości w poszczególnych wierszach, jeżeli wynegocjowano z dostawcą inne rabaty.  
    - Można wprowadzić procent rabatu, który zmniejsza kwotę netto w wierszu. Procent rabat zazwyczaj jest często automatycznie z umów zakupu lub umów handlowych, ale istnieje możliwość ręcznego zastąpienia wartości w poszczególnych wierszach, jeżeli wynegocjowano z dostawcą inny procent rabatu.  
    - Wartość w polu **Kwota netto** jest obliczana na podstawie innych pól wiesza, w tym ilości, ceny jednostkowej, rabatu i procentu rabatu. Istnieje możliwość zmiany kwoty netto, ale wtedy pola **Cena jednostkowa**, **Rabat** i **Procent rabatu** będą puste, a podczas księgowania względem wiersza zaksięgowana kwota będzie proporcjonalna do kwoty netto. Zwykle do wyświetlania kwoty netto w wierszu jest używane pole **Kwota netto**.  

8. Rozwiń sekcję **Szczegóły wiersza**.
9. Wybierz kartę **Dostawa**. Do każdego wiersza zamówienia można przypisać unikatową datę dostawy. Data jest dziedziczona z pola w nagłówku zamówienia zakupu, ale można ją zmienić.  

## <a name="review-order-totals"></a>Przegląd sum zamówienia
1. Wybierz **Sumy**.

    - Jeśli nie widać akcji **Sumy**, w okienku akcji wybierz kartę **Zamówienie zakupu**.  
    - To okno dialogowe pokazuje sumy dla całego zamówienia.  
    - Pole **Wybór** umożliwia zmianę podstawy obliczania sum. Na przykład można wybrać opcję **Ilość z dokumentu przyjęcia produktów**, aby pokazać sumy odnoszące się do przetworzonych ilości produktów, lub opcję **Ilość zamówiona**, aby pokazać zamówioną ilość produktu.  

2. Kliknij przycisk **OK**.

