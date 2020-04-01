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
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083639"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="a7f4d-103">Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6 in Office 365</span><span class="sxs-lookup"><span data-stu-id="a7f4d-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="a7f4d-104">Office 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme binnenkomende e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="a7f4d-105">De e-mailserver van de bron-IPv6 moet aan beide volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="a7f4d-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="a7f4d-106">Het bron-IPv6-adres moet een geldige reverse DNS lookup (PTR)-record hebben waarmee de bestemming de domeinnaam kan vinden vanaf het IPv6-adres.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="a7f4d-107">De afzender moet slagen voor spf-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="a7f4d-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="a7f4d-108">Voordat uw organisatie anonieme binnenkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en erom vragen:</span><span class="sxs-lookup"><span data-stu-id="a7f4d-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="a7f4d-109">Open het Microsoft 365-beheercentrum bij <https://admin.microsoft.com/adminportal/home> en klik op **Help** (?).</span><span class="sxs-lookup"><span data-stu-id="a7f4d-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="a7f4d-110">Typ in de **help nodig?** flyout die wordt weergegeven, typ iets beschrijvends in het zoekvak (bijvoorbeeld 'vraag anonieme inkomende IPv6-e-mail' aan en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="a7f4d-111">Klik onder aan de pagina op **Ondersteuning voor contact opnemen**.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="a7f4d-112">Vul op de **ondersteuningspagina Van contact** die wordt weergegeven de gegevens in en verifieer deze (scroll naar beneden als dat nodig is) en klik vervolgens op **Contact met mij**opnemen.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="a7f4d-113">Nadat anonieme inkomende IPv6-berichtondersteuning is ingeschakeld in uw organisatie, wordt het bericht door de normale berichtfiltering uitgevoerd die door de service wordt geleverd.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a7f4d-114">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="a7f4d-114">Troubleshooting</span></span>

- <span data-ttu-id="a7f4d-115">Als de brone-mailserver geen IPv6 reverse DNS-opzoekrecord heeft, worden de berichten met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="a7f4d-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="a7f4d-116">450 4.7.25 Service niet beschikbaar, het verzenden van IPv6-adres [2a01:111:f200:2004::240] moet een omgekeerd DNS-record hebben.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="a7f4d-117">Als de afzender de SPF- of DKIM-validatie niet doorstaat, worden de berichten met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="a7f4d-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="a7f4d-118">450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet slagen voor SPF- of DKIM-validatie.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="a7f4d-119">Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt aangemeld, wordt het bericht met de volgende fout geweigerd:</span><span class="sxs-lookup"><span data-stu-id="a7f4d-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="a7f4d-120">550 5.2.1 Service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.</span><span class="sxs-lookup"><span data-stu-id="a7f4d-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a7f4d-121">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="a7f4d-121">For more information</span></span>

[<span data-ttu-id="a7f4d-122">Ondersteuning voor validatie van ondertekende DKIM-berichten</span><span class="sxs-lookup"><span data-stu-id="a7f4d-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
