---
title: Inzichten in wachtrijen in het dashboard E-mailstroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Beheerders kunnen informatie vinden over het gebruik van de widget Wachtrijen in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum om de niet-geslaagde e-mailstroom naar hun on-premises of partnerorganisaties te controleren via uitgaande connectors.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8ee5ea37fa5a63b8035572059e419c400d66f3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289435"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="dd3b2-103">Inzichten in wachtrijen in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="dd3b2-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dd3b2-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-104">**Applies to**</span></span>
- [<span data-ttu-id="dd3b2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dd3b2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dd3b2-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="dd3b2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="dd3b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd3b2-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="dd3b2-108">Wanneer berichten niet vanuit uw organisatie via connectors naar uw on-premises e-mailservers of partnerservers kunnen worden verzonden, worden de berichten in de wachtrij geplaatst in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="dd3b2-109">Veelvoorkomende voorbeelden die deze voorwaarde veroorzaken zijn:</span><span class="sxs-lookup"><span data-stu-id="dd3b2-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="dd3b2-110">De verbindingslijn is onjuist geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="dd3b2-111">Er zijn netwerk- of firewallwijzigingen geweest in uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="dd3b2-112">Microsoft 365 blijft 24 uur lang proberen de bestelling af te leveren.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="dd3b2-113">Na 24 uur verlopen de berichten en worden ze geretourneerd aan de afzenders in niet-bezorgingsrapporten (ook wel NDR's of niet-bezorgdberichten genoemd).</span><span class="sxs-lookup"><span data-stu-id="dd3b2-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="dd3b2-114">Als het e-mailvolume in de wachtrij de vooraf gedefinieerde drempel overschrijdt (de standaardwaarde is 200 berichten), is de informatie beschikbaar op de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="dd3b2-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="dd3b2-115">Het **inzicht in wachtrijen** in [het dashboard E-mailstroom](mail-flow-insights-v2.md) in het [& Compliancecentrum.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="dd3b2-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="dd3b2-116">Zie de sectie [Queues insight in the Mail flow dashboard in](#queues-insight-in-the-mail-flow-dashboard) this article (Inzichten in wachtrijen in het dashboard van de e-mailstroom in dit artikel) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="dd3b2-117">Er wordt een waarschuwing weergegeven in **recente waarschuwingen** op het dashboard Waarschuwingen in het [& Compliancecentrum](https://protection.office.com)  \> **(dashboard Waarschuwingen** of <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="dd3b2-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Recente waarschuwingen in het dashboard Waarschuwingen in het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="dd3b2-119">Beheerders ontvangen een e-mailmelding op basis van de configuratie van het standaardwaarschuwingsbeleid met de naam Berichten **is vertraagd.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="dd3b2-120">Zie de volgende sectie als u de instellingen voor meldingen voor deze waarschuwing wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="dd3b2-121">Zie Waarschuwingsbeleid in het beveiligings- en compliancecentrum & voor meer [informatie over waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dd3b2-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="dd3b2-122">Wachtrijwaarschuwingen aanpassen</span><span class="sxs-lookup"><span data-stu-id="dd3b2-122">Customize queue alerts</span></span>

1. <span data-ttu-id="dd3b2-123">Ga in [het & Compliancecentrum](https://protection.office.com)naar **Waarschuwingsbeleid** \> **voor** waarschuwingen of <https://protection.office.com/alertpolicies> open.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="dd3b2-124">Zoek en **selecteer op de** pagina Waarschuwingsbeleid het beleid met de naam Berichten is **vertraagd.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="dd3b2-125">In de **flyout Bericht is vertraagd** die wordt geopend, kunt u de waarschuwing in- of uitschakelen en de instellingen voor meldingen configureren.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Berichten zijn vertraagd waarschuwingsbeleid details van het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="dd3b2-127">**Status:** u kunt de waarschuwing in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="dd3b2-128">**E-mailontvangers** en **de limiet voor dagelijkse meldingen:** klik op Bewerken **om** de volgende instellingen te configureren:</span><span class="sxs-lookup"><span data-stu-id="dd3b2-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="dd3b2-129">Als u de instellingen voor meldingen wilt configureren, klikt u op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="dd3b2-130">Configureer **de volgende instellingen** in de flyout Beleid bewerken die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="dd3b2-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="dd3b2-131">**E-mailmeldingen verzenden:** de standaardwaarde is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="dd3b2-132">**E-mailontvangers:** De standaardwaarde is **TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="dd3b2-133">**Dagelijkse meldingslimiet:** de standaardwaarde is **Geen limiet.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="dd3b2-134">**Drempelwaarde:** de standaardwaarde is 200.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-134">**Threshold**: The default value is 200.</span></span>

   ![Meldingsinstellingen in het beleid voor meldingen zijn vertraagd met details van het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="dd3b2-136">Klik op Opslaan en sluiten wanneer u **klaar** **bent.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="dd3b2-137">Inzichten in wachtrijen in het dashboard E-mailstroom</span><span class="sxs-lookup"><span data-stu-id="dd3b2-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="dd3b2-138">Zelfs als het bericht in de wachtrij de drempelwaarde niet heeft overschreden  en een waarschuwing heeft gegenereerd, kunt u het inzichten in Wachtrijen in het [dashboard](mail-flow-insights-v2.md) E-mailstroom nog steeds gebruiken om berichten te zien die langer dan een uur in de wachtrij staan en actie te ondernemen voordat het aantal in de wachtrij geplaatste berichten te groot wordt.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget Wachtrijen in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-queues-widget.png)

<span data-ttu-id="dd3b2-140">Als u op het aantal berichten in de widget klikt, wordt een **flyout** Berichten in de wachtrij met de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="dd3b2-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="dd3b2-141">**Aantal berichten in wachtrij**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-141">**Number of queued messages**</span></span>
- <span data-ttu-id="dd3b2-142">**Connectornaam:** klik op de naam van de connector om de connector te beheren in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="dd3b2-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="dd3b2-143">**Wachttijd**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-143">**Queue started time**</span></span>
- <span data-ttu-id="dd3b2-144">**Oudste berichten verlopen**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="dd3b2-145">**Doelserver**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-145">**Destination server**</span></span>
- <span data-ttu-id="dd3b2-146">**Laatste IP-adres**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-146">**Last IP address**</span></span>
- <span data-ttu-id="dd3b2-147">**Laatste fout**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-147">**Last error**</span></span>
- <span data-ttu-id="dd3b2-148">**Oplossing: er** zijn veelvoorkomende problemen en oplossingen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="dd3b2-149">Als de koppeling **Nu oplossen beschikbaar** is, klikt u erop om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="dd3b2-150">Klik anders op beschikbare koppelingen voor meer informatie over de fout en mogelijke oplossingen.</span><span class="sxs-lookup"><span data-stu-id="dd3b2-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Details na klikken op Het inzichten in wachtrijen in het dashboard E-mailstroom](../../media/mfi-queues-details.png)

<span data-ttu-id="dd3b2-152">Dezelfde flyout wordt weergegeven nadat u op Wachtrij weergeven **hebt** geklikt in de details van een waarschuwing die **is vertraagd.**</span><span class="sxs-lookup"><span data-stu-id="dd3b2-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Details van vertraagde meldingen zijn vertraagd in het beveiligings- & compliancecentrum](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="dd3b2-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dd3b2-154">See also</span></span>

<span data-ttu-id="dd3b2-155">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dd3b2-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
