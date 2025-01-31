---
title: Dodaj obsługę dla sieci dostarczania zawartości (CDN)
description: W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0e888fca4a5401f1df6e61b10358489846ad4b0e
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517215"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Dodaj obsługę dla sieci dostarczania zawartości (CDN)


[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Podczas konfigurowania środowiska e-Commerce w Dynamics 365 Commerce można skonfigurować je do pracy z usługą CDN. 

Domenę niestandardową można włączyć podczas procesu zastrzegania dla środowiska e-Commerce. Można również skorzystać z żądania usługi w celu skonfigurowania go po zakończeniu procesu zastrzegania. Proces zastrzegania dla środowiska e-Commerce generuje nazwę hosta skojarzoną ze środowiskiem. Ta nazwa hosta ma następujący format: gdzie \<*e-commerce-tenant-name*\> jest nazwą Twojego środowiska:

&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com

Nazwa hosta lub punkt końcowy, który jest generowany podczas procesu zastrzegania, obsługuje certyfikat SSL (Secure Sockets Layer) tylko dla \*.commerce.dynamics.com. Nie obsługuje on protokołu SSL dla domen niestandardowych. Dlatego należy zamknąć protokół SSL dla domen niestandardowych w sieci CDN i przekazać ruch z sieci CDN do nazwy hosta lub punktu końcowego, który został wygenerowany przez moduł Commerce. 

Ponadto *statystyki* (pliki JavaScript lub kaskadowe arkusze stylów \[CSS\]) z modułu Commerce są doręczane z poziomu punktu końcowego, który jest generowany przez moduł Commerce wygenerowany (\*.commerce.dynamics.com). Statyczne dane mogą być buforowane tylko wtedy, gdy nazwa hosta lub punkt końcowy, który został wygenerowany przez moduł commerce, jest umieszczony za CDN.

## <a name="set-up-ssl"></a>Konfigurowanie systemu SSL

Aby zapewnić, że protokół SSL jest skonfigurowany, a statyczne są buforowane, należy skonfigurować sieć CDN w taki sposób, aby była skojarzona z nazwą hosta wygenerowaną przez moduł Commerce dla danego środowiska. Ponadto należy buforować następujący wzorzec wyłącznie dla statycznych: 

/\_msdyn365/\_scnr/\*

Po zainicjowaniu obsługi środowiska Commerce w dostarczonej niestandardowej domenie lub po dostarczeniu niestandardowej domeny środowiska za pomocą żądania obsługi, należy wskazać domenę niestandardową dla nazwy hosta lub punktu końcowego, który jest generowany przez moduł Commerce.

Jak wcześniej wspomniano, wygenerowana nazwa hosta lub punkt końcowy obsługuje certyfikat SSL tylko dla \*.commerce.dynamics.com. Nie obsługuje on protokołu SSL dla domen niestandardowych.

## <a name="cdn-services"></a>Usługi CDN

Ze środowiskiem Commerce można używać dowolnej usługi CDN. Oto dwa przykłady:

- **Microsoft Azure Front Door Service** — rozwiązanie usługi CDN sieci Azure. Aby uzyskać więcej informacji o usługach Azure Front Door Service, zapoznaj sięz dokumentacją usługi [Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Akceleratordynamiczny witryny Akamai** — Aby uzyskać więcej informacji, należy zapoznać się z informacjami o [dynamicznym akceleratorze witryny](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Ustawienia CDN

Proces konfiguracji sieci CDN składa się z następujących ogólnych kroków:

1. Dodaj hosta frontonu
1. Skonfiguruj pulę zaplecza.
1. Konfigurowanie reguł routingu i buforowania

### <a name="add-a-front-end-host"></a>Dodaj hosta frontonu.

Można użyć dowolnej usługi CDN, ale z przykładu w tym temacie jest używana usługa Azure Front Door Service. 

Aby uzyskać informacje na temat konfigurowania usługi Azure Front Door Service, odwiedź witrynę [Szybki start: Tworzenie drzwi frontowych dla globalnej aplikacji sieci Web o dużej dostępności](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Skonfiguruj pulę zaplecza w usłudze Azure Front Door Service

Aby skonfigurować pulę zaplecza w usłudze Azure Front Door Service, wykonaj nastepujące kroki.

1. Dodaj **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** do puli zaplecza jako hosta niestandardowego z pustym nagłówkiem hosta zaplecza końcowego.
1. W obszarze **równoważenie obciążenia** pozostaw wartości domyślne.

Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie zaplecza** w usłudze Azure Front Door Service z podaną nazwą hosta zaplecza.

![Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool.png)

Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie puli zaplecza** w usłudze Azure Front Door Service z domyślnymi wartościami równoważenia obciążenia.

![Kontynuacja Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a>Konfigurowanie reguł w usłudze Azure Front Door Service

Aby skonfigurować regułę routingu w usłudze Azure Front Door Service, wykonaj następujące kroki.

1. Dodawanie reguły routingu.
1. W polu **Nazwa** wpisz **domyślna**.
1. W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.
1. W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.
1. W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\**.
1. W obszarze _*Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.
1. W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.
1. W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**. 
1. Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.
1. Ustawienie opcji **Buforowanie** na **wyłączone**.

Aby skonfigurować regułę buforowania w usłudze Azure Front Door Service, wykonaj następujące kroki.

1. Dodawanie reguły buforowania.
1. W polu **Nazwa** wpisz **statystyki**.
1. W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.
1. W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.
1. W obszarze **Wzory do dopasowania**, w górnym polu wprowadź wartość **/\_msdyn365/\_scnr/\**.
1. W obszarze _*Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.
1. W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.
1. W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**.
1. Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.
1. Ustawienie opcji **Buforowanie** na **wyłączone**.
1. W polu **Zachowanie buforowania ciągu zapytania** wybierz opcję **Buforuj każdy unikatowy adres URL**.
1. W grupie pól **kompresja dynamiczna** wybierz opcję **włączone**.

Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie reguły** w usłudze Azure Front Door Service.

![Onko dialogowe dodaj regułę](./media/CDN_CachingRule.png)

> [!WARNING]
> Jeśli domena, której będziesz korzystać, jest już aktywna i na żywo, Utwórz bilet pomocy technicznej na kafelku **Pomocy technicznej** w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/), aby uzyskać pomoc w następnych etapach. Aby uzyskać więcej informacji, przejrzyj temat [Uzyskaj pomoc techniczną dla aplikacji Finance and Operations lub usług Lifecycle Services (usługi LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Jeśli Twoja domena jest nowa i nie jest wcześniej istniejącą domeną aktywną, możesz dodać swoją domenę niestandardową do konfiguracji usługi Azure Front Door. Umożliwi to kierowanie ruchu internetowego do Twojej witryny za pośrednictwem wystąpienia usługi Azure Front Door. Aby dodać domenę niestandardową (na przykład `www.fabrikam.com`), należy skonfigurować nazwę kanoniczną (CNAME) dla domeny.

Na poniższej ilustracji przedstawiono okno dialogowe **Konfiguracja CNAME** w usłudze Azure Front Door Service.

![Okno dialogowe konfiguracji CNAME](./media/CNAME_Configuration.png)

Za pomocą usługi Azure Front Door Service można zarządzać certyfikatem lub można skorzystać z własnego certyfikatu dla domeny niestandardowej.

Na poniższej ilustracji przedstawiono okno dialogowe **Niestandardowa domena HTTPS** w usłudze Azure Front Door Service.

![Okno dialogowe domeny niestandardowej HTTPS](./media/Custom_Domain_HTTPS.png)

Aby uzyskać szczegółowe instrukcje dotyczące dodawania domeny niestandardowej do Azure Front Door, zamieszczono w temacie [Dodawanie domeny niestandardowej do swoich Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).

Sieć CDN powinna być teraz poprawnie skonfigurowana, aby można było jej używać z witryną Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
