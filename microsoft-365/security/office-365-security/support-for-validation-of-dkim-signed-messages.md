---
title: Ondersteuning voor validatie van DKIM-ondertekende berichten (Domain Keys Identified Mail)
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
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204630"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="adafd-103">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="adafd-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="adafd-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="adafd-104">**Applies to**</span></span>
- [<span data-ttu-id="adafd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="adafd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="adafd-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="adafd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="adafd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adafd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="adafd-108">Exchange Online Protection (EOP) en Exchange Online ondersteunen zowel inkomende validatie van[DKIM-berichten](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="adafd-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="adafd-109">DKIM valideert dat een e-mailbericht niet is vervalst door iemand anders en is verzonden vanuit het domein *waar* het vandaan komt. </span><span class="sxs-lookup"><span data-stu-id="adafd-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="adafd-110">Er wordt een e-mailbericht aan de organisatie verbonden die het heeft verzonden.</span><span class="sxs-lookup"><span data-stu-id="adafd-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="adafd-111">DKIM-verificatie wordt automatisch gebruikt voor alle berichten die met IPv6 worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="adafd-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="adafd-112">Microsoft 365 ondersteunt ook DKIM wanneer e-mail wordt verzonden via IPv4.</span><span class="sxs-lookup"><span data-stu-id="adafd-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="adafd-113">(Zie Ondersteuning voor anonieme inkomende e-mailberichten [via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)voor meer informatie over IPv6-ondersteuning .)</span><span class="sxs-lookup"><span data-stu-id="adafd-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="adafd-114">DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in de DKIM-Signature koptekst van de berichtkoppen.</span><span class="sxs-lookup"><span data-stu-id="adafd-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="adafd-115">De resultaten van een DKIM-Signature validatie worden gestempeld in de Authentication-Results koptekst.</span><span class="sxs-lookup"><span data-stu-id="adafd-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="adafd-116">De tekst van de berichtkoptekst lijkt op het volgende (waarbij contoso.com afzender is):</span><span class="sxs-lookup"><span data-stu-id="adafd-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="adafd-117">Zie RFC 7001 (Veld voor berichtkoptekst voor het aangeven van de status van berichtverificatie) voor meer informatie over de Authentication-Results[koptekst.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="adafd-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="adafd-118">De DKIM-implementatie van Microsoft voldoet aan deze RFC.</span><span class="sxs-lookup"><span data-stu-id="adafd-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="adafd-119">Beheerders kunnen Exchange [regels](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor e-mailstroom (ook wel transportregels genoemd) maken op de resultaten van DKIM-validatie.</span><span class="sxs-lookup"><span data-stu-id="adafd-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="adafd-120">Met deze regels voor e-mailstroom kunnen beheerders berichten zo nodig filteren of doorgestuurd worden.</span><span class="sxs-lookup"><span data-stu-id="adafd-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>