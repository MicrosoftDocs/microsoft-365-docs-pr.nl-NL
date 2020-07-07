---
title: Gegevenstabellen in het geavanceerde jachtschema van Microsoft Threat Protection
description: Meer informatie over de tabellen in het geavanceerde jachtschema om inzicht te krijgen in de gegevens waarop u bedreigingenjachtquery's uitvoeren
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, gegevens
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
ms.openlocfilehash: 0cb275584acfc2ea0d2a2969694ee189f48a875d
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046041"
---
# <a name="understand-the-advanced-hunting-schema"></a>Begrijp het geavanceerde jachtschema

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde jachtschema](advanced-hunting-overview.md) bestaat uit meerdere tabellen die informatie over gebeurtenissen of informatie over apparaten, waarschuwingen, identiteiten en andere entiteitstypen bevatten. Als u query's wilt maken die meerdere tabellen omvatten, moet u de tabellen en de kolommen in het geavanceerde jachtschema begrijpen.

## <a name="get-schema-information-in-the-security-center"></a>Ontvang schema-informatie in het beveiligingscentrum
Gebruik tijdens het maken van query's de ingebouwde schemaverwijzing om snel de volgende informatie over elke tabel in het schema op te halen:

- **Beschrijving** van tabellen — type gegevens in de tabel en de bron van die gegevens.
- **Kolommen** : alle kolommen in de tabel.
- **Actietypen** : mogelijke waarden in de `ActionType` kolom die de gebeurtenistypen weergeeft die door de tabel worden ondersteund. Dit wordt alleen verstrekt voor tabellen die gebeurtenis-informatie bevatten.
- **Voorbeeldquery** : voorbeeldquery's met de manier waarop de tabel kan worden gebruikt.

### <a name="access-the-schema-reference"></a>Toegang tot de schemaverwijzing
Als u snel toegang wilt krijgen tot de schemaverwijzing, selecteert u de **referentieactie Weergeven** naast de tabelnaam in de schemaweergave. U ook **schemaverwijzing** selecteren om naar een tabel te zoeken.   

![Afbeelding die laat zien hoe u toegang krijgt tot in-portal-schemaverwijzing ](../../media/mtp-ah/ah-reference.png) 

## <a name="schema-tables"></a>Schematabellen
In de volgende referentie worden alle tabellen in het schema weergegeven. Elke tabelnaam verwijst naar een pagina met de kolomnamen voor die tabel. Tabel- en kolomnamen worden ook vermeld in het beveiligingscentrum als onderdeel van de schemaweergave op het geavanceerde jachtscherm.

| Tabelnaam | Beschrijving |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP, inclusief ernstinformatie en bedreigingscategorisering  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Bestandsgerelateerde activiteiten in cloud-apps en -services |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Meerdere gebeurtenistypen, waaronder gebeurtenissen die zijn geactiveerd door beveiligingsbesturingselementen zoals Windows Defender Antivirus en exploitbeveiliging |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certificaatinformatie van ondertekende bestanden die zijn verkregen uit certificaatverificatiegebeurtenissen op eindpunten |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Bestandsgebeurtenissen, wijziging en andere bestandssysteemgebeurtenissen |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-laadgebeurtenissen |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Machine-informatie, inclusief OS-informatie |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Aanmeldingen en andere verificatiegebeurtenissen op apparaten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netwerkverbinding en gerelateerde gebeurtenissen |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netwerkeigenschappen van machines, waaronder adapters, IP- en MAC-adressen, evenals verbonden netwerken en domeinen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Procescreatie en gerelateerde gebeurtenissen |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Aanmaken en wijzigen van registervermeldingen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Threat & Vulnerability Management assessment events, met vermelding van de status van verschillende beveiligingsconfiguraties op apparaten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Kennisbasis van verschillende beveiligingsconfiguraties die door Threat & Vulnerability Management worden gebruikt om apparaten te beoordelen; omvat mappings aan verschillende standaarden en benchmarks  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventaris van software op apparaten en bekende kwetsbaarheden in deze softwareproducten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Kennisbank van openbaar gemaakte kwetsbaarheden, inclusief de vraag of exploitcode openbaar beschikbaar is |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informatie over bestanden die aan e-mails zijn gekoppeld |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365-e-mailgebeurtenissen, waaronder e-mailbezorging en blokkeringsgebeurtenissen |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Beveiligingsgebeurtenissen die plaatsvinden na levering, nadat Microsoft 365 de e-mails naar het postvak van de ontvanger heeft bezorgd |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informatie over URL's in e-mails |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Verificatiegebeurtenissen op onlineservices van Active Directory en Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Queryactiviteiten uitgevoerd met Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
