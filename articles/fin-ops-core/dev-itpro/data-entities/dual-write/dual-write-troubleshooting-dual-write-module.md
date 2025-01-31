---
title: Rozwiązywanie problemów z modułem podwójnego zapisu w aplikacjach Finance and Operations
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem podwójnego zapisu w aplikacjach Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2241e7e6219f95115f55bc45a4d94550276e1e21
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683630"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Rozwiązywanie problemów z modułem podwójnego zapisu w aplikacjach Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem **podwójnego zapisu** w aplikacjach Finance and Operations.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Nie można załadować modułu podwójnego zapisywania w aplikacji Finance and Operations

Jeśli nie można otworzyć strony **podwójnego zapisywania**, wybierając opcję **podwójnego zapisywania** w obszarze roboczym **zarządzanie danymi**, prawdopodobnie usługa integracji danych jest niemożliwa. Utwórz bilet pomocy technicznej, aby zażądać ponownego uruchomienia usługi integracji danych.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Błąd podczas próby utworzenia mapy nowej tabeli

**Wymagane poświadczenia w celu rozwiązania problemu:** Ten sam użytkownik, który skonfigurował podwójne zapisywanie.

Podczas próby skonfigurowania nowej jednostki na potrzeby podwójnego zapisywania może pojawić się następujący komunikat o błędzie. Jedyny użytkownik, który może stworzyć mapę, jest użytkownikiem, który konfiguruje połączenie podwójnego zapisu.

*Kod stanu odpowiedzi nie wskazuje powodzenia: 401 (nieautoryzowany)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Błąd podczas otwierania interfejsu użytkownika z podwójnym zapisywaniem

Podczas próby uzyskania dostępu do podwójnego zapisu w obszarze roboczym **zarządzanie danymi** może zostać wyświetlony następujący komunikat o błędzie:

*login.microsoftonline.com odmówił połączenia.*

Aby rozwiązać ten problem, zaloguj się przy użyciu okna prywatnego w Microsoft Edge, w oknie incognito w Chromium lub w oknie incognito w usłudze Google Chrome. Należy również odblokować lub wyczyścić pliki cookie innych firm.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Błąd podczas łączenia środowiska w celu wykonania podwójnego zapisywania lub dodania nowego mapowania tabeli

**Wymagana rola w celu rozwiązania problemu:** administrator systemu w aplikacjach Finance and Operations i Dataverse.

Podczas łączenia lub tworzenia map może wystąpić następujący błąd:

*Kod stanu odpowiedzi nie wskazuje powodzenia: 403 (tokenexchange). <br> Identyfikator sesji: \<your session id\><br> Identyfikator głównego działania: \<your root activity id\>*

Ten błąd może wystąpić, jeśli użytkownik nie ma wystarczających uprawnień, aby połączyć podwójny zapis lub utworzyć mapy. Ten błąd może również wystąpić, jeśli środowisko Dataverse zostało zresetowane bez odłączenia podwójnego zapisu. Każdy użytkownik z rolą administratora systemu w aplikacjach Finance and Operations i Dataverse może łączyć środowiska. Tylko użytkownik instalujący połączenie podwójnego zapisu może dodawać nowe mapowania tabeli. Po zakończeniu instalacji każdy użytkownik z rolą administratora systemu może monitorować stan i edytować mapowania.

## <a name="error-when-you-stop-the-table-mapping"></a>Błąd podczas zatrzymania mapowania tabeli

Podczas próby zatrzymania mapowania tabeli może pojawić się następujący komunikat o błędzie:

*\[Zabroniony\], \[{„stan”: 403, „źródłowy”: „”, „komunikat”: „błąd wymiany tokenów: Użytkownik nie może uzyskać dostępu do połączenia dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx”}\]”. Serwer zdalny zwrócił błąd: (403) zabroniony.*

Ten błąd występuje, gdy połączone środowisko Dataverse jest niedostępne.

Aby rozwiązać ten problem, utwórz bilet dla zespołu integracji danych. Dołącz śledzenie sieci, aby zespół integracji danych mógł oznaczyć mapy jako **Nie uruchomione** na zapleczu.

## <a name="error-while-trying-to-start-an-table-mapping"></a>Błąd podczas próby uruchomienia mapowania tabeli

Podczas próby ustawienia tego stanu mapowania na **Uruchomione** może się pojawić komunikat o błędzie podobny do następującego:

*Nie można ukończyć wstępnej synchronizacji danych. Błąd: błąd podwójnego zapisu — Rejestracja wtyczki nie powiodła się: nie można zbudować metadanych wyszukiwania przy podwójnym zapisie. Odwołanie do obiektu błędu nie jest ustawione na wystąpienie obiektu.*

Poprawka dla tego błędu jest zależna od przyczyny błędu:

+ Jeśli mapowanie ma zależne mapowania, należy pamiętać, aby włączyć mapowania zależne tego mapowania tabeli.
+ Być może w mapowaniu brakuje pól źródłowych lub docelowych. Jeśli brak pola w aplikacji Finance and Operations, należy wykonać kroki w sekcji [Problem braku pól jednostki dla map](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps). Jeśli brakuje pola w Dataverse, w mapowaniu należy kliknąć przycisk **Odśwież tabele**, tak aby pola były automatycznie wstawiane ponownie do mapowania.
