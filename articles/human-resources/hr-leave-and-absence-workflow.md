---
title: Tworzenie przepływu pracy wniosku urlopowego
description: W programie Dynamics 365 Human Resources można utworzyć przepływ pracy wniosków o urlopy i nieobecności, aby konsekwentnie zarządzać wnioskami urlopowymi.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 209f0ec7236778cc0a828102e554b02206b45b73
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420006"
---
# <a name="create-a-leave-request-workflow"></a>Tworzenie przepływu pracy wniosku urlopowego

W programie Dynamics 365 Human Resources można utworzyć przepływ pracy, aby spójnie zarządzać wnioskami o urlopy i nieobecności. Przepływ pracy **Urlopy i nieobecności** umożliwia:

- Definiowanie zadań
- Określanie, kto musi wykonać te zadania
- Określanie, kto może zatwierdzać lub odrzucać wnioski

## <a name="create-a-leave-and-absence-request-workflow"></a>Tworzenie przepływu pracy wniosków o urlopy i nieobecności

1. Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Przepływy pracy modułu zasobów ludzkich**.

3. Wybierz kolejno opcje **Nowy** i **Wniosek o urlop i nieobecność**. 

4. Gdy pojawi się okno komunikatu **Otworzyć ten plik?**, kliknij przycisk **Otwórz** i zaloguj się przy użyciu firmowych poświadczeń.

5. Za pomocą edytora przepływu pracy utwórz przepływ pracy dla wniosków urlopowych. Więcej informacji na temat pracy z przepływami pracy zawiera temat [Omówienie tworzenia przepływów pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementy danych przepływu pracy wniosków o urlopy i nieobecności

Poniższe elementy danych mogą służyć do tworzenia warunkowych lub automatycznych zatwierdzeń w przepływach pracy dotyczących wniosków o urlopy i nieobecności:

- **Ilość**
- **Komentarz**
- **Firma**
- **Utworzony przez**
- **Data i godzina utworzenia**
- **Data końcowa**
- **Typ urlopu**
- **Zmodyfikowane przez**
- **Data i godzina modyfikacji**
- **Kod przyczyny**
- **Identyfikator wniosku**
- **d. rozpoczęcia**
- **Stan** 
- **Data przesłania**
- **Przesłane przez**
- **Przesłane przez dział kadr**
- **Przesłane przez menedżera**
- **Przesłane w imieniu**
- **Pracownik**
- **Typ pracownika**

Poniższe przykłady pokazują, jak można tworzyć różne typy warunków przepływu pracy za pomocą następujących elementów danych:

- **Kod przyczyny** jest używany w instrukcji warunkowej do przekierowywania wniosków o urlop zdrowotny z kodem przyczyny **Operacja** do zatwierdzenia przez dział kadr oraz do przekierowywania wszystkich innych kodów przyczyn do menedżera. Aby uzyskać więcej informacji na temat instrukcji warunkowych, zobacz temat [Konfigurowanie decyzji warunkowych w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow). 

- Opcje **Przesłanych przez dział kadr** i **Przesłane przez menedżera** są używane w ramach akcji automatycznej w celu automatycznego zatwierdzania wniosków o urlop przesyłanych przez te role w imieniu pracowników. Aby uzyskać więcej informacji o akcjach automatycznych, zobacz temat [Konfigurowanie procesów zatwierdzania w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- **Typ urlopu** jest używany w instrukcji warunkowej lub akcji automatycznej do kontrolowania sposobu, w jaki przepływ pracy kieruje wnioski do określonych typów urlopów.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
