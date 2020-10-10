---
title: Geavanceerde jagers-query's migreren vanuit Microsoft Defender ATP
description: Meer informatie over het aanpassen van uw Microsoft Defender ATP-query's, zodat u deze kunt gebruiken in Microsoft Threat Protection
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
- m365-initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1738180e192baafa60f76fada1e433319922b91
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412680"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Geavanceerde jagers-query's migreren vanuit Microsoft Defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft Threat Protection

Verplaats uw werkstromen voor gevorderden in Microsoft Defender ATP om te zoeken naar bedreigingen met een bredere set gegevens. In Microsoft Threat Protection krijgt u toegang tot gegevens vanuit andere Microsoft 365-beveiligingsoplossingen, waaronder:

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

>[!NOTE]
>De meeste Microsoft Defender ATP-klanten kunnen [Microsoft Threat Protection gebruiken zonder extra licenties](prerequisites.md#licensing-requirements). [Schakel Microsoft Threat Protection](mtp-enable.md)in om te beginnen met het overstappen van uw werkstromen voor gevorderden in Microsoft Defender ATP.

U kunt overstappen zonder dat dit invloed heeft op uw bestaande Microsoft Defender ATP-werkstromen. Opgeslagen query's blijven behouden en aangepaste detectieregels blijven doorgaan met het uitvoeren en genereren van waarschuwingen. Ze zijn echter ook zichtbaar in Microsoft Threat Protection. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Schema tabellen in Microsoft Threat Protection
Het [geavanceerde Microsoft Threat Protection-schema](advanced-hunting-schema-tables.md) bevat extra tabellen met gegevens van diverse microsoft 365-beveiligingsoplossingen. De volgende tabellen zijn alleen beschikbaar in Microsoft Threat Protection:

| Tabelnaam | Beschrijving |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Bestanden, IP-adressen, Url's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Waarschuwingen uit Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud app Security en Azure ATP, waaronder informatie over de ernst en bedreigings Categorieën  |
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
`AlertInfo`Met de `AlertEvidence` tabellen en worden de tabellen `DeviceAlertEvents` in het MICROsoft Defender ATP-schema vervangen. Naast gegevens over waarschuwingen voor apparaten, bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.

Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen zijn toegewezen aan kolommen in de `AlertInfo` `AlertEvidence` tabellen en.

>[!TIP]
>Naast de kolommen de volgende tabel `AlertEvidence` bevat de tabel veel andere kolommen die een meer holistische afbeelding van waarschuwingen van diverse bronnen bieden. [Alle AlertEvidence kolommen weergeven](advanced-hunting-alertevidence-table.md) 

| Kolom DeviceAlertEvents | Waarnaar u dezelfde gegevens kunt vinden in Microsoft Threat Protection |
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
| `ReportId` | Deze kolom wordt meestal gebruikt in Microsoft Defender ATP om gerelateerde records in andere tabellen te zoeken. In Microsoft Threat Protection kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` . |
| `Table` | Deze kolom wordt meestal gebruikt in Microsoft Defender ATP voor aanvullende informatie over gebeurtenissen in andere tabellen. In Microsoft Threat Protection kunt u gerelateerde gegevens rechtstreeks uit de tabel weergeven `AlertEvidence` . |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Bestaande Microsoft Defender ATP-query's aanpassen
Microsoft Defender ATP-query's werken net zo, tenzij ze naar de `DeviceAlertEvents` tabel verwijzen. Als u deze query's wilt gebruiken in Microsoft Threat Protection, past u de volgende wijzigingen aan:

- Vervangen `DeviceAlertEvents` door `AlertInfo` .
- Neem deel aan de `AlertInfo` tabellen en de `AlertEvidence` tabellen `AlertId` om equivalente gegevens te vinden.

### <a name="original-query"></a>Oorspronkelijke query
De volgende query wordt `DeviceAlertEvents` in Microsoft Defender ATP gebruikt om de gewenste waarschuwingen _powershell.exe_te ontvangen:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Gewijzigde query
De volgende query is aangepast voor gebruik in Microsoft Threat Protection. In plaats van de bestandsnaam rechtstreeks van `DeviceAlertEvents` te controleren, wordt `AlertEvidence` de bestandsnaam in die tabel samengevoegd en gecontroleerd.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft Threat Protection inschakelen](advanced-hunting-query-language.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Geavanceerde jacht in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)