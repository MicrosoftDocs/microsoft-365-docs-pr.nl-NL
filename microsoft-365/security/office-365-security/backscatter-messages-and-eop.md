---
title: Backscatter messages and EOP(Backscatter-berichten en EOP)
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
description: Backscatter-berichten zijn automatische bounceberichten die naar vervalste e-mailadressen worden verzonden. De Backscatterer DNSBL identificeert servers die backscatter-berichten verzenden (waaronder veel legitieme e-mailbronnen). Aangezien het geen spammerlijst is, proberen wij niet om van De DNSBL van Backscatterer te verwijderen.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/27/2020
ms.locfileid: "42810934"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="ecaea-105">Backscatter messages and EOP(Backscatter-berichten en EOP)</span><span class="sxs-lookup"><span data-stu-id="ecaea-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="ecaea-106">*Backscatter-berichten* zijn niet-leveringsrapporten (ook wel NDR's of bounceberichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden.</span><span class="sxs-lookup"><span data-stu-id="ecaea-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="ecaea-107">Spammers smeden (spoof) de Van: adres van hun berichten, en ze gebruiken vaak echte e-mailadressen om geloofwaardigheid te verlenen aan hun berichten.</span><span class="sxs-lookup"><span data-stu-id="ecaea-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="ecaea-108">Dus, wanneer een spammer onvermijdelijk berichten te sturen naar niet-bestaande ontvangers (spam is een high-volume operatie), zal de bestemming e-mailserver waarschijnlijk terug de onbestelbare bericht in een NDR, die wordt verzonden naar de vervalste afzender in de Van: adres.</span><span class="sxs-lookup"><span data-stu-id="ecaea-108">So, when a spammer inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server will likely return the undeliverable message in an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="ecaea-109">Exchange Online Protection (EOP) stelt alles in het werk om berichten van dubieuze bronnen te identificeren en in stilte te droppen zonder een NDR te genereren.</span><span class="sxs-lookup"><span data-stu-id="ecaea-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="ecaea-110">Maar, op basis van het enorme volume e-mail stroomt door de dienst, is er altijd de mogelijkheid dat EOP onbedoeld backscatter berichten zal sturen.</span><span class="sxs-lookup"><span data-stu-id="ecaea-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="ecaea-111">Backscatterer.org een bloklijst (ook wel DNS-bloklijst of DNSBL) bijhoudt van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter-berichten, en EOP-servers kunnen in deze lijst worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ecaea-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="ecaea-112">Maar, we proberen niet om onszelf te verwijderen uit de Backscatterer.org blok lijst, want het is niet een lijst van spammers (door hun eigen toelating).</span><span class="sxs-lookup"><span data-stu-id="ecaea-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="ecaea-113">De Backscatter.org<http://www.backscatterer.org/?target=usage>website ( ) raadt het gebruik van hun service om inkomende e-mail te controleren in de veilige modus in plaats van Reject-modus (grote e-maildiensten bijna altijd een aantal backscatter berichten).</span><span class="sxs-lookup"><span data-stu-id="ecaea-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
