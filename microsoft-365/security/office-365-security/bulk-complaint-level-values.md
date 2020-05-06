---
title: Waarden op bulkklachtenniveau
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Meer informatie over de BCL-waarden (Bulk Compliance Level) in Office 365.
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035566"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="12ed5-103">Bulkklachtenniveau (BCL) in Office 365</span><span class="sxs-lookup"><span data-stu-id="12ed5-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="12ed5-104">Bulkmailers variëren in hun verzendpatronen, het maken van inhoud en acquisitiepraktijken voor ontvangers.</span><span class="sxs-lookup"><span data-stu-id="12ed5-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="12ed5-105">Sommige zijn goede bulk mailers die gewenste berichten met relevante inhoud te sturen naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="12ed5-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="12ed5-106">Deze berichten genereren weinig klachten van ontvangers.</span><span class="sxs-lookup"><span data-stu-id="12ed5-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="12ed5-107">Andere bulkmailers sturen ongevraagde berichten die sterk op spam lijken en veel klachten van ontvangers genereren.</span><span class="sxs-lookup"><span data-stu-id="12ed5-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="12ed5-108">Berichten van een bulkmailer staan bekend als bulkmail of grijze e-mail.</span><span class="sxs-lookup"><span data-stu-id="12ed5-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="12ed5-109">Als u berichten wilt onderscheiden van verschillende soorten bulkmailers, krijgt binnenkomende e-mail van bulkmailers (Exchange Online of zelfstandige Exchange Online Protection (EOP) zonder Exchange Online-postvakken) een bulkklachtenniveau (BCL) dat aan het bericht is toegevoegd in een X-header.</span><span class="sxs-lookup"><span data-stu-id="12ed5-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="12ed5-110">De BCL is vergelijkbaar met het [spamvertrouwensniveau (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten als spam te identificeren.</span><span class="sxs-lookup"><span data-stu-id="12ed5-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="12ed5-111">Een hogere BCL geeft aan dat een bulkbericht meer kans heeft om klachten te genereren (en daarom meer kans heeft op spam).</span><span class="sxs-lookup"><span data-stu-id="12ed5-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="12ed5-112">Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.</span><span class="sxs-lookup"><span data-stu-id="12ed5-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="12ed5-113">Spamfiltering markeert berichten als **Bulk-e-mail** op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en neemt de opgegeven actie op het bericht (de standaardactie is het verzenden van het bericht naar de map Ongewenste e-mail van de ontvanger).</span><span class="sxs-lookup"><span data-stu-id="12ed5-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="12ed5-114">Zie [Beleid voor antispam configureren](configure-your-spam-filter-policies.md) voor meer informatie en Wat is het verschil tussen ongewenste [e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="12ed5-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="12ed5-115">De BCL-drempels worden beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="12ed5-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="12ed5-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="12ed5-116">**BCL**</span></span>|<span data-ttu-id="12ed5-117">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="12ed5-117">**Description**</span></span>|
|<span data-ttu-id="12ed5-118">0</span><span class="sxs-lookup"><span data-stu-id="12ed5-118">0</span></span>|<span data-ttu-id="12ed5-119">Het bericht is niet van een afzender in bulk.</span><span class="sxs-lookup"><span data-stu-id="12ed5-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="12ed5-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="12ed5-120">1, 2, 3</span></span>|<span data-ttu-id="12ed5-121">Het bericht is van een bulk afzender die weinig klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="12ed5-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="12ed5-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="12ed5-122">4, 5, 6, 7</span></span>|<span data-ttu-id="12ed5-123">Het bericht is van een bulk afzender die een gemengd aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="12ed5-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="12ed5-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="12ed5-124">8, 9</span></span>|<span data-ttu-id="12ed5-125">Het bericht is van een bulk afzender die een groot aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="12ed5-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
