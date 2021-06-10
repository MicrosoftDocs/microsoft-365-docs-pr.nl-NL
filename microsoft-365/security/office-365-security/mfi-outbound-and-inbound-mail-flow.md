---
title: Inzicht in uitgaande en binnenkomende e-mailstroom in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Beheerders kunnen meer informatie krijgen over het inzicht in uitgaande en binnenkomende e-mailstroom in het e-mailstroomdashboard in het beveiligings- & Compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204135"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="934b8-103">Inzicht in uitgaande en binnenkomende e-mailstroom in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="934b8-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="934b8-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="934b8-104">**Applies to**</span></span>
- [<span data-ttu-id="934b8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="934b8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="934b8-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="934b8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="934b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="934b8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="934b8-108">Het inzicht in uitgaande en **binnenkomende** e-mailstroom in het E-mailstroomdashboard in het [](mail-flow-insights-v2.md) [Beveiligings- & Compliancecentrum](https://protection.office.com) combineert de gegevens uit het [connectorrapport](view-mail-flow-reports.md#connector-report) en het voormalige **TLS-overzichtsrapport** op één plaats.</span><span class="sxs-lookup"><span data-stu-id="934b8-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="934b8-109">De widget bevat de TLS-versleuteling die wordt gebruikt voor de verbinding wanneer berichten van en naar uw organisatie worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="934b8-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="934b8-110">De verbindingen die zijn tot stand gebracht met andere e-mailservices, worden versleuteld door TLS wanneer TLS door beide zijden wordt aangeboden.</span><span class="sxs-lookup"><span data-stu-id="934b8-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="934b8-111">De widget biedt een momentopname van de laatste week van de e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="934b8-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget Uitgaande en binnenkomende e-mailstroom in het e-mailstroomdashboard in & Compliance center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="934b8-113">De informatie in de widget is gerelateerd aan verbindingslijnen en TLS-berichtbeveiliging in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="934b8-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="934b8-114">Zie deze onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="934b8-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="934b8-115">E-mailstroom configureren met behulp van verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="934b8-115">Configure mail flow using connectors</span></span>](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="934b8-116">Hoe Exchange Online TLS gebruikt om e-mailverbindingen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="934b8-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="934b8-117">Technische naslaginformatie over versleuteling in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="934b8-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="934b8-118">Bericht beveiligd tijdens doorvoer (met TLS)</span><span class="sxs-lookup"><span data-stu-id="934b8-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="934b8-119">Wanneer u op **Details weergeven** op de widget klikt, wordt in het flyout Bericht beveiligd tijdens doorvoer **(door TLS)** de TLS-beveiliging weergegeven voor berichten die uw organisatie binnenkomen en verlaten.</span><span class="sxs-lookup"><span data-stu-id="934b8-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Beveiligde berichten tijdens doorvoer (met TLS)-flyout die wordt weergegeven nadat u op Details weergeven hebt geklikt in de widget Uitgaande en binnenkomende e-mail](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="934b8-121">Op dit moment is TLS 1.2 de veiligste versie van TLS die wordt aangeboden door Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="934b8-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="934b8-122">Vaak moet u de TLS-versleuteling kennen die wordt gebruikt voor nalevingscontroles.</span><span class="sxs-lookup"><span data-stu-id="934b8-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="934b8-123">U hebt waarschijnlijk geen directe relatie met de meeste bron- en doel-e-mailservers (u bent niet de eigenaar van deze servers en Microsoft ook niet), dus u hebt niet veel opties om de TLS-versleuteling te verbeteren die door deze servers wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="934b8-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="934b8-124">U kunt echter [verbindingslijnen gebruiken](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) om de best beschikbare TLS-beveiliging te garanderen voor berichten die tussen uw e-mailservers en e-mailservers Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="934b8-124">But, you can use [connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="934b8-125">E-mailstroom tussen Microsoft 365 en uw eigen e-mailservers of servers die deel uitmaken van uw partners is vaak belangrijker en gevoeliger dan gewone berichten, dus u wilt extra beveiliging en waakzaamheid toepassen op deze berichten.</span><span class="sxs-lookup"><span data-stu-id="934b8-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="934b8-126">U kunt uw eigen e-mailservers upgraden of herstellen om de TLS-versleuteling te verbeteren die wordt gebruikt, of contact op te zoeken met uw partners om hetzelfde te doen.</span><span class="sxs-lookup"><span data-stu-id="934b8-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="934b8-127">In **het connectorrapport** worden zowel het volume van de e-mailstroom als de TLS-versleuteling weergegeven voor berichten die gebruikmaken van Microsoft 365 connectors.</span><span class="sxs-lookup"><span data-stu-id="934b8-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="934b8-128">U kunt op de **koppeling Verbindingslijnrapport** klikken om naar het [connectorrapport te gaan.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="934b8-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="934b8-129">De volgende inzichten zijn mogelijk beschikbaar op de rapportpagina **Connector** als de bijbehorende voorwaarde is gedetecteerd:</span><span class="sxs-lookup"><span data-stu-id="934b8-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="934b8-130">**Inkomende partnerconnector ziet significante TLS1.0-e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="934b8-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="934b8-131">**Inkomende OnPremises-connector met significante TLS1.0-e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="934b8-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="934b8-132">Voor TLS 1.0-verbindingen moet u uw e-mailserver of de server van uw partner echt upgraden of oplossen om problemen te voorkomen wanneer TLS 1.0-ondersteuning uiteindelijk wordt afgeschaft in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="934b8-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="934b8-133">Zie ook</span><span class="sxs-lookup"><span data-stu-id="934b8-133">See also</span></span>

<span data-ttu-id="934b8-134">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="934b8-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>