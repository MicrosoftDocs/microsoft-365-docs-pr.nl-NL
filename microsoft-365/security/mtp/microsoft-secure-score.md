---
title: Microsoft Secure Score
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe u het beveiligingsbeleid verbetert en wat beveiligingsbeheerders kunnen verwachten.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft-beveiligingsscore, Microsoft 365-beveiligingscentrum, acties voor verbetering
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930580"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="50373-104">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="50373-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="50373-105">Microsoft Secure Score is een meting van de beveiligingsrisico's van een organisatie, met een hoger getal dat aangeeft dat er meer acties zijn ondernomen.</span><span class="sxs-lookup"><span data-stu-id="50373-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="50373-106">U vindt deze in https://security.microsoft.com/securescore het [Microsoft 365-beveiligingscentrum.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="50373-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="50373-107">Als u de aanbevelingen van Secure Score volgt, kunt u uw organisatie beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="50373-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="50373-108">Vanuit een centraal dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, -apps en -apparaten controleren en er aan werken.</span><span class="sxs-lookup"><span data-stu-id="50373-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="50373-109">Secure Score helpt organisaties met het volgende:</span><span class="sxs-lookup"><span data-stu-id="50373-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="50373-110">Rapporteer over de huidige status van de beveiligingsrisico's van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="50373-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="50373-111">Verbeter de beveiligingsmogelijkheden door zichtbaarheid, zichtbaarheid, begeleiding en controle te bieden.</span><span class="sxs-lookup"><span data-stu-id="50373-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="50373-112">Vergelijk met benchmarks en stel KPI's (Key Performance Indicators) op.</span><span class="sxs-lookup"><span data-stu-id="50373-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="50373-113">Organisaties krijgen toegang tot krachtige visualisaties van meetwaarden en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="50373-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="50373-114">De score kan ook worden weergegeven wanneer aanbevolen acties door externe oplossingen zijn aangepakt.</span><span class="sxs-lookup"><span data-stu-id="50373-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Secure Score-startpagina](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="50373-116">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="50373-116">How it works</span></span>

<span data-ttu-id="50373-117">U krijgt punten voor de volgende acties:</span><span class="sxs-lookup"><span data-stu-id="50373-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="50373-118">Aanbevolen beveiligingsfuncties configureren</span><span class="sxs-lookup"><span data-stu-id="50373-118">Configuring recommended security features</span></span>
- <span data-ttu-id="50373-119">Beveiligingstaken uitvoeren</span><span class="sxs-lookup"><span data-stu-id="50373-119">Doing security-related tasks</span></span>
- <span data-ttu-id="50373-120">Het aanpakken van de actie voor verbetering met een toepassing of software van derden, of een alternatieve risicobeperking</span><span class="sxs-lookup"><span data-stu-id="50373-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="50373-121">Sommige acties voor kwaliteitsverbetering geven alleen punten wanneer ze volledig zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="50373-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="50373-122">Sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers.</span><span class="sxs-lookup"><span data-stu-id="50373-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="50373-123">Als u een van de acties ter verbetering niet of niet wilt uitvoeren, kunt u ervoor kiezen het risico of het resterende risico te accepteren.</span><span class="sxs-lookup"><span data-stu-id="50373-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="50373-124">Als u een licentie hebt voor een van de ondersteunde Microsoft-producten, ziet u aanbevelingen voor deze producten.</span><span class="sxs-lookup"><span data-stu-id="50373-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="50373-125">U ziet alle mogelijke verbeteringen voor een product, ongeacht de licentie-versie, het abonnement of het abonnement.</span><span class="sxs-lookup"><span data-stu-id="50373-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="50373-126">Op deze manier begrijpt u de beste beveiligingsprocedures en verbetert u uw score.</span><span class="sxs-lookup"><span data-stu-id="50373-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="50373-127">Uw absolute beveiligingsrisico, vertegenwoordigd door Secure Score, blijft hetzelfde, ongeacht de licenties die uw organisatie bezit voor een specifiek product.</span><span class="sxs-lookup"><span data-stu-id="50373-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="50373-128">Houd er rekening mee dat beveiliging moet worden gebalanceerd met bruikbaarheid en dat niet elke aanbeveling voor uw omgeving kan werken.</span><span class="sxs-lookup"><span data-stu-id="50373-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="50373-129">Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven op de visualisaties en actiepagina's voor verbetering.</span><span class="sxs-lookup"><span data-stu-id="50373-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="50373-130">Secure Score synchroniseert ook dagelijks met systeemgegevens over uw bereikt punten voor elke actie.</span><span class="sxs-lookup"><span data-stu-id="50373-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="50373-131">Belangrijke scenario's</span><span class="sxs-lookup"><span data-stu-id="50373-131">Key scenarios</span></span>

- [<span data-ttu-id="50373-132">Uw huidige score controleren</span><span class="sxs-lookup"><span data-stu-id="50373-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="50373-133">Vergelijk uw score met organisaties zoals die van u</span><span class="sxs-lookup"><span data-stu-id="50373-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="50373-134">Acties voor verbetering weergeven en een plan van aanpak bepalen</span><span class="sxs-lookup"><span data-stu-id="50373-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="50373-135">Werkstromen starten om dit te onderzoeken of te implementeren</span><span class="sxs-lookup"><span data-stu-id="50373-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="50373-136">Hoe acties voor kwaliteitsverbetering worden gescored</span><span class="sxs-lookup"><span data-stu-id="50373-136">How improvement actions are scored</span></span>

<span data-ttu-id="50373-137">Elke verbeteringsactie is 10 punten of minder waard en de meeste worden op binaire wijze als scorescores genomen.</span><span class="sxs-lookup"><span data-stu-id="50373-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="50373-138">Als u de actie voor verbetering implementeert, zoals een nieuw beleid maken of een specifieke instelling in schakelt, krijgt u 100% van de punten.</span><span class="sxs-lookup"><span data-stu-id="50373-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="50373-139">Voor andere acties ter verbetering worden punten gegeven als een percentage van de totale configuratie.</span><span class="sxs-lookup"><span data-stu-id="50373-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="50373-140">Met een actie ter verbetering krijgt u bijvoorbeeld 10 punten door alle gebruikers te beschermen met meervoudige verificatie.</span><span class="sxs-lookup"><span data-stu-id="50373-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="50373-141">U hebt in totaal slechts 50 van de 100 gebruikers beveiligd, dus krijgt u een gedeeltelijke score van 5 punten (50 beveiligde / 100 totaal \* 10 max pts = 5 pts).</span><span class="sxs-lookup"><span data-stu-id="50373-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="50373-142">Producten die zijn opgenomen in Secure Score</span><span class="sxs-lookup"><span data-stu-id="50373-142">Products included in Secure Score</span></span>

<span data-ttu-id="50373-143">Momenteel zijn er aanbevelingen voor de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="50373-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="50373-144">Microsoft 365 (inclusief Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="50373-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="50373-145">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="50373-145">Azure Active Directory</span></span>
- <span data-ttu-id="50373-146">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="50373-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="50373-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="50373-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="50373-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="50373-148">Cloud App Security</span></span>

<span data-ttu-id="50373-149">Aanbevelingen voor andere beveiligingsproducten komen binnenkort beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="50373-149">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="50373-150">De aanbevelingen hebben niet betrekking op alle aanvallen die aan elk product zijn gekoppeld, maar ze zijn wel een goede basislijn.</span><span class="sxs-lookup"><span data-stu-id="50373-150">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="50373-151">U kunt de acties voor kwaliteitsverbetering ook markeren als gedekt door een derde partij of een alternatieve risicobeperking.</span><span class="sxs-lookup"><span data-stu-id="50373-151">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="50373-152">Standaardinstellingen voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="50373-152">Security defaults</span></span>

<span data-ttu-id="50373-153">Microsoft Secure Score heeft acties ter verbetering bijgewerkt ter ondersteuning van beveiligingsinstellingen [in Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waarmee het gemakkelijker wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor algemene aanvallen.</span><span class="sxs-lookup"><span data-stu-id="50373-153">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="50373-154">Als u beveiligingsinstellingen in ingeschakeld, krijgt u volledige punten voor de volgende acties ter verbetering:</span><span class="sxs-lookup"><span data-stu-id="50373-154">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="50373-155">Controleren of alle gebruikers meervoudige verificatie kunnen voltooien voor beveiligde toegang (9 punten)</span><span class="sxs-lookup"><span data-stu-id="50373-155">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="50373-156">MFA vereisen voor beheerdersrollen (10 punten)</span><span class="sxs-lookup"><span data-stu-id="50373-156">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="50373-157">Beleid inschakelen om verouderde verificatie te blokkeren (7 punten)</span><span class="sxs-lookup"><span data-stu-id="50373-157">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="50373-158">Beveiligingsfuncties bevatten beveiligingsfuncties die vergelijkbaar zijn met de acties voor het 'aanmeldingsrisicobeleid' en 'gebruikersrisicobeleid'.</span><span class="sxs-lookup"><span data-stu-id="50373-158">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="50373-159">In plaats van dit beleid boven op de beveiligingsinstellingen in te stellen, raden we u aan hun status bij te werken naar 'Opgelost door alternatieve risicobeperking'.</span><span class="sxs-lookup"><span data-stu-id="50373-159">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="50373-160">Vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="50373-160">Required permissions</span></span>

<span data-ttu-id="50373-161">Als u toegang wilt krijgen tot Microsoft Secure Score, moet u een van de volgende rollen in Azure Active Directory toegewezen krijgen.</span><span class="sxs-lookup"><span data-stu-id="50373-161">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="50373-162">Rollen lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="50373-162">Read and write roles</span></span>

<span data-ttu-id="50373-163">Met lees- en schrijftoegang kunt u wijzigingen aanbrengen en rechtstreeks communiceren met Secure Score.</span><span class="sxs-lookup"><span data-stu-id="50373-163">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="50373-164">U kunt ook alleen-lezentoegang toewijzen aan andere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="50373-164">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="50373-165">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="50373-165">Global administrator</span></span>
* <span data-ttu-id="50373-166">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="50373-166">Security administrator</span></span>
* <span data-ttu-id="50373-167">Exchange-beheerder</span><span class="sxs-lookup"><span data-stu-id="50373-167">Exchange administrator</span></span>
* <span data-ttu-id="50373-168">SharePoint-beheerder</span><span class="sxs-lookup"><span data-stu-id="50373-168">SharePoint administrator</span></span>
* <span data-ttu-id="50373-169">Accountbeheerder</span><span class="sxs-lookup"><span data-stu-id="50373-169">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="50373-170">Alleen-lezen rollen</span><span class="sxs-lookup"><span data-stu-id="50373-170">Read-only roles</span></span>

<span data-ttu-id="50373-171">Met alleen-lezen toegang kunt u geen status of notities bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="50373-171">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="50373-172">Helpdeskbeheerder</span><span class="sxs-lookup"><span data-stu-id="50373-172">Helpdesk administrator</span></span>
* <span data-ttu-id="50373-173">Gebruikersbeheerder</span><span class="sxs-lookup"><span data-stu-id="50373-173">User administrator</span></span>
* <span data-ttu-id="50373-174">Servicebeheerder</span><span class="sxs-lookup"><span data-stu-id="50373-174">Service administrator</span></span>
* <span data-ttu-id="50373-175">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="50373-175">Security reader</span></span>
* <span data-ttu-id="50373-176">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="50373-176">Security operator</span></span>
* <span data-ttu-id="50373-177">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="50373-177">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="50373-178">Risico-bekendheid</span><span class="sxs-lookup"><span data-stu-id="50373-178">Risk awareness</span></span>

<span data-ttu-id="50373-179">Microsoft Secure Score is een numeriek overzicht van uw beveiligingsrisico op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde afmetingen.</span><span class="sxs-lookup"><span data-stu-id="50373-179">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="50373-180">Het is geen absolute maateenheid voor de kans dat uw systeem of gegevens worden geschonden.</span><span class="sxs-lookup"><span data-stu-id="50373-180">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="50373-181">Het vertegenwoordigt in plaats van de mate waarin u beveiligingscontroles hebt overgenomen in uw Microsoft-omgeving, waardoor het risico op inbreuk kan worden verschoven.</span><span class="sxs-lookup"><span data-stu-id="50373-181">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="50373-182">Er is geen online service die te maken heeft met beveiligingsinbreuken en secure score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op welke manier dan ook.</span><span class="sxs-lookup"><span data-stu-id="50373-182">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="50373-183">Wij horen graag van u</span><span class="sxs-lookup"><span data-stu-id="50373-183">We want to hear from you</span></span>

<span data-ttu-id="50373-184">Als u problemen hebt, laat het ons dan weten door berichten te plaatsen in de community [over beveiliging, & compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="50373-184">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="50373-185">We houden de community in de gaten en bieden hulp.</span><span class="sxs-lookup"><span data-stu-id="50373-185">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="50373-186">Verwante informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="50373-186">Related resources</span></span>

- [<span data-ttu-id="50373-187">Uw beveiligingspositie vaststellen</span><span class="sxs-lookup"><span data-stu-id="50373-187">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="50373-188">Uw geschiedenis van Microsoft Secure Score bijhouden en doelstellingen behalen</span><span class="sxs-lookup"><span data-stu-id="50373-188">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="50373-189">Binnenkort beschikbaar</span><span class="sxs-lookup"><span data-stu-id="50373-189">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="50373-190">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="50373-190">What's new</span></span>](microsoft-secure-score-whats-new.md)
