---
title: Backscatter en EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Backscatter is geautomatiseerde bounceberichten die naar vervalste e-mailadressen worden verzonden. De Backscatterer DNSBL identificeert servers die backscatter-berichten verzenden (waaronder veel legitieme e-mailbronnen). Aangezien het geen spammerlijst is, proberen wij niet om van De DNSBL van Backscatterer te verwijderen.
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895403"
---
# <a name="backscatter-and-eop"></a><span data-ttu-id="403ca-105">Backscatter en EOP</span><span class="sxs-lookup"><span data-stu-id="403ca-105">Backscatter and EOP</span></span>

<span data-ttu-id="403ca-106">*Backscatter* is niet-levering rapporten (ook wel bekend als NDR's of bounce berichten) die u ontvangt voor berichten die u niet hebt verzonden.</span><span class="sxs-lookup"><span data-stu-id="403ca-106">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="403ca-107">Spammers smeden (spoof) de Van: adres van hun berichten, en ze gebruiken vaak echte e-mailadressen om geloofwaardigheid te verlenen aan hun berichten.</span><span class="sxs-lookup"><span data-stu-id="403ca-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="403ca-108">Dus, wanneer spammers onvermijdelijk berichten sturen naar niet-bestaande ontvangers (spam is een high-volume operatie), de bestemming e-mailserver is in wezen misleid in het retourneren van de niet-leverbare bericht in een NDR naar de vervalste afzender in de Van: adres.</span><span class="sxs-lookup"><span data-stu-id="403ca-108">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="403ca-109">Exchange Online Protection (EOP) stelt alles in het werk om berichten van dubieuze bronnen te identificeren en in stilte te droppen zonder een NDR te genereren.</span><span class="sxs-lookup"><span data-stu-id="403ca-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="403ca-110">Maar, op basis van het enorme volume e-mail stroomt door de dienst, is er altijd de mogelijkheid dat EOP onbedoeld backscatter zal sturen.</span><span class="sxs-lookup"><span data-stu-id="403ca-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="403ca-111">Backscatterer.org een bloklijst (ook wel DNS-bloklijst of DNSBL) bijhoudt van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter, en EOP-servers kunnen in deze lijst worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="403ca-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="403ca-112">Maar, we proberen niet om onszelf te verwijderen uit de Backscatterer.org blok lijst, want het is niet een lijst van spammers (door hun eigen toelating).</span><span class="sxs-lookup"><span data-stu-id="403ca-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="403ca-113">De Backscatter.org<http://www.backscatterer.org/?target=usage>website ( ) raadt het gebruik van hun service om inkomende e-mail te controleren in de veilige modus in plaats van Reject-modus (grote e-maildiensten bijna altijd een aantal backscatter).</span><span class="sxs-lookup"><span data-stu-id="403ca-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
