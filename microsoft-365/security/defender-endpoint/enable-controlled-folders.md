---
title: Gecontroleerde maptoegang inschakelen
keywords: Gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen, inschakelen, inschakelen, gebruiken
description: Informatie over het beveiligen van uw belangrijke bestanden door gecontroleerde maptoegang in te stellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218758"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="0c117-104">Gecontroleerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="0c117-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c117-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0c117-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c117-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c117-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0c117-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c117-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0c117-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0c117-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0c117-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0c117-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="0c117-110">[Met gecontroleerde maptoegang](controlled-folders.md) kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware.</span><span class="sxs-lookup"><span data-stu-id="0c117-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="0c117-111">Gecontroleerde maptoegang is inbegrepen in Windows 10 en Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0c117-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="0c117-112">U kunt beheerde maptoegang inschakelen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="0c117-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="0c117-113">Windows-beveiligingsapp</span><span class="sxs-lookup"><span data-stu-id="0c117-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="0c117-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0c117-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="0c117-115">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="0c117-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="0c117-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0c117-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="0c117-117">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="0c117-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="0c117-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c117-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="0c117-119">[Met de auditmodus](evaluate-controlled-folder-access.md) kunt u testen hoe de functie werkt (en gebeurtenissen controleren) zonder dat dit gevolgen heeft voor het normale gebruik van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c117-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="0c117-120">Instellingen voor groepsbeleid die het samenvoegen van de lokale beheerderslijst uitschakelen, overschrijven de instellingen voor beheerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="0c117-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="0c117-121">Ze overschrijven ook beveiligde mappen en toegestane apps die door de lokale beheerder zijn ingesteld via beheerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="0c117-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="0c117-122">Deze beleidsregels omvatten:</span><span class="sxs-lookup"><span data-stu-id="0c117-122">These policies include:</span></span>

* <span data-ttu-id="0c117-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span><span class="sxs-lookup"><span data-stu-id="0c117-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="0c117-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span><span class="sxs-lookup"><span data-stu-id="0c117-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="0c117-125">Zie Voorkomen of toestaan dat gebruikers lokaal microsoft Defender AV-beleidsinstellingen wijzigen voor meer informatie over het uitschakelen van het samenvoegen van lokale [lijst.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="0c117-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="0c117-126">Windows-beveiligingsapp</span><span class="sxs-lookup"><span data-stu-id="0c117-126">Windows Security app</span></span>

1. <span data-ttu-id="0c117-127">Open de Windows Security-app door het schildpictogram op de taakbalk te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0c117-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="0c117-128">U kunt ook zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="0c117-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="0c117-129">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer **vervolgens Ransomware-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="0c117-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="0c117-130">Stel de schakelknop voor **gecontroleerde maptoegang in** op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="0c117-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c117-131">Als beheerde maptoegang is geconfigureerd met groepsbeleid, PowerShell- of MDM-CSP's, wordt de status gewijzigd in de Windows Security-app na een herstart van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c117-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="0c117-132">Als de functie is ingesteld op **auditmodus** met een van deze hulpprogramma's, wordt in de Windows-beveiligings-app de status **Uit gebruikt.**</span><span class="sxs-lookup"><span data-stu-id="0c117-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="0c117-133">Als u gebruikersprofielgegevens beschermt, wordt u aangeraden het gebruikersprofiel op het standaardstation voor Windows-installatie te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="0c117-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="0c117-134">Intune</span><span class="sxs-lookup"><span data-stu-id="0c117-134">Intune</span></span>

1. <span data-ttu-id="0c117-135">Meld u aan bij [de Azure-portal](https://portal.azure.com) en open Intune.</span><span class="sxs-lookup"><span data-stu-id="0c117-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="0c117-136">Ga naar **Apparaatconfiguratieprofielen**  >    >  **Profiel maken.**</span><span class="sxs-lookup"><span data-stu-id="0c117-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="0c117-137">Noem het profiel een naam, kies **Windows 10 en hoger** en **Endpoint-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="0c117-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="0c117-138">![Eindpuntbeveiligingsprofiel maken](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="0c117-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="0c117-139">Ga naar **Configure**  >  **Windows Defender Exploit Guard Controlled folder**  >  **access**  >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="0c117-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="0c117-140">Typ het pad naar elke toepassing die toegang heeft tot beveiligde mappen en het pad naar een andere map die bescherming nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="0c117-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="0c117-141">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0c117-141">Select **Add**.</span></span><br/> <span data-ttu-id="0c117-142">![Gecontroleerde maptoegang inschakelen in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="0c117-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="0c117-143">Wilcard wordt ondersteund voor toepassingen, maar niet voor mappen.</span><span class="sxs-lookup"><span data-stu-id="0c117-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="0c117-144">Submappen zijn niet beveiligd.</span><span class="sxs-lookup"><span data-stu-id="0c117-144">Subfolders are not protected.</span></span> <span data-ttu-id="0c117-145">Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.</span><span class="sxs-lookup"><span data-stu-id="0c117-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="0c117-146">Selecteer **OK om** elk geopend blad op te slaan en Te **maken.**</span><span class="sxs-lookup"><span data-stu-id="0c117-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="0c117-147">Selecteer de **profieltoewijzingen, wijs** **alle gebruikers & alle apparaten** en Opslaan **aan.**</span><span class="sxs-lookup"><span data-stu-id="0c117-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="0c117-148">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="0c117-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="0c117-149">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) om apps in staat te stellen om wijzigingen aan te brengen in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="0c117-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="0c117-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0c117-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="0c117-151">Ga in Microsoft Endpoint Configuration Manager naar **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="0c117-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="0c117-152">Selecteer **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="0c117-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="0c117-153">Voer een naam en een beschrijving in, selecteer **Gecontroleerde maptoegang** en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="0c117-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="0c117-154">Kies of u wijzigingen blokkeert of controleert, andere apps toestaat of andere mappen toevoegt en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="0c117-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0c117-155">Wilcard wordt ondersteund voor toepassingen, maar niet voor mappen.</span><span class="sxs-lookup"><span data-stu-id="0c117-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="0c117-156">Submappen zijn niet beveiligd.</span><span class="sxs-lookup"><span data-stu-id="0c117-156">Subfolders are not protected.</span></span> <span data-ttu-id="0c117-157">Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.</span><span class="sxs-lookup"><span data-stu-id="0c117-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="0c117-158">Controleer de instellingen en selecteer **Volgende om** het beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="0c117-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="0c117-159">Nadat het beleid is gemaakt, **sluit u**.</span><span class="sxs-lookup"><span data-stu-id="0c117-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="0c117-160">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="0c117-160">Group Policy</span></span>

1. <span data-ttu-id="0c117-161">Open op uw apparaat voor [](https://technet.microsoft.com/library/cc731212.aspx)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="0c117-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="0c117-162">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="0c117-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="0c117-163">Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Gecontroleerde maptoegang.**</span><span class="sxs-lookup"><span data-stu-id="0c117-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="0c117-164">Dubbelklik op de instelling **Beheerde maptoegang configureren** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="0c117-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="0c117-165">In de sectie Opties moet u een van de volgende opties opgeven:</span><span class="sxs-lookup"><span data-stu-id="0c117-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="0c117-166">**Inschakelen:** schadelijke en verdachte apps mogen geen wijzigingen aanbrengen in bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="0c117-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="0c117-167">Er wordt een melding gegeven in het Windows-gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="0c117-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="0c117-168">**Uitschakelen (standaard)** - De functie Voor gecontroleerde maptoegang werkt niet.</span><span class="sxs-lookup"><span data-stu-id="0c117-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="0c117-169">Alle apps kunnen wijzigingen aanbrengen in bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="0c117-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="0c117-170">**Controlemodus:** wijzigingen zijn toegestaan als een schadelijke of verdachte app probeert een wijziging aan te brengen in een bestand in een beveiligde map.</span><span class="sxs-lookup"><span data-stu-id="0c117-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="0c117-171">Het wordt echter opgenomen in het Windows-gebeurtenislogboek, waar u de impact op uw organisatie kunt beoordelen.</span><span class="sxs-lookup"><span data-stu-id="0c117-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="0c117-172">**Alleen schijfwijzigingen blokkeren:** pogingen van niet-vertrouwde apps om naar schijfsectoren te schrijven, worden geregistreerd in het Windows-gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="0c117-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="0c117-173">Deze logboeken zijn te vinden in toepassingen en **serviceslogboeken** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="0c117-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="0c117-174">**Alleen controleschijfwijzigingen:** alleen pogingen om te schrijven naar beveiligde schijfsectoren worden opgenomen in het Windows-gebeurtenislogboek (onder Toepassingen en **serviceslogboeken**  >  **Microsoft**  >  **Windows Windows**  >  **Defender**  >  **Operational**  >  **ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="0c117-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="0c117-175">Pogingen om bestanden in beveiligde mappen te wijzigen of te verwijderen, worden niet opgenomen.</span><span class="sxs-lookup"><span data-stu-id="0c117-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Schermafbeelding van de groepsbeleidsoptie Ingeschakeld en Auditmodus geselecteerd in de vervolgkeuzekeuze](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="0c117-177">Als u gecontroleerde maptoegang volledig wilt inschakelen, moet u de optie Groepsbeleid instellen op Ingeschakeld en Blokkeren **selecteren** in de vervolgkeuzelijst Opties. </span><span class="sxs-lookup"><span data-stu-id="0c117-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="0c117-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c117-178">PowerShell</span></span>

1. <span data-ttu-id="0c117-179">Typ **powershell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell** en selecteer **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="0c117-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="0c117-180">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="0c117-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="0c117-181">U kunt de functie in de auditmodus inschakelen door in plaats van `AuditMode` `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="0c117-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="0c117-182">Gebruik `Disabled` deze functie om de functie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0c117-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c117-183">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0c117-183">See also</span></span>

* [<span data-ttu-id="0c117-184">Belangrijke mappen beveiligen met gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="0c117-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="0c117-185">Beheerde maptoegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="0c117-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="0c117-186">Microsoft Defender voor eindpunt evalueren</span><span class="sxs-lookup"><span data-stu-id="0c117-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
