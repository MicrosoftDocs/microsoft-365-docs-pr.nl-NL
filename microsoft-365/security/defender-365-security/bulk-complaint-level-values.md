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
description: Beheerders kunnen meer informatie krijgen over BCL-waarden (Bulk Compliance Level) die worden gebruikt in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058982"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="04dcd-103">Bulkklachtsniveau (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="04dcd-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04dcd-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="04dcd-104">**Applies to**</span></span>
- [<span data-ttu-id="04dcd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04dcd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04dcd-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="04dcd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04dcd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04dcd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="04dcd-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, wijst EOP een bulksgewijs compatibel niveau (BCL) toe aan binnenkomende berichten van bulkmailers.</span><span class="sxs-lookup"><span data-stu-id="04dcd-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="04dcd-109">De BCL wordt toegevoegd aan het bericht in een X-header en is vergelijkbaar met het betrouwbaarheidsniveau voor [spam (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten te identificeren als spam.</span><span class="sxs-lookup"><span data-stu-id="04dcd-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="04dcd-110">Een hogere BCL geeft aan dat een bulkbericht meer kans heeft op het genereren van klachten (en dus waarschijnlijk spam is).</span><span class="sxs-lookup"><span data-stu-id="04dcd-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="04dcd-111">Microsoft gebruikt interne en externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.</span><span class="sxs-lookup"><span data-stu-id="04dcd-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="04dcd-112">Bulkmailers variëren in hun verzendingspatronen, het maken van inhoud en het verkrijgen van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="04dcd-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="04dcd-113">Goede bulkmailers verzenden gewenste berichten met relevante inhoud naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="04dcd-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="04dcd-114">Deze berichten genereren weinig klachten van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="04dcd-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="04dcd-115">Andere bulkmailers verzenden ongevraagde berichten die sterk lijken op spam en veel klachten van geadresseerden genereren.</span><span class="sxs-lookup"><span data-stu-id="04dcd-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="04dcd-116">Berichten van een bulkmailer worden bulkmail of grijze e-mail genoemd.</span><span class="sxs-lookup"><span data-stu-id="04dcd-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="04dcd-117">Met spamfilters  worden berichten gemarkeerd als Bulk-e-mail op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en voert u de opgegeven actie uit voor het bericht (de standaardactie is om het bericht naar de map Ongewenste e-mail van de geadresseerde te sturen).</span><span class="sxs-lookup"><span data-stu-id="04dcd-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="04dcd-118">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en Wat is het verschil tussen ongewenste e-mail en [bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="04dcd-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="04dcd-119">De BCL-drempelwaarden worden beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="04dcd-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="04dcd-120">BCL</span><span class="sxs-lookup"><span data-stu-id="04dcd-120">BCL</span></span>|<span data-ttu-id="04dcd-121">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04dcd-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="04dcd-122">0</span><span class="sxs-lookup"><span data-stu-id="04dcd-122">0</span></span>|<span data-ttu-id="04dcd-123">Het bericht is niet afkomstig van een bulksgewijs afzender.</span><span class="sxs-lookup"><span data-stu-id="04dcd-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="04dcd-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="04dcd-124">1, 2, 3</span></span>|<span data-ttu-id="04dcd-125">Het bericht is afkomstig van een bulksgewijs afzender die weinig klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="04dcd-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="04dcd-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04dcd-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="04dcd-127">Het bericht is afkomstig van een bulksgewijs afzender die een gemengd aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="04dcd-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="04dcd-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="04dcd-128">8, 9</span></span>|<span data-ttu-id="04dcd-129">Het bericht is afkomstig van een bulksgewijs afzender die een groot aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="04dcd-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="04dcd-130"><sup>\*</sup> Dit is de standaard drempelwaarde die wordt gebruikt in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="04dcd-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
