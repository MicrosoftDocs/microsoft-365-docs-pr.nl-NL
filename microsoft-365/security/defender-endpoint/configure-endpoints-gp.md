---
title: Onboard Windows 10 devices to Microsoft Defender for Endpoint via Group Policy
description: Gebruik Groepsbeleid om het configuratiepakket te implementeren op Windows 10 apparaten, zodat ze zijn aan boord van de service.
keywords: apparaten configureren met groepsbeleid, apparaatbeheer, Microsoft Defender configureren voor endpoint-apparaten, aan boord van Microsoft Defender voor eindpuntapparaten, groepsbeleid
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: f607e36cef85f30fa1d6e073da871ac1c140684c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841832"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="e8568-104">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="e8568-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8568-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e8568-105">**Applies to:**</span></span>

- <span data-ttu-id="e8568-106">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="e8568-106">Group Policy</span></span>
- [<span data-ttu-id="e8568-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e8568-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8568-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8568-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e8568-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e8568-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e8568-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e8568-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="e8568-111">Als u gp-updates (Group Policy) wilt gebruiken om het pakket te implementeren, moet u zich Windows Server 2008 R2 of hoger.</span><span class="sxs-lookup"><span data-stu-id="e8568-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="e8568-112">Voor Windows Server 2019 moet u mogelijk NT AUTHORITY\Well-Known-System-Account vervangen door NT AUTHORITY\SYSTEM van het XML-bestand dat door de groepsbeleidsvoorkeur wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e8568-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="e8568-113">Onboarden apparaten met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="e8568-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="e8568-114">[![Afbeelding van het PDF-bestand met de verschillende implementatiepaden](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e8568-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="e8568-115">Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) of [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="e8568-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="e8568-116">Open het GP-configuratiepakket .zip bestand *(WindowsDefenderATPOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="e8568-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="e8568-117">U kunt het pakket ook van [Microsoft Defender-beveiligingscentrum:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="e8568-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="e8568-118">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="e8568-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="e8568-119">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="e8568-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="e8568-120">Selecteer groepsbeleid in **het veld** **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="e8568-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="e8568-121">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="e8568-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="e8568-122">Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="e8568-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="e8568-123">U moet een map met de naam *OptionalParamsPolicy en* het bestand *WindowsDefenderATPOnboardingScript.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="e8568-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="e8568-124">Open de GPMC (Group [Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e8568-124">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="e8568-125">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie,** vervolgens **Voorkeuren** en vervolgens **naar Configuratiescherminstellingen.**</span><span class="sxs-lookup"><span data-stu-id="e8568-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="e8568-126">Klik met de rechtermuisknop **op Geplande taken,** wijs **Nieuw** aan en klik vervolgens op Onmiddellijke **taak (ten minste Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="e8568-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="e8568-127">Ga in **het** venster Taak dat wordt geopend naar het **tabblad** Algemeen. Klik **onder Beveiligingsopties** **op Gebruiker of Groep wijzigen** en typ SYSTEEM en klik vervolgens op Namen **controleren** en vervolgens **OP OK.**</span><span class="sxs-lookup"><span data-stu-id="e8568-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="e8568-128">NT AUTHORITY\SYSTEM wordt weergegeven als het gebruikersaccount dat de taak als wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8568-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="e8568-129">Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.</span><span class="sxs-lookup"><span data-stu-id="e8568-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="e8568-130">Ga naar het **tabblad Acties** en klik op **Nieuw...** Zorg ervoor **dat Een programma starten** is geselecteerd in het **veld** Actie.</span><span class="sxs-lookup"><span data-stu-id="e8568-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="e8568-131">Voer de bestandsnaam en locatie in van het gedeelde *WindowsDefenderATPOnboardingScript.cmd-bestand.*</span><span class="sxs-lookup"><span data-stu-id="e8568-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="e8568-132">Klik **op OK** en sluit alle geopende GPMC-vensters.</span><span class="sxs-lookup"><span data-stu-id="e8568-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="e8568-133">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="e8568-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="e8568-134">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpuntapparaat](run-detection-test.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8568-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="e8568-135">Aanvullende instellingen voor configuratie van Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="e8568-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="e8568-136">Voor elk apparaat kunt u bepalen of er steekproeven kunnen worden verzameld vanaf het apparaat wanneer er een verzoek wordt ingediend via Microsoft Defender-beveiligingscentrum om een bestand in te dienen voor uitgebreide analyse.</span><span class="sxs-lookup"><span data-stu-id="e8568-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="e8568-137">U kunt Groepsbeleid (GP) gebruiken om instellingen te configureren, zoals instellingen voor het delen van voorbeelden die worden gebruikt in de functie voor uitgebreide analyse.</span><span class="sxs-lookup"><span data-stu-id="e8568-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="e8568-138">Voorbeeldverzamelingsinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="e8568-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="e8568-139">Kopieer op uw GP-beheerapparaat de volgende bestanden uit het configuratiepakket:</span><span class="sxs-lookup"><span data-stu-id="e8568-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="e8568-140">_AtpConfiguration.admx kopiëren_ naar _C: \\ Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="e8568-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="e8568-141">_AtpConfiguration.adml kopiëren_ naar _C: \\ Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="e8568-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="e8568-142">Als u een Centraal Archief voor beheersjablonen voor [groepsbeleid](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)gebruikt, kopieert u de volgende bestanden uit het configuratiepakket:</span><span class="sxs-lookup"><span data-stu-id="e8568-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="e8568-143">_AtpConfiguration.admx kopiëren_ naar _\\ \\ \<forest.root\> \\ Beleidsregels voor SysVolDefinitions \\ \<forest.root\> \\ \\_</span><span class="sxs-lookup"><span data-stu-id="e8568-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="e8568-144">_AtpConfiguration.adml kopiëren_ naar _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="e8568-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="e8568-145">Open de [console Groepsbeleidsbeheer,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)klik met de rechtermuisknop op het GPO dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e8568-145">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="e8568-146">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="e8568-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="e8568-147">Klik **op Beleid** en vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="e8568-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="e8568-148">Klik **Windows onderdelen en** klik Windows Defender **SmartScreen.**</span><span class="sxs-lookup"><span data-stu-id="e8568-148">Click **Windows components** and then **Windows Defender SmartScreen**.</span></span>

6.  <span data-ttu-id="e8568-149">Kies om voorbeeld delen in of uit te schakelen vanaf uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="e8568-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="e8568-150">Als u geen waarde in stelt, is de standaardwaarde het inschakelen van voorbeeldverzameling.</span><span class="sxs-lookup"><span data-stu-id="e8568-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="e8568-151">Andere aanbevolen configuratie-instellingen</span><span class="sxs-lookup"><span data-stu-id="e8568-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="e8568-152">Configuratie van eindpuntbeveiliging bijwerken</span><span class="sxs-lookup"><span data-stu-id="e8568-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="e8568-153">Nadat u het onboarding-script heeft geconfigureerd, kunt u hetzelfde groepsbeleid blijven bewerken om configuraties voor eindpuntbeveiliging toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e8568-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="e8568-154">Voer groepsbeleidsbewerkingen uit vanaf een systeem met Windows 10 of Server 2019 om ervoor te zorgen dat u alle vereiste Microsoft Defender Antivirus hebt.</span><span class="sxs-lookup"><span data-stu-id="e8568-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="e8568-155">Mogelijk moet u het groepsbeleidsobject sluiten en opnieuw openen om de atp-configuratie-instellingen van Defender te registreren.</span><span class="sxs-lookup"><span data-stu-id="e8568-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="e8568-156">Alle beleidsregels bevinden zich onder `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="e8568-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="e8568-157">**Beleidslocatie:** \Windows Components\Windows Defender SmartScreen\*</span><span class="sxs-lookup"><span data-stu-id="e8568-157">**Policy location:** \Windows Components\Windows Defender SmartScreen\*</span></span>

<span data-ttu-id="e8568-158">Beleid</span><span class="sxs-lookup"><span data-stu-id="e8568-158">Policy</span></span> | <span data-ttu-id="e8568-159">Instelling</span><span class="sxs-lookup"><span data-stu-id="e8568-159">Setting</span></span> 
:---|:---
<span data-ttu-id="e8568-160">Inschakelen\Voorbeeldverzameling uitschakelen</span><span class="sxs-lookup"><span data-stu-id="e8568-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="e8568-161">Ingeschakeld - 'Voorbeeldverzameling op machines inschakelen' ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8568-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="e8568-162">**Beleidslocatie:** \Windows Onderdelen\Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e8568-162">**Policy location:**  \Windows Components\Microsoft Defender Antivirus</span></span>

<span data-ttu-id="e8568-163">Beleid</span><span class="sxs-lookup"><span data-stu-id="e8568-163">Policy</span></span> | <span data-ttu-id="e8568-164">Instelling</span><span class="sxs-lookup"><span data-stu-id="e8568-164">Setting</span></span> 
:---|:---
<span data-ttu-id="e8568-165">Detectie configureren voor potentieel ongewenste toepassingen</span><span class="sxs-lookup"><span data-stu-id="e8568-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="e8568-166">Ingeschakeld, Blokkeren</span><span class="sxs-lookup"><span data-stu-id="e8568-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="e8568-167">**Beleidslocatie:** \Windows Components\Microsoft Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="e8568-167">**Policy location:** \Windows Components\Microsoft Defender Antivirus\MAPS</span></span>

<span data-ttu-id="e8568-168">Beleid</span><span class="sxs-lookup"><span data-stu-id="e8568-168">Policy</span></span> | <span data-ttu-id="e8568-169">Instelling</span><span class="sxs-lookup"><span data-stu-id="e8568-169">Setting</span></span> 
:---|:---
<span data-ttu-id="e8568-170">Deelnemen aan Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="e8568-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="e8568-171">Ingeschakelde, geavanceerde KAARTEN</span><span class="sxs-lookup"><span data-stu-id="e8568-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="e8568-172">Bestandsvoorbeelden verzenden wanneer verdere analyse is vereist</span><span class="sxs-lookup"><span data-stu-id="e8568-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="e8568-173">Ingeschakeld: Veilige steekproeven verzenden</span><span class="sxs-lookup"><span data-stu-id="e8568-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="e8568-174">**Beleidslocatie:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span><span class="sxs-lookup"><span data-stu-id="e8568-174">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="e8568-175">Beleid</span><span class="sxs-lookup"><span data-stu-id="e8568-175">Policy</span></span> | <span data-ttu-id="e8568-176">Instelling</span><span class="sxs-lookup"><span data-stu-id="e8568-176">Setting</span></span> 
:---|:---
<span data-ttu-id="e8568-177">Realtime beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="e8568-177">Turn off real-time protection</span></span>|<span data-ttu-id="e8568-178">Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8568-178">Disabled</span></span>
<span data-ttu-id="e8568-179">Gedragscontrole in- en uit-</span><span class="sxs-lookup"><span data-stu-id="e8568-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="e8568-180">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8568-180">Enabled</span></span>
<span data-ttu-id="e8568-181">Alle gedownloade bestanden en bijlagen scannen</span><span class="sxs-lookup"><span data-stu-id="e8568-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="e8568-182">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8568-182">Enabled</span></span>
<span data-ttu-id="e8568-183">Bestands- en programmaactiviteit op uw computer controleren</span><span class="sxs-lookup"><span data-stu-id="e8568-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="e8568-184">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8568-184">Enabled</span></span>

<br/>

<span data-ttu-id="e8568-185">**Beleidslocatie:** \Windows Components\Microsoft Defender AntivirusScan</span><span class="sxs-lookup"><span data-stu-id="e8568-185">**Policy location:**  \Windows Components\Microsoft Defender AntivirusScan</span></span>

<span data-ttu-id="e8568-186">Deze instellingen configureren periodieke scans van het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="e8568-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="e8568-187">We raden u aan om een wekelijkse quick scan uit te voeren, waardoor de prestaties worden toegestaan.</span><span class="sxs-lookup"><span data-stu-id="e8568-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="e8568-188">Beleid</span><span class="sxs-lookup"><span data-stu-id="e8568-188">Policy</span></span> | <span data-ttu-id="e8568-189">Instelling</span><span class="sxs-lookup"><span data-stu-id="e8568-189">Setting</span></span> 
:---|:---
<span data-ttu-id="e8568-190">Controleer op de meest recente beveiligingsinformatie over virussen en spyware voordat u een geplande scan gaat uitvoeren</span><span class="sxs-lookup"><span data-stu-id="e8568-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="e8568-191">Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e8568-191">Enabled</span></span>


<br/>

<span data-ttu-id="e8568-192">**Beleidslocatie:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="e8568-192">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="e8568-193">De huidige lijst met GUID's voor het verlagen van het aanvalsoppervlak op de markt krijgen via De regels voor het verlagen van [de surface aanpassen](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="e8568-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="e8568-194">Open het **beleid Voor het configureren van Attack Surface Reduction.**</span><span class="sxs-lookup"><span data-stu-id="e8568-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="e8568-195">Selecteer **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="e8568-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="e8568-196">Selecteer de **knop** Weergeven.</span><span class="sxs-lookup"><span data-stu-id="e8568-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="e8568-197">Voeg elke GUID toe aan **het veld Waardenaam** met een waarde van 2.</span><span class="sxs-lookup"><span data-stu-id="e8568-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="e8568-198">Hiermee wordt elke audit alleen ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e8568-198">This will set each up for audit only.</span></span>

   ![Afbeelding van de configuratie van de surface reduction van de aanval](images/asr-guid.png)



<span data-ttu-id="e8568-200">Beleid</span><span class="sxs-lookup"><span data-stu-id="e8568-200">Policy</span></span> | <span data-ttu-id="e8568-201">Instelling</span><span class="sxs-lookup"><span data-stu-id="e8568-201">Setting</span></span> 
:---|:---
<span data-ttu-id="e8568-202">Beheerde maptoegang configureren</span><span class="sxs-lookup"><span data-stu-id="e8568-202">Configure Controlled folder access</span></span>| <span data-ttu-id="e8568-203">Ingeschakeld, auditmodus</span><span class="sxs-lookup"><span data-stu-id="e8568-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="e8568-204">Offboard-apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="e8568-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="e8568-205">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="e8568-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="e8568-206">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="e8568-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="e8568-207">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="e8568-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="e8568-208">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="e8568-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="e8568-209">Haal het offboarding-pakket van [Microsoft Defender-beveiligingscentrum:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="e8568-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="e8568-210">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="e8568-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="e8568-211">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="e8568-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="e8568-212">Selecteer groepsbeleid in **het veld** **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="e8568-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="e8568-213">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="e8568-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="e8568-214">Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="e8568-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="e8568-215">U moet een bestand met de *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="e8568-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="e8568-216">Open de GPMC (Group [Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e8568-216">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="e8568-217">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie,** vervolgens **Voorkeuren** en vervolgens **naar Configuratiescherminstellingen.**</span><span class="sxs-lookup"><span data-stu-id="e8568-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="e8568-218">Klik met de rechtermuisknop **op Geplande taken,** wijs **Nieuw** aan en klik vervolgens op **Onmiddellijke taak.**</span><span class="sxs-lookup"><span data-stu-id="e8568-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="e8568-219">Ga in **het** venster Taak dat wordt geopend naar het **tabblad** Algemeen. Kies het lokale SYSTEEM-gebruikersaccount (BUILTIN\SYSTEM) onder **Beveiligingsopties.**</span><span class="sxs-lookup"><span data-stu-id="e8568-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="e8568-220">Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.</span><span class="sxs-lookup"><span data-stu-id="e8568-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="e8568-221">Ga naar het **tabblad Acties** en klik op **Nieuw...**. Zorg ervoor **dat Een programma starten** is geselecteerd in het **veld** Actie.</span><span class="sxs-lookup"><span data-stu-id="e8568-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="e8568-222">Voer de bestandsnaam en de locatie van het gedeelde  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd-bestand* in.</span><span class="sxs-lookup"><span data-stu-id="e8568-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="e8568-223">Klik **op OK** en sluit alle geopende GPMC-vensters.</span><span class="sxs-lookup"><span data-stu-id="e8568-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8568-224">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="e8568-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="e8568-225">Apparaatconfiguratie controleren</span><span class="sxs-lookup"><span data-stu-id="e8568-225">Monitor device configuration</span></span>
<span data-ttu-id="e8568-226">Met Groepsbeleid is er geen optie om de implementatie van beleidsregels op de apparaten te controleren.</span><span class="sxs-lookup"><span data-stu-id="e8568-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="e8568-227">Monitoring kan rechtstreeks in de portal of met behulp van de verschillende implementatiehulpmiddelen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8568-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="e8568-228">Apparaten controleren met behulp van de portal</span><span class="sxs-lookup"><span data-stu-id="e8568-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="e8568-229">Ga naar [Microsoft Defender-beveiligingscentrum.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="e8568-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="e8568-230">Klik **op De lijst Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="e8568-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="e8568-231">Controleer of apparaten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8568-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="e8568-232">Het kan enkele dagen duren voordat apparaten worden weergegeven in de **lijst Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="e8568-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="e8568-233">Dit omvat de tijd die nodig is voor de distributie van het beleid naar het apparaat, de tijd die nodig is voordat de gebruiker zich aanmeldt en de tijd die nodig is voor het eindpunt om te beginnen met rapporteren.</span><span class="sxs-lookup"><span data-stu-id="e8568-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e8568-234">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e8568-234">Related topics</span></span>
- [<span data-ttu-id="e8568-235">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e8568-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="e8568-236">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="e8568-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="e8568-237">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="e8568-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="e8568-238">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="e8568-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="e8568-239">Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="e8568-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="e8568-240">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="e8568-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
