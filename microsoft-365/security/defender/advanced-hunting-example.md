---
title: Geavanceerd voorbeeld van jagen voor Microsoft Defender voor Office 365
description: Aan de slag met het zoeken naar e-mailbedreigingen met behulp van geavanceerde zoekactie
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965142"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="6faa0-104">Geavanceerd voorbeeld van jagen voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6faa0-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6faa0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6faa0-105">**Applies to:**</span></span>
- <span data-ttu-id="6faa0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6faa0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6faa0-107">Wil je aan de slag met het zoeken naar e-maildreigingen met geavanceerde opsporing?</span><span class="sxs-lookup"><span data-stu-id="6faa0-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="6faa0-108">Probeer dit:</span><span class="sxs-lookup"><span data-stu-id="6faa0-108">Try this:</span></span>

<span data-ttu-id="6faa0-109">De sectie [Aan de slag](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) van het [Artikel over Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) heeft logische vroege configuratiesegmenten die er als volgt uitzien:</span><span class="sxs-lookup"><span data-stu-id="6faa0-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="6faa0-110">Configureer alles met 'Anti' in de naam.</span><span class="sxs-lookup"><span data-stu-id="6faa0-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="6faa0-111">Anti-malware</span><span class="sxs-lookup"><span data-stu-id="6faa0-111">Anti-malware</span></span>
   - <span data-ttu-id="6faa0-112">Anti-phishing</span><span class="sxs-lookup"><span data-stu-id="6faa0-112">Anti-phishing</span></span>
   - <span data-ttu-id="6faa0-113">Antispam</span><span class="sxs-lookup"><span data-stu-id="6faa0-113">Anti-spam</span></span>
2. <span data-ttu-id="6faa0-114">Stel alles in met 'Safe' in de naam.</span><span class="sxs-lookup"><span data-stu-id="6faa0-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="6faa0-115">Veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="6faa0-115">Safe Links</span></span>
   - <span data-ttu-id="6faa0-116">Veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="6faa0-116">Safe Attachments</span></span>
3. <span data-ttu-id="6faa0-117">De werkbelastingen verdedigen (bijv.</span><span class="sxs-lookup"><span data-stu-id="6faa0-117">Defend the workloads (ex.</span></span> <span data-ttu-id="6faa0-118">SharePoint Online, OneDrive en Teams).</span><span class="sxs-lookup"><span data-stu-id="6faa0-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="6faa0-119">Beveiligen met auto purge van nul uur.</span><span class="sxs-lookup"><span data-stu-id="6faa0-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="6faa0-120">Samen met de [snelkoppeling](../office-365-security/protect-against-threats.md) om meteen aan de slag te gaan en start de configuratie op Dag 1.</span><span class="sxs-lookup"><span data-stu-id="6faa0-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="6faa0-121">De laatste stap in **Aan de slag** is de bescherming van gebruikers met **Zero-Hour Auto Purge**, ook bekend als ZAP.</span><span class="sxs-lookup"><span data-stu-id="6faa0-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="6faa0-122">Het kan heel belangrijk zijn om te weten of jouw inspanningen om verdachte of schadelijke e-mail te zappen na levering succesvol waren of niet.</span><span class="sxs-lookup"><span data-stu-id="6faa0-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="6faa0-123">Een belangrijk voordeel van het samenvoegen van deze twee beveiligingscentra is snelle navigatie naar Kusto querytaal om problemen op te sporen.</span><span class="sxs-lookup"><span data-stu-id="6faa0-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="6faa0-124">Beveiligingsteams kunnen ZAP-missers controleren door hun volgende [stappen](https://security.microsoft.com/advanced-hunting)hier onder **Geavanceerd** jagen \> **te volgen.**</span><span class="sxs-lookup"><span data-stu-id="6faa0-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="6faa0-125">Klik op de pagina Geavanceerd zoeken op **Query.**</span><span class="sxs-lookup"><span data-stu-id="6faa0-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="6faa0-126">Kopieer de query onderaan naar het queryvenster.</span><span class="sxs-lookup"><span data-stu-id="6faa0-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="6faa0-127">Selecteer **Query uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="6faa0-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="De pagina Geavanceerd zoeken (onder Jagen) met Query geselecteerd boven aan het queryvenster en het uitvoeren van een Kusto-query om ZAP-acties in de afgelopen 7 dagen vast te leggen.":::

<span data-ttu-id="6faa0-129">De gegevens van deze query zullen in het resultatenvenster onder de query zelf zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="6faa0-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="6faa0-130">Resultaten bevatten informatie zoal 'DeviceName', 'AccountDisplayName' en 'ZapTime' in een resultatenset die kan aangepast worden.</span><span class="sxs-lookup"><span data-stu-id="6faa0-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="6faa0-131">Resultaten kunnen geëxporteerd worden voor het archief.</span><span class="sxs-lookup"><span data-stu-id="6faa0-131">Results can also be exported for your records.</span></span> <span data-ttu-id="6faa0-132">Als het om een query gaat die je later opnieuw nodig zult hebben, selecteer dan **Opslaan** > **Opslaan als** en voeg de query toe aan de lijst van query's, gedeeld of community query's.</span><span class="sxs-lookup"><span data-stu-id="6faa0-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="6faa0-133">Gerelateerde informatie</span><span class="sxs-lookup"><span data-stu-id="6faa0-133">Related information</span></span>
- [<span data-ttu-id="6faa0-134">Geavanceerde best practices voor jagen</span><span class="sxs-lookup"><span data-stu-id="6faa0-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6faa0-135">Overzicht - Geavanceerd zoeken</span><span class="sxs-lookup"><span data-stu-id="6faa0-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
