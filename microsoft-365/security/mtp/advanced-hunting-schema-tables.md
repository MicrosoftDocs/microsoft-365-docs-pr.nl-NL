---
title: Gegevenstabellen in het geavanceerde schema van Microsoft 365 Defender voor zoeken
description: Lees meer over de tabellen in het geavanceerde schema voor het zoeken naar gegevens die u kunt uitvoeren op bedreigingsquery's
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925040"
---
# <a name="understand-the-advanced-hunting-schema"></a>Meer te weten komen over het geavanceerde schema voor het zoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde schema voor](advanced-hunting-overview.md) zoeken bestaat uit meerdere tabellen met informatie over gebeurtenissen of informatie over apparaten, waarschuwingen, identiteiten en andere entiteitstypen. Als u effectief query's wilt maken die meerdere tabellen bespannen, moet u de tabellen en kolommen in het geavanceerde schema voor het zoeken begrijpen.

## <a name="get-schema-information-in-the-security-center"></a>Schemagegevens op halen in het beveiligingscentrum
Gebruik tijdens het maken van query's de ingebouwde schemaverwijzing om snel de volgende informatie over elke tabel in het schema op te halen:

- **Beschrijving van** tabellen: het type gegevens in de tabel en de bron van die gegevens.
- **Kolommen:** alle kolommen in de tabel.
- **Actietypen**: mogelijke waarden in de `ActionType` kolom die de gebeurtenistypen vertegenwoordigen die door de tabel worden ondersteund. Deze informatie wordt alleen verstrekt voor tabellen die gebeurtenisgegevens bevatten.
- **Voorbeeldquery:** voorbeeldquery's die laten zien hoe de tabel kan worden gebruikt.

### <a name="access-the-schema-reference"></a>Toegang tot de schemaverwijzing
Als u snel toegang wilt tot de schemaverwijzing, selecteert u de actie Verwijzing **weergeven** naast de tabelnaam in de schemaweergave. U kunt ook Schemaverwijzing **selecteren om** naar een tabel te zoeken.   

![Afbeelding van toegang tot schemaverwijzing in de portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Informatie over de schematabellen
De volgende verwijzing bevat alle tabellen in het schema. Elke tabelnaam is een koppeling naar een pagina met een beschrijving van de kolomnamen voor die tabel. Tabel- en kolomnamen worden ook weergegeven in het beveiligingscentrum als onderdeel van de schemaweergave op het geavanceerde zoekscherm.

| Tabelnaam | Beschrijving |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Waarschuwingen van Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit, inclusief ernstgegevens en bedreigingscategorisatie  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Activiteiten in verband met bestanden in cloud-apps en -services |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Gebeurtenissen die betrekking hebben op accounts en objecten in Office 365 en andere cloud-apps en -services |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Meerdere gebeurtenistypen, waaronder gebeurtenissen die worden geactiveerd door beveiligingsbesturingselementen, zoals Windows Defender Antivirus en exploit protection |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Certificaatgegevens van ondertekende bestanden die zijn verkregen uit certificaatverificatiegebeurtenissen op eindpunten |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Gebeurtenissen in het bestandssysteem voor het maken, wijzigen en andere bestandssysteemgebeurtenissen |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-laadgebeurtenissen |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Computergegevens, inclusief informatie over het besturingssysteem |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Aanmeldingen en andere verificatiegebeurtenissen op apparaten |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netwerkverbinding en gerelateerde gebeurtenissen |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netwerkeigenschappen van apparaten, waaronder fysieke adapters, IP- en MAC-adressen, evenals verbonden netwerken en domeinen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Proces maken en gerelateerde gebeurtenissen |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Registergegevens maken en wijzigen |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Bedreiging & beveiligingsrisico's, die de status van verschillende beveiligingsconfiguraties op apparaten aangeven |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Knowledge Base van verschillende beveiligingsconfiguraties die door Bedreigingsbeveiliging & beveiligingsprobleembeheer worden gebruikt om apparaten te beoordelen; bevat toewijzingen aan verschillende standaarden en benchmarks  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventaris van software op apparaten en bekende beveiligingsproblemen in deze softwareproducten |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Knowledge Base van openbaar openbaar bekendgemaakte beveiligingslekken, waaronder of misbruik van code openbaar beschikbaar is |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informatie over bestanden die zijn bijgevoegd bij e-mailberichten |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | E-mailgebeurtenissen van Microsoft 365, inclusief bezorging van e-mail en blokkeren van gebeurtenissen |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Beveiligingsgebeurtenissen na bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informatie over URL's in e-mailberichten |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Gebeurtenissen waarbij een on-premises domeincontroller Active Directory (AD) wordt uitgevoerd. Deze tabel beslaat een bereik van identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Verificatiegebeurtenissen in Active Directory en Online Services van Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
