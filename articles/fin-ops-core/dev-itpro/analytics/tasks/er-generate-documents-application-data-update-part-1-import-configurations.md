---
title: Importowanie konfiguracji w celu generowania dokumentów zawierających dane aplikacji
description: Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f919d953c3aa0c8d16366167a12e52d35f32cdf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684626"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>Importowanie konfiguracji w celu generowania dokumentów zawierających dane aplikacji

[!include [banner](../../includes/banner.md)]

Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego. W tej procedurze zaimportujesz wymaganą konfigurację ER, którą utworzono dla przykładowej firmy Litware, Inc., i będziesz jej używać do generowania dokumentów elektronicznych. Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy DEMF. Zanim rozpoczniesz, pobierz i zapisz pliki wymienione w temacie pomocy „Generowanie dokumentów elektronicznych i aktualizowanie danych aplikacji za pomocą narzędzia ER” (generate-electronic-documents-update-application-data/). Są to następujące pliki: Intrastat (model).xml, Intrastat (mapping).xml i Intrastat (format).xml.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego.  
    * Kroki opisane w tej procedurze pokazują, jak używać funkcji raportowania elektronicznego do wykonania aktualizacji danych aplikacji i jak generować raport Intrastat. Szczegóły procesu sprawozdawczego są archiwizowane w tabelach aplikacji. Obecnie po uaktywnieniu procesu raportowania Intrastat z formularza Intrastat archiwizacja odbywa się przy użyciu logiki zaprogramowanej w istniejącym kodzie źródłowym. W tej procedurze skonfigurujesz podobną, ale uproszczoną logikę danych aplikacji, używając tylko struktury ER. W kodzie źródłowym nie zostaną wprowadzone żadne zmiany.   

## <a name="import-er-configurations"></a>Importowanie konfiguracji ER
1. Kliknij opcję Konfiguracje raportowania.
2. Kliknij opcję Import/eksport.
3. Kliknij opcję Załaduj z pliku XML.
    * Zaimportuj nową konfigurację modelu raportowania elektronicznego zawierającą model danych, który jest przeznaczony do używania jako źródło danych do generowania raportu Intrastat. Później rozszerzysz tę definicję modelu danych, aby ją stosować do aktualizowania danych aplikacji w celu zarchiwizowania szczegółów procesu raportowania Intrastat.   
    * Kliknij przycisk Przeglądaj i wybierz plik Intrastat (model).xml.  
4. Kliknij przycisk OK.
5. W drzewie zaznacz element „Intrastat (model)”.
6. Kliknij przycisk Konstruktor.
7. W drzewie rozwiń węzeł „Dla dokumentu wychodzącego”.
8. W drzewie rozwiń węzeł „Dla dokumentu wychodzącego\Transakcje”.
    * Przejrzyj strukturę zaimportowanego modelu danych. Należy zauważyć, że pozycja główna „Dla dokumentu wychodzącego” jest zdefiniowana w celu określenia przepływu pobierania danych z aplikacji i jej używania jako źródła danych do generowania raportu Intrastat. Spis „Transakcje (lista rekordów)” jest używany do reprezentowania listy transakcji Intrastat, które należy zgłosić. Ponieważ będziesz archiwizować zaraportowane kody asortymentu, w tym przepływie danych jest wymagany unikatowy identyfikator pojedynczego kodu asortymentu „Identyfikator rekordu asortymentu (Int64)”.   
9. Zamknij stronę.
10. Kliknij opcję Import/eksport.
11. Kliknij opcję Załaduj z pliku XML.
    * Zaimportuj konfigurację mapowania ER określającą przepływ pobierania danych z aplikacji, a następnie ich stosowania do generowania raportu Intrastat. Później rozszerzysz tę definicję mapowania modelu w celu pobrania danych z raportu Intrastat i ich zastosowania do aktualizacji danych aplikacji w celu zarchiwizowania szczegółów procesu raportowania Intrastat.   
    * Kliknij przycisk Przeglądaj i wybierz plik Intrastat (mapping).xml.  
12. Kliknij przycisk OK.
13. W drzewie rozwiń węzeł „Intrastat (model)”.
14. W drzewie zaznacz element „Intrastat (model)\Intrastat (mapowanie)”.
15. Kliknij przycisk Konstruktor.
    * Należy zwrócić uwagę, że bieżące mapowania modelu zawiera wartość „Do modelu” w polu Kierunek. Oznacza to, że to mapowanie modelu zostało zaprojektowane do pobierania danych z aplikacji i przechowywania ich w modelu danych.  
16. Kliknij przycisk Konstruktor.
17. W drzewie rozwiń węzeł „Lista”.
18. W drzewie rozwiń węzeł „Transakcje = Lista”.
    * Przejrzyj strukturę mapowania modelu, która używa modelu danych wyfiltrowanego na podstawie pozycji głównej „Dla dokumentu wychodzącego”. Należy zauważyć, że dodane źródło danych „Lista” zapewnia dostęp do wymaganych danych aplikacji, czyli listy rekordów z tabeli Intrastat.  
19. Zamknij stronę.
20. Zamknij stronę.
21. Kliknij opcję Import/eksport.
22. Kliknij opcję Załaduj z pliku XML.
    * Zaimportuj konfigurację formatu modułu ER, która określa układ raportu Intrastat i proces wypełniania raportu danymi. Później rozszerzysz tę definicję formatu w celu umieszczenia danych z raportu Intrastat w modelu danych, a następnie ich zastosowania do aktualizacji danych aplikacji w celu zarchiwizowania szczegółów procesu raportowania Intrastat.   
    * Kliknij przycisk Przeglądaj i wybierz plik Intrastat (format).xml.  
23. Kliknij przycisk OK.
24. W drzewie zaznacz element „Intrastat (model)\Intrastat (format)”.
25. Kliknij przycisk Konstruktor.
26. Kliknij przycisk Rozwiń/zwiń.
27. W drzewie zaznacz element „Plik\Deklaracja”.
28. Kliknij kartę Mapowanie.
29. W drzewie zaznacz element „Plik”.
    * Przejrzyj strukturę formatu używaną do generowania raportu Intrastat. Należy zwrócić uwagę na to, że jest ona przeznaczona do generowania pliku XML przez wypełnianie danymi z modelu danych zależnego od pozycji głównej „Dla dokumentu wychodzącego”. Upewnij się, że nazwa wygenerowanego pliku jest zdefiniowana w formularzu okna dialogowego użytkownika (do tego jest używane źródło danych „fn”).   
30. Zamknij stronę.

