---
title: Nowości i zmiany w aplikacji Dynamics AX w wersji 7.0.1 (maj 2016)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w aplikacji Microsoft Dynamics AX w wersji 7.0.1. Ta wersja została wydana w maju 2016 r. i ma numer kompilacji 7.0.1265.23014.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 1dd76150dd1519adf2c453db8e874d6db32b5906
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693149"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Nowości i zmiany w aplikacji Dynamics AX w wersji 7.0.1 (maj 2016)

[!include [banner](../includes/banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w aplikacji Microsoft Dynamics AX w wersji 7.0.1. Ta wersja została wydana w maju 2016 r. i ma numer kompilacji 7.0.1265.23014.

## <a name="electronic-reporting-er"></a>Raportowanie elektroniczne (ER)

| Co można zrobić? | Dlaczego to jest ważne? |
|------------------|------------------------|
| Konfigurowanie okna dialogowego czasu wykonywania umożliwiającego projektowanie raportów modułu Raportowanie elektroniczne (ER), dzięki czemu użytkownicy mogą wybrać żądane wymiary finansowe. | W czasie wykonywania w oknie dialogowym generowania raportu aplikacji ER użytkownicy mogą wybrać wiele wymiarów finansowych. Szczegóły wybranych wymiarów finansowych będą wyświetlane w generowanym dokumencie elektronicznym. |
| Konfigurowanie dostępu do wielu wymiarów finansowych podczas projektowania raportu ER poprzez jedno mapowanie do żądanego źródła danych. | Ta sama konfiguracja raportu ER może służyć do generowania dokumentów elektronicznych pokazujących dane transakcyjne wraz ze szczegółami wymiarów finansowych, bez względu na liczbę wymiarów finansowych wybranych przez użytkownika lub skonfigurowanych dla bieżącej firmy lub wystąpienia. |
| Konfigurowanie raportu ER w celu wprowadzania danych w dynamicznie generowanych kolumnach dokumentu elektronicznego, który jest tworzony w formacie arkusza OPENXML. | Raport ER może wprowadzać dane do generowanego arkusza OPENXML poprzez poziome replikowanie kolumn. W związku z tym tej samej konfiguracji raportu ER można użyć również do generowania dokumentów elektronicznych, które mają inną liczbę dynamicznie generowanych kolumn. |
| Konfigurowanie miejsc docelowych aplikacji ER, tak aby dane wyjściowe w określonym formacie były kierowane do określonego miejsca docelowego: pliku, wiadomości e-mail lub archiwum (folderu programu Microsoft SharePoint lub magazynu w usłudze Microsoft Azure). | Wcześniej podczas sesji konfiguracji ER pojawiało się okno komunikatu z monitem do użytkownika, aby zapisał lub otworzył plik. Teraz można wstępnie skonfigurować miejsce docelowe osobno dla każdej konfiguracji formatu i każdego składnika wyjściowego (folderu lub pliku). Użytkownicy mający odpowiednie prawa dostępu mogą także modyfikować ustawienia miejsca docelowego w czasie wykonywania. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>POS — moduł sprzedaży detalicznej w systemie Microsoft Dynamics AX

| Co można zrobić? | Dlaczego to jest ważne? |
|------------------|------------------------|
| Używanie przeglądarki internetowej Google Chrome. | Sprzedawcy detaliczni mogą teraz uruchamiać aplikację Cloud POS w przeglądarce Chrome oraz korzystać ze wszystkich funkcji, które można znaleźć w aplikacji Cloud POS w wersji dla przeglądarek Microsoft Edge i Internet Explorer. |

## <a name="financial-reporting"></a>Raporty finansowe

| Co można zrobić? | Dlaczego to jest ważne? |
|------------------|------------------------|
| Odbudowa składniki danych aplikacji Raportowanie finansowe. | Po przeniesieniu baz danych systemu Dynamics AX między środowiskami lub wprowadzeniu innych inwazyjnych zmian w środowisku może być konieczne odbudowanie bazy danych składnika Raporty finansowe. Teraz jest dostępny skrypt narzędzia Windows PowerShell, który umożliwia automatyczne odbudowanie bazy danych. |
| Nie można już wybierać nieprawidłowych opcji projektanta raportów. | Niektóre opcje projektanta raportów, które były używane w lokalnych wersjach programu Management Reporter, nie mają zastosowania w tej wersji systemu Dynamics AX. Te opcje dotyczyły projektów, danych wyjściowych i połączeń raportów finansowych. Opcje zostały usunięte z projektanta raportów finansowych, aby zapobiec popełnianiu błędów przez użytkowników. |

## <a name="financial-management"></a>Zarządzanie finansami

| Co można zrobić? | Dlaczego to jest ważne? |
|------------------|------------------------|
| Generowanie plików płatności dodatnich dla płatności w ramach rozrachunków z dostawcami. | Można generować pliki płatności dodatnich, aby ułatwić bankom walkę z oszustwami dotyczącymi czeków. |

## <a name="warehouse-and-production"></a>Magazyn i produkcja

<table>
<thead>
<tr>
<th>Co można zrobić?</th>
<th>Dlaczego to jest ważne?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definiowanie zasady pracy magazynu, która steruje tworzeniem pracy dla zbioru produktów w określonych lokalizacjach.</td>
<td>Procesy magazynowe nie zawsze obejmują pracę. Korzystając z nowych zasad pracy magazynowej, można zablokować tworzenie pracy pobierania surowców i odkładania wyrobów gotowych dla zbioru produktów w określonych lokalizacjach.</td>
</tr>
<tr>
<td>Określanie, że lokalizacja wyjściowa produkcji nie ma być kontrolowana za pomocą numerów identyfikacyjnych.</td>
<td>Teraz można określić, że lokalizacja wyjściowa produktu nie ma być kontrolowana za pomocą numerów identyfikacyjnych. Na przykład ta funkcja jest użyteczna, gdy zlecenie produkcyjne bliżej dostawcy zgłasza towary jako gotowe bezpośrednio do lokalizacji, która działa jako lokalizacja wejściowa produkcji dla zlecenia produkcyjnego bliżej odbiorcy.</td>
</tr>
<tr>
<td>Obsługa BOM zawierających towary o różnych wymiarach produktów w tym samym wierszu.</td>
<td>Podczas używania jednego lub wielu wymiarów produktu w produkcji można mieć sytuacje, gdy chcesz wytworzyć towar oparty na innym wariancie tego samego towaru. Aby uzyskać więcej informacji, zobacz <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">ten blog</a>.</td>
</tr>
<tr>
<td>Zlecenia produkcyjne ze strukturami rekurencyjnymi na pierwszym poziomie ich BOM są wykluczone z obliczeń poziomu BOM w planowania zasobów materiałowych.</td>
<td>Nie jest możliwe przypisanie poprawnych poziomów BOM do wariantów produktu dla zleceń produkcyjnych, które powodują cykliczność w hierarchii BOM.</td>
</tr>
<tr>
<td>Obliczanie oddzielnych poziomów BOM dla planowania zasobów materiałowych i kosztów:
<ul>
<li>W planowania zasobów materiałowych poziomy BOM są obliczane w nowej tabeli <strong>ReqItemLevel</strong>. Zakończone zlecenia produkcyjne są ignorowane w obliczeniach.</li>
<li>W przypadku kosztów produkcji poziomy BOM są obliczane w tabeli <strong>InventTable</strong>. Zakończone zlecenia produkcyjne są uwzględniane w obliczeniach.</li>
</ul>
</td>
<td>
<ul>
<li>Podczas planowania zasobów materiałowych, na przykład tworzenia i rozwijania planu w ramach planowania głównego, konieczność ponownego obliczania istnieje tylko dla poziomów BOM używanych do planowania zasobów materiałowych. Innymi słowy nie trzeba obliczać poziomów BOM używanych do obliczania wyceny produkcji.</li>
<li>Podczas operacji wyceny, na przykład w celu zamknięcia magazynu, trzeba ponownie obliczać tylko poziomy BOM używane do obliczania wyceny produkcji.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Nowości i zmiany w rozwiązaniu Finance and Operations — strona główna](whats-new-changed.md)

[Nowe lub zaktualizowane przewodniki po zadaniach (maj 2016 r.)](new-updated-task-guides-available-may-2016.md)
