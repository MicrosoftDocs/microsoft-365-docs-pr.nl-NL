---
title: Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Admin kan leren hoe u ondersteuning voor anonieme binnenkomende e-mail van IPv6-bronnen configureert in Exchange Online en Exchange Online Protection.
ms.openlocfilehash: fbbcba3631c7b2a7060f07011c119ee973fdf4af
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818707"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="80310-103">Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="80310-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="80310-104">Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme binnenkomende e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="80310-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="80310-105">De iPv6-e-mailserver voor bron moet aan beide volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="80310-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="80310-106">Het bron-IPv6-adres moet een geldige REVERSE DNS-lookup (PTR)-record hebben waarmee de bestemming de domeinnaam kan vinden vanaf het IPv6-adres.</span><span class="sxs-lookup"><span data-stu-id="80310-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="80310-107">De afzender moet slagen voor de SPF-verificatie (gedefinieerd in [RFC 7208](https://tools.ietf.org/html/rfc7208)) of [de DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="80310-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="80310-108">Voordat uw organisatie anonieme binnenkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en erom vragen.</span><span class="sxs-lookup"><span data-stu-id="80310-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="80310-109">Zie [Contact opnemen met ondersteuning voor zakelijke producten - Help voor beheerders](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="80310-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="80310-110">Nadat anonieme ondersteuning voor binnenkomende IPv6-berichten is ingeschakeld in uw organisatie, gaat het bericht door de normale berichtfiltering die door de service wordt geleverd.</span><span class="sxs-lookup"><span data-stu-id="80310-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="80310-111">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="80310-111">Troubleshooting</span></span>

- <span data-ttu-id="80310-112">Als de brone-mailserver geen IPv6 reverse DNS-opzoekrecord heeft, worden de berichten geweigerd met de volgende fout:</span><span class="sxs-lookup"><span data-stu-id="80310-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="80310-113">450 4.7.25 Service niet beschikbaar, verzenden van IPv6-adres [2a01:111:f200:2004::240] moet reverse DNS-record hebben.</span><span class="sxs-lookup"><span data-stu-id="80310-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="80310-114">Als de afzender de SPF- of DKIM-validatie niet doorstaat, worden de berichten geweigerd met de volgende fout:</span><span class="sxs-lookup"><span data-stu-id="80310-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="80310-115">450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet SPF- of DKIM-validatie doorstaan.</span><span class="sxs-lookup"><span data-stu-id="80310-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="80310-116">Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt aangemeld, wordt het bericht geweigerd met de volgende fout:</span><span class="sxs-lookup"><span data-stu-id="80310-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="80310-117">550 5.2.1-service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="80310-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80310-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="80310-118">Related topics</span></span>

[<span data-ttu-id="80310-119">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="80310-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)