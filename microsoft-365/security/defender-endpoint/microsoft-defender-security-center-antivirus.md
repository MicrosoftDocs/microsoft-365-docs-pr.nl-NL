---
title: Microsoft Defender Antivirus in de Windows Security-app
description: Nu Microsoft Defender Antivirus is opgenomen in de Windows Security-app, kunt u veelvoorkomende taken bekijken, vergelijken en uitvoeren.
keywords: wdav, antivirus, firewall, beveiliging, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 042bb67c223631ae1759b62a32c2f5713b4d62e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690077"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="f2f8c-104">Microsoft Defender Antivirus in de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2f8c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-105">**Applies to:**</span></span>

- [<span data-ttu-id="f2f8c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f2f8c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f2f8c-107">In Windows 10, versie 1703 en hoger maakt de Windows Defender-app deel uit van de Windows-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="f2f8c-108">Instellingen die voorheen deel uitmaakten van de Windows Defender-client en de hoofdinstellingen van Windows, zijn gecombineerd en verplaatst naar de nieuwe app, die standaard is geïnstalleerd als onderdeel van Windows 10, versie 1703.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2f8c-109">Als u de Windows Security Center-service uit schakelt, wordt Microsoft Defender Antivirus of [Windows Defender Firewall niet uitgeschakeld.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="f2f8c-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="f2f8c-110">Deze worden automatisch uitgeschakeld wanneer een antivirus- of firewallproduct van derden is geïnstalleerd en up-to-date wordt gehouden.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="f2f8c-111">Als u de Windows Security Center-service uit schakelt of de bijbehorende instellingen voor groepsbeleid configureert om te voorkomen dat deze wordt uitgevoerd of wordt uitgevoerd, kan de Windows Security-app verouderde of onjuiste informatie weergeven over antivirus- of firewallproducten die u op het apparaat hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="f2f8c-112">Het kan ook voorkomen dat Microsoft Defender Antivirus zichzelf inschakelen als u een oude of verouderde antivirussoftware van derden hebt of als u antivirusproducten van derden verwijdert die u mogelijk eerder hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="f2f8c-113">Hierdoor wordt de beveiliging van uw apparaat aanzienlijk lager en kan dit leiden tot malware-infecties.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="f2f8c-114">Zie het [windows-beveiligingsartikel](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) voor meer informatie over andere Windows-beveiligingsfuncties die in de app kunnen worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="f2f8c-115">De Windows Security-app is een clientinterface in Windows 10, versie 1703 en hoger.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="f2f8c-116">Het is niet de microsoft Defender Security Center-webportal die wordt gebruikt voor het controleren en beheren van [Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="f2f8c-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="f2f8c-117">Instellingen voor virus- en bedreigingsbeveiliging controleren in de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Schermafbeelding van het label & beveiligingsinstellingen voor virussen in de Windows Security-app](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="f2f8c-119">Open de Windows Security-app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="f2f8c-120">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="f2f8c-121">In de volgende secties wordt beschreven hoe u enkele van de meest voorkomende taken kunt uitvoeren bij het controleren of werken met de bedreigingsbeveiliging die wordt geboden door Microsoft Defender Antivirus in de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="f2f8c-122">Als deze instellingen zijn geconfigureerd en geïmplementeerd met groepsbeleid, zijn de instellingen die in deze sectie worden beschreven grijs en niet beschikbaar voor gebruik op afzonderlijke eindpunten.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="f2f8c-123">Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in Windows-instellingen.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="f2f8c-124">In het onderwerp Interactie [tussen eindgebruikers configureren met Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) wordt beschreven hoe instellingen voor lokaal beleid kunnen worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="f2f8c-125">Een scan uitvoeren met de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="f2f8c-126">Open de Windows Security-app door in het startmenu **voor** beveiliging te zoeken en vervolgens **Windows-beveiliging te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="f2f8c-127">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="f2f8c-128">Selecteer **Snel scannen.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-128">Select **Quick scan**.</span></span> <span data-ttu-id="f2f8c-129">Of als u een volledige scan wilt uitvoeren, **selecteert** u Scanopties en selecteert u vervolgens een optie, zoals **Volledige scan.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="f2f8c-130">Bekijk de versie van de beveiligingsinformatieupdate en download de meest recente updates in de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Versienummergegevens van beveiligingsinformatie](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="f2f8c-132">Open de Windows Security-app door in het startmenu *voor* beveiliging te zoeken en vervolgens **Windows-beveiliging te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="f2f8c-133">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="f2f8c-134">Selecteer **Virus- & beveiligingsupdates voor bedreigingen.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="f2f8c-135">De momenteel geïnstalleerde versie wordt weergegeven, samen met informatie over wanneer deze is gedownload.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="f2f8c-136">U kunt uw huidige gegevens controleren op de nieuwste versie die beschikbaar is voor handmatig downloaden of het wijzigingslogboek voor die versie controleren.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="f2f8c-137">Zie [Beveiligingsintelligentie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f2f8c-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="f2f8c-138">Selecteer **Controleren op updates om** nieuwe beveiligingsupdates te downloaden (als deze er zijn).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="f2f8c-139">Ervoor zorgen dat Microsoft Defender Antivirus is ingeschakeld in de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="f2f8c-140">Open de Windows Security-app door in het startmenu *voor* beveiliging te zoeken en vervolgens **Windows-beveiliging te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="f2f8c-141">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="f2f8c-142">Selecteer **Virusbeveiliging & beveiligingsinstellingen voor bedreigingen.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="f2f8c-143">Schakel de schakelknop **Realtimebeveiliging** in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2f8c-144">Als u **realtimebeveiliging uitschakelt,** wordt deze na een korte vertraging automatisch weer inschakelen.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="f2f8c-145">Dit is om ervoor te zorgen dat u beschermd bent tegen malware en bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="f2f8c-146">Als u een ander antivirusproduct installeert, schakelt Microsoft Defender Antivirus zichzelf automatisch uit en wordt dit als zodanig aangegeven in de Windows Security-app.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="f2f8c-147">Er wordt een instelling weergegeven waarmee u beperkt periodiek scannen [kunt inschakelen.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f2f8c-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="f2f8c-148">Uitsluitingen toevoegen voor Microsoft Defender Antivirus in de Windows Security-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="f2f8c-149">Open de Windows Security-app door in het startmenu *voor* beveiliging te zoeken en vervolgens **Windows-beveiliging te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="f2f8c-150">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="f2f8c-151">Selecteer onder **Instellingen beheren** de optie Virus & instellingen **voor bedreigingsbeveiliging.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="f2f8c-152">Selecteer onder **de instelling Uitsluitingen** de optie **Uitsluitingen toevoegen of verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="f2f8c-153">Selecteer het pluspictogram **+** () om het type te kiezen en stel de opties in voor elke uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="f2f8c-154">De volgende tabel bevat een overzicht van uitsluitingstypen en wat er gebeurt:</span><span class="sxs-lookup"><span data-stu-id="f2f8c-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="f2f8c-155">Type uitsluiting</span><span class="sxs-lookup"><span data-stu-id="f2f8c-155">Exclusion type</span></span>  |<span data-ttu-id="f2f8c-156">Gedefinieerd door</span><span class="sxs-lookup"><span data-stu-id="f2f8c-156">Defined by</span></span>  |<span data-ttu-id="f2f8c-157">Wat gebeurt er?</span><span class="sxs-lookup"><span data-stu-id="f2f8c-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f2f8c-158">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-158">**File**</span></span> |<span data-ttu-id="f2f8c-159">Locatie</span><span class="sxs-lookup"><span data-stu-id="f2f8c-159">Location</span></span> <br/><span data-ttu-id="f2f8c-160">Voorbeeld: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="f2f8c-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="f2f8c-161">Het specifieke bestand wordt overgeslagen door Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="f2f8c-162">**Map**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-162">**Folder**</span></span>    |<span data-ttu-id="f2f8c-163">Locatie</span><span class="sxs-lookup"><span data-stu-id="f2f8c-163">Location</span></span> <br/><span data-ttu-id="f2f8c-164">Voorbeeld: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="f2f8c-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="f2f8c-165">Alle items in de opgegeven map worden overgeslagen door Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="f2f8c-166">**Bestandstype**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-166">**File type**</span></span>   |<span data-ttu-id="f2f8c-167">Bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="f2f8c-167">File extension</span></span> <br/><span data-ttu-id="f2f8c-168">Voorbeeld: `.test`</span><span class="sxs-lookup"><span data-stu-id="f2f8c-168">Example: `.test`</span></span> |<span data-ttu-id="f2f8c-169">Alle bestanden met de `.test` extensie op uw apparaat worden overgeslagen door Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="f2f8c-170">**Proces**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-170">**Process**</span></span>     |<span data-ttu-id="f2f8c-171">Uitvoerbaar bestandspad</span><span class="sxs-lookup"><span data-stu-id="f2f8c-171">Executable file path</span></span> <br><span data-ttu-id="f2f8c-172">Voorbeeld: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="f2f8c-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="f2f8c-173">Het specifieke proces en alle bestanden die door dat proces worden geopend, worden overgeslagen door Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="f2f8c-174">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="f2f8c-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="f2f8c-175">Uitsluitingen configureren en valideren op basis van bestandsextensie en maplocatie</span><span class="sxs-lookup"><span data-stu-id="f2f8c-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="f2f8c-176">Uitsluitingen configureren voor bestanden die door processen zijn geopend</span><span class="sxs-lookup"><span data-stu-id="f2f8c-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="f2f8c-177">Geschiedenis van bedreigingsdetectie bekijken in de Windows Defender-beveiligingscentrum-app</span><span class="sxs-lookup"><span data-stu-id="f2f8c-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="f2f8c-178">Open de Windows Security-app door in het startmenu *voor* beveiliging te zoeken en vervolgens **Windows-beveiliging te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="f2f8c-179">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="f2f8c-180">Selecteer **Beveiligingsgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-180">Select **Protection history**.</span></span> <span data-ttu-id="f2f8c-181">Recente items worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="f2f8c-182">Opties voor beveiliging en herstel van ransomware instellen</span><span class="sxs-lookup"><span data-stu-id="f2f8c-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="f2f8c-183">Open de Windows Security-app door in het startmenu *voor* beveiliging te zoeken en vervolgens **Windows-beveiliging te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="f2f8c-184">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).</span><span class="sxs-lookup"><span data-stu-id="f2f8c-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="f2f8c-185">Selecteer **onder Ransomware-beveiliging** de optie **Ransomware-beveiliging beheren.**</span><span class="sxs-lookup"><span data-stu-id="f2f8c-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="f2f8c-186">Zie Belangrijke mappen beveiligen met gecontroleerde maptoegang als u instellingen **voor** gecontroleerde maptoegang [wilt wijzigen.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="f2f8c-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="f2f8c-187">Als u herstelopties voor  ransomware wilt instellen, selecteert u Instellen onder **Ransomware data recovery** en volgt u de instructies voor het koppelen of instellen van uw OneDrive-account, zodat u eenvoudig kunt herstellen van een ransomware-aanval.</span><span class="sxs-lookup"><span data-stu-id="f2f8c-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2f8c-188">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f2f8c-188">See also</span></span>
- [<span data-ttu-id="f2f8c-189">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f2f8c-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)