---
title: Rozwiązywanie problemów z konfiguracją magazynu
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas konfiguracji Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646114"
---
# <a name="troubleshoot-warehouse-configuration"></a>Rozwiązywanie problemów z konfiguracją magazynu

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas konfiguracji Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Pojawia się następujący komunikat o błędzie: „Numer identyfikacyjny lub lokalizacja jest nieprawidłowa”.

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie pojawia się podczas skanowania identyfikatora numeru identyfikacyjnego lub lokalizacji.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Upewnij się, że identyfikator numeru identyfikacyjnego nie jest zarezerwowany na coś innego. Ten problem występuje, jeśli wartość, którą użytkownik przeskanował w aplikacji magazynu, była zarówno prawidłową lokalizacją, jak i prawidłowym identyfikatorem numeru identyfikacyjnego. Jednak ten problem został rozwiązany w wersji 10.0.11.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>Pojawia się następujący komunikat o błędzie: „Numer identyfikacyjny musi być określony dla tej lokalizacji”.

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie pojawia się, jeśli utworzysz zlecenie przeniesienia przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”. Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym. Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>Otrzymuję następujący komunikat o błędzie: „Nie można utworzyć wiersza szablonu pracy dla zmiany stanu zapasów, ponieważ typ pracy jest nieprawidłowy. Wybierz inny typ pracy".

### <a name="issue-description"></a>Opis problemu

W przypadku szablonu pracy nie można wybrać *Zmianę stanu zapasów* w kolumnie **Typ pracy** w sekcji **Szczegóły szablonu pracy**.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe. Typ pracy *Zmiana stanu zapasów* jest używany tylko przez procesy systemowe. Nie można go skonfigurować. Ponieważ lista typów prac jest ustalona jako wyliczenie, dodatkowe wpisy nie mogą być filtrowane z menu rozwijanego **Typ pracy**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Otrzymuję następujący komunikat o błędzie: „Ilość jest nieprawidłowa dla jednostki 1%”.

### <a name="issue-description"></a>Opis problemu

Ilość jest nieprawidłowa dla jednostki *każdy*, jeśli w jednej lokalizacji istnieje praca pobrania zawierająca wiele numerów identyfikacyjnych.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Sprawdź, czy pola **Identyfikator grupy sekwencji jednostek** i **Konwersje jednostek** dla zwolnionego produktu lub wariantu produktu są poprawnie ustawione.

Należy zauważyć, że komunikat o błędzie został ulepszony w wersji 10.0.15 (zobacz [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Nowy komunikat o błędzie to „Ilość jest nieprawidłowa. Oczekiwane %1 %2."

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>W dyrektywach lokalizacji dotyczących pracy nad zamówieniem sprzedaży, opcja wielu jednostek SKU nie ocenia wielu akcji dyrektywy lokalizacji.

### <a name="issue-description"></a>Opis problemu

Dyrektywy lokalizacji typu zlecenia pracy *Zamówienia sprzedaży* i typu pracy *Odłożenie* nie oceniają wielu działań dyrektywy lokalizacji, gdy wybrana jest opcja **Wiele jednostek SKU**. Sprawdzana jest tylko akcja dyrektywy pierwszej lokalizacji.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Nowa funkcja *Oceń wszystkie akcje dla dyrektyw lokalizacji dla wielu jednostek SKU* została dodana w wersji 10.0.15 (zobacz [4579866 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Ta funkcja ocenia wszystkie akcje dyrektyw lokalizacji w wielu jednostkach SKU. Jeśli ta funkcja jest wymagana, należy skorzystać [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby ją włączyć.

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a>Nie mogę skorzystać z aplikacji magazynowej, aby przeprowadzić pobieranie częściowe.

### <a name="issue-description"></a>Opis problemu

W przypadku zamówień sprzedaży i przeniesienia nie można pomijać towarów ani wykonać pobrania częściowego.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Na stronie **Elementy menu urządzenia przenośnego** dla każdego elementu menu skonfigurowanego do przetwarzania zamówień sprzedaży lub zamówień przeniesienia ustaw opcję **Zezwalaj na dzielenie pracy** na skróconej karcie **Ogólne** na wartość *Tak*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Jak mogę wykonać zmianę stanu zapasów dla części pracy dotyczącej ilości częściowej?

### <a name="issue-description"></a>Opis problemu

Konieczna jest zmiana stanu zapasów dla częściowej ilości partii.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby umożliwić pracownikom wprowadzenie tej zmiany, można utworzyć element menu dla aplikacji magazynowej. Na stronie **Elementy menu urządzenia przenośnego** utwórz (lub edytuj) element menu, który ma następujące ustawienia:

- **Tryb:** *Praca*
- **Używanie istniejącej pracy:** *Nie*
- **Proces tworzenia pracy:** *Przesunięcie*
- **Wyświetl kolumnę Stan zapasów:** *Tak*

W razie konieczności można skonfigurować inne pola na stronie.
