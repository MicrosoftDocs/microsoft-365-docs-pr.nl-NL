---
title: Bulk Complaint Level waarden, bulk mailers, BCL niveaus, hoe BCL werkt, BCL ratings, Antispam, Antispam header, bulk mail filtering, stop bulk mail
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Meer informatie over de BCL-waarden (Bulk Complain Level) in Office 365.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806099"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="bc645-103">Waarden op bulkklachtenniveau</span><span class="sxs-lookup"><span data-stu-id="bc645-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="bc645-104">Bulkmailers variëren in hun verzendpatronen, het maken van inhoud en het maken van lijstacquisitiepraktijken.</span><span class="sxs-lookup"><span data-stu-id="bc645-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="bc645-105">Sommige zijn goede bulk mailers die wilde berichten met relevante inhoud te sturen naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="bc645-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="bc645-106">Deze berichten genereren weinig klachten van ontvangers.</span><span class="sxs-lookup"><span data-stu-id="bc645-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="bc645-107">Andere bulkmailers sturen ongevraagde berichten die sterk op spam lijken en veel klachten van ontvangers genereren.</span><span class="sxs-lookup"><span data-stu-id="bc645-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="bc645-108">Om onderscheid te maken tussen dit soort bulkmailers, krijgen berichten van bulkmailers een BCL-classificatie (Bulk Complaint Level) toegewezen.</span><span class="sxs-lookup"><span data-stu-id="bc645-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="bc645-109">BCL ratings variëren van 1 tot 9, afhankelijk van hoe waarschijnlijk de bulk mailer is om klachten te genereren.</span><span class="sxs-lookup"><span data-stu-id="bc645-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="bc645-110">Een afzender met een rating van BCL 9 zal waarschijnlijk veel klachten van ontvangers genereren, terwijl een rating van BCL 3 waarschijnlijk niet veel klachten zal genereren.</span><span class="sxs-lookup"><span data-stu-id="bc645-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="bc645-111">Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.</span><span class="sxs-lookup"><span data-stu-id="bc645-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="bc645-112">Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie over deze berichtkoptekst.</span><span class="sxs-lookup"><span data-stu-id="bc645-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="bc645-113">Aangezien een bulkmailer met een rating van 9 waarschijnlijk klachten genereert, is de standaard BCL 7.</span><span class="sxs-lookup"><span data-stu-id="bc645-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="bc645-114">Dit betekent dat bulkmails worden geaccepteerd totdat het klachtenniveau van 7 en e-mail daarna niet meer worden geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="bc645-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="bc645-115">Hoe lager de beoordeling, hoe minder bulkpost wordt geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="bc645-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="bc645-116">Als uw gebruikers zijn, en hun werk is, gevoelig voor bulk mail, en uw BCL is ingesteld op 4, dan is er geen bulk mail met een hogere BCL dan 4 zal worden geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="bc645-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="bc645-117">U BCL-waarden gebruiken om het gewenste niveau van bulkfiltering in te stellen die uw organisatie nodig heeft door de stappen te volgen in [Uw beleid voor spamfilters configureren.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bc645-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bc645-118">In de volgende tabel worden de BCL-waarden beschreven die momenteel worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="bc645-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bc645-119">**BCL-waarde**</span><span class="sxs-lookup"><span data-stu-id="bc645-119">**BCL Value**</span></span>|<span data-ttu-id="bc645-120">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="bc645-120">**Description**</span></span>|
|<span data-ttu-id="bc645-121">0</span><span class="sxs-lookup"><span data-stu-id="bc645-121">0</span></span>|<span data-ttu-id="bc645-122">Het bericht is niet van een afzender in bulk.</span><span class="sxs-lookup"><span data-stu-id="bc645-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="bc645-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="bc645-123">1, 2, 3</span></span>|<span data-ttu-id="bc645-124">Het bericht is van een bulk afzender die weinig klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="bc645-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="bc645-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="bc645-125">4, 5, 6, 7</span></span>|<span data-ttu-id="bc645-126">Het bericht is van een bulk afzender die een gemengd aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="bc645-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="bc645-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="bc645-127">8, 9</span></span>|<span data-ttu-id="bc645-128">Het bericht is van een bulk afzender die een groot aantal klachten genereert.</span><span class="sxs-lookup"><span data-stu-id="bc645-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
