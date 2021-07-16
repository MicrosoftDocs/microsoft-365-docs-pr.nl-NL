---
title: Microsoft Defender for Endpoint (MDE) ervaren via gesimuleerde aanvallen
description: Test uw Microsoft 365 Defender proeflaboratorium of testomgeving.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457823"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="ba7a1-104">Microsoft Defender for Endpoint (MDE) ervaren via gesimuleerde aanvallen</span><span class="sxs-lookup"><span data-stu-id="ba7a1-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="ba7a1-105">Meer informatie over de nieuwste verbeteringen in Microsoft Defender voor Eindpunt: Wat is er [nieuw in Defender voor Eindpunt?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="ba7a1-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="ba7a1-106">Defender for Endpoint heeft in de recente MITRE-evaluatie de toonaangevende mogelijkheden voor optica en detectie gedemonstreerd.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="ba7a1-107">Lees: [Insights van de MITRE ATT-&op CK gebaseerde evaluatie](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="ba7a1-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="ba7a1-108">Mogelijk wilt u Defender voor Eindpunt ervaren voordat u meer dan een paar apparaten aan boord van de service aan boord gaat.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="ba7a1-109">Hiervoor kunt u gecontroleerde aanvalssimulaties uitvoeren op een paar testapparaten.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="ba7a1-110">Nadat u de gesimuleerde aanvallen hebt uitgevoerd, kunt u bekijken hoe in Defender voor Eindpunt schadelijke activiteiten worden aan het licht gekomen en kunt u bekijken hoe dit een efficiënte reactie mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ba7a1-111">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ba7a1-111">Before you begin</span></span>

<span data-ttu-id="ba7a1-112">Als u een van de meegeleverde simulaties wilt uitvoeren, hebt u ten minste [één apparaat met onboarding nodig.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="ba7a1-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="ba7a1-113">Lees het walkthrough-document dat bij elk aanvalsscenario wordt geleverd.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="ba7a1-114">Elk document bevat besturingssysteem- en toepassingsvereisten, evenals gedetailleerde instructies die specifiek zijn voor een aanvalsscenario.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="ba7a1-115">Een simulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ba7a1-115">Run a simulation</span></span>

1. <span data-ttu-id="ba7a1-116">Selecteer **in**  >  **Help-& zelfstudies** welke van de beschikbare aanvalsscenario's u wilt simuleren:</span><span class="sxs-lookup"><span data-stu-id="ba7a1-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="ba7a1-117">**Scenario 1: Document dropt backdoor-** simuleert de bezorging van een sociaal ontworpen lokmiddeldocument.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="ba7a1-118">Het document start een speciaal ontworpen backdoor die aanvallers controle geeft.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="ba7a1-119">**Scenario 2: PowerShell-script in bestandsloze** aanval : simuleert een bestandsloze aanval die afhankelijk is van PowerShell, waarbij de surface reduction van de aanval wordt belicht en de detectie van schadelijke geheugenactiviteit op apparaten wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="ba7a1-120">**Scenario 3: Geautomatiseerde reactie** op incidenten : activeert automatisch onderzoek, waarmee automatisch wordt gejaagd naar en herstelt van inbreukartefacten om de reactiecapaciteit voor incidenten te vergroten.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="ba7a1-121">Download en lees het bijbehorende doorloopdocument dat bij het geselecteerde scenario is geleverd.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="ba7a1-122">Download het simulatiebestand of kopieer het simulatiescript door naar  >  **Help-& navigeren.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="ba7a1-123">U kunt ervoor kiezen om het bestand of script te downloaden op het testapparaat, maar dit is niet verplicht.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="ba7a1-124">Voer het simulatiebestand of script uit op het testapparaat, zoals wordt geïnstrueerd in het doorloopdocument.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="ba7a1-125">Simulatiebestanden of scripts bootsen aanvalsactiviteit na, maar zijn in feite goedaardig en kunnen het testapparaat niet schaden of in gevaar brengen.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="ba7a1-126">ALTERNATIEVE ONDERWERPTEKST</span><span class="sxs-lookup"><span data-stu-id="ba7a1-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="ba7a1-127">Scenario's voor aanvallen simuleren</span><span class="sxs-lookup"><span data-stu-id="ba7a1-127">Simulate attack scenarios</span></span>

<span data-ttu-id="ba7a1-128">Gebruik de testapparaten om uw eigen aanvalssimulaties uit te voeren door er verbinding mee te maken.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="ba7a1-129">U kunt aanvalsscenario's simuleren met behulp van:</span><span class="sxs-lookup"><span data-stu-id="ba7a1-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="ba7a1-130">De [aanvalsscenario's 'Doe het zelf'](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="ba7a1-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="ba7a1-131">Bedreigingssimulatoren</span><span class="sxs-lookup"><span data-stu-id="ba7a1-131">Threat simulators</span></span>

<span data-ttu-id="ba7a1-132">U kunt ook Geavanceerd zoeken [gebruiken](advanced-hunting-overview.md) om gegevens op te vragen en [bedreigingsanalyses](threat-analytics.md) te gebruiken om rapporten over nieuwe bedreigingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="ba7a1-133">Doe-het-zelf-aanvalsscenario's</span><span class="sxs-lookup"><span data-stu-id="ba7a1-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="ba7a1-134">Als u op zoek bent naar een vooraf gemaakte simulatie, kunt u onze aanvalsscenario's ['Doe het zelf' gebruiken.](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="ba7a1-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="ba7a1-135">Deze scripts zijn veilig, gedocumenteerd en eenvoudig te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="ba7a1-136">Deze scenario's weerspiegelen de mogelijkheden van Defender voor eindpunten en helpen u bij het onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="ba7a1-137">De verbinding met de testapparaten wordt uitgevoerd met RDP.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="ba7a1-138">Zorg ervoor dat uw firewallinstellingen RDP-verbindingen toestaan.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="ba7a1-139">Verbinding maken naar uw apparaat en voer een aanvalssimulatie uit door **Verbinding maken.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![Afbeelding van de knop Verbinding maken voor testapparaten](images/test-machine-table.png)

2. <span data-ttu-id="ba7a1-141">Sla het RDP-bestand op en start het door **Verbinding maken.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Afbeelding van verbinding met extern bureaublad](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="ba7a1-143">Als u geen kopie van het wachtwoord hebt opgeslagen tijdens de eerste installatie, kunt u het wachtwoord opnieuw instellen door Wachtwoord opnieuw instellen te selecteren **in** het menu: Afbeelding van wachtwoord ![ opnieuw instellen](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="ba7a1-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="ba7a1-144">Het apparaat wijzigt de status in 'Wachtwoord opnieuw instellen', waarna u binnen enkele minuten uw nieuwe wachtwoord krijgt.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="ba7a1-145">Voer het wachtwoord in dat is weergegeven tijdens de stap voor het maken van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-145">Enter the password that was displayed during the device creation step.</span></span>

   ![Afbeelding van venster om referenties in te voeren](images/enter-password.png)

4. <span data-ttu-id="ba7a1-147">Voer doe-het-zelf-aanvalssimulaties uit op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="ba7a1-148">Scenario's voor bedreigingssimulator</span><span class="sxs-lookup"><span data-stu-id="ba7a1-148">Threat simulator scenarios</span></span>

<span data-ttu-id="ba7a1-149">Als u ervoor kiest om een van de ondersteunde bedreigingssimulatoren te installeren tijdens de installatie van het lab, kunt u de ingebouwde simulaties uitvoeren op de evaluatielaboratoriumapparaten.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="ba7a1-150">Het uitvoeren van bedreigingssimulaties met behulp van platforms van derden is een goede manier om Microsoft Defender te evalueren voor endpoint-mogelijkheden binnen de grenzen van een labomgeving.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="ba7a1-151">Voordat u simulaties kunt uitvoeren, moet u ervoor zorgen dat aan de volgende vereisten wordt voldaan:</span><span class="sxs-lookup"><span data-stu-id="ba7a1-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="ba7a1-152">Apparaten moeten worden toegevoegd aan het evaluatielaboratorium</span><span class="sxs-lookup"><span data-stu-id="ba7a1-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="ba7a1-153">Bedreigingssimulatoren moeten worden geïnstalleerd in het evaluatielaboratorium</span><span class="sxs-lookup"><span data-stu-id="ba7a1-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="ba7a1-154">Selecteer in de portal de optie **Simulatie maken.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="ba7a1-155">Selecteer een bedreigingssimulator.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-155">Select a threat simulator.</span></span>

    ![Afbeelding van de selectie van de bedreigingssimulator](images/select-simulator.png)

3. <span data-ttu-id="ba7a1-157">Kies een simulatie of kijk door de simulatiegalerie om door de beschikbare simulaties te bladeren.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="ba7a1-158">U kunt naar de galerie met simulaties gaan via:</span><span class="sxs-lookup"><span data-stu-id="ba7a1-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="ba7a1-159">Het hoofdevaluatiedashboard in **de tegel Overzicht van simulaties** of</span><span class="sxs-lookup"><span data-stu-id="ba7a1-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="ba7a1-160">Door te navigeren vanuit het **navigatiedeelvenster Evaluatie en zelfstudies**& zelfstudies en selecteer vervolgens  >  De catalogus van de **simulaties.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="ba7a1-161">Selecteer de apparaten waarop u de simulatie wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="ba7a1-162">Selecteer **Simulatie maken.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="ba7a1-163">Bekijk de voortgang van een simulatie door het tabblad **Simulaties te** selecteren. Bekijk de status van de simulatie, actieve waarschuwingen en andere details.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="ba7a1-164">![Afbeelding van het tabblad Simulaties](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="ba7a1-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="ba7a1-165">Nadat u uw simulaties hebt uitgevoerd, raden we u aan om door de voortgangsbalk van het lab te lopen en Microsoft Defender voor Eindpunt te verkennen en een geautomatiseerd onderzoek en herstel **te starten.**</span><span class="sxs-lookup"><span data-stu-id="ba7a1-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="ba7a1-166">Bekijk het bewijs dat door de functie is verzameld en geanalyseerd.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="ba7a1-167">Zoek naar bewijs van aanvallen door middel van geavanceerde jacht met behulp van de uitgebreide querytaal en onbewerkte telemetrie en bekijk enkele bedreigingen over de hele wereld die zijn gedocumenteerd in Bedreigingsanalyse.</span><span class="sxs-lookup"><span data-stu-id="ba7a1-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
