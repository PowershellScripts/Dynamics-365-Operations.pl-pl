---
title: Rozszerzone filtrowania RCS w repozytorium RCS/globalnym
description: W tym temacie opisano ulepszone możliwości filtrowania w repozytorium globalnym RCS, które zostało udoskonalone w celu uwzględnienia dodatkowych filtrów.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446674"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>Rozszerzone z RCS opcje filtrowania służące do wyszukiwania konfiguracji w RCS/repozytorium globalnym

[!include [banner](../includes/banner.md)]

W tym temacie opisano ulepszone możliwości filtrowania w repozytorium globalnym Regulatory Configuration Services (RCS), które zostało udoskonalone w celu uwzględnienia możliwości filtrowania następujących kryteriów: 
- **Kraj/region** — Na podstawie kodów krajów ISO  
- Typy **Znaczników** dla:
  - Obszar funkcjonalny
  - Obszar funkcji
  - Branża 
  - Dokument biznesowy 

Aby ułatwić odkrywanie określonych lub powiązanych konfiguracji, można zastosować filtry, pojedynczo lub jako grupę. Aby na przykład znaleźć pojedynczy typ dokumentów biznesowych, które są związane z fakturami od dostawców, można zastosować filtr **Typu dokumentu biznesowego** w celu wyszukania tego typu dokumentu. 

[![Sekcja filtru dla repozytorium globalnego](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

Można dodatkowo uściślić wyszukiwanie, wybierając typ dokumentu, na przykład „faktura od dostawcy”, i klikając przycisk **Zastosuj filtr**. W poniższym przykładzie przedstawiono wyniki filtrowania **typu dokumentu biznesowego** z dodanym typem dokumentu. 

[![Zastosowano filtr i import dla typu dokumentu biznesowego](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Przefiltrowane wyniki mogą być importowane do repozytorium RCS lub środowiska Dynamics 365 Finance albo indywidualnie, albo jako zbiór. W tym celu należy wybrać grupę konfiguracji i kliknąć przycisk **Importuj**.
