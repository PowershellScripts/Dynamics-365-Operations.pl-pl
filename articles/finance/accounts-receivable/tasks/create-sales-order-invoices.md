---
title: Tworzenie faktur zamówienia sprzedaży
description: W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c504ef36f61613c7aa7db5a1e5ddba6e69cd7285
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446927"
---
# <a name="create-sales-order-invoices"></a>Tworzenie faktur zamówienia sprzedaży

[!include [banner](../../includes/banner.md)]

W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym. Ta procedura wykorzystuje firmę demonstracyjną USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Tworzenie faktury na podstawie zamówienia sprzedaży
1. Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Niezafakturowane zamówienia sprzedaży o stanie Wysłano**.
2. Zaznacz zamówienie sprzedaży na liście. 
3. W **okienku akcji** kliknij pozycję **Faktura > Generuj > Faktura**. Należy zauważyć, że z tym zamówieniem sprzedaży jest skojarzonych wiele dokumentów dostawy. Zamiast numeru dokumentu dostawy będzie wyświetlane tylko słowo <multiple>.  
4. Rozwiń sekcję **Parametry**.
    - W celu zaksięgowania faktury w ustawieniu Księgowanie musi być ustawiona wartość Tak. Można także wyłączyć księgowania i tylko wydrukować fakturę. Jednak ten sam efekt można osiągnąć przez utworzenie faktury pro forma zamiast regularnej faktury.  
    - Ta opcja jest używana do zadań wsadowych. Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.
5. W polu **Drukuj** wybierz opcję „Po”.
6. W obszarze **Drukuj fakturę** zaznacz opcję **Tak**. Funkcja Zarządzanie drukowaniem może wydrukować wiele kopii faktury i również wysłać ją pocztą e-mail jako plik PDF.  
7. W polu **Drukuj opłaty** zaznacz opcję „Podsumowanie”.
8. W polu **Sprawdzanie limitu kredytu** zaznacz opcję „Saldo”.
9. Kliknij **Anuluj**.

## <a name="combine-orders-into-a-single-invoice"></a>Łączenie zamówień w jedną fakturę
1. Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.
2. Odszukaj odbiorcę, który ma otwartych wiele faktur.
3. Umożliwia wybór wielu otwartych zamówień sprzedaży od tego samego odbiorcy.
4. W **okienku akcji** kliknij pozycję **Faktura > Generuj > Faktura**.
5. Rozwiń sekcję **Parametry**.
6. W polu **Ilość** zaznacz opcję „Wszystko”. Należy zwrócić uwagę, że w sekcji Przegląd widać dwie faktury. Scalmy je teraz w jedną fakturę.  
7. W pola **Aktualizacja zbiorcza dla** zaznacz opcję „Konto płatnika”.
8. Kliknij przycisk **Rozmieść**, aby scalić zamówienia sprzedaży w jedną fakturę. Dwa zamówienia sprzedaży są teraz scalone w jedną fakturę.   
9. Kliknij **Anuluj**.
10. Kliknij przycisk **Tak**.

## <a name="post-invoices-in-a-batch"></a>Zbiorcze księgowanie faktur
1. Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Faktury > Fakturowanie zbiorcze > Faktura**.
2. Kliknij opcję **Wybierz**.
3. Kliknij przycisk **OK**.
4. Kliknij przycisk **Zadanie wsadowe**.
5. W polu **Przetwarzanie wsadowe** wybierz opcję **Tak**.
6. Kliknij **Cykl**.
7. Wybierz **Dni**.
8. Kliknij przycisk **OK**.
9. Kliknij przycisk **OK**.
10. Kliknij **Anuluj**.
11. Kliknij przycisk **Tak**.

