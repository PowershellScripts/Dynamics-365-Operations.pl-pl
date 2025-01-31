---
title: Przetwarzanie rabatów za płatność
description: Ta procedura przedstawia sposób przekonwertowania zatwierdzonych i przetworzonych rabatów dla odbiorców na faktury korygujące.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 981068d26d232b10efd8d7288daaf7358aee3728
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435348"
---
# <a name="process-rebates-for-payment"></a>Przetwarzanie rabatów za płatność

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób przekonwertowania zatwierdzonych i przetworzonych rabatów dla odbiorców na faktury korygujące. Zadania z przewodnika można wykonać przy użyciu firmy demonstracyjnej USMF. Warunkiem wstępnym dla tego przewodnika jest istnienie jednego lub kilku wniosków rabatowych, które mają stan Zaznacz. Jeśli używasz firmy USMF, przed uruchomieniem tego przewodnika należy wykonać zadania z przewodnika „Generowanie i przetwarzanie rabatów dla odbiorcy”.


## <a name="convert-rebate-claims-to-credit-note"></a>Konwertowanie wniosków rabatowych na fakturę korygującą
1. Przejdź do okna Wszyscy odbiorcy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij pozycję Windykacja.
5. Kliknij opcję Rozlicz transakcje.
6. Kliknij przycisk Funkcje.
7. Kliknij opcję Program rabatowy.
    * Strona Rabaty zawiera listę wniosków rabatowych, które zostały przetworzone w pulpicie rabatów dla odbiorców i mają stan „Zaznacz”.    
8. Kliknij przycisk Edytuj.
    * W polu Zaznacz ustaw znaczniki wyboru dla wniosków, które chcesz dołączyć do faktury korygującej.   
9. Kliknij przycisk Funkcje.
10. Kliknij opcję Tworzenie faktury korygującej.
    * Zostanie wyświetlony komunikat z informacją, że arkusz został zaksięgowany (jest to arkusza zużycia dla modułu rozrachunków z odbiorcami określony na stronie Parametry modułu rozrachunków z odbiorcami). Spowoduje to przeniesienie rzeczywistej kwoty zobowiązań (kredytu) do salda odbiorcy. Oznacza to, że konto odbiorcy zostanie uznane, a konto naliczania Rabatów zostanie obciążone.  
11. Zamknij stronę.
12. Kliknij przycisk Anuluj.
    * Spowoduje to odświeżenie strony, dzięki czemu można zobaczyć aktualizacje.  
13. W okienku akcji kliknij pozycję Windykacja.
14. Kliknij opcję Rozlicz transakcje.
    * Należy zwrócić uwagę, że do salda odbiorcy została dodana transakcja na kwotę ujemną, reprezentująca łączna kwotę rabatu, bez odwołania do faktury.   
15. Kliknij przycisk Anuluj.

