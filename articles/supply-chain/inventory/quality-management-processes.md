---
title: Procesy zarządzania jakością
description: Ten artykuł zawiera informacje o procesie zarządzania jakością produktów niespełniającymi norm. Opisano w nim, jak korzystać z funkcji kontroli jakości, jak definiować i obsługiwać braki zgodności oraz jak obsługiwać korekty.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 11574
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ab3b886b9d5237e96e193d7369c6060f19516e5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435498"
---
# <a name="quality-management-processes"></a>Procesy zarządzania jakością

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o procesie zarządzania jakością produktów niespełniającymi norm. Opisano w nim, jak korzystać z funkcji kontroli jakości, jak definiować i obsługiwać braki zgodności oraz jak obsługiwać korekty.

Zapewnienie jakości polega na testowaniu produktu i zarządzaniu materiałami niespełniającymi norm. Procesy zarządzania jakością zapewniają wysoki poziom jakości produktu w łańcuchu dostaw. Procesy te umożliwiają także optymalizowanie procesów łańcucha dostaw i zwiększają zadowolenie klientów. Zarządzanie jakością pomaga przy zarządzaniu czasem przetwarzania, kiedy masz do czynienia z produktami niespełniającymi norm, bez względu na pochodzenie tych produktów. Zadania korekty można połączyć z wynikami diagnostyki. System można zaplanować zadania, aby naprawić problemy i w ten sposób zapobiec powtórzeniu tych problemów w przyszłości. Zarządzanie jakością umożliwia też śledzenie problemów (w tym problemów wewnętrznych) według typu problemu i pozwala na określenie rozwiązań jako krótkoterminowych lub długoterminowych. Statystyki kluczowych wskaźników wydajności (KPI) pokazują problemy z niezgodnością, które wystąpiły wcześniej, i rozwiązania, które zostały zastosowane do ich korekty. Korzystając z danych historycznych można sprawdzić skuteczność pomiarów jakości, które zostały wcześniej przeprowadzone, i określić odpowiednie rozwiązania na przyszłość.

## <a name="controlling-the-quality-management-process"></a>Kontrolowanie procesu zarządzania jakością
Oto kilka sposobów kontrolowania procesu zarządzania jakością:

-   Tworzenie zleceń kontroli jakości na podstawie punktów wyzwalania, takich jak „przy odbiorze produktu” dla operacji przychodzących lub „przy pobraniu produktu” dla operacji wychodzących.
-   Dokumentowanie wyników testu i określenie, czy spełniają założone kryteria oraz akceptowane poziomy jakości.
-   Korzystanie z zarządzania dokumentami szczegółowych specyfikacji produktu i notatkami użytkownika w ramach raportowania podczas procesu inspekcji.
-   Obsługa niezgodnych produktów i skorelowanie tych produktów z dodatkowymi informacjami o niezgodności w celu śledzenia pierwotnych przyczyn problemu.
-   Dokumentowanie kosztów zarządzania niezgodnością. Koszty te mogą się wiązać z towarami (jak części zapasowe), opłatami dodatkowymi i wiążą się z towarami, opłatami dodatkowymi i godzinami pracy poświęconymi na korygowanie niezgodności.
-   Planowanie procesów korekty niezgodności przy użyciu narzędzia do korekty powiązanego ze zleceniem kontroli jakości.

[![Proces zarządzania jakością](./media/quality-management-process-diagram.png)](./media/quality-management-process-diagram.png)  

## <a name="product-testing-and-quality-orders"></a>Testowanie produktu i zlecenia kontroli jakości
Testowanie produktu jest zazwyczaj nazywane kontrolą jakości i wymaga zastosowania zleceń kontroli jakości. Za pomocą funkcji kontroli jakości, można wykonać następujące czynności:

-   Określenie wymaganych testów materiału. Testy te uwzględniają testy zgodności ze specyfikacjami jakości, narzędzie testowe, dokumenty z opisem testu, plan pobierania próbek i akceptowane poziomy jakości;
-   Tworzenie zlecenia kontroli jakości określającego testy, które trzeba wykonać w wypadku określonego zlecenia (zlecenia zakupu lub zlecenia produkcyjnego) lub określonej ilości magazynowej. Zlecenie kontroli jakości można utworzyć ręcznie, można je także wygenerować automatycznie na podstawie wymagań jakościowych.
-   Definiowanie wymagań jakościowych w każdym procesie biznesowym (dotyczące zleceń zakupu, kwarantanny, zleceń produkcyjnych i zleceń sprzedaży) w celu automatycznego generowania zlecenia kontroli jakości, w którym zdefiniowano wymagania dotyczące testowania materiału przychodzącego i wychodzącego;
-   Rejestrowanie wyników testów w ramach zlecenia kontroli jakości, sprawdzanie poprawności wyników testów na podstawie akceptowanego poziomu jakości i drukowanie certyfikatu analizy zawierającego wyniki testów.

## <a name="nonconformance"></a>Niezgodność
Niezgodność dotyczy towaru, odnośnie do którego wykryto problem związany z jakością. W procesie niezgodności można utworzyć zlecenie kontroli niezgodności opisujące ilość materiału niespełniającego norm, źródło problemu, typu problemu i informacje wyjaśniające. Można definiować klasyfikację typów problemów w celu ułatwienia analizy materiału niespełniającego norm. Można również wydrukować znacznik niezgodności i raport o niezgodności do dyspozycji materiału niespełniającego norm. Na przykład, znacznik i raport może wskazywać warunek **nienadający się do użytku** lub **ograniczone użycie**.

W poniższej tabeli wymieniono sześć domyślnych typów niezgodności i opisano informacje, które muszą być rejestrowane dla każdego typu.

| Typ niezgodności   | Informacje źródłowe                                                                                                                                                                                                                          |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Klient              | Numer konta odbiorcy, numer zamówienia sprzedaży lub numer partii odnośnie do transakcji zamówienia sprzedaży. Niezgodność może dotyczyć na przykład określonej dostawy zamówienia sprzedaży lub być oparta na uwagach o jakości produktu otrzymanych od odbiorcy.       |
| Zlecenie usługi       | Numer konta odbiorcy, numer zamówienia sprzedaży lub numer partii odnośnie do transakcji zamówienia sprzedaży. Niezgodność może dotyczyć na przykład określonej dostawy zamówienia sprzedaży lub być oparta na skardze odbiorcy dotyczącej jakości towaru.     |
| Dostawca                | Numer konta dostawcy, numer zamówienia zakupu lub numer partii odnośnie do transakcji zamówienia zakupu. Niezgodność może dotyczyć na przykład przyjęcia zamówienia zakupu lub obaw dostawcy wiążących się z określoną dostarczaną częścią. |
| Produkcja            | Numer zlecenia produkcyjnego lub numer transakcji zlecenia produkcyjnego. Niezgodność może dotyczyć na przykład określonej partii wyprodukowanych towarów.                                                                      |
| Wewnętrzne              | Numer zlecenia kontroli jakości lub numer transakcji zlecenia kontroli jakości. Niezgodność może dotyczyć na przykład testów przeprowadzanych w ramach zlecenia kontroli jakości lub obaw pracownika odnośnie do jakości produktu.     |
| Wytwarzanie produktu towarzyszącego | Niezgodność produktu towarzyszącego zleceniu produkcyjnemu, związana z zadaniem wsadowym zleceń produkcyjnych.                                                                                                                                                    |

Niezgodności są skojarzone z typem problemu. Typy problemów są definiowane na stronie **typów problemów**, gdzie można określić typy problemów, które mogą być skojarzone z poszczególnymi typami niezgodności. Na przykład typy problemów związanych z niezgodnością **Zlecenia usługi** mogą odzwierciedlać klasyfikację skarg odbiorców, a typy problemów związanych z niezgodnością typu **Wewnętrzna** — klasyfikację kodów wad.

Na etapie tworzenia nowej niezgodności można wybrać jej typ oraz typ problemu. Początkowy stan zatwierdzenia ma wartość **Nowe**, co oznacza żądanie akcji. Kolejnym krokiem jest zmiana stanu zatwierdzenia na **Zatwierdzono** lub **Odrzucono**, co oznacza odpowiednio zamiar podjęcia działania dotyczącego niezgodności lub brak takiego zamiaru. Możliwe jest również zamknięcie niezgodności (za pomocą oddzielnego pola wyboru), co oznacza zakończenie prac nad nią, a także ponowne jej otwarcie — sygnalizujące, że wymagana jest dalsza analiza.

Można wprowadzić komentarze dotyczące niezgodności przez dołączanie dokumentu. Warto określić niepowtarzalny typ dokumentu dla niezgodności na stronie **Typ dokumentu**. Następnie można użyć strony **Konfiguracja raportu**, aby określić, czy komentarze dla tego typu dokumentu mają być drukowane w raporcie niezgodności, a także znacznik niezgodności. Wydrukowanie raportu dotyczącego zgodności i znacznika niezgodności ułatwia proces dyspozycji materiałów. Raporty i znaczniki można generować wybiórczo na podstawie powiązanych z daną niezgodnością kryteriów wyboru. Te kryteria obejmują numer niezgodności, towar, odbiorcę, dostawcę i stan.

Raport dotyczący niezgodności zawiera numer niezgodności, towar i typ problemu. W zależności od ustawienia zasad raportu raport może być również pokazywać powiązane notatki dotyczące niezgodności. Znacznik niezgodności pokazuje podobne informacje i zawiera dane o strefie i typie kwarantanny (na przykład **Ograniczone użycie** albo **Nienadający się do użytku**), które pomagają w rozdysponowaniu wadliwych materiałów.

## <a name="approved-nonconformance"></a>Zatwierdzanie braku zgodności
Opcjonalnie można zdefiniować jedną lub więcej powiązanych operacji dla zatwierdzonej niezgodności. Operacja powiązana opisuje pracę, która powinna być wykonywana, i zawiera listę operacji kontroli jakości, które zostały zdefiniowane, a także tekst opisujący przyczynę pracy. Po zdefiniowaniu operacji można opcjonalnie zdefiniować towary, opłaty dodatkowe oraz godziny w grafiku wymagane do wykonania operacji. Wyświetlane są obliczone koszty operacji pokrewnej oraz łączne obliczone koszty braku zgodności. Obliczone koszty i związane z tym szczegóły (o towarach, godzinach pracy i opłatach dodatkowych) pokazują informacje dodatkowe, i są używane tylko w przypadku funkcji zarządzania jakością.

Opcjonalnie można utworzyć zlecenia kontroli jakości z braku zgodności poprzez utworzenie zapytania dla zlecenia kontroli jakości, a następnie utworzenie nowego zlecenia kontroli jakości. Zlecenie kontroli jakości może na przykład wskazywać potrzebę testowania (lub ponownego przetestowania) wadliwych materiałów. Nowo utworzone zlecenie kontroli jakości zawiera łącze do źródłowego braku zgodności.

Opcjonalnie można połączyć wybraną niezgodność z inną i utworzyć nową niezgodność na podstawie istniejącej. Na przykład łącze może odzwierciedlać powiązania między problemami dotyczącymi jakości.

## <a name="correction-handling"></a>Obsługa korekty
Strona **Korekty** pozwala utworzyć listę niezgodności, które muszą zostać poprawione. Każdy element korekty jest skojarzony z typem diagnostyki, który spowodował wykrycie problemu. Strona **Korekty** zawiera również informacje, kto ma podjąć działania naprawcze i kiedy. Można opisać szczegóły problemu oraz wymagane działania naprawcze poprzez dołączenie dokumentu do korekty. Po skierowaniu lub korekcie niezgodności można ją zamknąć, wybierając opcję **zakończone**. Można także wskazać, że rozwiązanie jest rozwiązaniem krótkoterminowym.

Warto określić niepowtarzalny typ dokumentu dla korekty na stronie **Typ dokumentu**. Następnie można użyć strony **Konfiguracja raportu**, aby określić, czy komentarze dla tego typu dokumentu mają być drukowane w raporcie korekty. Wydrukowany raport korekty zawiera informacje o braku zgodności i pokrewne notatki. Raport zawiera także informacje dotyczące korekty, takie jak typ diagnostyki i notatki dotyczące korekty.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie zarządzanie jakością](enable-quality-management.md)

[Zarządzanie brakiem zgodności](enable-nonconformance-management.md)

[Blokowanie zapasów](inventory-blocking.md)

[Zlecenia kwarantanny](quarantine-orders.md)

[Konfigurowanie zleceń kontroli jakości](tasks/set-up-quality-orders.md)

[Sprawdzenie jakości towarów](tasks/inspect-quality-goods.md)
