---
title: Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten met een geavanceerde jacht
description: Onderzoek veelvoorkomende jacht-scenario's en voorbeelden van zoekopdrachten die betrekking hebben op apparaten, e-mailberichten, apps en identiteiten.
keywords: geavanceerde jacht, Office365 gegevens, Windows-apparaten, Office365 e-mailberichten normaliseren, e-mails, apps, identiteiten, bedreigings jacht, Cyber Threat jacht, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 5b2ef4881eabea7e546eb8cd3d164b372b0018ee
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199827"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Met de [geavanceerde jacht](advanced-hunting-overview.md) in Microsoft Threat Protection kunt u op verschillende manieren te zoeken naar bedreigingen voor:
- Apparaten die worden beheerd met Microsoft Defender ATP
- E-mailberichten die worden verwerkt door Microsoft 365
- Cloud-app-activiteiten, verificatiegebeurtenissen en activiteiten van de domeincontroller die worden bijgehouden via de beveiliging van Microsoft Cloud-apps en Azure ATP

Met dit niveau van de zichtbaarheid kunt u snel zoeken naar bedreigingen die door secties van uw netwerk bladeren, waaronder verfijnde indringers die aankomen via e-mail of het web, lokale bevoegdheden toevoegen, machtigingen voor domeinnamen 

Hier volgen algemene technieken en voorbeelden van query's op basis van diverse jacht scenario's die u kunnen helpen om te ontdekken hoe u query's kunt maken wanneer u een nieuwe oplossing uitvoert voor dergelijke geavanceerde bedreigingen.

## <a name="get-entity-info"></a>Gegevens voor entiteit weergeven
Gebruik deze query's om te leren hoe u snel informatie kunt vinden over gebruikersaccounts, apparaten en bestanden. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Gebruikersaccounts van e-mailadressen verkrijgen
Wanneer u query's maakt [voor de tabellen die betrekking hebben op apparaten en e-mailberichten](advanced-hunting-schema-tables.md), moet u waarschijnlijk de naam van gebruikersaccounts verkrijgen via e-mailadressen van afzender of geadresseerde. U kunt dit algemeen doen voor geadresseerden of adressen van geadresseerden met behulp van de *lokale host* uit het e-mailadres.

In het onderstaande fragment wordt de functie [toString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto gebruikt om de lokale host te extraheren voordat de `@` e-mailadressen van de geadresseerden in de kolom worden weergegeven `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
In de volgende query ziet u hoe dit fragment kan worden gebruikt:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>De tabel IdentityInfo samenvoegen

U kunt rekening namen en andere accountgegevens aanvragen door de [tabel IdentityInfo](advanced-hunting-identityinfo-table.md)samen te voegen of eraan deel te nemen. De onderstaande query biedt de lijst met opsporings-en malware-detecties van de [tabel EmailEvents](advanced-hunting-emailevents-table.md) en voegt vervolgens deze informatie toe aan de `IdentityInfo` tabel voor gedetailleerde informatie over de geadresseerden. 

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

### <a name="get-device-information"></a>Apparaatgegevens achterhalen
Het [geavanceerde jacht-schema](advanced-hunting-schema-tables.md) biedt uitgebreide informatie over apparaten in diverse tabellen. De [tabel DeviceInfo](advanced-hunting-deviceinfo-table.md) bevat bijvoorbeeld uitgebreide informatie over apparaten op basis van de gebeurtenisgegevens die regelmatig zijn samengeteld. Met deze query wordt de `DeviceInfo` tabel gebruikt om te controleren of een gebruiker met een risico gemanipuleerd ( `<account-name>` ) is aangemeld bij een willekeurige computer en welke waarschuwingen op die apparaten zijn geactiveerd.

>[!Tip]
> Met deze query wordt `kind=inner` een [inner join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)opgegeven waarmee ontdubbeling van de linkerkant van waarden wordt voorkomen `DeviceId` .

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

## <a name="hunting-scenarios"></a>Jacht scenario's

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Aanmeldings activiteiten vermelden van gebruikers die e-mails ontvangen die niet zijn zapped
[Zero-Hour auto leegmaak (ZAP)](../office-365-security/zero-hour-auto-purge.md) verstuurt kwaadwillende e-mailberichten nadat deze zijn ontvangen. Als ZAP mislukt, kan kwaadaardige code uiteindelijk op het apparaat worden uitgevoerd en kan de accounts worden beschadigd. Met deze query wordt gecontroleerd of er een aanmeldingsactiviteit is uitgevoerd door de geadresseerden van e-mailberichten die niet zijn geadresseerd door ZAP.

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Aanmeldingspogingen voor domeinaccounts met een referentie diefstal aanvragen
Met deze query worden eerst alle waarschuwingen voor toegangsrechten voor referenties in de `AlertInfo` tabel aangeduid. De tabel wordt vervolgens samengevoegd of samengevoegd `AlertEvidence` , die wordt geparseerd voor de namen van de gerichte accounts en filters voor accounts die lid zijn van een domein. Ten slotte wordt de `IdentityLogonEvents` tabel gecontroleerd op alle aanmeldings activiteiten van de domeinnaam gerichte accounts.

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Controleren of bestanden van een bekende, schadelijke afzender op uw apparaten staan
Ervan uitgaand dat u bekend bent met een e-mailadres dat u schadelijke bestanden verzendt ( `MaliciousSender@example.com` ), kunt u deze query uitvoeren om te bepalen of bestanden van deze afzender bestaan op uw apparaten. U kunt deze query bijvoorbeeld gebruiken om apparaten aan te geven die worden beïnvloed door een malware-distributie campagne.

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Aanmeldingspogingen nakijken na ontvangst van kwaadaardige e-mailberichten
Met deze query vindt u de tien meest recente aanmeldingen van e-mail geadresseerden binnen 30 minuten nadat ze bekende, schadelijke e-mails hebben ontvangen. U kunt deze query gebruiken om te controleren of de accounts van de geadresseerden van het e-mailbericht zijn aangetast.

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>PowerShell-activiteiten nakijken na ontvangst van e-mailberichten van bekende schadelijke afzender
Kwaadwillende e-mailberichten bevatten vaak documenten en andere speciaal vervaardigde bijlagen die PowerShell-opdrachten uitvoeren voor het leveren van extra nettoladingen. Als u op de hoogte bent van e-mailberichten die afkomstig zijn van een bekende, schadelijke afzender ( `MaliciousSender@example.com` ), kunt u deze query gebruiken om PowerShell-activiteiten weer te geven en te controleren die binnen 30 minuten zijn opgetreden nadat een e-mailbericht van de afzender is ontvangen.  

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
