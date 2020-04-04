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
description: Beheerder kan in Exchange Online en Exchange Online Protection leren hoe u ondersteuning configureert voor anonieme binnenkomende e-mail van IPv6-bronnen.
ms.openlocfilehash: 414c10f3387138ed7e62f2de4e8549e45d128d2e
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131517"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="7720e-103">Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6 in Office 365</span><span class="sxs-lookup"><span data-stu-id="7720e-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="7720e-104">Office 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme binnenkomende e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="7720e-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="7720e-105">De e-mailserver van de bron-IPv6 moet aan beide volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="7720e-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="7720e-106">Het bron-IPv6-adres moet een geldige reverse DNS lookup (PTR)-record hebben waarmee de bestemming de domeinnaam kan vinden vanaf het IPv6-adres.</span><span class="sxs-lookup"><span data-stu-id="7720e-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="7720e-107">De afzender moet slagen voor spf-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="7720e-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="7720e-108">Voordat uw organisatie anonieme binnenkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en erom vragen.</span><span class="sxs-lookup"><span data-stu-id="7720e-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="7720e-109">Zie [Contact opnemen met ondersteuning voor zakelijke producten - Help voor beheerders](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="7720e-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="7720e-110">Nadat anonieme inkomende IPv6-berichtondersteuning is ingeschakeld in uw organisatie, wordt het bericht door de normale berichtfiltering uitgevoerd die door de service wordt geleverd.</span><span class="sxs-lookup"><span data-stu-id="7720e-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7720e-111">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="7720e-111">Troubleshooting</span></span>

- <span data-ttu-id="7720e-112">Als de brone-mailserver geen IPv6 reverse DNS-opzoekrecord heeft, worden de berichten met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="7720e-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="7720e-113">450 4.7.25 Service niet beschikbaar, het verzenden van IPv6-adres [2a01:111:f200:2004::240] moet een omgekeerd DNS-record hebben.</span><span class="sxs-lookup"><span data-stu-id="7720e-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="7720e-114">Als de afzender de SPF- of DKIM-validatie niet doorstaat, worden de berichten met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="7720e-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="7720e-115">450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet slagen voor SPF- of DKIM-validatie.</span><span class="sxs-lookup"><span data-stu-id="7720e-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="7720e-116">Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt aangemeld, wordt het bericht met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="7720e-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="7720e-117">550 5.2.1 Service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="7720e-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="7720e-118">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="7720e-118">For more information</span></span>

[<span data-ttu-id="7720e-119">Ondersteuning voor validatie van ondertekende DKIM-berichten</span><span class="sxs-lookup"><span data-stu-id="7720e-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
