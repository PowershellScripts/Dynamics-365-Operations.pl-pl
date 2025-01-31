---
title: Sprawdzanie skonfigurowanego składnika ER, aby zapobiec problemom w czasie wykonywania
description: W tym temacie opisano sposób sprawdzania skonfigurowanych składników raportowania elektronicznego (ER) w celu zapobiegania problemom, które mogą wystąpić w czasie wykonywania.
author: NickSelin
manager: AnnBe
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72db7660c07b2f57f8609ab6c14964193e842d75
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688574"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>Sprawdzanie skonfigurowanego składnika ER, aby zapobiec problemom w czasie wykonywania

[!include[banner](../includes/banner.md)]

Każdy skonfigurowany składnik w postaci [formatu](general-electronic-reporting.md#FormatComponentOutbound) i [mapowania modelu](general-electronic-reporting.md#data-model-and-model-mapping-components) modułu [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) może być [weryfikowany](er-fillable-excel.md#validate-an-er-format) w czasie projektowania. Podczas tego sprawdzania spójności jest przeprowadzane sprawdzanie spójności w celu uniknięcia problemów, które mogą wystąpić w czasie wykonywania, takich jak błędy wykonywania i pogorszenie wydajności. Dla każdego znalezionego problemu jest podawana ścieżka do problematycznego elementu. W przypadku niektórych problemów jest dostępna automatyczna poprawka.

Domyślnie sprawdzanie poprawności jest stosowane automatycznie w następujących przypadkach dla konfiguracji ER, która zawiera wspomniane wcześniej składniki ER:

- [Importujesz](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) nową [wersję](general-electronic-reporting.md#component-versioning) konfiguracji ER do wystąpienia rozwiązania Microsoft Dynamics 365 Finance.
- Zmieniasz [stan](general-electronic-reporting.md#component-versioning) edytowalnej konfiguracji ER z **Wersja robocza** na **Ukończono**.
- Zmieniasz [podstawę](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) edytowalnej konfiguracji ER poprzez zastosowanie nowej wersji bazowej.

To sprawdzenie poprawności można uruchomić jawnie. Wybierz jedną z następujących trzech opcji i wykonaj podane kroki:

- Opcja 1:

    1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
    2. W drzewie konfiguracje w lewym okienku wybierz żądaną konfigurację ER, która zawiera składnik w postaci formatu ER lub mapowania modelu ER.
    3. Na skróconej karcie **Wersje** wybierz żądaną wersję wybranej konfiguracji ER.
    4. W okienku akcji wybierz pozycję **Weryfikacja**.

- Opcja 2, w przypadku formatu ER:

    1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
    2. W drzewie konfiguracje w lewym okienku wybierz żądaną konfigurację ER, która zawiera składnik w postaci formatu ER.
    3. Na skróconej karcie **Wersje** wybierz żądaną wersję wybranej konfiguracji ER.
    4. W okienku akcji wybierz opcję **Projektant**.
    5. Na stronie **Projektant formatów** w okienku akcji wybierz opcję **Weryfikuj**.

- Opcja 3, w przypadku mapowania modelu ER:

    1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
    2. W drzewie konfiguracje w lewym okienku wybierz żądaną konfigurację ER, która zawiera składnik w postaci mapowania modelu ER.
    3. Na skróconej karcie **Wersje** wybierz żądaną wersję wybranej konfiguracji ER.
    4. W okienku akcji wybierz opcję **Projektant**.
    5. Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Modelowanie do mapowania źródła danych**.
    6. Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Weryfikuj**.

Aby pominąć sprawdzanie poprawności podczas importowania konfiguracji, wykonaj następujące kroki.

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W opcji **Weryfikuj konfigurację po zaimportowaniu** ustaw wartość **Nie**.

Aby pominąć sprawdzanie poprawności w przypadku zmiany stanu lub jej podstawy (bazy) wersji, wykonaj następujące kroki.

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W opcji **Pomiń weryfikację przy zmianie stanu konfiguracji i zmianie bazy** ustaw wartość **Tak**.

Moduł ER grupuje inspekcje sprawdzające spójność w następujące kategorie:

- **Wykonywalność** — inspekcje wykrywające krytyczne problemy, które mogą wystąpić w czasie wykonywania. Te problemy są najczęściej na poziomie **Błąd**. 
- **Wydajność** — inspekcje wykrywające problemy, które mogą spowodować nieefektywne wykonanie skonfigurowanych składników ER. Te problemy są najczęściej na poziomie **Ostrzeżenie**.
- **Integralność danych** — inspekcje wykrywające problemy, które mogą spowodować utratę danych lub problemy w czasie wykonywania. Te problemy są najczęściej na poziomie **Ostrzeżenie**.

## <a name="list-of-inspections"></a>Lista inspekcji

W poniższej tabeli znajduje się omówienie inspekcji dostępnych w module ER. Aby uzyskać więcej informacji dotyczących tych inspekcji, skorzystaj z łączy w pierwszej kolumnie, które powodują przejście do odpowiednich sekcji tego tematu. W tych sekcjach objaśniono typy składników, dla których są dostępne inspekcje w module ER, oraz sposób rekonfigurowania składników ER w celu lepszego zapobiegania problemom.

<table>
<thead>
<tr>
<th>Imię i nazwisko</th>
<th>Kategoria</th>
<th>Poziom</th>
<th>Komunikat</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Konwersja typu</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Nie można przekształcić wyrażenia typu &lt;typ&gt; na pole typu &lt;typ&gt;.</p>
<p><b>Błąd czasu wykonywania:</b> Wyjątek o danym typie</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Zgodność typu</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Skonfigurowanego wyrażenia nie można użyć do powiązania bieżącego elementu formatu ze źródłem danych, ponieważ to wyrażenie zwraca wartość o typie danych &lt;typ&gt;, która jest poza zakresem typów danych obsługiwanych przez bieżący element formatu o typie &lt;typ&gt;.</p>
<p><b>Błąd czasu wykonywania:</b> Wyjątek o danym typie</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Brak elementu konfiguracji</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Nie znaleziono ścieżki &lt;ścieżka&gt;.</p>
<p><b>Błąd czasu wykonywania:</b> Nie znaleziono elementu konfiguracji &lt;ścieżka&gt;</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Wykonywalność wyrażenia z funkcją FILTER</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Wyrażenie listy funkcji FILTER nie jest odpytywalne.</p>
<p><b>Błąd czasu wykonywania:</b> Filtrowanie nie jest obsługiwane. Aby uzyskać więcej szczegółowych informacji na ten temat, sprawdź poprawność konfiguracji.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Wykonywalność źródła danych typu GROUPBY</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>Ścieżka &lt;ścieżka&gt; nie obsługuje wykonywania zapytań.</td>
</tr>
<tr>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Funkcji Grupuj wg nie można wykonać przy użyciu kwerendy.</p>
<p><b>Błąd czasu wykonywania:</b> Funkcji Grupuj wg nie można wykonać przy użyciu kwerendy.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Wykonywalność źródła danych typu JOIN</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Nie można dołączyć do listy &lt;ścieżka&gt;, która nie jest filtrem w zapytaniu.</p>
<p><b>Błąd czasu wykonywania:</b> Funkcja Połączone źródło danych musi być wyrażeniem filtru. Pole obliczeniowe zostało błędnie wywołane.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>Preferowanie funkcji FILTER wobec WHERE</a></td>
<td>Wydajność</td>
<td>Ostrzeżenie</td>
<td>Z perspektywy wydajności lepiej w wyrażeniu używać funkcji FILTER niż WHERE. Wybierz opcję Napraw, aby zamienić automatycznie.</td>
</tr>
<tr>
<td><a href='#i8'>Preferowanie funkcji ALLITEMSQUERY wobec ALLITEMS</a></td>
<td>Wydajność</td>
<td>Ostrzeżenie</td>
<td>Z perspektywy wydajności lepiej w wyrażeniu używać funkcji ALLITEMSQUERY niż ALLITEMS. Wybierz opcję Napraw, aby zamienić automatycznie.</td>
</tr>
<tr>
<td><a href='#i9'>Uwagi dotyczące przypadków z pustymi listami</a></td>
<td>Wykonywalność</td>
<td>Ostrzeżenie</td>
<td>
<p>Lista &lt;ścieżka&gt; nie ma żadnych opcji sprawdzania dla przypadków z pustymi listami. Może to spowodować błąd w czasie wykonywania. Dodaj opcję sprawdzania występowania przypadków z pustymi listami.</p>
<p><b>Błąd czasu wykonywania:</b> Lista w &lt;ścieżka&gt; jest pusta</p>
<p><b><a href='#i9a'>Potencjalny problem</a>:</b> Wiersz jest wypełniany jeden raz, podczas gdy źródło danych zawiera wiele rekordów</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Wykonywalność wyrażenia z funkcją FILTER (buforowanie)</a></td>
<td>Wykonywalność</td>
<td>Wadliwe</td>
<td>
<p>Funkcji FILTER nie można zastosować do wybranego typu źródła danych. Źródło danych typu Rekordy tabeli ma zastosowanie tylko wtedy, gdy nie jest buforowane i nie ma ręcznie dodanych zagnieżdżonych źródeł danych.</p>
<p><b>Błąd czasu wykonywania:</b> Filtrowanie nie jest obsługiwane. Aby uzyskać więcej szczegółowych informacji na ten temat, sprawdź poprawność konfiguracji.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Brak powiązania</a></td>
<td>Wykonywalność</td>
<td>Ostrzeżenie</td>
<td>
<p>Ścieżka &lt;ścieżka&gt; nie ma powiązania z żadnym źródłem danych podczas używania mapowania modelu.</p>
<p><b>Błąd czasu wykonywania:</b> Ścieżka &lt;ścieżka&gt; nie jest powiązana</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Niepołączony szablon</a></td>
<td>Integralność danych</td>
<td>Ostrzeżenie</td>
<td>Plik &lt;nazwa&gt; nie jest połączony z żadnymi składnikami plikowymi i zostanie usunięty po zmianie stanu wersji konfiguracji.</td>
</tr>
<tr>
<td><a href='#i13'>Niezsynchronizowany format</a></td>
<td>Integralność danych</td>
<td>Ostrzeżenie</td>
<td>Zdefiniowana nazwa &lt;nazwa składnika&gt; nie istnieje w arkuszu programu Excel &lt;nazwa arkusza&gt;</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Konwersja typu

W module ER następuje sprawdzenie, czy typ danych pola modelu danych jest zgodny z typem danych wyrażenia skonfigurowanego jako powiązanie tego pola. Jeśli typy danych są niezgodne, w projektancie mapowania modelu ER wystąpi błąd sprawdzania poprawności. Odebrany komunikat stwierdza, że moduł ER nie może przekonwertować wyrażenia typu A na pole typu B.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Rozpocznij konfigurowanie jednocześnie modelu danych ER i składników mapowania modelu ER.
2. W drzewie modelu danych dodaj pole o nazwie **X** i jako typ danych wybierz opcję **Liczba całkowita**.

    ![Pole X i typ danych Liczba całkowita dodane do drzewa trybu danych na stronie Model danych](./media/er-components-inspections-01.png)

3. W okienku źródeł danych mapowania modelu dodaj źródło danych typu **Pole obliczeniowe**.
4. Nazwij nowe źródło danych **Y** i skonfiguruj je tak, aby zawierało wyrażenie `INTVALUE(100)`.
5. Powiąż **X** z **Y**.
6. W projektancie modelu danych zmień typ danych pola **X** z **Liczba całkowita** na **Int64**.
7. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu**.

    ![sprawdzanie poprawności edytowalnego składnika mapowania modelu na stronie Projektant mapowania modelu](./media/er-components-inspections-01.gif)

8. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję składnika mapowania modelu wybranej konfiguracji ER na stronie **Konfiguracje**.

    ![Sprawdzanie poprawności w celu skontrolowania składnika mapowania modelu na stronie Konfiguracje](./media/er-components-inspections-01a.png)

9. Zauważ, że występuje błąd sprawdzania poprawności. Komunikat stwierdza, że wartość typu **Liczba całkowita** zwracana przez wyrażenie `INTVALUE(100)` źródła danych **Y** nie może być przechowywana w polu modelu danych **X** o typie **Int64**.

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia i wybrania opcji **Uruchom** w celu uruchomienia formatu skonfigurowanego do używania mapowania modelu.

![Błędy czasu wykonywania na stronie Projektant formatów](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zaktualizuj strukturę modelu danych, zmieniając typ danych pola modelu danych, tak aby odpowiadał on typowi danych wyrażenia skonfigurowanego dla powiązania tego pola. W poprzednim przykładzie typ danych pola **X** musi zostać zmieniony z powrotem na **Liczba całkowita**.

#### <a name="option-2"></a>Opcja 2

Zaktualizuj mapowanie modelu, zmieniając wyrażenie źródła danych powiązanego z polem modelu danych. W poprzednim przykładzie wyrażenie źródła danych **Y** musi zostać zmienione na `INT64VALUE(100)`.

## <a name="type-compatibility"></a><a id="i2"></a>Zgodność typu

W module ER następuje sprawdzenie, czy typ danych elementu formatu jest zgodny z typem danych wyrażenia skonfigurowanego jako powiązanie tego elementu formatu. Jeśli typy danych są niezgodne, w projektancie operacji ER wystąpi błąd sprawdzania poprawności. Odebrany komunikat stwierdza, że skonfigurowanego wyrażenia nie można użyć do powiązania bieżącego elementu formatu ze źródłem danych, ponieważ wyrażenie zwraca wartość o typie danych A, która jest poza zakresem typów danych obsługiwanych przez bieżący element formatu o typie B.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Rozpocznij konfigurowanie jednocześnie modelu danych ER i składników formatu ER.
2. W drzewie modelu danych dodaj pole o nazwie **X** i jako typ danych wybierz opcję **Liczba całkowita**.
3. W drzewie struktury formatu dodaj element formatu o typie **Liczbowe**.
4. Nadaj nowemu elementowi formatu nazwę **Y** . W polu **Typ liczbowy** jako typ danych wybierz opcję **Liczba całkowita**.
5. Powiąż **X** z **Y**.
6. W drzewie struktury formatu zmień typ danych elementu formatu **Y** z **Liczba całkowita** na **Int64**.
7. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika formatu na stronie **Projektant formatów**.

    ![Weryfikowanie zgodności typów na stronie Projektant formatów](./media/er-components-inspections-02.gif)

8. Zauważ, że występuje błąd sprawdzania poprawności. Komunikat stwierdza, że skonfigurowane wyrażenie akceptuje tylko wartości **Int64**. Z tego względu wartości pola model danych **X** o typie **Liczba całkowita** nie można wprowadzić w elemencie formatu **Y**.

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zaktualizuj strukturę formatu, zmieniając typ danych elementu formatu **Liczbowe**, tak aby odpowiadał on typowi danych wyrażenia skonfigurowanego dla powiązania tego elementu. W poprzednim przykładzie wartość **Typ liczbowy** elementu formatu **X** należy zmienić z powrotem na **Liczba całkowita**.

#### <a name="option-2"></a>Opcja 2

Zaktualizuj mapowanie formatu elementu formatu **X**, zmieniając wyrażenie z `model.X` na `INT64VALUE(model.X)`.

## <a name="missing-configuration-element"></a><a id="i3"></a>Brak elementu konfiguracji

W module ER następuje sprawdzenie, czy wyrażenia wiązania zawierają tylko źródła danych skonfigurowane w edytowalnym składniku ER. Dla każdego powiązania zawierającego źródło danych, którego nie ma w edytowalnym składniku ER, występuje błąd sprawdzania poprawności w projektancie operacji ER lub projektancie mapowania modelu ER.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Rozpocznij konfigurowanie jednocześnie modelu danych ER i składników mapowania modelu ER.
2. W drzewie modelu danych dodaj pole o nazwie **X** i jako typ danych wybierz opcję **Liczba całkowita**.

    ![Drzewo modelu danych z polem X i typem danych Liczba całkowita na stronie Model danych](./media/er-components-inspections-01.png)

3. W okienku źródeł danych mapowania modelu dodaj źródło danych typu **Pole obliczeniowe**.
4. Nazwij nowe źródło danych **Y** i skonfiguruj je tak, aby zawierało wyrażenie `INTVALUE(100)`.
5. Powiąż **X** z **Y**.
6. W projektancie mapowania modelu w okienku źródła danych usuń źródło danych **Y**.
7. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu**.

    ![Sprawdzanie edytowalnego składnika mapowania modelu ER na stronie Projektant mapowania modelu](./media/er-components-inspections-03.gif)

8. Zauważ, że występuje błąd sprawdzania poprawności. Komunikat stwierdza, że powiązanie pola modelu danych **X** zawiera ścieżkę odwołującą się do źródła danych **Y**, ale nie można odnaleźć tego źródła danych.

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Wybierz opcję **Usuń powiązanie**, aby automatycznie rozwiązać ten problem poprzez usunięcie powiązania z brakującym źródłem danych.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Usuń powiązanie pola modelu danych **X** w celu zakończenia odwoływania do nieistniejącego źródła danych **Y**.

#### <a name="option-2"></a>Opcja 2

W okienku źródła danych w projektancie mapowania modelu ER dodaj ponownie źródło danych **Y**.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Wykonywalność wyrażenia z funkcją FILTER

Funkcja [FILTER](er-functions-list-filter.md) wbudowana w module ER służy do uzyskiwania dostępu do tabel, widoków lub jednostek danych aplikacji poprzez wykonywanie pojedynczego wywołania SQL w celu uzyskania wymaganych danych w postaci listy rekordów. Źródło danych typu **Lista rekordów** jest używane jako argument tej funkcji i określa źródło aplikacji dla tego wywołania. Moduł ER sprawdza, czy można ustanowić bezpośrednie zapytanie SQL do źródła danych, do którego istnieje odwołanie w funkcji `FILTER`. Jeśli nie można ustanowić bezpośredniego zapytania, w projektancie mapowania modelu ER wystąpi błąd sprawdzania poprawności. Odebrany komunikat stwierdza, że wyrażenie ER zawierające funkcję `FILTER` nie może zostać uruchomione w czasie wykonywania. 

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik mapowania modelu ER.
2. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
3. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
4. Dodaj źródło danych typu **Pole obliczeniowe**.
5. Nazwij nowe źródło danych **FilteredVendor** i skonfiguruj je tak, aby zawierało wyrażenie `FILTER(Vendor, Vendor.AccountNum="US-101")`.
6. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu** oraz sprawdzić, czy można wykonać zapytanie do wyrażenia `FILTER(Vendor, Vendor.AccountNum="US-101")` znajdującego się w źródle danych **Vendor**.
7. Zmodyfikuj źródło danych **Vendor** poprzez dodanie pola zagnieżdżonego o typie **Pole obliczeniowe**, aby uzyskać przycięty numer konta dostawcy.
8. Nazwij nowe zagnieżdżone pole **$AccNumber** i skonfiguruj je tak, aby zawierało wyrażenie `TRIM(Vendor.AccountNum)`.
9. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu** oraz sprawdzić, czy można wykonać zapytanie do wyrażenia `FILTER(Vendor, Vendor.AccountNum="US-101")` znajdującego się w źródle danych **Vendor**.

    ![Sprawdzanie, czy można wykonać zapytanie do wyrażenia na stronie Projektant mapowania modelu](./media/er-components-inspections-04.gif)

10. Zauważ, że występuje błąd sprawdzania poprawności, ponieważ źródło danych **Vendor** zawiera zagnieżdżone pole typu **Pole obliczeniowe**, które nie zezwala na przekształcenie wyrażenia źródła danych **FilteredVendor** na bezpośrednią instrukcję SQL.

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia i wybrania opcji **Uruchom** w celu uruchomienia formatu skonfigurowanego do używania mapowania modelu.

![Błędy czasu wykonywania występujące podczas uruchamiania edytowalnego formatu na stronie Projektant formatów](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zamiast dodawać zagnieżdżone pole typu **Pole obliczeniowe** do źródła danych **Vendor**, dodaj zagnieżdżone pole **$AccNumber** do źródła danych **FilteredVendor** i skonfiguruj je w taki sposób, aby zawierało wyrażenie `TRIM(FilteredVendor.AccountNum)`. W ten sposób wyrażenie `FILTER(Vendor, Vendor.AccountNum="US-101")` można uruchomić na poziomie SQL, a zagnieżdżone pole **$AccNumber** obliczyć później.

#### <a name="option-2"></a>Opcja 2

Zmień wyrażenie w źródle danych **FilteredVendor** z `FILTER(Vendor, Vendor.AccountNum="US-101")` na `WHERE(Vendor, Vendor.AccountNum="US-101")`. Nie zalecamy zmiany wyrażenia dla tabeli zawierającej dużą ilość danych (tabela transakcji), ponieważ zostaną pobrane wszystkie rekordy, a wybór wymaganych rekordów zostanie dokonany w pamięci. Z tego względu ta metoda może spowodować pogorszenie wydajności. Aby uzyskać więcej informacji, zobacz [WHERE, funkcja ER](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Wykonywalność źródła danych typu GROUPBY

Źródło danych typu **GROUPBY** dzieli wyniki zapytania na grupy rekordów, zazwyczaj w celu wykonania jednej lub więcej agregacji w każdej grupie. Każde źródło danych typu **GROUPBY** można tak skonfigurować, aby było uruchamiane na poziomie bazy danych lub w pamięci. Gdy źródło danych typu **GROUPBY** skonfigurowano tak, aby było uruchamiane na poziomie bazy danych, moduł ER sprawdza, czy można ustanowić bezpośrednie zapytanie SQL do źródła danych, do którego istnieje odwołanie w tym źródle danych. Jeśli nie można ustanowić bezpośredniego zapytania, w projektancie mapowania modelu ER wystąpi błąd sprawdzania poprawności. Odebrany komunikat stwierdza, że skonfigurowane źródło danych **GROUPBY** nie może być uruchamiane w czasie wykonywania.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik mapowania modelu ER.
2. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
3. Nazwij nowe źródło danych **Trans**. W polu **Tabela** wybierz opcję **VendTrans**, aby określić, że to źródło danych będzie żądało tabeli VendTrans.
4. Dodaj źródło danych typu **Grupuj wg**.
5. Nazwij nowe źródło danych **GroupedTrans** i skonfiguruj je w następujący sposób:

    - Wybierz źródło danych **Trans** jako źródło rekordów, które powinny być zgrupowane.
    - W polu **Lokalizacja wykonywania** wybierz opcję **Zapytanie**, aby określić, że chcesz uruchamiać to źródło danych na poziomie bazy danych.

    ![Konfigurowanie źródła danych na stronie edytowania parametrów funkcji „Grupuj wg”](./media/er-components-inspections-05a.gif)

6. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu** oraz sprawdzić, czy można wykonać zapytanie do skonfigurowanego źródła danych **GroupedTrans**.
7. Zmodyfikuj źródło danych **Trans** poprzez dodanie pola zagnieżdżonego o typie **Pole obliczeniowe**, aby uzyskać przycięty numer konta dostawcy.
8. Nazwij nowe źródło danych **$AccNumber** i skonfiguruj je tak, aby zawierało wyrażenie `TRIM(Trans.AccountNum)`.

    ![Konfigurowanie źródła danych na stronie Projektant mapowania modelu](./media/er-components-inspections-05a.png)

9. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu** oraz sprawdzić, czy można wykonać zapytanie do skonfigurowanego źródła danych **GroupedTrans**.

    ![Weryfikowanie składnika mapowania modelu ER oraz sprawdzanie, czy można wykonać zapytanie do skonfigurowanego źródła danych GroupedTrans na stronie Projektant mapowania modelu](./media/er-components-inspections-05b.png)

10. Zauważ, że występuje błąd sprawdzania poprawności, ponieważ źródło danych **Trans** zawiera zagnieżdżone pole typu **Pole obliczeniowe**, które nie zezwala na przekształcenie wywołania o źródło danych **GroupedTrans** na bezpośrednią instrukcję SQL.

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia i wybrania opcji **Uruchom** w celu uruchomienia formatu skonfigurowanego do używania mapowania modelu.

![Błędy czasu wykonywania występujące w przypadku zignorowania ostrzeżenia wyświetlanego na stronie Projektant formatów](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zamiast dodawać zagnieżdżone pole typu **Pole obliczeniowe** do źródła danych **Trans**, dodaj zagnieżdżone pole **$AccNumber** do elementu **GroupedTrans.lines** w źródle danych **GroupedTrans** i skonfiguruj je w taki sposób, aby zawierało wyrażenie `TRIM(GroupedTrans.lines.AccountNum)`. W ten sposób źródło danych **GroupedTrans** można uruchomić na poziomie SQL, a zagnieżdżone pole **$AccNumber** obliczyć później.

#### <a name="option-2"></a>Opcja 2

Zmień wartość pola **Lokalizacja wykonywania** dla źródła danych **GroupedTrans** z **Zapytanie** na **W pamięci**. Nie zalecamy zmiany wartości dla tabeli zawierającej dużą ilość danych (tabela transakcji), ponieważ zostaną pobrane wszystkie rekordy, a grupowanie i agregowanie zostanie dokonane w pamięci. Z tego względu ta metoda może spowodować pogorszenie wydajności.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Wykonywalność źródła danych typu JOIN

Źródło danych typu [JOIN](er-join-data-sources.md) łączy rekordy z dwóch lub więcej tabel bazy danych na podstawie pól pokrewnych. Każde źródło danych typu **JOIN** można tak skonfigurować, aby było uruchamiane na poziomie bazy danych lub w pamięci. Gdy źródło danych typu **JOIN** skonfigurowano tak, aby było uruchamiane na poziomie bazy danych, moduł ER sprawdza, czy można ustanowić bezpośrednie zapytanie SQL do źródeł danych, do których istnieje odwołanie w tym źródle danych. Jeśli nie można ustanowić bezpośredniego zapytania SQL do co najmniej jednego przywoływanego źródła danych, w projektancie mapowania modelu ER wystąpi błąd sprawdzania poprawności. Odebrany komunikat stwierdza, że skonfigurowane źródło danych **JOIN** nie może być uruchamiane w czasie wykonywania.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik mapowania modelu ER.
2. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
3. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
4. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
5. Nazwij nowe źródło danych **Trans**. W polu **Tabela** wybierz opcję **VendTrans**, aby określić, że to źródło danych będzie żądało tabeli VendTrans.
6. Dodaj źródło danych typu **Pole obliczeniowe** jako zagnieżdżone pole źródła danych **Vendor**.
7. Nazwij nowe źródło danych **FilteredTrans** i skonfiguruj je tak, aby zawierało wyrażenie `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`.
8. Dodaj źródło danych typu **Sprzężenie**.
9. Nazwij nowe źródło danych **JoinedList** i skonfiguruj je w następujący sposób:

    1. Dodaj źródło danych **Vendor** jako pierwszy zbiór rekordów do sprzężenia.
    2. Dodaj źródło danych **Vendor.FilteredTrans** jako drugi zbiór rekordów do sprzężenia. Wybierz **WEWNĘTRZNE** jako typ.
    3. W polu **Wykonaj** wybierz opcję **Zapytanie**, aby określić, że chcesz uruchamiać to źródło danych na poziomie bazy danych.

    ![Konfigurowanie źródła danych na stronie Projektant sprzężenia](./media/er-components-inspections-06a.gif)

10. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu** oraz sprawdzić, czy można wykonać zapytanie do skonfigurowanego źródła danych **JoinedList**.
11. Zmień wyrażenie w źródle danych **Vendor.FilteredTrans** z `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` na `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`.
12. Wybierz opcję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu** oraz sprawdzić, czy można wykonać zapytanie do skonfigurowanego źródła danych **JoinedList**.

    ![Weryfikowanie edytowalnego składnika mapowania modelu oraz sprawdzanie, czy można wykonać zapytanie do skonfigurowanego źródła danych JoinedList na stronie Projektant mapowania modelu](./media/er-components-inspections-06b.png)

13. Zauważ, że występuje błąd sprawdzania poprawności, ponieważ nie można przekształcić wyrażenia źródła danych **Vendor.FilteredTrans** na bezpośrednie wywołanie SQL. Ponadto bezpośrednie wywołanie SQL nie zezwala na przekształcenie wywołania o źródło danych **JoinedList** na bezpośrednią instrukcję SQL.

    ![Błędy czasu wykonywania spowodowane nieudaną weryfikacją źródła danych JoinedList na stronie Projektant mapowania modelu](./media/er-components-inspections-06c.png)

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia i wybrania opcji **Uruchom** w celu uruchomienia formatu skonfigurowanego do używania mapowania modelu.

![Uruchamianie edytowalnego formatu na stronie Projektant formatów](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zmień wyrażenie źródła danych **Vendor.FilteredTrans** z `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` z powrotem na `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`, zgodnie z zaleceniem w ostrzeżeniu.

![Zaktualizowane wyrażenie źródła danych na stronie Projektant mapowania modelu](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>Opcja 2

Zmień wartość pola **Wykonaj** dla źródła danych **JoinedList** z **Zapytanie** na **W pamięci**. Nie zalecamy zmiany wartości dla tabeli zawierającej dużą ilość danych (tabela transakcji), ponieważ zostaną pobrane wszystkie rekordy, a sprzężenie zostanie dokonane w pamięci. Z tego względu ta metoda może spowodować pogorszenie wydajności. Zostanie wyświetlone ostrzeżenie sprawdzania poprawności informujące o tym ryzyku.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>Preferowanie funkcji FILTER wobec WHERE

Funkcja [FILTER](er-functions-list-filter.md) wbudowana w module ER służy do uzyskiwania dostępu do tabel, widoków lub jednostek danych aplikacji poprzez wykonywanie pojedynczego wywołania SQL w celu uzyskania wymaganych danych w postaci listy rekordów. Funkcja [WHERE](er-functions-list-where.md) pobiera wszystkie rekordy z podanego źródła, a wyboru rekordów dokonuje w pamięci. Źródło danych typu **Lista rekordów** jest używane jako argument obu funkcji i określa źródło pozyskiwania rekordów. Moduł ER sprawdza, czy można ustanowić bezpośrednie wywołanie SQL do źródła danych, do którego istnieje odwołanie w funkcji **WHERE**. Jeśli nie można ustanowić bezpośredniego wywołania, w projektancie mapowania modelu ER wystąpi ostrzeżenie sprawdzania poprawności. Odebrany komunikat zaleca użycie funkcji **FILTER** zamiast funkcji **WHERE**, ponieważ działa ona sprawniej.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik mapowania modelu ER.
2. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
3. Nazwij nowe źródło danych **Trans**. W polu **Tabela** wybierz opcję **VendTrans**, aby określić, że to źródło danych będzie żądało tabeli VendTrans.
4. Dodaj źródło danych typu **Pole obliczeniowe** jako zagnieżdżone pole źródła danych **Vendor**.
5. Nazwij nowe źródło danych **FilteredTrans** i skonfiguruj je tak, aby zawierało wyrażenie `WHERE(Trans, Trans.AccountNum="US-101")`.
6. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
7. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
8. Dodaj źródło danych typu **Pole obliczeniowe**.
9. Nazwij nowe źródło danych **FilteredVendor** i skonfiguruj je tak, aby zawierało wyrażenie `WHERE(Vendor, Vendor.AccountNum="US-101")`.
10. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu**.

    ![Sprawdzanie poprawności w celu skontrolowania edytowalnego składnika mapowania modelu na stronie Projektant mapowania modelu](./media/er-components-inspections-07a.png)

11. Zauważ, że ostrzeżenia sprawdzania poprawności zalecają używanie funkcji **FILTER** zamiast funkcji **WHERE** dla źródeł danych **FilteredVendor** i **FilteredTrans**.

    ![Ostrzeżenia sprawdzania poprawności rekomendujące funkcję Filter zamiast funkcji Where na stronie Projektant mapowania modelu](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Wybierz opcję **Napraw**, aby automatycznie zastąpić funkcję **WHERE** funkcją **FILTER** w wyrażeniu we wszystkich źródłach danych wyświetlanych w siatce na karcie **Ostrzeżenia** dla tego typu inspekcji.

Alternatywnie można zaznaczyć wiersz jednego ostrzeżenia w siatce, a następnie wybrać opcję **Napraw wybrane**. W tym przypadku wyrażenie jest automatycznie zmieniane tylko w źródle danych wymienionym w wybranym ostrzeżeniu.

![Wybieranie opcji Napraw w celu automatycznego zastąpienia funkcji WHERE funkcją FILTER na stronie Projektant mapowania modelu](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

Można ręcznie skorygować wyrażenia we wszystkich źródłach danych wymienionych w siatce sprawdzania poprawności, zastępując funkcję **WHERE** funkcją **FILTER**.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Preferowanie funkcji ALLITEMSQUERY wobec ALLITEMS

Funkcje [ALLITEMS](er-functions-list-allitems.md) i [ALLITEMSQUERY](er-functions-list-allitemsquery.md) wbudowane w module ER służą do uzyskania spłaszczonej wartości **Lista rekordów** zawierającej listę rekordów reprezentujących wszystkie elementy pasujące do podanej ścieżki. Moduł ER sprawdza, czy można ustanowić bezpośrednie wywołanie SQL do źródła danych, do którego istnieje odwołanie w funkcji **ALLITEMS**. Jeśli nie można ustanowić bezpośredniego wywołania, w projektancie mapowania modelu ER wystąpi ostrzeżenie sprawdzania poprawności. Odebrany komunikat zaleca użycie funkcji **ALLITEMSQUERY** zamiast funkcji **ALLITEMS**, ponieważ działa ona sprawniej.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik mapowania modelu ER.
2. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
3. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
4. Aby pobierać rekordy kilku dostawców, dodaj źródło danych typu **Pole obliczeniowe**.
5. Nazwij nowe źródło danych **FilteredVendor** i skonfiguruj je tak, aby zawierało wyrażenie `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`.
6. Aby pobierać transakcje wszystkich wyfiltrowanych dostawców, dodaj źródło danych typu **Pole obliczeniowe**.
7. Nazwij nowe źródło danych **FilteredVendorTrans** i skonfiguruj je tak, aby zawierało wyrażenie `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`.
8. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu**.

    ![Strona Projektant mapowania modelu, przycisk Weryfikuj](./media/er-components-inspections-08a.png)

9. Zauważ, że występuje ostrzeżenie sprawdzania poprawności. Komunikat zaleca użycie funkcji **ALLITEMSQUERY** zamiast funkcji **ALLITEMS** dla źródła danych **FilteredVendorTrans**.

    ![Ostrzeżenie sprawdzania poprawności zalecające użycie funkcji ALLITEMSQUERY zamiast funkcji ALLITEMS w składniku mapowania modelu ER na stronie Projektant mapowania modelu](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Wybierz opcję **Napraw**, aby automatycznie zastąpić funkcję **ALLITEMS** funkcją **ALLITEMSQUERY** w wyrażeniu we wszystkich źródłach danych wyświetlanych w siatce na karcie **Ostrzeżenia** dla tego typu inspekcji.

Alternatywnie można zaznaczyć wiersz jednego ostrzeżenia w siatce, a następnie wybrać opcję **Napraw wybrane**. W tym przypadku wyrażenie jest automatycznie zmieniane tylko w źródle danych wymienionym w wybranym ostrzeżeniu.

![Strona Projektant mapowania modelu, zaznaczona opcja Napraw](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

Można ręcznie skorygować wyrażenia we wszystkich źródłach danych wymienionych w siatce sprawdzania poprawności, zastępując funkcję **ALLITEMS** funkcją **ALLITEMSQUERY**.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Uwagi dotyczące przypadków z pustymi listami

Format lub składnik mapowania modelu ER można skonfigurować w taki sposób, aby pobierać wartość pola źródła danych typu **Lista rekordów**. Moduł ER sprawdza, czy projekt uwzględnia przypadek, że wywoływane źródło danych nie zawiera żadnych rekordów (to znaczy jest puste), aby zapobiec błędom wykonywania, gdy wartość jest pobierana z pola nieistniejącego rekordu.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Rozpocznij konfigurowanie jednocześnie modelu danych ER, mapowania modelu ER i składników formatu ER.
2. W drzewie modelu danych dodaj element główny o nazwie **Root3**.
3. Zmodyfikuj element **Root3**, dodając zagnieżdżony element typu **Lista rekordów**.
4. Nazwij nowy zagnieżdżony element **Vendor**.
5. Zmodyfikuj element **Vendor** w następujący sposób:

    - Dodaj pole zagnieżdżone typu **Ciąg** i nadaj mu nazwę **Name**.
    - Dodaj pole zagnieżdżone typu **Ciąg** i nadaj mu nazwę **AccountNumber**.

    ![Dodawanie zagnieżdżonych pól na stronie Model danych](./media/er-components-inspections-09a.png)

6. W okienku źródeł danych mapowania modelu dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
7. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
8. Dodaj źródło danych typu **Ogólne \\ Parametr wprowadzany przez użytkownika**, aby szukać konta dostawcy w oknie dialogowym środowiska uruchomieniowego.
9. Nazwij nowe źródło danych **RequestedAccountNum**. W polu **Etykieta** wpisz **Numer konta dostawcy**. W polu **Nazwa typu danych operacyjnych** pozostaw wartość domyślną **Opis**.
10. Aby wyfiltrować dostawcę, o którego jest wykonywane zapytanie, dodaj źródło danych typu **Pole obliczeniowe**.
11. Nazwij nowe źródło danych **FilteredVendor** i skonfiguruj je tak, aby zawierało wyrażenie `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Powiąż elementy modelu danych ze skonfigurowanymi źródłami danych w następujący sposób:

    - Powiąż **FilteredVendor** z **Vendor**.
    - Powiąż **FilteredVendor.AccountNum** z **Vendor.AccountNumber**.
    - Powiąż **FilteredVendor.'name()'** z **Vendor.Name**.

    ![Powiązanie elementów modelu danych na stronie Projektant mapowania modelu](./media/er-components-inspections-09b.png)

13. W drzewie struktury formatu dodaj następujące elementy w celu wygenerowania dokumentu wychodzącego w formacie XML zawierającego szczegóły dostawcy:

    1. Dodaj główny element XML **Zestawienie**.
    2. Dla elementu XML **Zestawienie** dodaj zagnieżdżony element XML **Strona**.
    3. Dla elementu XML **Strona** dodaj następujące zagnieżdżone atrybuty XML:

        - Imię i nazwisko
        - AccountNum

14. Powiąż elementy formatu z podanymi źródłami danych w następujący sposób:

    - Powiąż element formatu **Zestawienie\\Strona\\Name** z polem źródła danych **model.Vendor.Name**.
    - Powiąż element formatu **Zestawienie\\Strona\\AccountNum** z polem źródła danych **model.Vendor.AccountNumber**.

15. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika formatu na stronie **Projektant formatów**.

    ![Sprawdzanie poprawności elementów formatu powiązanych ze źródłami danych na stronie Projektant formatów](./media/er-components-inspections-09c.png)

16. Zauważ, że występują błędy sprawdzania poprawności. Komunikat stwierdza, że w czasie wykonywania może być zgłaszany błąd dla skonfigurowanych elementów formatu **Zestawienie\\Strona\\Name** i **Zestawienie\\Strona\\AccountNum**, jeżeli lista **model.Vendor** jest pusta.

    ![Błąd sprawdzania poprawności powiadamiający o potencjalnym błędzie w skonfigurowanych elementach formatu](./media/er-components-inspections-09d.png)

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia, wybrania opcji **Uruchom** w celu uruchomienia formatu oraz wybrania numeru konta nieistniejącego dostawcy. Ponieważ żądany dostawca nie istnieje, lista **model.Vendor** będzie pusta (czyli nie będzie zawierała żadnych rekordów).

![Błędy czasu wykonywania występujące po uruchomieniu mapowania formatu](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Dla wybranego wiersza w siatce na karcie **Ostrzeżenia** można wybrać opcję **Usuń powiązanie**. Powiązanie wskazane w kolumnie **Ścieżka** zostanie automatycznie usunięte z elementów formatu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Można ręcznie powiązać element formatu **Zestawienie\\Strona\\Name** z elementem źródła danych **model.Vendor**. W czasie wykonywania powiązanie spowoduje najpierw wywołanie źródła danych **model.Vendor**. Gdy źródło danych **model.Vendor** zwróci pustą listę rekordów, zagnieżdżone elementy formatu nie zostaną uruchomione. Z tego powodu nie występują ostrzeżenia sprawdzania poprawności dla tej konfiguracji formatu.

![Powiązanie elementu formatu z elementem źródła danych na stronie Projektant formatów](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>Opcja 2

Zmień powiązanie elementu formatu **Zestawienie\\Strona\\Name** z `model.Vendor.Name` na `FIRSTORNULL(model.Vendor).Name`. Zaktualizowane powiązanie warunkowo konwertuje pierwszy rekord źródła danych **model.Vendor** o typie **Lista rekordów** na nowe źródło danych o typie **Rekord**. To nowe źródło danych zawiera ten sam zestaw pól.

- Jeśli w źródle danych jest dostępny co najmniej jeden rekord **model.Vendor**, pola tego rekordu są wypełniane wartościami z pól pierwszego rekordu źródła danych **model.Vendor**. W tym przypadku zaktualizowane powiązanie zwraca nazwę dostawcy.
- W przeciwnym razie każde pole tworzonego rekordu jest wypełniane domyślną wartością o typie danych tego pola. W tym przypadku jest zwracany pusty ciąg jako wartość domyślna typu danych **Ciąg**.

Z tego powodu nie występują ostrzeżenia sprawdzania poprawności dla elementu formatu **Zestawienie\\Strona\\Name**, gdy jest on powiązany z wyrażeniem `FIRSTORNULL(model.Vendor).Name`.

![Zmienione powiązanie eliminuje problemy powodujące wyświetlanie ostrzeżeń sprawdzania poprawności na stronie Projektant formatów](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>Opcja 3

Jeśli chcesz jawnie określić dane wprowadzane w wygenerowanym dokumencie, gdy źródło danych **model.Vendor** o typie **Lista rekordów** nie zwraca żadnych rekordów (w tym przykładzie tekst **Niedostępne**), zmień powiązanie elementu formatu **Zestawienie\\Strona\\Name** z `model.Vendor.Name` na `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`. Można również użyć wyrażenia `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`.

### <a name="additional-consideration"></a><a id="i9a"></a>Dodatkowe zagadnienia

Inspekcja ostrzega również o innym potencjalnym problemie. Domyślnie po powiązaniu elementów formatu **Zestawienie\\Strona\\Name** i **Zestawienie\\Strona\\AccountNum** z odpowiednimi polami źródła danych **model.Vendor** o typie **Lista rekordów** te powiązania zostaną uruchomione i będą przyjmować wartości odpowiednich pól pierwszego rekordu źródła danych **model.Vendor**, jeśli ta lista nie jest pusta.

Ponieważ nie powiązano elementu formatu **Zestawienie\\Strona** ze źródłem danych **model.Vendor**, element **Zestawienie\\Strona** nie będzie iterowany dla każdego rekordu źródła danych **model.Vendor** podczas wykonywania formatu. Zamiast tego wygenerowany dokument zostanie wypełniony informacjami tylko z pierwszego rekordu listy rekordów, jeśli ta lista zawiera wiele rekordów. Może więc wystąpić błąd, jeśli format jest przeznaczony do wypełnienia wygenerowanego dokumentu informacjami o wszystkich dostawcach ze źródła danych **model.Vendor**. Aby rozwiązać ten problem, należy powiązać element **Zestawienie\\Strona** ze źródłem danych **model.Vendor**.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Wykonywalność wyrażenia z funkcją FILTER (buforowanie)

Kilka wbudowanych funkcji modułu ER, w tym [FILTER](er-functions-list-filter.md) i [ALLITEMSQUERY](er-functions-list-allitemsquery.md), służy do uzyskiwania dostępu do tabel, widoków lub jednostek danych aplikacji poprzez wykonywanie pojedynczego wywołania SQL w celu uzyskania wymaganych danych w postaci listy rekordów. Źródło danych typu **Lista rekordów** jest używane jako argument w każdej z tych funkcji i określa źródło aplikacji dla tego wywołania. Moduł ER sprawdza, czy można ustanowić bezpośrednie wywołanie SQL do źródła danych, do którego istnieje odwołanie w jednej z tych funkcji. Jeśli nie można ustanowić bezpośredniego wywołania, ponieważ źródło danych zostało oznaczone jako [buforowane](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace), w projektancie mapowania modelu ER wystąpi błąd sprawdzania poprawności. Odebrany komunikat stwierdza, że wyrażenie ER zawierające jedną z tych funkcji nie może zostać uruchomione w czasie wykonywania.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik mapowania modelu ER.
2. Dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
3. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
4. Dodaj źródło danych typu **Ogólne \\ Parametr wprowadzany przez użytkownika**, aby szukać konta dostawcy w oknie dialogowym środowiska uruchomieniowego.
5. Nazwij nowe źródło danych **RequestedAccountNum**. W polu **Etykieta** wpisz **Numer konta dostawcy**. W polu **Nazwa typu danych operacyjnych** pozostaw wartość domyślną **Opis**.
6. Aby wyfiltrować dostawcę, o którego jest wykonywane zapytanie, dodaj źródło danych typu **Pole obliczeniowe**.
7. Nazwij nowe źródło danych **FilteredVendor** i skonfiguruj je tak, aby zawierało wyrażenie `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
8. Oznacz skonfigurowane źródło danych **Vendor** jako buforowane.

    ![Konfigurowanie składnika mapowania modelu na stronie Projektant mapowania modelu](./media/er-components-inspections-10a.gif)

9. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika mapowania modelu na stronie **Projektant mapowania modelu**.

    ![Sprawdzanie poprawności funkcji Filter zastosowanej do buforowanego źródła danych Vendor na stronie Projektant mapowania modelu](./media/er-components-inspections-10a.png)

10. Zauważ, że występuje błąd sprawdzania poprawności. Komunikat stwierdza, że funkcji **FILTER** nie można zastosować do buforowanego źródła danych **Vendor**.

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia i wybrania opcji **Uruchom** w celu uruchomienia formatu.

![Błąd czasu wykonywania występujący po uruchomieniu mapowania formatu na stronie Projektant formatów](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Usuń flagę **Pamięć podręczna** ze źródła danych **Vendor**. Źródło danych **FilteredVendor** stanie się wykonywalne, ale źródło danych **Vendor**, do którego odwołuje się tabela VendTable, będzie używane za każdym razem, gdy jest wywoływane źródło danych **FilteredVendor**.

#### <a name="option-2"></a>Opcja 2

Zmień wyrażenie w źródle danych **FilteredVendor** z `FILTER(Vendor, Vendor.AccountNum="US-101")` na `WHERE(Vendor, Vendor.AccountNum="US-101")`. W tym przypadku dostęp do źródła danych **Vendor**, do którego odwołuje się tabela VendTable, będzie uzyskiwany tylko podczas pierwszego wywołania źródła danych **Vendor**. Jednak wybór rekordów zostanie dokonany w pamięci. Z tego względu ta metoda może spowodować pogorszenie wydajności.

## <a name="missing-binding"></a><a id="i11"></a>Brak powiązania

Podczas konfigurowania składnika formatu modułu ER podstawowy model danych ER jest podpowiadany jako domyślne źródło danych dla formatu ER. Po uruchomieniu skonfigurowanego formatu ER [domyślne mapowanie modelu](er-country-dependent-model-mapping.md) dla modelu podstawowego jest używane do wypełniania modelu danych danymi aplikacji. W projektancie formatów w aplikacji ER jest wyświetlane ostrzeżenie, jeśli powiążesz element formatu z elementem modelu danych, który nie jest powiązany z żadnym źródłem danych w mapowaniu modelu aktualnie zaznaczonym jako domyślne mapowanie modelu dla edytowalnego formatu. Tego typu powiązania nie można uruchomić w czasie wykonywania, ponieważ uruchomiony format nie może wypełnić powiązanego elementu danymi aplikacji. Z tego powodu w czasie wykonywania występuje błąd.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Rozpocznij konfigurowanie jednocześnie modelu danych ER, mapowania modelu ER i składników formatu ER.
2. W drzewie modelu danych dodaj element główny o nazwie **Root3**.
3. Zmodyfikuj element **Root3**, dodając nowy zagnieżdżony element typu **Lista rekordów**.
4. Nazwij nowy zagnieżdżony element **Vendor**.
5. Zmodyfikuj element **Vendor** w następujący sposób:

    - Dodaj pole zagnieżdżone typu **Ciąg** i nadaj mu nazwę **Name**.
    - Dodaj pole zagnieżdżone typu **Ciąg** i nadaj mu nazwę **AccountNumber**.

    ![Dodawanie zagnieżdżonych pól do elementu Vendor na stronie Model danych](./media/er-components-inspections-11a.png)

6. W okienku źródeł danych mapowania modelu dodaj źródło danych typu **Dynamics 365 for Operations \\ Rekordy tabeli**.
7. Nazwij nowe źródło danych **Vendor**. W polu **Tabela** wybierz opcję **VendTable**, aby określić, że to źródło danych będzie żądało tabeli VendTable.
8. Dodaj źródło danych typu **Ogólne \\ Parametr wprowadzany przez użytkownika**, aby wykonywać zapytanie o konto dostawcy w oknie dialogowym środowiska uruchomieniowego.
9 Nazwij nowe źródło danych **RequestedAccountNum**. W polu **Etykieta** wpisz **Numer konta dostawcy**. W polu **Nazwa typu danych operacyjnych** pozostaw wartość domyślną **Opis**.
10. Aby wyfiltrować dostawcę, o którego jest wykonywane zapytanie, dodaj źródło danych typu **Pole obliczeniowe**.
11. Nazwij nowe źródło danych **FilteredVendor** i skonfiguruj je tak, aby zawierało wyrażenie `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Powiąż elementy modelu danych ze skonfigurowanymi źródłami danych w następujący sposób:

    - Powiąż **FilteredVendor** z **Vendor**.
    - Powiąż **FilteredVendor.AccountNum** z **Vendor.AccountNumber**.

    > [!NOTE]
    > Pole modelu danych **Vendor.Name** pozostaje niepowiązane.

    ![Elementy modelu danych powiązane ze skonfigurowanymi źródłami danych oraz element modelu danych pozostający niepowiązany na stronie Projektant mapowania modelu](./media/er-components-inspections-11b.png)

13. W drzewie struktury formatu dodaj następujące elementy w celu wygenerowania dokumentu wychodzącego w formacie XML zawierającego szczegóły dostawców, o których jest wykonywane zapytanie:

    1. Dodaj główny element XML **Zestawienie**.
    2. Dla elementu XML **Zestawienie** dodaj zagnieżdżony element XML **Strona**.
    3. Dla elementu XML **Strona** dodaj następujące zagnieżdżone atrybuty XML:

        - Imię i nazwisko
        - AccountNum

14. Powiąż elementy formatu z podanymi źródłami danych w następujący sposób:

    - Powiąż element formatu **Zestawienie\\Strona** z elementem źródła danych **model.Vendor**.
    - Powiąż element formatu **Zestawienie\\Strona\\Name** z polem źródła danych **model.Vendor.Name**.
    - Powiąż element formatu **Zestawienie\\Strona\\AccountNum** z polem źródła danych **model.Vendor.AccountNumber**.

15. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika formatu na stronie **Projektant formatów**.

    ![Sprawdzanie poprawności składnika formatu ER na stronie Projektant formatów](./media/er-components-inspections-11c.png)

16. Zauważ, że występuje ostrzeżenie sprawdzania poprawności. Komunikat stwierdza, że pole źródła danych **model.Vendor.Name** nie jest powiązane z żadnym źródłem danych w mapowaniu modelu skonfigurowanym do używania przez format. Z tego względu element formatu **Zestawienie\\Strona\\Name** może nie być wypełniany w czasie wykonywania i w efekcie może wystąpić wyjątek czasu wykonywania.

    ![Sprawdzanie poprawności składnika formatu ER na stronie Projektant formatów](./media/er-components-inspections-11d.png)

Na poniższej ilustracji przedstawiono błąd czasu wykonywania, który występuje w przypadku zignorowania ostrzeżenia i wybrania opcji **Uruchom** w celu uruchomienia formatu.

![Uruchamianie edytowalnego formatu na stronie Projektant formatów](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zmodyfikuj skonfigurowane mapowanie modelu, dodając powiązanie dla pola źródła danych **model.Vendor.Name**.

#### <a name="option-2"></a>Opcja 2

Zmodyfikuj skonfigurowany format, usuwając powiązanie dla elementu formatu **Zestawienie\\Strona\\Name**.

## <a name="not-linked-template"></a><a id="i12"></a>Niepołączony szablon

Podczas [ręcznego](er-fillable-excel.md#manual-entry) konfigurowania składnika formatu ER, aby używał szablonu do generowania dokumentu wychodzącego, należy ręcznie dodać element **Excel\\Plik**, dodać wymagany szablon jako załącznik edytowalnego składnika, a następnie wybrać ten załącznik w dodanym elemencie **Excel\\Plik**. W ten sposób wskażesz, że dodany element będzie wypełniał wybrany szablon w czasie wykonywania. Podczas konfigurowania wersji składnika formatu o [stanie](general-electronic-reporting.md#component-versioning) **Wersja robocza** można dodać kilka szablonów do edytowalnego składnika, a następnie wybierać każdy szablon w składniku **Excel\\Plik** w celu uruchamiania formatu ER. W ten sposób można zobaczyć, jak są wypełniane różne szablony w czasie wykonywania. Jeśli masz szablony, które nie są wybierane w żadnych elementach **Excel\\Plik**, projektant formatu w module ER ostrzeżenie, że te szablony zostaną usunięte z wersji edytowalnego składnika formatu ER po zmianie jego stanu z **Wersja robocza** na **Ukończono**.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik formatu ER.
2. W drzewie struktury formatu dodaj element **Excel\\Plik**.
3. Dla dodanego właśnie elementu **Excel\\Plik** dodaj plik skoroszyt programu Excel, **A.xlsx**, jako załącznik. Użyj typu dokumentu skonfigurowanego w [parametrach modułu ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) do określania sposobu przechowywania szablonów formatów ER.
4. Dla elementu **Excel\\Plik** dodaj plik kolejny skoroszyt programu Excel, **B.xlsx**, jako załącznik. Użyj tego samego typu dokumentu, który został użyty dla pliku skoroszytu A.
5. W elemencie **Excel\\Plik** wybierz plik skoroszytu A.
6. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika formatu na stronie **Projektant formatów**.

    ![Sprawdzanie poprawności edytowalnego składnika formatu pliku skoroszytu na stronie Projektant formatów](./media/er-components-inspections-12a.gif)

7. Zauważ, że występuje ostrzeżenie sprawdzania poprawności. Komunikat stwierdza, że plik skoroszytu **B. xlsx** nie jest połączony z żadnymi składnikami i zostanie usunięty po zmianie stanu wersji konfiguracji.

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

Zmodyfikuj skonfigurowany format, usuwając wszystkie szablony, które nie są połączone z żadnym elementem **Excel\\Plik**.

## <a name="not-synced-format"></a><a id="i13"></a>Niezsynchronizowany format

Podczas [konfigurowania](er-fillable-excel.md) składnika formatu ER, aby używał szablonu programu Excel do generowania dokumentu wychodzącego, można ręcznie dodać element **Excel\\Plik**, dodać wymagany szablon jako załącznik edytowalnego składnika, a następnie wybrać ten załącznik w dodanym elemencie **Excel\\Plik**. W ten sposób wskażesz, że dodany element będzie wypełniał wybrany szablon w czasie wykonywania. Ponieważ dodany szablon programu Excel został zaprojektowany zewnętrznie, edytowalny format ER może zawierać nazwy programu Excel, których brakuje w dodanym szablonie. Projektant formatów modułu ER ostrzega o wszelkich niespójnościach między właściwościami elementów formatu ER, które odwołują się do nazw nieistniejących w dodanym szablonie programu Excel.

Poniższe kroki pokazują, jak może dojść do tego problemu.

1. Zacznij konfigurować składnik formatu ER.
2. W drzewie struktury formatu dodaj element **Excel\\Plik** **Report**.
3. Dla dodanego właśnie elementu **Excel\\Plik** dodaj plik skoroszyt programu Excel, **A.xlsx**, jako załącznik. Użyj typu dokumentu skonfigurowanego w [parametrach modułu ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) do określania sposobu przechowywania szablonów formatów ER.

    > [!IMPORTANT]
    > Upewnij się, że dodany skoroszyt programu Excel nie zawiera nazwy **ReportTitle**.

4. Dodaj następujący element **Excel\\Komórka** **Title** jako zagnieżdżony element elementu **Report**. W polu **Zakres programu Excel** wprowadź **ReportTitle**.
5. Wybierz pozycję **Weryfikuj**, aby przeprowadzić inspekcję edytowalnego składnika formatu na stronie **Projektant formatów**.

    ![Sprawdzanie poprawności zagnieżdżonych elementów i pól na stronie Projektant formatów](./media/er-components-inspections-13a.png)

6. Zauważ, że występuje ostrzeżenie sprawdzania poprawności. Komunikat stwierdza, że nazwa **ReportTitle** nie istnieje w arkuszu **Arkusz1** w używanym szablonie programu Excel.

    ![Ostrzeżenie sprawdzania poprawności informujące, że nazwa ReportTitle nie istnieje w arkuszu Arkusz1 w szablonie programu Excel](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Automatyczne rozwiązywanie

Nie jest dostępna żadna opcja automatycznego rozwiązywania tego problemu.

### <a name="manual-resolution"></a>Ręczne rozwiązywanie

#### <a name="option-1"></a>Opcja 1

Zmodyfikuj skonfigurowany format, usuwając wszystkie elementy odwołujące się do nazw programu Excel, których nie ma w szablonie.

#### <a name="option-2"></a>Opcja 2

[Zaktualizuj](er-fillable-excel.md#template-import) edytowalny format ER poprzez zaimportowanie szablonu programu Excel. Struktura edytowalnego formatu ER zostanie [zsynchronizowana](modify-electronic-reporting-format-reapply-excel-template.md) ze strukturą zaimportowanego szablonu programu Excel.

### <a name="additional-consideration"></a>Dodatkowe zagadnienia

Aby dowiedzieć się, jak zsynchronizować strukturę formatu z szablonem ER w edytorze szablonu w module [Zarządzanie dokumentami biznesowymi](er-business-document-management.md), zobacz [Aktualizowanie struktury szablonu dokumentu biznesowego](er-bdm-update-structure.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[ALLITEMS, funkcja ER](er-functions-list-allitems.md)

[ALLITEMSQUERY, funkcja ER](er-functions-list-allitemsquery.md)

[INT64VALUE, funkcja ER](er-functions-conversion-int64value.md)

[INTVALUE, funkcja ER](er-functions-conversion-intvalue.md)

[FILTER, funkcja ER](er-functions-list-filter.md)

[WHERE, funkcja ER](er-functions-list-where.md)

[Używanie źródeł danych typu JOIN do pobierania danych z wielu tabel aplikacji w mapowaniach modeli ER](er-join-data-sources.md)

[Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md)

[Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md)
