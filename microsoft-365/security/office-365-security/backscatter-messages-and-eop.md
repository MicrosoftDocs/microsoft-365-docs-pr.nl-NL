---
title: Backscatter in EOP
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
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over Backscatter en Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209629"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="b7f42-103">Backscatter in EOP</span><span class="sxs-lookup"><span data-stu-id="b7f42-103">Backscatter in EOP</span></span>

<span data-ttu-id="b7f42-104">*Backscatter* is niet-levering rapporten (ook wel bekend als NDR's of bounce berichten) die u ontvangt voor berichten die u niet hebt verzonden.</span><span class="sxs-lookup"><span data-stu-id="b7f42-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="b7f42-105">Spammers smeden (spoof) de Van: adres van hun berichten, en ze gebruiken vaak echte e-mailadressen om geloofwaardigheid te verlenen aan hun berichten.</span><span class="sxs-lookup"><span data-stu-id="b7f42-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="b7f42-106">Dus, wanneer spammers onvermijdelijk berichten sturen naar niet-bestaande ontvangers (spam is een high-volume operatie), de bestemming e-mailserver is in wezen misleid in het retourneren van de niet-leverbare bericht in een NDR naar de vervalste afzender in de Van: adres.</span><span class="sxs-lookup"><span data-stu-id="b7f42-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="b7f42-107">In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, doet EOP er alles aan om berichten van dubieuze bronnen te identificeren en in stilte te droppen zonder een NDR te genereren.</span><span class="sxs-lookup"><span data-stu-id="b7f42-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="b7f42-108">Maar, op basis van het enorme volume e-mail stroomt door de dienst, is er altijd de mogelijkheid dat EOP onbedoeld backscatter zal sturen.</span><span class="sxs-lookup"><span data-stu-id="b7f42-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="b7f42-109">Backscatterer.org een bloklijst (ook wel DNS-bloklijst of DNSBL) bijhoudt van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter, en EOP-servers kunnen in deze lijst worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b7f42-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="b7f42-110">Maar, we proberen niet om onszelf te verwijderen uit de Backscatterer.org blok lijst, want het is niet een lijst van spammers (door hun eigen toelating).</span><span class="sxs-lookup"><span data-stu-id="b7f42-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="b7f42-111">De Backscatter.org website ( <http://www.backscatterer.org/?target=usage> ) raadt het gebruik van hun service om inkomende e-mail te controleren in de veilige modus in plaats van Reject-modus (grote e-maildiensten bijna altijd een aantal backscatter).</span><span class="sxs-lookup"><span data-stu-id="b7f42-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
