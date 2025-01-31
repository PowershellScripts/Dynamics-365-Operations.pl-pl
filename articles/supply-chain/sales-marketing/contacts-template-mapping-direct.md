---
title: Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania pozycji Kontakt (Kontakty) i Kontakt (Klienci) kont z Dynamics 365 Sales do rozwiązań Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: a252c3ecb12cb6a4dc429f35c8aeab6bd3914d03
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528956"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania pozycji Kontakt (Kontakty) i Kontakt (Klienci) kont bezpośrednio z Dynamics 365 Sales do rozwiązań Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujące szablony i podstawowe zadania są używane do synchronizowania jednostek kontaktów (kontaktów) w programie Sales z jednostkami kontaktów (odbiorcami) w Supply Chain Management.

- **Nazwy szablonów w integracji danych**

    - Kontakty (Sales to Supply Chain Management) — bezpośrednie
    - Kontakty do Klienta (Sales to Supply Chain Management) — bezpośrednie

- **Nazwy zadań w projekcie integracji danych**

    - Kontakty
    - ContactToCustomer

Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (Z Sales do Supply Chain Management)

## <a name="entity-sets"></a>Zestawy jednostek

| Sprzedaż    | Zarządzanie łańcuchem dostaw |
|----------|------------------------|
| Kontakty | Kontakty w usłudze CDS           |
| Kontakty | Odbiorcy V2           |

## <a name="entity-flow"></a>Przepływ jednostek

Kontakty są zarządzane w usłudze Sales i synchronizowane z usługą Supply Chain Management.

Kontakt w programie Sales może stać się kontaktem lub odbiorcą w rozwiązaniu Supply Chain Management. Aby określić, czy kontakt w programie Sales ma być synchronizowany z programem Supply Chain Management jako kontakt lub odbiorca, system sprawdza następujące właściwości kontaktu w programie Sales:

- **Synchronizacja z klientem w programie Supply Chain Management:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**
- **Synchronizacja z kontaktem w programie Supply Chain Management:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje na konto (nie kontakt)

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Do kontaktu dodano nowe pole **Aktywny odbiorca**. To pole służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań. Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury. Tylko te kontakty są synchronizowane z programem Supply Chain Management jako odbiorcy.

Do kontaktu dodano nowe pole **IsCompanyAnAccount**. To pole wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**. Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Supply Chain Management jako kontakty.

Do kontaktu dodano nowe pole **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji. Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji. Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka. Oto przykład: **CON-01000-BVRCPS**

Gdy rozwiązanie integracji dla programu Sales zostanie zastosowane, skrypt uaktualniania ustawia pole **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji. Skrypt uaktualniania ustawia również w polu **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.

## <a name="in-supply-chain-management"></a>W Supply Chain Management

Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**. Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie. W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

### <a name="contact-to-customer"></a>Kontakt > odbiorca

- **CustomerGroup** jest wymagane w Supply Chain Management. Aby ułatwić uniknięcie błędów synchronizacji, można określić wartość domyślną w mapowaniu. Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.

    Wartość domyślna w szablonie to **10**.

- Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wymaganych w usłudze Supply Chain Management. Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.

    - **SiteId** — W programie Supply Chain Management można również określić domyślny oddział. Witryna jest konieczna do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.

        Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.

    - **WarehouseId** — W programie Supply Chain Management można również określić domyślny magazyn. Magazyn jest konieczny do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.

        Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.

    - **LanguageId** — Język jest konieczny do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.
    
        Domyślna wartość pola w szablonie to **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.

### <a name="contact-to-contact"></a>Kontakt > kontakt

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Kontakt > odbiorca

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Powiązane tematy

[Od prospekta do gotówki](prospect-to-cash.md)

[Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management](accounts-template-mapping-direct.md)

[Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales](products-template-mapping-direct.md)

[Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)


