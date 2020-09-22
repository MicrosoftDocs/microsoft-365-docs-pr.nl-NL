---
title: Waarden voor bulk klachten niveau
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over de BCL-waarden (bulk compliance niveau) die worden gebruikt in Exchange Online Protection (EOP).
ms.openlocfilehash: d59bb152de075bb807e3cae72839fe459d7da40f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203525"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="3c85d-103">Bulk klachten niveau (BCL) in EOP</span><span class="sxs-lookup"><span data-stu-id="3c85d-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3c85d-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken wordt in EOP een BCL (bulk compliant niveau) toegewezen aan inkomende berichten van grote Mailers.</span><span class="sxs-lookup"><span data-stu-id="3c85d-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="3c85d-105">De BCL wordt aan het bericht toegevoegd in een X-header en is vergelijkbaar met het [spam betrouwbaarheidsniveau (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten als spam op te sporen.</span><span class="sxs-lookup"><span data-stu-id="3c85d-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="3c85d-106">Een hogere BCL geeft aan dat een bulk bericht waarschijnlijk klachten genereert (en dat waarschijnlijk spam is).</span><span class="sxs-lookup"><span data-stu-id="3c85d-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="3c85d-107">Microsoft gebruikt interne en externe bronnen voor het identificeren van bulk berichten en het bepalen van de juiste BCL.</span><span class="sxs-lookup"><span data-stu-id="3c85d-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="3c85d-108">Grote Mailers verschillen in hun verzend patronen, het maken van inhoud en de overname van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="3c85d-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="3c85d-109">Goede bulk berichten sturen de gewenste berichten met relevante inhoud naar hun abonnees.</span><span class="sxs-lookup"><span data-stu-id="3c85d-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="3c85d-110">Deze berichten genereren enkele klachten van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="3c85d-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="3c85d-111">Andere grote Mailers verzenden ongevraagde berichten die sterk lijken op spam en Genereer veel klachten van geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="3c85d-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="3c85d-112">Berichten van een grootschalige e-mail band worden ook wel grote hoeveelheden e-mail of grijze e-mail genoemd.</span><span class="sxs-lookup"><span data-stu-id="3c85d-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="3c85d-113">Met filters voor ongewenste e-mail worden berichten als **bulk e-mail** gemarkeerd op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en wordt de opgegeven actie op het bericht uitgevoerd (de standaardactie zorgt voor het verzenden van het bericht naar de map Ongewenste e-mail van de geadresseerde).</span><span class="sxs-lookup"><span data-stu-id="3c85d-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="3c85d-114">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c85d-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="3c85d-115">In de volgende tabel vindt u een beschrijving van de BCL-drempelwaarden.</span><span class="sxs-lookup"><span data-stu-id="3c85d-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="3c85d-116">BCL</span><span class="sxs-lookup"><span data-stu-id="3c85d-116">BCL</span></span>|<span data-ttu-id="3c85d-117">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3c85d-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="3c85d-118">0</span><span class="sxs-lookup"><span data-stu-id="3c85d-118">0</span></span>|<span data-ttu-id="3c85d-119">Het bericht is niet afkomstig van een bulk verzender.</span><span class="sxs-lookup"><span data-stu-id="3c85d-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="3c85d-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="3c85d-120">1, 2, 3</span></span>|<span data-ttu-id="3c85d-121">Het bericht is afkomstig uit een bulk verzender waarmee een aantal klachten wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="3c85d-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="3c85d-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="3c85d-122">4, 5, 6, 7</span></span>|<span data-ttu-id="3c85d-123">Het bericht is afkomstig uit een bulk verzender waarmee een gemengde soort klachten wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="3c85d-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="3c85d-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="3c85d-124">8, 9</span></span>|<span data-ttu-id="3c85d-125">Het bericht is afkomstig van een bulk verzender waarmee een groot aantal klachten wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="3c85d-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
