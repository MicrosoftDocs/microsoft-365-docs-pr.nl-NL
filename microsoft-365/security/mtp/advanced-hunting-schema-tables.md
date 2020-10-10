---
title: Gegevenstabellen in het geavanceerde jacht schema Microsoft Threat Protection
description: Meer informatie over de tabellen in het geavanceerde jacht-schema om inzicht te krijgen in de gegevens waarop u de zoekopdrachten voor de bedreiging kunt uitvoeren
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, schema naslag, kusto, tabel, Data
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 916f86cf9536101bdbb2650bf7381682203d343f
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412428"
---
# <a name="understand-the-advanced-hunting-schema"></a>Meer informatie over het schema voor geavanceerde jacht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het schema voor [geavanceerde jacht](advanced-hunting-overview.md) bestaat uit meerdere tabellen met informatie over gebeurtenissen of informatie over apparaten, waarschuwingen, identiteiten en andere entiteitstypen. U moet inzicht krijgen in de tabellen en de kolommen in het geavanceerde jacht schema, zodat u query's effectiever kunt opbouwen in meerdere tabellen.

## <a name="get-schema-information-in-the-security-center"></a>Schemainformatie in het Beveiligingscentrum weergeven
Gebruik tijdens het maken van query's de ingebouwde schema verwijzing om snel de volgende informatie weer te geven over de tabellen in het schema:

- **Beschrijving van tabellen** : type gegevens in de tabel en de gegevensbron.
- **Kolommen** : alle kolommen in de tabel.
- **Actietypen** : mogelijke waarden in de `ActionType` kolom die de gebeurtenistypen vertegenwoordigen die door de tabel worden ondersteund. Dit wordt alleen verleend voor tabellen met informatie over gebeurtenissen.
- **Voorbeeldquery** : voorbeeldquery's die de werking van de tabel kunnen benutten.

### <a name="access-the-schema-reference"></a>Toegang tot de schema verwijzing
Om snel toegang te krijgen tot de schema verwijzing, selecteert u de **verwijzingsactie weergeven** naast de tabelnaam in de schema weergave. U kunt ook **schema verwijzingen** selecteren om een tabel te zoeken.   

![Afbeelding van naslaginformatie over het gebruik van naslaginformatie over Portal in de portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Meer informatie over de schema tabellen
In de volgende naslag worden alle tabellen in het schema weergegeven. Met elke tabelnaam wordt een koppeling naar een pagina gemaakt met een beschrijving van de kolomnamen voor de tabel. De namen van tabellen en kolommen worden ook weergegeven in het Beveiligingscentrum, als onderdeel van de schema weergave in het scherm Geavanceerde jacht.

| Tabelnaam | Beschrijving |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Bestanden, IP-adressen, Url's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Waarschuwingen uit Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud app Security en Azure ATP, waaronder informatie over de ernst en de bedreiging van de bedreiging  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Activiteiten met betrekking tot bestanden in Cloud-apps en-services |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Meerdere gebeurtenistypen, waaronder gebeurtenissen die zijn geactiveerd door beveiligings besturingselementen zoals Windows Defender antivirus en exploit Protection |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certificaatgegevens met ondertekende bestanden die zijn opgehaald uit certificaatverificatie gebeurtenissen op eindpunten |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Bestanden maken, wijzigen en andere bestandssystemen gebeurtenissen |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Laad gebeurtenissen van DLL-bestand |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Computerinformatie, waaronder besturingssysteemgegevens |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Registreren en andere verificatiegebeurtenissen op apparaten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netwerkverbinding en gerelateerde gebeurtenissen |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netwerkeigenschappen van machines, waaronder adapters, IP-en MAC-adressen, en verbonden netwerken en domeinen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Proces maken en gerelateerde gebeurtenissen |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Registervermeldingen maken en wijzigen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | & bedreiging van beveiligingsgebeurtenissen in het beveiligingslek met betrekking tot het beheren van beveiligingsfuncties, met de status van diverse beveiligingsconfiguraties op apparaten |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Knowledge Base van diverse beveiligingsconfiguraties die worden gebruikt door bedreigingen van & beveiligingslek voor het beoordelen van apparatuur; inclusief toewijzingen aan diverse standaarden en benchenen  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventarisatie van software op apparaten en bekende beveiligingsproblemen in deze softwareproducten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | De Knowledge Base van bekendgemaakte zwakke plekken, waaronder de exploitatiecode openbaar beschikbaar |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informatie over bestanden die zijn gekoppeld aan e-mailberichten |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365-e-mail gebeurtenissen, waaronder e-mail bezorging en blokkering van gebeurtenissen |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Beveiligingsgebeurtenissen die na na ontvangst plaatsvinden, nadat Microsoft 365 de e-mail heeft bezorgd in het postvak van de geadresseerde |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Info over Url's voor e-mailberichten |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Gebeurtenissen waarbij een on-premises domeincontroller met Active Directory (AD) wordt uitgevoerd. Deze tabel bevat een reeks identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Account gegevens van diverse bronnen, waaronder Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Verificatiegebeurtenissen in Active Directory en Microsoft Online Services |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Query activiteiten die worden uitgevoerd op Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
