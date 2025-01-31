---
title: Konfigurowanie informacji o firmie w Attract
description: W tym temacie opisano sposób konfigurowania informacji o firmie i kreowania marki w Microsoft Dynamics 365 Talent- Attract.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: db3ec965f3a52810d5f310697b9ed830c3abe681
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462290"
---
# <a name="configure-company-information-in-attract"></a>Konfigurowanie informacji o firmie w Attract

[!include [banner](includes/banner.md)]

Centrum administracyjne w aplikacji Microsoft Dynamics 365 Talent: Attract zawiera ustawienia konfiguracyjne, opcje integracji i opcje konfiguracji dla aplikacji Attract.

## <a name="company-information"></a>Informacje o firmie

Wprowadź nazwę wyświetlaną firmy i dodaj logo firmy. Odtąd nazwa wyświetlana i logo mogą być używane w ofertach pracy oraz w trakcie wdrażania pracowników do pracy.

## <a name="linkedin-integration"></a>Integracja z serwisem LinkedIn

Konfigurowanie integracji z modułem LinkedIn Recruiter System Connect(RSC). Gdy się połączysz z serwisem LinkedIn przy użyciu swoich poświadczeń użytkownika serwisu LinkedIn, możesz zsynchronizować profil kandydata na LinkedIn, zgłoszenia, opinie po rozmowach kwalifikacyjnych i notatki zespołu rekrutacyjnego. Wymagana jest pełna licencja usługi LinkedIn Recruiter. Aby uzyskać więcej informacji o LinkedIn Recruiter, zobacz [Recruiter System Connect (RSC) — często zadawane pytania](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Uprawnienia użytkownika

Przypisz role użytkownikom w organizacji. Dostępne są następujące role: **Administrator**, **Osoba rekrutująca**, **Menedżer zatrudniający** i **Tylko do odczytu**. Aby uzyskać więcej informacji o uprawnieniach użytkowników, zobacz [Zarządzanie zabezpieczeniami i rolami w aplikacji Attract](./security-attract.md).

## <a name="feature-management"></a>Zarządzanie funkcjami

Nowo dodawane funkcje mogą być wprowadzane w publicznej wersji zapoznawczej. Funkcje w publicznych wersjach zapoznawczych nie spełniają wszystkich wymagań dotyczących jakości usług. Korzystając z takich funkcji, zgadzasz się udostępniać swoje dane do systemów zewnętrznych. Może się okazać, że organizacja nie potrzebuje wszystkich nowych funkcji, które zostały opublikowane. Dlatego w zależności od potrzeb organizacji funkcje w publicznej wersji zapoznawczej można wyłączać i włączać.

## <a name="template-management"></a>Zarządzanie szablonami

Szablon procesu zawiera wszystkie działania, które należy wykonać w procesie rekrutacji na funkcję. Organizacja może pozwolić wszystkim członkom zespołu albo tylko administratorom na tworzenie szablonów procesu rekrutacji. Aby umożliwić członkom zespołu tworzenie własnych szablonów procesu rekrutacji, włącz funkcję Zarządzanie szablonami. Aby uzyskać więcej informacji o szablonach procesów, zobacz [Tworzenie szablonu procesu w aplikacji Attract](./process-templates-attract.md).

## <a name="email-template-settings"></a>Ustawienia szablonu wiadomości e-mail

Organizacje mogą tworzyć szablony wiadomości e-mail dla różnych scenariuszy. Można wybrać obraz nagłówka, który ma być umieszczony w szablonach wiadomości e-mail. Wybrany nagłówek będzie wtedy widoczny we wszystkich szablonach wiadomości e-mail. W stopce szablonu można dodać łącze do firmowych zasad zachowania poufności informacji oraz warunków użytkowania funkcji komunikacyjnych. Aby uzyskać więcej informacji o szablonach, zobacz temat [Szablony wiadomości e-mail](./email-templates.md).

## <a name="offer-process"></a>Proces oferty

Można skonfigurować proces zatwierdzania dla ofert pracy. Na przykład można określić, czy oferta musi zostać zatwierdzona, zanim zostanie wysłana do kandydata. Można również dodać wymóg, aby osoby zatwierdzające wystawiały komentarze do swoich decyzji dotyczących ofert.

Dostępne są dwa przepływy pracy zatwierdzania: **Równoległy** i **Sekwencyjny**.

- **Równoległy** — wnioski o akceptację są wysyłane do wszystkich osób zatwierdzających w tym samym czasie.
- **Sekwencyjny** — wnioski o akceptację są wysyłane do osób zatwierdzających w ustalonej kolejności.

Można również skonfigurować opcje związane ze środowiskiem obsługi kandydata. Na przykład jedna opcja umożliwia określenie, czy kandydaci mogą odrzucić ofertę bez dodatkowych dyskusji. Po ustawieniu opcji **Zezwalaj kandydatom na odrzucanie ofert bez dodatkowych dyskusji** na **Nie** kandydaci mogą używać przycisku **Odrzuć ofertę**. Jeśli ustawisz tę opcję na **Tak**, kandydaci w celu odrzucenia oferty muszą najpierw wybrać przyczynę, a dopiero potem mogą nacisnąć przycisk **Odrzuć ofertę**.

Można także ustawić i wymuszać daty ważności ofert. Po ustawieniu opcji **Wymagaj daty ważności dla wszystkich ofert** na **Tak** oferty wygasają po określonej przez Ciebie liczbie godzin lub dni.

Aby uzyskać więcej informacji o zarządzaniu ofertami, zobacz [Konfigurowanie zarządzania ofertami](./offer-setup.md).
