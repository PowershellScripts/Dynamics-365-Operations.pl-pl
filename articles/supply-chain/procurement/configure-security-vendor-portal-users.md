---
title: Zabezpieczenia użytkowników portalu dostawców
description: W tym artykule wyjaśniono, jak skonfigurować zabezpieczenia dla zewnętrznych dostawców używających portalu dostawców. Informacje te dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72f353448f3b5d1f816bb240a230e26529c9cec3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435508"
---
# <a name="vendor-portal-user-security"></a>Zabezpieczenia użytkowników portalu dostawców

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak skonfigurować zabezpieczenia dla zewnętrznych dostawców używających portalu dostawców. Informacje te dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku.

Funkcjonalność portalu dostawców została zastąpiona rozszerzoną funkcjonalnością portalu współpracy z dostawcami w programie Dynamics 365 for Operations w wersji 1611. Aby uzyskać więcej informacji o konfigurowaniu zabezpieczeń w portalu współpracy z dostawcami, zobacz [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md). Portal dostawców pokazuje ograniczone informacje o zamówieniach zakupu zewnętrznym dostawcom. Konieczne jest prawidłowe ustawienie uprawnień użytkowników Portalu dostawców w systemie Microsoft Dynamics AX, aby dostawcy nie mieli dostępu do dodatkowych informacji w Twojej instalacji systemu Dynamics AX. **Ważne:** w przeciwieństwie do innych użytkowników dostawcy zewnętrzni nie powinni mieć przypisanej roli **SystemUser**. Rola **SystemUser** przyznaje dostęp do zestawu uprawnień, do których nie powinni mieć dostępu użytkownicy zewnętrzni.

## <a name="setting-up-a-vendor-portal-user"></a>Konfigurowanie użytkownika portalu dostawców
Przed utworzeniem konta użytkownika dla kogoś, kto będzie korzystał z Portalu dostawców, trzeba ustawić użytkownikowi możliwość współpracy na Portalu dostawców. Użyj pola **Współpraca dotycząca zamówienia zakupu** na karcie **Ogólne** na stronie **Dostawcy**. Dostawcy zewnętrzni korzystający z Portalu dostawców muszą mieć następującą konfigurację:

-   Konto użytkownika Microsoft Azure Active Directory (AAD) musi być zarejestrowane dla dostawcy na stronie **Użytkownicy** w systemie Dynamics AX.
-   Dostawca musi mieć rolę zabezpieczeń **Vendor (zewnętrzna)**, a nie **SystemUser**. **Uwaga:** Rola **SystemUser** jest przyznawana automatycznie podczas tworzenia nowego konta użytkownika w systemie Dynamics AX. W związku z tym należy usunąć tę rolę i potwierdzić otrzymaną wiadomość z ostrzeżeniem.
-   Użytkownik Dostawca nie powinien mieć uprawnień dodawania pól z tabel zamówienia zakupu do widoku zamówienia zakupu. Na karcie **personalizacji** na karcie **użytkowników** należy ustawić opcję **Jawne personalizacje dozwolone** jako **Nie**.
-   Konto użytkownika należy skojarzyć z zarejestrowaną osobą kontaktową. Na stronie **użytkowników** wybierz osobę kontaktową w polu **Imię i nazwisko**. Wybrana osoba powinna mieć rolę **kontakt** dla odpowiednich dostawców.

Jeśli ta sama osoba wymaga dostępu do portalu dostawców dla wielu kont dostawców (dla różnych podmiotów prawnych), każde konto użytkownika tej osoby musi być skojarzone z tą samą osobą kontaktową. Rola **dostawcy (zewnętrzna)** zawiera wszystkie podstawowe funkcje, które są niezbędne, aby korzystać z funkcji portalu dostawców. Ta konfiguracja pomaga zagwarantować, że interfejs użytkownika, który widzi użytkownik zewnętrzny, zawiera tylko odpowiednie informacje.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Współpraca z dostawcami za pomocą portalu dostawców](collaborate-vendors-vendor-portal.md)



