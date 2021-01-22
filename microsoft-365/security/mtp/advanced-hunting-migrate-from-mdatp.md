---
title: Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint
description: Informatie over het aanpassen van uw query's van Microsoft Defender voor eindpunten, zodat u deze kunt gebruiken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 08bdd1e22040166bb3becac32580a185c74f34a0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932308"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender for Endpoint om proactief te zoeken naar bedreigingen met behulp van een bredere set gegevens. In Microsoft 365 Defender krijgt u toegang tot gegevens uit andere beveiligingsoplossingen van Microsoft 365, waaronder:

- Microsoft Defender for Endpoint
- Microsoft Defender voor Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>De meeste klanten van Microsoft Defender voor eindpunten kunnen [Microsoft 365 Defender](prerequisites.md#licensing-requirements)zonder extra licenties gebruiken. Schakel [Microsoft 365 Defender](mtp-enable.md)in om te beginnen met de overgang van geavanceerde zoekwerkstromen van Defender voor eindpunt.

U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor eindpunt-werkstromen. Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd. Ze zijn echter wel zichtbaar in Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Alleen schematabellen in Microsoft 365 Defender
Het [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) biedt aanvullende tabellen met gegevens uit diverse Microsoft 365-beveiligingsoplossingen. De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:

| Tabelnaam | Beschrijving |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Waarschuwingen van Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit, inclusief ernstgegevens en bedreigingscategorieën  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Activiteiten in verband met bestanden in cloud-apps en -services |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informatie over bestanden die zijn bijgevoegd bij e-mailberichten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | E-mailgebeurtenissen van Microsoft 365, inclusief bezorging van e-mail en blokkeren van gebeurtenissen |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Beveiligingsgebeurtenissen na bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informatie over URL's in e-mailberichten |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Gebeurtenissen waarbij een on-premises domeincontroller Active Directory (AD) wordt uitgevoerd. Deze tabel beslaat een bereik van identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Verificatiegebeurtenissen in Active Directory en Online Services van Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents table
De `AlertInfo` tabel en tabellen vervangen de tabel in het schema van Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint. Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.

Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen worden toe te staan aan kolommen in de `AlertInfo` `AlertEvidence` tabellen.

>[!TIP]
>Naast de kolommen uit de volgende tabel bevat de tabel vele andere kolommen die een beter beeld geven van `AlertEvidence` waarschuwingen uit verschillende bronnen. [Alle kolommen voor AlertEvidence bekijken](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents column | Waar vind ik dezelfde gegevens in Microsoft 365 Defender? |
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
| `ReportId` | Deze kolom wordt meestal gebruikt in Microsoft Defender voor eindpunt om gerelateerde records te zoeken in andere tabellen. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen. |
| `Table` | Deze kolom wordt meestal gebruikt in Microsoft Defender for Endpoint voor aanvullende gebeurtenisgegevens in andere tabellen. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Bestaande Microsoft Defender voor eindpuntquery's aanpassen
Microsoft Defender voor eindpuntquery's werkt zoals ze zijn, tenzij ze naar de tabel `DeviceAlertEvents` verwijzen. Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u deze wijzigingen toepassen:

- Vervangen `DeviceAlertEvents` door `AlertInfo` .
- Join the `AlertInfo` and the tables on to get equivalent `AlertEvidence` `AlertId` data.

### <a name="original-query"></a>Oorspronkelijke query
De volgende query gebruikt microsoft Defender for Endpoint om de `DeviceAlertEvents` waarschuwingen te ontvangen die betrekking hebben oppowershell.exe: __

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Aangepaste query
De volgende query is aangepast voor gebruik in Microsoft 365 Defender. In plaats van de bestandsnaam rechtstreeks te controleren, wordt de naam van het bestand in de tabel toegevoegd en `DeviceAlertEvents` `AlertEvidence` gecontroleerd.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft 365 Defender in te zetten](advanced-hunting-query-language.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Geavanceerd zoeken in Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)