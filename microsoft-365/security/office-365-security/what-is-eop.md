---
title: Wat is EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom:
- TN2DMC
- seo-marvel-apr2020
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: In dit artikel vindt u meer informatie over Exchange Online Protection (EOP), een cloudservice voor e-mailfiltering.
ms.openlocfilehash: 7a9c122edf229d70f0ea5a1dbea8be56b5a2a3a9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034936"
---
# <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="8a5d3-103">Wat is Exchange Online Protection (EOP)</span><span class="sxs-lookup"><span data-stu-id="8a5d3-103">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="8a5d3-104">Exchange Online Protection (EOP) is een cloudservice voor e-mailfiltering die uw organisatie beschermt tegen spam en malware.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-104">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="8a5d3-105">Als u postvakken in Microsoft 365 hebt, worden deze automatisch beschermd door EOP omdat deze deel uitmaken van de service.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-105">If you have mailboxes in Microsoft 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="8a5d3-106">Dit geldt ook voor organisaties die mailboxen hebben in zowel Microsoft 365 als on-premise, wat algemeen bekend staat als een hybride scenario.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-106">This includes organizations that have mailboxes in both Microsoft 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="8a5d3-107">EOP standalone is ook beschikbaar voor klanten die geen mailboxen in de cloud hebben, maar hun on-premises mailboxen willen beschermen.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-107">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premises mailboxes.</span></span>

<span data-ttu-id="8a5d3-108">EOP probeert rommel uit te filteren, zodat uw Postvak IN vrij blijft van inhoud die gebruikers niet willen zien.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-108">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="8a5d3-109">Normaal gesproken wordt ongewenste e-mail bezorgd in de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-109">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="8a5d3-110">Sommige gebruikers willen controleren om ervoor te zorgen dat het filteren doet wat ze willen, zodat de junk e-map is een gemakkelijke manier voor gebruikers om te controleren op hun eigen.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-110">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="8a5d3-111">Het is een goede zaak wanneer junk of anderszins slechte e-mail gaat in de Junk Email map automatisch.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-111">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="8a5d3-112">De service doet wat nodig is op basis van de standaard- of de aangepaste beheerinstellingen.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-112">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="8a5d3-113">Met andere woorden, gebruikers moeten zich geen zorgen maken over het zien van veel spammail in de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-113">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="8a5d3-114">Als beheerders alle rommel liever uit het zicht verplaatsen, moet de quarantaine worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-114">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="8a5d3-115">Zie het artikel [Voor e-mailberichten quarantaine](quarantine-email-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-115">For more details, see the [Quarantine email messages](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="8a5d3-116">Belangrijke voorwaarden</span><span class="sxs-lookup"><span data-stu-id="8a5d3-116">Important terms</span></span>

<span data-ttu-id="8a5d3-117">**Binnenkomend:** berichten die in Microsoft 365 binnenkomen.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-117">**Inbound**: Messages that are coming into Microsoft 365.</span></span>

<span data-ttu-id="8a5d3-118">**Uitgaand:** Berichten die uit Microsoft 365 gaan.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-118">**Outbound**: Messages that are going out of Microsoft 365.</span></span>

<span data-ttu-id="8a5d3-119">**Intern**: Berichten die van iemand binnen de organisatie zijn naar iemand binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-119">**Internal**: Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="8a5d3-120">Dit geldt ook voor klanten die zich in hybride scenario's bevinden en een postvak kan on-premises zijn en het andere postvak bevindt zich in de cloud.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-120">This includes customers who are in hybrid scenarios and one mailbox could be on-premises and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="8a5d3-121">**False Negative (FN)**: Spam en andere rommel die ten onrechte wordt verzonden in de inbox.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-121">**False Negative (FN)**: Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="8a5d3-122">**False Positive (FP)**: Legitieme berichten die ten onrechte worden gemarkeerd als spam en in de map Ongewenste e-mail of Quarantaine worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-122">**False Positive (FP)**: Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="8a5d3-123">**Spam, ook wel bekend als ongevraagde e-mail**: Dit komt in de vorm van commerciële reclame, kettingbrieven, politieke mailings, enz. Dit is e-mail die gebruikers niet aanmelden voor en van spammers die proberen om producten te werven of een poging om fraude te plegen.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-123">**Spam, also known as unsolicited e-mail**: This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="8a5d3-124">**Phish**: Phishing is een speciaal type spam dat is bedoeld om u te verleiden tot het opgeven van persoonlijke informatie met het oog op het plegen van identiteitsdiefstal of fraude.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-124">**Phish**: Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="8a5d3-125">Dit type bericht bevat meestal een kwaadaardige link of bijlage, maar niet altijd.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-125">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="8a5d3-126">**Spoof:** Spoofing is wanneer spammers de FROM-header vervalsen, zodat berichten afkomstig lijken te zijn van iemand of ergens anders dan de werkelijke bron.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-126">**Spoof**: Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="8a5d3-127">Dit kan spam zijn, maar meestal gebruikt om phish gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-127">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="8a5d3-128">**Imitatie**: Dit soort spam is ook een manier om de afzender adres te smeden, maar het wordt gedaan door het wijzigen van een deel van de naam of het domein, zodat het lijkt op de echte bron.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-128">**Impersonation**: This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="8a5d3-129">Bijvoorbeeld, Bi11@micr0s0ft.com, waar de "l" in Bill was eigenlijk het nummer elf en de "o" in Microsoft werd vervangen door het nummer nul.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-129">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="8a5d3-130">**Bulk**: Bulk mail wordt meestal gevraagd door gebruikers, hoewel soms indirect wanneer bedrijven informatie verkopen aan andere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-130">**Bulk**: Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="8a5d3-131">Het is gebruikelijk dat gebruikers zich opzettelijk aanmelden voor bulkmail (d.w.z. nieuwe brieven), maar vergeet later en denk dat het spam is.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-131">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="8a5d3-132">Bulk mail wordt spam wanneer bulk mailers meer verzenden dan gebruikers zich aanmelden en klachtenniveaus te hoog worden.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-132">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
