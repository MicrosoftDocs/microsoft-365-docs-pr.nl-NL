---
title: Beheerde maptoegang inschakelen
keywords: Gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen, inschakelen, inschakelen, gebruiken
description: Informatie over het beveiligen van uw belangrijke bestanden door gecontroleerde maptoegang in te stellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5a90a12457597fa38c648fd44bf194d2322a26af
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861218"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="f3328-104">Beheerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="f3328-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3328-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f3328-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3328-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f3328-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3328-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3328-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f3328-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f3328-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f3328-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f3328-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f3328-110">[Met gecontroleerde maptoegang](controlled-folders.md) kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware.</span><span class="sxs-lookup"><span data-stu-id="f3328-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="f3328-111">Gecontroleerde maptoegang is opgenomen in Windows 10 en Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f3328-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="f3328-112">U kunt beheerde maptoegang inschakelen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="f3328-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="f3328-113">Windows-beveiliging app</span><span class="sxs-lookup"><span data-stu-id="f3328-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="f3328-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="f3328-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="f3328-115">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="f3328-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="f3328-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f3328-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="f3328-117">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="f3328-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="f3328-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3328-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="f3328-119">[Met de auditmodus](evaluate-controlled-folder-access.md) kunt u testen hoe de functie werkt (en gebeurtenissen controleren) zonder dat dit gevolgen heeft voor het normale gebruik van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="f3328-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="f3328-120">Instellingen voor groepsbeleid die het samenvoegen van de lokale beheerderslijst uitschakelen, overschrijven de instellingen voor beheerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="f3328-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="f3328-121">Ze overschrijven ook beveiligde mappen en toegestane apps die door de lokale beheerder zijn ingesteld via beheerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="f3328-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="f3328-122">Deze beleidsregels omvatten:</span><span class="sxs-lookup"><span data-stu-id="f3328-122">These policies include:</span></span>

* <span data-ttu-id="f3328-123">Microsoft Defender Antivirus Gedrag **van lokale beheerders samenvoegen configureren voor lijsten**</span><span class="sxs-lookup"><span data-stu-id="f3328-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="f3328-124">System Center Endpoint Protection Toestaan **dat gebruikers uitsluitingen en overschrijven toevoegen**</span><span class="sxs-lookup"><span data-stu-id="f3328-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="f3328-125">Zie Voorkomen of toestaan dat gebruikers lokaal microsoft Defender AV-beleidsinstellingen wijzigen voor meer informatie over het uitschakelen van het samenvoegen van lokale [lijst.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="f3328-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="f3328-126">Windows-beveiliging app</span><span class="sxs-lookup"><span data-stu-id="f3328-126">Windows Security app</span></span>

1. <span data-ttu-id="f3328-127">Open de Windows-beveiliging app door het schildpictogram op de taakbalk te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f3328-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="f3328-128">U kunt ook zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="f3328-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="f3328-129">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer **vervolgens Ransomware-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="f3328-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="f3328-130">Stel de schakelknop voor **gecontroleerde maptoegang in** op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="f3328-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="f3328-131">Als beheerde maptoegang is geconfigureerd met groepsbeleids-, PowerShell- of MDM-CSP's, wordt de status gewijzigd in de Windows-beveiliging-app na een herstart van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="f3328-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="f3328-132">Als de functie is ingesteld op **auditmodus** met een van deze hulpprogramma's, Windows-beveiliging de app de status **Uit.**</span><span class="sxs-lookup"><span data-stu-id="f3328-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="f3328-133">Als u gebruikersprofielgegevens beschermt, raden we aan dat het gebruikersprofiel zich op het standaardstation Windows installeren.</span><span class="sxs-lookup"><span data-stu-id="f3328-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="f3328-134">Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="f3328-134">Endpoint Manager</span></span>

1. <span data-ttu-id="f3328-135">Meld u aan bij de [Endpoint Manager](https://endpoint.microsoft.com) en open **Endpoint Security**.</span><span class="sxs-lookup"><span data-stu-id="f3328-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="f3328-136">Ga naar **Attack Surface Reduction**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="f3328-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="f3328-137">Selecteer **Platform,** kies **Windows 10 en hoger** en selecteer het profiel Attack Surface Reduction **rules**  >  **Create**.</span><span class="sxs-lookup"><span data-stu-id="f3328-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="f3328-138">Geef het beleid een naam en voeg een beschrijving toe.</span><span class="sxs-lookup"><span data-stu-id="f3328-138">Name the policy and add a description.</span></span> <span data-ttu-id="f3328-139">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f3328-139">Select **Next**.</span></span>

5.  <span data-ttu-id="f3328-140">Schuif omlaag naar de onderkant, selecteer **de vervolgkeuzekeuzeknop** Mapbeveiliging inschakelen en kies **Inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="f3328-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="f3328-141">Selecteer **Lijst met extra mappen die moeten worden beveiligd** en voeg de mappen toe die moeten worden beveiligd.</span><span class="sxs-lookup"><span data-stu-id="f3328-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="f3328-142">Selecteer **Lijst met apps die toegang hebben tot beveiligde** mappen en voeg de apps toe die toegang hebben tot beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="f3328-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="f3328-143">Selecteer **Bestanden en paden uitsluiten van regels** voor het verlagen van het aanvalsoppervlak en voeg de bestanden en paden toe die moeten worden uitgesloten van de regels voor het verminderen van het aanvalsoppervlak.</span><span class="sxs-lookup"><span data-stu-id="f3328-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="f3328-144">Selecteer de **profieltoewijzingen, wijs** alle & **alle** apparaten toe en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f3328-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="f3328-145">Selecteer **Volgende om** elk geopend blad op te slaan en vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="f3328-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f3328-146">Jokertekens worden ondersteund voor toepassingen, maar niet voor mappen.</span><span class="sxs-lookup"><span data-stu-id="f3328-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="f3328-147">Submappen zijn niet beveiligd.</span><span class="sxs-lookup"><span data-stu-id="f3328-147">Subfolders are not protected.</span></span> <span data-ttu-id="f3328-148">Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.</span><span class="sxs-lookup"><span data-stu-id="f3328-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="f3328-149">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="f3328-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="f3328-150">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) om apps in staat te stellen om wijzigingen aan te brengen in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="f3328-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="f3328-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f3328-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="f3328-152">Ga Microsoft Endpoint Configuration Manager naar Assets **and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="f3328-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="f3328-153">Selecteer **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="f3328-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="f3328-154">Voer een naam en een beschrijving in, selecteer **Gecontroleerde maptoegang** en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="f3328-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="f3328-155">Kies of u wijzigingen blokkeert of controleert, andere apps toestaat of andere mappen toevoegt en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="f3328-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f3328-156">Wilcard wordt ondersteund voor toepassingen, maar niet voor mappen.</span><span class="sxs-lookup"><span data-stu-id="f3328-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="f3328-157">Submappen zijn niet beveiligd.</span><span class="sxs-lookup"><span data-stu-id="f3328-157">Subfolders are not protected.</span></span> <span data-ttu-id="f3328-158">Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.</span><span class="sxs-lookup"><span data-stu-id="f3328-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="f3328-159">Controleer de instellingen en selecteer **Volgende om** het beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="f3328-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="f3328-160">Nadat het beleid is gemaakt, **sluit u**.</span><span class="sxs-lookup"><span data-stu-id="f3328-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="f3328-161">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="f3328-161">Group Policy</span></span>

1. <span data-ttu-id="f3328-162">Open op uw apparaat voor [](https://technet.microsoft.com/library/cc731212.aspx)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="f3328-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="f3328-163">Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="f3328-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="f3328-164">Vouw de boom uit Windows **onderdelen > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Gecontroleerde maptoegang.**</span><span class="sxs-lookup"><span data-stu-id="f3328-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="f3328-165">Dubbelklik op de instelling **Beheerde maptoegang configureren** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="f3328-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="f3328-166">In de sectie Opties moet u een van de volgende opties opgeven:</span><span class="sxs-lookup"><span data-stu-id="f3328-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="f3328-167">**Inschakelen:** schadelijke en verdachte apps mogen geen wijzigingen aanbrengen in bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="f3328-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="f3328-168">Er wordt een melding verstrekt in het Windows gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="f3328-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="f3328-169">**Uitschakelen (standaard)** - De functie Voor gecontroleerde maptoegang werkt niet.</span><span class="sxs-lookup"><span data-stu-id="f3328-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="f3328-170">Alle apps kunnen wijzigingen aanbrengen in bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="f3328-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="f3328-171">**Controlemodus:** wijzigingen zijn toegestaan als een schadelijke of verdachte app probeert een wijziging aan te brengen in een bestand in een beveiligde map.</span><span class="sxs-lookup"><span data-stu-id="f3328-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="f3328-172">Het wordt echter opgenomen in het logboek Windows gebeurtenislogboek waarin u de impact op uw organisatie kunt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="f3328-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="f3328-173">**Alleen schijfwijzigingen blokkeren:** pogingen van niet-vertrouwde apps om naar schijfsectoren te schrijven, worden aangemeld Windows gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="f3328-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="f3328-174">Deze logboeken zijn te vinden in **toepassingen en serviceslogboeken** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="f3328-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="f3328-175">**Alleen** controleschijfwijzigingen: alleen pogingen om te schrijven naar beveiligde schijfsectoren worden opgenomen in het gebeurtenislogboek van Windows (onder Toepassingen en **serviceslogboeken**  >  **van Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**  >  **ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="f3328-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="f3328-176">Pogingen om bestanden in beveiligde mappen te wijzigen of te verwijderen, worden niet opgenomen.</span><span class="sxs-lookup"><span data-stu-id="f3328-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Schermafbeelding van de groepsbeleidsoptie Ingeschakeld en Auditmodus geselecteerd in de vervolgkeuzekeuze](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="f3328-178">Als u gecontroleerde maptoegang volledig wilt inschakelen, moet u de optie Groepsbeleid instellen op Ingeschakeld en Blokkeren **selecteren** in de vervolgkeuzelijst Opties. </span><span class="sxs-lookup"><span data-stu-id="f3328-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="f3328-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3328-179">PowerShell</span></span>

1. <span data-ttu-id="f3328-180">Typ **powershell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="f3328-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="f3328-181">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="f3328-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="f3328-182">U kunt de functie in de auditmodus inschakelen door in plaats van `AuditMode` `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="f3328-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="f3328-183">Gebruik `Disabled` deze functie om de functie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="f3328-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3328-184">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f3328-184">See also</span></span>

* [<span data-ttu-id="f3328-185">Belangrijke mappen beveiligen met gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="f3328-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="f3328-186">Beheerde maptoegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="f3328-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="f3328-187">Microsoft Defender voor Eindpunt evalueren</span><span class="sxs-lookup"><span data-stu-id="f3328-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
