---
title: Wachtrijwaarschuwingen en wachtrijen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Beheerders kunnen meer te weten komen over wachtrijwaarschuwingen en wachtrijen in het dashboard voor e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: bc777e3c9764987dc72aa0407f19618bc26f7528
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805908"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="73d83-103">Wachtrijwaarschuwingen en wachtrijen</span><span class="sxs-lookup"><span data-stu-id="73d83-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="73d83-104">Wachtrijwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="73d83-104">Queue alerts</span></span>

<span data-ttu-id="73d83-105">Wanneer berichten niet vanuit uw Office 365-organisatie naar uw on-premises of partnere-e-mailservers kunnen worden verzonden met behulp van connectoren, staan de berichten in de wachtrij in Office 365.</span><span class="sxs-lookup"><span data-stu-id="73d83-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="73d83-106">Veelvoorkomende voorbeelden die deze voorwaarde veroorzaken zijn:</span><span class="sxs-lookup"><span data-stu-id="73d83-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="73d83-107">De connector is onjuist geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="73d83-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="73d83-108">Er zijn netwerk- of firewallwijzigingen geweest in uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="73d83-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="73d83-109">Office 365 blijft 24 uur opnieuw proberen om te worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="73d83-109">Office 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="73d83-110">Na 24 uur verlopen de berichten en worden ze teruggestuurd naar de afzenders in niet-leveringsrapporten (ook bekend als een NDR of bounceberichten).</span><span class="sxs-lookup"><span data-stu-id="73d83-110">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="73d83-111">Als het e-mailvolume in de wachtrij de vooraf gedefinieerde drempelwaarde overschrijdt (de standaardwaarde is 2000 berichten), zijn de waarschuwingen beschikbaar in het dashboard voor de e-mailstroom bij **Recente waarschuwingen**en ontvangen beheerders een e-mailmelding (naar hun alternatieve e-mailadres).</span><span class="sxs-lookup"><span data-stu-id="73d83-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="73d83-112">Zie de sectie **Wachtrijwaarschuwingen** aanpassen hieronder als u de waarschuwingsdrempel, de dagelijkse meldingslimiet en/of ontvangers van de waarschuwing wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="73d83-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Wachtrijwaarschuwingen in het gebied Recente waarschuwingen van het dashboard voor de e-mailstroom in het Security & Compliance Center](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="73d83-114">Wachtrijwaarschuwingen aanpassen</span><span class="sxs-lookup"><span data-stu-id="73d83-114">Customize queue alerts</span></span>

<span data-ttu-id="73d83-115">Inzichten in de mailstroom maken een waarschuwingsbeleid met de naam **Berichten zijn vertraagd** (het selectievakje **E-mailmeldingen verzenden** in het onderstaande voorbeeldschermafbeelding) die is gevonden in **Alerts** \> **waarschuwingsbeleid**.</span><span class="sxs-lookup"><span data-stu-id="73d83-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="73d83-116">U de drempelwaarde wijzigen en ontvangers waarschuwen door op het beleid te klikken.</span><span class="sxs-lookup"><span data-stu-id="73d83-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Navigatie waarschuwingen](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="73d83-118">U ziet een nieuw beleidsinformatieblad, u nu op **Beleid bewerken**klikken.</span><span class="sxs-lookup"><span data-stu-id="73d83-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Beleid bewerken](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="73d83-120">Het informatieblad wordt gewijzigd in het **beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="73d83-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="73d83-121">U nu de ontvangers voor de waarschuwingse-mail, de limiet voor het aantal verzonden meldingen per dag en de minimumdrempel wijzigen om de waarschuwing te activeren (200 of meer).</span><span class="sxs-lookup"><span data-stu-id="73d83-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Beleidsblad bewerken](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="73d83-123">Waarschuwingsgegevens voor wachtrijen</span><span class="sxs-lookup"><span data-stu-id="73d83-123">Queue alert details</span></span>

<span data-ttu-id="73d83-124">Wanneer u op de waarschuwing klikt, worden de waarschuwingsgegevens weergegeven in een flyoutvenster.</span><span class="sxs-lookup"><span data-stu-id="73d83-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Een wachtrijwaarschuwing selecteren in het gebied Recente waarschuwingen van het dashboard voor de e-mailstroom in het Security & Compliance Center](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![De wachtrijwaarschuwing Details flyout in het Security & Compliance Center](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="73d83-127">U in de waarschuwingsdetails op **Wachtrijgegevens weergeven** klikken om de wachtrijdetails, problemen en koppelingen naar de beschikbare oplossingen in een nieuw flyout-deelvenster te bekijken.</span><span class="sxs-lookup"><span data-stu-id="73d83-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![De wachtrijwaarschuwing Details flyout in het Security & Compliance Center](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Wachtrij weergeven in de waarschuwingsdetails](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="73d83-130">Wachtrijen</span><span class="sxs-lookup"><span data-stu-id="73d83-130">Queues</span></span>

<span data-ttu-id="73d83-131">Zelfs als het berichtvolume in de wachtrij de drempelwaarde niet heeft overschreden, u nog steeds het gebied **Wachtrijen** van het dashboard voor e-mailstroom gebruiken om berichten te zien die langer dan een uur in de wachtrij staan.</span><span class="sxs-lookup"><span data-stu-id="73d83-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="73d83-132">U het gebied **Wachtrijen** gebruiken om het aantal berichten in de wachtrij te controleren (de waarde 0 geeft de e-mailstroom aan in ok) en actie ondernemen voordat het aantal berichten in de wachtrij te groot wordt.</span><span class="sxs-lookup"><span data-stu-id="73d83-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Wachtrijen in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="73d83-134">Wanneer u op het aantal berichten in de wachtrij in **wachtrijen**klikt, worden de wachtrijgegevens en richtlijnen voor het oplossen van het probleem weergegeven in een flyout-deelvenster (dezelfde flyout die wordt weergegeven nadat u op **Wachtrij weergeven** in de details van een wachtrijwaarschuwing hebt geklikt).</span><span class="sxs-lookup"><span data-stu-id="73d83-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Wachtrijdetails](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="73d83-136">Zie ook</span><span class="sxs-lookup"><span data-stu-id="73d83-136">See also</span></span>

<span data-ttu-id="73d83-137">Zie Inzichten in de [stroomstromen in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroom-inzichten in het dashboard voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="73d83-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
