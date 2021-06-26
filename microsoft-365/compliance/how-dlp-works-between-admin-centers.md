---
title: Hoe DLP werkt met & compliancecentrum & Exchange beheercentrum
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Meer informatie over hoe DLP in & compliancecentrum voor beveiliging werkt met DLP- en e-mailstroomregels (transportregels) in het Exchange beheercentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d71c45e5483bc73afbe2598415e30b84e97c2539
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149140"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="0a7b9-103">Hoe DLP werkt tussen het Microsoft 365 compliancecentrum en Exchange beheercentrum</span><span class="sxs-lookup"><span data-stu-id="0a7b9-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="0a7b9-104">In Microsoft 365 kunt u een DLP-beleid (Data Loss Prevention) maken in twee verschillende beheercentra:</span><span class="sxs-lookup"><span data-stu-id="0a7b9-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="0a7b9-105">In het **Microsoft 365 compliancecentrum** kunt u één DLP-beleid maken om inhoud in SharePoint, OneDrive, Exchange, Teams en nu Endpoint-apparaten te beschermen.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="0a7b9-106">U wordt aangeraden hier een DLP-beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="0a7b9-107">Zie Verwijzing naar preventie van [gegevensverlies voor meer informatie.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0a7b9-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="0a7b9-108">In het **Exchange beheercentrum** kunt u een DLP-beleid maken om inhoud alleen in de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="0a7b9-109">In dit beleid kunnen Exchange regels voor e-mailstroom (ook wel transportregels genoemd) gebruiken, zodat er meer specifieke opties zijn voor het verwerken van e-mail.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="0a7b9-110">Zie [DLP in het Exchange beheercentrum voor meer informatie.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="0a7b9-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="0a7b9-111">DLP-agenten die in deze beheercentra zijn gemaakt, werken naast elkaar: in dit onderwerp wordt uitgelegd hoe.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![DLP-pagina's in het beveiligings- en compliancecentrum en Exchange beheercentrum](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="0a7b9-113">Hoe DLP in het beveiligings- & compliancecentrum werkt met DLP- en e-mailstroomregels in het Exchange beheercentrum</span><span class="sxs-lookup"><span data-stu-id="0a7b9-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="0a7b9-114">Nadat u een DLP-beleid hebt opgesteld in het Beveiligings- & Compliancecentrum, wordt het beleid geïmplementeerd op alle locaties die in het beleid zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="0a7b9-115">Als het beleid Exchange Online, wordt het beleid daar gesynchroniseerd en afgedwongen op precies dezelfde manier als een DLP-beleid dat is gemaakt in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="0a7b9-116">Als u DLP-beleid hebt gemaakt in het Exchange-beheercentrum, blijven deze beleidsregels naast elk beleid voor e-mail werken dat u maakt in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="0a7b9-117">Houd er echter rekening mee dat regels die zijn gemaakt in het Exchange beheercentrum voorrang hebben.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="0a7b9-118">Alle Exchange e-mailstroomregels worden eerst verwerkt en vervolgens worden de DLP-regels van & compliancecentrum verwerkt.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="0a7b9-119">Dit betekent:</span><span class="sxs-lookup"><span data-stu-id="0a7b9-119">This means that:</span></span>
  
- <span data-ttu-id="0a7b9-120">Berichten die worden geblokkeerd door Exchange regels voor e-mailstroom, worden niet gescand door DLP-regels die zijn gemaakt in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="0a7b9-121">Als een Exchange-e-mailstroomregel een bericht zodanig wijzigt dat het voldoet aan een DLP-beleid in het beveiligings- &-compliancecentrum , zoals het toevoegen van externe gebruikers, wordt dit gedetecteerd door de DLP-regels en wordt het beleid zo nodig afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="0a7b9-122">Houd er ook rekening mee dat Exchange regels voor e-mailstroom die de actie Stoppen met verwerken gebruiken, geen invloed hebben op de verwerking van DLP-regels in het Beveiligings- & Compliancecentrum. Ze worden nog steeds verwerkt.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="0a7b9-123">Beleidstips in het beveiligings- & compliancecentrum versus het Exchange beheercentrum</span><span class="sxs-lookup"><span data-stu-id="0a7b9-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="0a7b9-124">Beleidstips kunnen werken met DLP-beleidsregels en e-mailstroomregels die zijn gemaakt in het Exchange-beheercentrum of met DLP-beleid dat is gemaakt in het Compliancecentrum voor beveiliging &, maar niet beide.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="0a7b9-125">Dit komt omdat deze beleidsregels op verschillende locaties worden opgeslagen, maar beleidstips kunnen slechts op één locatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="0a7b9-126">Als u beleidstips hebt geconfigureerd in het Exchange-beheercentrum, worden beleidstips die u configureert in het Compliancecentrum voor beveiliging & niet weergegeven voor gebruikers in webversie van Outlook en Outlook 2013 en hoger totdat u de tips in het Exchange-beheercentrum uit schakelen.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="0a7b9-127">Dit zorgt ervoor dat uw huidige Exchange e-mailstroomregels blijven werken totdat u ervoor kiest om over te schakelen naar het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="0a7b9-128">Hoewel beleidstips slechts vanaf één locatie kunnen worden gebruikt, worden er altijd e-mailmeldingen verzonden, zelfs als u DLP-beleid gebruikt in zowel het Compliancecentrum voor beveiliging & als het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
