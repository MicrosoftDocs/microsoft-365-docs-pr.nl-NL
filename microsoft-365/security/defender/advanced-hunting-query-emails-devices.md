---
title: Op bedreigingen zoeken op verschillende apparaten, e-mailberichten, apps en identiteiten met geavanceerde jacht
description: Bestudeer veelvoorkomende scenario's en voorbeeldquery's die betrekking hebben op apparaten, e-mailberichten, apps en identiteiten.
keywords: geavanceerde jacht, Office365-gegevens, Windows-apparaten, Office365-e-mails normaliseren, e-mails, apps, identiteiten, bedreigingsjacht, cyberdreigingsjacht, zoeken, query, telemetrie, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: 8a811d60af281bb534776736e77c3eb54ab6a760
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932963"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Dreigingen in apparaten, e-mailberichten, apps en identiteiten opsporen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Met geavanceerde Microsoft 365](advanced-hunting-overview.md) Defender kunt u proactief op bedreigingen zoeken:
- Apparaten die worden beheerd door Microsoft Defender voor Eindpunt
- E-mailberichten die door Microsoft 365
- Activiteiten van cloud-apps, verificatiegebeurtenissen en activiteiten van domeincontrollers die worden bij Microsoft Cloud App Security en Microsoft Defender voor identiteit

Met dit niveau van zichtbaarheid kunt u snel zoeken naar bedreigingen die door secties van uw netwerk lopen, zoals geavanceerde inbraken die binnenkomen op e-mail of internet, lokale bevoegdheden verhogen, geprivilegieerde domeinreferenties verkrijgen en lateraal naar uw apparaten gaan. 

Hier vindt u algemene technieken en voorbeeldquery's op basis van verschillende scenario's waarmee u kunt onderzoeken hoe u query's kunt maken wanneer u op dergelijke geavanceerde bedreigingen jaagt.

## <a name="get-entity-info"></a>Entiteitsgegevens krijgen
Gebruik deze query's om te leren hoe u snel informatie kunt krijgen over gebruikersaccounts, apparaten en bestanden. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Gebruikersaccounts verkrijgen van e-mailadressen
Bij het maken van query's in tabellen die betrekking hebben op [apparaten](advanced-hunting-schema-tables.md)en e-mailberichten, moet u waarschijnlijk gebruikersaccountnamen verkrijgen van e-mailadressen van afzenders of geadresseerden. U kunt dit in het algemeen doen voor geadresseerde of afzender met behulp van de lokale host vanaf het *e-mailadres.*

In het onderstaande fragment gebruiken we de [functie tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto om de lokale host direct vóór de e-mailadressen van geadresseerden in de kolom `@` op te `RecipientEmailAddress` halen.

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
In de onderstaande query ziet u hoe dit fragment kan worden gebruikt:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>De tabel IdentityInfo samenvoegen

U kunt accountnamen en andere accountgegevens verkrijgen door de tabel [IdentityInfo samen](advanced-hunting-identityinfo-table.md)te voegen of aan te sluiten. In de onderstaande query wordt de lijst met phishing- en malwaredetecties uit de tabel [EmailEvents](advanced-hunting-emailevents-table.md) opgevraagd en wordt deze informatie toegevoegd aan de tabel voor gedetailleerde informatie `IdentityInfo` over elke geadresseerde. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Apparaatgegevens verkrijgen
Het [geavanceerde schema voor jagen](advanced-hunting-schema-tables.md) bevat uitgebreide apparaatinformatie in verschillende tabellen. De tabel [DeviceInfo](advanced-hunting-deviceinfo-table.md) bevat bijvoorbeeld uitgebreide apparaatgegevens op basis van gebeurtenisgegevens die regelmatig worden samengevoegd. In deze query wordt de tabel gebruikt om te controleren of een mogelijk gecompromitteerde gebruiker () zich heeft aangemeld bij apparaten en worden vervolgens de waarschuwingen vermeld die op die apparaten `DeviceInfo` `<account-name>` zijn geactiveerd.

>[!Tip]
> Deze query wordt `kind=inner` gebruikt om een [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)op te geven, waarmee deduplicatie van waarden aan de linkerkant voor wordt `DeviceId` voorkomen.

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>Scenario's voor jagen

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Aanmeldingsactiviteiten lijst van gebruikers die e-mailberichten hebben ontvangen die niet zijn gezapeerd
[Zap (Zero Hour Auto Purge)](../office-365-security/zero-hour-auto-purge.md) adresseert schadelijke e-mailberichten nadat ze zijn ontvangen. Als ZAP mislukt, kan schadelijke code uiteindelijk worden uitgevoerd op het apparaat en accounts in gevaar brengen. Met deze query wordt gecontroleerd op aanmeldingsactiviteit die is uitgevoerd door de geadresseerden van e-mailberichten die niet zijn geadresseerd door ZAP.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Aanmeldingspogingen krijgen van domeinaccounts die zijn gericht op diefstal van referenties
Met deze query worden eerst alle waarschuwingen voor toegang tot referenties in de `AlertInfo` tabel geïdentificeerd. Vervolgens wordt de tabel samengevoegd of samengevoegd, die alleen wordt geparseert voor de namen van de doelaccounts en filters voor accounts met een `AlertEvidence` domein. Ten slotte wordt de tabel gecontroleerd om alle aanmeldingsactiviteiten van de met het domein verbonden `IdentityLogonEvents` gerichte accounts op te halen.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Controleren of bestanden van een bekende kwaadwillende afzender zich op uw apparaten
Ervan uitgaande dat u op de hoogte bent van een e-mailadres dat schadelijke bestanden () verstuurt, kunt u deze query uitvoeren om te bepalen of er bestanden van deze afzender op `MaliciousSender@example.com` uw apparaten aanwezig zijn. U kunt deze query bijvoorbeeld gebruiken om apparaten te identificeren die zijn beïnvloed door een malwaredistributiecampagne.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Aanmeldingspogingen controleren na ontvangst van schadelijke e-mailberichten
Met deze query worden de tien meest recente aanmeldingen gevonden die zijn uitgevoerd door e-mailontvangers binnen 30 minuten nadat ze bekende schadelijke e-mailberichten hebben ontvangen. U kunt deze query gebruiken om te controleren of de accounts van de e-mailontvangers zijn gehackt.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>PowerShell-activiteiten controleren na ontvangst van e-mailberichten van bekende kwaadwillende afzender
Schadelijke e-mailberichten bevatten vaak documenten en andere speciaal ontworpen bijlagen die PowerShell-opdrachten uitvoeren om extra laadvermogen te leveren. Als u op de hoogte bent van e-mailberichten die afkomstig zijn van een bekende kwaadwillende afzender (), kunt u deze query gebruiken om PowerShell-activiteiten op te nemen en te bekijken die binnen 30 minuten na ontvangst van een e-mailbericht van de afzender hebben `MaliciousSender@example.com` plaatsgevonden.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)