---
title: Op bedreigingen zoeken op verschillende apparaten, e-mailberichten, apps en identiteiten met geavanceerde jacht
description: Bestudeer veelvoorkomende scenario's en voorbeeldquery's die betrekking hebben op apparaten, e-mailberichten, apps en identiteiten.
keywords: geavanceerde zoekactie, Office365-gegevens, Windows-apparaten, Office365-e-mailberichten normaliseren, e-mails, apps, identiteiten, bedreigingsjacht, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: a12b2dcf2de472f43e782e2064944ec774bdb9e1
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727257"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="d4392-104">Op bedreigingen zoeken op verschillende apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="d4392-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4392-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d4392-105">**Applies to:**</span></span>
- <span data-ttu-id="d4392-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4392-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d4392-107">[Met geavanceerd zoeken](advanced-hunting-overview.md) in Microsoft 365 Defender kunt u proactief op bedreigingen zoeken:</span><span class="sxs-lookup"><span data-stu-id="d4392-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="d4392-108">Apparaten die worden beheerd door Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d4392-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d4392-109">E-mailberichten die zijn verwerkt door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4392-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="d4392-110">Activiteiten in cloud-apps, verificatiegebeurtenissen en domeincontrolleractiviteiten die worden bijgespoord door Microsoft Cloud App Security en Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="d4392-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="d4392-111">Met dit niveau van zichtbaarheid kunt u snel zoeken naar bedreigingen die door secties van uw netwerk lopen, zoals geavanceerde inbraken die binnenkomen op e-mail of internet, lokale bevoegdheden verhogen, geprivilegieerde domeinreferenties verkrijgen en lateraal naar uw apparaten gaan.</span><span class="sxs-lookup"><span data-stu-id="d4392-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="d4392-112">Hier vindt u algemene technieken en voorbeeldquery's op basis van verschillende scenario's waarmee u kunt onderzoeken hoe u query's kunt maken wanneer u op dergelijke geavanceerde bedreigingen jaagt.</span><span class="sxs-lookup"><span data-stu-id="d4392-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="d4392-113">Entiteitsgegevens krijgen</span><span class="sxs-lookup"><span data-stu-id="d4392-113">Get entity info</span></span>
<span data-ttu-id="d4392-114">Gebruik deze query's om te leren hoe u snel informatie kunt krijgen over gebruikersaccounts, apparaten en bestanden.</span><span class="sxs-lookup"><span data-stu-id="d4392-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="d4392-115">Gebruikersaccounts verkrijgen van e-mailadressen</span><span class="sxs-lookup"><span data-stu-id="d4392-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="d4392-116">Bij het maken van query's in tabellen die betrekking hebben op [apparaten](advanced-hunting-schema-tables.md)en e-mailberichten, moet u waarschijnlijk gebruikersaccountnamen verkrijgen van e-mailadressen van afzenders of geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="d4392-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="d4392-117">U kunt dit in het algemeen doen voor geadresseerde of afzender met behulp van de lokale host vanaf het *e-mailadres.*</span><span class="sxs-lookup"><span data-stu-id="d4392-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="d4392-118">In het onderstaande fragment gebruiken we de [functie tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto om de lokale host direct vóór de e-mailadressen van geadresseerden in de kolom `@` op te `RecipientEmailAddress` halen.</span><span class="sxs-lookup"><span data-stu-id="d4392-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="d4392-119">In de onderstaande query ziet u hoe dit fragment kan worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="d4392-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="d4392-120">De tabel IdentityInfo samenvoegen</span><span class="sxs-lookup"><span data-stu-id="d4392-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="d4392-121">U kunt accountnamen en andere accountgegevens verkrijgen door de tabel [IdentityInfo samen](advanced-hunting-identityinfo-table.md)te voegen of aan te sluiten.</span><span class="sxs-lookup"><span data-stu-id="d4392-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="d4392-122">In de onderstaande query wordt de lijst met phishing- en malwaredetecties uit de tabel [EmailEvents](advanced-hunting-emailevents-table.md) opgevraagd en wordt deze informatie toegevoegd aan de tabel voor gedetailleerde informatie `IdentityInfo` over elke geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="d4392-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="d4392-123">Apparaatgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="d4392-123">Get device information</span></span>
<span data-ttu-id="d4392-124">Het [geavanceerde schema voor jagen](advanced-hunting-schema-tables.md) bevat uitgebreide apparaatinformatie in verschillende tabellen.</span><span class="sxs-lookup"><span data-stu-id="d4392-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="d4392-125">De tabel [DeviceInfo](advanced-hunting-deviceinfo-table.md) bevat bijvoorbeeld uitgebreide apparaatgegevens op basis van gebeurtenisgegevens die regelmatig worden samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="d4392-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="d4392-126">In deze query wordt de tabel gebruikt om te controleren of een mogelijk gecompromitteerde gebruiker () zich heeft aangemeld bij apparaten en worden vervolgens de waarschuwingen vermeld die op die apparaten `DeviceInfo` `<account-name>` zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d4392-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="d4392-127">Deze query wordt `kind=inner` gebruikt om een [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)op te geven, waarmee deduplicatie van waarden aan de linkerkant voor wordt `DeviceId` voorkomen.</span><span class="sxs-lookup"><span data-stu-id="d4392-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="d4392-128">Scenario's voor jagen</span><span class="sxs-lookup"><span data-stu-id="d4392-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="d4392-129">Aanmeldingsactiviteiten lijst van gebruikers die e-mailberichten hebben ontvangen die niet zijn gezapeerd</span><span class="sxs-lookup"><span data-stu-id="d4392-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="d4392-130">[Zap (Zero Hour Auto Purge)](../office-365-security/zero-hour-auto-purge.md) adresseert schadelijke e-mailberichten nadat ze zijn ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d4392-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="d4392-131">Als ZAP mislukt, kan schadelijke code uiteindelijk worden uitgevoerd op het apparaat en accounts in gevaar brengen.</span><span class="sxs-lookup"><span data-stu-id="d4392-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="d4392-132">Met deze query wordt gecontroleerd op aanmeldingsactiviteit die is uitgevoerd door de geadresseerden van e-mailberichten die niet zijn geadresseerd door ZAP.</span><span class="sxs-lookup"><span data-stu-id="d4392-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="d4392-133">Aanmeldingspogingen krijgen van domeinaccounts die zijn gericht op diefstal van referenties</span><span class="sxs-lookup"><span data-stu-id="d4392-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="d4392-134">Met deze query worden eerst alle waarschuwingen voor toegang tot referenties in de `AlertInfo` tabel geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="d4392-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="d4392-135">Vervolgens wordt de tabel samengevoegd of samengevoegd, die alleen wordt geparseert voor de namen van de doelaccounts en filters voor accounts met een `AlertEvidence` domein.</span><span class="sxs-lookup"><span data-stu-id="d4392-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="d4392-136">Ten slotte wordt de tabel gecontroleerd om alle aanmeldingsactiviteiten van de met het domein verbonden `IdentityLogonEvents` gerichte accounts op te halen.</span><span class="sxs-lookup"><span data-stu-id="d4392-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="d4392-137">Controleren of bestanden van een bekende kwaadwillende afzender zich op uw apparaten</span><span class="sxs-lookup"><span data-stu-id="d4392-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="d4392-138">Ervan uitgaande dat u op de hoogte bent van een e-mailadres dat schadelijke bestanden () verstuurt, kunt u deze query uitvoeren om te bepalen of er bestanden van deze afzender op `MaliciousSender@example.com` uw apparaten aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="d4392-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="d4392-139">U kunt deze query bijvoorbeeld gebruiken om apparaten te identificeren die zijn beïnvloed door een malwaredistributiecampagne.</span><span class="sxs-lookup"><span data-stu-id="d4392-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="d4392-140">Aanmeldingspogingen controleren na ontvangst van schadelijke e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="d4392-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="d4392-141">Met deze query worden de tien meest recente aanmeldingen gevonden die zijn uitgevoerd door e-mailontvangers binnen 30 minuten nadat ze bekende schadelijke e-mailberichten hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d4392-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="d4392-142">U kunt deze query gebruiken om te controleren of de accounts van de e-mailontvangers zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="d4392-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="d4392-143">PowerShell-activiteiten controleren na ontvangst van e-mailberichten van bekende kwaadwillende afzender</span><span class="sxs-lookup"><span data-stu-id="d4392-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="d4392-144">Schadelijke e-mailberichten bevatten vaak documenten en andere speciaal ontworpen bijlagen die PowerShell-opdrachten uitvoeren om extra laadvermogen te leveren.</span><span class="sxs-lookup"><span data-stu-id="d4392-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="d4392-145">Als u op de hoogte bent van e-mailberichten die afkomstig zijn van een bekende kwaadwillende afzender (), kunt u deze query gebruiken om PowerShell-activiteiten op te nemen en te bekijken die binnen 30 minuten na ontvangst van een e-mailbericht van de afzender hebben `MaliciousSender@example.com` plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="d4392-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="d4392-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d4392-146">Related topics</span></span>
- [<span data-ttu-id="d4392-147">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="d4392-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d4392-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d4392-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d4392-149">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="d4392-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d4392-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="d4392-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d4392-151">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="d4392-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d4392-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="d4392-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
