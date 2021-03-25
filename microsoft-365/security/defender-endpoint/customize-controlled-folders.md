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
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199903"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="38cc8-104">Beheerde maptoegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="38cc8-104">Customize controlled folder access</span></span>

<span data-ttu-id="38cc8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="38cc8-105">**Applies to:**</span></span>
- [<span data-ttu-id="38cc8-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="38cc8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="38cc8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38cc8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="38cc8-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="38cc8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="38cc8-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="38cc8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="38cc8-110">Met gecontroleerde maptoegang kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware.</span><span class="sxs-lookup"><span data-stu-id="38cc8-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="38cc8-111">Gecontroleerde maptoegang wordt ondersteund op Windows Server 2019- en Windows 10-clients.</span><span class="sxs-lookup"><span data-stu-id="38cc8-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="38cc8-112">In dit artikel wordt beschreven hoe u de mogelijkheden voor beheerde maptoegang kunt aanpassen en worden de volgende secties beschreven:</span><span class="sxs-lookup"><span data-stu-id="38cc8-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="38cc8-113">Extra mappen beveiligen</span><span class="sxs-lookup"><span data-stu-id="38cc8-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="38cc8-114">Apps toevoegen die toegang moeten krijgen tot beveiligde mappen</span><span class="sxs-lookup"><span data-stu-id="38cc8-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="38cc8-115">Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen</span><span class="sxs-lookup"><span data-stu-id="38cc8-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="38cc8-116">De melding aanpassen</span><span class="sxs-lookup"><span data-stu-id="38cc8-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="38cc8-117">Met gecontroleerde maptoegang worden apps gecontroleerd op activiteiten die als schadelijk worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="38cc8-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="38cc8-118">Soms worden legitieme apps geblokkeerd om wijzigingen aan te brengen in uw bestanden.</span><span class="sxs-lookup"><span data-stu-id="38cc8-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="38cc8-119">Als gecontroleerde maptoegang van invloed is op de productiviteit van uw organisatie, kunt u overwegen deze functie in de [auditmodus](audit-windows-defender.md) uit te voeren om de impact volledig te beoordelen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="38cc8-120">Extra mappen beveiligen</span><span class="sxs-lookup"><span data-stu-id="38cc8-120">Protect additional folders</span></span>

<span data-ttu-id="38cc8-121">Gecontroleerde maptoegang is van toepassing op veel systeemmappen en standaardlocaties, waaronder mappen zoals **Documenten,** **Afbeeldingen** en **Films.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="38cc8-122">U kunt extra mappen toevoegen die moeten worden beveiligd, maar u kunt de standaardmappen in de standaardlijst niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="38cc8-123">Het toevoegen van andere mappen aan gecontroleerde maptoegang kan handig zijn voor gevallen waarin u geen bestanden opgeslagen in de standaard Windows-bibliotheken of als u de standaardlocatie van uw bibliotheken hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="38cc8-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="38cc8-124">U kunt ook netwerkaandelen en in kaart gebrachte stations opgeven.</span><span class="sxs-lookup"><span data-stu-id="38cc8-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="38cc8-125">Omgevingsvariabelen en jokertekens worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="38cc8-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="38cc8-126">Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="38cc8-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="38cc8-127">U kunt de Windows Security-app, groepsbeleid, PowerShell-cmdlets of configuratieproviders voor mobiel apparaatbeheer gebruiken om extra beveiligde mappen toe te voegen en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="38cc8-128">De Windows Security-app gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="38cc8-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="38cc8-129">Open de Windows Security-app door het schildpictogram op de taakbalk te selecteren of door in het startmenu naar Beveiliging te **zoeken.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="38cc8-130">Selecteer **Virusbeveiliging & en** schuif omlaag naar de sectie **Ransomware-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="38cc8-131">Selecteer **Beveiliging van ransomware beheren** om het deelvenster **Ransomware-beveiliging te** openen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="38cc8-132">Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Beveiligde mappen.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="38cc8-133">Kies **Ja** in de **prompt Gebruikerstoegangsbesturingselement.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="38cc8-134">Het **deelvenster Beveiligde mappen** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="38cc8-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="38cc8-135">Selecteer **Een beveiligde map toevoegen** en volg de aanwijzingen om mappen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="38cc8-136">Groepsbeleid gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="38cc8-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="38cc8-137">Open op uw groepsbeleidscomputer de console Groepsbeleidsbeheer, [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="38cc8-138">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="38cc8-139">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Windows Defender Exploit Guard  >  **Controlled** map  >  **access**.</span><span class="sxs-lookup"><span data-stu-id="38cc8-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="38cc8-140">Dubbelklik op **Geconfigureerde beveiligde mappen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="38cc8-141">Selecteer **Weergeven** en voer elke map in.</span><span class="sxs-lookup"><span data-stu-id="38cc8-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="38cc8-142">PowerShell gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="38cc8-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="38cc8-143">Typ **PowerShell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell en** selecteer Uitvoeren als **beheerder**</span><span class="sxs-lookup"><span data-stu-id="38cc8-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="38cc8-144">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="38cc8-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="38cc8-145">Herhaal stap 2 totdat u alle mappen hebt toegevoegd die u wilt beveiligen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="38cc8-146">Mappen die worden toegevoegd, zijn zichtbaar in de Windows-beveiligingsapp.</span><span class="sxs-lookup"><span data-stu-id="38cc8-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Schermafbeelding van een PowerShell-venster met de cmdlet hierboven ingevoerd](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="38cc8-148">Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="38cc8-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="38cc8-149">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="38cc8-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="38cc8-150">MDM-CSP's gebruiken om extra mappen te beveiligen</span><span class="sxs-lookup"><span data-stu-id="38cc8-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="38cc8-151">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="38cc8-152">Specifieke apps toestaan om wijzigingen aan te brengen in gecontroleerde mappen</span><span class="sxs-lookup"><span data-stu-id="38cc8-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="38cc8-153">U kunt opgeven of bepaalde apps altijd als veilig worden beschouwd en schrijftoegang geven tot bestanden in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="38cc8-154">Het toestaan van apps kan handig zijn als een bepaalde app die u kent en vertrouwt, wordt geblokkeerd door de functie voor toegang tot beheerde mappen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38cc8-155">Standaard worden in Windows apps toegevoegd die als vriendelijk worden beschouwd aan de toegestane lijst.</span><span class="sxs-lookup"><span data-stu-id="38cc8-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="38cc8-156">Dergelijke apps die automatisch worden toegevoegd, worden niet opgenomen in de lijst die wordt weergegeven in de Windows Security-app of met de bijbehorende PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="38cc8-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="38cc8-157">U hoeft de meeste apps niet toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="38cc8-158">Voeg alleen apps toe als ze worden geblokkeerd en u kunt hun betrouwbaarheid controleren.</span><span class="sxs-lookup"><span data-stu-id="38cc8-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="38cc8-159">Wanneer u een app toevoegt, moet u de locatie van de app opgeven.</span><span class="sxs-lookup"><span data-stu-id="38cc8-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="38cc8-160">Alleen de app op die locatie heeft toegang tot de beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="38cc8-161">Als de app (met dezelfde naam) zich op een andere locatie bevindt, wordt deze niet toegevoegd aan de lijst met toegestane bestanden en kan deze worden geblokkeerd door gecontroleerde maptoegang.</span><span class="sxs-lookup"><span data-stu-id="38cc8-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="38cc8-162">Een toegestane toepassing of service heeft alleen schrijftoegang tot een gecontroleerde map nadat deze is gestart.</span><span class="sxs-lookup"><span data-stu-id="38cc8-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="38cc8-163">Een updateservice blijft bijvoorbeeld gebeurtenissen activeren nadat deze is toegestaan totdat deze is gestopt en opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="38cc8-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="38cc8-164">De Windows Defender-beveiligingsapp gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="38cc8-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="38cc8-165">Open de Windows Security-app door te zoeken in het startmenu voor **Beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="38cc8-166">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer vervolgens **Beveiliging tegen ransomware beheren.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="38cc8-167">Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Een app toestaan via Gecontroleerde maptoegang**</span><span class="sxs-lookup"><span data-stu-id="38cc8-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="38cc8-168">Selecteer **Een toegestane app toevoegen** en volg de aanwijzingen om apps toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knop Toegestane app toevoegen":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="38cc8-170">Groepsbeleid gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="38cc8-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="38cc8-171">Open op uw apparaat voor [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="38cc8-172">Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="38cc8-173">Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Windows Defender Exploit Guard  >  **Controlled** map  >  **access**.</span><span class="sxs-lookup"><span data-stu-id="38cc8-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="38cc8-174">Dubbelklik op de instelling **Toegestane toepassingen configureren** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="38cc8-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="38cc8-175">Selecteer **Elke** app laten zien en invoeren.</span><span class="sxs-lookup"><span data-stu-id="38cc8-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="38cc8-176">PowerShell gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="38cc8-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="38cc8-177">Typ **PowerShell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell en** selecteer Uitvoeren als **beheerder**</span><span class="sxs-lookup"><span data-stu-id="38cc8-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="38cc8-178">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="38cc8-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="38cc8-179">Als u bijvoorbeeld de  uitvoerbaretest.exein de map *C:\apps* wilt toevoegen, is de cmdlet als volgt:</span><span class="sxs-lookup"><span data-stu-id="38cc8-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="38cc8-180">Blijf gebruiken om `Add-MpPreference -ControlledFolderAccessAllowedApplications` meer apps toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="38cc8-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="38cc8-181">Apps die met deze cmdlet zijn toegevoegd, worden weergegeven in de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="38cc8-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdlet om een app toe te staan":::

> [!IMPORTANT]
> <span data-ttu-id="38cc8-183">Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="38cc8-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="38cc8-184">Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="38cc8-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="38cc8-185">MDM-CSP's gebruiken om specifieke apps toe te staan</span><span class="sxs-lookup"><span data-stu-id="38cc8-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="38cc8-186">Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="38cc8-187">Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen</span><span class="sxs-lookup"><span data-stu-id="38cc8-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="38cc8-188">Met Microsoft Defender voor endpoint-certificaat- en bestandsindicatoren kunnen ondertekende uitvoerbare bestanden toegang krijgen tot beveiligde mappen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="38cc8-189">Zie Indicatoren maken op basis van certificaten voor meer [informatie over de implementatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="38cc8-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="38cc8-190">Dit is niet van toepassing op scripting-engines, waaronder Powershell</span><span class="sxs-lookup"><span data-stu-id="38cc8-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="38cc8-191">De melding aanpassen</span><span class="sxs-lookup"><span data-stu-id="38cc8-191">Customize the notification</span></span>

<span data-ttu-id="38cc8-192">Zie [Waarschuwingsmeldingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)configureren in Microsoft Defender voor Eindpunt voor meer informatie over het aanpassen van de melding wanneer een regel wordt geactiveerd en blokkeert.</span><span class="sxs-lookup"><span data-stu-id="38cc8-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="38cc8-193">Zie ook</span><span class="sxs-lookup"><span data-stu-id="38cc8-193">See also</span></span>

- [<span data-ttu-id="38cc8-194">Belangrijke mappen beveiligen met gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="38cc8-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="38cc8-195">Gecontroleerde maptoegang inschakelen</span><span class="sxs-lookup"><span data-stu-id="38cc8-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="38cc8-196">Regels voor het verlagen van het oppervlak van de aanval evalueren</span><span class="sxs-lookup"><span data-stu-id="38cc8-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
