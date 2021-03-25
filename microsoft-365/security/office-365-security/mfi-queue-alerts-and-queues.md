---
title: Inzicht in wachtrijen in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Beheerders kunnen leren hoe ze de widget Wachtrijen gebruiken in het e-mailstroomdashboard in het beveiligings- & compliancecentrum om mislukte e-mailstroom naar hun on-premises of partnerorganisaties te controleren via uitgaande verbindingslijnen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204919"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="ae5b5-103">Inzicht in wachtrijen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="ae5b5-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ae5b5-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-104">**Applies to**</span></span>
- [<span data-ttu-id="ae5b5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ae5b5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ae5b5-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ae5b5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ae5b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae5b5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ae5b5-108">Wanneer berichten niet kunnen worden verzonden vanuit uw organisatie naar uw on-premises e-mailservers of partner-e-mailservers met connectors, worden de berichten in de wachtrij geplaatst in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="ae5b5-109">Veelvoorkomende voorbeelden die deze voorwaarde veroorzaken zijn:</span><span class="sxs-lookup"><span data-stu-id="ae5b5-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="ae5b5-110">De verbindingslijn is onjuist geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="ae5b5-111">Er zijn netwerk- of firewallwijzigingen aangebracht in uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="ae5b5-112">Microsoft 365 blijft 24 uur lang proberen om te leveren.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="ae5b5-113">Na 24 uur verlopen de berichten en worden ze geretourneerd aan de afzenders in niet-bezorgingsrapporten (ook wel bekend als een NDR of bounce-berichten).</span><span class="sxs-lookup"><span data-stu-id="ae5b5-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="ae5b5-114">Als het e-mailvolume in de wachtrij de vooraf gedefinieerde drempel overschrijdt (de standaardwaarde is 200 berichten), is de informatie beschikbaar op de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="ae5b5-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="ae5b5-115">Het **inzicht in wachtrijen** in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in [& Beveiligingscentrum.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="ae5b5-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ae5b5-116">Zie het inzicht wachtrijen in de sectie [E-mailstroomdashboard](#queues-insight-in-the-mail-flow-dashboard) in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="ae5b5-117">Er wordt een waarschuwing weergegeven in **Recente waarschuwingen op** het dashboard Waarschuwingen in & [Beveiligingscentrum](https://protection.office.com) ( \> **Waarschuwingendashboard** of <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="ae5b5-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Recente waarschuwingen in het dashboard Waarschuwingen in het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="ae5b5-119">Beheerders ontvangen een e-mailmelding op basis van de configuratie van het standaardwaarschuwingsbeleid met de naam **Berichten zijn vertraagd.**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="ae5b5-120">Zie de volgende sectie als u de instellingen voor meldingen voor deze waarschuwing wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="ae5b5-121">Zie Waarschuwingsbeleid in het Beveiligings- & compliancecentrum voor meer [informatie over waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ae5b5-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="ae5b5-122">Wachtrijwaarschuwingen aanpassen</span><span class="sxs-lookup"><span data-stu-id="ae5b5-122">Customize queue alerts</span></span>

1. <span data-ttu-id="ae5b5-123">Ga in [het & Compliancecentrum](https://protection.office.com)naar  \> **Waarschuwingenwaarschuwingsbeleid** of open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="ae5b5-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="ae5b5-124">Zoek en selecteer **op de** pagina Waarschuwingsbeleid het beleid met de naam Berichten **zijn vertraagd.**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="ae5b5-125">In de **fly-out Bericht is vertraagd** die wordt geopend, kunt u de waarschuwing in- of uitschakelen en de instellingen voor meldingen configureren.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Berichten zijn vertraagde waarschuwingsbeleidsdetails van het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="ae5b5-127">**Status:** U kunt de waarschuwing in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="ae5b5-128">**E-mailontvangers** **en limiet voor dagelijkse meldingen:** Klik op Bewerken **om** de volgende instellingen te configureren:</span><span class="sxs-lookup"><span data-stu-id="ae5b5-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="ae5b5-129">Als u de instellingen voor meldingen wilt configureren, klikt u op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="ae5b5-130">Configureer **de volgende instellingen** in het flyout Beleid bewerken dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ae5b5-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ae5b5-131">**E-mailmeldingen verzenden:** de standaardwaarde is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="ae5b5-132">**E-mailontvangers:** De standaardwaarde is **TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="ae5b5-133">**Dagelijkse meldingslimiet:** De standaardwaarde is **Geen limiet.**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="ae5b5-134">**Drempelwaarde:** de standaardwaarde is 200.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-134">**Threshold**: The default value is 200.</span></span>

   ![Meldingsinstellingen in de Berichten zijn vertraagde waarschuwingsbeleidsdetails van het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="ae5b5-136">Wanneer u klaar bent, klikt u op **Opslaan** en **sluiten.**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="ae5b5-137">Inzicht in wachtrijen in het e-mailstroomdashboard</span><span class="sxs-lookup"><span data-stu-id="ae5b5-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="ae5b5-138">Zelfs als het berichtvolume in de wachtrij de drempelwaarde niet heeft  overschreden en een waarschuwing heeft gegenereerd, kunt u nog steeds het inzicht Wachtrijen in het e-mailstroomdashboard gebruiken om berichten te zien die langer dan een uur in de wachtrij staan en actie ondernemen voordat het aantal in de wachtrij geplaatste berichten te groot wordt. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ae5b5-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![De widget Wachtrijen in het e-mailstroomdashboard in & Beveiligingscentrum](../../media/mfi-queues-widget.png)

<span data-ttu-id="ae5b5-140">Als u op het aantal berichten in de widget klikt, wordt er een fly-out met berichten **in** de wachtrij weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="ae5b5-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="ae5b5-141">**Aantal in de wachtrij geplaatste berichten**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-141">**Number of queued messages**</span></span>
- <span data-ttu-id="ae5b5-142">**Naam van** verbindingslijn: Klik op de naam van de verbindingslijn om de verbindingslijn te beheren in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="ae5b5-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="ae5b5-143">**De begintijd van de wachtrij**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-143">**Queue started time**</span></span>
- <span data-ttu-id="ae5b5-144">**Oudste berichten verlopen**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="ae5b5-145">**Doelserver**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-145">**Destination server**</span></span>
- <span data-ttu-id="ae5b5-146">**Laatste IP-adres**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-146">**Last IP address**</span></span>
- <span data-ttu-id="ae5b5-147">**Laatste fout**</span><span class="sxs-lookup"><span data-stu-id="ae5b5-147">**Last error**</span></span>
- <span data-ttu-id="ae5b5-148">**Oplossen: er** zijn veelvoorkomende problemen en oplossingen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="ae5b5-149">Als de koppeling **Nu oplossen** beschikbaar is, klikt u erop om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="ae5b5-150">Klik anders op beschikbare koppelingen voor meer informatie over de fout en mogelijke oplossingen.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Details nadat u op het inzicht Wachtrijen in het e-mailstroomdashboard hebt geklikt](../../media/mfi-queues-details.png)

<span data-ttu-id="ae5b5-152">Hetzelfde flyout wordt weergegeven nadat  u in de details van een waarschuwing op Wachtrij weergeven **hebt** geklikt.</span><span class="sxs-lookup"><span data-stu-id="ae5b5-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Berichten zijn vertraagde waarschuwingsdetails in het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="ae5b5-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ae5b5-154">See also</span></span>

<span data-ttu-id="ae5b5-155">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ae5b5-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
