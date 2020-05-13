---
title: Waarden voor bulkklachten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer te weten komen over bcl-waarden (bulkcomplianceniveau) die worden gebruikt in Exchange Online Protection (EOP).
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209605"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="58d42-103">Bulkklachtenniveau (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="58d42-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="58d42-104">In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken, wijst EOP een bulkcompliant niveau (BCL) toe aan binnenkomende berichten van bulkmailers.</span><span class="sxs-lookup"><span data-stu-id="58d42-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="58d42-105">De BCL wordt toegevoegd aan het bericht in een X-header en is vergelijkbaar met het [spam vertrouwensniveau (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten te identificeren als spam.</span><span class="sxs-lookup"><span data-stu-id="58d42-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="58d42-106">Een hogere BCL geeft aan dat een bulkbericht meer kans heeft om klachten te genereren (en daarom meer kans heeft op spam).</span><span class="sxs-lookup"><span data-stu-id="58d42-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="58d42-107">Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.</span><span class="sxs-lookup"><span data-stu-id="58d42-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="58d42-108">Bulkmailers variëren in hun verzendpatronen, het maken van inhoud en acquisitiepraktijken voor ontvangers.</span><span class="sxs-lookup"><span data-stu-id="58d42-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="58d42-109">Goede bulk mailers sturen gewenste berichten met relevante inhoud naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="58d42-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="58d42-110">Deze berichten genereren weinig klachten van ontvangers.</span><span class="sxs-lookup"><span data-stu-id="58d42-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="58d42-111">Andere bulkmailers sturen ongevraagde berichten die sterk op spam lijken en veel klachten van ontvangers genereren.</span><span class="sxs-lookup"><span data-stu-id="58d42-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="58d42-112">Berichten van een bulkmailer worden bulkmail of grijze e-mail genoemd.</span><span class="sxs-lookup"><span data-stu-id="58d42-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="58d42-113">Spamfiltering markeert berichten als **Bulk-e-mail** op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en neemt de opgegeven actie op het bericht (de standaardactie is het verzenden van het bericht naar de map Ongewenste e-mail van de ontvanger).</span><span class="sxs-lookup"><span data-stu-id="58d42-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="58d42-114">Zie [Beleid voor antispam configureren](configure-your-spam-filter-policies.md) voor meer informatie en Wat is het verschil tussen ongewenste [e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="58d42-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="58d42-115">De BCL-drempels worden beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="58d42-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="58d42-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="58d42-116">**BCL**</span></span>|<span data-ttu-id="58d42-117">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="58d42-117">**Description**</span></span>|
|<span data-ttu-id="58d42-118">0</span><span class="sxs-lookup"><span data-stu-id="58d42-118">0</span></span>|<span data-ttu-id="58d42-119">Het bericht is niet van een afzender in bulk.</span><span class="sxs-lookup"><span data-stu-id="58d42-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="58d42-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="58d42-120">1, 2, 3</span></span>|<span data-ttu-id="58d42-121">Het bericht is van een bulk afzender die weinig klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="58d42-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="58d42-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="58d42-122">4, 5, 6, 7</span></span>|<span data-ttu-id="58d42-123">Het bericht is van een bulk afzender die een gemengd aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="58d42-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="58d42-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="58d42-124">8, 9</span></span>|<span data-ttu-id="58d42-125">Het bericht is van een bulk afzender die een groot aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="58d42-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
