---
title: Obszar roboczy Lista kontrolna weryfikacji danych
description: Obszar roboczy Lista kontrolna weryfikacji danych umożliwia śledzenie procesów sprawdzania poprawności danych dla różnych firm, obszarów i osób. Lista kontrolna może być używana podczas nowej implementacji, po wykonaniu uaktualnienia lub po migracji.
author: bking
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: rhaertle
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: a3ac338670fdc9fc7cb526cdcdc1e7199904da8f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687582"
---
# <a name="data-validation-checklist-workspace"></a>Obszar roboczy Lista kontrolna weryfikacji danych

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie obszaru roboczego **Lista kontrolna weryfikacji danych** oraz pokrewnej konfiguracji.

Obszar roboczy **Lista kontrolna weryfikacji** danych umożliwia śledzenie procesów sprawdzania poprawności danych dla różnych firm, obszarów i osób. Lista kontrolna może być używana podczas nowej implementacji, po wykonaniu uaktualnienia lub po migracji. W zależności od widoku obszaru roboczego **Lista kontrolna weryfikacji danych** będą widoczne albo wszystkie zadania i stany dla projektu sprawdzania poprawności danych, albo tylko zadania, które są przypisane do Ciebie.

Należy najpierw wybrać projekt weryfikacji danych w górnej części obszaru roboczego. Wszystkie dane, które są widoczne w obszarze roboczym, są następnie filtrowane według wybranego projektu weryfikacji danych.

## <a name="summary-tiles"></a>Kafelki podsumowania

Kafelki **Podsumowanie** zawierają przegląd procesu, a wskaźniki ułatwiają realizację procesu sprawdzania poprawności danych. Widoczne są wszystkie pozostałe zadani, ukończone zadania, zadania w toku i nierozpoczęte dla procesu. Te informacje dotyczą wszystkich firm, które są uwzględniane w wybranym projekcie weryfikacji danych.

## <a name="tasks-and-status-section"></a>Sekcja Zadania i stan

W sekcji **Zadania i stan** stan całego projektu sprawdzania poprawności danych jest wyświetlany na różne sposoby: według firmy, obszaru i listy zadań. Można również wybrać filtr pokazujący stan dla określonego przedsiębiorstwa. Każda karta stanu pokazuje podział według procentu ukończenia oraz według liczby pozostałych zadań.

Na ostatniej karcie jest szczegółowa lista zadań. Ta lista pokazuje wszystkie zadania.
Listę zadań można filtrować na kilka sposobów. Kliknij przycisk **Edytuj zadanie**, aby zmienić stan zadania i lub przydzielić zadanie. Kliknij przycisk **Załączniki**, aby wyświetlić załączniki do zadania.

Nazwa zadania jest hiperłączem do strony, na którą użytkownik musi przejść, aby ukończyć pracę. To hiperłącze można ustawić przy użyciu pola **Nazwa elementu menu** podczas edytowania lub tworzenia zadania z formularza **Konfiguruj projekt weryfikacji danych**.

Do zadania można dołączać pliki, notatki, obrazy i adresy URL za pomocą akcji **Załączniki**. Na przykład można dołączyć plik raportu wydrukowanego dla zadania. Ikona pojawia się w kolumnie **Załącznik** dla zadania, jeśli załącznik jest obecny.

Opcja **Wykonane przez** jest automatycznie wypełniane po zakończeniu zadania imieniem i nazwiskiem pracownika, który wykonał zadanie. Gdy zadanie jest oznaczone jako ukończone, pole **Data zakończenia** jest automatycznie aktualizowane na bieżącą datę i godzinę.

## <a name="configure-data-validation-project-page"></a>Strona Konfiguruj projekt weryfikacji danych

Aby można było używać obszaru roboczego **Lista kontrolna weryfikacji danych**, należy skonfigurować proces za pomocą strony **Konfiguruj projekt weryfikacji danych**. (Kliknij kolejno opcje **Obszary robocze** \> **Lista kontrolna weryfikacji danych** \> **Konfiguruj projekt weryfikacji danych**).

## <a name="task-areas"></a>Obszary zadań

Za pomocą obszarów zadań można grupować zadania weryfikacji danych w logiczne obszary własności w obrębie organizacji. Obszarami zadań mogą być na przykład Rozrachunki z dostawcami, Rozrachunki z odbiorcami lub Księga główna.

Pole **Nazwa elementu menu** jest skojarzone z pracą w zadaniu i pozwala przejść bezpośrednio do skojarzonej strony z łącza zadania w obszarze roboczym. Na przykład zadanie weryfikacji danych polegające na wygenerowaniu raportu **Wiekowanie rozrachunków z dostawcami** dla modułu Rozrachunki z dostawcami może być połączone ze stroną **Raport o wiekowaniu rozrachunków z dostawcami** strony.
