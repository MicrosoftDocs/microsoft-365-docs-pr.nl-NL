---
title: Vertrouwensniveaus voor spam
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Wanneer een e-mailbericht via spamfiltering gaat, krijgt het een spamscore toegewezen. Die score is in kaart gebracht aan een individuele Spam Confidence Level (SCL) rating en gestempeld in een X-header. De dienst onderneemt acties op de berichten, afhankelijk van de spam vertrouwen interpretatie van de SCL rating. In de volgende tabel ziet u hoe de verschillende SCL-classificaties worden geïnterpreteerd door de filters en de standaardactie die wordt uitgevoerd op binnenkomende berichten voor elke beoordeling.
ms.openlocfilehash: 65b6f51199e6d8f6ce17a05b28c5bad15d9d1760
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810443"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="1933a-106">Vertrouwensniveaus voor spam</span><span class="sxs-lookup"><span data-stu-id="1933a-106">Spam confidence levels</span></span>

<span data-ttu-id="1933a-107">Wanneer een e-mailbericht via spamfiltering gaat, krijgt het een spamscore toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1933a-107">When an email message goes through spam filtering it is assigned a spam score.</span></span> <span data-ttu-id="1933a-108">Die score is in kaart gebracht aan een individuele Spam Confidence Level (SCL) rating en gestempeld in een X-header.</span><span class="sxs-lookup"><span data-stu-id="1933a-108">That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header.</span></span> <span data-ttu-id="1933a-109">De dienst onderneemt acties op de berichten, afhankelijk van de spam vertrouwen interpretatie van de SCL rating.</span><span class="sxs-lookup"><span data-stu-id="1933a-109">The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating.</span></span> <span data-ttu-id="1933a-110">In de volgende tabel ziet u hoe de verschillende SCL-classificaties worden geïnterpreteerd door de filters en de standaardactie die wordt uitgevoerd op binnenkomende berichten voor elke beoordeling.</span><span class="sxs-lookup"><span data-stu-id="1933a-110">The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="1933a-111">**SCL-beoordeling**</span><span class="sxs-lookup"><span data-stu-id="1933a-111">**SCL Rating**</span></span>|<span data-ttu-id="1933a-112">**Spam vertrouwen interpretatie**</span><span class="sxs-lookup"><span data-stu-id="1933a-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="1933a-113">**Standaardactie**</span><span class="sxs-lookup"><span data-stu-id="1933a-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1933a-114">-1</span><span class="sxs-lookup"><span data-stu-id="1933a-114">-1</span></span>|<span data-ttu-id="1933a-115">Niet-spam afkomstig van een veilige afzender, veilige ontvanger of veilig vermeld IP-adres (vertrouwde partner).</span><span class="sxs-lookup"><span data-stu-id="1933a-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="1933a-116">Lever het bericht af bij het postvak IN van de ontvangers.</span><span class="sxs-lookup"><span data-stu-id="1933a-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="1933a-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="1933a-117">0, 1</span></span>|<span data-ttu-id="1933a-118">Niet-spam omdat het bericht is gescand en bepaald om schoon te zijn.</span><span class="sxs-lookup"><span data-stu-id="1933a-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="1933a-119">Lever het bericht af bij het postvak IN van de ontvangers.</span><span class="sxs-lookup"><span data-stu-id="1933a-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="1933a-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="1933a-120">5, 6</span></span>|<span data-ttu-id="1933a-121">Spam</span><span class="sxs-lookup"><span data-stu-id="1933a-121">Spam</span></span>|<span data-ttu-id="1933a-122">Lever het bericht af op de map Ongewenste e-mail van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="1933a-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="1933a-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="1933a-123">7, 8, 9</span></span>|<span data-ttu-id="1933a-124">Hoog vertrouwen spam</span><span class="sxs-lookup"><span data-stu-id="1933a-124">High confidence spam</span></span>|<span data-ttu-id="1933a-125">Lever het bericht af op de map Ongewenste e-mail van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="1933a-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="1933a-126">SCL ratings van 2, 3, 4, 7 en 8 worden niet vastgesteld door de service.</span><span class="sxs-lookup"><span data-stu-id="1933a-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="1933a-127">Een SCL rating van 5 of 6 wordt beschouwd als vermoedelijke spam, die minder zeker spam dan een SCL rating van 9, die wordt beschouwd als bepaalde spam.</span><span class="sxs-lookup"><span data-stu-id="1933a-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="1933a-128">Verschillende acties voor spam en spam met een hoog vertrouwen kunnen worden geconfigureerd via uw beleid voor inhoudsfilter in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1933a-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="1933a-129">Zie [Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1933a-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="1933a-130">U ook de SCL-classificatie instellen voor berichten die overeenkomen met specifieke voorwaarden met behulp van e-mailstroomregels (ook wel transportregels genoemd), zoals beschreven in regels voor [de stroomstroom gebruiken om het spamvertrouwenniveau (SCL) in berichten in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="1933a-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="1933a-131">Als u een e-mailstroomregel gebruikt om SCL van 7, 8 of 9 in te stellen, wordt het bericht behandeld als spam met een hoog vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="1933a-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="1933a-132">![Het korte pictogram voor](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **Nieuw in Office 365?**</span><span class="sxs-lookup"><span data-stu-id="1933a-132">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span>         <span data-ttu-id="1933a-133">Ontdek gratis videocursussen voor **Office 365-beheerders en IT-professionals**, aangeboden via LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="1933a-133">Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

