---
title: Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt
description: Meer informatie over het aanpassen van uw Microsoft Defender voor eindpuntquery's, zodat u ze kunt gebruiken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender for Endpoint, search, query, telemetry, custom detections, schema, kusto, mapping
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 5513c4b4fd8c5e24f9ada989113abc8a10e6a864
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933443"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Geavanceerde zoekquery's migreren van Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender voor Eindpunt om proactief te zoeken naar bedreigingen met een bredere set gegevens. In Microsoft 365 Defender krijgt u toegang tot gegevens van andere beveiligingsoplossingen van Microsoft 365, waaronder:

- Microsoft Defender voor Eindpunt
- Microsoft Defender voor Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>De meeste Klanten van Microsoft Defender voor eindpunten kunnen [Microsoft 365 Defender gebruiken zonder extra licenties.](prerequisites.md#licensing-requirements) Schakel [Microsoft 365 Defender](m365d-enable.md)in om te beginnen met het overstappen van uw geavanceerde werkstromen voor jagen vanuit Defender voor Eindpunt.

U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor Eindpunt-werkstromen. Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd. Ze zijn echter zichtbaar in Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Alleen schematabellen in Microsoft 365 Defender
Het geavanceerde zoekschema van [Microsoft 365 Defender](advanced-hunting-schema-tables.md) bevat aanvullende tabellen met gegevens uit verschillende beveiligingsoplossingen van Microsoft 365. De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:

| Tabelnaam | Beschrijving |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Bestanden, IP-adressen, URL's, gebruikers of apparaten die zijn gekoppeld aan waarschuwingen |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit, inclusief ernstsinformatie en bedreigingscategorieën  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Bestandsgerelateerde activiteiten in cloud-apps en -services |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informatie over bestanden die zijn gekoppeld aan e-mailberichten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | E-mailgebeurtenissen van Microsoft 365, inclusief e-mailbezorging en het blokkeren van gebeurtenissen |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Beveiligingsgebeurtenissen die zich voordoen na de bezorging, nadat Microsoft 365 de e-mailberichten heeft bezorgd bij het postvak van de geadresseerde |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informatie over URL's in e-mailberichten |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Gebeurtenissen met een on-premises domeincontroller met Active Directory (AD). Deze tabel bestrijkt een reeks identiteitsgerelateerde gebeurtenissen en systeemgebeurtenissen op de domeincontroller. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Accountgegevens uit verschillende bronnen, waaronder Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Verificatiegebeurtenissen in Active Directory- en Microsoft-onlineservices |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

>[!IMPORTANT]
> Query's en aangepaste detecties die schematabellen gebruiken die alleen beschikbaar zijn in Microsoft 365 Defender, kunnen alleen worden weergegeven in Microsoft 365 Defender.

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents table
De `AlertInfo` en tabellen vervangen de tabel in het Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-schema. Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.

Gebruik de volgende tabel om te controleren hoe `DeviceAlertEvents` kolommen worden toe te schrijven aan kolommen in de en `AlertInfo` `AlertEvidence` tabellen.

>[!TIP]
>Naast de kolommen in de volgende tabel bevat de tabel veel andere kolommen die een meer holistisch beeld geven van `AlertEvidence` waarschuwingen uit verschillende bronnen. [Alle kolommen van AlertEvidence bekijken](advanced-hunting-alertevidence-table.md) 

| Kolom DeviceAlertEvents | Waar vindt u dezelfde gegevens in Microsoft 365 Defender |
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
| `ReportId` | Deze kolom wordt meestal gebruikt in Microsoft Defender voor Eindpunt om gerelateerde records in andere tabellen te zoeken. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de `AlertEvidence` tabel halen. |
| `Table` | Deze kolom wordt meestal gebruikt in Microsoft Defender voor Eindpunt voor aanvullende gebeurtenisgegevens in andere tabellen. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de `AlertEvidence` tabel halen. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Bestaande Microsoft Defender voor eindpuntquery's aanpassen
Microsoft Defender voor eindpuntquery's werken zoals ze zijn, tenzij ze verwijzen naar de `DeviceAlertEvents` tabel. Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u de volgende wijzigingen toepassen:

- Vervangen `DeviceAlertEvents` door `AlertInfo` .
- Sluit u `AlertInfo` aan bij de tabellen en voeg deze toe om `AlertEvidence` `AlertId` equivalente gegevens te krijgen.

### <a name="original-query"></a>Oorspronkelijke query
De volgende query wordt gebruikt in Microsoft Defender voor Eindpunt om de waarschuwingen te `DeviceAlertEvents` krijgen die betrekking hebben op _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Gewijzigde query
De volgende query is aangepast voor gebruik in Microsoft 365 Defender. In plaats van de bestandsnaam rechtstreeks vandaan te controleren, wordt de bestandsnaam in die tabel toegevoegd en gecontroleerd `DeviceAlertEvents` `AlertEvidence` op de bestandsnaam.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Aangepaste detectieregels migreren

Wanneer microsoft Defender voor eindpuntregels worden bewerkt op Microsoft 365 Defender, blijven ze werken zoals voorheen als de resulterende query alleen naar apparaattabellen kijkt. 

Waarschuwingen die worden gegenereerd door aangepaste detectieregels die alleen apparaattabellen bevragen, blijven bijvoorbeeld bezorgd bij uw SIEM en genereren e-mailmeldingen, afhankelijk van hoe u deze hebt geconfigureerd in Microsoft Defender voor Eindpunt. Bestaande onderdrukkingsregels in Defender voor Eindpunt blijven ook van toepassing.

Nadat u een Defender voor Eindpunt-regel hebt bewerkt, zodat identiteits- en e-mailtabellen worden opgevraagd, die alleen beschikbaar zijn in Microsoft 365 Defender, wordt de regel automatisch verplaatst naar Microsoft 365 Defender. 

Waarschuwingen gegenereerd door de gemigreerde regel:

- Zijn niet meer zichtbaar in de Defender for Endpoint-portal (Microsoft Defender Security Center)
- Stop met leveren aan uw SIEM of genereer e-mailmeldingen. Als u deze wijziging wilt aanpassen, configureert u meldingen via Microsoft 365 Defender om de waarschuwingen te ontvangen. U kunt de [Microsoft 365 Defender-API gebruiken](api-incident.md) om meldingen te ontvangen voor waarschuwingen voor klantdetectie of verwante incidenten.
- Wordt niet onderdrukt door microsoft Defender voor endpoint-onderdrukkingsregels. Als u wilt voorkomen dat waarschuwingen worden gegenereerd voor bepaalde gebruikers, apparaten of postvakken, wijzigt u de bijbehorende query's om deze entiteiten expliciet uit te sluiten.

Als u een regel op deze manier bewerkt, wordt u gevraagd om bevestiging voordat dergelijke wijzigingen worden toegepast.

Nieuwe waarschuwingen die worden gegenereerd door aangepaste detectieregels in de Microsoft 365 Defender-portal, worden weergegeven op een waarschuwingspagina met de volgende informatie:

- Waarschuwingstitel en beschrijving 
- Beïnvloede activa
- Acties die zijn ondernomen in reactie op de waarschuwing
- Queryresultaten die de waarschuwing hebben geactiveerd 
- Informatie over de aangepaste detectieregel 
 
![Afbeelding van nieuwe waarschuwingspagina](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>Query's schrijven zonder DeviceAlertEvents

In het Microsoft 365 Defender-schema worden de tabellen en tabellen geleverd voor de diverse set informatie die bij `AlertInfo` waarschuwingen van verschillende bronnen `AlertEvidence` past. 

Als u dezelfde waarschuwingsgegevens wilt ontvangen die u hebt gebruikt om uit de tabel in het Schema van Microsoft Defender voor eindpunten te komen, filtert u de tabel op en voegt u vervolgens elke unieke id toe aan de tabel, die gedetailleerde gebeurtenis- en entiteitsgegevens `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` bevat. 

Zie de voorbeeldquery hieronder:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Deze query levert veel meer kolommen op dan `DeviceAlertEvents` in het Schema van Microsoft Defender voor eindpunt. Als u de resultaten beheersbaar wilt houden, `project` gebruikt u alleen de kolommen waarin u geïnteresseerd bent. In het onderstaande voorbeeld ziet u kolommen waarin u mogelijk geïnteresseerd bent wanneer tijdens het onderzoek PowerShell-activiteit is gedetecteerd:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Als u wilt filteren op specifieke entiteiten die betrokken zijn bij de waarschuwingen, kunt u dit doen door het entiteitstype in op te geven en de waarde op te geven die u `EntityType` wilt filteren. In het volgende voorbeeld wordt naar een specifiek IP-adres op zoek:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Zie ook
- [Microsoft 365 Defender inschakelen](advanced-hunting-query-language.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)