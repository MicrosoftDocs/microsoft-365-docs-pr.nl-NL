---
title: Netwerkbeveiliging inschakelen
description: Schakel netwerkbeveiliging in met Groepsbeleid, PowerShell of Mobile Device Management en Configuration Manager.
keywords: ANetwork-beveiliging, exploits, schadelijke website, ip, domein, domeinen, inschakelen, inschakelen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6afdcc16493839e83771ac831831fdbb121663a1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841772"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="fcda9-104">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="fcda9-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fcda9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fcda9-105">**Applies to:**</span></span>
- [<span data-ttu-id="fcda9-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fcda9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fcda9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcda9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="fcda9-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fcda9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fcda9-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fcda9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fcda9-110">[Netwerkbeveiliging](network-protection.md) helpt voorkomen dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten.</span><span class="sxs-lookup"><span data-stu-id="fcda9-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="fcda9-111">U kunt [netwerkbeveiliging](evaluate-network-protection.md) controleren in een testomgeving om te bekijken welke apps worden geblokkeerd voordat u deze inschakelen.</span><span class="sxs-lookup"><span data-stu-id="fcda9-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="fcda9-112">Meer informatie over configuratieopties voor netwerkfilters</span><span class="sxs-lookup"><span data-stu-id="fcda9-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="fcda9-113">Controleren of netwerkbeveiliging is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="fcda9-113">Check if network protection is enabled</span></span>

<span data-ttu-id="fcda9-114">Controleer of netwerkbeveiliging is ingeschakeld op een lokaal apparaat met behulp van registereditor.</span><span class="sxs-lookup"><span data-stu-id="fcda9-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="fcda9-115">Selecteer de **knop Start** op de taakbalk en typ **regedit om** registereditor te openen</span><span class="sxs-lookup"><span data-stu-id="fcda9-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="fcda9-116">Kies **HKEY_LOCAL_MACHINE** in het zijmenu</span><span class="sxs-lookup"><span data-stu-id="fcda9-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="fcda9-117">Navigeren door de geneste menu's naar  >  **SOFTWARE-beleid**  >  **van Microsoft**  >  **Windows Defender**  >  **Policy Manager**</span><span class="sxs-lookup"><span data-stu-id="fcda9-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Policy Manager**</span></span> 

4. <span data-ttu-id="fcda9-118">Selecteer **EnableNetworkProtection om** de huidige status van netwerkbeveiliging op het apparaat te bekijken</span><span class="sxs-lookup"><span data-stu-id="fcda9-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="fcda9-119">0 of **Uit**</span><span class="sxs-lookup"><span data-stu-id="fcda9-119">0, or **Off**</span></span>
    * <span data-ttu-id="fcda9-120">1 of **Aan**</span><span class="sxs-lookup"><span data-stu-id="fcda9-120">1, or **On**</span></span>
    * <span data-ttu-id="fcda9-121">2 of **auditmodus**</span><span class="sxs-lookup"><span data-stu-id="fcda9-121">2, or **Audit** mode</span></span>
    
    ![netwerkprotectie](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="fcda9-123">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="fcda9-123">Enable network protection</span></span>

<span data-ttu-id="fcda9-124">Schakel netwerkbeveiliging in met behulp van een van deze methoden:</span><span class="sxs-lookup"><span data-stu-id="fcda9-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="fcda9-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcda9-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="fcda9-126">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="fcda9-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="fcda9-127">Microsoft Endpoint Manager / Intune</span><span class="sxs-lookup"><span data-stu-id="fcda9-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="fcda9-128">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="fcda9-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="fcda9-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcda9-129">PowerShell</span></span>

1. <span data-ttu-id="fcda9-130">Typ **powershell** in het menu Start, klik met de **rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**</span><span class="sxs-lookup"><span data-stu-id="fcda9-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="fcda9-131">Voer de volgende cmdlet in:</span><span class="sxs-lookup"><span data-stu-id="fcda9-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="fcda9-132">Optioneel: Schakel de functie in de auditmodus in met de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fcda9-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="fcda9-133">Gebruik `Disabled` deze functie in plaats van of uit te `AuditMode` `Enabled` schakelen.</span><span class="sxs-lookup"><span data-stu-id="fcda9-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="fcda9-134">Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="fcda9-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="fcda9-135">Gebruik de CSP -configuratieprovider [(./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection)](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) om netwerkbeveiliging in of uit te schakelen of auditmodus in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="fcda9-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="fcda9-136">Microsoft Endpoint Manager (voorheen Intune)</span><span class="sxs-lookup"><span data-stu-id="fcda9-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="fcda9-137">Meld u aan bij Microsoft Endpoint Manager beheercentrum (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fcda9-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="fcda9-138">Een configuratieprofiel voor [eindpuntbeveiliging maken of bewerken](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="fcda9-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="fcda9-139">Ga **onder Configuratie Instellingen** in de profielstroom naar **Microsoft Defender Exploit Guard**  >  **Netwerkfiltering** Netwerkbeveiliging  >    >  **inschakelen** of alleen **controleren**</span><span class="sxs-lookup"><span data-stu-id="fcda9-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="fcda9-140">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="fcda9-140">Group Policy</span></span>

<span data-ttu-id="fcda9-141">Gebruik de volgende procedure om netwerkbeveiliging in te stellen op domeincomputers of op een zelfstandige computer.</span><span class="sxs-lookup"><span data-stu-id="fcda9-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="fcda9-142">Ga op een zelfstandige computer naar **Start** en typ en selecteer **Groepsbeleid bewerken.**</span><span class="sxs-lookup"><span data-stu-id="fcda9-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="fcda9-143">*-Of-*</span><span class="sxs-lookup"><span data-stu-id="fcda9-143">*-Or-*</span></span>

    <span data-ttu-id="fcda9-144">Open op een domeingevoegde computer [](https://technet.microsoft.com/library/cc731212.aspx)voor groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="fcda9-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="fcda9-145">Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.</span><span class="sxs-lookup"><span data-stu-id="fcda9-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="fcda9-146">Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit Guard Network**  >  **protection**.</span><span class="sxs-lookup"><span data-stu-id="fcda9-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="fcda9-147">In oudere versies van Windows kan het groepsbeleidspad 'Windows Defender Antivirus' zeggen in plaats van 'Microsoft Defender Antivirus'.</span><span class="sxs-lookup"><span data-stu-id="fcda9-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="fcda9-148">Dubbelklik op de **instelling Voorkomen dat gebruikers** en apps toegang krijgen tot gevaarlijke websites en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="fcda9-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="fcda9-149">In de sectie Opties moet u een van de volgende opties opgeven:</span><span class="sxs-lookup"><span data-stu-id="fcda9-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="fcda9-150">**Blokkeren:** gebruikers hebben geen toegang tot schadelijke IP-adressen en domeinen</span><span class="sxs-lookup"><span data-stu-id="fcda9-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="fcda9-151">**Uitschakelen (standaard)** - De functie Netwerkbeveiliging werkt niet.</span><span class="sxs-lookup"><span data-stu-id="fcda9-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="fcda9-152">Gebruikers worden niet geblokkeerd voor toegang tot schadelijke domeinen</span><span class="sxs-lookup"><span data-stu-id="fcda9-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="fcda9-153">**Auditmodus:** als een gebruiker een schadelijk IP-adres of domein bezoekt, wordt er een gebeurtenis opgenomen in het Windows gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="fcda9-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="fcda9-154">De gebruiker wordt echter niet geblokkeerd voor het bezoeken van het adres.</span><span class="sxs-lookup"><span data-stu-id="fcda9-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcda9-155">Als u netwerkbeveiliging volledig wilt inschakelen, moet u de optie Groepsbeleid instellen op **Ingeschakeld** en ook Blokkeren **selecteren** in de vervolgkeuzelijst Opties.</span><span class="sxs-lookup"><span data-stu-id="fcda9-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="fcda9-156">Bevestig dat netwerkbeveiliging is ingeschakeld op een lokale computer met behulp van registereditor:</span><span class="sxs-lookup"><span data-stu-id="fcda9-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="fcda9-157">Selecteer **Start** en typ **regedit om** registereditor te **openen.**</span><span class="sxs-lookup"><span data-stu-id="fcda9-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="fcda9-158">Navigeer naar **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="fcda9-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="fcda9-159">Selecteer **EnableNetworkProtection en** bevestig de waarde:</span><span class="sxs-lookup"><span data-stu-id="fcda9-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="fcda9-160">0=Uit</span><span class="sxs-lookup"><span data-stu-id="fcda9-160">0=Off</span></span>
   * <span data-ttu-id="fcda9-161">1=Aan</span><span class="sxs-lookup"><span data-stu-id="fcda9-161">1=On</span></span>
   * <span data-ttu-id="fcda9-162">2=Audit</span><span class="sxs-lookup"><span data-stu-id="fcda9-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="fcda9-163">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fcda9-163">See also</span></span>

* [<span data-ttu-id="fcda9-164">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="fcda9-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="fcda9-165">Netwerkbeveiliging evalueren</span><span class="sxs-lookup"><span data-stu-id="fcda9-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="fcda9-166">Problemen met netwerkbeveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="fcda9-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
