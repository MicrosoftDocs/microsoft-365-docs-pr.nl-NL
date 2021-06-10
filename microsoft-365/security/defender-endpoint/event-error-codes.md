---
title: Gebeurtenissen en fouten controleren met Behulp van Gebeurtenisviewer
description: Hier worden beschrijvingen en verdere stappen voor probleemoplossing (indien nodig) weergegeven voor alle gebeurtenissen die zijn gerapporteerd door de Microsoft Defender voor Eindpunt-service.
keywords: probleemoplosser, gebeurtenisviewer, logboekoverzicht, foutcode, mislukt, Microsoft Defender voor Endpoint-service, kan niet starten, niet starten, niet starten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933839"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="6e972-104">Gebeurtenissen en fouten controleren met Behulp van Gebeurtenisviewer</span><span class="sxs-lookup"><span data-stu-id="6e972-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6e972-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6e972-105">**Applies to:**</span></span>
- <span data-ttu-id="6e972-106">Gebeurtenisviewer</span><span class="sxs-lookup"><span data-stu-id="6e972-106">Event Viewer</span></span>
- [<span data-ttu-id="6e972-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6e972-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6e972-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e972-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6e972-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6e972-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e972-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6e972-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="6e972-111">U kunt gebeurtenis-ID's in de [Gebeurtenisviewer op](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) afzonderlijke apparaten bekijken.</span><span class="sxs-lookup"><span data-stu-id="6e972-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="6e972-112">Als apparaten bijvoorbeeld niet worden weergegeven in de lijst **Apparaten,** moet u mogelijk zoeken naar gebeurtenis-ID's op de apparaten.</span><span class="sxs-lookup"><span data-stu-id="6e972-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="6e972-113">Vervolgens kunt u deze tabel gebruiken om verdere stappen voor het oplossen van problemen te bepalen.</span><span class="sxs-lookup"><span data-stu-id="6e972-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="6e972-114">**Open Gebeurtenisviewer en zoek het gebeurtenislogboek van de Microsoft Defender for Endpoint-service:**</span><span class="sxs-lookup"><span data-stu-id="6e972-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="6e972-115">Klik **op Start** in het Windows menu, typ **Gebeurtenisviewer** en druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="6e972-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="6e972-116">Schuif in de logboeklijst onder **Logboekoverzicht** door totdat u **Microsoft-Windows-SENSE/Operationeel ziet.**</span><span class="sxs-lookup"><span data-stu-id="6e972-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="6e972-117">Dubbelklik op het item om het logboek te openen.</span><span class="sxs-lookup"><span data-stu-id="6e972-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="6e972-118">a.</span><span class="sxs-lookup"><span data-stu-id="6e972-118">a.</span></span>  <span data-ttu-id="6e972-119">U kunt het logboek ook openen door toepassingen en **serviceslogboeken** uit te breiden  >  **Windows**  >    >  **SENSE** en op **Operationeel te klikken.**</span><span class="sxs-lookup"><span data-stu-id="6e972-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6e972-120">SENSE is de interne naam die wordt gebruikt om te verwijzen naar de gedrags sensor die Microsoft Defender voor Eindpunt aandreed.</span><span class="sxs-lookup"><span data-stu-id="6e972-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="6e972-121">Gebeurtenissen die door de service zijn geregistreerd, worden weergegeven in het logboek.</span><span class="sxs-lookup"><span data-stu-id="6e972-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="6e972-122">Zie de volgende tabel voor een lijst met gebeurtenissen die zijn vastgelegd door de service.</span><span class="sxs-lookup"><span data-stu-id="6e972-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="6e972-123">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="6e972-123">Event ID</span></span></th>
<th><span data-ttu-id="6e972-124">Bericht</span><span class="sxs-lookup"><span data-stu-id="6e972-124">Message</span></span></th>
<th><span data-ttu-id="6e972-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6e972-125">Description</span></span></th>
<th><span data-ttu-id="6e972-126">Actie</span><span class="sxs-lookup"><span data-stu-id="6e972-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="6e972-127">1</span><span class="sxs-lookup"><span data-stu-id="6e972-127">1</span></span></td>
<td><span data-ttu-id="6e972-128">Microsoft Defender for Endpoint-service gestart <code>variable</code> (versie).</span><span class="sxs-lookup"><span data-stu-id="6e972-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="6e972-129">Dit gebeurt tijdens het opstarten van het systeem, tijdens het afsluiten en tijdens onboarding.</span><span class="sxs-lookup"><span data-stu-id="6e972-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="6e972-130">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-131">2</span><span class="sxs-lookup"><span data-stu-id="6e972-131">2</span></span></td>
<td><span data-ttu-id="6e972-132">Microsoft Defender for Endpoint service shutdown.</span><span class="sxs-lookup"><span data-stu-id="6e972-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="6e972-133">Dit gebeurt wanneer het apparaat is uitgeschakeld of buiten gebruik wordt gezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="6e972-134">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-135">3</span><span class="sxs-lookup"><span data-stu-id="6e972-135">3</span></span></td>
<td><span data-ttu-id="6e972-136">Microsoft Defender voor Endpoint-service kan niet worden begonnen.</span><span class="sxs-lookup"><span data-stu-id="6e972-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="6e972-137">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-138">De service is niet begonnen.</span><span class="sxs-lookup"><span data-stu-id="6e972-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="6e972-139">Controleer andere berichten om mogelijke oorzaak- en probleemoplossingsstappen te bepalen.</span><span class="sxs-lookup"><span data-stu-id="6e972-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-140">4</span><span class="sxs-lookup"><span data-stu-id="6e972-140">4</span></span></td>
<td><span data-ttu-id="6e972-141">Microsoft Defender for Endpoint-service heeft contact opgenomen met de server op <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-142">Variabele = URL van de defender voor eindpuntverwerkingsservers.</span><span class="sxs-lookup"><span data-stu-id="6e972-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="6e972-143">Deze URL komt overeen met die in de firewall- of netwerkactiviteit.</span><span class="sxs-lookup"><span data-stu-id="6e972-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="6e972-144">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-145">5</span><span class="sxs-lookup"><span data-stu-id="6e972-145">5</span></span></td>
<td><span data-ttu-id="6e972-146">Microsoft Defender for Endpoint-service kan geen verbinding maken met de server op <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-147">Variabele = URL van de defender voor eindpuntverwerkingsservers.</span><span class="sxs-lookup"><span data-stu-id="6e972-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="6e972-148">De service kan geen contact opnemen met de externe verwerkingsservers op die URL.</span><span class="sxs-lookup"><span data-stu-id="6e972-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="6e972-149">Controleer de verbinding met de URL.</span><span class="sxs-lookup"><span data-stu-id="6e972-149">Check the connection to the URL.</span></span> <span data-ttu-id="6e972-150">Zie <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Proxy en internetverbinding configureren.</a></span><span class="sxs-lookup"><span data-stu-id="6e972-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-151">6</span><span class="sxs-lookup"><span data-stu-id="6e972-151">6</span></span></td>
<td><span data-ttu-id="6e972-152">Microsoft Defender voor Endpoint-service is niet onboarded en er zijn geen onboarding-parameters gevonden.</span><span class="sxs-lookup"><span data-stu-id="6e972-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="6e972-153">Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</span><span class="sxs-lookup"><span data-stu-id="6e972-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="6e972-154">Onboarding moet worden uitgevoerd voordat u de service start.</span><span class="sxs-lookup"><span data-stu-id="6e972-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="6e972-155">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-156">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-157">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-158">7</span><span class="sxs-lookup"><span data-stu-id="6e972-158">7</span></span></td>
<td><span data-ttu-id="6e972-159">Microsoft Defender voor Endpoint-service kan de onboarding-parameters niet lezen.</span><span class="sxs-lookup"><span data-stu-id="6e972-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="6e972-160">Fout: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-161">Variabele = gedetailleerde foutbeschrijving.</span><span class="sxs-lookup"><span data-stu-id="6e972-161">Variable = detailed error description.</span></span> <span data-ttu-id="6e972-162">Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</span><span class="sxs-lookup"><span data-stu-id="6e972-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="6e972-163">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-164">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-165">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-166">8</span><span class="sxs-lookup"><span data-stu-id="6e972-166">8</span></span></td>
<td><span data-ttu-id="6e972-167">De configuratie van de Microsoft Defender for Endpoint-service is niet op te schonen.</span><span class="sxs-lookup"><span data-stu-id="6e972-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="6e972-168">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-169"><b>Tijdens onboarding:</b> De service heeft de configuratie tijdens de onboarding niet schoon kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="6e972-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="6e972-170">Het onboardingproces wordt voortgezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="6e972-171"><b>Tijdens offboarding:</b> De service heeft de configuratie tijdens het offboarden niet schoon kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="6e972-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="6e972-172">Het offboarding-proces is voltooid, maar de service blijft actief.</span><span class="sxs-lookup"><span data-stu-id="6e972-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="6e972-173"><b>Onboarding:</b> Geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="6e972-174"><b>Offboarding:</b> Start het systeem opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="6e972-175">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-176">9</span><span class="sxs-lookup"><span data-stu-id="6e972-176">9</span></span></td>
<td><span data-ttu-id="6e972-177">Het begintype van de Microsoft Defender voor Eindpunt-service is niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="6e972-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="6e972-178">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-179"><b>Tijdens onboarding:</b> Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</span><span class="sxs-lookup"><span data-stu-id="6e972-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="6e972-180"><b>Tijdens offboarding:</b> Kan het begintype van de service niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6e972-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="6e972-181">Het offboardingproces wordt voortgezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="6e972-182">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-183">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-184">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-185">10</span><span class="sxs-lookup"><span data-stu-id="6e972-185">10</span></span></td>
<td><span data-ttu-id="6e972-186">Microsoft Defender voor Endpoint-service kan de onboarding-informatie niet blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6e972-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="6e972-187">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-188">Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</span><span class="sxs-lookup"><span data-stu-id="6e972-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="6e972-189">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-190">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-191">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-192">11</span><span class="sxs-lookup"><span data-stu-id="6e972-192">11</span></span></td>
<td><span data-ttu-id="6e972-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span><span class="sxs-lookup"><span data-stu-id="6e972-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="6e972-194">Het apparaat is correct aan boord.</span><span class="sxs-lookup"><span data-stu-id="6e972-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="6e972-195">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="6e972-196">Het kan enkele uren duren voordat het apparaat in de portal wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6e972-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-197">12</span><span class="sxs-lookup"><span data-stu-id="6e972-197">12</span></span></td>
<td><span data-ttu-id="6e972-198">Microsoft Defender voor Eindpunt kan de standaardconfiguratie niet toepassen.</span><span class="sxs-lookup"><span data-stu-id="6e972-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="6e972-199">Service kon de standaardconfiguratie niet toepassen.</span><span class="sxs-lookup"><span data-stu-id="6e972-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="6e972-200">Deze fout moet na een korte periode worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="6e972-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-201">13</span><span class="sxs-lookup"><span data-stu-id="6e972-201">13</span></span></td>
<td><span data-ttu-id="6e972-202">Microsoft Defender voor endpoint-apparaat-id berekend: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-203">Normaal besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="6e972-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="6e972-204">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-205">15</span><span class="sxs-lookup"><span data-stu-id="6e972-205">15</span></span></td>
<td><span data-ttu-id="6e972-206">Microsoft Defender voor Eindpunt kan het opdrachtkanaal niet starten met URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-207">Variabele = URL van de defender voor eindpuntverwerkingsservers.</span><span class="sxs-lookup"><span data-stu-id="6e972-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="6e972-208">De service kan geen contact opnemen met de externe verwerkingsservers op die URL.</span><span class="sxs-lookup"><span data-stu-id="6e972-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="6e972-209">Controleer de verbinding met de URL.</span><span class="sxs-lookup"><span data-stu-id="6e972-209">Check the connection to the URL.</span></span> <span data-ttu-id="6e972-210">Zie <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Proxy en internetverbinding configureren.</a></span><span class="sxs-lookup"><span data-stu-id="6e972-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-211">17</span><span class="sxs-lookup"><span data-stu-id="6e972-211">17</span></span></td>
<td><span data-ttu-id="6e972-212">Microsoft Defender voor Endpoint-service kan de verbonden gebruikerservaringen en telemetrieservicelocatie niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6e972-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="6e972-213">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-214">Er is een fout opgetreden bij Windows telemetrieservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="6e972-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Controleer of de diagnostische gegevensservice is ingeschakeld.</a></span><span class="sxs-lookup"><span data-stu-id="6e972-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="6e972-216">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-217">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-218">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-219">18</span><span class="sxs-lookup"><span data-stu-id="6e972-219">18</span></span></td>
<td><span data-ttu-id="6e972-220">OOBE (Windows Welkom) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="6e972-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="6e972-221">De service wordt pas van start Windows updates zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="6e972-222">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-223">19</span><span class="sxs-lookup"><span data-stu-id="6e972-223">19</span></span></td>
<td><span data-ttu-id="6e972-224">OOBE (Windows Welkom) is nog niet voltooid.</span><span class="sxs-lookup"><span data-stu-id="6e972-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="6e972-225">De service wordt pas van start Windows updates zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="6e972-226">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="6e972-227">Als deze fout blijft bestaan nadat een systeem opnieuw is gestart, controleert u of Windows alle updates volledig zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-228">20</span><span class="sxs-lookup"><span data-stu-id="6e972-228">20</span></span></td>
<td><span data-ttu-id="6e972-229">Kan niet wachten totdat OOBE (Windows Welkom) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="6e972-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="6e972-230">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-231">Interne fout.</span><span class="sxs-lookup"><span data-stu-id="6e972-231">Internal error.</span></span></td>
<td><span data-ttu-id="6e972-232">Als deze fout blijft bestaan nadat een systeem opnieuw is gestart, controleert u of Windows alle updates volledig zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-233">25</span><span class="sxs-lookup"><span data-stu-id="6e972-233">25</span></span></td>
<td><span data-ttu-id="6e972-234">De statusstatus van het register is niet opnieuw ingesteld door de Microsoft Defender voor eindpuntservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="6e972-235">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-236">Het apparaat is niet correct aan boord.</span><span class="sxs-lookup"><span data-stu-id="6e972-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="6e972-237">De service rapporteert aan de portal, maar de service wordt mogelijk niet weergegeven als geregistreerd in SCCM of het register.</span><span class="sxs-lookup"><span data-stu-id="6e972-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="6e972-238">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-239">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-240">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-241">26</span><span class="sxs-lookup"><span data-stu-id="6e972-241">26</span></span></td>
<td><span data-ttu-id="6e972-242">Microsoft Defender voor Eindpunt-service kan de onboarding-status niet instellen in het register.</span><span class="sxs-lookup"><span data-stu-id="6e972-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="6e972-243">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-244">Het apparaat is niet correct aan boord.</span><span class="sxs-lookup"><span data-stu-id="6e972-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="6e972-245">De service rapporteert aan de portal, maar de service wordt mogelijk niet weergegeven als geregistreerd in SCCM of het register.</span><span class="sxs-lookup"><span data-stu-id="6e972-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="6e972-246">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-247">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-248">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-249">27</span><span class="sxs-lookup"><span data-stu-id="6e972-249">27</span></span></td>
<td><span data-ttu-id="6e972-250">Microsoft Defender for Endpoint-service kan de sense aware-modus niet inschakelen in Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="6e972-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="6e972-251">Onboarding is mislukt.</span><span class="sxs-lookup"><span data-stu-id="6e972-251">Onboarding process failed.</span></span> <span data-ttu-id="6e972-252">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-253">Normaal gesproken Microsoft Defender Antivirus een speciale passieve status als een ander antimalwareproduct in realtime correct wordt uitgevoerd op het apparaat en het apparaat rapporteert aan Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6e972-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="6e972-254">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-255">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-256">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="6e972-257">Zorg ervoor dat antimalwarebeveiliging in realtime correct wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-258">28</span><span class="sxs-lookup"><span data-stu-id="6e972-258">28</span></span></td>
<td><span data-ttu-id="6e972-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span><span class="sxs-lookup"><span data-stu-id="6e972-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="6e972-260">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-261">Er is een fout opgetreden bij Windows telemetrieservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="6e972-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Controleer of de diagnostische gegevensservice is ingeschakeld.</a></span><span class="sxs-lookup"><span data-stu-id="6e972-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="6e972-263">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-264">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-265">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-266">29</span><span class="sxs-lookup"><span data-stu-id="6e972-266">29</span></span></td>
<td><span data-ttu-id="6e972-267">Kan de offboarding-parameters niet lezen.</span><span class="sxs-lookup"><span data-stu-id="6e972-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="6e972-268">Fouttype: %1, Foutcode: %2, Beschrijving: %3</span><span class="sxs-lookup"><span data-stu-id="6e972-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="6e972-269">Deze gebeurtenis treedt op wanneer het systeem&#39;de offboarding-parameters kan lezen.</span><span class="sxs-lookup"><span data-stu-id="6e972-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="6e972-270">Controleer of het apparaat internettoegang heeft en voer vervolgens het hele offboarding-proces opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="6e972-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="6e972-271">Controleer of het offboarding-pakket niet is verlopen.</span><span class="sxs-lookup"><span data-stu-id="6e972-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-272">30</span><span class="sxs-lookup"><span data-stu-id="6e972-272">30</span></span></td>
<td><span data-ttu-id="6e972-273">Microsoft Defender for Endpoint-service kan de sense aware-modus niet uitschakelen in Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="6e972-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="6e972-274">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-275">Normaal gesproken Microsoft Defender Antivirus een speciale passieve status als een ander antimalwareproduct in realtime correct wordt uitgevoerd op het apparaat en het apparaat rapporteert aan Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6e972-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="6e972-276">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-277">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-278">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a></span><span class="sxs-lookup"><span data-stu-id="6e972-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="6e972-279">Zorg ervoor dat antimalwarebeveiliging in realtime correct wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-280">31</span><span class="sxs-lookup"><span data-stu-id="6e972-280">31</span></span></td>
<td><span data-ttu-id="6e972-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span><span class="sxs-lookup"><span data-stu-id="6e972-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="6e972-282">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-283">Er is een fout opgetreden bij Windows telemetrieservice tijdens onboarding.</span><span class="sxs-lookup"><span data-stu-id="6e972-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="6e972-284">Het offboardingproces wordt voortgezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="6e972-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Controleer op fouten met de Windows telemetrieservice.</a></span><span class="sxs-lookup"><span data-stu-id="6e972-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-286">32</span><span class="sxs-lookup"><span data-stu-id="6e972-286">32</span></span></td>
<td><span data-ttu-id="6e972-287">Microsoft Defender for Endpoint-service heeft niet gevraagd om zichzelf te stoppen na het offboarden.</span><span class="sxs-lookup"><span data-stu-id="6e972-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="6e972-288">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="6e972-289">Er is een fout opgetreden tijdens het offboarden.</span><span class="sxs-lookup"><span data-stu-id="6e972-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="6e972-290">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-291">33</span><span class="sxs-lookup"><span data-stu-id="6e972-291">33</span></span></td>
<td><span data-ttu-id="6e972-292">Microsoft Defender for Endpoint-service kan SENSE GUID niet aanhouden.</span><span class="sxs-lookup"><span data-stu-id="6e972-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="6e972-293">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-294">Er wordt een unieke id gebruikt voor elk apparaat dat rapporteert aan de portal.</span><span class="sxs-lookup"><span data-stu-id="6e972-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="6e972-295">Als de id niet blijft bestaan, wordt hetzelfde apparaat mogelijk tweemaal weergegeven in de portal.</span><span class="sxs-lookup"><span data-stu-id="6e972-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="6e972-296">Controleer de registermachtigingen op het apparaat om ervoor te zorgen dat de service het register kan bijwerken.</span><span class="sxs-lookup"><span data-stu-id="6e972-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-297">34</span><span class="sxs-lookup"><span data-stu-id="6e972-297">34</span></span></td>
<td><span data-ttu-id="6e972-298">Microsoft Defender voor Endpoint-service kan zichzelf niet toevoegen als afhankelijkheid van de verbonden gebruikerservaringen en telemetrieservice, waardoor het onboardingproces mislukt.</span><span class="sxs-lookup"><span data-stu-id="6e972-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="6e972-299">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-300">Er is een fout opgetreden bij Windows telemetrieservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="6e972-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Controleer of de diagnostische gegevensservice is ingeschakeld.</a></span><span class="sxs-lookup"><span data-stu-id="6e972-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="6e972-302">Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="6e972-303">Probeer de configuratiepakketten opnieuw te configureren.</span><span class="sxs-lookup"><span data-stu-id="6e972-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="6e972-304">Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 apparaten</a>.</span><span class="sxs-lookup"><span data-stu-id="6e972-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-305">35</span><span class="sxs-lookup"><span data-stu-id="6e972-305">35</span></span></td>
<td><span data-ttu-id="6e972-306">Microsoft Defender for Endpoint-service kan zichzelf niet verwijderen als afhankelijkheid van de verbonden gebruikerservaringen en telemetrieservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="6e972-307">Foutcode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-308">Er is een fout opgetreden bij Windows telemetrieservice tijdens het offboarden.</span><span class="sxs-lookup"><span data-stu-id="6e972-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="6e972-309">Het offboardingproces wordt voortgezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="6e972-310">Controleer op fouten met de Windows diagnostische gegevensservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-311">36</span><span class="sxs-lookup"><span data-stu-id="6e972-311">36</span></span></td>
<td><span data-ttu-id="6e972-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span><span class="sxs-lookup"><span data-stu-id="6e972-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="6e972-313">Voltooiingscode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="6e972-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="6e972-314">Het registreren van Defender voor Eindpunt met de verbonden gebruikerservaringen en telemetrieservice is voltooid.</span><span class="sxs-lookup"><span data-stu-id="6e972-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="6e972-315">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-316">37</span><span class="sxs-lookup"><span data-stu-id="6e972-316">37</span></span></td>
<td><span data-ttu-id="6e972-317">Microsoft Defender voor eindpunt Een module staat op het punt het quotum te overschrijden.</span><span class="sxs-lookup"><span data-stu-id="6e972-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="6e972-318">Module: %1, Quotum: {%2} {%3}, Percentage van quotumgebruik: %4.</span><span class="sxs-lookup"><span data-stu-id="6e972-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="6e972-319">Het apparaat heeft het toegewezen quotum van het huidige venster van 24 uur bijna gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6e972-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="6e972-320">Het wordt nu beperkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="6e972-321">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-322">38</span><span class="sxs-lookup"><span data-stu-id="6e972-322">38</span></span></td>
<td><span data-ttu-id="6e972-323">Netwerkverbinding wordt als laag aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-323">Network connection is identified as low.</span></span> <span data-ttu-id="6e972-324">Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="6e972-325">Verbinding met dataverbinding: %2, internet beschikbaar: %3, gratis netwerk beschikbaar: %4.</span><span class="sxs-lookup"><span data-stu-id="6e972-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="6e972-326">Het apparaat gebruikt een netwerk met een datameter en neemt minder vaak contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="6e972-327">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-328">39</span><span class="sxs-lookup"><span data-stu-id="6e972-328">39</span></span></td>
<td><span data-ttu-id="6e972-329">Netwerkverbinding wordt als normaal aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-329">Network connection is identified as normal.</span></span> <span data-ttu-id="6e972-330">Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="6e972-331">Verbinding met dataverbinding: %2, internet beschikbaar: %3, gratis netwerk beschikbaar: %4.</span><span class="sxs-lookup"><span data-stu-id="6e972-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="6e972-332">Het apparaat gebruikt geen verbinding met een datameter/betaalde verbinding en neemt zoals gewoonlijk contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="6e972-333">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-334">40</span><span class="sxs-lookup"><span data-stu-id="6e972-334">40</span></span></td>
<td><span data-ttu-id="6e972-335">De batterijtoestand wordt als laag aangeduid.</span><span class="sxs-lookup"><span data-stu-id="6e972-335">Battery state is identified as low.</span></span> <span data-ttu-id="6e972-336">Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="6e972-337">Batterijtoestand: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="6e972-338">Het apparaat heeft een laag batterijniveau en neemt minder vaak contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="6e972-339">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-340">41</span><span class="sxs-lookup"><span data-stu-id="6e972-340">41</span></span></td>
<td><span data-ttu-id="6e972-341">De batterijtoestand wordt als normaal aangeduid.</span><span class="sxs-lookup"><span data-stu-id="6e972-341">Battery state is identified as normal.</span></span> <span data-ttu-id="6e972-342">Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="6e972-343">Batterijtoestand: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="6e972-344">Het apparaat heeft geen laag batterijniveau en neemt zoals gewoonlijk contact op met de server.</span><span class="sxs-lookup"><span data-stu-id="6e972-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="6e972-345">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-346">42</span><span class="sxs-lookup"><span data-stu-id="6e972-346">42</span></span></td>
<td><span data-ttu-id="6e972-347">Microsoft Defender voor eindpuntonderdeel kan geen actie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6e972-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="6e972-348">Component: %1, Actie: %2, Uitzonderingstype: %3, Uitzonderingsbericht: %4</span><span class="sxs-lookup"><span data-stu-id="6e972-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="6e972-349">Interne fout.</span><span class="sxs-lookup"><span data-stu-id="6e972-349">Internal error.</span></span> <span data-ttu-id="6e972-350">De service kan niet worden begonnen.</span><span class="sxs-lookup"><span data-stu-id="6e972-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="6e972-351">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-352">43</span><span class="sxs-lookup"><span data-stu-id="6e972-352">43</span></span></td>
<td><span data-ttu-id="6e972-353">Microsoft Defender voor eindpuntonderdeel kan geen actie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6e972-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="6e972-354">Component: %1, Actie: %2, Uitzonderingstype: %3, Uitzonderingsfout: %4, Uitzonderingsbericht: %5</span><span class="sxs-lookup"><span data-stu-id="6e972-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="6e972-355">Interne fout.</span><span class="sxs-lookup"><span data-stu-id="6e972-355">Internal error.</span></span> <span data-ttu-id="6e972-356">De service kan niet worden begonnen.</span><span class="sxs-lookup"><span data-stu-id="6e972-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="6e972-357">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-358">44</span><span class="sxs-lookup"><span data-stu-id="6e972-358">44</span></span></td>
<td><span data-ttu-id="6e972-359">Offboarding of Defender for Endpoint service completed.</span><span class="sxs-lookup"><span data-stu-id="6e972-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="6e972-360">De service is buiten het bord gezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="6e972-361">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-362">45</span><span class="sxs-lookup"><span data-stu-id="6e972-362">45</span></span></td>
<td><span data-ttu-id="6e972-363">Kan zich niet registreren en de gebeurtenis traceersessie starten [%1].</span><span class="sxs-lookup"><span data-stu-id="6e972-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="6e972-364">Foutcode: %2</span><span class="sxs-lookup"><span data-stu-id="6e972-364">Error code: %2</span></span></td>
<td><span data-ttu-id="6e972-365">Er is een fout opgetreden bij het opstarten van de service tijdens het maken van ETW-sessie.</span><span class="sxs-lookup"><span data-stu-id="6e972-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="6e972-366">Hierdoor is het starten van een service mislukt.</span><span class="sxs-lookup"><span data-stu-id="6e972-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="6e972-367">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-368">46</span><span class="sxs-lookup"><span data-stu-id="6e972-368">46</span></span></td>
<td><span data-ttu-id="6e972-369">Kan de gebeurtenis traceersessie niet registreren en starten [%1] vanwege een gebrek aan resources.</span><span class="sxs-lookup"><span data-stu-id="6e972-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="6e972-370">Foutcode: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-370">Error code: %2.</span></span> <span data-ttu-id="6e972-371">Dit komt waarschijnlijk omdat er te veel actieve gebeurtenis tracesessies zijn.</span><span class="sxs-lookup"><span data-stu-id="6e972-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="6e972-372">De service wordt binnen 1 minuut opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="6e972-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="6e972-373">Er is een fout opgetreden bij het opstarten van de service tijdens het maken van ETW-sessie vanwege een gebrek aan resources.</span><span class="sxs-lookup"><span data-stu-id="6e972-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="6e972-374">De service is gestart en wordt uitgevoerd, maar meldt geen sensorgebeurtenis totdat de ETW-sessie is gestart.</span><span class="sxs-lookup"><span data-stu-id="6e972-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="6e972-375">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="6e972-376">De service probeert de sessie elke minuut te starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-377">47</span><span class="sxs-lookup"><span data-stu-id="6e972-377">47</span></span></td>
<td><span data-ttu-id="6e972-378">De gebeurtenis trace-sessie is geregistreerd en gestart- hersteld na eerdere mislukte pogingen.</span><span class="sxs-lookup"><span data-stu-id="6e972-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="6e972-379">Deze gebeurtenis volgt de vorige gebeurtenis na het starten van de ETW-sessie.</span><span class="sxs-lookup"><span data-stu-id="6e972-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="6e972-380">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6e972-381">48</span><span class="sxs-lookup"><span data-stu-id="6e972-381">48</span></span></td>
<td><span data-ttu-id="6e972-382">Kan geen provider [%1] toevoegen aan gebeurtenis traceersessie [%2].</span><span class="sxs-lookup"><span data-stu-id="6e972-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="6e972-383">Foutcode: %3.</span><span class="sxs-lookup"><span data-stu-id="6e972-383">Error code: %3.</span></span> <span data-ttu-id="6e972-384">Dit betekent dat gebeurtenissen van deze provider niet worden gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="6e972-385">Het is niet gelukt om een provider toe te voegen aan ETW-sessie.</span><span class="sxs-lookup"><span data-stu-id="6e972-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="6e972-386">Hierdoor worden de providergebeurtenissen niet gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="6e972-387">Controleer de foutcode.</span><span class="sxs-lookup"><span data-stu-id="6e972-387">Check the error code.</span></span> <span data-ttu-id="6e972-388">Als de fout zich blijft voordoen, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="6e972-389">49</span><span class="sxs-lookup"><span data-stu-id="6e972-389">49</span></span></td>
   <td><span data-ttu-id="6e972-390">Ongeldige cloudconfiguratieopdracht ontvangen en genegeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="6e972-391">Versie: %1, status: %2, foutcode: %3, bericht: %4</span><span class="sxs-lookup"><span data-stu-id="6e972-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="6e972-392">Een ongeldig configuratiebestand ontvangen van de cloudservice die is genegeerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="6e972-393">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-394">50</span><span class="sxs-lookup"><span data-stu-id="6e972-394">50</span></span></td>
   <td><span data-ttu-id="6e972-395">Nieuwe cloudconfiguratie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="6e972-396">Versie: %1.</span><span class="sxs-lookup"><span data-stu-id="6e972-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="6e972-397">Er is een nieuwe configuratie van de cloudservice toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="6e972-398">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-399">51</span><span class="sxs-lookup"><span data-stu-id="6e972-399">51</span></span></td>
   <td><span data-ttu-id="6e972-400">Nieuwe cloudconfiguratie is niet van toepassing, versie: %1.</span><span class="sxs-lookup"><span data-stu-id="6e972-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="6e972-401">De laatst bekende goede configuratie, versie %2, is toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="6e972-402">Een slecht configuratiebestand ontvangen van de cloudservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="6e972-403">Laatst bekende goede configuratie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="6e972-404">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-405">52</span><span class="sxs-lookup"><span data-stu-id="6e972-405">52</span></span></td>
   <td><span data-ttu-id="6e972-406">Nieuwe cloudconfiguratie is niet van toepassing, versie: %1.</span><span class="sxs-lookup"><span data-stu-id="6e972-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="6e972-407">Ook is de laatst bekende goede configuratie, versie %2, niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="6e972-408">De standaardconfiguratie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="6e972-409">Een slecht configuratiebestand ontvangen van de cloudservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="6e972-410">De laatst bekende goede configuratie is niet toegepast en de standaardconfiguratie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="6e972-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="6e972-411">De service probeert binnen 5 minuten een nieuw configuratiebestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="6e972-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="6e972-412">Als u de gebeurtenis niet ziet #50 neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-413">53</span><span class="sxs-lookup"><span data-stu-id="6e972-413">53</span></span></td>
   <td><span data-ttu-id="6e972-414">Cloudconfiguratie geladen vanuit permanente opslag, versie: %1.</span><span class="sxs-lookup"><span data-stu-id="6e972-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="6e972-415">De configuratie is geladen vanuit permanente opslag bij het opstarten van de service.</span><span class="sxs-lookup"><span data-stu-id="6e972-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="6e972-416">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-417">55</span><span class="sxs-lookup"><span data-stu-id="6e972-417">55</span></span></td>
   <td><span data-ttu-id="6e972-418">Kan de autologger Secure ETW niet maken.</span><span class="sxs-lookup"><span data-stu-id="6e972-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="6e972-419">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-420">Het is niet gelukt om de beveiligde ETW-logger te maken.</span><span class="sxs-lookup"><span data-stu-id="6e972-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="6e972-421">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-421">Reboot the device.</span></span> <span data-ttu-id="6e972-422">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-423">56</span><span class="sxs-lookup"><span data-stu-id="6e972-423">56</span></span></td>
   <td><span data-ttu-id="6e972-424">De autologger Secure ETW kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6e972-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="6e972-425">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-426">De beveiligde ETW-sessie bij offboarding is niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6e972-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="6e972-427">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-428">57</span><span class="sxs-lookup"><span data-stu-id="6e972-428">57</span></span></td>
   <td><span data-ttu-id="6e972-429">Een momentopname van de computer vastleggen om problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6e972-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="6e972-430">Er wordt een onderzoekspakket verzameld, ook wel bekend als het pakket met de technische recherche.</span><span class="sxs-lookup"><span data-stu-id="6e972-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="6e972-431">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-432">59</span><span class="sxs-lookup"><span data-stu-id="6e972-432">59</span></span></td>
   <td><span data-ttu-id="6e972-433">Opdracht Starten: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="6e972-434">Uitvoering van de antwoordopdracht starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="6e972-435">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-436">60</span><span class="sxs-lookup"><span data-stu-id="6e972-436">60</span></span></td>
   <td><span data-ttu-id="6e972-437">Opdracht %1 kan niet worden uitgevoerd, fout: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="6e972-438">De opdracht Antwoord kan niet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="6e972-439">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-440">61</span><span class="sxs-lookup"><span data-stu-id="6e972-440">61</span></span></td>
   <td><span data-ttu-id="6e972-441">Opdrachtparameters voor gegevensverzameling zijn ongeldig: SasUri: %1, compressieNiveau: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="6e972-442">Kan de opdrachtargumenten voor gegevensverzameling niet lezen of parseren (ongeldige argumenten).</span><span class="sxs-lookup"><span data-stu-id="6e972-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="6e972-443">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-444">62</span><span class="sxs-lookup"><span data-stu-id="6e972-444">62</span></span></td>
   <td><span data-ttu-id="6e972-445">Kan verbonden gebruikerservaringen en telemetrieservice niet starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="6e972-446">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-447">Verbonden gebruikerservaringen en telemetrieservice (diagtrack) kunnen niet worden begonnen.</span><span class="sxs-lookup"><span data-stu-id="6e972-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="6e972-448">Telemetrie van niet-Microsoft Defender voor Eindpunt wordt niet verzonden vanaf deze computer.</span><span class="sxs-lookup"><span data-stu-id="6e972-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="6e972-449">Zoek naar meer tips voor het oplossen van problemen in het gebeurtenislogboek: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="6e972-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-450">63</span><span class="sxs-lookup"><span data-stu-id="6e972-450">63</span></span></td>
   <td><span data-ttu-id="6e972-451">Het begintype van een externe service bijwerken.</span><span class="sxs-lookup"><span data-stu-id="6e972-451">Updating the start type of external service.</span></span> <span data-ttu-id="6e972-452">Naam: %1, werkelijke begintype: %2, verwacht begintype: %3, exitcode: %4</span><span class="sxs-lookup"><span data-stu-id="6e972-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="6e972-453">Bijgewerkt begintype van de externe service.</span><span class="sxs-lookup"><span data-stu-id="6e972-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="6e972-454">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-455">64</span><span class="sxs-lookup"><span data-stu-id="6e972-455">64</span></span></td>
   <td><span data-ttu-id="6e972-456">Externe service starten gestopt.</span><span class="sxs-lookup"><span data-stu-id="6e972-456">Starting stopped external service.</span></span> <span data-ttu-id="6e972-457">Naam: %1, exitcode: %2</span><span class="sxs-lookup"><span data-stu-id="6e972-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="6e972-458">Een externe service starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="6e972-459">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-460">65</span><span class="sxs-lookup"><span data-stu-id="6e972-460">65</span></span></td>
   <td><span data-ttu-id="6e972-461">Microsoft Security Events Component Minifilter driver kan niet worden geladen.</span><span class="sxs-lookup"><span data-stu-id="6e972-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="6e972-462">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-463">Kan het minifilter MsSecFlt.sys bestandssysteem niet laden.</span><span class="sxs-lookup"><span data-stu-id="6e972-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="6e972-464">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-464">Reboot the device.</span></span> <span data-ttu-id="6e972-465">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-466">66</span><span class="sxs-lookup"><span data-stu-id="6e972-466">66</span></span></td>
   <td><span data-ttu-id="6e972-467">Beleidsupdate: Latentiemodus - %1</span><span class="sxs-lookup"><span data-stu-id="6e972-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="6e972-468">Het C-&C-verbindingsfrequentiebeleid is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="6e972-469">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-470">68</span><span class="sxs-lookup"><span data-stu-id="6e972-470">68</span></span></td>
   <td><span data-ttu-id="6e972-471">Het begintype van de service is onverwacht.</span><span class="sxs-lookup"><span data-stu-id="6e972-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="6e972-472">Servicenaam: %1, werkelijke begintype: %2, verwacht begintype: %3</span><span class="sxs-lookup"><span data-stu-id="6e972-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="6e972-473">Onverwachte externe servicestarttype.</span><span class="sxs-lookup"><span data-stu-id="6e972-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="6e972-474">Los het starttype van de externe service op.</span><span class="sxs-lookup"><span data-stu-id="6e972-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-475">69</span><span class="sxs-lookup"><span data-stu-id="6e972-475">69</span></span></td>
   <td><span data-ttu-id="6e972-476">De service wordt gestopt.</span><span class="sxs-lookup"><span data-stu-id="6e972-476">The service is stopped.</span></span> <span data-ttu-id="6e972-477">Servicenaam: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="6e972-478">De externe service wordt gestopt.</span><span class="sxs-lookup"><span data-stu-id="6e972-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="6e972-479">Start de externe service.</span><span class="sxs-lookup"><span data-stu-id="6e972-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-480">70</span><span class="sxs-lookup"><span data-stu-id="6e972-480">70</span></span></td>
   <td><span data-ttu-id="6e972-481">Beleidsupdate: Voorbeeldverzameling toestaan - %1</span><span class="sxs-lookup"><span data-stu-id="6e972-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="6e972-482">Het voorbeeldverzamelingsbeleid is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="6e972-483">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-484">71</span><span class="sxs-lookup"><span data-stu-id="6e972-484">71</span></span></td>
   <td><span data-ttu-id="6e972-485">Geslaagd om opdracht uit te voeren: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="6e972-486">De opdracht is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="6e972-487">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-488">72</span><span class="sxs-lookup"><span data-stu-id="6e972-488">72</span></span></td>
   <td><span data-ttu-id="6e972-489">Geprobeerd om het eerste volledige machineprofielrapport te verzenden.</span><span class="sxs-lookup"><span data-stu-id="6e972-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="6e972-490">Resultaatcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="6e972-491">Alleen informatief.</span><span class="sxs-lookup"><span data-stu-id="6e972-491">Informational only.</span></span></td>
   <td><span data-ttu-id="6e972-492">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-493">73</span><span class="sxs-lookup"><span data-stu-id="6e972-493">73</span></span></td>
   <td><span data-ttu-id="6e972-494">Sense starting for platform: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="6e972-495">Alleen informatief.</span><span class="sxs-lookup"><span data-stu-id="6e972-495">Informational only.</span></span></td>
   <td><span data-ttu-id="6e972-496">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-497">74</span><span class="sxs-lookup"><span data-stu-id="6e972-497">74</span></span></td>
   <td><span data-ttu-id="6e972-498">Apparaatlabel in register overschrijdt de lengtelimiet.</span><span class="sxs-lookup"><span data-stu-id="6e972-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="6e972-499">Labelnaam: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-499">Tag name: %2.</span></span> <span data-ttu-id="6e972-500">Lengtelimiet: %1.</span><span class="sxs-lookup"><span data-stu-id="6e972-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="6e972-501">De apparaattag overschrijdt de lengtelimiet.</span><span class="sxs-lookup"><span data-stu-id="6e972-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="6e972-502">Gebruik een kortere apparaattag.</span><span class="sxs-lookup"><span data-stu-id="6e972-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-503">81</span><span class="sxs-lookup"><span data-stu-id="6e972-503">81</span></span></td>
   <td><span data-ttu-id="6e972-504">Kan microsoft Defender voor endpoint ETW-autologger niet maken.</span><span class="sxs-lookup"><span data-stu-id="6e972-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="6e972-505">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-506">Kan de ETW-sessie niet maken.</span><span class="sxs-lookup"><span data-stu-id="6e972-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="6e972-507">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-507">Reboot the device.</span></span> <span data-ttu-id="6e972-508">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-509">82</span><span class="sxs-lookup"><span data-stu-id="6e972-509">82</span></span></td>
   <td><span data-ttu-id="6e972-510">Microsoft Defender voor endpoint ETW-autologger kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6e972-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="6e972-511">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-512">De ETW-sessie is niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6e972-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="6e972-513">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-514">84</span><span class="sxs-lookup"><span data-stu-id="6e972-514">84</span></span></td>
   <td><span data-ttu-id="6e972-515">De Windows Defender Antivirus modus instellen.</span><span class="sxs-lookup"><span data-stu-id="6e972-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="6e972-516">Passieve modus forceer: %1, resultaatcode: %2.</span><span class="sxs-lookup"><span data-stu-id="6e972-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="6e972-517">De modus Defender Running Instellen (actief of passief).</span><span class="sxs-lookup"><span data-stu-id="6e972-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="6e972-518">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-519">85</span><span class="sxs-lookup"><span data-stu-id="6e972-519">85</span></span></td>
   <td><span data-ttu-id="6e972-520">Microsoft Defender voor Eindpunt kan niet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="6e972-521">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-522">In de hoofdrollen is SenseIR uitvoerbaar mislukt.</span><span class="sxs-lookup"><span data-stu-id="6e972-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="6e972-523">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-523">Reboot the device.</span></span> <span data-ttu-id="6e972-524">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-525">86</span><span class="sxs-lookup"><span data-stu-id="6e972-525">86</span></span></td>
   <td><span data-ttu-id="6e972-526">Als u opnieuw begint, is de externe service die moet worden opgehouden, gestopt.</span><span class="sxs-lookup"><span data-stu-id="6e972-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="6e972-527">Naam: %1, exitcode: %2</span><span class="sxs-lookup"><span data-stu-id="6e972-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="6e972-528">De externe service opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="6e972-529">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-530">87</span><span class="sxs-lookup"><span data-stu-id="6e972-530">87</span></span></td>
   <td><span data-ttu-id="6e972-531">U kunt de externe service niet starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-531">Cannot start the external service.</span></span> <span data-ttu-id="6e972-532">Naam: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-532">Name: %1</span></span></td>
   <td><span data-ttu-id="6e972-533">Kan de externe service niet starten.</span><span class="sxs-lookup"><span data-stu-id="6e972-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="6e972-534">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-535">88</span><span class="sxs-lookup"><span data-stu-id="6e972-535">88</span></span></td>
   <td><span data-ttu-id="6e972-536">Het begintype van de externe service opnieuw bijwerken.</span><span class="sxs-lookup"><span data-stu-id="6e972-536">Updating the start type of external service again.</span></span> <span data-ttu-id="6e972-537">Naam: %1, werkelijke begintype: %2, verwacht begintype: %3, exitcode: %4</span><span class="sxs-lookup"><span data-stu-id="6e972-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="6e972-538">Het begintype van de externe service is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="6e972-539">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-540">89</span><span class="sxs-lookup"><span data-stu-id="6e972-540">89</span></span></td>
   <td><span data-ttu-id="6e972-541">Kan het begintype van de externe service niet bijwerken.</span><span class="sxs-lookup"><span data-stu-id="6e972-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="6e972-542">Naam: %1, werkelijke begintype: %2, verwacht begintype: %3</span><span class="sxs-lookup"><span data-stu-id="6e972-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="6e972-543">Het starttype van de externe service kan niet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6e972-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="6e972-544">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-545">90</span><span class="sxs-lookup"><span data-stu-id="6e972-545">90</span></span></td>
   <td><span data-ttu-id="6e972-546">Het is niet gelukt om System Guard Runtime Monitor te configureren om verbinding te maken met de cloudservice in georegio %1.</span><span class="sxs-lookup"><span data-stu-id="6e972-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="6e972-547">Foutcode: %2</span><span class="sxs-lookup"><span data-stu-id="6e972-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="6e972-548">System Guard Runtime Monitor verzendt geen bevestigingsgegevens naar de cloudservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="6e972-549">Controleer de machtigingen op het registerpad: 'HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm'.</span><span class="sxs-lookup"><span data-stu-id="6e972-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="6e972-550">Als er geen problemen zijn gevonden, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-551">91</span><span class="sxs-lookup"><span data-stu-id="6e972-551">91</span></span></td>
   <td><span data-ttu-id="6e972-552">Kan Runtime Runtime Monitor georegiogegevens niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="6e972-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="6e972-553">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-554">System Guard Runtime Monitor verzendt geen bevestigingsgegevens naar de cloudservice.</span><span class="sxs-lookup"><span data-stu-id="6e972-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="6e972-555">Controleer de machtigingen op het registerpad: 'HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm'.</span><span class="sxs-lookup"><span data-stu-id="6e972-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="6e972-556">Als er geen problemen zijn gevonden, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-557">92</span><span class="sxs-lookup"><span data-stu-id="6e972-557">92</span></span></td>
   <td><span data-ttu-id="6e972-558">Stoppen met het verzenden van cybergegevensquotum voor sensor omdat het gegevensquotum wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="6e972-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="6e972-559">Wordt hervat wanneer de quotumperiode voorbij is.</span><span class="sxs-lookup"><span data-stu-id="6e972-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="6e972-560">Statusmasker: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="6e972-561">De beperkingslimiet overschrijden.</span><span class="sxs-lookup"><span data-stu-id="6e972-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="6e972-562">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-563">93</span><span class="sxs-lookup"><span data-stu-id="6e972-563">93</span></span></td>
   <td><span data-ttu-id="6e972-564">Het verzenden van cybergegevens van sensor opnieuw op te geven.</span><span class="sxs-lookup"><span data-stu-id="6e972-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="6e972-565">Statusmasker: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="6e972-566">Hervat de inzending van cybergegevens.</span><span class="sxs-lookup"><span data-stu-id="6e972-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="6e972-567">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-568">94</span><span class="sxs-lookup"><span data-stu-id="6e972-568">94</span></span></td>
   <td><span data-ttu-id="6e972-569">Microsoft Defender for Endpoint executable is gestart</span><span class="sxs-lookup"><span data-stu-id="6e972-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="6e972-570">De Uitvoerbare SenseCE is gestart.</span><span class="sxs-lookup"><span data-stu-id="6e972-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="6e972-571">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-572">95</span><span class="sxs-lookup"><span data-stu-id="6e972-572">95</span></span></td>
   <td><span data-ttu-id="6e972-573">Microsoft Defender voor Endpoint executable is beëindigd</span><span class="sxs-lookup"><span data-stu-id="6e972-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="6e972-574">De uitvoerbare SenseCE is beëindigd.</span><span class="sxs-lookup"><span data-stu-id="6e972-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="6e972-575">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-576">96</span><span class="sxs-lookup"><span data-stu-id="6e972-576">96</span></span></td>
   <td><span data-ttu-id="6e972-577">Microsoft Defender voor Eindpunt Init heeft gebeld.</span><span class="sxs-lookup"><span data-stu-id="6e972-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="6e972-578">Resultaatcode: %2</span><span class="sxs-lookup"><span data-stu-id="6e972-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="6e972-579">De Uitvoerbare SenseCE heeft MCE-initialisatie genoemd.</span><span class="sxs-lookup"><span data-stu-id="6e972-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="6e972-580">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-581">97</span><span class="sxs-lookup"><span data-stu-id="6e972-581">97</span></span></td>
   <td><span data-ttu-id="6e972-582">Er zijn verbindingsproblemen met de cloud voor het DLP-scenario</span><span class="sxs-lookup"><span data-stu-id="6e972-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="6e972-583">Er zijn netwerkconnectiviteitsproblemen die van invloed zijn op de DLP-classificatiestroom.</span><span class="sxs-lookup"><span data-stu-id="6e972-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="6e972-584">Controleer de netwerkconnectiviteit.</span><span class="sxs-lookup"><span data-stu-id="6e972-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-585">98</span><span class="sxs-lookup"><span data-stu-id="6e972-585">98</span></span></td>
   <td><span data-ttu-id="6e972-586">De verbinding met de cloud voor het DLP-scenario is hersteld</span><span class="sxs-lookup"><span data-stu-id="6e972-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="6e972-587">De verbinding met het netwerk is hersteld en de DLP-classificatiestroom kan worden voortgezet.</span><span class="sxs-lookup"><span data-stu-id="6e972-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="6e972-588">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-589">99</span><span class="sxs-lookup"><span data-stu-id="6e972-589">99</span></span></td>
   <td><span data-ttu-id="6e972-590">De volgende fout is opgetreden tijdens het communiceren met de server: (%1).</span><span class="sxs-lookup"><span data-stu-id="6e972-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="6e972-591">Resultaat: (%2)</span><span class="sxs-lookup"><span data-stu-id="6e972-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="6e972-592">Er is een communicatiefout opgetreden.</span><span class="sxs-lookup"><span data-stu-id="6e972-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="6e972-593">Controleer de volgende gebeurtenissen in het gebeurtenislogboek voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6e972-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-594">100</span><span class="sxs-lookup"><span data-stu-id="6e972-594">100</span></span></td>
   <td><span data-ttu-id="6e972-595">Microsoft Defender voor Eindpunt kan niet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="6e972-596">Foutcode: %1</span><span class="sxs-lookup"><span data-stu-id="6e972-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="6e972-597">De uitvoerbare SenseCE kan niet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6e972-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="6e972-598">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="6e972-598">Reboot the device.</span></span> <span data-ttu-id="6e972-599">Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="6e972-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-600">102</span><span class="sxs-lookup"><span data-stu-id="6e972-600">102</span></span></td>
   <td><span data-ttu-id="6e972-601">Microsoft Defender voor Endpoint Network Detection and Response executable is gestart</span><span class="sxs-lookup"><span data-stu-id="6e972-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="6e972-602">De uitvoerbare SenseNdr is gestart.</span><span class="sxs-lookup"><span data-stu-id="6e972-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="6e972-603">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="6e972-604">103</span><span class="sxs-lookup"><span data-stu-id="6e972-604">103</span></span></td>
   <td><span data-ttu-id="6e972-605">Microsoft Defender voor Endpoint Network Detection and Response executable is beëindigd</span><span class="sxs-lookup"><span data-stu-id="6e972-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="6e972-606">De uitvoerbare SenseNdr is beëindigd.</span><span class="sxs-lookup"><span data-stu-id="6e972-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="6e972-607">Normale bedrijfsmelding; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="6e972-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="6e972-608">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6e972-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e972-609">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6e972-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="6e972-610">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6e972-610">Related topics</span></span>
- [<span data-ttu-id="6e972-611">Onboarden Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="6e972-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="6e972-612">Instellingen voor apparaatproxy en internetverbinding configureren</span><span class="sxs-lookup"><span data-stu-id="6e972-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="6e972-613">Problemen met Microsoft Defender voor Eindpunt oplossen</span><span class="sxs-lookup"><span data-stu-id="6e972-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
