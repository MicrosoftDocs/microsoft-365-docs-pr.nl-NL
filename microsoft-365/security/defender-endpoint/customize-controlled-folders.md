---
title: Beheerde maptoegang aanpassen
description: Voeg andere mappen toe die moeten worden beveiligd door gecontroleerde maptoegang of sta apps toe die wijzigingen in belangrijke bestanden onjuist blokkeren.
keywords: Gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen, aanpassen, map toevoegen, app toevoegen, toestaan, uitvoerbaar toevoegen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326531"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="5a412-104">Beheerde maptoegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="5a412-104">Customize controlled folder access</span></span>

<span data-ttu-id="5a412-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5a412-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a412-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5a412-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5a412-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a412-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="5a412-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5a412-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5a412-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5a412-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="5a412-110">Met gecontroleerde maptoegang kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware.</span><span class="sxs-lookup"><span data-stu-id="5a412-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="5a412-111">Gecontroleerde maptoegang wordt ondersteund op Windows Server 2019 en Windows 10 clients.</span><span class="sxs-lookup"><span data-stu-id="5a412-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="5a412-112">In dit artikel wordt beschreven hoe u de mogelijkheden voor beheerde maptoegang kunt aanpassen en worden de volgende secties beschreven:</span><span class="sxs-lookup"><span data-stu-id="5a412-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="5a412-113">Extra mappen beveiligen</span><span class="sxs-lookup"><span data-stu-id="5a412-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="5a412-114">Apps toevoegen die toegang moeten krijgen tot beveiligde mappen</span><span class="sxs-lookup"><span data-stu-id="5a412-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="5a412-115">Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen</span><span class="sxs-lookup"><span data-stu-id="5a412-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="5a412-116">De melding aanpassen</span><span class="sxs-lookup"><span data-stu-id="5a412-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="5a412-117">Met gecontroleerde maptoegang worden apps gecontroleerd op activiteiten die als schadelijk worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="5a412-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="5a412-118">Soms worden legitieme apps geblokkeerd om wijzigingen aan te brengen in uw bestanden.</span><span class="sxs-lookup"><span data-stu-id="5a412-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="5a412-119">Als gecontroleerde maptoegang van invloed is op de productiviteit van uw organisatie, kunt u overwegen deze functie in de [auditmodus](audit-windows-defender.md) uit te voeren om de impact volledig te beoordelen.</span><span class="sxs-lookup"><span data-stu-id="5a412-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="5a412-120">Extra mappen beveiligen</span><span class="sxs-lookup"><span data-stu-id="5a412-120">Protect additional folders</span></span>

<span data-ttu-id="5a412-121">Gecontroleerde maptoegang is van toepassing op veel systeemmappen en standaardlocaties, waaronder mappen zoals **Documenten,** **Afbeeldingen** en **Films.**</span><span class="sxs-lookup"><span data-stu-id="5a412-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="5a412-122">U kunt andere mappen toevoegen die moeten worden beveiligd, maar u kunt de standaardmappen in de standaardlijst niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5a412-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="5a412-123">Het toevoegen van andere mappen aan gecontroleerde maptoegang kan handig zijn voor gevallen waarin u geen bestanden opgeslagen in de standaardbibliotheken Windows of als u de standaardlocatie van uw bibliotheken hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5a412-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="5a412-124">U kunt ook netwerkaandelen en in kaart gebrachte stations opgeven.</span><span class="sxs-lookup"><span data-stu-id="5a412-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="5a412-125">Omgevingsvariabelen en jokertekens worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="5a412-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="5a412-126">Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5a412-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="5a412-127">U kunt de Windows-beveiliging, groepsbeleid, PowerShell-cmdlets of configuratieproviders voor mobiel apparaatbeheer gebruiken om beveiligde mappen toe te voegen en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5a412-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="5a412-128">De app Windows-beveiliging gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="5a412-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="5a412-129">Open de Windows-beveiliging app door het schildpictogram op de taakbalk te selecteren of door te zoeken naar *beveiliging* in het menu Start.</span><span class="sxs-lookup"><span data-stu-id="5a412-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="5a412-130">Selecteer **Virusbeveiliging & en** schuif omlaag naar de sectie **Ransomware-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="5a412-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="5a412-131">Selecteer **Beveiliging van ransomware beheren** om het deelvenster **Ransomware-beveiliging te** openen.</span><span class="sxs-lookup"><span data-stu-id="5a412-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="5a412-132">Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Beveiligde mappen.**</span><span class="sxs-lookup"><span data-stu-id="5a412-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="5a412-133">Kies **Ja** in de **prompt Gebruikerstoegangsbesturingselement.**</span><span class="sxs-lookup"><span data-stu-id="5a412-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="5a412-134">Het **deelvenster Beveiligde mappen** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5a412-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="5a412-135">Selecteer **Een beveiligde map toevoegen** en volg de aanwijzingen om mappen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="5a412-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="5a412-136">Groepsbeleid gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="5a412-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="5a412-137">Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span><span class="sxs-lookup"><span data-stu-id="5a412-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="5a412-138">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="5a412-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="5a412-139">Ga in **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor**  >    >  **computerconfiguratiebeleid.**</span><span class="sxs-lookup"><span data-stu-id="5a412-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="5a412-140">Vouw de structuur uit Windows **onderdelen van**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Beheerde maptoegang** van Exploit  >  Guard.</span><span class="sxs-lookup"><span data-stu-id="5a412-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="5a412-141">**OPMERKING**: In oudere versies van Windows ziet u mogelijk Windows Defender Antivirus **in** plaats van **Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="5a412-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="5a412-142">Dubbelklik op **Geconfigureerde beveiligde mappen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="5a412-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="5a412-143">Selecteer **Weergeven** en geef elke map op die u wilt beveiligen.</span><span class="sxs-lookup"><span data-stu-id="5a412-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="5a412-144">Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.</span><span class="sxs-lookup"><span data-stu-id="5a412-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="5a412-145">PowerShell gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="5a412-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="5a412-146">Typ **PowerShell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**</span><span class="sxs-lookup"><span data-stu-id="5a412-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="5a412-147">Typ de volgende PowerShell-cmdlet, vervangen door het pad van de `<the folder to be protected>` map (zoals `"c:\apps\"` ):</span><span class="sxs-lookup"><span data-stu-id="5a412-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="5a412-148">Herhaal stap 2 voor elke map die u wilt beveiligen.</span><span class="sxs-lookup"><span data-stu-id="5a412-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="5a412-149">Mappen die zijn beveiligd, zijn zichtbaar in de Windows-beveiliging app.</span><span class="sxs-lookup"><span data-stu-id="5a412-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="PowerShell-venster met cmdlet weergegeven":::

> [!IMPORTANT]
> <span data-ttu-id="5a412-151">Gebruik deze app om apps toe te voegen of toe te voegen `Add-MpPreference` aan de lijst en niet `Set-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="5a412-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="5a412-152">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="5a412-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="5a412-153">MDM-CSP's gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="5a412-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="5a412-154">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="5a412-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="5a412-155">Specifieke apps toestaan om wijzigingen aan te brengen in gecontroleerde mappen</span><span class="sxs-lookup"><span data-stu-id="5a412-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="5a412-156">U kunt opgeven of bepaalde apps altijd als veilig worden beschouwd en schrijftoegang geven tot bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="5a412-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="5a412-157">Het toestaan van apps kan handig zijn als een bepaalde app die u kent en vertrouwt, wordt geblokkeerd door de functie voor toegang tot beheerde mappen.</span><span class="sxs-lookup"><span data-stu-id="5a412-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a412-158">Standaard worden Windows apps toegevoegd die worden beschouwd als vriendelijk voor de toegestane lijst.</span><span class="sxs-lookup"><span data-stu-id="5a412-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="5a412-159">Dergelijke apps die automatisch worden toegevoegd, worden niet opgenomen in de lijst die wordt weergegeven in de Windows-beveiliging app of met de bijbehorende PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5a412-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="5a412-160">U hoeft de meeste apps niet toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="5a412-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="5a412-161">Voeg alleen apps toe als ze worden geblokkeerd en u kunt hun betrouwbaarheid controleren.</span><span class="sxs-lookup"><span data-stu-id="5a412-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="5a412-162">Wanneer u een app toevoegt, moet u de locatie van de app opgeven.</span><span class="sxs-lookup"><span data-stu-id="5a412-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="5a412-163">Alleen de app op die locatie heeft toegang tot de beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="5a412-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="5a412-164">Als de app (met dezelfde naam) zich op een andere locatie bevindt, wordt deze niet toegevoegd aan de allowlist en kan deze worden geblokkeerd door gecontroleerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="5a412-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="5a412-165">Een toegestane toepassing of service heeft alleen schrijftoegang tot een gecontroleerde map nadat deze is gestart.</span><span class="sxs-lookup"><span data-stu-id="5a412-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="5a412-166">Een updateservice blijft bijvoorbeeld gebeurtenissen activeren nadat deze is toegestaan totdat deze is gestopt en opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="5a412-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="5a412-167">De beveiligings-Windows Defender gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="5a412-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="5a412-168">Open de Windows-beveiliging app door te zoeken in het startmenu voor **Beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="5a412-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="5a412-169">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer vervolgens **Beveiliging tegen ransomware beheren.**</span><span class="sxs-lookup"><span data-stu-id="5a412-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="5a412-170">Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Een app toestaan via Gecontroleerde maptoegang**</span><span class="sxs-lookup"><span data-stu-id="5a412-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="5a412-171">Selecteer **Een toegestane app toevoegen** en volg de aanwijzingen om apps toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="5a412-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knop Toegestane app toevoegen":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="5a412-173">Groepsbeleid gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="5a412-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="5a412-174">Open op uw apparaat voor [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="5a412-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="5a412-175">Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="5a412-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="5a412-176">Vouw de structuur uit Windows **onderdelen van**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Beheerde maptoegang** van Exploit  >  Guard.</span><span class="sxs-lookup"><span data-stu-id="5a412-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="5a412-177">Dubbelklik op de instelling **Toegestane toepassingen configureren** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="5a412-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="5a412-178">Selecteer **Elke** app laten zien en invoeren.</span><span class="sxs-lookup"><span data-stu-id="5a412-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="5a412-179">PowerShell gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="5a412-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="5a412-180">Typ **PowerShell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**</span><span class="sxs-lookup"><span data-stu-id="5a412-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="5a412-181">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="5a412-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="5a412-182">Als u bijvoorbeeld de  uitvoerbaretest.exein de map *C:\apps* wilt toevoegen, is de cmdlet als volgt:</span><span class="sxs-lookup"><span data-stu-id="5a412-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="5a412-183">Blijf gebruiken om `Add-MpPreference -ControlledFolderAccessAllowedApplications` meer apps toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="5a412-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="5a412-184">Apps die met deze cmdlet zijn toegevoegd, worden weergegeven in de Windows-beveiliging app.</span><span class="sxs-lookup"><span data-stu-id="5a412-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdlet om een app toe te staan":::

> [!IMPORTANT]
> <span data-ttu-id="5a412-186">Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="5a412-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="5a412-187">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="5a412-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="5a412-188">MDM-CSP's gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="5a412-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="5a412-189">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="5a412-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="5a412-190">Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen</span><span class="sxs-lookup"><span data-stu-id="5a412-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="5a412-191">Met Microsoft Defender voor endpoint-certificaat- en bestandsindicatoren kunnen ondertekende uitvoerbare bestanden toegang krijgen tot beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="5a412-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="5a412-192">Zie Indicatoren maken op basis van certificaten voor meer [informatie over de implementatie.](indicator-certificates.md)</span><span class="sxs-lookup"><span data-stu-id="5a412-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="5a412-193">Dit is niet van toepassing op scripting-engines, waaronder Powershell</span><span class="sxs-lookup"><span data-stu-id="5a412-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="5a412-194">De melding aanpassen</span><span class="sxs-lookup"><span data-stu-id="5a412-194">Customize the notification</span></span>

<span data-ttu-id="5a412-195">Zie [Waarschuwingsmeldingen](configure-email-notifications.md)configureren in Microsoft Defender voor Eindpunt voor meer informatie over het aanpassen van de melding wanneer een regel wordt geactiveerd en blokkeert.</span><span class="sxs-lookup"><span data-stu-id="5a412-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a412-196">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5a412-196">See also</span></span>

- [<span data-ttu-id="5a412-197">Belangrijke mappen beveiligen met gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="5a412-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="5a412-198">Beheerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="5a412-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="5a412-199">Regels voor het verminderen van kwetsbaarheid voor aanvallen evalueren</span><span class="sxs-lookup"><span data-stu-id="5a412-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
