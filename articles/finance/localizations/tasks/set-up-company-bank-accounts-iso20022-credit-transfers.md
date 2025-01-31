---
title: Konfigurowanie kont bankowych firmy dla poleceń przelewu ISO20022
description: Ta procedura przedstawia sposób konfigurowania danych konta bankowego specyficznych dla firmy wymaganych do generowania pliku płatności.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e121ce7d87ee50a4e6b367a170eea4375d64fb3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446721"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Konfigurowanie kont bankowych firmy dla poleceń przelewu ISO20022

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób konfigurowania danych konta bankowego specyficznych dla firmy wymaganych do generowania pliku płatności. Ustawiasz informacje wymagane do wygenerowania formatu polecenia przelewu ISO 20022, ale w zależności od formatu mogą być wymagane dodatkowe informacje, takie jak identyfikator firmy lub numer rozliczeniowy. 

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.

Jest to druga z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="set-up-iban-and-swift-code"></a>Konfigurowanie kodów IBAN i SWIFT
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe.
2. Użyj szybkiego filtru, aby wyfiltrować pole Konto bankowe według wartości „DEMF OPER”.
3. Kliknij pozycję DEMF OPER, aby otworzyć szczegóły konta bankowego.
4. Kliknij przycisk Edytuj.
5. Rozwiń sekcję Dodatkowa identyfikacja.
6. W polu IBAN wpisz wartość „DE89370400440532013000”.
7. W polu Kod SWIFT wpisz wartość „DEUTDEFF”.
    * Należy zauważyć, że kod SWIFT\BIC nie jest wymagany dla wielu formatów płatności, jednak zaleca się zarejestrowanie go dla konta bankowego.  
8. Kliknij przycisk Zapisz.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Konfigurowanie konta bankowego firmy
1. Wybierz kolejno opcje Administrowanie organizacją > Organizacje > Firmy.
2. Kliknij przycisk Edytuj.
3. Rozwiń sekcję Informacje o koncie bankowym.
4. W polu Konto bankowe wprowadź lub wybierz wartość.
5. Kliknij przycisk Zapisz.

