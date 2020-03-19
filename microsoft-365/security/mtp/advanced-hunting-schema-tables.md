---
title: Gegevenstabellen in het geavanceerde jachtschema van Microsoft Threat Protection
description: Meer informatie over de tabellen in het geavanceerde jachtschema om inzicht te krijgen in de gegevens waarop u zoekopdrachten voor bedreigingsjacht uitvoeren
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, schemareferentie, kusto, tabel, gegevens
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bb3eae9fff658ee1cbb7f80fa3ff15f2335a9a3a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809533"
---
# <a name="understand-the-advanced-hunting-schema"></a>Begrijp het geavanceerde jachtschema

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



Het [geavanceerde jachtschema](advanced-hunting-overview.md) bestaat uit meerdere tabellen die informatie over gebeurtenissen of informatie over machines en entiteiten bevatten. Als u query's wilt maken die meerdere tabellen omvatten, moet u de tabellen en kolommen in het geavanceerde jachtschema begrijpen.

## <a name="schema-tables"></a>Schematabellen

In de volgende verwijzing worden alle tabellen in het schema weergegeven. Elke tabelnaam wordt gekoppeld aan een pagina met een beschrijving van de kolomnamen voor die tabel. Tabel- en kolomnamen worden ook in het beveiligingscentrum vermeld als onderdeel van de schemaweergave op het geavanceerde jachtscherm.

| Tabelnaam | Beschrijving |
|------------|-------------|
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Machine-informatie, inclusief OS-informatie |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netwerkeigenschappen van machines, waaronder adapters, IP- en MAC-adressen, evenals verbonden netwerken en domeinen |
| **[DeviceProcessEvents DeviceProcess](advanced-hunting-deviceprocessevents-table.md)** | Procescreatie en gerelateerde gebeurtenissen |
| **[DeviceNetworkEvents DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netwerkverbinding en gerelateerde gebeurtenissen |
| **[DeviceFileEvents DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Bestandscreatie, wijziging en andere bestandssysteemgebeurtenissen |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Aanmaken en wijzigen van registervermeldingen |
| **[DeviceLogonEvents DeviceLogonEvents DeviceLogonEvents DeviceLog](advanced-hunting-devicelogonevents-table.md)** | Aanmeldingen en andere verificatiegebeurtenissen |
| **[DeviceImageLoadEvents DeviceImageLoadEvents DeviceImageLoadEvents DeviceImage](advanced-hunting-deviceimageloadevents-table.md)** | DLL-laadgebeurtenissen |
| **[DeviceEvents DeviceEvents](advanced-hunting-deviceevents-table.md)** | Meerdere gebeurtenistypen, waaronder gebeurtenissen die worden geactiveerd door beveiligingsbesturingselementen zoals Windows Defender Antivirus en exploitprotection |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | Certificaatgegevens van ondertekende bestanden verkregen uit certificaatverificatiegebeurtenissen op eindpunten |
| **[E-mailgebeurtenissen](advanced-hunting-emailevents-table.md)** | Office 365-e-mailgebeurtenissen, waaronder e-mailbezorging en blokkeringsgebeurtenissen |
| **[E-mailbijlageInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informatie over bestanden die zijn gekoppeld aan Office 365-e-mails |
| **[E-mailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informatie over URL's in E-mails in Office 365 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventarisatie van software op apparaten en eventuele bekende kwetsbaarheden in deze softwareproducten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Kennisbank van openbaar gemaakte kwetsbaarheden, waaronder de vraag of exploitcode openbaar beschikbaar is |
| **[DeviceTvmSecureConfigurationAssessment DeviceTvmSecureConfigurationAssessment DeviceTvmSecureConfigurationAssessment DeviceTv](advanced-hunting-tvm-configassessment-table.md)** | Beoordelingsgebeurtenissen voor & kwetsbaarheidsbeheer, die de status van verschillende beveiligingsconfiguraties op apparaten aangeven |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Kennisbank van verschillende beveiligingsconfiguraties die worden gebruikt door Threat & Vulnerability Management om apparaten te beoordelen; omvat mappings naar verschillende standaarden en benchmarks  |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
