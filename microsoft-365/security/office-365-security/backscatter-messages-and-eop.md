---
title: Backscatter in EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over Backscatter en Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827783"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="7a56b-103">Backscatter in EOP</span><span class="sxs-lookup"><span data-stu-id="7a56b-103">Backscatter in EOP</span></span>

<span data-ttu-id="7a56b-104">*Backscatter* is rapporten over niet-uitgevoerde bezorging (ook wel ndr's genoemd of berichten verzenden) die u ontvangt voor berichten die u niet heb verzonden.</span><span class="sxs-lookup"><span data-stu-id="7a56b-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="7a56b-105">Spammers smeden (spoof) The from: adres van hun berichten, en ze gebruiken vaak realtime e-mailadressen om geloofwaardigheid te lenen aan hun berichten.</span><span class="sxs-lookup"><span data-stu-id="7a56b-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="7a56b-106">Wanneer spammers via een zeer grote transactie geen berichten naar niet-bestaande geadresseerden sturen (spam is een high-volume-actie), wordt de doel-e-mailserver in feite omgezet in een NDR naar de vervalste afzender in het adres van:.</span><span class="sxs-lookup"><span data-stu-id="7a56b-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="7a56b-107">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, zorgt EOP ervoor dat elke inspanning berichten van dubious-bronnen identificeert en ongestilled verwijdert zonder een NDR te genereren.</span><span class="sxs-lookup"><span data-stu-id="7a56b-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="7a56b-108">Op basis van het e-mailadres van doorschijnende, kunt u altijd Backscatter de mogelijkheid bieden om te verzenden.</span><span class="sxs-lookup"><span data-stu-id="7a56b-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="7a56b-109">Backscatterer.org onderhoudt een blokkeringslijst (ook wel bekend als DNS-bloklijst of DNSBL) van e-mailservers die verantwoordelijk zijn voor het verzenden van Backscatter en EOP servers mogelijk in deze lijst worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7a56b-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="7a56b-110">Maar we proberen onszelf niet te verwijderen uit de lijst met Backscatterer.org-blokken omdat dit geen lijst is met spammers (op basis van eigen invoer).</span><span class="sxs-lookup"><span data-stu-id="7a56b-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="7a56b-111">De Backscatter.org-website ( <http://www.backscatterer.org/?target=usage> ) adviseert hun service te gebruiken voor het controleren van inkomende e-mail in de veilige modus in plaats van de reject-modus (grootschalige e-mailservices verzenden bijna altijd een aantal Backscatter).</span><span class="sxs-lookup"><span data-stu-id="7a56b-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
