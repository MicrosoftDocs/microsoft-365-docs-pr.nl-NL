---
title: Inzicht in wachtrijen in het dashboard voor e-mail stromen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Beheerders kunnen informatie over het gebruik van de widget wachtrijen in het dashboard voor e-mail stroom in het beveiligings & nalevings centrum om de niet-geslaagde e-mail stroom te controleren aan hun on-premises of partnerorganisaties via uitgaande connectoren.
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826903"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="44bb3-103">Inzicht in wachtrijen in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="44bb3-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="44bb3-104">Wanneer berichten niet vanuit uw organisatie kunnen worden verzonden naar uw on-premises e-mailservers en e-mailservers met connectors, worden de berichten in de wachtrij geplaatst in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44bb3-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="44bb3-105">Veelgebruikte voorbeelden die deze voorwaarde veroorzaken:</span><span class="sxs-lookup"><span data-stu-id="44bb3-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="44bb3-106">De verbindingslijn is onjuist geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="44bb3-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="44bb3-107">Uw on-premises omgeving heeft een netwerk-of firewall wijziging.</span><span class="sxs-lookup"><span data-stu-id="44bb3-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="44bb3-108">Microsoft 365 blijft opnieuw proberen na 24 uur.</span><span class="sxs-lookup"><span data-stu-id="44bb3-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="44bb3-109">Na 24 uur verloopt de berichten en gaan ze terug naar de afzenders in rapporten over niet-uitgevoerde bezorging (ook wel Ndr's of stuiterende berichten).</span><span class="sxs-lookup"><span data-stu-id="44bb3-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="44bb3-110">Als het e-mail volume in de wachtrij de vooraf gedefinieerde drempelwaarde overschrijdt (de standaardwaarde is 200-berichten), is de informatie beschikbaar op de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="44bb3-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="44bb3-111">De **wachtrijen** zijn te zien in het [Dashboard voor de e-mail stroom](mail-flow-insights-v2.md) van het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="44bb3-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="44bb3-112">Zie voor meer informatie de [wachtrijen inzichtelijk in de sectie e-mail stroom dashboard](#queues-insight-in-the-mail-flow-dashboard) in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="44bb3-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="44bb3-113">Er wordt een waarschuwing weergegeven bij **recente meldingen** het dashboard waarschuwingen in het [compliance-Beveiligingscentrum van beveiligings &](https://protection.office.com) (**waarschuwingen** \> **Dashboard** of <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="44bb3-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Recente waarschuwingen in het meldingen dashboard in het nalevings centrum voor beveiliging &](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="44bb3-115">Beheerders ontvangen een e-mail melding op basis van de configuratie van het standaard waarschuwings beleid met de naam **berichten zijn vertraagd**.</span><span class="sxs-lookup"><span data-stu-id="44bb3-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="44bb3-116">Zie de volgende sectie voor informatie over het configureren van de instellingen voor meldingen voor deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="44bb3-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="44bb3-117">Zie voor meer informatie over waarschuwings beleidsregels [een waarschuwings beleid in het beveiligings & nalevings centrum](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="44bb3-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="44bb3-118">Wachtrij waarschuwingen aanpassen</span><span class="sxs-lookup"><span data-stu-id="44bb3-118">Customize queue alerts</span></span>

1. <span data-ttu-id="44bb3-119">Ga in het [beveiligings & nalevings centrum](https://protection.office.com)naar **Alerts** \> **waarschuwings beleid** voor meldingen of open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="44bb3-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="44bb3-120">Ga naar de pagina met **waarschuwings beleidsregels** en selecteer het beleid **met de naam vertraagde berichten**.</span><span class="sxs-lookup"><span data-stu-id="44bb3-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="44bb3-121">In het **bericht zijn vertraagde** flyout die wordt geopend, kunt u de melding in-of uitschakelen en de instellingen voor meldingen configureren.</span><span class="sxs-lookup"><span data-stu-id="44bb3-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Berichten hebben een vertragings beleid voor de beveiliging & nalevings centrum](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="44bb3-123">**Status**: u kunt de melding in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="44bb3-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="44bb3-124">Geadresseerden en **meldingen** **per E-mail ontvangen** : Klik op **bewerken** om de volgende instellingen te configureren:</span><span class="sxs-lookup"><span data-stu-id="44bb3-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="44bb3-125">Klik op **bewerken**om de instellingen voor meldingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="44bb3-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="44bb3-126">Configureer de volgende instellingen in de flyout **beleidsregels bewerken** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="44bb3-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="44bb3-127">**E-mail meldingen verzenden**: de standaardwaarde is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="44bb3-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="44bb3-128">**Geadresseerden voor e-mail**: de standaardwaarde is **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="44bb3-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="44bb3-129">**Dagelijkse meldings limiet**: de standaardwaarde is **geen limiet**.</span><span class="sxs-lookup"><span data-stu-id="44bb3-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="44bb3-130">**Drempel**waarde: de standaardwaarde is 200.</span><span class="sxs-lookup"><span data-stu-id="44bb3-130">**Threshold**: The default value is 200.</span></span>

   ![De instellingen voor meldingen in de berichten hebben een vertragings beleid voor de beveiliging & nalevings centrum](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="44bb3-132">Wanneer u klaar bent, klikt u op **Opslaan** en **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="44bb3-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="44bb3-133">Inzicht in wachtrijen in het dashboard voor e-mail stromen</span><span class="sxs-lookup"><span data-stu-id="44bb3-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="44bb3-134">Ook als het volume van de wachtrij niet de drempelwaarde heeft overschreden en een waarschuwing heeft gegenereerd, kunt u nog steeds het inzicht in de **wachtrijen** van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) gebruiken om berichten weer te geven die zijn gefactureerd voor meer dan één uur en om actie te ondernemen voordat het aantal berichten in de wachtrij te groot wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="44bb3-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![De widget wachtrijen in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-queues-widget.png)

<span data-ttu-id="44bb3-136">Als u op het aantal berichten in het object klikt, wordt een flyout met de berichten in de **wachtrij** weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="44bb3-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="44bb3-137">**Aantal berichten in de wachtrij**</span><span class="sxs-lookup"><span data-stu-id="44bb3-137">**Number of queued messages**</span></span>
- <span data-ttu-id="44bb3-138">**Naam connector**: Klik op de naam van de verbindingslijn om de connector te beheren in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="44bb3-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="44bb3-139">**Begintijd wachtrij**</span><span class="sxs-lookup"><span data-stu-id="44bb3-139">**Queue started time**</span></span>
- <span data-ttu-id="44bb3-140">**Oudste berichten verlopen**</span><span class="sxs-lookup"><span data-stu-id="44bb3-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="44bb3-141">**Doelserver**</span><span class="sxs-lookup"><span data-stu-id="44bb3-141">**Destination server**</span></span>
- <span data-ttu-id="44bb3-142">**Laatste IP-adres**</span><span class="sxs-lookup"><span data-stu-id="44bb3-142">**Last IP address**</span></span>
- <span data-ttu-id="44bb3-143">**Laatste fout**</span><span class="sxs-lookup"><span data-stu-id="44bb3-143">**Last error**</span></span>
- <span data-ttu-id="44bb3-144">**Oplossing**: er zijn veelvoorkomende problemen en oplossingen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="44bb3-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="44bb3-145">Als de koppeling **nu repareren** beschikbaar is, klikt u erop om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="44bb3-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="44bb3-146">U kunt ook op een van de beschikbare koppelingen klikken voor meer informatie over de fout en mogelijke oplossingen.</span><span class="sxs-lookup"><span data-stu-id="44bb3-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Meer informatie over het klikken op de wachtrijen in het dashboard voor e-mail stroom](../../media/mfi-queues-details.png)

<span data-ttu-id="44bb3-148">Wanneer u op **wachtrij weergeven** klikt, wordt dezelfde flyout weergegeven wanneer u op wachtrij weergeven klikt voor de details van een **bericht zijn uitgesteld** .</span><span class="sxs-lookup"><span data-stu-id="44bb3-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Berichten hebben een vertragings waarschuwing voor de beveiliging & nalevings centrum](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="44bb3-150">Zie ook</span><span class="sxs-lookup"><span data-stu-id="44bb3-150">See also</span></span>

<span data-ttu-id="44bb3-151">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="44bb3-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
