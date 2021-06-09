---
title: Gegevenstabellen in het geavanceerde Microsoft 365 Defender
description: Meer informatie over de tabellen in het geavanceerde schema voor het zoeken naar informatie over de gegevens waarin u query's voor het zoeken naar bedreigingen kunt uitvoeren
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3c8c65d012467317bf8335f47c3f686a5d7255d1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470578"
---
# <a name="understand-the-advanced-hunting-schema"></a>Het geavanceerde schema voor de jacht begrijpen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde schema](advanced-hunting-overview.md) bestaat uit meerdere tabellen met gebeurtenisgegevens of informatie over apparaten, waarschuwingen, identiteiten en andere entiteitstypen. Als u query's wilt maken die meerdere tabellen bespannen, moet u de tabellen en kolommen in het geavanceerde schema voor de jacht begrijpen.

## <a name="get-schema-information-in-the-security-center"></a>Schemagegevens verkrijgen in het beveiligingscentrum
Gebruik de ingebouwde schemaverwijzing tijdens het maken van query's om snel de volgende informatie over elke tabel in het schema te krijgen:

- **Beschrijving van tabellen:** het type gegevens in de tabel en de bron van die gegevens.
- **Kolommen:** alle kolommen in de tabel.
- **Actietypen:** mogelijke waarden in de `ActionType` kolom die de gebeurtenistypen vertegenwoordigen die door de tabel worden ondersteund. Deze informatie wordt alleen verstrekt voor tabellen die gebeurtenisgegevens bevatten.
- **Voorbeeldquery:** voorbeeldquery's met de manier waarop de tabel kan worden gebruikt.

### <a name="access-the-schema-reference"></a>De schemaverwijzing openen
Als u snel toegang wilt tot de schemaverwijzing, selecteert u de actie Verwijzing **weergeven** naast de tabelnaam in de schemaweergave. U kunt ook **Schemaverwijzing selecteren om** naar een tabel te zoeken.   

![Afbeelding waarin wordt getoond hoe u toegang hebt tot schemaverwijzing in de portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>De schematabellen leren
In de volgende verwijzing worden alle tabellen in het schema weergegeven. Elke tabelnaam wordt koppelingen naar een pagina met de kolomnamen voor die tabel. Tabel- en kolomnamen worden ook weergegeven in het beveiligingscentrum als onderdeel van de schemaweergave op het geavanceerde zoekscherm.

| Tabelnaam | Beschrijving |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit, inclusief ernstsinformatie en bedreigingscategorisatie  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Gebeurtenissen met accounts en objecten in Office 365 en andere cloud-apps en -services |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Meerdere gebeurtenistypen, waaronder gebeurtenissen die worden geactiveerd door beveiligingsbesturingselementen, zoals Windows Defender Antivirus en bescherming tegen misbruik |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certificaatgegevens van ondertekende bestanden die zijn verkregen uit gebeurtenissen met certificaatverificatie op eindpunten |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Bestandscreatie, wijziging en andere bestandssysteemgebeurtenissen |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-laadgebeurtenissen |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Computergegevens, inclusief OS-informatie |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Aanmeldingen en andere verificatiegebeurtenissen op apparaten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netwerkverbinding en gerelateerde gebeurtenissen |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netwerkeigenschappen van apparaten, waaronder fysieke adapters, IP- en MAC-adressen, evenals verbonden netwerken en domeinen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Procescreatie en gerelateerde gebeurtenissen |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Registergegevens maken en wijzigen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Gebeurtenissen & beveiligingsprobleembeheer, waarmee de status van verschillende beveiligingsconfiguraties op apparaten wordt aangegeven |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; bevat toewijzingen aan verschillende standaarden en benchmarks  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventaris van software die op apparaten is geïnstalleerd, inclusief de versiegegevens en de status van het einde van de ondersteuning |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Softwareproblemen die zijn gevonden op apparaten en de lijst met beschikbare beveiligingsupdates die elk beveiligingsprobleem verhelpen |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informatie over bestanden die zijn gekoppeld aan e-mailberichten |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 e-mailgebeurtenissen, waaronder e-mailbezorging en het blokkeren van gebeurtenissen |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Beveiligingsgebeurtenissen die zich voordoen na de bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informatie over URL's in e-mailberichten |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Gebeurtenissen met een on-premises domeincontroller met Active Directory (AD). Deze tabel bestrijkt een reeks identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Verificatiegebeurtenissen in Active Directory- en Microsoft-onlineservices |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
