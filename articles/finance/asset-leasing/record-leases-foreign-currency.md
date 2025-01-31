---
title: Rejestrowanie wynajmów w walutach obcych
description: W tym temacie wyjaśniono, jak rejestrować umowy wynajmu w walutach innych niż waluta rozliczeniowa lub waluta raportowania.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 92177d4f808bfec88dabe9277c3d584ed02e401e
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446993"
---
# <a name="record-leases-in-foreign-currencies"></a>Rejestrowanie wynajmów w walutach obcych

[!include [banner](../includes/banner.md)]

Moduł Wynajem składnika majątku uwzględnia umowy wynajmu będące w walutach innych niż rozliczeniowa lub waluta raportowania skonfigurowane na stronie **Ustawienia księgi**. Wszystkie umowy wynajmu powinny być wprowadzane w ich walutach transakcji. Innymi słowy należy je wprowadzić w walucie określonej w umowie wynajmu. W tym temacie wyjaśniono, jak rejestrować umowy wynajmu w walutach innych niż waluta rozliczeniowa lub waluta raportowania.

W przypadku wprowadzenia umowy wynajmu w walucie obcej składnik majątku z prawem do użytkowania (PDU) jest amortyzowany zarówno w walucie rozliczeniowej, jak i w walucie raportowania. Waluty te są konfigurowane na stronie **Ustawienia księgi**. To zachowanie jest również używane do środków trwałych. Podczas tworzenia wpisu wynajmu w walucie obcej należy wybrać walutę transakcji w polu **Waluta**.

Kurs wymiany waluty rozliczeniowej jest wartością domyślną w polu **Kurs wymiany waluty rozliczeniowej**. Kurs wymiany waluty raportowania jest wartością domyślną w polu **Kurs wymiany waluty raportowania**. Te kursy wymiany obowiązywały w dniu rozpoczęcia wynajmu. Pola **Kurs wymiany waluty rozliczeniowej** i **Kurs wymiany waluty raportowania** znajdują się na skróconej karcie **Informacje o kursach wymiany parametrów finansowych i sprawozdawczych** na stronie **Szczegóły wynajmu**.

1. Zaznacz pole wyboru **Stały kurs**, aby zastąpić kurs wymiany wprowadzony automatycznie, a następnie wprowadź nowy kurs.
2. W pozostałych polach wprowadź informacje wymagane dla umowy wynajmu, a następnie wybierz opcję **Utwórz harmonogramy**.
3. Na nowej stronie **Szczegóły wynajmu** wybierz pozycję **Księgi**.
4. Na stronie **Księga wynajmu** na karcie **Informacje o kursach wymiany parametrów finansowych i sprawozdawczych** sprawdź wartości w polach **Waluta rozliczeniowa początkowego składnika majątku z prawem do użytkowania** i **Waluta raportowania początkowego składnika majątku z prawem do użytkowania**. Każde z tych pól zawiera przeliczone saldo składnika majątku z PDU w odpowiedniej walucie. Te pola są aktualizowane po każdej zmianie jakichkolwiek informacji finansowych. Przed potwierdzeniem harmonogramu płatności wybierz opcję **Utwórz harmonogramy**.

    Wpis w arkuszu początkowego ujęcia rejestruje składnik majątku z PDU używający kursów wymiany określonych w umowie wynajmu. Wpis w arkuszu uwzględnia również wartości pól **Waluta rozliczeniowa początkowego składnika majątku z prawem do użytkowania** i **Waluta raportowania początkowego składnika majątku z prawem do użytkowania** .

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>Kolejny pomiar dla wynajmów w walutach obcych

W harmonogramie amortyzacji są wyświetlane oczekiwane kwoty wydatków amortyzacji w walutach raportowania, rozliczeniowej i transakcji.

Aby wyświetlić salda składników majątku z PDU i kwoty amortyzacji w walucie raportowania lub walucie rozliczeniowej, otwórz stronę **Harmonogram amortyzacji składników majątku** i zaznacz pole wyboru **Pokaż kwoty w walucie rozliczeniowej** lub **Pokaż kwoty w walucie raportowania**.

Podczas tworzenia wpisów w arkuszu dotyczących wydatków amortyzacji w odniesieniu do wynajmu denominowanego w walucie obcej we wpisach są używane kursy wymiany określone w umowie wynajmu. Są tam również używane wartości pól **Waluta rozliczeniowa początkowego składnika majątku z prawem do użytkowania** i **Waluta raportowania początkowego składnika majątku z prawem do użytkowania** .

Ostateczna kwota wydatku amortyzacji może zostać obliczona przy użyciu nieco innego kursu wymiany, tak aby składnik majątku z PDU był w pełni amortyzowany w walucie rozliczeniowej i walucie raportowania.

Jeśli wynajem został przeklasyfikowany jako **Odroczony czynsz**, system automatycznie wyczyści kursy wymiany w walutach rozliczeniowej i raportowania, jeśli zostały one już zdefiniowane.
