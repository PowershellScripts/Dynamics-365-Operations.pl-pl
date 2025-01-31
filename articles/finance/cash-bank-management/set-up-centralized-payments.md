---
title: Konfigurowanie scentralizowanych płatności
description: Wykonaj następujące kroki, aby przygotować się do przetwarzania płatności w jednej firmie w imieniu innych firm w organizacji.
author: kweekley
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70b47f819730ae221568e625a1b218e046927e41
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446796"
---
# <a name="set-up-centralized-payments"></a>Konfigurowanie scentralizowanych płatności

[!include [banner](../includes/banner.md)]

Wykonaj następujące kroki, aby przygotować się do przetwarzania płatności w jednej firmie w imieniu innych firm w organizacji. Przed rozpoczęciem wykonaj następującą konfigurację:

-   Utwórz firmy.
-   Ustaw parametry księgi głównej i plany kont.
-   Ustaw parametry rozrachunków z dostawcami i parametry rozrachunków z odbiorcami (w zależności od modułów, w których jest używana funkcja płatności scentralizowane).
-   Skonfiguruj księgowanie międzyfirmowe.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Konfigurowanie hierarchii organizacyjnej na potrzeby płatności scentralizowanych
Konfigurowanie hierarchii organizacyjnej na potrzeby płatności scentralizowanych jest konieczne. Do przetwarzania scentralizowanych płatności dostawców i odbiorców jest używana ta sama hierarchia organizacyjna. **Uwaga:** Struktura hierarchii nie ma znaczenia w przypadku scentralizowanych płatności. Dowolna firma w hierarchii będzie mogła przetwarzać płatności w imieniu dowolnej innej firmy w hierarchii. Na stronie **hierarchii organizacyjnych** można utworzyć nową hierarchię organizacyjną. W polu **Cel** musisz wybrać **Płatności scentralizowane**. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Konfigurowanie księgowania międzyfirmowego na potrzeby płatności scentralizowanych
Gdy transakcje płatności w bieżącej firmie są rozliczane za pomocą faktur w innych firmach, dla każdej firmy są tworzone odpowiednie transakcje zobowiązań i należności. Należy określić firmę, dla której są księgowane kwoty rabatu gotówkowego oraz zrealizowane dodatnie lub ujemne różnice kursowe. Przed rozpoczęciem określ firmę używaną w przetwarzaniu płatności odbiorcy i dostawcy. Jeśli jedna firma przetwarza płatności dostawcy, a inna płatności odbiorcy, trzeba będzie przełączyć na każdą z firm. Na stronie **Księgowanie międzyfirmowe** można wybrać rekord relacji międzyfirmowej firmy, w imieniu której będą przetwarzane płatności. 

Na karcie **Płatności scentralizowane** można wybrać, czy rabaty gotówkowe mają być księgowane dla firmy obsługującej płatności (lub inne transakcje powodujące zmniejszenie salda konta dostawcy), czy dla firmy obsługującej faktury (lub inne transakcje powodujące zwiększenie salda konta dostawcy). Ten wybór funkcjonuje w powiązaniu z polem **Zarządzanie rabatami gotówkowymi** na stronach **parametrów rozrachunków z dostawcami** i **parametrów rozrachunków z odbiorcami**. W wypadku nadpłat i rozbieżności dla różnic groszowych jest używane ustawienie firmy obsługującej płatności. W wypadku niedopłat i rozbieżności dla różnic groszowych jest używane ustawienie firmy obsługującej fakturowanie.

## <a name="map-vendor-accounts-across-legal-entities"></a>Mapowanie kont dostawcy na firmy
Jeśli płacisz dostawcy z jednej firmy i chcesz wybrać faktury dla tego dostawcy w innych firmach, musisz się upewnić, że wszystkie odpowiednie konta dostawcy w każdej firmie używają tego samego identyfikatora książki adresowej. Jeśli otrzymujesz płatności odbiorcy, który płaci faktury w więcej niż jednej firmie, to musisz dopilnować, by w odniesieniu do wszystkich odpowiednich kont odbiorcy w każdej firmie były używane te same identyfikatory książki adresowej.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Konfigurowanie profilów księgowania na potrzeby płatności scentralizowanych
Gdy w jednej firmie tworzysz płatność, która skutkuje rozliczeniem faktur w innych firmach, wówczas w każdej firmie musi być używany ten sam identyfikator profilu księgowania. Aby zapewnić poprawne utworzenie płatności, w każdej firmie obsługującej fakturowanie skonfiguruj profil księgowania odpowiadający profilom księgowania używanym w firmie obsługującej płatności. Przełącz do pierwszej firmy obsługującej fakturę, a następnie na stronie **Profile księgowania dostawców** można utworzyć nowy profil księgowania lub edytować istniejący. Opcje wybrane w profilu księgowania firmy obsługującej fakturowanie nie muszą się zgadzać z konfiguracją profilu księgowania w firmie obsługującej płatności.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Konfigurowanie metod płatności na potrzeby płatności scentralizowanych
Gdy w jednej firmie tworzysz płatność, która skutkuje rozliczeniem faktur w innych firmach, wówczas w każdej firmie musi być używany ten sam identyfikator metody płatności. Aby zapewnić poprawne utworzenie płatności, w każdej firmie obsługującej fakturowanie skonfiguruj metodę płatności odpowiadającą metodom płatności używanym w firmie obsługującej płatności. Przełącz do pierwszej firmy obsługującej fakturę, a następnie na stronie **Metody płatności** można utworzyć nową metodę płatności lub edytować istniejącą metodę płatności. Opcje wybrane w przypadku metody płatności firmy obsługującej fakturowanie nie muszą się zgadzać z konfiguracją metody płatności w firmie obsługującej płatności.

## <a name="set-up-default-descriptions"></a>Ustawianie opisów domyślnych
Można zdefiniować domyślne opisy dla załączników rozliczeń międzyfirmowych. Domyślny opis jest dołączany do transakcji „należne do” i „należne od” w trakcie procesu rozliczeń międzyfirmowych. Na stronie **Opisy domyślne** można tworzyć nowe opisy dla **rozliczenia z odbiorcą międzyfirmowym** i **rozliczenia z dostawcą międzyfirmowym** poprzez wybranie języka i wprowadzenie tekstu.



