---
title: Betrouwbaarheidsniveau van spam
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
description: Beheerders kunnen meer informatie krijgen over het betrouwbaarheidsniveau voor spam dat is toegepast op berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05faec8101bfb13265d3cca7c661f2e86ac21c8d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290403"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="2bc5c-103">Betrouwbaarheidsniveau voor ongewenste e-mail in EOP</span><span class="sxs-lookup"><span data-stu-id="2bc5c-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="2bc5c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2bc5c-104">**Applies to**</span></span>
- [<span data-ttu-id="2bc5c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2bc5c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2bc5c-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2bc5c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2bc5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bc5c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2bc5c-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken worden inkomende berichten in EOP door spamfilters heen geplaatst en krijgen ze een spamscore toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="2bc5c-109">Deze score wordt toegesneden op een individueel spamver vertrouwelijkheidsniveau dat is toegevoegd aan het bericht in een X-koptekst.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="2bc5c-110">Een hogere SCL geeft aan dat de kans groter is dat het om een bericht gaat om spam.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="2bc5c-111">EOP voert een actie uit op het bericht op basis van de SCL.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="2bc5c-112">Wat de SCL betekent en wat de standaardacties zijn die worden ondernomen op berichten, worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="2bc5c-113">Zie [Antispambeleid](configure-your-spam-filter-policies.md)configureren in EOP voor meer informatie over acties die u op berichten kunt uitvoeren op basis van het spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="2bc5c-114">SCL</span><span class="sxs-lookup"><span data-stu-id="2bc5c-114">SCL</span></span>|<span data-ttu-id="2bc5c-115">Definitie</span><span class="sxs-lookup"><span data-stu-id="2bc5c-115">Definition</span></span>|<span data-ttu-id="2bc5c-116">Standaardactie</span><span class="sxs-lookup"><span data-stu-id="2bc5c-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="2bc5c-117">-1</span><span class="sxs-lookup"><span data-stu-id="2bc5c-117">-1</span></span>|<span data-ttu-id="2bc5c-118">Het bericht heeft het spamfilter overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-118">The message skipped spam filtering.</span></span> <span data-ttu-id="2bc5c-119">Het bericht is bijvoorbeeld afkomstig van een veilige afzender, is verzonden naar een veilige geadresseerde of is afkomstig van een e-mailbronserver op de lijst met toegestane IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="2bc5c-120">Zie Lijsten met veilige [afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="2bc5c-121">Bezorg het bericht in het Postvak IN van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="2bc5c-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="2bc5c-122">0, 1</span></span>|<span data-ttu-id="2bc5c-123">Het filteren van ongewenste e-mail bepaalt dat het bericht geen spam is.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="2bc5c-124">Bezorg het bericht in het Postvak IN van de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="2bc5c-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="2bc5c-125">5, 6</span></span>|<span data-ttu-id="2bc5c-126">Spamfilter heeft het bericht gemarkeerd als **Spam**</span><span class="sxs-lookup"><span data-stu-id="2bc5c-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="2bc5c-127">Bezorg het bericht in de map Ongewenste e-mail van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="2bc5c-128">9</span><span class="sxs-lookup"><span data-stu-id="2bc5c-128">9</span></span>|<span data-ttu-id="2bc5c-129">Spamfilter heeft het bericht gemarkeerd als **zeer snelle spam**</span><span class="sxs-lookup"><span data-stu-id="2bc5c-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="2bc5c-130">Bezorg het bericht in de map Ongewenste e-mail van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="2bc5c-131">SCL 2, 3, 4, 7 en 8 worden niet gebruikt door spamfilters.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="2bc5c-132">U kunt regels voor de e-mailstroom (ook wel transportregels genoemd) gebruiken om de SCL op berichten te stempelen.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="2bc5c-133">Als u een regel voor de e-mailstroom gebruikt om de spamfilterregel in te stellen, activeren de waarden 5 of 6 de spamfilteractie voor **spam,** en activeren de waarden 7, 8 of 9 de spamfilteractie voor spam met hoge **betrouwbaarheid.**</span><span class="sxs-lookup"><span data-stu-id="2bc5c-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="2bc5c-134">Zie Regels voor de e-mailstroom gebruiken om het betrouwbaarheidsniveau voor ongewenste e-mail [in berichten in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="2bc5c-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="2bc5c-135">Net als bij de SCL identificeert het bulksgelaagde niveau (BCL) bad bulk-e-mail (ook wel _grijze e-mail genoemd)._</span><span class="sxs-lookup"><span data-stu-id="2bc5c-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="2bc5c-136">Een hogere BCL duidt op een bulk-e-mailbericht en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam).</span><span class="sxs-lookup"><span data-stu-id="2bc5c-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="2bc5c-137">U configureert de drempelwaarde voor BCL in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="2bc5c-138">Zie Antispambeleid configureren [in EOP,](configure-your-spam-filter-policies.md)bulksgewijs klachtniveau [(BCL) in EOP)](bulk-complaint-level-values.md)en wat is het verschil tussen ongewenste e-mail en [bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="2bc5c-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="2bc5c-139">![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nieuw voor Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="2bc5c-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="2bc5c-140">Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** aangeboden door LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
