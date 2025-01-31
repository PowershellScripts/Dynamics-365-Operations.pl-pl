---
title: Wyświetlanie zmian adresu i zarządzanie nimi
description: W tym temacie wyjaśniono, w jaki sposób można przeglądać i zarządzać zmianami adresu w Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a69d723b45e834b022491c8eaf2a7fb580e54f1d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420012"
---
# <a name="view-and-manage-address-changes"></a>Wyświetlanie zmian adresu i zarządzanie nimi

W tym temacie wyjaśniono, w jaki sposób można wyświetlać zmiany adresu i zarządzać nimi na stronie **Edytuj dane osobowe pracownika sklepu internetowego** lub strony szczegółów **pracownika** w programie Dynamics 365 Human Resources.

Wiele organizacji chce, aby pracownicy mogli zarządzać własnymi szczegółami, korzystając z funkcji samoobsługi. Można zezwolić użytkownikom na aktualizowanie ich adresów w obszarze roboczym **samoobsługi pracownika etatowego**. Następnie można monitorować te zmiany w obszarze roboczym **zarządzanie kadrami**. Aby użyć tej funkcji, należy określić liczbę dni, które mają zostać wyświetlone, aby wyświetlić zmiany na stronie **Parametry modułu Human Resources**.

## <a name="configure-address-change-parameters"></a>Konfigurowanie parametrów zmiany adresu

Aby skonfigurować liczbę dni, o jaką zmiany adresu mają się pojawiać w obszarze roboczym **zarządzanie personelem**, wykonaj następujące kroki:

1. W okienku nawigacji wybierz opcję **Zarządzanie personelem**.

2. Wybierz **Łącza**.

3. Wybierz **Parametry modułu Human Resources**.

4. W polu **Liczba dni** w obszarze **Zmiana adresu** wprowadź liczbę dni, w ciągu których zmiany adresu mają się pojawiać w obszarze roboczym **Zarządzanie kadrami**.

5. Zamknij stronę.

## <a name="create-or-change-an-employee-address"></a>Utwórz lub zmień adres pracownika etatowego

Pracownicy mogą aktualizować własne adresy w obszarze roboczym **samoobsługi pracownika etatowego**. Wykonaj następujące kroki, aby utworzyć lub zmienić adres:

1. Wybierz kafelek **Samoobsługa pracownika etatowego** na swojej stronie głównej.

2. Wybierz opcję **Edytuj dane osobowe**.

3. Wybierz pozycję **Dodaj**, aby dodać adres. Aby aktualizować istniejący adres, wybierz adres z listy i wybierz opcję **Edytuj**.

4. Wprowadź **Nazwę lub opis**.

5. Zaznacz pole rozwijane **Cel**, a następnie wybierz typ adresu.

6. Wprowadź **Kraj/region**.

7. Wprowadź **ZIP/Kod pocztowy**.

8. Wprowadź **Ulica**.

9. Wprowadź **Miasto**, **Stan** i **Kraj**. Zazwyczaj pola te są automatycznie ustawiane na podstawie pola **ZIP/kod pocztowy**.

10. Opcjonalnie wybierz pole **Podstawowe**, które ma wskazywać adres podstawowy. Jako główny może być zaznaczony tylko jeden adres. Jeśli inny adres jest już oznaczony jako adres podstawowy, musisz potwierdzić, że chcesz używać tego adresu jako adresu podstawowego.

11. Opcjonalnie wybierz pole **Prywatne**, które ma wskazywać adres prywatny. Tylko użytkownicy z wyraźnymi uprawnieniami do przeglądania prywatnych informacji adresowych mogą wyświetlać ten adres.

12. Kliknij przycisk **OK**.

## <a name="create-or-change-a-worker-address"></a>Utwórz lub zmień adres pracownika

Adres można zaktualizować w obszarze roboczym **Zarządzanie personelem**. Wykonaj następujące kroki, aby utworzyć lub zmienić adres:

1. W obszarze roboczym **Zarządzanie personelem** wybierz opcję **Łącza**, a następnie wybierz **Pracownicy**.

3. Wybierz pracownika, a następnie wybierz **Adresy**.

3. Wybierz pozycję **Dodaj**, aby dodać adres. Aby aktualizować istniejący adres, wybierz adres z listy i wybierz opcję **Edytuj**.

4. Wprowadź **Nazwę lub opis**.

5. Zaznacz pole rozwijane **Cel**, a następnie wybierz typ adresu.

6. Wprowadź **Kraj/region**.

7. Wprowadź **ZIP/Kod pocztowy**.

8. Wprowadź **Ulica**.

9. Wprowadź **Miasto**, **Stan** i **Kraj**. Zazwyczaj pola te są automatycznie ustawiane na podstawie pola **ZIP/kod pocztowy**.

10. Opcjonalnie wybierz pole **Podstawowe**, które ma wskazywać adres podstawowy. Jako główny może być zaznaczony tylko jeden adres. Jeśli inny adres jest już oznaczony jako adres podstawowy, musisz potwierdzić, że chcesz używać tego adresu jako adresu podstawowego.

11. Opcjonalnie wybierz pole **Prywatne**, które ma wskazywać adres prywatny. Tylko użytkownicy z wyraźnymi uprawnieniami do przeglądania prywatnych informacji adresowych mogą wyświetlać ten adres.

12. Kliknij przycisk **OK**.
 
## <a name="create-a-future-change-for-an-address"></a>Tworzenie przyszłej zmiany adresu

W niektórych przypadkach może być konieczne zaktualizowanie adresu w celu zmiany w przyszłości. Na przykład byłoby to przydatne, jeśli pracownik wyprowadza się 15 dnia następnego miesiąca.

1. Otwórz stronę **Zarządzanie adresami**, wybierając **Więcej opcji > Zaawansowane** z dowolnej siatki adresów.

2. Wybierz pozycję **Nowy**, aby utworzyć nowy adres.

3. Umożliwia wprowadzenie szczegółów adresu.

4. Wybierz skróconą kartę **Ogólne**.

5. W polu **Data wejścia w życie** wybierz datę, od której będzie obowiązywać nowy adres.

6. Opcjonalnie wybierz pole **Data wygaśnięcia** i określ, kiedy adres nie będzie już obowiązywać.

7. Zamknij strony.

## <a name="view-and-monitor-address-changes"></a>Wyświetlanie i monitorowanie zmian adresu

Pracownicy działu kadr mogą wyświetlać i monitorować zmiany adresów z obszaru roboczego **Zarządzanie personelem**. Aby wyświetlić zmiany adresu, otwórz kafelek **Zarządzanie personelem** ze strony **Głównej**. Adres zmienia się na kafelku w prawym górnym rogu. Liczba powyżej **Zmiany adresu** pokazuje, ile zmian adresu wystąpiło w ciągu liczby dni określonej na stronie **Parametry Human resources**. 

Po wybraniu kafelka **Zmiany adresu** na nowej stronie są wyświetlane szczegółowe informacje o wszelkich zmianach adresu. Opcjonalnie można wybrać opcję **Dołącz przyszłe zmiany adresu** w prawym górnym rogu, aby wyświetlić zmiany w adresie z przyszłą datą.

> [!NOTE]
> Jeśli chcesz otrzymywać alert lub pocztę e-mail o tych zmianach adresu, możesz utworzyć nową regułę alertu na karcie **Opcje** w okienku akcji. Aby uzyskać więcej informacji dotyczących sposobu tworzenia reguł, zobacz [Tworzenie reguł alertów](/fin-ops-core/fin-ops/get-started/create-alert-rules.md).<br><br>

> Jeśli chcesz skonfigurować przepływ pracy dla zmiany adresu, możesz wybrać opcję **Wyślij zewnętrznie** w regule alertu, a następnie użyć Power Automate do wyzwolenia zdarzenia biznesowego i skonfigurowania przepływu pracy. Aby uzyskać więcej informacji, zajrzyj do [Alerty jako zdarzenia biznesowe](/fin-ops-core/dev-itpro/business-events/alerts-business-events.md).
