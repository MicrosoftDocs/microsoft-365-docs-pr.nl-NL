---
title: Geavanceerde verwijzing naar het schema voor de jacht
description: Meer informatie over de tabellen in het geavanceerde schema voor het zoeken naar informatie over de gegevens waarin u query's voor het zoeken naar bedreigingen kunt uitvoeren.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: ce87b6e9e462ba5bd1bab1542c41ac72092dabd4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500593"
---
# <a name="understand-the-advanced-hunting-schema"></a>Het geavanceerde schema voor de jacht begrijpen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Het [geavanceerde schema](advanced-hunting-overview.md) bestaat uit meerdere tabellen die gebeurtenisgegevens of informatie over apparaten en andere entiteiten bevatten. Als u query's wilt maken die meerdere tabellen bespannen, moet u de tabellen en kolommen in het geavanceerde schema voor de jacht begrijpen.

## <a name="get-schema-information-in-the-security-center"></a>Schemagegevens verkrijgen in het beveiligingscentrum
Gebruik de ingebouwde schemaverwijzing tijdens het maken van query's om snel de volgende informatie over elke tabel in het schema te krijgen:

- **Beschrijving van tabellen:** het type gegevens in de tabel en de bron van die gegevens.
- **Kolommen:** alle kolommen in de tabel.
- **Actietypen:** mogelijke waarden in de `ActionType` kolom die de gebeurtenistypen vertegenwoordigen die door de tabel worden ondersteund. Dit is alleen beschikbaar voor tabellen die gebeurtenisgegevens bevatten.
- **Voorbeeldquery:** voorbeeldquery's met de manier waarop de tabel kan worden gebruikt.

### <a name="access-the-schema-reference"></a>De schemaverwijzing openen
Als u snel toegang wilt tot de schemaverwijzing, selecteert u de actie Verwijzing **weergeven** naast de tabelnaam in de schemaweergave. U kunt ook **Schemaverwijzing selecteren om** naar een tabel te zoeken.

![Afbeelding waarin wordt getoond hoe u toegang hebt tot schemaverwijzing in de portal](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>De schematabellen leren

In de volgende verwijzing vindt u alle tabellen in het geavanceerde schema voor de jacht. Elke tabelnaam wordt koppelingen naar een pagina met de kolomnamen voor die tabel.

Tabel- en kolomnamen worden ook weergegeven in het Microsoft Defender-beveiligingscentrum, in de schemaweergave op het geavanceerde zoekscherm.

| Tabelnaam | Omschrijving |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Waarschuwingen in het Microsoft Defender-beveiligingscentrum |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Apparaatgegevens, inclusief OS-informatie |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Netwerkeigenschappen van apparaten, waaronder adapters, IP- en MAC-adressen, evenals verbonden netwerken en domeinen |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Procescreatie en gerelateerde gebeurtenissen |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Netwerkverbinding en gerelateerde gebeurtenissen |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Bestandscreatie, wijziging en andere bestandssysteemgebeurtenissen |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Registergegevens maken en wijzigen |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Aanmeldingen en andere verificatiegebeurtenissen |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL-laadgebeurtenissen |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Meerdere gebeurtenistypen, waaronder gebeurtenissen die worden geactiveerd door beveiligingsbesturingselementen, zoals Microsoft Defender Antivirus en bescherming tegen misbruik |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | Certificaatgegevens van ondertekende bestanden die zijn verkregen uit gebeurtenissen met certificaatverificatie op eindpunten |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventaris van software die op apparaten is geïnstalleerd, inclusief de versiegegevens en de status van het einde van de ondersteuning |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Softwareproblemen die zijn gevonden op apparaten en de lijst met beschikbare beveiligingsupdates die elk beveiligingsprobleem verhelpen |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Gebeurtenissen & beveiligingsprobleembeheer, waarmee de status van verschillende beveiligingsconfiguraties op apparaten wordt aangegeven |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; bevat toewijzingen aan verschillende standaarden en benchmarks |


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
- [Geavanceerde wijzigingen in schema's voor jagende gegevens](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
