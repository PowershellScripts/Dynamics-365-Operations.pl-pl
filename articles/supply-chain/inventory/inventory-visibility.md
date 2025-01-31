---
title: '`Dodatek Widoczność magazynu'
description: W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625072"
---
# <a name="inventory-visibility-add-in"></a>Dodatek Widoczność magazynu

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Dodatek Widoczność magazynu jest niezależną i wysoko skalowalną mikrodostępną usługą, która umożliwia śledzenie dostępnych zapasów w czasie rzeczywistym, udostępniając w ten sposób globalny widok widoczności zapasów.

Wszystkie informacje dotyczące dostępnych zapasów są eksportowane do usługi w czasie rzeczywistym przez integrację SQL niskiego poziomu. System zewnętrzny uzyskuje dostęp do usługi za pośrednictwem interfejsów API RESTful w celu uzyskania informacji o dostępnych zapasach w danym zbiorze wymiarów, pobierając w ten sposób listę dostępnych stanowisk.

Widoczność zapasów to mikrousługa wbudowana w systemie Common Data Service, co oznacza, że można ją rozszerzyć przez budowanie Power Apps i stosowanie dostosowanych funkcji Power BI w celu spełnienia wymagań biznesowych. Możliwe jest również uaktualnienie indeksu do kwerend magazynowych.

Widoczność zapasów zapewnia opcje konfiguracji, które umożliwiają integrację z wieloma systemami innych firm. Obsługuje on standardowy rozmiar magazynu, możliwe do dostosowania rozszerzenia i standardowe, konfigurowalne obliczone ilości.

W tym temacie opisano sposób instalowania i konfigurowania dodatku widoczność magazynu dla systemu Dynamics 365 Supply Chain Management oraz używania jego interfejsu programowania aplikacji (API).

## <a name="install-the-inventory-visibility-add-in"></a>Instalowanie dodatku Widoczność magazynu

Musisz zainstalować dodatek Widoczność magazynu, korzystając z Microsoft Dynamics Lifecycle Services (LCS). LCS to portal współpracy, który zapewnia środowisko i zbiór regularnie zaktualizowanych usług ułatwiających zarządzanie cyklem życia aplikacji w aplikacjach Dynamics 365 Finance and Operations.

Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Wymagania wstępne

Aby można było zainstalować dodatek Widoczność magazynu, trzeba:

- Uzyskać projekt implementacji usługi LCS z co najmniej jednym wdrożonym środowiskiem.
- Wygeneruj klucze beta dla oferty w LCS.
- Włącz klucze beta dla usługi LCS.
- Skontaktuj się z zespołem ds. produktu Widoczność magazynu Microsoft i podaj identyfikator środowiska, w którym chcesz wdrożyć dodatek Widoczność magazynu.

Jeśli masz pytania dotyczące tych wymagań wstępnych, skontaktuj się z zespołem ds. produktu Widoczność magazynu.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Instalacja aplikacji dodatkowych

Aby zainstalować dodatek Widoczność magazynu, trzeba:

1. Zalogować się do portalu [Microsoft LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Na stronie głównej wybierz projekt, w którym jest wdrożone środowisko.
1. Na stronie projektu wybierz środowisko, w którym chcesz zainstalować dodatek.
1. Na stronie środowiska przewiń w dół, aż zostanie wyświetlona sekcja **Dodatki środowiska**. Jeśli sekcja nie jest widoczna, należy upewnić się, że wstępnie wymagane klucze beta zostały w pełni przetworzone.
1. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
    ![Strona środowiska w LCS](media/inventory-visibility-environment.png "Strona środowiska w LCS")
1. Wybierz opcję **Zainstaluj nowy dodatek**. Zostanie otwarta lista dostępnych dodatków.
1. Wybierz **Usługę zapasy** z listy. (Uwaga: może to być teraz widoczne jako **Dodatek Widoczność magazynu dla Dynamics 365 Supply Chain Management** .)
1. Wprowadź wartości dla następujących pól środowiska:

    - **AAD identyfikatora aplikacji**
    - **Identyfikator AAD dzierżawy**

    ![Strona konfiguracji dodatku](media/inventory-visibility-setup.png "Strona konfiguracji dodatku")

1. Zaakceptuj regulamin, zaznaczając pole wyboru **Regulamin**.
1. Wybierz **Zainstaluj**. Stan dodatku będzie widoczny jako **Instalowany**. Po zakończeniu operacji odśwież stronę, aby zobaczyć zmianę stanu na **Zainstalowane**.

### <a name="get-a-security-service-token"></a>Pobierz token usługi zabezpieczeń

Aby uzyskać token usługi zabezpieczeń, wykonaj następujące czynności:

1. Pobierz `aadToken` i wywołaj punkt końcowy: https://securityservice.operations365.dynamics.com/token.
1. Zastąp `client_assertion` w treści swoim `aadToken`.
1. Zastąp kontekst w treści środowiskiem, w którym chcesz wdrożyć dodatek.
1. Zamień zakres w treści na następujące elementy:

    - Zakres dla MCK — „https://inventoryservice.operations365.dynamics.cn/.default”  
    (Identyfikator aplikacji Azure Active Directory i identyfikator dzierżawy MCK można znaleźć w `appsettings.mck.json` .)
    - Zakres dla PROD — „https://inventoryservice.operations365.dynamics.com/.default”  
    (Identyfikator aplikacji Azure Active Directory i identyfikator dzierżawy PROD można znaleźć w `appsettings.prod.json` .)

    Nowy raport powinien przypominać następujący przykład.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. Otrzymasz `access_token` w odpowiedzi. Do wywołania interfejsu API Widoczność magazynu potrzebny jest token elementu nośnego. Oto przykład.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>Odinstalowywanie dodatku

Aby odinstalować dodatek, wybierz opcję **Odinstaluj**. Odśwież usługi LCS i dodatek Widoczność magazynu zostanie usunięty. Proces odinstalowywania usunie rejestrację dodatku, a także uruchomi zadanie w celu oczyszczenia wszystkich danych biznesowych przechowywanych w usłudze.

## <a name="inventory-visibility-add-in-public-api"></a>Dodatek Widoczność magazynu w API publicznym

Publiczny interfejs API REST w dodatku Widoczność magazynu przedstawia kilka konkretnych punktów końcowych integracji. Obsługuje on trzy główne typy interakcji:

- Księgowanie dostępnych zmian zapasów w dodatku z systemu zewnętrznego.
- Badanie bieżących ilości dostępnych zapasów z systemu zewnętrznego.
- Automatyczna synchronizacja z Supply Chain Management.

Synchronizacja automatyczna nie jest częścią publicznego interfejsu API, ale jest traktowana w tle dla środowisk, w których włączono dodatek widoczności magazynu.

### <a name="authentication"></a>Uwierzytelnianie

Token zabezpieczający platformy jest używany do wywoływania dodatku widoczności magazynu, więc musisz wygenerować token Azure Active Directory przy użyciu Azure Active Directory.

Aby uzyskać więcej informacji na temat uzyskiwania tokenu zabezpieczającego, przejrzyj temat [Instalowanie dodatku Widoczność zapasów](#install-add-in).

### <a name="configure-the-inventory-visibility-api"></a>Skonfiguruj interfejs API funkcji Widoczność magazynu

Przed rozpoczęciem korzystania z usługi należy wykonać konfiguracje opisane w poniższych podsekcjach. Konfiguracja może się różnić w zależności od szczegółów środowiska. Obejmuje ono głównie cztery części:

- [Partycjonowanie](#partitioning)
- [Konfiguracje wymiarów](#dimension-configurations)
- [Indeksowanie](#indexing)
- [Miara niestandardowa](#custom-measurement)

#### <a name="partitioning"></a>Partycjonowanie

Partycjonowanie może znacząco wpłynąć na wydajność interfejsu API funkcji Widoczność magazynu. Dobrym pomysłem jest zdefiniowanie schematu, który umożliwi obsługę małych grup danych, a jednocześnie pozwala na uzyskanie istotnych kwerend dotyczących danych.

`organizationId` (`dataAreaId` w Supply Chain Management) zawsze jest częścią partycjonowania, a domyślnie Widoczność magazynu jest ustawiana jako partycja według wymiarów jako *Oddział + Lokalizacja*. Oznacza to, że usługa musi być zawsze kwerendą o wymiarach zdefiniowane w filtrach.

> [!NOTE]
> *Oddział* i *Lokalizacja* to dwa ogólne wymiary domyślne w obszarze Widoczność zapasów. W Supply Chain Management te wymiary są nazywane *Oddziałem* (`InventSiteId`) i *Magazynem* (`InventLocationId`)

### <a name="dimension-configurations"></a>Konfiguracje wymiarów

Widoczność magazynu będzie zawierać listę ogólnych wymiarów, które umożliwiają integrację z systemem z wieloma źródłami.

W poniższej tabeli wymieniono wymiary magazynowe, które będą domyślnymi nazwami wymiarów widocznymi w obszarze Widoczność zapasów.

| Typ wymiaru | Nazwa wymiaru |
|---|---|
| Produkt | `ColorId` |
| Produkt | `SizeId` |
| Produkt | `StyleId` |
| Produkt | `ConfigId` |
| Śledzenie | `BatchId` |
| Śledzenie | `SerialId` |
| Lokalizacja | `LocationId` |
| Lokalizacja | `SiteId` |
| Stan zapasów | `StatusId` |
| Właściwe dla magazynu | `WMSLocationId` |
| Właściwe dla magazynu | `WMSPalletId` |
| Właściwe dla magazynu | `LicensePlateId` |

> [!NOTE]
> Typ wymiaru wymieniony w poprzedniej tabeli służy tylko do celów informacyjnych. Nie trzeba definiować typu wymiaru w funkcji Widoczność zapasów.

Jeśli wymiar niestandardowy istnieje i musi przepływać do wartości domyślnej w przypadku zużycia przez Widoczność zapasów, można skonfigurować **niestandardową** nazwę wymiaru w funkcji Widoczność zapasów.

Widoczność zapasów w systemie zewnętrznym za pośrednictwem interfejsów API RESTful, które umożliwiają uzyskiwanie dostępnych informacji na temat danego zestawu wymiarów do zbadania. W przypadku integracji funkcja Widoczność zapasów umożliwia skonfigurowanie *źródła danych kanału zewnętrznego* i wymiaru źródłowego do *Wymiarów docelowych* w ramach funkcji Widoczność zapasów.

Wymiar docelowy powinien mieć jedną z następujących wartości:

- Wymiary domyślne w funkcji Widoczność zapasów
- Wymiary niestandardowe

Celem konfiguracji wymiarów jest ujednolicenie integracji wielosystemowej dla kwerendy dotyczącej wymiarów i zdarzenia księgowania z wymiarami.

#### <a name="indexing"></a>Indeksowanie

W większości momentów zapytanie o dostępne zapasy nie będzie zwracane tylko na najwyższym poziomie „suma”, ale wyniki zagregowane mogą być wyświetlane na podstawie wymiarów magazynowych.

Widoczność zapasów zapewnia elastyczność, umożliwiając konfigurowanie indeksów opartych na wymiarze lub kombinacji wymiarów.

> [!NOTE]
> Obecnie można konfigurować indeksy tylko do maks. pięć. Należy dokładnie rozważyć, którą kombinację wymiarów należy zastosować przed implementacją, aby zagwarantować, że będzie ona zgodna z potrzebami biznesowymi. Na przykład, jeśli chcesz zbadać produkty w następujący sposób:

- Umożliwia wykonanie kwerendy dotyczącej zagregowanych dostępnych zapasów towaru, korzystając z wymiarów *Kolor* i *Rozmiar*.
- W niektórych przypadkach użytkownik chce jedynie wykonać kwerendę dotyczącą produktu łącznie.

Dwa indeksy powinny mieć zdefiniowane następujące elementy:

- `["ColorId", "SizeId"]`
- `[]`

Pusty nawias będzie agregował na podstawie identyfikatora produktu w partycji.

Indeksowanie określa sposób grupowania wyników na podstawie ustawienia kwerendy `groupBy`. W takim przypadku, jeśli nie zostaną zdefiniowane żadne wartości `groupBy`, sumy będą pobierane według `productid`. W przeciwnym razie, jeśli zostanie zdefiniowana `groupBy` jako `groupBy=ColorId&groupBy=SizeId`, zostanie otrzymanych wiele wierszy na podstawie różnych kombinacji koloru i rozmiaru w systemie.

Kryteria kwerendy można umieścić w treści żądania.

Oto przykładowe zapytanie dotyczące produktu z kombinacją koloru i rozmiaru.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a>Miara niestandardowa

Domyślne ilości miar są połączone z Supply Chain Management, jednak może zaistnieć potrzeba utworzenia ilości składającej się z kombinacji domyślnych miar. W tym celu można skonfigurować niestandardowe ilości, które zostaną dodane do danych wyjściowych zapytań dostępnych zapasów.

Funkcja umożliwia po prostu zdefiniowanie zestawu miar, które będą dodawane, i/lub zestawu miar, które zostaną odjęte od miary niestandardowej.

Na przykład przy użyciu poniższego warunku kwerendy można skonfigurować niestandardową ilość miary jako `MyCustomAvailableforReservation`, która będzie zużywana przez system zużycia.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| System zużycia | Obliczone miary | Źródło danych | Modyfikator | Typ obliczania modyfikatora |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Dodanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Dodanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Odejmowanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Dodanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Odejmowanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Dodanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Dodanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Odejmowanie |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Odejmowanie |

Dzięki temu kwerenda dotycząca niestandardowej ilości miary zwróci następujące dane wyjściowe.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Dane wyjściowe `MyCustomAvailableforReservation` są oparte na ustawieniu obliczania w niestandardowych pomiarach jako:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Księgowanie zmian dostępnych zapasów

Dokładny adres URL, na który zostanie ogłoszone zdarzenie, zależy od regionu geograficznego. Przyjmie on postać:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Po uwierzytelnieniu ten adres URL może być używany wraz z HTTP `POST` w celu wysyłania do usługi zdarzeń zmiany dostępnych zapasów.

Specjalny nagłówek jest używany do komunikowania się z usługami Dynamics 365 Services za pośrednictwem żądań HTTP, oznaczający identyfikator środowiska Supply Chain Management, z którym są połączone dane. Na przykład:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Wysyłanie zapytania o zmiany dostępnych zapasów — przykład 1

W tym przykładzie przedstawiono scenariusz, w którym zostanie ustawiona konfiguracja wymiaru w programie Power Apps.

Aby skonfigurować mapowanie wymiaru w programie, należy skorzystać z następującej kwerendy Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Teraz można określić `dimensionDataSource` i zastosować w kwerendach niestandardowe wymiary. System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Wysyłanie zapytania o zmiany dostępnych zapasów — przykład 2

W tym przykładzie przedstawiono scenariusz, w którym nie skonfigurowano żadnych mapowań konfiguracji wymiarów w systemie Power Apps, więc Księgowanie powinno również mieć wymiary podstawowe. Wszystkie wymiary muszą być wymiarami podstawowymi, jeśli pole `dimensionDataSource` ma wartość null, jest puste lub zawiera białe znaki.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Edytowanie pól właściwości dokumentów JSON

Pola z dostarczonych wcześniej przykładów zapytania JSON mają właściwości wymienione w poniższej tabeli.

| Identyfikator pola | opis |
|---|---|
| `id` | Unikatowy identyfikator określonego zdarzenia zmiany. Ten identyfikator służy do zapewnienia, że jeśli komunikacja z usługą nie powiedzie się w trakcie księgowania, ponowne przesłanie zdarzenia nie spowoduje, że zdarzenie to jest zliczane dwukrotnie w systemie. |
| `organizationId` | Identyfikator organizacji połączonej ze zdarzeniem. Ta opcja jest mapowana na dane organizacji Supply Chain Management lub identyfikatory obszaru danych. |
| `productId` | Identyfikator zlecenia produkcyjnego. |
| `quantity` | Ilość, o którą należy zmienić dostępne zapasy. Jeśli na przykład do półki dodano 10 nowych bajgli, ta wartość byłaby równa 10. Jeśli 3 bajgle zostały usunięte z półki lub sprzedane, ta wartość wynosi-3. |
| `dimensionDataSource` | Źródło danych wymiarów używanych w zdarzeniu zmiany księgowania i kwerendzie. W przypadku określenia źródła danych można wykorzystać niestandardowe wymiary z określonego źródła danych. W przypadku konfiguracji wymiarów widoczność zapasów może mapować niestandardowe wymiary do ogólnych wymiarów domyślnych. Jeśli `dimensionDataSource` nie określiło wartości, w kwerendach można stosować tylko ogólne wymiary domyślne.   |
| `dimensions` | Dynamiczny zbiór par klucz-wartość. Zostaną one zmapowane na niektóre wymiary w module Supply Chain Management, ale można również dodać niestandardowe wymiary (np *źródło*), które mogą oznaczać, że zdarzenie pochodzi z Supply Chain Management lub z systemu zewnętrznego. |

### <a name="querying-current-on-hand"></a>Badanie bieżących dostępnych zapasów

Punkt końcowy badania bieżących dostępnych zapasów będzie miał podobny adres URL:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Zostanie zbadany za pomocą metody HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Bieżąca kwerenda dostępnych zapasów — przykład 1

W tym przykładzie przedstawiono scenariusz, w którym została zakończona konfiguracja wymiaru w programie Power Apps.

Aby skonfigurować mapowanie wymiaru w programie, należy skorzystać z następującej kwerendy Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Teraz można określić `dimensionDataSource` i zastosować w kwerendach niestandardowe wymiary. System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe. Istnieje możliwość określenia wartości `DimensionDataSource` w polu `filters` i określenia wymiarów niestandardowych w polach `filters` i `groupByValues`. System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Bieżąca kwerenda dostępnych zapasów — przykład 2

W tym przykładzie przedstawiono scenariusz, w którym nie skonfigurowano żadnych mapowań konfiguracji wymiarów w systemie Power Apps, więc Księgowanie powinno również mieć wymiary podstawowe. Wszystkie wymiary muszą być wymiarami podstawowymi, jeśli pole `dimensionDataSource` ma wartość null w `filters`, jest puste lub zawiera białe znaki.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Przykładowy wynik zwrotu

Kwerendy przedstawione w poprzednich przykładach mogą zwracać wynik podobny do tego.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Należy zwrócić uwagę, że pola ilości są ustrukturyzowane i w postaci słownika miar i skojarzonych z nimi wartości.
