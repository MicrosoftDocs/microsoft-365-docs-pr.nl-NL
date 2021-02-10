---
title: Waarden voor bulksgelaagden
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
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165965"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="2821a-103">Bulksgewijs klachtniveau (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="2821a-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2821a-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2821a-104">**Applies to**</span></span>
- [<span data-ttu-id="2821a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2821a-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="2821a-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2821a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="2821a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2821a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2821a-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken wijst EOP een bulksgewijs compatibel niveau (BCL) toe aan inkomende berichten van bulkmailers.</span><span class="sxs-lookup"><span data-stu-id="2821a-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="2821a-109">De BCL wordt toegevoegd aan het bericht in een X-koptekst en is vergelijkbaar met het spamniveau [dat](spam-confidence-levels.md) wordt gebruikt om berichten als spam te identificeren.</span><span class="sxs-lookup"><span data-stu-id="2821a-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="2821a-110">Een hogere BCL geeft aan dat de kans groter is dat een bulkbericht klachten genereert (en daarom waarschijnlijk spam is).</span><span class="sxs-lookup"><span data-stu-id="2821a-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="2821a-111">Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.</span><span class="sxs-lookup"><span data-stu-id="2821a-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="2821a-112">Bulkmailers variëren in hun verzendingspatronen, het maken van inhoud en het verkrijgen van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2821a-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="2821a-113">Goede bulkmailers sturen gewenste berichten met relevante inhoud naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="2821a-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="2821a-114">Deze berichten genereren weinig klachten van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2821a-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="2821a-115">Andere bulkmailers verzenden ongevraagde berichten die sterk lijken op spam en genereren veel klachten van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2821a-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="2821a-116">Berichten van een bulkmailer worden ook wel bulkmail of grijze e-mail genoemd.</span><span class="sxs-lookup"><span data-stu-id="2821a-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="2821a-117">Met spamfilters  worden berichten gemarkeerd als bulk-e-mail op basis van de drempelwaarde voor BCL (de standaardwaarde of een waarde die u opgeeft) en wordt de opgegeven actie ondernomen op het bericht (de standaardactie is het bericht bezorgen bij de map Ongewenste e-mail van de geadresseerde).</span><span class="sxs-lookup"><span data-stu-id="2821a-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="2821a-118">Zie Antispambeleid configureren en wat is het verschil tussen ongewenste [e-mail](configure-your-spam-filter-policies.md) en [bulk-e-mail voor meer informatie.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="2821a-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="2821a-119">De drempelwaarden voor BCL worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="2821a-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="2821a-120">BCL</span><span class="sxs-lookup"><span data-stu-id="2821a-120">BCL</span></span>|<span data-ttu-id="2821a-121">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2821a-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="2821a-122">0</span><span class="sxs-lookup"><span data-stu-id="2821a-122">0</span></span>|<span data-ttu-id="2821a-123">Het bericht is niet afkomstig van een bulksge keer.</span><span class="sxs-lookup"><span data-stu-id="2821a-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="2821a-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="2821a-124">1, 2, 3</span></span>|<span data-ttu-id="2821a-125">Het bericht is afkomstig van een afzender die bulksgewijs maar weinig klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="2821a-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="2821a-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2821a-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="2821a-127">Het bericht is afkomstig van een afzender die bulksgewijs een gemengd aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="2821a-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="2821a-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="2821a-128">8, 9</span></span>|<span data-ttu-id="2821a-129">Het bericht is afkomstig van een afzender die bulksgewijs veel klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="2821a-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="2821a-130"><sup>\*</sup> Dit is de standaard drempelwaarde die wordt gebruikt in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="2821a-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
