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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6c758c05a64cd7ce84a2b021fe32f9e5ce5c1090
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431061"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="d0450-104">Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="d0450-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d0450-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d0450-105">**Applies to:**</span></span>
- <span data-ttu-id="d0450-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d0450-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d0450-107">Met de [geavanceerde jacht](advanced-hunting-overview.md) in Microsoft Threat Protection kunt u op verschillende manieren te zoeken naar bedreigingen voor:</span><span class="sxs-lookup"><span data-stu-id="d0450-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="d0450-108">Apparaten die worden beheerd met Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d0450-108">Devices managed by Microsoft Defender ATP</span></span>
- <span data-ttu-id="d0450-109">E-mailberichten die worden verwerkt door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0450-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="d0450-110">Cloud-app-activiteiten, verificatiegebeurtenissen en activiteiten van de domeincontroller die worden bijgehouden via de beveiliging van Microsoft Cloud-apps en Azure ATP</span><span class="sxs-lookup"><span data-stu-id="d0450-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Azure ATP</span></span>

<span data-ttu-id="d0450-111">Met dit niveau van de zichtbaarheid kunt u snel zoeken naar bedreigingen die door secties van uw netwerk bladeren, waaronder verfijnde indringers die aankomen via e-mail of het web, lokale bevoegdheden toevoegen, machtigingen voor domeinnamen</span><span class="sxs-lookup"><span data-stu-id="d0450-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="d0450-112">Hier volgen algemene technieken en voorbeelden van query's op basis van diverse jacht scenario's die u kunnen helpen om te ontdekken hoe u query's kunt maken wanneer u een nieuwe oplossing uitvoert voor dergelijke geavanceerde bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d0450-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="d0450-113">Gegevens voor entiteit weergeven</span><span class="sxs-lookup"><span data-stu-id="d0450-113">Get entity info</span></span>
<span data-ttu-id="d0450-114">Gebruik deze query's om te leren hoe u snel informatie kunt vinden over gebruikersaccounts, apparaten en bestanden.</span><span class="sxs-lookup"><span data-stu-id="d0450-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="d0450-115">Gebruikersaccounts van e-mailadressen verkrijgen</span><span class="sxs-lookup"><span data-stu-id="d0450-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="d0450-116">Wanneer u query's maakt [voor de tabellen die betrekking hebben op apparaten en e-mailberichten](advanced-hunting-schema-tables.md), moet u waarschijnlijk de naam van gebruikersaccounts verkrijgen via e-mailadressen van afzender of geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="d0450-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="d0450-117">U kunt dit algemeen doen voor geadresseerden of adressen van geadresseerden met behulp van de *lokale host* uit het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="d0450-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="d0450-118">In het onderstaande fragment wordt de functie [toString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto gebruikt om de lokale host te extraheren voordat de `@` e-mailadressen van de geadresseerden in de kolom worden weergegeven `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="d0450-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="d0450-119">In de volgende query ziet u hoe dit fragment kan worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="d0450-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="d0450-120">De tabel IdentityInfo samenvoegen</span><span class="sxs-lookup"><span data-stu-id="d0450-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="d0450-121">U kunt rekening namen en andere accountgegevens aanvragen door de [tabel IdentityInfo](advanced-hunting-identityinfo-table.md)samen te voegen of eraan deel te nemen.</span><span class="sxs-lookup"><span data-stu-id="d0450-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="d0450-122">De onderstaande query biedt de lijst met opsporings-en malware-detecties van de [tabel EmailEvents](advanced-hunting-emailevents-table.md) en voegt vervolgens deze informatie toe aan de `IdentityInfo` tabel voor gedetailleerde informatie over de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="d0450-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="d0450-123">Apparaatgegevens achterhalen</span><span class="sxs-lookup"><span data-stu-id="d0450-123">Get device information</span></span>
<span data-ttu-id="d0450-124">Het [geavanceerde jacht-schema](advanced-hunting-schema-tables.md) biedt uitgebreide informatie over apparaten in diverse tabellen.</span><span class="sxs-lookup"><span data-stu-id="d0450-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="d0450-125">De [tabel DeviceInfo](advanced-hunting-deviceinfo-table.md) bevat bijvoorbeeld uitgebreide informatie over apparaten op basis van de gebeurtenisgegevens die regelmatig zijn samengeteld.</span><span class="sxs-lookup"><span data-stu-id="d0450-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="d0450-126">Met deze query wordt de `DeviceInfo` tabel gebruikt om te controleren of een gebruiker met een risico gemanipuleerd ( `<account-name>` ) is aangemeld bij een willekeurige computer en welke waarschuwingen op die apparaten zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d0450-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="d0450-127">Met deze query wordt `kind=inner` een [inner join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)opgegeven waarmee ontdubbeling van de linkerkant van waarden wordt voorkomen `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="d0450-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="d0450-128">Jacht scenario's</span><span class="sxs-lookup"><span data-stu-id="d0450-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="d0450-129">Aanmeldings activiteiten vermelden van gebruikers die e-mails ontvangen die niet zijn zapped</span><span class="sxs-lookup"><span data-stu-id="d0450-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="d0450-130">[Zero-Hour auto leegmaak (ZAP)](../office-365-security/zero-hour-auto-purge.md) verstuurt kwaadwillende e-mailberichten nadat deze zijn ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d0450-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="d0450-131">Als ZAP mislukt, kan kwaadaardige code uiteindelijk op het apparaat worden uitgevoerd en kan de accounts worden beschadigd.</span><span class="sxs-lookup"><span data-stu-id="d0450-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="d0450-132">Met deze query wordt gecontroleerd of er een aanmeldingsactiviteit is uitgevoerd door de geadresseerden van e-mailberichten die niet zijn geadresseerd door ZAP.</span><span class="sxs-lookup"><span data-stu-id="d0450-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="d0450-133">Aanmeldingspogingen voor domeinaccounts met een referentie diefstal aanvragen</span><span class="sxs-lookup"><span data-stu-id="d0450-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="d0450-134">Met deze query worden eerst alle waarschuwingen voor toegangsrechten voor referenties in de `AlertInfo` tabel aangeduid.</span><span class="sxs-lookup"><span data-stu-id="d0450-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="d0450-135">De tabel wordt vervolgens samengevoegd of samengevoegd `AlertEvidence` , die wordt geparseerd voor de namen van de gerichte accounts en filters voor accounts die lid zijn van een domein.</span><span class="sxs-lookup"><span data-stu-id="d0450-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="d0450-136">Ten slotte wordt de `IdentityLogonEvents` tabel gecontroleerd op alle aanmeldings activiteiten van de domeinnaam gerichte accounts.</span><span class="sxs-lookup"><span data-stu-id="d0450-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="d0450-137">Controleren of bestanden van een bekende, schadelijke afzender op uw apparaten staan</span><span class="sxs-lookup"><span data-stu-id="d0450-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="d0450-138">Ervan uitgaand dat u bekend bent met een e-mailadres dat u schadelijke bestanden verzendt ( `MaliciousSender@example.com` ), kunt u deze query uitvoeren om te bepalen of bestanden van deze afzender bestaan op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="d0450-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="d0450-139">U kunt deze query bijvoorbeeld gebruiken om apparaten aan te geven die worden beïnvloed door een malware-distributie campagne.</span><span class="sxs-lookup"><span data-stu-id="d0450-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="d0450-140">Aanmeldingspogingen nakijken na ontvangst van kwaadaardige e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="d0450-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="d0450-141">Met deze query vindt u de tien meest recente aanmeldingen van e-mail geadresseerden binnen 30 minuten nadat ze bekende, schadelijke e-mails hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d0450-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="d0450-142">U kunt deze query gebruiken om te controleren of de accounts van de geadresseerden van het e-mailbericht zijn aangetast.</span><span class="sxs-lookup"><span data-stu-id="d0450-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="d0450-143">PowerShell-activiteiten nakijken na ontvangst van e-mailberichten van bekende schadelijke afzender</span><span class="sxs-lookup"><span data-stu-id="d0450-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="d0450-144">Kwaadwillende e-mailberichten bevatten vaak documenten en andere speciaal vervaardigde bijlagen die PowerShell-opdrachten uitvoeren voor het leveren van extra nettoladingen.</span><span class="sxs-lookup"><span data-stu-id="d0450-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="d0450-145">Als u op de hoogte bent van e-mailberichten die afkomstig zijn van een bekende, schadelijke afzender ( `MaliciousSender@example.com` ), kunt u deze query gebruiken om PowerShell-activiteiten weer te geven en te controleren die binnen 30 minuten zijn opgetreden nadat een e-mailbericht van de afzender is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d0450-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="d0450-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d0450-146">Related topics</span></span>
- [<span data-ttu-id="d0450-147">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="d0450-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0450-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d0450-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0450-149">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="d0450-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d0450-150">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="d0450-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d0450-151">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="d0450-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d0450-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="d0450-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
