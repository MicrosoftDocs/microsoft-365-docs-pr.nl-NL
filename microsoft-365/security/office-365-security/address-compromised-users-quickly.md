---
title: Opgetaste gebruikersaccounts met een automatisch onderzoek en antwoord
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herbemiddeling, bedreiging, Geavanceerd, bedreiging, beveiliging, compromissen
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Meer informatie over het versnellen van het proces voor het opsporen en adresseren van gebruikersaccounts met automatisch onderzoek en antwoord mogelijkheden in Microsoft Defender voor Office 365, abonnement 2.
ms.openlocfilehash: 19c9bad33263178f92c6fe523b44497cf38ebd53
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616735"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="b0662-104">Opgetaste gebruikersaccounts met een automatisch onderzoek en antwoord</span><span class="sxs-lookup"><span data-stu-id="b0662-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b0662-105">[Microsoft Defender voor Office 365 abonnement 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) bevat krachtige mogelijkheden voor [automatisch onderzoek en reacties](office-365-air.md) (lucht).</span><span class="sxs-lookup"><span data-stu-id="b0662-105">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="b0662-106">Een dergelijk vermogen kan uw bedrijfsactiviteiten team een veel tijd en een inspanning van bedreigingen bieden.</span><span class="sxs-lookup"><span data-stu-id="b0662-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="b0662-107">Microsoft blijft de functionaliteit van beveiligingsfuncties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="b0662-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="b0662-108">Onlangs werden lucht mogelijkheden uitgebreid met een in de preview-versie Playbook (momenteel in preview-versie).</span><span class="sxs-lookup"><span data-stu-id="b0662-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="b0662-109">Lees dit artikel voor meer informatie over de beveiligings Playbook van de aanvaller.</span><span class="sxs-lookup"><span data-stu-id="b0662-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="b0662-110">En de beschikbare tijd voor een blogbericht [detecteren en beantwoorden met Microsoft Defender voor Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b0662-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Automatisch onderzoek voor een gemanipuleerde gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="b0662-112">Met de gemanipuleerde Playbook voor gebruikersbeveiliging kan het beveiligingsteam van uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="b0662-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="b0662-113">Het detecteren van gebruikersaccounts versnellen.</span><span class="sxs-lookup"><span data-stu-id="b0662-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="b0662-114">U beperkt het reikwijdte van een schending wanneer een account wordt aangetast. en</span><span class="sxs-lookup"><span data-stu-id="b0662-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="b0662-115">U kunt gebruikers effectiever en efficiënter beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="b0662-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="b0662-116">Gebruikers waarschuwingen met compromissen</span><span class="sxs-lookup"><span data-stu-id="b0662-116">Compromised user alerts</span></span>

<span data-ttu-id="b0662-117">Wanneer er sprake is van een onveilig gedrag van een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="b0662-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="b0662-118">Malafide en spamberichten kunnen bijvoorbeeld intern worden verzonden via een vertrouwd gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="b0662-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="b0662-119">Met Defender voor Office 365 kunt u afwijkingen detecteren in e-mail patronen en samenwerkingsactiviteiten in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0662-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="b0662-120">Wanneer dit gebeurt, worden waarschuwingen geactiveerd en wordt het probleem met risicobeperking gestart.</span><span class="sxs-lookup"><span data-stu-id="b0662-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="b0662-121">Hier ziet u bijvoorbeeld een waarschuwing die werd geactiveerd vanwege verdachte e-mail die wordt verzonden:</span><span class="sxs-lookup"><span data-stu-id="b0662-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Waarschuwing veroorzaakt vanwege verdachte e-mail verzonden](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="b0662-123">En hier volgt een voorbeeld van een waarschuwing die werd geactiveerd wanneer een verzendings limiet voor een gebruiker is bereikt:</span><span class="sxs-lookup"><span data-stu-id="b0662-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Waarschuwing geactiveerd door limiet is bereikt](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="b0662-125">Een door een gebruiker gemanipuleerd onderzoek beantwoorden en beantwoorden</span><span class="sxs-lookup"><span data-stu-id="b0662-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="b0662-126">Wanneer een gebruikersaccount wordt gekraakt, worden waarschuwingen geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="b0662-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="b0662-127">In sommige gevallen is het niet mogelijk om verdere e-mailberichten te verzenden, zodat u geen e-mailberichten kunt verzenden totdat het probleem is verholpen door het team van het beveiligingsactiviteiten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b0662-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="b0662-128">In andere gevallen begint een geautomatiseerd onderzoek waarmee de aanbevolen acties kunnen worden uitgevoerd die uw beveiligingsteam moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b0662-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="b0662-129">Gebruikers met beperkte toegang weergeven en onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b0662-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="b0662-130">Details van geautomatiseerde onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="b0662-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="b0662-131">U moet de juiste machtigingen hebben om de volgende taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b0662-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="b0662-132">Zie de [vereiste machtigingen voor het gebruik van lucht mogelijkheden](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="b0662-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="b0662-133">Gebruikers met beperkte toegang weergeven en onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b0662-133">View and investigate restricted users</span></span>

<span data-ttu-id="b0662-134">U kunt op een aantal manieren naar een lijst met gebruikers met beperkte toegang navigeren.</span><span class="sxs-lookup"><span data-stu-id="b0662-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="b0662-135">In dit voorbeeld kunt u in het beveiligings & compliance de gebruikers **met** \>  \> **beperkte toegang** controleren.</span><span class="sxs-lookup"><span data-stu-id="b0662-135">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="b0662-136">In de volgende procedure wordt de navigatie in het dashboard **waarschuwingen** beschreven, wat een goede manier is om diverse soorten waarschuwingen te zien die mogelijk zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="b0662-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="b0662-137">Ga naar <https://protection.office.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="b0662-137">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="b0662-138">Kies in het navigatiedeelvenster **meldingen** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="b0662-138">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="b0662-139">Kies in de **andere waarschuwings** widget de optie **gebruikers met beperkte beperkingen**.</span><span class="sxs-lookup"><span data-stu-id="b0662-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Andere meldingen](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="b0662-141">Hiermee opent u de lijst met gebruikers met beperkte rechten.</span><span class="sxs-lookup"><span data-stu-id="b0662-141">This opens the list of restricted users.</span></span>

   ![Gebruikers met beperkingen in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="b0662-143">Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals [de beperkte gebruiker vrijgeven](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="b0662-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="b0662-144">Details van geautomatiseerde onderzoeken weergeven</span><span class="sxs-lookup"><span data-stu-id="b0662-144">View details about automated investigations</span></span>

<span data-ttu-id="b0662-145">Wanneer een geautomatiseerd onderzoek is begonnen, kunt u de details en resultaten bekijken in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="b0662-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="b0662-146">Ga naar onderzoek voor **Threat Management** \> en selecteer een onderzoek om de details ervan weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b0662-146">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="b0662-147">Zie [Details van een onderzoek weergeven](air-view-investigation-results.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b0662-147">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="b0662-148">Let op de volgende punten</span><span class="sxs-lookup"><span data-stu-id="b0662-148">Keep the following points in mind</span></span>

- <span data-ttu-id="b0662-149">**Blijf op de hoogte van uw meldingen**.</span><span class="sxs-lookup"><span data-stu-id="b0662-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="b0662-150">Aangezien u weet, loopt het langer een aanval niet, hoe groter de potentiële impact en kosten voor uw organisatie, klanten en partners.</span><span class="sxs-lookup"><span data-stu-id="b0662-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="b0662-151">Vroegtijdige detectie en tijdig antwoord zijn essentieel voor het beperken van bedreigingen en vooral wanneer het account van een gebruiker wordt aangetast.</span><span class="sxs-lookup"><span data-stu-id="b0662-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="b0662-152">**Automatisering assistt, maar het team van uw beveiligingsactiviteiten wordt niet vervangen**.</span><span class="sxs-lookup"><span data-stu-id="b0662-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="b0662-153">Met de functie voor automatisch onderzoek en antwoord kunt u een gemanipuleerde gebruiker op een vroeg moment detecteren, maar het team van uw beveiligingsactiviteiten dient waarschijnlijk een oplossing te bieden voor onderzoek en herstel.</span><span class="sxs-lookup"><span data-stu-id="b0662-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="b0662-154">Hebt u hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="b0662-154">Need some help with this?</span></span> <span data-ttu-id="b0662-155">Zie [acties controleren en goedkeuren](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="b0662-155">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="b0662-156">**Vertrouw niet op een verdachte aanmeldingen als u maar wilt**.</span><span class="sxs-lookup"><span data-stu-id="b0662-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="b0662-157">Als een gebruikersaccount wordt gekraakt, wordt dit mogelijk veroorzaakt door een verdachte inlog signaal.</span><span class="sxs-lookup"><span data-stu-id="b0662-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="b0662-158">Soms is het de reeks activiteiten die zich voordoen nadat een account is geknoeid en een melding wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="b0662-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="b0662-159">Wilt u meer weten over waarschuwingen?</span><span class="sxs-lookup"><span data-stu-id="b0662-159">Want to know more about alerts?</span></span> <span data-ttu-id="b0662-160">Zie [waarschuwings beleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="b0662-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0662-161">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b0662-161">Next steps</span></span>

- [<span data-ttu-id="b0662-162">Controleer de vereiste machtigingen voor het gebruik van lucht mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="b0662-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="b0662-163">Schadelijke e-mail zoeken en onderzoeken in Office 365</span><span class="sxs-lookup"><span data-stu-id="b0662-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="b0662-164">Meer informatie over AIR in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="b0662-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="b0662-165">Ga naar het Microsoft 365-wegwijzer om te zien wat er binnenkort beschikbaar is en rollen</span><span class="sxs-lookup"><span data-stu-id="b0662-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
