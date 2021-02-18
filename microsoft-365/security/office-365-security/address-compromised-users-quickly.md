---
title: Adres van gekromde gebruikersaccounts met geautomatiseerd onderzoek en reactie
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection, compromised
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Lees hoe u het proces voor het detecteren en adresseren van gekromde gebruikersaccounts kunt versnellen met behulp van geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 Abonnement 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288739"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="ca0e0-104">Adres van gekromde gebruikersaccounts met geautomatiseerd onderzoek en reactie</span><span class="sxs-lookup"><span data-stu-id="ca0e0-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ca0e0-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ca0e0-105">**Applies to**</span></span>
- [<span data-ttu-id="ca0e0-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ca0e0-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ca0e0-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ca0e0-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ca0e0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca0e0-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="ca0e0-109">[Microsoft Defender voor Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) bevat krachtige mogelijkheden voor geautomatiseerde onderzoeken en antwoorden [(AIR).](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="ca0e0-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="ca0e0-110">Dergelijke mogelijkheden kunnen uw team voor beveiligingsbewerkingen veel tijd en moeite besparen bij het omgaan met bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="ca0e0-111">Microsoft blijft de beveiligingsmogelijkheden verbeteren.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="ca0e0-112">Onlangs zijn de AIR-mogelijkheden uitgebreid met een gekromde playbook voor gebruikersbeveiliging (momenteel in preview).</span><span class="sxs-lookup"><span data-stu-id="ca0e0-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="ca0e0-113">Lees dit artikel voor meer informatie over de gekromde playbook voor gebruikersbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="ca0e0-114">En zie het blogbericht Sneller tijd om gebruikerscompromitteerd gedrag te detecteren en te beperken met Microsoft Defender voor [Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Geautomatiseerd onderzoek voor een gecompromitteerd gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="ca0e0-116">Met de gekromde playbook voor gebruikersbeveiliging kan het beveiligingsteam van uw organisatie het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="ca0e0-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="ca0e0-117">Snelle detectie van gekromde gebruikersaccounts;</span><span class="sxs-lookup"><span data-stu-id="ca0e0-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="ca0e0-118">Beperk het bereik van een inbreuk wanneer een account wordt gehackt; en</span><span class="sxs-lookup"><span data-stu-id="ca0e0-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="ca0e0-119">Reageer effectiever en efficiënter op gecompromitteerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="ca0e0-120">Meldingen over gekromde gebruikers</span><span class="sxs-lookup"><span data-stu-id="ca0e0-120">Compromised user alerts</span></span>

<span data-ttu-id="ca0e0-121">Wanneer een gebruikersaccount is gehackt, treedt er atypisch of anomiaal gedrag op.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="ca0e0-122">Phishing- en spamberichten kunnen bijvoorbeeld intern worden verzonden vanuit een vertrouwd gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="ca0e0-123">Defender voor Office 365 kan dergelijke problemen herkennen in e-mailpatronen en samenwerkingsactiviteit in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="ca0e0-124">Wanneer dit gebeurt, worden waarschuwingen geactiveerd en wordt de risicobeperking gestart.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="ca0e0-125">Hier ziet u een waarschuwing die is geactiveerd vanwege verdachte e-mails die worden verzonden:</span><span class="sxs-lookup"><span data-stu-id="ca0e0-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Waarschuwing geactiveerd vanwege verdachte verzending van e-mailberichten](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="ca0e0-127">Hier is een voorbeeld van een waarschuwing die werd geactiveerd toen een limiet voor verzenden voor een gebruiker werd bereikt:</span><span class="sxs-lookup"><span data-stu-id="ca0e0-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Waarschuwing geactiveerd door verzenden limiet bereikt](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="ca0e0-129">Een gekromde gebruiker onderzoeken en beantwoorden</span><span class="sxs-lookup"><span data-stu-id="ca0e0-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="ca0e0-130">Wanneer een gebruikersaccount niet meer werkt, worden waarschuwingen geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="ca0e0-131">En in sommige gevallen is dat gebruikersaccount geblokkeerd en kunnen er geen e-mailberichten meer worden verzonden totdat het probleem is opgelost door het beveiligingsteam van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="ca0e0-132">In andere gevallen wordt een geautomatiseerd onderzoek gestart dat kan leiden tot aanbevolen acties die uw beveiligingsteam moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="ca0e0-133">Beperkte gebruikers weergeven en onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ca0e0-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="ca0e0-134">Details over geautomatiseerde onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="ca0e0-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="ca0e0-135">U moet de juiste machtigingen hebben om de volgende taken te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="ca0e0-136">Zie [Vereiste machtigingen voor het gebruik van AIR-mogelijkheden.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="ca0e0-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="ca0e0-137">Beperkte gebruikers weergeven en onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ca0e0-137">View and investigate restricted users</span></span>

<span data-ttu-id="ca0e0-138">U hebt een aantal opties voor het navigeren naar een lijst met beperkte gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="ca0e0-139">U kunt bijvoorbeeld in het & Compliancecentrum voor  risicobeheer \> **beperkte** \> **gebruikers gaan.**</span><span class="sxs-lookup"><span data-stu-id="ca0e0-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="ca0e0-140">In de volgende procedure wordt de navigatie beschreven met behulp van het **dashboard** Waarschuwingen, wat een goede manier is om verschillende soorten waarschuwingen te zien die mogelijk zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="ca0e0-141">Ga naar <https://protection.office.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="ca0e0-142">Kies Waarschuwingendashboard in **het navigatiedeelvenster.** \> </span><span class="sxs-lookup"><span data-stu-id="ca0e0-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="ca0e0-143">Kies Beperkte **gebruikers in** de widget Overige **waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="ca0e0-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Andere waarschuwingswidget](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="ca0e0-145">Hiermee wordt de lijst met gebruikers met beperkingen geopend.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-145">This opens the list of restricted users.</span></span>

   ![Gebruikers met beperkingen in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="ca0e0-147">Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals het [vrijgeven van de beperkte gebruiker.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="ca0e0-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="ca0e0-148">Details over geautomatiseerde onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="ca0e0-148">View details about automated investigations</span></span>

<span data-ttu-id="ca0e0-149">Wanneer een geautomatiseerd onderzoek is gestart, kunt u de details en resultaten bekijken in het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="ca0e0-150">Ga naar **Onderzoeken van** \> **bedreigingsbeheer** en selecteer vervolgens een onderzoek om de details ervan weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="ca0e0-151">Zie Details van een onderzoek weergeven voor [meer informatie.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="ca0e0-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="ca0e0-152">Houd rekening met de volgende punten</span><span class="sxs-lookup"><span data-stu-id="ca0e0-152">Keep the following points in mind</span></span>

- <span data-ttu-id="ca0e0-153">**Blijf op de hoogte van uw waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="ca0e0-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="ca0e0-154">Zoals u weet, hoe langer een compromis wordt gedetecteerd, hoe groter de kans op enorme impact en kosten voor uw organisatie, klanten en partners.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="ca0e0-155">Vroegtijdige detectie en tijdige reactie zijn essentieel om bedreigingen te beperken, vooral wanneer het account van een gebruiker wordt gehackt.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="ca0e0-156">Automatisering helpt uw team voor beveiligingsbewerkingen om uw **beveiligingsbewerkingen te helpen, maar niet te vervangen.**</span><span class="sxs-lookup"><span data-stu-id="ca0e0-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="ca0e0-157">Met geautomatiseerde onderzoeks- en antwoordmogelijkheden kan een gecompromitteerde gebruiker vroeg worden gedetecteerd, maar uw team voor beveiligingsbewerkingen moet waarschijnlijk een onderzoek uitvoeren en herstel uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="ca0e0-158">Hebt u hier hulp bij nodig?</span><span class="sxs-lookup"><span data-stu-id="ca0e0-158">Need some help with this?</span></span> <span data-ttu-id="ca0e0-159">Zie [Acties beoordelen en goedkeuren.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="ca0e0-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="ca0e0-160">**Vertrouw niet op een verdachte aanmeldingsmelding als enige indicator.**</span><span class="sxs-lookup"><span data-stu-id="ca0e0-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="ca0e0-161">Als een gebruikersaccount is gehackt, kan er al dan niet een verdachte aanmeldingsmelding worden verstuurd.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="ca0e0-162">Soms is het de reeks activiteiten die plaatsvinden nadat een account is gekromd en dat een waarschuwing activeert.</span><span class="sxs-lookup"><span data-stu-id="ca0e0-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="ca0e0-163">Wilt u meer weten over waarschuwingen?</span><span class="sxs-lookup"><span data-stu-id="ca0e0-163">Want to know more about alerts?</span></span> <span data-ttu-id="ca0e0-164">Zie [Beleidsregels voor waarschuwingen.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ca0e0-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca0e0-165">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="ca0e0-165">Next steps</span></span>

- [<span data-ttu-id="ca0e0-166">Bekijk de vereiste machtigingen voor het gebruik van AIR-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="ca0e0-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="ca0e0-167">Schadelijke e-mail zoeken en onderzoeken in Office 365</span><span class="sxs-lookup"><span data-stu-id="ca0e0-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="ca0e0-168">Meer informatie over AIR in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ca0e0-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="ca0e0-169">Ga naar de routekaart voor Microsoft 365 om te zien wat er binnenkort beschikbaar komt en uit te rollen</span><span class="sxs-lookup"><span data-stu-id="ca0e0-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
