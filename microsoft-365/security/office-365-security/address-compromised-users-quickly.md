---
title: Gecompromitteerde gebruikersaccounts adresseerde met geautomatiseerde onderzoeken en antwoorden
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection, compromised
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
description: Lees hoe u het proces voor het opsporen en aanpakken van gecompromitteerde gebruikersaccounts kunt versnellen met geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c500221a10c00cc3b8d9d99c102ce8ec54fa2a48
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934691"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="64b04-104">Gecompromitteerde gebruikersaccounts adresseerde met geautomatiseerde onderzoeken en antwoorden</span><span class="sxs-lookup"><span data-stu-id="64b04-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="64b04-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="64b04-105">**Applies to**</span></span>
- [<span data-ttu-id="64b04-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="64b04-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="64b04-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="64b04-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="64b04-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64b04-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="64b04-109">[Microsoft Defender voor Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) bevat krachtige air-mogelijkheden (Automated [Investigation and Response).](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="64b04-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="64b04-110">Dergelijke mogelijkheden kunnen uw beveiligingsbewerkingsteam veel tijd en moeite besparen bij het omgaan met bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="64b04-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="64b04-111">Microsoft blijft de beveiligingsmogelijkheden verbeteren.</span><span class="sxs-lookup"><span data-stu-id="64b04-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="64b04-112">Onlangs zijn de AIR-mogelijkheden uitgebreid met een gecompromitteerde playbook voor gebruikersbeveiliging (momenteel in preview).</span><span class="sxs-lookup"><span data-stu-id="64b04-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="64b04-113">Lees dit artikel voor meer informatie over de gecompromitteerde playbook voor gebruikersbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="64b04-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="64b04-114">En zie het blogbericht [Beperk](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) de tijd om gebruikerscompromitteerd gedrag op te sporen en te beantwoorden en het bereik van inbreuken met Microsoft Defender te beperken Office 365 voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="64b04-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Geautomatiseerd onderzoek voor een gecompromitteerde gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="64b04-116">Met de gecompromitteerde playbook voor gebruikersbeveiliging kan het beveiligingsteam van uw organisatie het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="64b04-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="64b04-117">De detectie van gecompromitteerde gebruikersaccounts versnellen;</span><span class="sxs-lookup"><span data-stu-id="64b04-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="64b04-118">Beperk het bereik van een inbreuk wanneer een account wordt gecompromitteerd; en</span><span class="sxs-lookup"><span data-stu-id="64b04-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="64b04-119">Reageer effectiever en efficiënter op gecompromitteerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="64b04-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="64b04-120">Meldingen van gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="64b04-120">Compromised user alerts</span></span>

<span data-ttu-id="64b04-121">Wanneer een gebruikersaccount wordt gecompromitteerd, treden atypische of afwijkende gedragingen op.</span><span class="sxs-lookup"><span data-stu-id="64b04-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="64b04-122">Phishing- en spamberichten kunnen bijvoorbeeld intern worden verzonden vanuit een vertrouwd gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="64b04-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="64b04-123">Defender voor Office 365 dergelijke afwijkingen in e-mailpatronen en samenwerkingsactiviteit binnen de Office 365.</span><span class="sxs-lookup"><span data-stu-id="64b04-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="64b04-124">Wanneer dit gebeurt, worden waarschuwingen geactiveerd en wordt het risicobeperkingsproces gestart.</span><span class="sxs-lookup"><span data-stu-id="64b04-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="64b04-125">Hier ziet u bijvoorbeeld een waarschuwing die is geactiveerd vanwege verdachte e-mail verzenden:</span><span class="sxs-lookup"><span data-stu-id="64b04-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Waarschuwing geactiveerd vanwege verdachte e-mail verzenden](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="64b04-127">En hier is een voorbeeld van een waarschuwing die is geactiveerd wanneer een verzendende limiet voor een gebruiker is bereikt:</span><span class="sxs-lookup"><span data-stu-id="64b04-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Waarschuwing geactiveerd door verzenden limiet bereikt](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="64b04-129">Een gecompromitteerde gebruiker onderzoeken en hierop reageren</span><span class="sxs-lookup"><span data-stu-id="64b04-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="64b04-130">Wanneer een gebruikersaccount wordt gecompromitteerd, worden waarschuwingen geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="64b04-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="64b04-131">En in sommige gevallen wordt dat gebruikersaccount geblokkeerd en kunnen er geen verdere e-mailberichten worden verzonden totdat het probleem is opgelost door het beveiligingsteam van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="64b04-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="64b04-132">In andere gevallen wordt een geautomatiseerd onderzoek gestart dat kan leiden tot aanbevolen acties die uw beveiligingsteam moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="64b04-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="64b04-133">Beperkte gebruikers weergeven en onderzoeken</span><span class="sxs-lookup"><span data-stu-id="64b04-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="64b04-134">Details over geautomatiseerde onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="64b04-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="64b04-135">U moet de juiste machtigingen hebben om de volgende taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="64b04-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="64b04-136">Zie [Vereiste machtigingen voor het gebruik van AIR-mogelijkheden.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="64b04-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="64b04-137">Beperkte gebruikers weergeven en onderzoeken</span><span class="sxs-lookup"><span data-stu-id="64b04-137">View and investigate restricted users</span></span>

<span data-ttu-id="64b04-138">U hebt een paar opties voor het navigeren naar een lijst met beperkte gebruikers.</span><span class="sxs-lookup"><span data-stu-id="64b04-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="64b04-139">In het Beveiligings- & compliancecentrum kunt u bijvoorbeeld naar **Gebruikers** met beperkingen voor bedreigingsbeheer \>  \> **controleren.**</span><span class="sxs-lookup"><span data-stu-id="64b04-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="64b04-140">In de volgende procedure wordt navigatie beschreven **met** behulp van het dashboard Waarschuwingen. Dit is een goede manier om verschillende soorten waarschuwingen te zien die mogelijk zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="64b04-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="64b04-141">Ga naar <https://protection.office.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="64b04-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="64b04-142">Kies in het  navigatiedeelvenster \> **Waarschuwingendashboard.**</span><span class="sxs-lookup"><span data-stu-id="64b04-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="64b04-143">Kies in **de widget Overige waarschuwingen** de optie Beperkte **gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="64b04-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget Andere waarschuwingen](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="64b04-145">Hiermee wordt de lijst met beperkte gebruikers geopend.</span><span class="sxs-lookup"><span data-stu-id="64b04-145">This opens the list of restricted users.</span></span>

   ![Beperkte gebruikers in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="64b04-147">Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals het [vrijgeven van de beperkte gebruiker.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="64b04-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="64b04-148">Details over geautomatiseerde onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="64b04-148">View details about automated investigations</span></span>

<span data-ttu-id="64b04-149">Wanneer een geautomatiseerd onderzoek is gestart, kunt u de details en resultaten ervan zien in het & Compliance center.</span><span class="sxs-lookup"><span data-stu-id="64b04-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="64b04-150">Ga naar **Threat Management** \> **Investigations** en selecteer vervolgens een onderzoek om de details ervan weer te geven.</span><span class="sxs-lookup"><span data-stu-id="64b04-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="64b04-151">Zie Details van een onderzoek weergeven voor [meer informatie.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="64b04-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="64b04-152">Houd rekening met de volgende punten</span><span class="sxs-lookup"><span data-stu-id="64b04-152">Keep the following points in mind</span></span>

- <span data-ttu-id="64b04-153">**Blijf op de hoogte van uw waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="64b04-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="64b04-154">Zoals u weet, hoe langer een compromis niet wordt gedetecteerd, hoe groter de kans op grootschalige gevolgen en kosten voor uw organisatie, klanten en partners.</span><span class="sxs-lookup"><span data-stu-id="64b04-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="64b04-155">Vroegtijdige detectie en tijdige reactie zijn essentieel om bedreigingen te beperken, vooral wanneer het account van een gebruiker wordt gehackt.</span><span class="sxs-lookup"><span data-stu-id="64b04-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="64b04-156">Automatisering helpt uw team voor beveiligingsbewerkingen, maar **vervangt deze niet.**</span><span class="sxs-lookup"><span data-stu-id="64b04-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="64b04-157">Met geautomatiseerde onderzoeks- en antwoordmogelijkheden kan een gecompromitteerde gebruiker al vroeg worden gedetecteerd, maar uw team voor beveiligingsbewerkingen moet waarschijnlijk onderzoek doen en herstellen.</span><span class="sxs-lookup"><span data-stu-id="64b04-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="64b04-158">Hebt u hier hulp bij nodig?</span><span class="sxs-lookup"><span data-stu-id="64b04-158">Need some help with this?</span></span> <span data-ttu-id="64b04-159">Zie [Acties controleren en goedkeuren.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="64b04-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="64b04-160">**Vertrouw niet op een verdachte aanmeldingsmelding als enige indicator.**</span><span class="sxs-lookup"><span data-stu-id="64b04-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="64b04-161">Wanneer een gebruikersaccount is gehackt, kan dit een verdachte aanmeldingsmelding al dan niet activeren.</span><span class="sxs-lookup"><span data-stu-id="64b04-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="64b04-162">Soms is het de reeks activiteiten die plaatsvinden nadat een account is gecompromitteerd, die een waarschuwing activeert.</span><span class="sxs-lookup"><span data-stu-id="64b04-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="64b04-163">Wilt u meer weten over waarschuwingen?</span><span class="sxs-lookup"><span data-stu-id="64b04-163">Want to know more about alerts?</span></span> <span data-ttu-id="64b04-164">Zie [Waarschuwingsbeleid](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64b04-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="64b04-165">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="64b04-165">Next steps</span></span>

- [<span data-ttu-id="64b04-166">De vereiste machtigingen controleren voor het gebruik van AIR-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="64b04-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="64b04-167">Schadelijke e-mail zoeken en onderzoeken in Office 365</span><span class="sxs-lookup"><span data-stu-id="64b04-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="64b04-168">Meer informatie over AIR in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="64b04-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="64b04-169">Ga naar Microsoft 365 routekaart om te zien wat er binnenkort komt en uit te rollen</span><span class="sxs-lookup"><span data-stu-id="64b04-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)