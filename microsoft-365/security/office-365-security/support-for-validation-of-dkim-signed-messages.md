---
title: Ondersteuning voor validatie van de domein sleutels met een ondertekende e-mail adres (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Meer informatie over het valideren van DKIM ondertekende berichten in Exchange Online Protection en Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845057"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="30067-103">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="30067-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="30067-104">Exchange Online Protection (EOP) en Exchange Online ondersteunen beide inkomende verificatie van domein sleutels geïdentificeerde E-mail ([dkim](https://www.rfc-editor.org/rfc/rfc6376.txt))-berichten.</span><span class="sxs-lookup"><span data-stu-id="30067-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="30067-105">DKIM valideert dat een e-mailbericht niet door iemand anders is *vervalst* en is verzonden vanaf het domein *waarnaar wordt aangegeven dat het e* -mailbericht afkomstig is.</span><span class="sxs-lookup"><span data-stu-id="30067-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="30067-106">Met deze functie wordt een e-mailbericht verzonden naar de organisatie die het heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="30067-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="30067-107">DKIM-verificatie wordt automatisch gebruikt voor alle berichten die met IPv6 worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="30067-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="30067-108">Microsoft 365 ondersteunt ook DKIM wanneer e-mail wordt verzonden via IPv4.</span><span class="sxs-lookup"><span data-stu-id="30067-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="30067-109">(Zie [ondersteuning voor anonieme inkomende e-mailberichten via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)) voor meer informatie over IPv6-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="30067-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="30067-110">DKIM controleert een digitaal ondertekend bericht dat wordt weergegeven in de koptekst DKIM-Signature van de berichtkoppen.</span><span class="sxs-lookup"><span data-stu-id="30067-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="30067-111">De resultaten van een DKIM-Signature validatie worden in de Authentication-Results koptekst vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="30067-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="30067-112">De kop van het bericht wordt weergegeven op de volgende manier (waarbij contoso.com de afzender is):</span><span class="sxs-lookup"><span data-stu-id="30067-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="30067-113">Als u meer wilt weten over de koptekst van Authentication-Results, raadpleegt u RFC 7001 ([berichtkop veld voor het aangeven van de status van de berichtverificatie](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="30067-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="30067-114">De DKIM-implementatie van Microsoft vervalt met deze RFC'S.</span><span class="sxs-lookup"><span data-stu-id="30067-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="30067-115">Beheerders kunnen Exchange [-e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) maken (ook wel een zogenaamde transportregels genoemd) op de resultaten van de validatie van dkim.</span><span class="sxs-lookup"><span data-stu-id="30067-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="30067-116">Met deze regels voor e-mail stroom kunnen beheerders berichten naar wens filteren of routeren.</span><span class="sxs-lookup"><span data-stu-id="30067-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
