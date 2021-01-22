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
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="5ec74-104">Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="5ec74-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5ec74-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5ec74-105">**Applies to:**</span></span>
- <span data-ttu-id="5ec74-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ec74-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5ec74-107">[Geavanceerd zoeken](advanced-hunting-overview.md) in Microsoft 365 Defender stelt u in staat proactief te zoeken naar bedreigingen:</span><span class="sxs-lookup"><span data-stu-id="5ec74-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="5ec74-108">Apparaten die worden beheerd door Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="5ec74-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="5ec74-109">E-mailberichten verwerkt door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ec74-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="5ec74-110">Activiteiten in de cloud-app, verificatiegebeurtenissen en activiteiten van de domeincontroller die worden bijgeslagen door Microsoft Cloud App Security en Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5ec74-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="5ec74-111">Met dit zichtbaarheidsniveau kunt u snel zoeken naar bedreigingen die secties in uw netwerk doorkruisen, waaronder geavanceerde toegangsgegevens die via e-mail of internet binnenkomen, lokale bevoegdheden verhogen, referenties voor bevoorrecht domein verkrijgen en laterally verplaatsen naar al uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="5ec74-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="5ec74-112">Hier vindt u algemene technieken en voorbeeldquery's op basis van verschillende scenario's voor het zoeken naar query's die u kunt gebruiken om query's te maken wanneer u op dergelijke geavanceerde bedreigingen kunt zoeken.</span><span class="sxs-lookup"><span data-stu-id="5ec74-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="5ec74-113">Informatie over de entiteit op halen</span><span class="sxs-lookup"><span data-stu-id="5ec74-113">Get entity info</span></span>
<span data-ttu-id="5ec74-114">Gebruik deze query's als u wilt weten hoe u snel informatie kunt krijgen over gebruikersaccounts, apparaten en bestanden.</span><span class="sxs-lookup"><span data-stu-id="5ec74-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="5ec74-115">Gebruikersaccounts verkrijgen van e-mailadressen</span><span class="sxs-lookup"><span data-stu-id="5ec74-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="5ec74-116">Wanneer u query's maakt [in](advanced-hunting-schema-tables.md)tabellen die betrekking hebben op apparaten en e-mailberichten, moet u waarschijnlijk de namen van gebruikersaccounts verkrijgen bij de e-mailadressen van afzenders of geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="5ec74-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="5ec74-117">In het algemeen kunt u dit doen voor het adres van de geadresseerde of de afzender met behulp van de lokale host via het *e-mailadres.*</span><span class="sxs-lookup"><span data-stu-id="5ec74-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="5ec74-118">In het onderstaande fragment gebruiken we de [functie tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto om de local-host direct voor de e-mailadressen van geadresseerden in de kolom `@` uit te `RecipientEmailAddress` halen.</span><span class="sxs-lookup"><span data-stu-id="5ec74-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="5ec74-119">De onderstaande query laat zien hoe dit fragment kan worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="5ec74-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="5ec74-120">De tabel IdentityInfo samenvoegen</span><span class="sxs-lookup"><span data-stu-id="5ec74-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="5ec74-121">U kunt accountnamen en andere accountgegevens verkrijgen door de [tabel IdentityInfo samen te](advanced-hunting-identityinfo-table.md)voegen of samen te voegen.</span><span class="sxs-lookup"><span data-stu-id="5ec74-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="5ec74-122">Met de onderstaande query wordt de lijst met phishing- en malwaredetecties uit de tabel [EmailEvents](advanced-hunting-emailevents-table.md) weergegeven en wordt die informatie vervolgens aan de tabel toegevoegd voor gedetailleerde informatie over `IdentityInfo` elke geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="5ec74-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="5ec74-123">Apparaatgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="5ec74-123">Get device information</span></span>
<span data-ttu-id="5ec74-124">Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) biedt uitgebreide informatie over het apparaat in verschillende tabellen.</span><span class="sxs-lookup"><span data-stu-id="5ec74-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="5ec74-125">De tabel [DeviceInfo](advanced-hunting-deviceinfo-table.md) bevat bijvoorbeeld uitgebreide apparaatgegevens op basis van gebeurtenisgegevens die regelmatig worden samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="5ec74-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="5ec74-126">Deze query gebruikt de tabel om te controleren of een mogelijk gecompromitteerd gebruiker () zich heeft aangemeld op een apparaat en geeft vervolgens de waarschuwingen weer die op die apparaten `DeviceInfo` `<account-name>` zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="5ec74-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="5ec74-127">Deze query wordt `kind=inner` gebruikt om een [inner-join op](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)te geven, waarmee deduplicatie van linkerwaarden voor `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="5ec74-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="5ec74-128">Scenario's zoeken</span><span class="sxs-lookup"><span data-stu-id="5ec74-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="5ec74-129">Aanmeldingsactiviteiten van gebruikers die e-mailberichten hebben ontvangen die niet zijn gezaped</span><span class="sxs-lookup"><span data-stu-id="5ec74-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="5ec74-130">[Met Zero-hour Auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) worden schadelijke e-mailberichten na ontvangst geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="5ec74-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="5ec74-131">Als ZAP mislukt, kan schadelijke code uiteindelijk worden uitgevoerd op het apparaat en accounts gehackt laten.</span><span class="sxs-lookup"><span data-stu-id="5ec74-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="5ec74-132">Deze query controleert op aanmeldingsactiviteiten die zijn uitgevoerd door de geadresseerden van e-mailberichten die niet konden worden verwerkt door ZAP.</span><span class="sxs-lookup"><span data-stu-id="5ec74-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="5ec74-133">Aanmeldingspogingen krijgen van domeinaccounts die zijn gericht op diefstal van referenties</span><span class="sxs-lookup"><span data-stu-id="5ec74-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="5ec74-134">Met deze query worden eerst alle waarschuwingen voor toegang tot referenties in de tabel `AlertInfo` geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="5ec74-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="5ec74-135">Vervolgens wordt de tabel samengevoegd of samengevoegd, die wordt geparseert voor de namen van de gerichte accounts en filters voor accounts die aan een domein zijn `AlertEvidence` verbonden.</span><span class="sxs-lookup"><span data-stu-id="5ec74-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="5ec74-136">Ten slotte wordt de tabel gecontroleerd op alle aanmeldingsactiviteiten van `IdentityLogonEvents` de targeted-accounts die lid zijn van een domein.</span><span class="sxs-lookup"><span data-stu-id="5ec74-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="5ec74-137">Controleren of bestanden van een bekende kwaadwillende afzender op uw apparaten staan</span><span class="sxs-lookup"><span data-stu-id="5ec74-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="5ec74-138">Als u zeker weet dat er een e-mailadres is voor het verzenden van schadelijke bestanden ( ), kunt u deze query uitvoeren om te bepalen of de bestanden van deze afzender `MaliciousSender@example.com` op uw apparaten aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="5ec74-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="5ec74-139">U kunt deze query bijvoorbeeld gebruiken om apparaten te identificeren die worden beïnvloed door een malwaredistributiecampagne.</span><span class="sxs-lookup"><span data-stu-id="5ec74-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="5ec74-140">Aanmeldingspogingen na ontvangst van schadelijke e-mailberichten controleren</span><span class="sxs-lookup"><span data-stu-id="5ec74-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="5ec74-141">Deze query vindt de tien meest recente aanmeldingen die zijn uitgevoerd door e-mailontvangers binnen 30 minuten nadat ze bekende schadelijke e-mailberichten hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="5ec74-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="5ec74-142">U kunt deze query gebruiken om te controleren of de accounts van de geadresseerden van de e-mail zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="5ec74-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="5ec74-143">PowerShell-activiteiten controleren na ontvangst van e-mailberichten van bekende kwaadwillende afzenders</span><span class="sxs-lookup"><span data-stu-id="5ec74-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="5ec74-144">Schadelijke e-mailberichten bevatten vaak documenten en andere speciaal opgebouwde bijlagen die PowerShell-opdrachten uitvoeren om extra nettolading aan te leveren.</span><span class="sxs-lookup"><span data-stu-id="5ec74-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="5ec74-145">Als u op de hoogte bent van e-mailberichten afkomstig van een bekende kwaadwillende afzender (), kunt u deze query gebruiken om PowerShell-activiteiten te bekijken die zijn opgetreden binnen 30 minuten nadat een e-mailbericht van de afzender is `MaliciousSender@example.com` ontvangen.</span><span class="sxs-lookup"><span data-stu-id="5ec74-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="5ec74-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5ec74-146">Related topics</span></span>
- [<span data-ttu-id="5ec74-147">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="5ec74-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5ec74-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="5ec74-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5ec74-149">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="5ec74-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="5ec74-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="5ec74-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5ec74-151">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="5ec74-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5ec74-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="5ec74-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
