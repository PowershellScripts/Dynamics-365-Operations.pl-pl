---
title: Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
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
ms.openlocfilehash: c2d0f671d4b824cb5d38a5d11c4b06b2e97bd0c8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528252"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania faktur umowy w Dynamics 365 Field Service z fakturami niezależnymi w Dynamics 365 Supply Chain Management.

## <a name="templates-and-tasks"></a>Szablony i zadania

Następujący szablon i podstawowe zadania są używane do wykonywania synchronizacji faktur za umowy w aplikacji Field Service z fakturami niezależnymi w aplikacji Supply Chain Management.

**Nazwa szablonu w integracji danych**

- Faktury za umowy (rozwiązanie Field Service do Supply Chain Management)

**Nazwy zadań w projekcie integracji danych**

- Nagłówki faktur
- Wiersze faktury

Następująca synchronizacja jest wymagana, zanim będzie można zsynchronizować faktury za umowy:

- Konta (Sales to Supply Chain Management) — bezpośrednie

## <a name="entity-set"></a>Zestaw jednostek

| Field Service  | Zarządzanie łańcuchem dostaw                 |
|----------------|----------------------------------------|
| faktury       | Nagłówki faktur niezależnych dla odbiorców (usługa CDS) |
| invoicedetails | Wiersze faktur niezależnych dla odbiorców (usługa CDS)   |

## <a name="entity-flow"></a>Przepływ jednostek

Faktury tworzone na podstawie umowy w programie Field Service mogą być synchronizowane z programem Supply Chain Management za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS). Aktualizacje tych faktur będą synchronizowane z fakturami niezależnymi w programie Supply Chain Management, jeśli faktury niezależne mają stan księgowania **W trakcie przetwarzania**. Po zaksięgowaniu faktur niezależnych w programie Supply Chain Management i zaktualizowaniu stanu księgowania na **Zakończone** nie będzie można synchronizować aktualizacji z programu Field Service.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service

Do jednostki **Faktury** dodano pole **Zawiera wiersze ze źródłem umowy**. To pole pomaga zagwarantować, że są synchronizowane tylko faktury utworzone na podstawie umowy. Wartością jest **prawda**, jeśli faktura zawiera co najmniej jeden wiersz faktury pochodzący z umowy.

Do jednostki **Wiersz faktury** dodano pole **Zawiera źródło umowy**. To pole pomaga zagwarantować, że są synchronizowane tylko wiersze faktur utworzone na podstawie umowy. Wartością jest **prawda**, jeżeli wiersz faktury pochodzi z umowy.

Pole **Data faktury** jest wymagane w aplikacji Supply Chain Management. W związku z tym musi mieć wartość w programie Field Service, zanim będzie mogła nastąpić synchronizacja. Aby spełnić ten wymóg, dodano następującą logikę:

- Jeśli pole **Data faktury** jest puste w jednostce **Faktura** (tzn. jeśli nie ma wartości), jest w nim ustawiana bieżąca data podczas dodawania wiersza faktury pochodzącego z umowy.
- Użytkownik może zmienić wartość w polu **Data faktury**. Jednak gdy użytkownik próbuje zapisać fakturę pochodzącą z umowy, widzi błąd procesu biznesowego, jeśli pole **Data faktury** jest puste na fakturze.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="in-supply-chain-management"></a>W Supply Chain Management

Na potrzeby integracji należy skonfigurować pochodzenie faktury, tak aby w programie Supply Chain Management odróżniać faktury niezależne utworzone na podstawie faktur za umowy w programie Field Service. Gdy faktura ma pochodzenie typu **Integracja faktury dotyczącej umowy**, pole **Zewnętrzny numer faktury** jest wyświetlane w nagłówku **Faktura sprzedaży**.

Informacje z pola **Zewnętrzny numer faktury** nie tylko pojawiają się w nagłówku faktury, ale mogą również pomóc zagwarantować, że faktury tworzone na podstawie faktur za umowy w programie Field Service są odfiltrowywane podczas synchronizacji faktur między programami Supply Chain Management i Field Service.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Kody pochodzenia faktur**.
2. Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie faktury.
3. W polu **Pochodzenie faktury** nadaj nazwę pochodzeniu faktury, taką jak **FS**.
4. W polu **Opis** wprowadź opis, taki jak **Faktura za umowę w programie Field Service**.
5. Zaznacz pole wyboru **Przypisanie typu pochodzenia**.
6. W polu **Typ pochodzenia faktury** ustaw wartość **Integracja faktury dotyczącej umowy**.
7. Wybierz opcję **Zapisz**.

### <a name="in-the-data-integration-project"></a>W projekcie integracji danych

Zadanie: **Wiersze faktury**  

Upewnij się, że wartość domyślna pola **Wartość wyświetlana konta głównego** w programie Supply Chain Management została zaktualizowana i jest zgodna z żądaną wartością.

Wartość domyślna w szablonie to **401100**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Nagłówki faktur

[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Faktury za umowy (rozwiązanie Field Service do Supply Chain Management): Wiersze faktur

[![Mapowanie szablonu w integracji danych](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)
