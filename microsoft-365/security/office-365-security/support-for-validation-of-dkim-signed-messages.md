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
description: Meer informatie over de validatie van door DKIM ondertekende berichten in Exchange Online Protection en Exchange Online
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631203"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="10cf5-103">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="10cf5-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="10cf5-104">Exchange Online Protection (EOP) en Exchange Online ondersteunen inkomende validatie van[DKIM-berichten (Domain](https://www.rfc-editor.org/rfc/rfc6376.txt)Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="10cf5-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="10cf5-105">DKIM is een methode om te valideren dat een bericht is verzonden vanuit het domein waarvan staat dat het afkomstig is van en dat het niet door iemand anders is vervalst.</span><span class="sxs-lookup"><span data-stu-id="10cf5-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="10cf5-106">Het koppelt een e-mailbericht aan de organisatie die verantwoordelijk is voor het verzenden van het.</span><span class="sxs-lookup"><span data-stu-id="10cf5-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="10cf5-107">DKIM-verificatie wordt automatisch gebruikt voor alle berichten die via IPv6-communicatie worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="10cf5-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="10cf5-108">Microsoft 365 ondersteunt nu ook DKIM wanneer e-mail via IPv4 wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="10cf5-108">Microsoft 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="10cf5-109">(Zie [Ondersteuning voor anonieme binnenkomende e-mailberichten via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)voor meer informatie over IPv6-ondersteuning.)</span><span class="sxs-lookup"><span data-stu-id="10cf5-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="10cf5-110">DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in de header DKIM-Signature in de berichtkoppen.</span><span class="sxs-lookup"><span data-stu-id="10cf5-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers.</span></span> <span data-ttu-id="10cf5-111">De resultaten van een DKIM-Signature-validatie worden gestempeld in de header Verificatieresultaten die voldoet aan RFC 7001[(Message Header Field for Indicating Message Authentication Status).](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="10cf5-111">The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)).</span></span> <span data-ttu-id="10cf5-112">De tekst van de berichtkoptekst wordt weergegeven als de volgende tekst (waarbij contoso.com de afzender is):</span><span class="sxs-lookup"><span data-stu-id="10cf5-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="10cf5-113">Beheerders kunnen [Exchange-mailstroomregels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) maken voor de resultaten van een DKIM-validatie om berichten te filteren of te routeren als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="10cf5-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
