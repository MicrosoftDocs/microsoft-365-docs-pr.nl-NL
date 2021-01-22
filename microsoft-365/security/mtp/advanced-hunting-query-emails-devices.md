---
title: Op bedreigingen zoeken op apparaten, e-mails, apps en identiteiten met geavanceerd zoeken
description: Veelvoorkomende zoekscenario's en voorbeeldquery's gebruiken voor apparaten, e-mailberichten, apps en identiteiten.
keywords: geavanceerd zoeken, Office365-gegevens, Windows-apparaten, Office365-e-mails normaliseren, e-mails, apps, identiteiten, bedreigingszoekactie, cyberaanvallen zoeken, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932248"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Geavanceerd zoeken](advanced-hunting-overview.md) in Microsoft 365 Defender stelt u in staat proactief te zoeken naar bedreigingen:
- Apparaten die worden beheerd door Microsoft Defender voor eindpunt
- E-mailberichten verwerkt door Microsoft 365
- Activiteiten in de cloud-app, verificatiegebeurtenissen en activiteiten van de domeincontroller die worden bijgeslagen door Microsoft Cloud App Security en Microsoft Defender for Identity

Met dit zichtbaarheidsniveau kunt u snel zoeken naar bedreigingen die secties in uw netwerk doorkruisen, waaronder geavanceerde toegangsgegevens die via e-mail of internet binnenkomen, lokale bevoegdheden verhogen, referenties voor bevoorrecht domein verkrijgen en laterally verplaatsen naar al uw apparaten. 

Hier vindt u algemene technieken en voorbeeldquery's op basis van verschillende scenario's voor het zoeken naar query's die u kunt gebruiken om query's te maken wanneer u op dergelijke geavanceerde bedreigingen kunt zoeken.

## <a name="get-entity-info"></a>Informatie over de entiteit op halen
Gebruik deze query's als u wilt weten hoe u snel informatie kunt krijgen over gebruikersaccounts, apparaten en bestanden. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Gebruikersaccounts verkrijgen van e-mailadressen
Wanneer u query's maakt [in](advanced-hunting-schema-tables.md)tabellen die betrekking hebben op apparaten en e-mailberichten, moet u waarschijnlijk de namen van gebruikersaccounts verkrijgen bij de e-mailadressen van afzenders of geadresseerden. In het algemeen kunt u dit doen voor het adres van de geadresseerde of de afzender met behulp van de lokale host via het *e-mailadres.*

In het onderstaande fragment gebruiken we de [functie tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto om de local-host direct voor de e-mailadressen van geadresseerden in de kolom `@` uit te `RecipientEmailAddress` halen.

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
De onderstaande query laat zien hoe dit fragment kan worden gebruikt:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>De tabel IdentityInfo samenvoegen

U kunt accountnamen en andere accountgegevens verkrijgen door de [tabel IdentityInfo samen te](advanced-hunting-identityinfo-table.md)voegen of samen te voegen. Met de onderstaande query wordt de lijst met phishing- en malwaredetecties uit de tabel [EmailEvents](advanced-hunting-emailevents-table.md) weergegeven en wordt die informatie vervolgens aan de tabel toegevoegd voor gedetailleerde informatie over `IdentityInfo` elke geadresseerde. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Apparaatgegevens verkrijgen
Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) biedt uitgebreide informatie over het apparaat in verschillende tabellen. De tabel [DeviceInfo](advanced-hunting-deviceinfo-table.md) bevat bijvoorbeeld uitgebreide apparaatgegevens op basis van gebeurtenisgegevens die regelmatig worden samengevoegd. Deze query gebruikt de tabel om te controleren of een mogelijk gecompromitteerd gebruiker () zich heeft aangemeld op een apparaat en geeft vervolgens de waarschuwingen weer die op die apparaten `DeviceInfo` `<account-name>` zijn geactiveerd.

>[!Tip]
> Deze query wordt `kind=inner` gebruikt om een [inner-join op](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)te geven, waarmee deduplicatie van linkerwaarden voor `DeviceId` .

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

## <a name="hunting-scenarios"></a>Scenario's zoeken

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Aanmeldingsactiviteiten van gebruikers die e-mailberichten hebben ontvangen die niet zijn gezaped
[Met Zero-hour Auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) worden schadelijke e-mailberichten na ontvangst geadresseerden. Als ZAP mislukt, kan schadelijke code uiteindelijk worden uitgevoerd op het apparaat en accounts gehackt laten. Deze query controleert op aanmeldingsactiviteiten die zijn uitgevoerd door de geadresseerden van e-mailberichten die niet konden worden verwerkt door ZAP.

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
Met deze query worden eerst alle waarschuwingen voor toegang tot referenties in de tabel `AlertInfo` geïdentificeerd. Vervolgens wordt de tabel samengevoegd of samengevoegd, die wordt geparseert voor de namen van de gerichte accounts en filters voor accounts die aan een domein zijn `AlertEvidence` verbonden. Ten slotte wordt de tabel gecontroleerd op alle aanmeldingsactiviteiten van `IdentityLogonEvents` de targeted-accounts die lid zijn van een domein.

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Controleren of bestanden van een bekende kwaadwillende afzender op uw apparaten staan
Als u zeker weet dat er een e-mailadres is voor het verzenden van schadelijke bestanden ( ), kunt u deze query uitvoeren om te bepalen of de bestanden van deze afzender `MaliciousSender@example.com` op uw apparaten aanwezig zijn. U kunt deze query bijvoorbeeld gebruiken om apparaten te identificeren die worden beïnvloed door een malwaredistributiecampagne.

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Aanmeldingspogingen na ontvangst van schadelijke e-mailberichten controleren
Deze query vindt de tien meest recente aanmeldingen die zijn uitgevoerd door e-mailontvangers binnen 30 minuten nadat ze bekende schadelijke e-mailberichten hebben ontvangen. U kunt deze query gebruiken om te controleren of de accounts van de geadresseerden van de e-mail zijn gehackt.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>PowerShell-activiteiten controleren na ontvangst van e-mailberichten van bekende kwaadwillende afzenders
Schadelijke e-mailberichten bevatten vaak documenten en andere speciaal opgebouwde bijlagen die PowerShell-opdrachten uitvoeren om extra nettolading aan te leveren. Als u op de hoogte bent van e-mailberichten afkomstig van een bekende kwaadwillende afzender (), kunt u deze query gebruiken om PowerShell-activiteiten te bekijken die zijn opgetreden binnen 30 minuten nadat een e-mailbericht van de afzender is `MaliciousSender@example.com` ontvangen.  

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
