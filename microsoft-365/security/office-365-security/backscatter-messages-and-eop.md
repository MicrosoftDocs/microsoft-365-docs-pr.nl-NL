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
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165953"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="23f73-103">Backscatter in EOP</span><span class="sxs-lookup"><span data-stu-id="23f73-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23f73-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="23f73-104">**Applies to**</span></span>
- [<span data-ttu-id="23f73-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="23f73-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="23f73-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="23f73-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="23f73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23f73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="23f73-108">*Backscatter* is rapporten over niet-bezorging (ook wel NR's of niet-bezorgdberichten genoemd) die u ontvangt voor berichten die u niet hebt verzonden.</span><span class="sxs-lookup"><span data-stu-id="23f73-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="23f73-109">Spammers vervalsen het Van:-adres van hun berichten en gebruiken vaak echte e-mailadressen om hun berichten geloofwaardig te maken.</span><span class="sxs-lookup"><span data-stu-id="23f73-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="23f73-110">Wanneer spammers dus onvermijdelijk berichten verzenden naar niet-bestaande geadresseerden (spam is een bewerking met hoog volume), wordt de doel-e-mailserver in feite gedredigd om het onbeslieerde bericht in een NDR te retourneren aan de vervalste afzender in het Van:-adres.</span><span class="sxs-lookup"><span data-stu-id="23f73-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="23f73-111">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken doet EOP er alles aan om berichten van bronnen te identificeren en op de rui uit te zetten zonder een NDR te genereren.</span><span class="sxs-lookup"><span data-stu-id="23f73-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="23f73-112">Maar op basis van de grote hoeveelheid e-mail die door de service wordt verzonden, is het echter altijd mogelijk dat EOP backscatter onbedoeld verzendt.</span><span class="sxs-lookup"><span data-stu-id="23f73-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="23f73-113">Backscatterer.org een blokkeringslijst bijhoudt (ook wel een DNS-blokkeringslijst of DNSBL genoemd) van e-mailservers die verantwoordelijk waren voor het verzenden van backscatter en EOP-servers kunnen in deze lijst worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="23f73-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="23f73-114">Maar we proberen niet te verwijderen uit de lijst met geblokkeerde Backscatterer.org omdat het geen lijst met spammers is (voor hun eigen toegang).</span><span class="sxs-lookup"><span data-stu-id="23f73-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="23f73-115">De Backscatter.org () raadt aan de service te gebruiken voor het controleren van inkomende e-mail in de veilige modus in plaats van de modus Weigeren (in grote e-mailservices wordt vrijwel altijd <http://www.backscatterer.org/?target=usage> backscatter verzonden).</span><span class="sxs-lookup"><span data-stu-id="23f73-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
