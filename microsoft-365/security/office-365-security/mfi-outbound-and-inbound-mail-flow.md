---
title: Inzichten in de uitgaande en binnenkomende e-mailstroom in het dashboard E-mailstroom
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
description: Beheerders kunnen meer informatie krijgen over het inzicht in de stroom voor uitgaande en binnenkomende e-mail in het dashboard E-mailstroom in het & compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcce6981369217f21ace5fdf2abbf23ca8606569
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150806"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="abaed-103">Inzichten in de uitgaande en binnenkomende e-mailstroom in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="abaed-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="abaed-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="abaed-104">**Applies to**</span></span>
- [<span data-ttu-id="abaed-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="abaed-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="abaed-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="abaed-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="abaed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abaed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="abaed-108">Het inzicht in de uitgaande en **binnenkomende e-mailstroom** in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) combineert de informatie uit het [rapport Connector](view-mail-flow-reports.md#connector-report) en het voormalige overzichtsrapport **TLS** op één plaats.</span><span class="sxs-lookup"><span data-stu-id="abaed-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="abaed-109">In de widget wordt de TLS-versleuteling weergegeven die wordt gebruikt voor de verbinding wanneer berichten worden bezorgd bij en van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="abaed-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="abaed-110">De verbindingen die tot stand worden gebracht met andere e-mailservices worden versleuteld door TLS wanneer TLS door beide zijden wordt aangeboden.</span><span class="sxs-lookup"><span data-stu-id="abaed-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="abaed-111">De widget bevat een momentopname van de laatste week van de e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="abaed-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget Voor uitgaande en binnenkomende e-mailstroom in het dashboard E-mailstroom in het & compliancecentrum](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="abaed-113">De informatie in de widget heeft betrekking op connectors en TLS-berichtbeveiliging in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="abaed-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="abaed-114">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="abaed-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="abaed-115">E-mailstroom configureren met connectors</span><span class="sxs-lookup"><span data-stu-id="abaed-115">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="abaed-116">Exchange Online gebruikt TLS om e-mailverbindingen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="abaed-116">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="abaed-117">Technische naslaginformatie over versleuteling in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="abaed-117">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="abaed-118">Bericht wordt tijdens overdracht beveiligd (door TLS)</span><span class="sxs-lookup"><span data-stu-id="abaed-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="abaed-119">Wanneer u op **Details weergeven** in de widget klikt, wordt in de flyout Bericht beveiligd tijdens **overdracht (met TLS) TLS-beveiliging** weergegeven voor berichten die worden weergegeven voor berichten die worden weergegeven bij het invoeren en verlaten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="abaed-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Flyout Berichten die tijdens het verzenden zijn beveiligd (met TLS) wordt weergegeven nadat u op Details weergeven hebt geklikt in de widget Voor uitgaande en binnenkomende e-mail](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="abaed-121">Op dit moment is TLS 1.2 de veiligste versie van TLS die wordt aangeboden door Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="abaed-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="abaed-122">Vaak moet u de TLS-versleuteling kennen die wordt gebruikt voor nalevingscontroles.</span><span class="sxs-lookup"><span data-stu-id="abaed-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="abaed-123">U hebt waarschijnlijk geen directe relatie met de meeste bron- en doel-e-mailservers (u bent niet de eigenaar en Microsoft ook niet). U hebt dus niet veel opties om de TLS-versleuteling te verbeteren die door deze servers wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="abaed-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="abaed-124">Maar u kunt [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) gebruiken om ervoor te zorgen dat berichten die tussen uw e-mailservers en Microsoft 365 worden verzonden, de beste TLS-beveiliging bieden.</span><span class="sxs-lookup"><span data-stu-id="abaed-124">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="abaed-125">De e-mailstroom tussen Microsoft 365 en uw eigen e-mailservers of -servers die tot uw partners behoren, is vaak belangrijker en gevoeliger dan normale berichten, dus u zult extra beveiliging en beveiliging op deze berichten willen toepassen.</span><span class="sxs-lookup"><span data-stu-id="abaed-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="abaed-126">U kunt uw eigen e-mailservers upgraden of herstellen om de TLS-versleuteling te verbeteren die wordt gebruikt, of contact op met uw partners om hetzelfde te doen.</span><span class="sxs-lookup"><span data-stu-id="abaed-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="abaed-127">In **het connectorrapport** worden zowel het volume van de e-mailstroom als de TLS-versleuteling weergegeven voor berichten die uw Microsoft 365-connectors gebruiken.</span><span class="sxs-lookup"><span data-stu-id="abaed-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="abaed-128">Klik op de koppeling **Rapport connector** om naar het rapport Connector [te gaan.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="abaed-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="abaed-129">De volgende inzichten zijn mogelijk beschikbaar op de rapportpagina **connector** als de bijbehorende voorwaarde is gedetecteerd:</span><span class="sxs-lookup"><span data-stu-id="abaed-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="abaed-130">**Binnenkomende partnerconnector ziet belangrijke TLS1.0-e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="abaed-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="abaed-131">**Binnenkomende OnPremises-connector ziet belangrijke TLS1.0-e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="abaed-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="abaed-132">Voor TLS 1.0-verbindingen moet u de e-mailserver of de server van uw partner upgraden of oplossen om problemen te voorkomen wanneer de ondersteuning voor TLS 1.0 uiteindelijk wordt afgeschaft in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="abaed-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="abaed-133">Zie ook</span><span class="sxs-lookup"><span data-stu-id="abaed-133">See also</span></span>

<span data-ttu-id="abaed-134">Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="abaed-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
