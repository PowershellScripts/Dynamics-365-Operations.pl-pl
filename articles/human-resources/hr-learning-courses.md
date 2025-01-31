---
title: Konfigurowanie kursów szkoleniowych
description: Administratorzy zasobów ludzkich i menedżerowie mogą korzystać z funkcji kursów do obsługi informacji o szkoleniu oferowanym pracownikom.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 253f0d07679b6327a0ed1e3cc20ede66249750b8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420134"
---
# <a name="set-up-training-courses"></a>Konfigurowanie kursów szkoleniowych

Administratorzy zasobów ludzkich i menedżerowie mogą korzystać z funkcji kursów do obsługi informacji o szkoleniu oferowanym pracownikom.

 <a name="set-up-prerequisites"></a> Ustawianie wymagań wstępnych
---------------------

Następujące informacje są wymagane i muszą być skonfigurowane przed utworzeniem kursów.
-   **Typy kursów**

Następujące informacje to opcjonalne informacje, które można określić dla kursów. Jeśli wiadomo, że użytkownik będzie wprowadzał te informacje dla kursów, powinien skonfigurować te informacje przed utworzeniem rekordów kursów.
-   **Grupy klas**
-   **Grupy kursów**
-   **Lokalizacje kursu**
-   **Klasy**
-   **Instruktorzy**

## <a name="course-types"></a>Typy kursów
Typy kursów służą do klasyfikowania kursów według struktury lub zawartości kursu. Typy kursów można tworzyć na stronie **Typy kursów**. Tworząc rekord kursu należy wybrać typ dla tego kursu.

## <a name="course-setup-type"></a>Rodzaj ustawień kursu
W poniższej tabeli wymieniono trzy rodzaje ustawień kursów. Typy ustawień określają struktury kursu.

<table>
<thead>
<tr class="header">
<th>Typ ustawień</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Standardowe</strong></td>
<td>Wybierz ten typ dla kursów, które nie będą miały dziennego terminarza. Jest to domyślny typ ustawień przy tworzeniu nowego kursu.</td>
</tr>
<tr class="even">
<td><strong>Terminarz</strong></td>
<td>Wybierz ten typ, aby zaplanować szczegóły każdego dnia kursu, który odbywa się przez kilka dni.</td>
</tr>
<tr class="odd">
<td><strong>Terminarz + sesja</strong></td>
<td>Wybierz ten typ dla bardziej złożonych kursów. Na przykład można podzielić terminarz kursu na ścieżki i sesje.
<ul>
<li><strong>Ścieżka</strong>— Ścieżki to określone obszary tematyczne kursu.</li>
<li><strong>Sesje </strong> – sesje rozdzielają ścieżki i pomagają w określeniu procesów i technik, które są związane z każdą ścieżką.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Zadania kursu
Dla każdego kursu można wykonać następujące zadania.
- Rejestracja uczestników
- Określenie ostatecznego terminu rejestracji
- Określenie minimalnej i maksymalnej liczby uczestników
- Przypisanie lokalizacji i sali
- Hotele rekomendowane uczestnikom kursu
- Utworzenie opisu kursu, który później może zostać zareklamowany w Samoobsłudze pracownika

  >**Uwaga** Kurs można usunąć tylko wtedy, gdy nikt się na niego nie zarejestrował. 

## <a name="course-statuses"></a>Stany kursu
W poniższej tabeli wymieniono możliwe stany i akcje kursu, które można wykonać, gdy kurs ma określony stan.

<table>
<thead>
<tr class="header">
<th>Stan</th>
<th>Akcje</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Utworzony</strong></td>
<td><ul>
<li>Wprowadzanie i modyfikowanie informacji o kursie.</li>
<li>Zmienianie stanu kursu na <strong>Otwarty</strong>, dzięki czemu pracownicy mogą rejestrować się na kursie.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Otwórz</strong></td>
<td><ul>
<li>Rejestrowanie uczestników kursu.</li>
<li>Usuwanie uczestników z kursu.</li>
<li>Zatwierdzanie uczestników kursu.</li>
<li>Zmienianie stanu kursu na <strong> Zamknięty</strong> lub <strong>Anulowany</strong>.</li>
<li>Planowanie kwestionariuszy dla uczestników ze stanem <strong>Potwierdzony</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Zamknięto</strong></td>
<td>Kurs można otworzyć ponownie.</td>
</tr>
<tr class="even">
<td><strong>Anulowano</strong></td>
<td>Kurs można otworzyć ponownie.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Uczestnicy kursu
Uczestnikami kursu są pracownicy, którzy biorą udział w kursie lub wydarzeniu. Można zarejestrować uczestników tylko na kursach otwartych. Minimalną i maksymalną liczbę uczestników, jaką można zarejestrować na kurs, określa się na skróconej karcie **Ogólne** na stronie **Kursy**.

<a name="workflow"></a>System Workflow
--------

Rejestracje pracowników, którzy zapisali się na kurs poprzez stronę **Samoobsługa pracownika etatowego**, mogą zostać przekierowane przez przepływ pracy celem zatwierdzenia. Możesz przypisać przepływ pracy do kursu na skróconej karcie **Ogólne** na stronie **Kursy**.





