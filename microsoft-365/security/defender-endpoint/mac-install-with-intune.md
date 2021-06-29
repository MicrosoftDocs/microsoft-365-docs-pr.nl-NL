---
title: Intune-implementatie voor Microsoft Defender voor Eindpunt op Mac
description: Installeer Microsoft Defender voor Eindpunt op Mac met Microsoft Intune.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7243e8f6fad225e6c4570184736e8d6588466d0a
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194959"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="7ef7e-104">Intune-implementatie voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="7ef7e-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ef7e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-105">**Applies to:**</span></span>

- [<span data-ttu-id="7ef7e-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="7ef7e-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="7ef7e-107">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt implementeert op macOS via Intune.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="7ef7e-108">Voor een geslaagde implementatie moet u alle volgende stappen voltooien:</span><span class="sxs-lookup"><span data-stu-id="7ef7e-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="7ef7e-109">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="7ef7e-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="7ef7e-110">Installatie van clientapparaat</span><span class="sxs-lookup"><span data-stu-id="7ef7e-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="7ef7e-111">Systeemextensies goedkeuren</span><span class="sxs-lookup"><span data-stu-id="7ef7e-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="7ef7e-112">Systeemconfiguratieprofielen maken</span><span class="sxs-lookup"><span data-stu-id="7ef7e-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="7ef7e-113">Toepassing publiceren</span><span class="sxs-lookup"><span data-stu-id="7ef7e-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="7ef7e-114">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="7ef7e-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="7ef7e-115">Voordat u aan de slag gaat, bekijkt u de hoofdpagina van Microsoft Defender voor Eindpunt op [macOS](microsoft-defender-endpoint-mac.md) voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="7ef7e-116">Overzicht</span><span class="sxs-lookup"><span data-stu-id="7ef7e-116">Overview</span></span>

<span data-ttu-id="7ef7e-117">In de volgende tabel vindt u een overzicht van de stappen die u moet ondernemen om Microsoft Defender voor Eindpunt op Macs te implementeren en te beheren via Intune.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="7ef7e-118">Hieronder vindt u meer gedetailleerde stappen.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="7ef7e-119">Stap</span><span class="sxs-lookup"><span data-stu-id="7ef7e-119">Step</span></span> | <span data-ttu-id="7ef7e-120">Voorbeeldbestandsnamen</span><span class="sxs-lookup"><span data-stu-id="7ef7e-120">Sample file names</span></span> | <span data-ttu-id="7ef7e-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="7ef7e-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="7ef7e-122">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="7ef7e-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="7ef7e-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="7ef7e-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="7ef7e-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="7ef7e-125">Systeemextensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7ef7e-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="7ef7e-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="7ef7e-127">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-127">N/A</span></span> |
| [<span data-ttu-id="7ef7e-128">Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7ef7e-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="7ef7e-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="7ef7e-130">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-130">N/A</span></span> |
| [<span data-ttu-id="7ef7e-131">Volledige schijftoegang verlenen aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7ef7e-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="7ef7e-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="7ef7e-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="7ef7e-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="7ef7e-134">Netwerkextensiebeleid</span><span class="sxs-lookup"><span data-stu-id="7ef7e-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="7ef7e-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="7ef7e-136">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-136">N/A</span></span> |
| [<span data-ttu-id="7ef7e-137">Microsoft AutoUpdate configureren (MAU)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="7ef7e-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="7ef7e-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="7ef7e-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="7ef7e-140">Configuratie-instellingen voor Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="7ef7e-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="7ef7e-141">**Opmerking:** Als u van plan bent een AV van derden voor macOS uit te voeren, stelt u dit `passiveMode` in op `true` .</span><span class="sxs-lookup"><span data-stu-id="7ef7e-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="7ef7e-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="7ef7e-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="7ef7e-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="7ef7e-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="7ef7e-144">Microsoft Defender configureren voor endpoint- en MS AutoUpdate-meldingen (MAU)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="7ef7e-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="7ef7e-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="7ef7e-146">com.microsoft.autoupdate2 of com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="7ef7e-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="7ef7e-147">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="7ef7e-147">Download the onboarding package</span></span>

<span data-ttu-id="7ef7e-148">Download de onboarding-pakketten van Microsoft Defender-beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="7ef7e-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="7ef7e-149">Ga Microsoft Defender-beveiligingscentrum naar Instellingen   >  **Onboarding voor**  >  **apparaatbeheer.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="7ef7e-150">Stel het besturingssysteem in **op macOS** en de implementatiemethode op **Mobile Device Management /Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Schermafbeelding van onboarding-instellingen](images/atp-mac-install.png)

3. <span data-ttu-id="7ef7e-152">Selecteer **Onboarding-pakket downloaden.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="7ef7e-153">Sla deze op als _WindowsDefenderATPOnboardingPackage.zip_ in dezelfde adreslijst.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="7ef7e-154">Haal de inhoud van het .zip op:</span><span class="sxs-lookup"><span data-stu-id="7ef7e-154">Extract the contents of the .zip file:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="7ef7e-155">Systeemconfiguratieprofielen maken</span><span class="sxs-lookup"><span data-stu-id="7ef7e-155">Create System Configuration profiles</span></span>

<span data-ttu-id="7ef7e-156">De volgende stap is het maken van systeemconfiguratieprofielen die microsoft Defender voor Eindpunt nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="7ef7e-157">Open in [Microsoft Endpoint Manager-beheercentrum](https://endpoint.microsoft.com/)de **profielen**  >  **Apparatenconfiguratie.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="7ef7e-158">Onboarding blob</span><span class="sxs-lookup"><span data-stu-id="7ef7e-158">Onboarding blob</span></span>

<span data-ttu-id="7ef7e-159">Dit profiel bevat een licentiegegevens voor Microsoft Defender voor Eindpunt, zonder dat het rapport meldt dat het niet is gelicentieerd.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="7ef7e-160">Selecteer **Profiel maken** onder **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="7ef7e-161">Selecteer **Platform** = **macOS**, **Profieltype** = **Sjablonen**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="7ef7e-162">**Naam van sjabloon** = **Aangepast**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="7ef7e-163">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-164">![Aangepaste configuratieprofiel maken](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="7ef7e-165">Kies een naam voor het profiel, bijvoorbeeld 'Defender or Endpoint onboarding for macOS'.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-165">Choose a name for the profile, e.g., "Defender or Endpoint onboarding for macOS".</span></span> <span data-ttu-id="7ef7e-166">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-167">![Aangepast configuratieprofiel - naam](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="7ef7e-168">Kies een naam voor de naam van het configuratieprofiel, bijvoorbeeld 'Defender for Endpoint onboarding for macOS'.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-168">Choose a name for the configuration profile name, e.g., "Defender for Endpoint onboarding for macOS".</span></span>
1. <span data-ttu-id="7ef7e-169">Selecteer intune/WindowsDefenderATPOnboarding.xml die u hebt geëxtraheerd uit het onboarding-pakket hierboven als configuratieprofielbestand.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-170">![Een configuratie importeren uit een bestand voor aangepast configuratieprofiel](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="7ef7e-171">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-171">Click **Next**.</span></span>
1. <span data-ttu-id="7ef7e-172">Wijs apparaten toe op **het tabblad** Toewijzing. Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-173">![Aangepast configuratieprofiel - toewijzing](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="7ef7e-174">Controleren en **maken.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-174">Review and **Create**.</span></span>
1. <span data-ttu-id="7ef7e-175">Open   >  **Apparaatconfiguratieprofielen,** u kunt uw gemaakte profiel daar zien.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-176">![Aangepast configuratieprofiel - klaar](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="7ef7e-177">Systeemextensies goedkeuren</span><span class="sxs-lookup"><span data-stu-id="7ef7e-177">Approve System Extensions</span></span>

<span data-ttu-id="7ef7e-178">Dit profiel is nodig voor macOS 10.15 (Catalina) of hoger.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="7ef7e-179">Deze wordt genegeerd op oudere macOS.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="7ef7e-180">Selecteer **Profiel maken** onder **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="7ef7e-181">Selecteer **Platform** = **macOS**, **Profieltype** = **Sjablonen**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="7ef7e-182">**Naam van sjabloon** = **Extensies**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="7ef7e-183">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-183">Click **Create**.</span></span>
1. <span data-ttu-id="7ef7e-184">Geef op **het** tabblad Basisbeginselen een naam op voor dit nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="7ef7e-185">Vouw op **het tabblad Configuratie-instellingen** **systeemextensies** uit om de volgende vermeldingen toe te voegen in **de sectie Toegestane systeemextensies:**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="7ef7e-186">Bundelaanduiding</span><span class="sxs-lookup"><span data-stu-id="7ef7e-186">Bundle identifier</span></span>         | <span data-ttu-id="7ef7e-187">Team-id</span><span class="sxs-lookup"><span data-stu-id="7ef7e-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="7ef7e-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="7ef7e-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="7ef7e-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="7ef7e-189">UBF8T346G9</span></span>
    <span data-ttu-id="7ef7e-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="7ef7e-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="7ef7e-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="7ef7e-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-192">![Systeemextensie-instellingen](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="7ef7e-193">Wijs **dit profiel op het** tabblad Opdrachten toe aan alle gebruikers & alle **apparaten.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="7ef7e-194">Controleer en maak dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="7ef7e-195">Kernelextensies</span><span class="sxs-lookup"><span data-stu-id="7ef7e-195">Kernel Extensions</span></span>

<span data-ttu-id="7ef7e-196">Dit profiel is nodig voor macOS 10.15 (Catalina) of ouder.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="7ef7e-197">Deze wordt genegeerd op nieuwere macOS.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="7ef7e-198">Apple Silicon (M1) apparaten bieden geen ondersteuning voor KEXT.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="7ef7e-199">De installatie van een configuratieprofiel met KEXT-beleid mislukt op deze apparaten.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="7ef7e-200">Selecteer **Profiel maken** onder **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="7ef7e-201">Selecteer **Platform** = **macOS**, **Profieltype** = **Sjablonen**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="7ef7e-202">**Naam van sjabloon** = **Extensies**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="7ef7e-203">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-203">Click **Create**.</span></span>
1. <span data-ttu-id="7ef7e-204">Geef op **het** tabblad Basisbeginselen een naam op voor dit nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="7ef7e-205">Vouw op **het tabblad Configuratie-instellingen** **kernelextensies uit.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="7ef7e-206">Stel **Team-id in** **op UBF8T346G9** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-207">![Instellingen voor kernelextensie](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="7ef7e-208">Wijs **dit profiel op het** tabblad Opdrachten toe aan alle gebruikers & alle **apparaten.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="7ef7e-209">Controleer en maak dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="7ef7e-210">Volledige schijftoegang</span><span class="sxs-lookup"><span data-stu-id="7ef7e-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="7ef7e-211">macOS 10.15 (Catalina) bevat nieuwe beveiligings- en privacyverbeteringen.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="7ef7e-212">Vanaf deze versie hebben toepassingen standaard geen toegang tot bepaalde locaties op schijf (zoals Documenten, Downloads, Bureaublad, enzovoort) zonder expliciete toestemming.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="7ef7e-213">Bij afwezigheid van deze toestemming kan Microsoft Defender voor Eindpunt uw apparaat niet volledig beveiligen.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="7ef7e-214">Dit configuratieprofiel verleent Volledige schijftoegang aan Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7ef7e-215">Als u Eerder Microsoft Defender voor Eindpunt hebt geconfigureerd via Intune, raden we u aan de implementatie bij te werken met dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="7ef7e-216">Download [**fulldisk.mobileconfig vanuit**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) [onze GitHub repository.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="7ef7e-217">Volg de instructies voor [Onboarding blob](#onboarding-blob) van bovenaf, gebruik 'Defender for Endpoint Full Disk Access' als profielnaam en **downloadde fulldisk.mobileconfig** als configuratieprofielnaam.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "Defender for Endpoint Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="7ef7e-218">Netwerkfilter</span><span class="sxs-lookup"><span data-stu-id="7ef7e-218">Network Filter</span></span>

<span data-ttu-id="7ef7e-219">Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoord controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="7ef7e-220">Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="7ef7e-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) vanuit [onze GitHub repository.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="7ef7e-222">Volg de instructies voor [Onboarding blob](#onboarding-blob) van bovenaf, gebruik 'Defender for Endpoint Network Filter' als profielnaam en **downloadde netfilter.mobileconfig** als configuratieprofielnaam.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "Defender for Endpoint Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="7ef7e-223">Meldingen</span><span class="sxs-lookup"><span data-stu-id="7ef7e-223">Notifications</span></span>

<span data-ttu-id="7ef7e-224">Dit profiel wordt gebruikt om microsoft Defender voor Eindpunt op macOS en Microsoft Auto Update toe te staan meldingen weer te geven in de gebruikersinterface op macOS 10.15 (Catalina) of hoger.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="7ef7e-225">Download [**notif.mobileconfig van**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) [onze GitHub repository.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="7ef7e-226">Volg de instructies voor [Onboarding blob](#onboarding-blob) van bovenaf, gebruik 'Defender for Endpoint Notifications' als profielnaam en **downloadde notif.mobileconfig** als configuratieprofielnaam.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "Defender for Endpoint Notifications" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="7ef7e-227">Status weergeven</span><span class="sxs-lookup"><span data-stu-id="7ef7e-227">View Status</span></span>

<span data-ttu-id="7ef7e-228">Wanneer de wijzigingen in Intune zijn doorgevoerd naar de geregistreerde apparaten, kunt u deze weergeven onder  >  **Apparaatstatus controleren:**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7ef7e-229">![Weergave van apparaatstatus in monitor](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="7ef7e-230">Toepassing publiceren</span><span class="sxs-lookup"><span data-stu-id="7ef7e-230">Publish application</span></span>

<span data-ttu-id="7ef7e-231">Met deze stap kunt u Microsoft Defender voor Eindpunt implementeren op geregistreerde machines.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="7ef7e-232">Open apps Microsoft Endpoint Manager het **beheercentrum.** [](https://endpoint.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-233">![Klaar om toepassing te maken](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="7ef7e-234">Selecteer Per platform > macOS > Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="7ef7e-235">Kies **App type** = **macOS**, klik op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-236">![Toepassingstype opgeven](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="7ef7e-237">Bewaar standaardwaarden en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-238">![Eigenschappen van toepassingen](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="7ef7e-239">Voeg opdrachten toe en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-240">![Schermafbeelding van intune-opdrachten](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="7ef7e-241">Controleren en **maken.**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-241">Review and **Create**.</span></span>
1. <span data-ttu-id="7ef7e-242">U kunt naar **Apps**  >  **per platform**  >  **macOS gaan** om deze te bekijken in de lijst met alle toepassingen.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-243">![Lijst met toepassingen](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="7ef7e-244">(U vindt gedetailleerde informatie op de [pagina van De Intune voor Defender-implementatie](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="7ef7e-245">U moet alle vereiste configuratieprofielen maken en deze naar alle machines pushen, zoals hierboven wordt uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="7ef7e-246">Installatie van clientapparaat</span><span class="sxs-lookup"><span data-stu-id="7ef7e-246">Client device setup</span></span>

<span data-ttu-id="7ef7e-247">U hebt geen speciale inrichting nodig voor een Mac-apparaat buiten een [standaardinstallatie Bedrijfsportal installeren.](/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="7ef7e-248">Bevestig apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-249">![Schermopname apparaatbeheer bevestigen](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="7ef7e-250">Selecteer **Systeemvoorkeuren** openen, zoek **Managementprofiel** in de lijst en selecteer **Goedkeuren...**. Uw managementprofiel wordt weergegeven als **Geverifieerd:**</span><span class="sxs-lookup"><span data-stu-id="7ef7e-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Schermafbeelding van managementprofiel](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="7ef7e-252">Selecteer **Doorgaan** en voltooi de inschrijving.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="7ef7e-253">U kunt nu meer apparaten registreren.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-253">You may now enroll more devices.</span></span> <span data-ttu-id="7ef7e-254">U kunt ze later ook registreren, nadat u klaar bent met het inrichten van systeemconfiguraties en toepassingspakketten.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="7ef7e-255">Open in Intune **Apparaten**  >  **beheren alle**  >  **apparaten**.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="7ef7e-256">Hier ziet u uw apparaat tussen de weergegeven apparaten:</span><span class="sxs-lookup"><span data-stu-id="7ef7e-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7ef7e-257">![Schermopname apparaten toevoegen](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="7ef7e-258">Status van clientapparaat controleren</span><span class="sxs-lookup"><span data-stu-id="7ef7e-258">Verify client device state</span></span>

1. <span data-ttu-id="7ef7e-259">Nadat de configuratieprofielen op uw apparaten zijn geïmplementeerd, opent u Systeemvoorkeurenprofielen  >   op uw Mac-apparaat.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-260">![Schermopname systeemvoorkeuren](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![Schermopname systeemvoorkeurenprofielen](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="7ef7e-262">Controleer of de volgende configuratieprofielen aanwezig en geïnstalleerd zijn.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="7ef7e-263">Het **managementprofiel** moet het Intune-systeemprofiel zijn.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="7ef7e-264">_Wdav-config_ en _wdav-kext_ zijn systeemconfiguratieprofielen die zijn toegevoegd in Intune:</span><span class="sxs-lookup"><span data-stu-id="7ef7e-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![Schermafbeelding van profielen](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="7ef7e-266">U ziet ook het pictogram Microsoft Defender voor eindpunt in de rechterbovenhoek:</span><span class="sxs-lookup"><span data-stu-id="7ef7e-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ef7e-267">![Pictogram Microsoft Defender voor eindpunt in schermafbeelding statusbalk](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7ef7e-268">Probleemoplossing</span><span class="sxs-lookup"><span data-stu-id="7ef7e-268">Troubleshooting</span></span>

<span data-ttu-id="7ef7e-269">Probleem: Er is geen licentie gevonden.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-269">Issue: No license found.</span></span>

<span data-ttu-id="7ef7e-270">Oplossing: Volg de bovenstaande stappen om een apparaatprofiel te maken met WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="7ef7e-271">Installatieproblemen met logboekregistratie</span><span class="sxs-lookup"><span data-stu-id="7ef7e-271">Logging installation issues</span></span>

<span data-ttu-id="7ef7e-272">Zie Installatieproblemen bij logboekregistratie voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma is gemaakt wanneer er een fout [optreedt.](mac-resources.md#logging-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="7ef7e-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="7ef7e-273">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="7ef7e-273">Uninstallation</span></span>

<span data-ttu-id="7ef7e-274">Zie [Verwijderen voor](mac-resources.md#uninstalling) meer informatie over het verwijderen van Microsoft Defender voor Eindpunt op macOS van clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="7ef7e-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
