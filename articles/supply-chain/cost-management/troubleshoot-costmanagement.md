---
title: Rozwiązywanie problemów z zarządzaniem kosztami
description: W tym temacie opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z zarządzaniem kosztami.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e84bb167395c06295b0e8ef8b9fd98aa4bc0cc14
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4435668"
---
# <a name="troubleshoot-cost-management"></a>Rozwiązywanie problemów z zarządzaniem kosztami

W tym temacie opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z zarządzaniem kosztami.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Przerwy funkcjonalne między raportami wartości zapasów/wiekowania i ich wersji magazynowej

Funkcje [Magazyn raportów wiekowania zapasów](inventory-aging-report-storage.md) i [Raport magazynu wartości zapasów](inventory-value-report-storage.md) umożliwiają Supply Chain Management wyświetlanie dużych ilości transakcji magazynowych. W każdym przypadku wyniki raportów są zapisywane w celu przeglądania i eksportowania, w przeciwieństwie do wersji tych raportów bez magazynowania. Jednak niektóre funkcje, które istnieją w wersjach tych raportów bez magazynu, nie istnieją w wersjach magazynu. Poniższe podsekcje podsumowują różnice i udostępniają rozwiązania.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Raporty magazynowania nie zawierają sum częściowych, nawet jeśli są włączone w układzie raportu

Sumy częściowe mogą powodować problemy podczas eksportowania wyniku, zwłaszcza jeśli użytkownicy zmienią sekwencję rekordów.

Aby sprawdzić sumy częściowe, można wyeksportować wyniki do Microsoft Excel. Alternatywnie, jeśli chcesz sprawdzić sumy częściowe w ramach Supply Chain Management, użyj funkcji [Zarządzanie funkcjamit](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby włączyć funkcje *Kontrolka nowej siatki* i *(Wersja zapoznawcza) Grupowania w siatkach*, które zapewniają znacznie bardziej elastyczny sposób wyświetlania sum częściowych dla dowolnej grupy według kolumny. Aby uzyskać dodatkowe informacje, zobacz [Zdolności siatki](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Raport magazynowania wartości zapasów nie obsługuje informacji o koncie księgowym

Bilans próbny można uruchomić, aby uzyskać saldo konta zapasów i porównać je z raportem **Magazynu wartości zapasów**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Ostrzeżenia lub błędy są wyświetlane podczas zmiany stanu okresu księgi bez zamknięcia magazynu

Firma Microsoft wprowadziła następujące procesy weryfikacji, aby zapobiec problemom spowodowanym przez nieprawidłowy proces zakończenia okresu dotyczący kalkulacji kosztów. W przypadku napotkania dowolnego z poniższych komunikatów o błędach zapoznaj się z [4561987 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3), aby uzyskać więcej informacji dotyczących sposobu rozwiązywania tych problemów.

- Zamierzasz wykonać ponowne obliczenie z datą %1 (10-02-2019). Ostatnie zarejestrowane ponowne obliczenie zostało wykonane w poprzednim okresie z datą %2 (20-01-2019). Nie zarejestrowano wykonania zamknięcia zapasów z datą %3 (31-01-2019) końca okresu dopasowania. Należy pamiętać o wykonaniu zamknięcia zapasów w dacie %3 (31-01-2019), odpowiadającej zakończeniu okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

- Zamierzasz zmienić stan okresu księgi %1 na %2. Nie zarejestrowano wykonania zamknięcia zapasów z datą %3, odpowiadającą zakończeniu okresu. Przed zmianą statusu należy wykonać zamknięcie zapasów na %3 odpowiadające końcowi okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji. Zgłoszone przez firmę %4. Obecnie ta akcja ma wartość informacyjną, ale w przyszłości jej wykonanie będzie wymagane.

- Struktura konta %1 została zmieniona. Co najmniej jedno konto główne %2 już nie istnieje. Te konta główne są wymagane przez %3 z datą %4. Dodaj te konta główne do struktury konta %1, aby móc wznowić zadanie %3. Obecnie ta akcja ma wartość informacyjną, ale w przyszłości jej wykonanie będzie wymagane.

- Zamierzasz wykonać zamknięcie zapasów z datą %1 (31-01-2019). Nie zarejestrowano wykonania obliczania wyceny wstecznej z datą %2 (31-01-2019) pasującą do zakończenia okresu. Należy pamiętać o wykonaniu obliczania wyceny wstecznej z datą %3 (31-01-2019) pasującą do zakończenia okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

- Zamierzasz wykonać obliczenie wycent wstecznej z datą %1 (28-02-2019). Ostatnie zarejestrowane obliczenie wyceny wstecznej zostało wykonane w poprzednim okresie z datą %2 (31-01-2019). Nie zarejestrowano wykonania zamknięcia zapasów z datą %3 (31-01-2019) końca okresu dopasowania.
Należy pamiętać o wykonaniu zamknięcia zapasów w dacie %3 (31-01-2019), odpowiadającej zakończeniu okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do wykonania zamknięcia zapasów.

## <a name="inventory-aging-report-discrepancies"></a>Rozbieżności w raportach wiekowania zapasów

**Raport wiekowania zapasów** zawiera różne wartości wyświetlane w różnych wymiarach przechowywania (np. oddział lub magazyn). Aby uzyskać więcej informacji o logice raportowania, zobacz [Przykłady i logika raportu wiekowania zapasów](inventory-aging-report.md).
