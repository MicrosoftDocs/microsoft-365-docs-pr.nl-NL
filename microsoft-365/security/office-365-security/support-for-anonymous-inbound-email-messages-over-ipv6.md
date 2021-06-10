---
title: Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerder kan informatie krijgen over het configureren van ondersteuning voor anonieme inkomende e-mail uit IPv6-bronnen in Exchange Online en Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300047"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="2252b-103">Ondersteuning toevoegen voor anonieme inkomende e-mail via IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2252b-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2252b-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2252b-104">**Applies to**</span></span>
- [<span data-ttu-id="2252b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2252b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2252b-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2252b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2252b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2252b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2252b-108">Microsoft 365 organisaties met Exchange Online postvakken en zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online ondersteunen anonieme inkomende e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="2252b-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="2252b-109">De bron-IPv6-e-mailserver moet aan beide van de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="2252b-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="2252b-110">Het bron-IPv6-adres moet een geldige PTR-record (Reverse DNS Lookup) hebben waarmee de bestemming de domeinnaam kan vinden op het IPv6-adres.</span><span class="sxs-lookup"><span data-stu-id="2252b-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="2252b-111">De afzender moet SPF-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](http://dkim.org/) (gedefinieerd in [RFC 6376) doorgeven.](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="2252b-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="2252b-112">Voordat uw organisatie anonieme inkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en om deze vragen.</span><span class="sxs-lookup"><span data-stu-id="2252b-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="2252b-113">Zie Contact opnemen met ondersteuning voor zakelijke producten - Help voor beheerders voor instructies over het openen van een [ondersteuningsaanvraag.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="2252b-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span></span>

<span data-ttu-id="2252b-114">Nadat anonieme inkomende IPv6-berichtondersteuning is ingeschakeld in uw organisatie, wordt het bericht door de normale berichtenfilters van de service gefilterd.</span><span class="sxs-lookup"><span data-stu-id="2252b-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2252b-115">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="2252b-115">Troubleshooting</span></span>

- <span data-ttu-id="2252b-116">Als de bron-e-mailserver geen reverse DNS-opzoekrecord voor IPv6 heeft, worden de berichten met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="2252b-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="2252b-117">450 4.7.25 Service niet beschikbaar, verzenden van IPv6-adres [2a01:111:f200:2004::240] moet reverse DNS-record hebben.</span><span class="sxs-lookup"><span data-stu-id="2252b-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="2252b-118">Als de afzender niet door SPF of DKIM-validatie komt, worden de berichten met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="2252b-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="2252b-119">450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet SPF- of DKIM-validatie passeren.</span><span class="sxs-lookup"><span data-stu-id="2252b-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="2252b-120">Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt afgemeld, wordt het bericht met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="2252b-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="2252b-121">550 5.2.1 Service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="2252b-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2252b-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2252b-122">Related topics</span></span>

[<span data-ttu-id="2252b-123">Ondersteuning voor validatie van DKIM-ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="2252b-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
