---
title: Rozszerzanie jednostek danych dostępnych zapasów
description: W tym temacie przedstawiono przykład, który pokazuje, jak dodawać pola rozszerzone do widoków INVENTORSITEONHANDENTITY i INVENTWAREHOUSEONHANDENTITY, tak aby możliwości jednostek danych znajdujących się w magazynie mogły współpracować z rozszerzeniami.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e3bf3a7d48b0aa3e48845882be0ee86da17ed040
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435294"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Rozszerzanie jednostek danych dostępnych zapasów

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management oferuje funkcje [rozszerzalności](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md), które umożliwiają [dDodawanie pól do tabel za pośrednictwem rozszerzenia](../../fin-ops-core/dev-itpro/extensibility/add-field-extension). W tym temacie przedstawiono przykład, który pokazuje, jak dodawać pola rozszerzone do widoków `INVENTORSITEONHANDENTITY` i `INVENTWAREHOUSEONHANDENTITY`, tak aby możliwości jednostek danych znajdujących się w magazynie mogły współpracować z rozszerzeniami. Aby uzyskać szczegółowe informacje o jednostkach danych, zapoznaj się z [omówieniem zarządzania danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> Poniżej znajduje się lista niektórych jednostek danych dostępnych zapasów:
>
> - Dostępne zapasy według oddziału
> - Dostępne zapasy według oddziału (wersja 2)
> - Dostępne zapasy według magazynu
> - Dostępne zapasy według magazynu wersja 2

Po dodaniu pól do tabel, które są używane przez widok `inventSiteOnHandView`, należy zsynchronizować aparat, aby rozszerzenia były rozpoznawane poprawnie.

1. Rozszerz widok `InventSiteOnHandView`, dodając pole rozszerzenie.
1. Rozszerz widok `InventSiteOnHandAggregatedView` z polami rozszerzenia.
1. Rozszerz klasę viewBuilder `InventSiteOnHandAggregatedViewBuilder`, modyfikując metodę `getExtensionFields()`. W ten sposób można mapować stare pola widoku na nowe pola widoku, gdy jest uruchamiana synchronizacja viewBuilder.

Na przykład dodałeś następujące cztery pola do tabeli `InventTable` poprzez rozszerzenie:

- Pole niestandardowe 1
- Pole niestandardowe 2
- Pole niestandardowe 3
- Pole niestandardowe 4

W przypadku należy zmodyfikować metodę `getExtensionFields()` w następujący sposób:

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

Po wykonaniu tych kroków można rozszerzyć dostępne zapasy zapasów według oddziału i dostępnych zapasów przez jednostki danych magazynu, dodając nowe pola. W ten sposób należy upewnić się, że rozszerzone pola są rozpoznawane i uwzględniane podczas migracji danych, w których są używane te jednostki danych.
