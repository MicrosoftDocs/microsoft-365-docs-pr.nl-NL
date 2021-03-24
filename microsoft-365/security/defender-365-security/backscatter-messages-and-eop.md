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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over Backscatter en Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058989"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="e8876-103">Backscatter in EOP</span><span class="sxs-lookup"><span data-stu-id="e8876-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e8876-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e8876-104">**Applies to**</span></span>
- [<span data-ttu-id="e8876-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e8876-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e8876-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e8876-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e8876-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8876-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e8876-108">*Backscatter* is niet-bezorgingsrapporten (ook wel NDR's of niet-bezorgde berichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden.</span><span class="sxs-lookup"><span data-stu-id="e8876-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="e8876-109">Spammers vervalsen (spoof) het Van:-adres van hun berichten en ze gebruiken vaak echte e-mailadressen om hun berichten geloofwaardig te maken.</span><span class="sxs-lookup"><span data-stu-id="e8876-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="e8876-110">Dus wanneer spammers onvermijdelijk berichten verzenden naar niet-bestaande geadresseerden (spam is een groot volumebewerking), wordt de doel-e-mailserver in feite misleid om het niet-beleverbare bericht in een NDR terug te sturen naar de vervalste afzender in het Van:-adres.</span><span class="sxs-lookup"><span data-stu-id="e8876-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="e8876-111">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, doet EOP er alles aan om berichten uit dubieuze bronnen te identificeren en in stilte neer te zetten zonder een NDR te genereren.</span><span class="sxs-lookup"><span data-stu-id="e8876-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="e8876-112">Maar op basis van het grote volume dat via de service wordt verzonden, is er altijd de mogelijkheid dat EOP per ongeluk backscatter verzendt.</span><span class="sxs-lookup"><span data-stu-id="e8876-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="e8876-113">Backscatterer.org een blokkeringslijst (ook wel een DNS-bloklijst of DNSBL genoemd) van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter, en EOP-servers worden mogelijk weergegeven in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="e8876-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="e8876-114">Maar we proberen ons niet uit de lijst met blokkeringen Backscatterer.org verwijderen omdat het geen lijst met spammers is (naar eigen zeggen).</span><span class="sxs-lookup"><span data-stu-id="e8876-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="e8876-115">De Backscatter.org website () raadt aan de service te gebruiken om binnenkomende e-mail te controleren in de veilige modus in plaats van de modus Weigeren (grote e-mailservices sturen vrijwel altijd wat <http://www.backscatterer.org/?target=usage> backscatter).</span><span class="sxs-lookup"><span data-stu-id="e8876-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
