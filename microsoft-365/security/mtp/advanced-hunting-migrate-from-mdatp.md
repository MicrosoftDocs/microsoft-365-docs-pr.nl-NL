---
title: Geavanceerde jagers-query's migreren van Microsoft Defender voor eindpunt
description: Meer informatie over het aanpassen van uw Microsoft Defender voor eindpunt query's, zodat u deze kunt gebruiken in Microsoft 365 Defender
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Microsoft Defender ATP, mdatp, Search, query, telemetrie, aangepaste detectie, schema, kusto, Microsoft 365, toewijzen
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
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846854"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Geavanceerde jagers-query's migreren van Microsoft Defender voor eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

U kunt uw werkstromen voor Geavanceerd zoeken van Microsoft Defender voor het eindpunt verplaatsen naar een meer ervaring met een uitgebreidere set gegevens. In Microsoft 365 Defender krijgt u toegang tot gegevens vanuit andere beveiligingsoplossingen van Microsoft 365, waaronder:

- Microsoft Defender voor eindpunt
- Microsoft Defender voor Office 365
- Microsoft Cloud App Security
- Microsoft Defender voor identiteit

>[!NOTE]
>De meeste Microsoft Defender voor eindpunten van klanten kunnen [Microsoft 365 Defender gebruiken zonder extra licenties](prerequisites.md#licensing-requirements). Als u wilt beginnen met het overstappen van uw Advanced jacht-werkstromen vanuit Defender voor eindpunten, [schakelt u Microsoft 365 Defender in](mtp-enable.md).

U kunt overstappen zonder dat dit van invloed is op de bestaande Defender voor eindpunten. Opgeslagen query's blijven behouden en aangepaste detectieregels blijven doorgaan met het uitvoeren en genereren van waarschuwingen. Deze worden echter wel weergegeven in Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Schema tabellen in Microsoft 365 Defender
Het [Microsoft 365 Defender Advanced jacht-schema](advanced-hunting-schema-tables.md) biedt extra tabellen met gegevens van diverse beveiligingsoplossingen van microsoft 365. De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:

| Tabelnaam | Beschrijving |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Bestanden, IP-adressen, Url's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Waarschuwingen van Microsoft Defender for endpoints, Microsoft Defender for Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity, waaronder informatie over de ernst en bedreigings Categorieën  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Activiteiten met betrekking tot bestanden in Cloud-apps en-services |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informatie over bestanden die zijn gekoppeld aan e-mailberichten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365-e-mail gebeurtenissen, waaronder e-mail bezorging en blokkering van gebeurtenissen |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Beveiligingsgebeurtenissen die na na ontvangst plaatsvinden, nadat Microsoft 365 de e-mail heeft bezorgd in het postvak van de geadresseerde |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Info over Url's voor e-mailberichten |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Gebeurtenissen waarbij een on-premises domeincontroller met Active Directory (AD) wordt uitgevoerd. Deze tabel behandelt een bereik van gebeurtenissen die betrekking hebben op de identiteit en de systeemgebeurtenissen op de domeincontroller. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Account gegevens van diverse bronnen, waaronder Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Verificatiegebeurtenissen in Active Directory en Microsoft Online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="map-devicealertevents-table"></a>Kaart DeviceAlertEvents tabel
`AlertInfo`Met de `AlertEvidence` tabellen en worden de tabellen `DeviceAlertEvents` in het Microsoft Defender voor eindpunt schema vervangen. Naast gegevens over waarschuwingen voor apparaten, bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.

Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen zijn toegewezen aan kolommen in de `AlertInfo` `AlertEvidence` tabellen en.

>[!TIP]
>Naast de kolommen de volgende tabel `AlertEvidence` bevat de tabel veel andere kolommen die een meer holistische afbeelding van waarschuwingen van diverse bronnen bieden. [Alle AlertEvidence kolommen weergeven](advanced-hunting-alertevidence-table.md) 

| Kolom DeviceAlertEvents | Waarnaar u dezelfde gegevens kunt vinden in Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` en  `AlertEvidence` tabellen |
| `Timestamp` | `AlertInfo` en  `AlertEvidence` tabellen |
| `DeviceId` | `AlertEvidence` tabel |
| `DeviceName` | `AlertEvidence` tabel |
| `Severity` | `AlertInfo` tabel |
| `Category` | `AlertInfo` tabel |
| `Title` | `AlertInfo` tabel |
| `FileName` | `AlertEvidence` tabel |
| `SHA1` | `AlertEvidence` tabel |
| `RemoteUrl` | `AlertEvidence` tabel |
| `RemoteIP` | `AlertEvidence` tabel |
| `AttackTechniques` | `AlertInfo` tabel |
| `ReportId` | Deze kolom wordt meestal in Microsoft Defender voor eindpunt gebruikt om gerelateerde records in andere tabellen te zoeken. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` . |
| `Table` | Deze kolom wordt meestal gebruikt in Microsoft Defender voor eindpunt voor aanvullende informatie over gebeurtenissen in andere tabellen. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` . |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Bestaande Microsoft Defender voor eindpunten query's aanpassen
Microsoft Defender voor eindpunt query's werken net zo, tenzij ze naar de `DeviceAlertEvents` tabel verwijzen. Als u deze query's wilt gebruiken in Microsoft 365 Defender, past u de volgende wijzigingen aan:

- Vervangen `DeviceAlertEvents` door `AlertInfo` .
- Neem deel aan de `AlertInfo` tabellen en de `AlertEvidence` tabellen `AlertId` om equivalente gegevens te vinden.

### <a name="original-query"></a>Oorspronkelijke query
De volgende query wordt `DeviceAlertEvents` in Microsoft Defender voor eindpunt gebruikt om de gewenste waarschuwingen _powershell.exe_ te ontvangen:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Gewijzigde query
De volgende query is aangepast voor gebruik in Microsoft 365 Defender. In plaats van de bestandsnaam rechtstreeks van `DeviceAlertEvents` te controleren, wordt `AlertEvidence` de bestandsnaam in die tabel samengevoegd en gecontroleerd.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft 365 Defender inschakelen](advanced-hunting-query-language.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Geavanceerde jacht in Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)