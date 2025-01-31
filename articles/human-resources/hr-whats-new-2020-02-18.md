---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (18 lutego 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 18 lutego 2020 roku.
author: Darinkramer
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 002b1b8b86c4fb40f46c239669cd5dfead251bfe
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526985"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (18 lutego 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.2903. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w LCS w charakterze informacyjnym.

## <a name="platform-update-32"></a>Aktualizacja platformy Update 32 

Aktualizacja platformy 32 jest teraz dostępna. Aby uzyskać więcej informacji, należy zapoznać się z [Nowości i zmiany w aktualizacji 32 platformy dla Finance and Operations (Luty 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>Wartości wyszukiwania są zapamiętane podczas zmiany opcji widoku w formularzu usprawnionego pracownika (383833)

Teraz nowy formularz **Pracownik** zapamiętuje wartości wyszukiwania po zmianie opcji widoku i zastosowaniu zmian.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>Kafelki podsumowania zarządzania kompensacją w funkcji podglądu przekierowują do niewłaściwego formularza (401861)

Kafelki zarządzania stałymi i zmiennymi wynagrodzeniami wyświetlają poprawne rekordy w nowym formularzu **Pracownik**. Dotyczy wyłącznie funkcji podglądu usprawnionego formularza pracownika etatowego. Tę funkcję podglądu można włączyć w module **Zarządzanie funkcjami**. Aby uzyskać więcej informacji, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-common-data-service-414915"></a>Puste pole stanu dla niektórych rekordów żądań urlopów w Common Data Service (414915)

Ta zmiana powoduje usunięcie błędu w Common Data Service, gdy pole **Stan** w żądaniu urlopu jest ustawione na wartość **Przegląd**. Common Data Service teraz odzwierciedla stan.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>Analiza braków kwalifikacji jest możliwa tylko dla przypisanego zadania (411390)

Można teraz przeprowadzić analizę braków kwalifikacji dla każdego zadania zdefiniowanego w Human Resources.

## <a name="system-currency-doesnt-sync-from-common-data-service-to-human-resources-in-new-environments-418011"></a>Waluta systemowa nie jest synchronizowana z Common Data Service do Human Resources w nowych środowiskach (418011)

Waluta systemowa w Common Data Service może teraz być synchronizowana z Human Resources.

## <a name="in-preview"></a>Wersja próbna

- [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Funkcje zarządzania świadczeniami w wersji zapoznawczej: zarządzanie świadczeniami](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Wkrótce

### <a name="updated-common-data-service-solution"></a>Zaktualizowano rozwiązanie Common Data Service

Nowe rozwiązanie Common Data Service będzie dostępne wkrótce z następującymi zmianami:

| Opis | Zmiana |
| ----------------------------------------- | --- |
| Zmiany encji **Zatrudnienie/Stanowisko** | Dodano **Region wynagrodzenia**</br>Dodano **wymiary finansowe** |
| Zmiany jednostki **Pracownik** | Dodano **Kolejność w nazwisku**</br>Dodano **Pracuje z domu**</br>Dodano **Język**</br>Dodano **Data stażu pracy**</br>Dodano **Rocznica**</br>Dodano **Pierwotna data zatrudnienia** |
| Zmiany jednostki **Zatrudnienie** | Dodano **wymiary finansowe**</br>Dodano **Powód rozwiązania umowy**</br>**Data zakończenia** zmieniona z **daty przejścia**</br>Dodano **Okres próbny** |
| Zmiany jednostki **Adres Pracownika** | Dodano **Ulica**</br>**Wiersz adresu 1**, **wiersz adresu 2** i **wiersz adresu 3** oznaczone do zaniechania |
| Nowe jednostki ustawień wynagrodzeń o zmiennej wysokości | **Typ planu wynagrodzeń o zmiennej wysokości**</br>**Plan wynagrodzeń o zmiennej wysokości**</br>**Reguły wypłat**</br>**Poziom planu wynagrodzeń o zmiennej wysokości** |
| Nowa jednostka **Zatrudnienie kalendarza pracownika** | Dodano **jednostkę kalendarza pracy** |
| Nowa jednostka **Szczegół stanowiska listy płac** | Dodano **Szczegół stanowiska listy płac** |
| Nowa jednostka **Tytuł** | Dodano **Tytuł**. Nowa jednostka **Tytułu** będzie uwzględniana w procesie synchronizacji między Human Resources a Common Data Service. Nie będzie początkowo przywoływany z **Stanowiska pracy** lub jednostek **Zadań**. |

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)