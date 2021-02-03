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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080736"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Geavanceerde zoekquery's migreren van Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Verplaats uw geavanceerde zoekwerkstromen van Microsoft Defender for Endpoint om proactief te zoeken naar bedreigingen met behulp van een bredere set gegevens. In Microsoft 365 Defender krijgt u toegang tot gegevens van andere beveiligingsoplossingen van Microsoft 365, waaronder:

- Microsoft Defender for Endpoint
- Microsoft Defender voor Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

>[!NOTE]
>De meeste klanten van Microsoft Defender voor eindpunten kunnen [Microsoft 365 Defender](prerequisites.md#licensing-requirements)zonder extra licenties gebruiken. Schakel [Microsoft 365 Defender](mtp-enable.md)in om te beginnen met de overgang van geavanceerde zoekwerkstromen van Defender voor eindpunt.

U kunt overstappen zonder dat dit van invloed is op uw bestaande Defender voor eindpunt-werkstromen. Opgeslagen query's blijven intact en aangepaste detectieregels blijven worden uitgevoerd en waarschuwingen worden gegenereerd. Ze zijn echter wel zichtbaar in Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Alleen schematabellen in Microsoft 365 Defender
Het [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) biedt aanvullende tabellen met gegevens uit diverse Microsoft 365-beveiligingsoplossingen. De volgende tabellen zijn alleen beschikbaar in Microsoft 365 Defender:

| Tabelnaam | Omschrijving |
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
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Verificatiegebeurtenissen in Active Directory en Microsoft-onlineservices |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query's voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen |

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents table
De tabel in het schema Microsoft Defender for Endpoint wordt vervangen door de `AlertInfo` `AlertEvidence` `DeviceAlertEvents` tabellen. Naast gegevens over apparaatwaarschuwingen bevatten deze twee tabellen gegevens over waarschuwingen voor identiteiten, apps en e-mailberichten.

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
| `ReportId` | Deze kolom wordt meestal gebruikt in Microsoft Defender voor eindpunt om gerelateerde records in andere tabellen te zoeken. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen. |
| `Table` | Deze kolom wordt meestal gebruikt in Microsoft Defender voor het eindpunt voor aanvullende gebeurtenisgegevens in andere tabellen. In Microsoft 365 Defender kunt u gerelateerde gegevens rechtstreeks uit de tabel `AlertEvidence` halen. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Bestaande Microsoft Defender voor eindpuntquery's aanpassen
Microsoft Defender voor eindpuntquery's werkt zoals ze zijn, tenzij ze naar de tabel `DeviceAlertEvents` verwijzen. Als u deze query's wilt gebruiken in Microsoft 365 Defender, moet u deze wijzigingen toepassen:

- Vervangen `DeviceAlertEvents` door `AlertInfo` .
- Join the `AlertInfo` and the tables on to get equivalent `AlertEvidence` `AlertId` data.

### <a name="original-query"></a>Oorspronkelijke query
De volgende query gebruikt `DeviceAlertEvents` Microsoft Defender for Endpoint __ om de waarschuwingen te ontvangen die betrekking hebben oppowershell.exe:

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

## <a name="migrate-custom-detection-rules"></a>Aangepaste detectieregels migreren

Wanneer regels van Microsoft Defender voor eindpunt worden bewerkt op Microsoft 365 Defender, blijven ze werken alsof de resulterende query alleen naar apparaattabellen kijkt. Waarschuwingen die worden gegenereerd door aangepaste detectieregels die query's uitvoeren op alleen apparaattabellen, worden bijvoorbeeld nog steeds bezorgd in uw SIEM en genereren e-mailmeldingen, afhankelijk van hoe u deze hebt geconfigureerd in Microsoft Defender voor eindpunt. Eventuele bestaande onderdrukkende regels in Defender voor eindpunt blijven van toepassing.

Zodra u een regel van Defender voor eindpunt bewerkt zodat identiteits- en e-mailtabellen worden opgevraagd, die alleen beschikbaar zijn in Microsoft 365 Defender, wordt de regel automatisch verplaatst naar Microsoft 365 Defender. 

Waarschuwingen die worden gegenereerd door de gemigreerde regel:

- Zijn niet meer zichtbaar in de portal Defender for Endpoint (Microsoft Defender-beveiligingscentrum)
- Stop met bezorgen in uw SIEM of genereer e-mailmeldingen. U kunt deze wijziging omsdraaien door meldingen via Microsoft 365 Defender zo te configureren dat de waarschuwingen worden ontvangen. U kunt de [Microsoft 365 Defender-API](api-incident.md) gebruiken om meldingen te ontvangen voor waarschuwingen van klantendetectie of verwante incidenten.
- Wordt niet onderdrukken door de regels voor het onderdrukken van eindpunten van Microsoft Defender voor Eindpunt. Als u wilt voorkomen dat waarschuwingen worden gegenereerd voor bepaalde gebruikers, apparaten of postvakken, wijzigt u de bijbehorende query's om deze entiteiten expliciet uit te sluiten.

Als u een regel op deze manier bewerkt, wordt u om bevestiging gevraagd voordat dergelijke wijzigingen worden toegepast.

Nieuwe waarschuwingen die worden gegenereerd door aangepaste detectieregels in de Microsoft 365 Defender-portal, worden weergegeven op een waarschuwingspagina met de volgende informatie:

- Naam en beschrijving van waarschuwing 
- Beïnvloede activa
- Acties die zijn ondernomen in reactie op de waarschuwing
- Queryresultaten die de waarschuwing hebben geactiveerd 
- Informatie over de aangepaste detectieregel 
 
![Afbeelding van de pagina Nieuwe waarschuwing](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>Query's schrijven zonder DeviceAlertEvents

In het Microsoft 365 Defender-schema worden de tabellen en de tabellen verstrekt voor de diverse reeks informatie die bij waarschuwingen `AlertInfo` `AlertEvidence` van verschillende bronnen past. 

Als u dezelfde waarschuwingsgegevens uit de tabel in het schema Microsoft Defender for Endpoint hebt ontvangen, filtert u de tabel op en voegt u elke unieke id toe aan de tabel, die gedetailleerde informatie over gebeurtenissen en entiteiten `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` biedt. 

Zie de voorbeeldquery hieronder:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Deze query levert veel meer kolommen op dan `DeviceAlertEvents` in het schema van Microsoft Defender voor eindpunt. Gebruik alleen kolommen waarin u geïnteresseerd bent om de resultaten `project` beheersbaar te houden. In het onderstaande voorbeeld ziet u de kolommen waarin u mogelijk geïnteresseerd bent wanneer door het onderzoek PowerShell-activiteit is gedetecteerd:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Als u wilt filteren op specifieke entiteiten die betrokken zijn bij de waarschuwingen, kunt u dit doen door het entiteitstype op te geven en de waarde die u wilt `EntityType` filteren. In het volgende voorbeeld wordt naar een specifiek IP-adres zoekt:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Zie ook
- [Microsoft 365 Defender in te zetten](advanced-hunting-query-language.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Geavanceerd zoeken in Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)