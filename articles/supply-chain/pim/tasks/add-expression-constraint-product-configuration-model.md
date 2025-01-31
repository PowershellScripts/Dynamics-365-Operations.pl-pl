---
title: Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c43d7f768069c5ef201a2823a9aa626b38220073
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435237"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu. Pokazuje sposób wprowadzenia wymogu zastosowania ochrony narożników do głośnika, jeśli użytkownik wybrał metalową maskownicę. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.


## <a name="create-an-expression-constraint"></a>Tworzenie ograniczenia wyrażenia
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Modele konfiguracji produktu.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * W tym przykładzie jest używany model głośnika o wysokiej jakości.  
4. Na liście kliknij łącze w wybranym wierszu.
5. Rozwiń sekcję Ograniczenia.
6. Kliknij przycisk Dodaj.
7. Kliknij przycisk Utwórz.
8. W polu Nazwa wpisz wartość.

## <a name="enter-expression"></a>Wprowadź wyrażenie
1. Kliknij opcję Edytuj wyrażenie.
    * Jeśli na tym etapie nagrania zadania odblokujesz interfejs użytkownika, możesz użyć funkcji IntelliSense i listy symboli, aby utworzyć wyrażenie ograniczenia.  
2. W polu ConstraintBody wpisz „Implies[FrontGrill=="Metal", CornerProtection]”.
    * Ta logika wyrażenia oznacza: Jeśli maskownica jest metalowa, to musi być zaznaczona opcja ochrony narożników.  
3. Kliknij przycisk Sprawdź poprawność.
    * Funkcja sprawdzania poprawności bada całe wyrażenie ograniczenia i wykrywa błędy składniowe.  
4. Kliknij przycisk Zamknij.
5. Kliknij przycisk OK.

