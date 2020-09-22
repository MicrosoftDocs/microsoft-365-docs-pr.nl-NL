---
title: Ondersteuning voor validatie van DKIM-ondertekende berichten
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
ms.openlocfilehash: e2e91fe426348487fa4dfa8ef929d2d8129ffddc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202135"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="2b049-103">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="2b049-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2b049-104">Exchange Online Protection (EOP) en Exchange Online ondersteuning voor inkomende verificatie van domein sleutels geïdentificeerde e-mail berichten ([dkim](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="2b049-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="2b049-105">DKIM is een methode waarmee wordt gecontroleerd of een bericht is verzonden vanaf het domein waaruit het is afgeleid en dat het niet door iemand anders is vervalst.</span><span class="sxs-lookup"><span data-stu-id="2b049-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="2b049-106">U ontvangt een e-mailbericht aan de organisatie die verantwoordelijk is voor het verzenden van het bericht.</span><span class="sxs-lookup"><span data-stu-id="2b049-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="2b049-107">DKIM-verificatie wordt automatisch gebruikt voor alle berichten die via IPv6-communicatie worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="2b049-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="2b049-108">Microsoft 365 biedt nu ondersteuning voor DKIM wanneer mail wordt verzonden via IPv4.</span><span class="sxs-lookup"><span data-stu-id="2b049-108">Microsoft 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="2b049-109">(Zie [ondersteuning voor anonieme inkomende e-mailberichten via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)) voor meer informatie over IPv6-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="2b049-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="2b049-110">DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in de koptekst DKIM-Signature in de berichtkoppen.</span><span class="sxs-lookup"><span data-stu-id="2b049-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers.</span></span> <span data-ttu-id="2b049-111">De resultaten van de validatie van een DKIM-handtekening worden voorzien van een stempel in de header voor verificatie-resultaten die voldoet aan de RFC'S 7001 ([bericht veldnamen veld waarmee de status van de berichtverificatie wordt aangegeven](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span><span class="sxs-lookup"><span data-stu-id="2b049-111">The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span></span> <span data-ttu-id="2b049-112">De kop van het bericht wordt weergegeven op de volgende manier (waarbij contoso.com de afzender is):</span><span class="sxs-lookup"><span data-stu-id="2b049-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="2b049-113">Beheerders kunnen Exchange [-e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel de zogenaamde transportregels genoemd) maken op de resultaten van een dkim-validatie om berichten naar wens te filteren of te routeren.</span><span class="sxs-lookup"><span data-stu-id="2b049-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
