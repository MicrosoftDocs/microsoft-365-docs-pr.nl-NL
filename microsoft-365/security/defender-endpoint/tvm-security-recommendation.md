---
title: Beveiligingsaanbevelingen van Threat and Vulnerability Management
description: Krijg actiebare beveiligingsaanbevelingen die prioriteit krijgen op basis van bedreiging, waarschijnlijkheid dat deze wordt geschonden en waarde, in Threat and Vulnerability Management.
keywords: Threat and Vulnerability Management, Microsoft Defender voor endpoint tvm-beveiligingsaanbeveling, aanbeveling voor cyberbeveiliging, actie-aanbevelingen voor beveiliging
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933731"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="3de5a-104">Beveiligingsaanbevelingen - Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="3de5a-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3de5a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3de5a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3de5a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3de5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3de5a-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="3de5a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3de5a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3de5a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3de5a-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3de5a-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3de5a-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="3de5a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="3de5a-111">Zwakke punten in de cyberbeveiliging die in uw organisatie zijn geïdentificeerd, worden in kaart gebracht aan actiebare beveiligingsaanbevelingen en worden geprioriteerd op basis van hun impact.</span><span class="sxs-lookup"><span data-stu-id="3de5a-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="3de5a-112">Met prioriteitsaanbevelingen kunt u de tijd verkorten om beveiligingsproblemen te beperken of te verhelpen en naleving te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="3de5a-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="3de5a-113">Elke beveiligingsaanbeveling bevat actiestappen voor herstel.</span><span class="sxs-lookup"><span data-stu-id="3de5a-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="3de5a-114">Om u te helpen bij taakbeheer, kan de aanbeveling ook worden verzonden met Microsoft Intune en Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3de5a-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3de5a-115">Wanneer het bedreigingslandschap verandert, wordt de aanbeveling ook gewijzigd terwijl er continu gegevens uit uw omgeving worden verzameld.</span><span class="sxs-lookup"><span data-stu-id="3de5a-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="3de5a-116">Zie E-mailmeldingen voor kwetsbaarheid configureren in Microsoft Defender voor Eindpunt voor e-mailberichten over [nieuwe beveiligingsprobleemgebeurtenissen](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="3de5a-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="3de5a-117">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="3de5a-117">How it works</span></span>

<span data-ttu-id="3de5a-118">Elk apparaat in de organisatie wordt gescored op basis van drie belangrijke factoren om klanten te helpen zich op het juiste moment op de juiste dingen te concentreren.</span><span class="sxs-lookup"><span data-stu-id="3de5a-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="3de5a-119">**Bedreiging:** kenmerken van de beveiligingslekken en exploits in de apparaten en inbreukgeschiedenis van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3de5a-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="3de5a-120">Op basis van deze factoren worden in de beveiligingsaanbevelingen de bijbehorende koppelingen naar actieve waarschuwingen, lopende bedreigingscampagnes en bijbehorende analyserapporten voor bedreigingen weergeven.</span><span class="sxs-lookup"><span data-stu-id="3de5a-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="3de5a-121">**Kans op inbreuk** : de beveiligingsstatus en tolerantie van uw organisatie tegen bedreigingen</span><span class="sxs-lookup"><span data-stu-id="3de5a-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="3de5a-122">**Bedrijfswaarde:** de activa, kritieke processen en intellectuele eigenschappen van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="3de5a-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="3de5a-123">Naar de pagina Beveiligingsaanbevelingen gaan</span><span class="sxs-lookup"><span data-stu-id="3de5a-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="3de5a-124">Toegang tot de pagina Beveiligingsaanbevelingen op verschillende manieren:</span><span class="sxs-lookup"><span data-stu-id="3de5a-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="3de5a-125">Het navigatiemenu bedreiging vulnerability management in de [Microsoft Defender-beveiligingscentrum](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3de5a-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="3de5a-126">Belangrijkste beveiligingsaanbevelingen in het [Threat and Vulnerability Management dashboard](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="3de5a-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="3de5a-127">Verwante beveiligingsaanbevelingen weergeven op de volgende plaatsen:</span><span class="sxs-lookup"><span data-stu-id="3de5a-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="3de5a-128">Softwarepagina</span><span class="sxs-lookup"><span data-stu-id="3de5a-128">Software page</span></span>
- <span data-ttu-id="3de5a-129">Apparaatpagina</span><span class="sxs-lookup"><span data-stu-id="3de5a-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="3de5a-130">Navigatiemenu</span><span class="sxs-lookup"><span data-stu-id="3de5a-130">Navigation menu</span></span>

<span data-ttu-id="3de5a-131">Ga naar het Threat and Vulnerability Management navigatiemenu en selecteer **Beveiligingsaanbevelingen.**</span><span class="sxs-lookup"><span data-stu-id="3de5a-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="3de5a-132">De pagina bevat een lijst met beveiligingsaanbevelingen voor de bedreigingen en beveiligingsproblemen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3de5a-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="3de5a-133">Belangrijkste beveiligingsaanbevelingen in het Threat and Vulnerability Management dashboard</span><span class="sxs-lookup"><span data-stu-id="3de5a-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="3de5a-134">Op een bepaalde dag als beveiligingsbeheerder kunt u het [Threat and Vulnerability Management-dashboard](tvm-dashboard-insights.md) [](tvm-exposure-score.md) bekijken om uw blootstellingsscore naast uw [Microsoft Secure Score voor apparaten te zien.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="3de5a-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="3de5a-135">Het doel is **om** de blootstelling van uw  organisatie aan beveiligingsproblemen te verlagen en de apparaatbeveiliging van uw organisatie te verhogen om beter bestand te zijn tegen cyberbeveiligingsaanvallen.</span><span class="sxs-lookup"><span data-stu-id="3de5a-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="3de5a-136">De lijst met beste beveiligingsaanbevelingen kan u helpen dat doel te bereiken.</span><span class="sxs-lookup"><span data-stu-id="3de5a-136">The top security recommendations list can help you achieve that goal.</span></span>

![Voorbeeld van De beste beveiligingsaanbevelingskaart, met vier beveiligingsaanbevelingen.](images/top-security-recommendations350.png)

<span data-ttu-id="3de5a-138">In de belangrijkste beveiligingsaanbevelingen worden de verbeterkansen vermeld die zijn geprioriteerd op basis van de belangrijke factoren die in de vorige sectie worden genoemd: bedreiging, kans op inbreuk en waarde.</span><span class="sxs-lookup"><span data-stu-id="3de5a-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="3de5a-139">Als u een aanbeveling selecteert, gaat u naar de pagina met beveiligingsaanbevelingen met meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3de5a-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="3de5a-140">Overzicht van beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="3de5a-140">Security recommendations overview</span></span>

<span data-ttu-id="3de5a-141">Bekijk aanbevelingen, het aantal gevonden zwakke punten, gerelateerde onderdelen, bedreigingsinzichten, aantal blootgestelde apparaten, status, hersteltype, herstelactiviteiten, invloed op uw blootstellingsscore en Microsoft Secure Score voor apparaten en bijbehorende tags.</span><span class="sxs-lookup"><span data-stu-id="3de5a-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="3de5a-142">De kleur van de **grafiek Exposed-apparaten** wordt gewijzigd naarmate de trend verandert.</span><span class="sxs-lookup"><span data-stu-id="3de5a-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="3de5a-143">Als het aantal blootgestelde apparaten toe neemt, verandert de kleur in rood.</span><span class="sxs-lookup"><span data-stu-id="3de5a-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="3de5a-144">Als het aantal blootgestelde apparaten afneemt, verandert de kleur van de grafiek in groen.</span><span class="sxs-lookup"><span data-stu-id="3de5a-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="3de5a-145">Bedreiging en vulnerability management toont apparaten die tot **30** dagen geleden werden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3de5a-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="3de5a-146">Dit is anders dan de rest van Microsoft Defender voor Eindpunt, waarbij een apparaat dat langer dan 7 dagen niet in gebruik is, een inactieve status heeft.</span><span class="sxs-lookup"><span data-stu-id="3de5a-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Voorbeeld van de landingspagina voor beveiligingsaanbevelingen.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="3de5a-148">Pictogrammen</span><span class="sxs-lookup"><span data-stu-id="3de5a-148">Icons</span></span>

<span data-ttu-id="3de5a-149">Met handige pictogrammen kunt u ook snel de aandacht vestigen op:</span><span class="sxs-lookup"><span data-stu-id="3de5a-149">Useful icons also quickly call your attention to:</span></span>
- ![pijl die een doel raakt](images/tvm_alert_icon.png) <span data-ttu-id="3de5a-151">mogelijke actieve waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="3de5a-151">possible active alerts</span></span>
- ![rode bug](images/tvm_bug_icon.png) <span data-ttu-id="3de5a-153">bijbehorende openbare exploits</span><span class="sxs-lookup"><span data-stu-id="3de5a-153">associated public exploits</span></span>
- ![gloeilamp](images/tvm_insight_icon.png) <span data-ttu-id="3de5a-155">aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="3de5a-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="3de5a-156">Opties voor beveiligingsaanbeveling verkennen</span><span class="sxs-lookup"><span data-stu-id="3de5a-156">Explore security recommendation options</span></span>

<span data-ttu-id="3de5a-157">Selecteer de beveiligingsaanbeveling die u wilt onderzoeken of verwerken.</span><span class="sxs-lookup"><span data-stu-id="3de5a-157">Select the security recommendation that you want to investigate or process.</span></span>

![Voorbeeld van een flyoutpagina met beveiligingsaanbevelingen.](images/secrec-flyouteolsw.png)

<span data-ttu-id="3de5a-159">In het flyout kunt u een van de volgende opties kiezen:</span><span class="sxs-lookup"><span data-stu-id="3de5a-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="3de5a-160">**Open de softwarepagina:** open de softwarepagina om meer context te krijgen over de software en hoe deze wordt gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="3de5a-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="3de5a-161">De informatie kan bedreigingscontext, bijbehorende aanbevelingen, gevonden zwakke punten, het aantal blootgestelde apparaten, gevonden beveiligingslekken, namen en gedetailleerde apparaten met de geïnstalleerde software en de distributie van versies omvatten.</span><span class="sxs-lookup"><span data-stu-id="3de5a-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="3de5a-162">[**Herstelopties:**](tvm-remediation.md) verzend een herstelaanvraag om een ticket te openen in Microsoft Intune om uw IT-beheerder op te halen en te adresseren.</span><span class="sxs-lookup"><span data-stu-id="3de5a-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="3de5a-163">Houd de herstelactiviteit bij op de pagina Herstel.</span><span class="sxs-lookup"><span data-stu-id="3de5a-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="3de5a-164">[**Uitzonderingsopties:**](tvm-exception.md) verzend een uitzondering, geef rechtvaardiging en stel de duur van de uitzondering in als u het probleem nog niet kunt verhelpen.</span><span class="sxs-lookup"><span data-stu-id="3de5a-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="3de5a-165">Wanneer een softwarewijziging wordt aangebracht op een apparaat, duurt het meestal 2 uur voordat de gegevens worden weergegeven in de beveiligingsportal.</span><span class="sxs-lookup"><span data-stu-id="3de5a-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="3de5a-166">Het kan echter soms langer duren.</span><span class="sxs-lookup"><span data-stu-id="3de5a-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="3de5a-167">Configuratiewijzigingen kunnen 4 tot 24 uur duren.</span><span class="sxs-lookup"><span data-stu-id="3de5a-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="3de5a-168">Wijzigingen in apparaatblootstelling of -impact onderzoeken</span><span class="sxs-lookup"><span data-stu-id="3de5a-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="3de5a-169">Als er een grote sprong is gemaakt in het aantal blootgestelde apparaten of als het effect op de blootstellingsscore van uw organisatie en Microsoft Secure Score voor apparaten sterk is toegenomen, is deze beveiligingsaanbeveling het onderzoeken waard.</span><span class="sxs-lookup"><span data-stu-id="3de5a-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="3de5a-170">Selecteer de aanbevelingspagina en **de pagina Software openen**</span><span class="sxs-lookup"><span data-stu-id="3de5a-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="3de5a-171">Selecteer het **tabblad Tijdlijn** van gebeurtenis om alle impactvolle gebeurtenissen met betrekking tot die software weer te geven, zoals nieuwe beveiligingslekken of nieuwe openbare exploits.</span><span class="sxs-lookup"><span data-stu-id="3de5a-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="3de5a-172">Meer informatie over de tijdlijn van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="3de5a-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="3de5a-173">Bepaal hoe u de toename of de blootstelling van uw organisatie kunt aanpakken, zoals het indienen van een herstelaanvraag</span><span class="sxs-lookup"><span data-stu-id="3de5a-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="3de5a-174">Herstelverzoeken</span><span class="sxs-lookup"><span data-stu-id="3de5a-174">Request remediation</span></span>

<span data-ttu-id="3de5a-175">De Threat and Vulnerability Management herstelfunctie overbrugt de kloof tussen beveiligings- en IT-beheerders via de werkstroom voor herstelverzoeken.</span><span class="sxs-lookup"><span data-stu-id="3de5a-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="3de5a-176">Beveiligingsbeheerders zoals u kunnen de IT-beheerder vragen om een beveiligingsprobleem op te verhelpen vanaf de pagina **Beveiligingsaanbeveling** naar Intune.</span><span class="sxs-lookup"><span data-stu-id="3de5a-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="3de5a-177">Meer informatie over herstelopties</span><span class="sxs-lookup"><span data-stu-id="3de5a-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="3de5a-178">Herstel aanvragen</span><span class="sxs-lookup"><span data-stu-id="3de5a-178">How to request remediation</span></span>

<span data-ttu-id="3de5a-179">Selecteer een beveiligingsaanbeveling voor wie u herstel wilt aanvragen en selecteer vervolgens **Herstelopties.**</span><span class="sxs-lookup"><span data-stu-id="3de5a-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="3de5a-180">Vul het formulier in en selecteer **Aanvraag indienen.**</span><span class="sxs-lookup"><span data-stu-id="3de5a-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="3de5a-181">Ga naar de [**pagina Herstel om**](tvm-remediation.md) de status van uw herstelaanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3de5a-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="3de5a-182">Meer informatie over het aanvragen van herstel</span><span class="sxs-lookup"><span data-stu-id="3de5a-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="3de5a-183">Bestand voor uitzondering</span><span class="sxs-lookup"><span data-stu-id="3de5a-183">File for exception</span></span>

<span data-ttu-id="3de5a-184">Als alternatief voor een herstelaanvraag wanneer een aanbeveling op dit moment niet relevant is, kunt u uitzonderingen maken voor aanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="3de5a-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="3de5a-185">Meer informatie over uitzonderingen</span><span class="sxs-lookup"><span data-stu-id="3de5a-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="3de5a-186">Alleen gebruikers met machtigingen voor het verwerken van uitzonderingen kunnen uitzondering toevoegen.</span><span class="sxs-lookup"><span data-stu-id="3de5a-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="3de5a-187">[Meer informatie over RBAC-rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3de5a-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="3de5a-188">Wanneer er een uitzondering wordt gemaakt voor een aanbeveling, is de aanbeveling niet meer actief.</span><span class="sxs-lookup"><span data-stu-id="3de5a-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="3de5a-189">De aanbevelingstoestand wordt gewijzigd in **Volledige uitzondering** of **Gedeeltelijke uitzondering** (per apparaatgroep).</span><span class="sxs-lookup"><span data-stu-id="3de5a-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="3de5a-190">Een uitzondering maken</span><span class="sxs-lookup"><span data-stu-id="3de5a-190">How to create an exception</span></span>

<span data-ttu-id="3de5a-191">Selecteer een beveiligingsaanbeveling voor wie u een uitzondering wilt maken en selecteer vervolgens **Uitzonderingsopties.**</span><span class="sxs-lookup"><span data-stu-id="3de5a-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Hier wordt weergegeven waar de knop voor 'uitzonderingsopties' zich bevindt in een flyout voor beveiligingsaanbeveling.](images/tvm-exception-options.png)

<span data-ttu-id="3de5a-193">Vul het formulier in en verzend het.</span><span class="sxs-lookup"><span data-stu-id="3de5a-193">Fill out the form and submit.</span></span> <span data-ttu-id="3de5a-194">Als u al uw uitzonderingen (huidig [](tvm-remediation.md) en verleden) wilt weergeven, gaat u naar  de pagina Herstel onder het menu Beveiligingsprobleembeheer bedreiging **&** en selecteert u het tabblad Uitzonderingen. Meer informatie over het maken van een [uitzondering](tvm-exception.md#create-an-exception)</span><span class="sxs-lookup"><span data-stu-id="3de5a-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="3de5a-195">Onnauwkeurigheid van rapport</span><span class="sxs-lookup"><span data-stu-id="3de5a-195">Report inaccuracy</span></span>

<span data-ttu-id="3de5a-196">U kunt een onwaar positief rapport rapporteren wanneer u vage, onnauwkeurige, onvolledige of al gesaneerde beveiligingsaanbevelingsgegevens ziet.</span><span class="sxs-lookup"><span data-stu-id="3de5a-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="3de5a-197">Open de beveiligingsaanbeveling.</span><span class="sxs-lookup"><span data-stu-id="3de5a-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="3de5a-198">Selecteer de drie puntjes naast de beveiligingsaanbeveling die u wilt rapporteren en selecteer vervolgens Onnauwkeurigheid **rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="3de5a-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Hier wordt weergegeven waar de knop Onnauwkeurigheid melden zich in een flyout voor beveiligingsaanbevelingen.](images/report-inaccuracy500.png)

3. <span data-ttu-id="3de5a-200">Selecteer in het deelvenster Flyout de onnauwkeurigheidscategorie in de vervolgkeuzelijst, vul uw e-mailadres in en details over de onnauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="3de5a-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="3de5a-201">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="3de5a-201">Select **Submit**.</span></span> <span data-ttu-id="3de5a-202">Uw feedback wordt onmiddellijk verzonden naar de Threat and Vulnerability Management experts.</span><span class="sxs-lookup"><span data-stu-id="3de5a-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3de5a-203">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3de5a-203">Related articles</span></span>

- [<span data-ttu-id="3de5a-204">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="3de5a-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3de5a-205">Dashboard</span><span class="sxs-lookup"><span data-stu-id="3de5a-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="3de5a-206">Blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="3de5a-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="3de5a-207">Microsoft Secure Score voor apparaten</span><span class="sxs-lookup"><span data-stu-id="3de5a-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="3de5a-208">Beveiligingsproblemen verhelpen</span><span class="sxs-lookup"><span data-stu-id="3de5a-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="3de5a-209">Uitzonderingen maken en weergeven voor beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="3de5a-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="3de5a-210">Tijdlijn van het evenement</span><span class="sxs-lookup"><span data-stu-id="3de5a-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
