---
title: Waarden voor bulksgewijs klachtenniveau
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over BCL-waarden (Bulk Complaint Level) die worden gebruikt in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537941"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="c3027-103">Bulkklachtsniveau (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="c3027-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3027-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c3027-104">**Applies to**</span></span>
- [<span data-ttu-id="c3027-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c3027-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c3027-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c3027-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c3027-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3027-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c3027-108">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, wijst EOP een bulkklachtsniveau (BCL) toe aan binnenkomende berichten van bulkmailers.</span><span class="sxs-lookup"><span data-stu-id="c3027-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="c3027-109">De BCL wordt toegevoegd aan het bericht in een X-header en is vergelijkbaar met het betrouwbaarheidsniveau voor [spam (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten te identificeren als spam.</span><span class="sxs-lookup"><span data-stu-id="c3027-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c3027-110">Een hogere BCL geeft aan dat een bulkbericht meer kans heeft op het genereren van klachten (en dus waarschijnlijk spam is).</span><span class="sxs-lookup"><span data-stu-id="c3027-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c3027-111">Microsoft gebruikt interne en externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.</span><span class="sxs-lookup"><span data-stu-id="c3027-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="c3027-112">Bulkmailers variëren in hun verzendingspatronen, het maken van inhoud en het verkrijgen van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="c3027-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c3027-113">Goede bulkmailers verzenden gewenste berichten met relevante inhoud naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="c3027-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c3027-114">Deze berichten genereren weinig klachten van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="c3027-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c3027-115">Andere bulkmailers verzenden ongevraagde berichten die sterk lijken op spam en veel klachten van geadresseerden genereren.</span><span class="sxs-lookup"><span data-stu-id="c3027-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c3027-116">Berichten van een bulkmailer worden bulkmail of grijze e-mail genoemd.</span><span class="sxs-lookup"><span data-stu-id="c3027-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="c3027-117">Met spamfilters  worden berichten gemarkeerd als Bulk-e-mail op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en voert u de opgegeven actie uit voor het bericht (de standaardactie is om het bericht naar de map Ongewenste e-mail van de geadresseerde te sturen).</span><span class="sxs-lookup"><span data-stu-id="c3027-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c3027-118">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en Wat is het verschil tussen ongewenste e-mail en [bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c3027-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c3027-119">U kunt de lijst Tenant toestaan/blokkeren gebruiken om uitzonderingen voor bulkmailfilters te configureren.</span><span class="sxs-lookup"><span data-stu-id="c3027-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="c3027-120">Berichten van afzenders in de opgegeven domeinen ontvangen niet  de actie voor het bulksgewijs filteren van e-mail in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="c3027-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c3027-121">Zie De lijst Tenant [toestaan/blokkeren beheren](tenant-allow-block-list.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c3027-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="c3027-122">De BCL-drempelwaarden worden beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="c3027-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="c3027-123">BCL</span><span class="sxs-lookup"><span data-stu-id="c3027-123">BCL</span></span>|<span data-ttu-id="c3027-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c3027-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="c3027-125">0</span><span class="sxs-lookup"><span data-stu-id="c3027-125">0</span></span>|<span data-ttu-id="c3027-126">Het bericht is niet afkomstig van een bulksgewijs afzender.</span><span class="sxs-lookup"><span data-stu-id="c3027-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c3027-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c3027-127">1, 2, 3</span></span>|<span data-ttu-id="c3027-128">Het bericht is afkomstig van een bulksgewijs afzender die weinig klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="c3027-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c3027-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c3027-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="c3027-130">Het bericht is afkomstig van een bulksgewijs afzender die een gemengd aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="c3027-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c3027-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="c3027-131">8, 9</span></span>|<span data-ttu-id="c3027-132">Het bericht is afkomstig van een bulksgewijs afzender die een groot aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="c3027-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="c3027-133"><sup>\*</sup> Dit is de standaard drempelwaarde die wordt gebruikt in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="c3027-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
