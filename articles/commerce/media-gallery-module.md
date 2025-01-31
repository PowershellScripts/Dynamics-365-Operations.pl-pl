---
title: Moduł galerii multimediów
description: W tym temacie opisano moduły galerii multimediów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 647387bafe8866cb1bee8c57675629af796f33e6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415037"
---
# <a name="media-gallery-module"></a>Moduł galerii multimediów

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły galerii multimediów i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduły galerii multimediów pokazują jeden lub więcej obrazów w widoku galerii. Moduły galerii multimediów obsługują miniatury obrazów, które można układać poziomo (jako wiersz pod obrazem) lub pionowo (jako kolumna obok obrazu). Moduły galerii multimediów zapewniają również możliwości, które umożliwiają powiększanie (powiększanie) obrazów lub przeglądanie ich w trybie pełnoekranowym. Aby obraz był renderowany w module galerii multimediów, obraz musi być dostępny w bibliotece multimediów narzędzia do tworzenia witryn Commerce. Obecnie moduły galerii multimediów obsługują tylko obrazy.

W trybie domyślnym moduł galerii multimediów używa identyfikatora produktu dostępnego w kontekście strony strony szczegółów produktu (PDP) do renderowania odpowiednich obrazów produktów. W module Commerce Headquarter należy zdefiniować ścieżkę pliku multimedialnego dla wszystkich produktów. Obrazy należy następnie przekazać do biblioteki multimediów konstruktora witryn zgodnie z ścieżką pliku zdefiniowaną dla produktów w Commerce headquarters. Obrazy te zawierają obrazy produktów i wszelkich wariantów produktów. Aby uzyskać więcej informacji na temat przekazywania obrazów do biblioteki multimediów konstruktora witryn, należy zapoznać się z tematem [Przekazywanie obrazów](dam-upload-images.md).

Alternatywnie, moduł galerii multimediów może udostępniać w pełni wyselekcjonowany zestaw obrazów na stronie galerii obrazów, gdzie nie ma zależności od identyfikatora produktu ani kontekstu strony. W takim przypadku obrazy należy przekazać do biblioteki multimediów konstruktora witryn i określić ją w konstruktorze witryn.

Oto kilka przykładów użycia modułów programu galerii multimediów:

- Renderowanie obrazów produktów na PDP
- Renderowanie obrazów produktów na stronie marketingowej produktów
- Prezentowanie wyselekcjonowanego zestawu obrazów na stronie marketingowej, takiej jak strona galerii

W przykładzie na poniższej ilustracji pole zakupu na PDP zawiera obrazy produktów przy użyciu modułu galerii multimediów.

![Przykład pola zakupu na stronie szczegółów produktu obsługującego obrazy produktu przy użyciu modułu galerii multimediów](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Właściwości galerii multimediów

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Źródło obrazu | **Kontekst strony** lub **Identyfikator produktu** | Wartość domyślna to **Kontekst strony**. Jeśli wybrano **Kontekst strony**, moduł oczekuje na stronę do dostarczenia informacji o identyfikatorze produktu. Jeśli wybrano **Identyfikator produktu**, identyfikator produktu dla obrazu musi być podany jako wartość właściwości **Identyfikator produktu**. Ta możliwość jest dostępna w Commerce w wersji 10.0.12. |
| Identyfikator produktu | Identyfikator produktu | Ta właściwość jest stosowana tylko w przypadku, gdy wartość właściwości **Źródło obrazu** to **Identyfikator produktu**. |
| Powiększenie obrazu | **Wbudowane** lub **Kontener** | Ta właściwość umożliwia użytkownikowi powiększenie obrazu w module galeria multimediów. Obraz można powiększać w tekście albo w osobnym kontenerze obok obrazu. Funkcja jest dostępna w 10.0.12 |
| Skala powiększenia | Liczba dziesiętna | Właściwość ta określa współczynnik skali dla powiększania obrazów. Jeśli na przykład wartość jest ustawiona na **2,5**, obrazy zostaną powiększone 2,5 razy.|
| Pełny ekran | **Prawda** lub **Fałsz** | Właściwość ta określa, czy obrazy mogą być wyświetlane w trybie pełnoekranowym. W trybie pełnoekranowym obrazy można również dodatkowo powiększać, jeśli jest włączona funkcja powiększania. Ta możliwość jest dostępna w Commerce w wersji 10.0.13. |
| Obrazy | Obrazy wybrane z biblioteki multimediów konstruktora witryn | Oprócz renderowania z poziomu produktu obrazy mogą być wybrane dla modułu galerii multimediów. Obrazy te zostaną dołączone do wszystkich dostępnych obrazów produktów. Ta możliwość jest dostępna w Commerce w wersji 10.0.12. |
| Orientacja miniatury | **Pionowa** lub **Pozioma** | Właściwość ta określa, czy miniatury obrazów mają być pokazywane w pionowym czy poziomym pasku. |

Na poniższej ilustracji przedstawiono przykład modułu galerii multimediów, w którym są dostępne opcje pełnego ekranu i powiększenia.

![Przykład modułu galerii multimediów, w którym są dostępne opcje pełnego ekranu i powiększenia](./media/ecommerce-media-zoom.png)

Na poniższej ilustracji przedstawiono przykład modułu galerii multimediów, który zawiera wybrane obrazy (czyli określone obrazy nie są zależne od identyfikatora produktu lub kontekstu strony).

![Przykład modułu galerii multimediów, który ma dobrane obrazy](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Gdy źródło obrazu pochodzi z kontekstu strony, identyfikator produktu z PDP jest używany do pobierania obrazów. Moduł galerii multimediów pobiera ścieżkę do pliku obrazu dla produktów przy użyciu interfejsów programowania aplikacji (API) Commerce Scale Unit. Obrazy są następnie pobierane z biblioteki multimediów w taki sposób, aby mogły być renderowane w module.

## <a name="add-a-media-gallery-module-to-a-page"></a>Dodawanie modułu galerii multimediów do nowej strony

Aby dodać moduł galerii multimediów do strony marketingowej, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon marketingowy**, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. W gnieździe **Głównym** na stronie domyślna wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon **Szablon marketingowy**. W sekcji **Nazwa strony** przejdź do **Strona galerii multimediów**, a następnie wybierz przycisk **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Galeria multimediów** i wybierz przycisk **OK**.
1. W okienku właściwości modułu galeria multimediów w obszarze **Źródło obrazu** wybierz opcję **Identyfikator produktu**. W polu **Identyfikator produktu** wprowadź identyfikator produktu.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Obrazy tego produktu powinny być widoczne w widoku galerii.
1. Aby wykorzystać tylko obrazy pod opieką, w okienku właściwości w obszarze **Źródło obrazu** wybierz opcję **Identyfikator produktu**. Następnie w obszarze **Obrazy** wybierz opcję **Dodaj obraz** tyle razy ile potrzeba, aby dodać obrazy z biblioteki multimediów.
1. Umożliwia ustawienie wszelkich dodatkowych właściwości, które mają zostać ustawione, takich jak **Powiększenie obrazu**, **Współczynnik powiększenia** i **Orientacja miniaturek**.
1. Po zakończeniu wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł kontenera](add-container-module.md)

[Przekazanie obrazów](dam-upload-images.md)
