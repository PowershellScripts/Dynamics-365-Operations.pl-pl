---
title: Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży
description: Ten temat opisuje kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21f1b0a34205e192957405bc9d298c45c8bb4d25
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414995"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży

[!include [banner](../includes/banner.md)]

Ten temat opisuje kolejne kroki ręcznego tworzenia, obliczania i księgowania zestawienia dla sklepu. Istnieją także zadania wsadowe, które można skonfigurować na potrzeby tych samych zadań. Kroki konfigurowania i wykonywania zadań wsadowych znajdują się w innych artykułach. Aby wykonać tę procedurę, muszą istnieć transakcji, które zostały wykonane w punkcie sprzedaży, a następnie pobrane do systemu Dynamics 365 Commerce. Nagranie wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz opcję **Finanse sklepu** na stronie głównej.
2. Wybierz opcję **Nowe zestawienie**.
3. W polu **Numer sklepu** wybierz opcję z listy rozwijanej.
4. Kliknij przycisk **OK**.
5. Grupa **Ustawienia** zawiera ustawienia kontrolujące, które transakcje są uwzględniane w zestawieniu i jak są grupowania w wiersze zestawienia. Można otworzyć grupę **Ustawienia** i zmienić te ustawienia lub można użyć ustawień domyślnych.  
    - Pole **Metoda zestawienia** określa sposób grupowania wierszy zestawienia.  
    - Wybierz pracownika lub kasę w polu **Pracownicy/kasa**, aby obliczać zestawienie tylko dla określonego pracownika lub kasy.  
6. W polu **Metoda zamknięcia** wybierz opcję.
7. Wybierz opcję **Oblicz zestawienie** z okienka akcji.
8. Wybierz opcję **Tak**.
    - Po obliczeniu zestawienia powinny być utworzone wiersze z sumami kwot dla każdej użytej metody płatności i metody zestawienia.  
    - Wprowadź zliczoną kwotę w każdym wierszu, jeśli musi ona być wprowadzona lub zaktualizowana. Pole zliczenia jest wypełniane kwotami z deklaracji środków płatniczych sporządzonych w punkcie sprzedaży.  
9. Wybierz opcję **Zaksięguj zestawienie** z okienka akcji.
10. Kliknij przycisk **Zamknij**.
11. Zamknij okienko.
12. Na stronie głównej wybierz opcję **Finanse sklepu**.
13. Wybierz kartę **Zaksięgowane zestawienia**.

