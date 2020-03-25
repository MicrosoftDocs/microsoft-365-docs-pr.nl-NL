---
title: Zoek bedreigingen op verschillende apparaten en e-mails met behulp van geavanceerde jacht
description: Bestudeer veelvoorkomende jachtscenario's en voorbeeldquery's die betrekking hebben op apparaten en e-mails.
keywords: geavanceerde jacht, Office365-gegevens, Windows-apparaten, Office365-e-mails normaliseren, e-mails, bedreigingsjacht, cyberdreiging, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 8310a9a57c8dc7406c0b1d56b20009b6400abcb1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928982"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Zoek naar bedreigingen op verschillende apparaten en e-mails

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



[Met geavanceerde jacht](advanced-hunting-overview.md) in Microsoft Threat Protection u proactief op zoek gaan naar bedreigingen op uw Windows-apparaten en Office 365-e-mails. Hier volgen enkele jachtscenario's en voorbeeldquery's die u kunnen helpen te onderzoeken hoe u query's maken voor zowel apparaten als e-mails.

## <a name="obtain-user-accounts-from-email-addresses"></a>Gebruikersaccounts verkrijgen via e-mailadressen
Wanneer u query's maakt in [tabellen die apparaten en e-mails behandelen,](advanced-hunting-schema-tables.md)moet u waarschijnlijk gebruikersaccountnamen verkrijgen van e-mailadressen van afzender of ontvanger. Gebruik hiervoor de lokale host vanaf het *e-mailadres:*

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Deze normalisatietechniek wordt gebruikt in de volgende scenario's.

## <a name="hunting-scenarios"></a>Jachtscenario's

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Controleren of bestanden van een bekende afzender op uw apparaten staan
Ervan uitgaande dat u weet van een e-mailadres dat schadelijke bestanden verzendt, u deze query uitvoeren om te bepalen of er bestanden van deze afzender op uw apparaten bestaan. U deze query bijvoorbeeld gebruiken om het aantal apparaten te bepalen dat wordt beïnvloed door een malwaredistributiecampagne.

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Inlogpogingen bekijken na ontvangst van kwaadaardige e-mails
Deze query vindt de 10 laatste logons uitgevoerd door e-mail ontvangers binnen 30 minuten nadat ze bekende kwaadaardige e-mails ontvangen. U deze query gebruiken om te controleren of de accounts van de e-mailontvangers zijn gecompromitteerd.

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>PowerShell-activiteiten bekijken na ontvangst van e-mails van bekende kwaadwillende afzender
Schadelijke e-mails bevatten vaak documenten en andere speciaal vervaardigde bijlagen die PowerShell-opdrachten uitvoeren om extra payloads te leveren. Als u op de hoogte bent van e-mails van een bekende afzender, u deze query gebruiken om PowerShell-activiteiten aan te geven en te bekijken die zich binnen 30 minuten nadat een e-mail van de afzender was ontvangen.  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Geavanceerd jachtoverzicht](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
