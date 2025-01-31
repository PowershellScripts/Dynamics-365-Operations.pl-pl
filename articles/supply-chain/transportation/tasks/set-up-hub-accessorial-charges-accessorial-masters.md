---
title: Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych
description: W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad89afe0a21261c57311c439153b969d837748e4
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435684"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum. Procedura wykorzystuje zestaw danych firmy USMF. Konfiguracji zazwyczaj dokonuje koordynator transportu.


## <a name="set-up-a-hub-master"></a>Ustawianie głównego centrum
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główne usługi dodatkowe.
2. Kliknij przycisk Nowy.
3. W polu Główne dodatkowe usługi wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Typ dodatkowych usług wybierz opcję „Centrum”.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="set-up-a-hub-accessorial-charge"></a>Konfigurowanie opłaty za usługi dodatkowe centrum
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Opłaty współpracownika centrum.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator współpracownika centrum wpisz wartość.
4. W polu Centrum kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. W polu Pozycja centrum wybierz opcję.
    * Opłatę można utworzyć za odbiór lub dostawę. W zależności od wybranej opcji opłata będzie stosowana do odpowiedniego segmentu transportu na trasie.  
7. W polu Główne dodatkowe usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz utworzone właśnie dane główne.  
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.

