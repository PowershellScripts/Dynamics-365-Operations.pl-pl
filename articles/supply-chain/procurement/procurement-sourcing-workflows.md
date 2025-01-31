---
title: Przepływy pracy dla zaopatrzenia i sourcingu
description: Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję. Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy.
author: mkirknel
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22602911fa5d395d439242746f2fe8a27c656bcf
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654155"
---
# <a name="procurement-and-sourcing-workflows"></a>Przepływy pracy dla zaopatrzenia i sourcingu

[!include [banner](../includes/banner.md)]

Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję. Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy.

Przepływ pracy reprezentuje proces biznesowy. Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument. Używanie systemu przepływu pracy w organizacji ma kilka zalet:

- **Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.
- **Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.
- **Scentralizowana Lista prac** — Na scentralizowanej liście prac użytkownicy mogą wyświetlać zadania i zatwierdzenia przepływów pracy przypisane im we wszystkich przepływach pracy, w których uczestniczą. Ta opcja jest dostępna na stronie Elementy pracy.

## <a name="the-types-of-workflows-that-you-can-create"></a> Dostępne typy przepływów pracy

Następujące typy przepływu pracy są dostępne w module Zaopatrzenie i sourcing.

| Typ | Ten typ służy do następujących zadań |
|---|---|
| Przegląd zapotrzebowań na zakup | Tworzenie przepływów pracy przeglądania i zatwierdzania zapotrzebowań zakupu. |
| Przegląd wiersza zapotrzebowania na zakup | Tworzenie przepływów pracy przeglądania i zatwierdzania wierszy zapotrzebowań zakupu. |
| Przepływ pracy zamówienia zakupu | Tworzenie przepływów pracy przeglądania i zatwierdzania dla zamówień zakupu. |
| Przepływ pracy wiersza zamówienia zakupu | Tworzenie przepływów pracy przeglądania i zatwierdzania dla wierszy zamówień zakupu. |
| Przepływ pracy zgłaszania dodania dostawcy | Służy do tworzenia przepływów pracy przeglądania i zatwierdzania w celu dodawania nowych dostawców za pomocą wniosków o nowych dostawców. |

> [!IMPORTANT]
> Podczas dodawania nowego przepływu pracy mogą być również wyświetlane następujące przestarzałe przepływy pracy w oknie dialogowym **Utwórz przepływ pracy**. Są one powiązane z funkcją *potwierdzenia odbioru* dostępną w [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), która jest już przestarzała. Te przepływy pracy są obecnie nieobsługiwane.
> 
> - Przepływ pracy powiadomienia o terminie dostawy
> - Przepływ pracy powiadomienia o otrzymaniu faktury
> - Przepływ pracy powiadamiania o niepowodzeniu przyjęcia produktów
> - Przepływ pracy powiadomienia o odrzuconym niepotwierdzonym dokumencie przyjęcia produktów

## <a name="creating-a-workflow"></a>Tworzenie przepływu pracy

Aby utworzyć przepływ pracy, kliknij kolejno opcje Zaopatrzenie i sourcing &gt; Ustawienia &gt; Przepływy pracy dla zaopatrzenia i sourcingu i utwórz nowy przepływ pracy poprzez wybranie typu przepływu pracy, który chcesz utworzyć. 

Na kanwie przepływu pracy możesz przeciągać elementy przepływu pracy do projektanta i łączyć elementy w sekwencje. Elementy przepływu pracy powinny być skonfigurowane. Dla elementów przepływu pracy zatwierdzania i zadań można skonfigurować, którzy uczestnicy powinni wykonywać czynności.

## <a name="types-of-participants"></a>Typy uczestników

Można przypisać krok zatwierdzania do następujących grup uczestników.

| Grupa użytkowników | Opis |
|---|---|
| Uczestnik | Przypisanie kroku zatwierdzania do członków grupy lub roli. |
| Hierarchia | Przypisz krok zatwierdzania do użytkowników w określonej hierarchii organizacyjnej. |
| Użytkownik przepływu pracy | Przypisanie kroku zatwierdzania do użytkowników tego przepływu pracy. |
| Kolejka | Przypisanie kroku zatwierdzania do kolejki etapów przepływu pracy. |
| Użytkownik | Przypisanie kroku zatwierdzania do określonych użytkowników. |

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Definiowanie przepływów pracy procesów biznesowych dla zapotrzebowań na zakup](https://www.microsoft.com/download/details.aspx?id=101821)
- [Przepływ pracy zapotrzebowań na zakup](purchase-requisitions-workflow.md)
- [Wdrażanie dostawców](vendor-onboarding.md)
