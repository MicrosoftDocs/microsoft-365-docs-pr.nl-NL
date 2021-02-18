---
title: Ondersteuning voor validatie van met domeinsleutels geïdentificeerde e-mail (DKIM) ondertekende berichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Meer informatie over de validatie van DKIM-ondertekende berichten in Exchange Online Protection en Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290259"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="af2d7-103">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="af2d7-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="af2d7-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="af2d7-104">**Applies to**</span></span>
- [<span data-ttu-id="af2d7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="af2d7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="af2d7-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="af2d7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="af2d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af2d7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="af2d7-108">Exchange Online Protection (EOP) en Exchange Online ondersteunen beide inkomende validatie van[DKIM-berichten](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="af2d7-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="af2d7-109">DKIM controleert of een e-mailbericht niet door iemand anders is  vervalst en is verzonden vanaf het domein waar het vandaan komt. </span><span class="sxs-lookup"><span data-stu-id="af2d7-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="af2d7-110">De tekst bindt een e-mailbericht aan de organisatie die het heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="af2d7-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="af2d7-111">DKIM-verificatie wordt automatisch gebruikt voor alle berichten die met IPv6 worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="af2d7-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="af2d7-112">Microsoft 365 ondersteunt ook DKIM wanneer e-mail wordt verzonden via IPv4.</span><span class="sxs-lookup"><span data-stu-id="af2d7-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="af2d7-113">(Zie Ondersteuning voor anonieme inkomende e-mailberichten via IPv6 voor meer informatie [over IPv6-ondersteuning.)](support-for-anonymous-inbound-email-messages-over-ipv6.md)</span><span class="sxs-lookup"><span data-stu-id="af2d7-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="af2d7-114">DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in DKIM-Signature koptekst van de berichtkoppen.</span><span class="sxs-lookup"><span data-stu-id="af2d7-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="af2d7-115">De resultaten van een DKIM-Signature worden in de koptekst van Authentication-Results stempel voorzien.</span><span class="sxs-lookup"><span data-stu-id="af2d7-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="af2d7-116">De tekst van de berichtkop ziet er ongeveer als volgt uit (contoso.com afzender is):</span><span class="sxs-lookup"><span data-stu-id="af2d7-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="af2d7-117">Zie RFC 7001 (berichtkopveld voor het[](https://www.rfc-editor.org/rfc/rfc7001.txt)aangeven van de status van de berichtverificatie) voor meer informatie over Authentication-Results berichtkoptekst.</span><span class="sxs-lookup"><span data-stu-id="af2d7-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="af2d7-118">De DKIM-implementatie van Microsoft voldoet aan deze RFC.</span><span class="sxs-lookup"><span data-stu-id="af2d7-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="af2d7-119">Beheerders kunnen Exchange-regels voor [de e-mailstroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) maken voor de resultaten van DKIM-validatie.</span><span class="sxs-lookup"><span data-stu-id="af2d7-119">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="af2d7-120">Met deze regels voor de e-mailstroom kunnen beheerders berichten filteren of routeeren naar behoefte.</span><span class="sxs-lookup"><span data-stu-id="af2d7-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
