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
ms.openlocfilehash: ec7f9083401fdf7a2114d99ddd2dcc009411e34b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633505"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="69a89-104">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="69a89-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="69a89-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="69a89-105">**Applies to:**</span></span>
- <span data-ttu-id="69a89-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69a89-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="69a89-107">[Geavanceerde jacht](advanced-hunting-overview.md) in Microsoft Threat Protection stelt u in staat om proactief te jagen op bedreigingen op uw Windows-apparaten en Microsoft-e-mails.</span><span class="sxs-lookup"><span data-stu-id="69a89-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Microsoft emails.</span></span> <span data-ttu-id="69a89-108">Hier volgen enkele jachtscenario's en voorbeeldquery's die u kunnen helpen te onderzoeken hoe u query's maken voor zowel apparaten als e-mails.</span><span class="sxs-lookup"><span data-stu-id="69a89-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="69a89-109">Gebruikersaccounts verkrijgen via e-mailadressen</span><span class="sxs-lookup"><span data-stu-id="69a89-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="69a89-110">Wanneer u query's maakt in [tabellen die apparaten en e-mails behandelen,](advanced-hunting-schema-tables.md)moet u waarschijnlijk gebruikersaccountnamen verkrijgen van e-mailadressen van afzender of ontvanger.</span><span class="sxs-lookup"><span data-stu-id="69a89-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="69a89-111">Gebruik hiervoor de lokale host vanaf het *e-mailadres:*</span><span class="sxs-lookup"><span data-stu-id="69a89-111">To do this use the *local-host* from the email address:</span></span>

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="69a89-112">Deze normalisatietechniek wordt gebruikt in de volgende scenario's.</span><span class="sxs-lookup"><span data-stu-id="69a89-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="69a89-113">Jachtscenario's</span><span class="sxs-lookup"><span data-stu-id="69a89-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="69a89-114">Controleren of bestanden van een bekende afzender op uw apparaten staan</span><span class="sxs-lookup"><span data-stu-id="69a89-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="69a89-115">Ervan uitgaande dat u weet van een e-mailadres dat schadelijke bestanden verzendt, u deze query uitvoeren om te bepalen of er bestanden van deze afzender op uw apparaten bestaan.</span><span class="sxs-lookup"><span data-stu-id="69a89-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="69a89-116">U deze query bijvoorbeeld gebruiken om het aantal apparaten te bepalen dat wordt beïnvloed door een malwaredistributiecampagne.</span><span class="sxs-lookup"><span data-stu-id="69a89-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="69a89-117">Inlogpogingen bekijken na ontvangst van kwaadaardige e-mails</span><span class="sxs-lookup"><span data-stu-id="69a89-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="69a89-118">Deze query vindt de 10 laatste logons uitgevoerd door e-mail ontvangers binnen 30 minuten nadat ze bekende kwaadaardige e-mails ontvangen.</span><span class="sxs-lookup"><span data-stu-id="69a89-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="69a89-119">U deze query gebruiken om te controleren of de accounts van de e-mailontvangers zijn gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="69a89-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="69a89-120">PowerShell-activiteiten bekijken na ontvangst van e-mails van bekende kwaadwillende afzender</span><span class="sxs-lookup"><span data-stu-id="69a89-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="69a89-121">Schadelijke e-mails bevatten vaak documenten en andere speciaal vervaardigde bijlagen die PowerShell-opdrachten uitvoeren om extra payloads te leveren.</span><span class="sxs-lookup"><span data-stu-id="69a89-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="69a89-122">Als u op de hoogte bent van e-mails van een bekende afzender, u deze query gebruiken om PowerShell-activiteiten aan te geven en te bekijken die zich binnen 30 minuten nadat een e-mail van de afzender was ontvangen.</span><span class="sxs-lookup"><span data-stu-id="69a89-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="69a89-123">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="69a89-123">Related topics</span></span>
- [<span data-ttu-id="69a89-124">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="69a89-124">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="69a89-125">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="69a89-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="69a89-126">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="69a89-126">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="69a89-127">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="69a89-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="69a89-128">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="69a89-128">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="69a89-129">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="69a89-129">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
