---
title: Omówienie zarządzanie jakością
description: W tym temacie opisano, jak za pomocą funkcji zarządzania jakością w Dynamics 365 Supply Chain Management poprawiać jakość produktów w łańcuchu dostaw.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1d7828e6bb9a3684c1d76e2cfac96174a8dfbf4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435295"
---
# <a name="quality-management-overview"></a>Omówienie zarządzanie jakością

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak za pomocą funkcji zarządzania jakością w Dynamics 365 Supply Chain Management poprawiać jakość produktów w łańcuchu dostaw.

Zarządzanie jakością pomaga przy zarządzaniu czasem przetwarzania, kiedy masz do czynienia z produktami niespełniającymi norm, bez względu na pochodzenie tych produktów. Ze względu na to, że typy diagnostyki są powiązane z raportowaniem korekt, rozwiązanie Supply Chain Management może zaplanować zadania naprawiania problemów i zapobiegania ich ponownemu występowaniu.

Oprócz funkcji związanych z zarządzaniem brakiem zgodności zarządzanie jakością zawiera funkcje monitorowania błędów według typu problemu (łącznie z błędami wewnętrznymi) i identyfikowania rozwiązań krótko- i długoterminowych. Statystyki kluczowych wskaźników wydajności (KPI) pokazują historię wcześniejszych problemów z brakiem zgodności i rozwiązania, które zostały zastosowane do ich korekty. Korzystając z danych historycznych można sprawdzić skuteczność pomiarów jakości, które zostały wcześniej przeprowadzone, i określić odpowiednie rozwiązania na przyszłość.

Po skonfigurowaniu powiązania jakości rozwiązanie Supply Chain Management może generować zlecania kontroli jakości dla różnych procesów biznesowych, zdarzenia i warunki. Skojarzenia jakości mogą obejmować określone pozycje, grupy towarów lub wszystkie pozycje.

## <a name="examples-of-the-use-of-quality-management"></a>Przykłady korzystania z funkcji zarządzania jakością
Zarządzanie jakością jest elastyczne i może być implementowane na różne sposoby, aby spełnić wymagania określonych poziomów operacji łańcucha dostaw. Poniższe przykłady ilustrują możliwe wykorzystanie tych funkcji:

-   Automatyczne uruchamianie procesu kontroli jakości, na podstawie wstępnie zdefiniowanych kryteriów (przy rejestracji magazynu zamówienia zakupu od określonego dostawcy).
-   Blokowanie zapasów podczas inspekcji, aby zapobiec używaniu niezatwierdzonych zapasów (całkowite blokowanie ilości zamówienia zakupu).
-   Używanie kontroli wyrywkowej pozycji w ramach powiązania jakości do określenia kwoty bieżących zapasów fizycznych, które muszą być poddane inspekcji. Kontrola wyrywkowa może dotyczyć stałej ilości lub części określonej procentowo lub pełnego numeru identyfikacyjnego.

> [!NOTE]
> Funkcja _Zarządzanie jakością dla procesów magazynowych_ rozszerza możliwości zarządzania jakością. Jeśli ta funkcja jest używana, zobacz [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md), aby przejrzeć przykłady sposobu działania funkcji zarządzania jakością, gdy jest ona włączona.

-   Tworzenie zleceń kontroli jakości dla przyjęć częściowych. Aby utworzyć zlecenie kontroli jakości oparte na ilości fizycznie przyjętej względem zamówienia, należy zaznaczyć pole wyboru **Dla zaktualizowanej ilości** w formularzu **Kontrola wyrywkowa towarów**.
-   Tworzenie typów testów zawierających minimalne, maksymalne i docelowe wartości testu, i testowanie jakościowe vs ilościowe ze wstępnie zdefiniowanymi wynikami weryfikacji.
-   Określanie akceptowanego poziomu jakości (AQL) do kontrolowania tolerancji pomiaru jakości.
-   Określanie zasobów wymaganych do operacji inspekcji, takich jak obszar testowy i przyrządy testowe.

## <a name="working-with-quality-associations"></a>Korzystanie ze skojarzeń jakości
Proces biznesowy, który używa skojarzeń jakości może być powiązany z różnymi dokumentami źródłowymi, takimi jak zamówienia zakupu, zamówienia sprzedaży lub zlecenia produkcyjne.

Poszczególne rekordy skojarzenia jakości określają serie testów, akceptowany poziom jakości i plan próbkowania dotyczące generowanych zleceń kontroli jakości. Należy określić rekord skojarzenia jakości dla każdego odchylenia w procesie biznesowym. Na przykład można skonfigurować skojarzenia jakości, które generuje zlecenia kontroli jakości podczas aktualizowania dokumentu przyjęcia produktów. W zależności od ustawień planu wykonania, można zablokować sam proces uruchomienia, gdy jest otwarte zlecenie kontroli jakości, lub następne procesy, takie jak fakturowanie zamówień zakupu.

**Uwaga:** jeśli są otwarte zlecenia kontroli jakości, ilości zapasów są automatycznie blokowane przed wydaniem. W zależności od ustawienia **pełnego blokowanie** na stronie **Kontrola wyrywkowa pozycji** ilość jest ilością w zleceniu kontroli jakości lub ilością w wierszu dokumentu źródłowego.

W danym procesie biznesowym rekord skojarzenia jakości identyfikuje zdarzenie i warunki, dla których wygenerowano zlecenie kontroli jakości. Warunki mogą być właściwe dla oddziału lub firmy. Zlecenia kontroli jakości, uwzględniające testy destrukcyjne mogą być generowane tylko wtedy, gdy istnieją dostępne zapasy dla zdarzenia.

Poniższe przykłady przedstawiają możliwe sposoby określania rekordu skojarzenia jakości dla odchyleń w poszczególnych procesach biznesowych. Dla każdego przykładu poniższa tabela podsumowuje zdarzenia i warunki zdefiniowane przez rekord skojarzenia jakości.

<table>
<tbody>
<tr>
<th>Typ odwołania</th>
<th>Typ zdarzenia</th>
<th>Wykonanie</th>
<th>Blokowanie zdarzeń</th>
<th>Odwołanie do dokumentu</th>
</tr>
<tr>
<td>Zapasy</td>
<td>Nie dotyczy</td>
<td>Nie dotyczy</td>
<td>Brak</td>
<td>Wszyscy</td>
</tr>
<tr>
<td rowspan="7">Sprzedaż</td>
<td rowspan="4">Proces pobierania został zaplanowany</td>
<td rowspan="4">Przed</td>
<td>Brak</td>
<td rowspan="22">Określony identyfikator, Grupa lub Tylko wszystkie</td>
</tr>
<tr>
<td>Proces pobierania</td>
</tr>
<tr>
<td>Dokument dostawy</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Dokument dostawy</td>
<td rowspan="3">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument dostawy</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="15">Zakup</td>
<td rowspan="7">Lista przychodu</td>
<td rowspan="4">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Lista przychodu</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Po</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Rejestracja</td>
<td rowspan="3">Nie dotyczy</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="5">Dokument przyjęcia produktów</td>
<td rowspan="3">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Dokument przyjęcia produktów</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="2">Po</td>
<td>Brak</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="8">Produkcja</td>
<td rowspan="3">Rejestracja</td>
<td rowspan="3">Nie dotyczy</td>
<td>Brak</td>
<td rowspan="12">Wszyscy</td>
</tr>
<tr>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="5">Zgłoszenie wyrobów gotowych</td>
<td rowspan="3">Przed</td>
<td>Brak</td>
</tr>
<tr>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="2">Po</td>
<td>Brak</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="4">Kwarantanna</td>
<td rowspan="3">Zgłoszenie wyrobów gotowych</td>
<td rowspan="2">Przed</td>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Zamknij</td>
</tr>
<tr>
<td>Po</td>
<td>Zamknij</td>
</tr>
<tr>
<td>Zamknij</td>
<td>Przed</td>
<td>Zamknij</td>
</tr>
<tr>
<td rowspan="3">Operacja marszruty</td>
<td rowspan="3">Zgłoszenie wyrobów gotowych</td>
<td rowspan="2">Przed</td>
<td>Brak</td>
<td rowspan="3">Określony identyfikator, Grupa lub Wszystkie, oraz Specyficzne dla zasobu, Grupa lub Wszystkie</td>
</tr>
<tr>
<td>Zgłoszenie wyrobów gotowych</td>
</tr>
<tr>
<td>Po</td>
<td>Brak</td>
</tr>
<tr>
<td rowspan="3">Wytwarzanie produktu towarzyszącego</td>
<td>Rejestracja</td>
<td>Nie dotyczy</td>
<td rowspan="3">Brak</td>
<td rowspan="3">Wszyscy</td>
</tr>
<tr>
<td rowspan="2">Zgłoszenie wyrobów gotowych</td>
<td>Przed</td>
</tr>
<tr>
<td>Po</td>
</tr>
</tbody>
</table>

Poniższa tabela zawiera więcej informacji na temat sposobu generowania zleceń kontroli jakości dla określonych typów procesów.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Typ procesu</th>
<th>Kiedy zlecenia kontroli jakości mogą być generowane automatycznie</th>
<th>Kiedy zlecenia kontroli jakości mogą być generowane, jeśli wymagane są testy destrukcyjne</th>
<th>Informacje o warunku</th>
<th>Informacje generowane ręcznie</th>
</tr>
<tr>
<td>Zamówienie zakupu</td>
<td>Przed zaksięgowaniem lub po zaksięgowaniu listy przychodu lub dokumentu przyjęcia produktu dla odebranego materiału</td>
<td>Po odebraniu i zaksięgowaniu dokumentu przyjęcia produktów dla materiału, ponieważ materiał musi być dostępny do testów destrukcyjnych</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia zakupu, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zlecenie kwarantanny</td>
<td>Przed lub po zgłoszeniu zlecenia kwarantanny jako zakończonego lub gotowego</td>
<td>Nie można generować zleceń kontroli jakości wymagających testów destrukcyjnych. Zakłada się, że funkcja zlecenia kwarantanny obsługuje dyspozycje niszczonego materiału.</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia kwarantanny, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zamówienie sprzedaży</td>
<td>Przed zaplanowanym procesem pobrania lub aktualizacją dokumentu dostawy dla wysłanych pozycji</td>
<td>Na dowolnym z etapów</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub odbiorcą, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia sprzedaży, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zlecenie produkcyjne</td>
<td>Przed zgłoszeniem lub po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</td>
<td>Po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia produkcyjnego, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zlecenie produkcyjne, które ma operację marszruty</td>
<td>Przed zakończeniem lub po zakończeniu raportu dla operacji</td>
<td>Po zakończeniu zgłaszania produkcji dla ostatniej operacji</td>
<td>Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub zasobem operacyjnym, lub kombinacją tych warunków.</td>
<td>Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy operacji marszruty, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</td>
</tr>
<tr>
<td>Zapasy</td>
<td>Zlecenie kontroli jakości nie może być generowane automatycznie dla transakcji w arkuszu magazynowym lub dla transakcji zamówienia przeniesienia.</td>
<td></td>
<td></td>
<td>Zlecenie kontroli jakości musi być tworzone ręcznie dla ilości zapasów towaru. Fizyczne dostępne zapasy są wymagane.</td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a>Przykłady automatycznego generowania zlecenia kontroli jakości

### <a name="purchasing"></a>Zakupy

Jeśli w obszarze zakupów w polu **Typ zdarzenia** zostanie ustawiona wartość **Przyjęcie produktów**, a w polu **Wykonanie** wartość **Po** na stronie **Powiązania jakości**, otrzymasz następujące wyniki : 

- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Tak**, zlecenie kontroli jakości jest generowane dla każdego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości i ustawień w ramach kontroli wyrywkowej pozycji. Za każdym razem, gdy ilość jest przyjmowana względem zamówienia zakupu, nowe zlecenia kontroli jakości są generowane na podstawie nowo przyjętej ilości.
- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Nie**, zlecenie kontroli jakości jest generowane dla pierwszego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości. Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia. Zlecenia kontroli jakości nie są generowane dla kolejnych przyjęć względem zamówienia zakupu.

### <a name="production"></a>Produkcyjne

Jeśli w obszarze produkcji w polu **Typ zdarzenia** zostanie ustawiona wartość **Zgłoszenie wyrobów gotowych**, a w polu **Wykonanie** wartość **Po** na stronie **Powiązania jakości**, otrzymasz następujące wyniki :

- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Tak**, zlecenie kontroli jakości jest generowane dla każdej ilości wyrobów gotowych i ustawień w ramach kontroli wyrywkowej pozycji. Za każdym razem, gdy ilość jest zgłaszana jako gotowa względem zlecenia produkcyjnego, nowe zlecenia kontroli jakości są generowane na podstawie nowej ilości zgłoszonej jako gotowa. Ta logika generowania jest spójna z procesem zakupów.
- Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Nie**, zlecenie kontroli jakości jest generowane po pierwszym zgłoszeniu ilości jako gotowej na podstawie gotowej ilości. Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia kontroli wyrywkowej pozycji. Zlecenia kontroli jakości nie są generowane dla kolejnych gotowych ilości.

<table>
<tbody>
<tr>
<th>Specyfikacja jakości</th>
<th>Dla zaktualizowanej ilości</th>
<th>Dla wymiaru śledzenia</th>
<th>Wynik</th>
</tr>
<tr>
<td>Wartość procentowa: 10%</td>
<td>Tak</td>
<td>
<p>Numer partii: Nie</p>
<p>Numer seryjny: Nie</p>
</td>
<td>
<p>Ilość w zamówieniu: 100</p>
<ol>
<li>Zgłaszanie wyrobów gotowych dla 30
<ul>
<li>Zlecenie kontroli jakości nr 1 dla 3 (10% z 30)</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 70
<ul>
<li>Zlecenie kontroli jakości nr 2 dla 7 (10% pozostałej ilości zamówienia, w tym przypadku 70)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Stała ilość: 1</td>
<td>Nie</td>
<td>
<p>Numer partii: Nie</p>
<p>Numer seryjny: Nie</p>
</td>
<td>Ilość w zamówieniu: 100
<ol>
<li>Zgłaszanie wyrobów gotowych dla 30
<ul>
<li>Zlecenie kontroli jakości nr 1 dla 1 (dla pierwszej ilości zgłoszonej jako gotowa, która ma stałą wartość równą 1)</li>
<li>Zlecenie kontroli jakości nr 2 dla 1 (dla pozostałej ilości, która nadal ma stałą wartość równą 1)</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 10
<ul>
<li>Zlecenia kontroli jakości nie są tworzone.</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 60
<ul>
<li>Zlecenia kontroli jakości nie są tworzone.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Stała ilość: 1</td>
<td>Tak</td>
<td>
<p>Numer partii: Tak</p>
<p>Numer seryjny: Tak</p>
</td>
<td>
<p>Ilość w zamówieniu: 10</p>
<ol>
<li>Zgłaszanie wyrobów gotowych dla 3: 1 dla b1, s1; 1 dla b2, s2; i 1 dla b3, s3
<ul>
<li>Zlecenie kontroli jakości nr 1 dla 1 — partia b1, numer seryjny s1</li>
<li>Zlecenie kontroli jakości nr 2 dla 1 — partia b2, numer seryjny s2</li>
<li>Zlecenie kontroli jakości nr 3 dla 1 — partia b3, numer seryjny s3</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 2: 1 dla b4, s4 i 1 dla b5, s5
<ul>
<li>Zlecenie kontroli jakości nr 4 dla 1 — partia b4, numer seryjny s4</li>
<li>Zlecenie kontroli jakości nr 5 dla 1 — partia b5, numer seryjny s5</li>
</ul>
</li>
</ol>
<p><strong>Uwaga:</strong> partii można użyć ponownie.</p>
</td>
</tr>
<tr>
<td>Stała ilość: 2</td>
<td>Nie</td>
<td>
<p>Numer partii: Tak</p>
<p>Numer seryjny: Tak</p>
</td>
<td>
<p>Ilość w zamówieniu: 10</p>
<ol>
<li>Zgłaszanie wyrobów gotowych dla 4: 1 dla b1, s1; 1 dla b2, s2; 1 dla b3, s3 i 1 dla b4, s4
<ul>
<li>Zlecenie kontroli jakości nr 1 dla 1 — partia b1, numer seryjny s1</li>
<li>Zlecenie kontroli jakości nr 2 dla 1 — partia b2, numer seryjny s2</li>
<li>Zlecenie kontroli jakości nr 3 dla 1 — partia b3, numer seryjny s3</li>
<li>Zlecenie kontroli jakości nr 4 dla 1 — partia b4, numer seryjny s4</li>
</ul>
<ul>
<li>Zlecenie kontroli jakości nr 5 dla 2 bez odwołania do partii i numeru seryjnego</li>
</ul>
</li>
<li>Zgłaszanie wyrobów gotowych dla 6: 1 dla b5, s5; 1 dla b6, s6; 1 dla b7, s7; 1 dla b8, s8; 1 dla b9, s9; i 1 dla b10, s10
<ul>
<li>Zlecenia kontroli jakości nie są tworzone.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Funkcja *Zarządzanie jakością dla procesów magazynowych* dodaje możliwości przetwarzania zlecenia kontroli jakości dla produkcji z ustawionym typem **Typ zdarzenia** jako *Zgłoś jako gotowe*, a  **Wykonanie** ma ustawienie *Po* i dla zakupów z typem **Typ zdarzenia** ustawionym jako *Rejestracja*. Aby zapoznać sie ze szczegółami, zobacz [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md).

## <a name="quality-management-pages"></a>Strony zarządzania jakością
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Strona</th>
<th>opis</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Powiązania jakości</td>
<td>Zobacz poprzednie części tego artykułu.</td>
<td>Powiązanie jakości określa wszystkie poniższe informacje dla generowanego zlecenia kontroli jakości:
<ul>
<li>Zdarzenie transakcji</li>
<li>Zestaw testów, które należy wykonać na towarach</li>
<li>AQL</li>
<li>Plan pobierania próbek</li>
</ul>
Należy określić skojarzenie jakości dla każdego odchylenia w procesie biznesowym, które wymaga automatycznego generowania zlecenia kontroli jakości. Na przykład: zlecenie kontroli jakości może być generowane w procesie biznesowym związanym z zamówieniami zakupu, zleceniami kwarantanny, zamówieniami sprzedaży i zleceniami produkcyjnymi.</td>
</tr>
<tr class="even">
<td>Testy</td>
<td>Ta strona służy do definiowania i wyświetlania poszczególnych testów decydujących, czy produkty są zgodne ze specyfikacjami jakości. Do grupy testowej można przypisać jeden lub więcej testów. W takim przypadku określa się również informacje właściwe dla danego testu, takie jak akceptowalne wartości pomiaru. Wartości pomiaru są używane w testach ilościowych, a zmienne testowe są używane w testach jakościowych.
<ul>
<li>Testy ilościowe mogą być typu <strong>Całkowity</strong> lub <strong>Ułamek</strong> i mają przypisaną jednostkę miary. Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</li>
<li>Test jakościowy ma przypisany typ <strong>Opcja</strong>. Testy jakości wymagają dodatkowych informacji konfiguracyjnych dotyczących zmiennej testowej i jej wyliczonych opcji. Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</li>
</ul></td>
<td>Firma produkcyjna wykonuje dwa testy na zakupionym materiale, w tym test ilości dotyczący jakości materiału i test jakości dotyczący uszkodzenia opakowania. Firma definiuje dodatkowe informacje na temat testu jakości w celu określenia zmiennej testowej (uszkodzone opakowanie) i jej wartości wynikowe. Firma używa strony <strong>Grupy testowe</strong> do przypisania dwóch testów do grupy testowej i do określenia informacji specyficznych dla testu. Grupa testów jest przypisywana do zlecenia kontroli jakości, dzięki czemu firma może raportować wyniki testu dla dwóch testów.</td>
</tr>
<tr class="odd">
<td>Grupy testowe</td>
<td>Strona ta służy do konfigurowania, edytowania i wyświetlania grup testowych oraz testów indywidualnych przypisanych do danej grupy testowej. W górnym okienku wyświetlane są grupy testowe, a w dolnym — testy przypisane do wybranej grupy testowej. Do grupy testowej można przypisać różne zasady, w tym plan próbkowania, akceptowany poziom jakości i wymaganie dotyczące testowania destrukcyjnego. Po przypisaniu każdego z tych testów do grupy testowej, można zdefiniować dodatkowe informacje, takie jak sekwencje, dokumenty i daty ważności. W przypadku testu ilościowego zdefiniowane informacje zawierają również akceptowalne wartości pomiaru. W przypadku testu jakościowego informacje zmienną testową i domyślny rezultat. Za pomocą grupy testów przypisanej do zlecenia kontroli jakości określa się domyślny zestaw testów, które muszą zostać przeprowadzone odnośnie do określonego towaru. Ale mnożna dodawać, usuwać lub zmieniać testy w zleceniu kontroli jakości. Wyniki testu są raportowane dla każdego testu w zleceniu kontroli jakości.</td>
<td>W przedsiębiorstwie produkcyjnym zdefiniowano grupę testową dla każdego odchylenia dotyczącego zasad kontroli jakości. Poszczególne grupy testowe odpowiadają różnym planom próbkowania, seriom testów, które muszą być wykonywane razem, akceptowanemu poziomowi jakości i innym czynnikom. W testach ilościowych są również różnice we właściwych wartościach pomiaru. Aby wymusić wytyczne co do jakości, firma przypisuje grupę testową do każdej reguły w celu automatycznego generowania zleceń kontroli jakości na stronie <strong>powiązań jakości</strong> i przypisuje grupę testową do ręcznie tworzonych zleceń kontroli jakości.</td>
</tr>
<tr class="even">
<td>Grupy jakości pozycji</td>
<td>Ta strona umożliwia konfigurowanie, edycję i wyświetlanie towarów przypisanych do grupy jakości lub grup jakości przypisanych do towaru. Grupa jakości reprezentuje wspólne wymagania dotyczące testowania towarów. Po zdefiniowaniu wymogów testu na stronie <strong>Grupy testowe</strong> można zdefiniować reguły automatycznego generowania zleceń kontroli jakości. Aby uprościć proces, nie definiuje się reguł dla poszczególnych towarów. Zamiast tego definiuje się reguły dla grupy jakości na stronie <strong>powiązań jakości</strong>. Można również użyć strony <strong>Grupy jakości towarów</strong> dla wybranej grupy jakości w celu przypisania odpowiednich towarów do tej grupy. Można również użyć strony <strong>Grupy jakości towarów</strong> dla wybranego towaru w celu przypisania odpowiednich grup jakości do danego towaru.</td>
<td>Firma produkcyjna nabywa kilka surowców mających te same wymagania dotyczące testowania przed zbliżającą się inspekcją. Firma definiuje grupę jakości, a następnie przypisuje do tej grupy kody towarów, które są skojarzone z surowcami. Później firma nabywa nowy typ surowca, który ma te same wymagania dotyczące testowania. Zamiast konfigurować nowe wymagania dotyczące nowego materiału, firma dodaje kod towaru dla nowego materiału do istniejącej grupy jakości. Ta sama firma produkuje również towary mające te same wymagania dotyczące testowania produkcji i wysyła towary mające te same wymagania dotyczące przeprowadzania testów przed wysyłką. Firma definiuje dwie dodatkowe grupy jakości i przypisuje do każdej z nich odpowiednie kody towarów.</td>
</tr>
<tr class="odd">
<td>Zmienne testowe</td>
<td>Ta strona umożliwia definiowanie i wyświetlanie zmiennych skojarzonych z testem jakościowym. Dla każdej zmiennej można zdefiniować wyliczenie wyników reprezentujące możliwe opcje. Testy definiuje się na stronie <strong>Testy</strong>. W przypadku testów jakościowych trzeba ustawić typ testu jako <strong>Opcja</strong>. Strona <strong>Grupy testowe</strong> służy do przypisywania zmiennej testowej do konkretnego testu.</td>
<td>Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie. Ten test inspekcji zawiera kilka zmiennych. Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły. Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.</td>
</tr>
<tr class="even">
<td>Wyniki zmiennych testowych.</td>
<td>Ta strona służy do konfigurowania, edytowania i wyświetlania możliwych wartości zmiennej testowej skojarzonej z testem jakości. Dla każdego wyniku należy przypisać stan <strong>powodzenie</strong> lub <strong>niepowodzenie</strong>. Należy zdefiniować zmienną i jej wyniki dla każdego testu jakości zdefiniowanego na stronie <strong>Testy</strong>. (Dla testów jakościowych ustawiono typ testu <strong>Opcja</strong> na stronie <strong>Testy</strong>). Strona <strong>Grupy testów</strong> służy do przypisywania zmiennej testowej i domyślnego wyniku do konkretnego testu.</td>
<td>Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie. Ten test inspekcji zawiera kilka zmiennych. Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły. Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy. Każdy wynik ma przypisany stan <strong>powodzenie</strong> lub <strong>niepowodzenie</strong>. Podczas sprawdzania poszczególnych zmiennych, kontroler raportuje wyniki testów, zaznaczając jeden z wyników.</td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Procesy zarządzania jakością](quality-management-processes.md)

[Zarządzanie brakiem zgodności](enable-nonconformance-management.md)

[Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)
