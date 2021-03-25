---
title: Betrouwbaarheidsniveau voor spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over het betrouwbaarheidsniveau voor spam (SCL) dat is toegepast op berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204056"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="9a395-103">Betrouwbaarheidsniveau voor spam (SCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="9a395-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="9a395-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="9a395-104">**Applies to**</span></span>
- [<span data-ttu-id="9a395-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9a395-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9a395-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9a395-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9a395-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a395-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9a395-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, worden binnenkomende berichten via spamfilters in EOP gefilterd en krijgen ze een spamscore toegewezen.</span><span class="sxs-lookup"><span data-stu-id="9a395-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="9a395-109">Die score wordt in kaart gebracht aan een individueel betrouwbaarheidsniveau voor spam (SCL) dat wordt toegevoegd aan het bericht in een X-header.</span><span class="sxs-lookup"><span data-stu-id="9a395-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="9a395-110">Een hogere SCL geeft aan dat een bericht waarschijnlijker spam is.</span><span class="sxs-lookup"><span data-stu-id="9a395-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="9a395-111">EOP onderneemt actie op basis van het bericht op basis van de SCL.</span><span class="sxs-lookup"><span data-stu-id="9a395-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="9a395-112">Wat de SCL betekent en de standaardacties die worden ondernomen op berichten, worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="9a395-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="9a395-113">Zie Antispambeleid configureren in EOP voor meer informatie over acties die u kunt uitvoeren op berichten op basis van de uitspraak over [spamfilters.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9a395-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="9a395-114">SCL</span><span class="sxs-lookup"><span data-stu-id="9a395-114">SCL</span></span>|<span data-ttu-id="9a395-115">Definitie</span><span class="sxs-lookup"><span data-stu-id="9a395-115">Definition</span></span>|<span data-ttu-id="9a395-116">Standaardactie</span><span class="sxs-lookup"><span data-stu-id="9a395-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="9a395-117">-1</span><span class="sxs-lookup"><span data-stu-id="9a395-117">-1</span></span>|<span data-ttu-id="9a395-118">Het bericht heeft spamfilters overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="9a395-118">The message skipped spam filtering.</span></span> <span data-ttu-id="9a395-119">Het bericht is bijvoorbeeld afkomstig van een veilige afzender, is verzonden naar een veilige geadresseerde of is afkomstig van een e-mailbronserver in de LIJST MET TOESTAAN VAN IP.</span><span class="sxs-lookup"><span data-stu-id="9a395-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="9a395-120">Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9a395-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="9a395-121">Bezorg het bericht in het Postvak IN van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="9a395-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="9a395-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="9a395-122">0, 1</span></span>|<span data-ttu-id="9a395-123">Spamfilters hebben vastgesteld dat het bericht geen spam was.</span><span class="sxs-lookup"><span data-stu-id="9a395-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="9a395-124">Bezorg het bericht in het Postvak IN van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="9a395-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="9a395-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="9a395-125">5, 6</span></span>|<span data-ttu-id="9a395-126">Spamfilters hebben het bericht gemarkeerd als **Spam**</span><span class="sxs-lookup"><span data-stu-id="9a395-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="9a395-127">Bezorg het bericht bij de map Ongewenste e-mail van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="9a395-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="9a395-128">9</span><span class="sxs-lookup"><span data-stu-id="9a395-128">9</span></span>|<span data-ttu-id="9a395-129">Spamfilters hebben het bericht gemarkeerd als **spam met hoge betrouwbaarheid**</span><span class="sxs-lookup"><span data-stu-id="9a395-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="9a395-130">Bezorg het bericht bij de map Ongewenste e-mail van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="9a395-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="9a395-131">U ziet dat SCL 2, 3, 4, 7 en 8 niet worden gebruikt door spamfilters.</span><span class="sxs-lookup"><span data-stu-id="9a395-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="9a395-132">U kunt e-mailstroomregels (ook wel transportregels genoemd) gebruiken om de SCL op berichten te stempelen.</span><span class="sxs-lookup"><span data-stu-id="9a395-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="9a395-133">Als u een regel voor de e-mailstroom gebruikt om de SCL in te stellen, worden met de waarden 5 of 6 de actie spamfilters voor **Spam** in gang gezet en worden de waarden 7, 8 of 9 de actie voor het filteren van spam met hoge betrouwbaarheid **ingesteld.**</span><span class="sxs-lookup"><span data-stu-id="9a395-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="9a395-134">Zie Regels voor e-mailstroom gebruiken om het betrouwbaarheidsniveau voor [spam (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)in berichten in te stellen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a395-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="9a395-135">Net als bij de SCL identificeert het bulkklachtsniveau (BCL) slechte bulk-e-mail (ook wel _grijze e-mail genoemd)._</span><span class="sxs-lookup"><span data-stu-id="9a395-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="9a395-136">Een hogere BCL duidt op een bulk-e-mailbericht en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam).</span><span class="sxs-lookup"><span data-stu-id="9a395-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="9a395-137">U configureert de BCL-drempel in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="9a395-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="9a395-138">Zie Antispambeleid configureren in EOP , Bulk [complaint level (BCL) in EOP)](bulk-complaint-level-values.md)en Wat is het verschil tussen ongewenste [e-mail](configure-your-spam-filter-policies.md)en [bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9a395-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="9a395-139">![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="9a395-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="9a395-140">Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** aangeboden door LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="9a395-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
