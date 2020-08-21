---
title: Uitgaand en binnenkomende e-mail stroom inzichtelijk in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Beheerders kunnen inzicht krijgen in de uitgaand en binnenkomende e-mail stroom informatie in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum.
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826891"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="e407c-103">Uitgaand en binnenkomende e-mail stroom inzicht in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="e407c-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="e407c-104">De **uitgaande en binnenkomende e-mail stroom** informatie in het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de beveiligings & nalevings centrum combineert de informatie uit het [verbindings rapport](view-mail-flow-reports.md#connector-report) en het voormalige **TLS-overzichtsrapport** op één plaats.</span><span class="sxs-lookup"><span data-stu-id="e407c-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="e407c-105">Het object geeft de TLS-versleuteling weer die wordt gebruikt voor de verbinding wanneer berichten worden bezorgd en van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e407c-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="e407c-106">De verbindingen die zijn gemaakt met andere e-mailservices, worden versleuteld door TLS wanneer TLS aan beide kanten wordt aangeboden.</span><span class="sxs-lookup"><span data-stu-id="e407c-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="e407c-107">De widget biedt een momentopname van de laatste week van de e-mail stroom.</span><span class="sxs-lookup"><span data-stu-id="e407c-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Uitgaande en binnenkomende e-mail stroom widget in het dashboard voor e-mail stroom in het Beveiligingscentrum beveiligings &](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="e407c-109">De gegevens in de widget hebben betrekking op connectors en TLS-berichtbeveiliging in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e407c-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="e407c-110">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="e407c-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="e407c-111">De e-mail stroom configureren met connectors</span><span class="sxs-lookup"><span data-stu-id="e407c-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="e407c-112">Hoe Exchange Online TLS gebruikt om verbinding te maken met e-mail verbindingen</span><span class="sxs-lookup"><span data-stu-id="e407c-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="e407c-113">Technische naslaginformatie over versleuteling in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e407c-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="e407c-114">Bericht beveiligd in transit (via TLS)</span><span class="sxs-lookup"><span data-stu-id="e407c-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="e407c-115">Wanneer u klikt op **Details weergeven** in de widget, ziet u in het bericht met de **tekst in het bericht in transit (per TLS)** de TLS-beveiliging voor berichten die uw organisatie binnenkomen en verlaten.</span><span class="sxs-lookup"><span data-stu-id="e407c-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Berichten die zijn beveiligd in de Transit (door TLS) flyout, die worden weergegeven nadat u op Details weergeven hebt geklikt in de widget uitgaande en binnenkomende e-mail](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="e407c-117">Op dit moment TLS 1,2 is de veiligste versie van TLS die wordt aangeboden door Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e407c-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="e407c-118">Vaak moet u weten wat de TLS-codering is die wordt gebruikt voor nalevingscontroles.</span><span class="sxs-lookup"><span data-stu-id="e407c-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="e407c-119">U hebt waarschijnlijk geen rechtstreekse relatie met de meeste bron-en doel-e-mailservers (u bezit ze niet, en hebt geen Microsoft), dus hebt u niet veel opties om de TLS-versleuteling te verbeteren die door die servers wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e407c-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="e407c-120">U kunt echter ook gebruikmaken van [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) om te zorgen dat u de beste beschikbare TLS-beveiliging voor berichten die zijn verzonden tussen uw e-mailservers en microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e407c-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="e407c-121">De e-mail stroom tussen Microsoft 365 en uw eigen e-mailservers of servers die deel uitmaken van uw partners, is vaak belangrijker en gevoeliger dan gewone berichten, dus wilt u extra beveiliging en waakzaamheid op deze berichten toepassen.</span><span class="sxs-lookup"><span data-stu-id="e407c-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="e407c-122">U kunt een upgrade uitvoeren naar uw eigen e-mailservers of deze oplossing voor het verbeteren van de gebruikte TLS-versleuteling of contact opnemen met uw partners.</span><span class="sxs-lookup"><span data-stu-id="e407c-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="e407c-123">In het **rapport connector** ziet u het e-mail stroom volume en de TLS-versleuteling voor berichten die gebruikmaken van uw microsoft 365-connectors.</span><span class="sxs-lookup"><span data-stu-id="e407c-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="e407c-124">U kunt klikken op de koppeling van het **verbindingslijn** om naar het [verbindings rapport](view-mail-flow-reports.md#connector-report)te gaan.</span><span class="sxs-lookup"><span data-stu-id="e407c-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="e407c-125">Mogelijk zijn de volgende inzichten beschikbaar op de pagina van het **connector rapport** als de bijbehorende voorwaarde is gedetecteerd:</span><span class="sxs-lookup"><span data-stu-id="e407c-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="e407c-126">**Binnenkomende partner connector met significante TLS 1.0-e-mail stroom**</span><span class="sxs-lookup"><span data-stu-id="e407c-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="e407c-127">**Binnenkomende OnPremises-connector met significante TLS 1.0-e-mail stroom**</span><span class="sxs-lookup"><span data-stu-id="e407c-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="e407c-128">Voor TLS 1,0-verbindingen moet u eerst uw e-mailserver of de server van uw partner of een upgrade naar de server of een oplossing voorkomen, zodat er geen problemen worden weergegeven wanneer TLS 1,0 voor ondersteuning in Microsoft 365 uiteindelijk is afgeschaft.</span><span class="sxs-lookup"><span data-stu-id="e407c-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="e407c-129">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e407c-129">See also</span></span>

<span data-ttu-id="e407c-130">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="e407c-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
