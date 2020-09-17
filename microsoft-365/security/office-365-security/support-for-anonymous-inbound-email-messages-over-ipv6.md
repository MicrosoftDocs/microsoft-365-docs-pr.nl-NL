---
title: Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: De beheerder kan leren hoe u ondersteuning configureert voor anonieme inkomende e-mail van IPv6-bronnen in Exchange Online en Exchange Online Protection.
ms.openlocfilehash: f2e14fe2e8e46d6085fc3764d3a41382f15049e9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950292"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="2d393-103">Ondersteuning toevoegen voor anonieme inkomende e-mail via IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d393-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="2d393-104">Microsoft 365-organisaties met postvakken van Exchange Online en standalone Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme inkomende e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="2d393-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="2d393-105">De e-mailserver voor bron IPv6 moet aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="2d393-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="2d393-106">Het bron-IPv6-adres moet een geldige DNS-opzoek record (PTR) bevatten waarmee de bestemming de domeinnaam van het IPv6-adres kan vinden.</span><span class="sxs-lookup"><span data-stu-id="2d393-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="2d393-107">De afzender moet authenticatie via SPF (gedefinieerd in [rfc 7208](https://tools.ietf.org/html/rfc7208)) of [dkim-verificatie](http://dkim.org/) (gedefinieerd in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) passeren.</span><span class="sxs-lookup"><span data-stu-id="2d393-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="2d393-108">Voordat uw organisatie anonieme inkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met Microsoft ondersteuning en vragen.</span><span class="sxs-lookup"><span data-stu-id="2d393-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="2d393-109">Zie [contact opnemen met ondersteuning voor bedrijfsproducten-Help voor beheerders](../../admin/contact-support-for-business-products.md)voor meer informatie over het openen van een ondersteuningsaanvraag.</span><span class="sxs-lookup"><span data-stu-id="2d393-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="2d393-110">Wanneer anoniem e-mailbericht ondersteuning voor anonieme ondersteuning in uw organisatie is ingeschakeld, wordt het bericht weergegeven met het filter voor normale berichten dat wordt geleverd door de service.</span><span class="sxs-lookup"><span data-stu-id="2d393-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2d393-111">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="2d393-111">Troubleshooting</span></span>

- <span data-ttu-id="2d393-112">Als de bron-e-mailserver geen IPv6-lookup record voor IPv6 bevat, worden de berichten genegeerd met de volgende fout:</span><span class="sxs-lookup"><span data-stu-id="2d393-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="2d393-113">de 4.7.25-service van 450 is niet beschikbaar en het verzenden van IPv6-adres [2a01:111: F200:2004:: 240] moet omgekeerde DNS-record hebben.</span><span class="sxs-lookup"><span data-stu-id="2d393-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="2d393-114">Als de afzender SPF-of DKIM-validatie niet doorgeeft, worden de berichten genegeerd met de volgende fout:</span><span class="sxs-lookup"><span data-stu-id="2d393-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="2d393-115">450 4.7.26 service niet beschikbaar, bericht verzonden via IPv6 [2a01:120: F200:2004:: 240] moet SPF-of DKIM validering passeren.</span><span class="sxs-lookup"><span data-stu-id="2d393-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="2d393-116">Als u probeert anonieme IPv6-berichten te ontvangen voordat u zich aanmeldt, wordt het bericht genegeerd met de volgende fout:</span><span class="sxs-lookup"><span data-stu-id="2d393-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="2d393-117">550 5.2.1-service niet beschikbaar, [contoso.com] aanvaardt geen e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="2d393-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d393-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2d393-118">Related topics</span></span>

[<span data-ttu-id="2d393-119">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="2d393-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)