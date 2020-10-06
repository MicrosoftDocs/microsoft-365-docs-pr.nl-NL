---
title: Uw proefproject voor Microsoft Threat Protection plannen
description: Plan uw pilot Microsoft Threat Protection-project met belanghebbenden voor het beheren van de verwachtingen en zorg voor een succesvolle uitslag.
keywords: Proefversie van Microsoft Threat Protection, proefabonnement Microsoft Threat Protection, Microsoft Threat Protection evalueren in productie, Microsoft Threat Protection pilotproject, Cyber beveiliging, Geavanceerd permanent risico, beveiliging van uw bedrijf, apparatuur, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 7d1870d1b8972009bed657f476810ca011dc2621
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367975"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="b8fc9-104">Uw proefproject voor Microsoft Threat Protection plannen</span><span class="sxs-lookup"><span data-stu-id="b8fc9-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8fc9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-105">**Applies to:**</span></span>
- <span data-ttu-id="b8fc9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8fc9-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Uw proefproject voor Microsoft Threat Protection plannen" />
      <br/><span data-ttu-id="b8fc9-108">Plannen</a></span><span class="sxs-lookup"><span data-stu-id="b8fc9-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden" />
      <br/><span data-ttu-id="b8fc9-110">Voorbereiden</a></span><span class="sxs-lookup"><span data-stu-id="b8fc9-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Simulaties van aanvallen van Microsoft Threat Protection uitvoeren" />
     <br/><span data-ttu-id="b8fc9-112">Een aanval simuleren</a></span><span class="sxs-lookup"><span data-stu-id="b8fc9-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Uw proef Microsoft Threat Protection sluiten en samenvatten" />
     <br/><span data-ttu-id="b8fc9-114">Sluiten en samenvatten</a></span><span class="sxs-lookup"><span data-stu-id="b8fc9-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="b8fc9-115">U bevindt zich momenteel in de planningsfase.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="b8fc9-116">Om ervoor te zorgen dat uw pilotproject een gunstige uitkomst is, is het van essentieel belang dat u de belanghebbenden snel goed keurt en goedkeuring van uw belanghebbenden ontvangt.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="b8fc9-117">De planning van elementen bevat identificatie bereik, gebruiks kwesties, vereisten en succescriteria.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="b8fc9-118">Deze handleiding helpt u bij het plannen van uw pilotproject.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="b8fc9-119">Volg voor optimale resultaten de instructies voor het testen.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="b8fc9-120">Scoop</span><span class="sxs-lookup"><span data-stu-id="b8fc9-120">Scope</span></span>

<span data-ttu-id="b8fc9-121">Het bereik van de leider bepaalt hoe breed de test is, op basis van uw omgeving en de acceptabele testmethoden.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="b8fc9-122">Hier volgen enkele voorbeelden van aandachtspunten:</span><span class="sxs-lookup"><span data-stu-id="b8fc9-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="b8fc9-123">Ontwikkelings-of testomgeving, waaronder eindpunten, servers, domeincontrollers.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="b8fc9-124">Productieomgeving met Microsoft 365, azure, Active Directory Services, eindpunten en servers</span><span class="sxs-lookup"><span data-stu-id="b8fc9-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="b8fc9-125">Als u de volledige licentie nog niet hebt, kunt u een proefabonnement krijgen voor het [evalueren van Microsoft Threat Protection (Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) plannen, voorbereiden, instellen, configureren en uitvoeren van uw pilotproject).</span><span class="sxs-lookup"><span data-stu-id="b8fc9-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="b8fc9-126">De belanghebbenden kunnen een belangrijke rol spelen, zodat de procedure van begin tot eind wordt vergemakkelijkt.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="b8fc9-127">De typen besturingssystemen die moeten worden geëvalueerd, worden ook gedefinieerd op basis van de organisatie-Makeup.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="b8fc9-128">Dit kan de volgende bebestaan: [Mac-eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="b8fc9-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="b8fc9-129">Gebruik zaken</span><span class="sxs-lookup"><span data-stu-id="b8fc9-129">Use cases</span></span>

<span data-ttu-id="b8fc9-130">Use-cases stellen de manier weer waarop het te testen instrument wordt gebruikt door de bedoelde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="b8fc9-131">Deze kunnen worden geformuleerd als gebruikers verhalen vanuit het oogpunt van een bepaalde persoon, zoals een SOC-analist.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="b8fc9-132">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b8fc9-132">For example:</span></span>
- <span data-ttu-id="b8fc9-133">Als SOC-analist moet ik waarschuwingen en gebeurtenissen op alle apparaten, gebruikers en postvakken in mijn netwerk weergeven, correleren, beoordelen, beoordelen en beheren.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="b8fc9-134">[Incidentenbeheer]</span><span class="sxs-lookup"><span data-stu-id="b8fc9-134">[Incident management]</span></span>
- <span data-ttu-id="b8fc9-135">Als SOC-Analyst moet ik het hulpmiddel en het proces voor het automatisch onderzoeken en beantwoorden van schadelijke gebeurtenissen in mijn netwerk hebben.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="b8fc9-136">[Automatische IR]</span><span class="sxs-lookup"><span data-stu-id="b8fc9-136">[Auto IR]</span></span>
- <span data-ttu-id="b8fc9-137">Als SOC-analist moet ik de gegevens van mijn omgeving doorzoeken om bekende, potentiële bedreigingen en verdachte activiteiten te vinden.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="b8fc9-138">[Geavanceerde jacht]</span><span class="sxs-lookup"><span data-stu-id="b8fc9-138">[Advanced Hunting]</span></span>

<span data-ttu-id="b8fc9-139">Houd er rekening mee dat het gebruik van dit soort aanvragen binnen de parameters van het gedefinieerde bereik moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="b8fc9-140">Als u bijvoorbeeld het test bereik omvat, is het niet mogelijk om een evaluatie te maken van hulpmiddelen zoals beveiliging van de Cloud-app van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8fc9-141">Vereisten</span><span class="sxs-lookup"><span data-stu-id="b8fc9-141">Requirements</span></span>

<span data-ttu-id="b8fc9-142">Vanuit de lijst met begebruikte zaken, kunt u beginnen met het maken van vereisten.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="b8fc9-143">Voor de vereisten behoren functies een programma dient te voldoen aan de use cases.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="b8fc9-144">Deze vereisten kunnen worden opgesplitst in categorieën zoals configuratie en onderhoud, ondersteuning voor integraties en functie-specifieke vereisten, zoals de ondersteuning van de jacht en de mogelijkheid om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="b8fc9-145">Test plan</span><span class="sxs-lookup"><span data-stu-id="b8fc9-145">Test plan</span></span>

<span data-ttu-id="b8fc9-146">Afhankelijk van de vereisten, is het mogelijk dat er verschillende testmethoden geschikt zijn.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="b8fc9-147">Als u bijvoorbeeld de effectiviteit van geautomatiseerde herbemiddeling evalueert, moet het testplan stappen opnemen om de gedrag (en) te genereren waarmee een geautomatiseerde herstelactie binnen Microsoft Threat Protection werd geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="b8fc9-148">Als u een bepaald gedrag of een bepaalde aanval moet detecteren, dan kan de test meer stappen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="b8fc9-149">U kunt het beste een plan op basis van de vereisten nauwkeurig testen.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="b8fc9-150">Criteria voor succes</span><span class="sxs-lookup"><span data-stu-id="b8fc9-150">Success criteria</span></span>

<span data-ttu-id="b8fc9-151">De criteria voor succes zijn uiteindelijk de balk die is ingesteld voor de waardering van wat u wilt testen.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="b8fc9-152">Of u nu Microsoft Threat Protection (of andere hulpmiddelen voor die materie) tegen andere hulpmiddelen of op een andere manier test, moet u een aantal meetbaarste criteria gebruiken om de waarde van het hulpmiddel te bepalen.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="b8fc9-153">Afhankelijk van de vereisten voor het bereik, de vereisten en het testen van het plan, wordt het resultaat van de test bepaald.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="b8fc9-154">Dit kan minder of niet meer zijn, en ook een gewogen score op basis van uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="b8fc9-155">Als u bijvoorbeeld een succesvolle aanduiding wilt hebben, moet een hulpmiddel mogelijk een Score van 80% hebben in bepaalde kritieke gebieden die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="b8fc9-156">Werd</span><span class="sxs-lookup"><span data-stu-id="b8fc9-156">Scorecard</span></span>

<span data-ttu-id="b8fc9-157">U kunt ook een scorecard maken om alle elementen van uw plan bijeen te brengen.</span><span class="sxs-lookup"><span data-stu-id="b8fc9-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="b8fc9-158">Hieronder ziet u een voorbeeld van een Scorecard:</span><span class="sxs-lookup"><span data-stu-id="b8fc9-158">See a sample scorecard below:</span></span>

|<span data-ttu-id="b8fc9-159">**Use-case**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-159">**Use case**</span></span>|<span data-ttu-id="b8fc9-160">**Vereisten**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-160">**Requirements**</span></span>|<span data-ttu-id="b8fc9-161">**Configuratievereisten**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-161">**Configuration requirements**</span></span>|<span data-ttu-id="b8fc9-162">**Test plan**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-162">**Test plan**</span></span>|<span data-ttu-id="b8fc9-163">**Verwacht resultaat**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-163">**Expected outcome**</span></span>|<span data-ttu-id="b8fc9-164">**Status testen**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-164">**Test status**</span></span>|<span data-ttu-id="b8fc9-165">**Score**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-165">**Score**</span></span>|<span data-ttu-id="b8fc9-166">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="b8fc9-166">**Notes**</span></span>|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="b8fc9-167">Incidentenbeheer</span><span class="sxs-lookup"><span data-stu-id="b8fc9-167">Incident management</span></span>|<span data-ttu-id="b8fc9-168">-Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8fc9-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="b8fc9-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="b8fc9-169">- Azure ATP</span></span> </br></br><span data-ttu-id="b8fc9-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b8fc9-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="b8fc9-171">-Beveiliging van Microsoft Cloud-app (optioneel)</span><span class="sxs-lookup"><span data-stu-id="b8fc9-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="b8fc9-172">Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="b8fc9-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="b8fc9-173">Een aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="b8fc9-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="b8fc9-174">Het incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b8fc9-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="b8fc9-175">Onderzoekers kunnen inzicht krijgen in de reikwijdte en impact van het incident en het incident beheren</span><span class="sxs-lookup"><span data-stu-id="b8fc9-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="b8fc9-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="b8fc9-176">AutoIR</span></span>|<span data-ttu-id="b8fc9-177">-Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8fc9-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="b8fc9-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="b8fc9-178">- Azure ATP</span></span> </br></br><span data-ttu-id="b8fc9-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b8fc9-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="b8fc9-180">Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="b8fc9-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="b8fc9-181">AutoIR inschakelen</span><span class="sxs-lookup"><span data-stu-id="b8fc9-181">Enable AutoIR</span></span>  |[<span data-ttu-id="b8fc9-182">Een aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="b8fc9-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="b8fc9-183">Automatisch onderzoek</span><span class="sxs-lookup"><span data-stu-id="b8fc9-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="b8fc9-184">Waarschuwingen en incidenten worden automatisch doorgevoerd door Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8fc9-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="b8fc9-185">Geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b8fc9-185">Advanced hunting</span></span>|<span data-ttu-id="b8fc9-186">-Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8fc9-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="b8fc9-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b8fc9-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="b8fc9-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b8fc9-188">- Office 365 ATP</span></span>   |<span data-ttu-id="b8fc9-189">Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="b8fc9-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="b8fc9-190">Scenario voor Geavanceerd jacht</span><span class="sxs-lookup"><span data-stu-id="b8fc9-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="b8fc9-191">Onderzoekers kunnen gegevens vinden via Geavanceerd jacht, draaien naar beïnvloede entiteiten en aangepaste detecties maken</span><span class="sxs-lookup"><span data-stu-id="b8fc9-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="b8fc9-192">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b8fc9-192">Next step</span></span>
|<span data-ttu-id="b8fc9-193">![Voorbereidende fase](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="b8fc9-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="b8fc9-194">Voorbereidende fase</span><span class="sxs-lookup"><span data-stu-id="b8fc9-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="b8fc9-195">Uw testomgeving voor Microsoft Threat Protection voorbereiden</span><span class="sxs-lookup"><span data-stu-id="b8fc9-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
