---
title: Microsoft Secure Score
description: Beschrijft Microsoft Secure Score in het Microsoft 365 beveiligingscentrum, hoe u uw beveiligingsbeleid kunt verbeteren en wat beveiligingsbeheerders kunnen verwachten.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 4a2c220cab15751671b9b38c3bb2fda3db12c9e1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245373"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="1eb05-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="1eb05-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1eb05-105">Microsoft Secure Score is een meting van de beveiligingsstatus van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteracties zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1eb05-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="1eb05-106">U vindt deze in https://security.microsoft.com/securescore het Microsoft 365 [beveiligingscentrum.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="1eb05-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="1eb05-107">Als u de aanbevelingen voor secure score volgt, kunt u uw organisatie beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="1eb05-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="1eb05-108">Vanuit een gecentraliseerd dashboard in Microsoft 365 beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365 identiteiten, apps en apparaten controleren en er aan werken.</span><span class="sxs-lookup"><span data-stu-id="1eb05-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="1eb05-109">Secure Score helpt organisaties:</span><span class="sxs-lookup"><span data-stu-id="1eb05-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="1eb05-110">Rapport over de huidige status van de beveiligingsstatus van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="1eb05-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="1eb05-111">Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, richtlijnen en controle te bieden.</span><span class="sxs-lookup"><span data-stu-id="1eb05-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="1eb05-112">Vergelijk dit met benchmarks en stel KPI's (Key Performance Indicators) vast.</span><span class="sxs-lookup"><span data-stu-id="1eb05-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="1eb05-113">Organisaties krijgen toegang tot krachtige visualisaties van meetgegevens en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="1eb05-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="1eb05-114">De score kan ook worden weergegeven wanneer oplossingen van derden aanbevolen acties hebben aangepakt.</span><span class="sxs-lookup"><span data-stu-id="1eb05-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Startpagina van Secure Score](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a><span data-ttu-id="1eb05-116">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="1eb05-116">How it works</span></span>

<span data-ttu-id="1eb05-117">U krijgt punten voor de volgende acties:</span><span class="sxs-lookup"><span data-stu-id="1eb05-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="1eb05-118">Aanbevolen beveiligingsfuncties configureren</span><span class="sxs-lookup"><span data-stu-id="1eb05-118">Configuring recommended security features</span></span>
- <span data-ttu-id="1eb05-119">Beveiligingsgerelateerde taken uitvoeren</span><span class="sxs-lookup"><span data-stu-id="1eb05-119">Doing security-related tasks</span></span>
- <span data-ttu-id="1eb05-120">De verbeteringsactie aanpakken met een toepassing of software van derden, of een alternatieve beperking</span><span class="sxs-lookup"><span data-stu-id="1eb05-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="1eb05-121">Sommige verbeteracties geven alleen punten wanneer ze volledig zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="1eb05-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="1eb05-122">Sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1eb05-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="1eb05-123">Als u een van de verbeteracties niet of niet wilt uitvoeren, kunt u ervoor kiezen om het risico of het resterende risico te accepteren.</span><span class="sxs-lookup"><span data-stu-id="1eb05-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="1eb05-124">Als u een licentie hebt voor een van de ondersteunde Microsoft-producten, ziet u aanbevelingen voor deze producten.</span><span class="sxs-lookup"><span data-stu-id="1eb05-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="1eb05-125">We tonen u de volledige reeks mogelijke verbeteringen voor een product, ongeacht de licentieeditie, het abonnement of het abonnement.</span><span class="sxs-lookup"><span data-stu-id="1eb05-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="1eb05-126">Op deze manier kunt u de best practices voor beveiliging begrijpen en uw score verbeteren.</span><span class="sxs-lookup"><span data-stu-id="1eb05-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="1eb05-127">Uw absolute beveiligingsstatus, vertegenwoordigd door Secure Score, blijft hetzelfde, ongeacht welke licenties uw organisatie bezit voor een bepaald product.</span><span class="sxs-lookup"><span data-stu-id="1eb05-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="1eb05-128">Houd er rekening mee dat beveiliging in balans moet zijn met bruikbaarheid en dat niet elke aanbeveling kan werken voor uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="1eb05-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="1eb05-129">Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven op de actiepagina's visualisaties en verbetering.</span><span class="sxs-lookup"><span data-stu-id="1eb05-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="1eb05-130">Secure Score wordt ook dagelijks gesynchroniseerd om systeemgegevens over uw behaalde punten voor elke actie te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1eb05-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="1eb05-131">Belangrijke scenario's</span><span class="sxs-lookup"><span data-stu-id="1eb05-131">Key scenarios</span></span>

- [<span data-ttu-id="1eb05-132">Uw huidige score controleren</span><span class="sxs-lookup"><span data-stu-id="1eb05-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="1eb05-133">Uw score vergelijken met organisaties zoals die van u</span><span class="sxs-lookup"><span data-stu-id="1eb05-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="1eb05-134">Verbeteracties bekijken en een actieplan bepalen</span><span class="sxs-lookup"><span data-stu-id="1eb05-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="1eb05-135">Werkstromen starten om te onderzoeken of te implementeren</span><span class="sxs-lookup"><span data-stu-id="1eb05-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="1eb05-136">Hoe verbeteracties worden gescored</span><span class="sxs-lookup"><span data-stu-id="1eb05-136">How improvement actions are scored</span></span>

<span data-ttu-id="1eb05-137">Elke verbeteringsactie is 10 punten of minder waard en de meeste worden op een binaire manier gescored.</span><span class="sxs-lookup"><span data-stu-id="1eb05-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="1eb05-138">Als u de verbeteringsactie implementeert, zoals een nieuw beleid maken of een specifieke instelling in te stellen, krijgt u 100% van de punten.</span><span class="sxs-lookup"><span data-stu-id="1eb05-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="1eb05-139">Voor andere verbeteracties worden punten gegeven als een percentage van de totale configuratie.</span><span class="sxs-lookup"><span data-stu-id="1eb05-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="1eb05-140">Een verbeteringsactie geeft bijvoorbeeld aan dat u 10 punten krijgt door al uw gebruikers te beschermen met meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="1eb05-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="1eb05-141">U hebt slechts 50 van de 100 totale gebruikers beveiligd, dus u krijgt een gedeeltelijke score van 5 punten (50 beveiligde / 100 totaal \* 10 max pts = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="1eb05-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="1eb05-142">Producten die zijn opgenomen in Secure Score</span><span class="sxs-lookup"><span data-stu-id="1eb05-142">Products included in Secure Score</span></span>

<span data-ttu-id="1eb05-143">Momenteel zijn er aanbevelingen voor de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="1eb05-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="1eb05-144">Microsoft 365 (inclusief Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="1eb05-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="1eb05-145">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1eb05-145">Azure Active Directory</span></span>
- <span data-ttu-id="1eb05-146">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1eb05-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1eb05-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1eb05-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="1eb05-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1eb05-148">Cloud App Security</span></span>
- <span data-ttu-id="1eb05-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1eb05-149">Microsoft Teams</span></span>

<span data-ttu-id="1eb05-150">Aanbevelingen voor andere beveiligingsproducten zijn binnenkort beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1eb05-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="1eb05-151">De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn wel een goede basislijn.</span><span class="sxs-lookup"><span data-stu-id="1eb05-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="1eb05-152">U kunt de verbeteracties ook markeren als gedekt door een derde partij of alternatieve mitigatie.</span><span class="sxs-lookup"><span data-stu-id="1eb05-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="1eb05-153">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="1eb05-153">Security defaults</span></span>

<span data-ttu-id="1eb05-154">Microsoft Secure Score heeft verbeteracties bijgewerkt ter ondersteuning van beveiligingsinstellingen [in Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waardoor u uw organisatie gemakkelijker kunt beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.</span><span class="sxs-lookup"><span data-stu-id="1eb05-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="1eb05-155">Als u beveiligings defaults in ingeschakeld, krijgt u volledige punten voor de volgende verbeteringsacties:</span><span class="sxs-lookup"><span data-stu-id="1eb05-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="1eb05-156">Zorg ervoor dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang (9 punten)</span><span class="sxs-lookup"><span data-stu-id="1eb05-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="1eb05-157">MFA vereisen voor beheerdersrollen (10 punten)</span><span class="sxs-lookup"><span data-stu-id="1eb05-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="1eb05-158">Beleid inschakelen om oudere verificatie te blokkeren (7 punten)</span><span class="sxs-lookup"><span data-stu-id="1eb05-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="1eb05-159">Beveiligings defaults omvatten beveiligingsfuncties die vergelijkbare beveiliging bieden als het 'aanmeldingsbeleid' en 'user risk policy' verbeteracties.</span><span class="sxs-lookup"><span data-stu-id="1eb05-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="1eb05-160">In plaats van dit beleid in te stellen boven op de beveiligings defaults, raden we aan hun statussen bij te werken naar 'Opgelost via alternatieve beperking'.</span><span class="sxs-lookup"><span data-stu-id="1eb05-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="1eb05-161">Vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="1eb05-161">Required permissions</span></span>

<span data-ttu-id="1eb05-162">Als u toestemming wilt hebben voor toegang tot Microsoft Secure Score, moet u een van de volgende rollen in de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1eb05-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="1eb05-163">Rollen lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="1eb05-163">Read and write roles</span></span>

<span data-ttu-id="1eb05-164">Met lees- en schrijftoegang kunt u wijzigingen aanbrengen en rechtstreeks werken met Secure Score.</span><span class="sxs-lookup"><span data-stu-id="1eb05-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="1eb05-165">U kunt ook alleen-lezen toegang toewijzen aan andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1eb05-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="1eb05-166">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-166">Global administrator</span></span>
* <span data-ttu-id="1eb05-167">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-167">Security administrator</span></span>
* <span data-ttu-id="1eb05-168">Exchange-beheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-168">Exchange administrator</span></span>
* <span data-ttu-id="1eb05-169">SharePoint-beheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-169">SharePoint administrator</span></span>
* <span data-ttu-id="1eb05-170">Accountbeheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="1eb05-171">Alleen-lezen rollen</span><span class="sxs-lookup"><span data-stu-id="1eb05-171">Read-only roles</span></span>

<span data-ttu-id="1eb05-172">Met alleen-lezen toegang kunt u de status of notities niet bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="1eb05-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="1eb05-173">Helpdeskbeheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-173">Helpdesk administrator</span></span>
* <span data-ttu-id="1eb05-174">Gebruikersbeheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-174">User administrator</span></span>
* <span data-ttu-id="1eb05-175">Servicebeheerder</span><span class="sxs-lookup"><span data-stu-id="1eb05-175">Service administrator</span></span>
* <span data-ttu-id="1eb05-176">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="1eb05-176">Security reader</span></span>
* <span data-ttu-id="1eb05-177">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="1eb05-177">Security operator</span></span>
* <span data-ttu-id="1eb05-178">Globale lezer</span><span class="sxs-lookup"><span data-stu-id="1eb05-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="1eb05-179">Risicobewustzijn</span><span class="sxs-lookup"><span data-stu-id="1eb05-179">Risk awareness</span></span>

<span data-ttu-id="1eb05-180">Microsoft Secure Score is een numerieke samenvatting van uw beveiligingsstatus op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen.</span><span class="sxs-lookup"><span data-stu-id="1eb05-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="1eb05-181">Het is geen absolute meting van de kans dat uw systeem of gegevens worden geschonden.</span><span class="sxs-lookup"><span data-stu-id="1eb05-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="1eb05-182">In plaats van de mate waarin u beveiligingsbesturingselementen hebt aangenomen in uw Microsoft-omgeving, kan dit helpen het risico op inbreuken te compenseren.</span><span class="sxs-lookup"><span data-stu-id="1eb05-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="1eb05-183">Geen enkele onlineservice is niet gevrijwaard van beveiligingsinbreuken en een veilige score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op welke manier dan ook.</span><span class="sxs-lookup"><span data-stu-id="1eb05-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="1eb05-184">Wij horen graag van u</span><span class="sxs-lookup"><span data-stu-id="1eb05-184">We want to hear from you</span></span>

<span data-ttu-id="1eb05-185">Als u problemen hebt, laat het ons weten door een bericht te plaatsen in de [beveiligings-, privacy- & Compliance-community.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="1eb05-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="1eb05-186">We houden de community in de gaten en bieden hulp.</span><span class="sxs-lookup"><span data-stu-id="1eb05-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="1eb05-187">Verwante informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="1eb05-187">Related resources</span></span>

- [<span data-ttu-id="1eb05-188">Uw beveiligingspositie vaststellen</span><span class="sxs-lookup"><span data-stu-id="1eb05-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="1eb05-189">Uw Microsoft Secure Score-geschiedenis bijhouden en doelstellingen behalen</span><span class="sxs-lookup"><span data-stu-id="1eb05-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="1eb05-190">Binnenkort beschikbaar</span><span class="sxs-lookup"><span data-stu-id="1eb05-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="1eb05-191">Nieuwe functies</span><span class="sxs-lookup"><span data-stu-id="1eb05-191">What's new</span></span>](microsoft-secure-score-whats-new.md)