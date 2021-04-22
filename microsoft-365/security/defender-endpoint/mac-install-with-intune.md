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
ms.openlocfilehash: c98ce17b7b71f2d05aeffe66dbb1e08f9046f463
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933143"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3931e-104">Intune-implementatie voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="3931e-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> <span data-ttu-id="3931e-105">In deze documentatie wordt uitgelegd wat de oudere methode is voor het implementeren en configureren van Microsoft Defender voor Eindpunt op macOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="3931e-105">This documentation explains the legacy method for deploying and configuring Microsoft Defender for Endpoint on macOS devices.</span></span> <span data-ttu-id="3931e-106">De native ervaring is nu beschikbaar in de MEM-console.</span><span class="sxs-lookup"><span data-stu-id="3931e-106">The native experience is now available in the MEM console.</span></span> <span data-ttu-id="3931e-107">De release van de native GEBRUIKERSINTERFACE in de MEM-console biedt beheerders een veel eenvoudigere manier om de toepassing te configureren en te implementeren en deze naar macOS-apparaten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="3931e-107">The release of the native UI in the MEM console provide admins with a much simpler way to configure and deploy the application and send it down to macOS devices.</span></span> <br> <br>
><span data-ttu-id="3931e-108">Het blogbericht [MEM vereenvoudigt de implementatie van Microsoft Defender voor Eindpunt voor macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) met uitleg over de nieuwe functies.</span><span class="sxs-lookup"><span data-stu-id="3931e-108">The blog post [MEM simplifies deployment of Microsoft Defender for Endpoint for macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explains the new features.</span></span> <span data-ttu-id="3931e-109">Als u de app wilt configureren, gaat u naar [Instellingen voor Microsoft Defender voor Eindpunt op macOS in Microsoft InTune.](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos)</span><span class="sxs-lookup"><span data-stu-id="3931e-109">To configure the app, go to [Settings for Microsoft Defender for Endpoint on macOS in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span></span> <span data-ttu-id="3931e-110">Als u de app wilt implementeren, gaat u naar Microsoft Defender voor Eindpunt toevoegen [aan macOS-apparaten met Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="3931e-110">To deploy the app, go to [Add Microsoft Defender for Endpoint to macOS devices using Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span></span>

<span data-ttu-id="3931e-111">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3931e-111">**Applies to:**</span></span>

- [<span data-ttu-id="3931e-112">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="3931e-112">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="3931e-113">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt implementeert op macOS via Intune.</span><span class="sxs-lookup"><span data-stu-id="3931e-113">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="3931e-114">Voor een geslaagde implementatie moet u alle volgende stappen voltooien:</span><span class="sxs-lookup"><span data-stu-id="3931e-114">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="3931e-115">Installatie- en onboarding-pakketten downloaden</span><span class="sxs-lookup"><span data-stu-id="3931e-115">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
1. [<span data-ttu-id="3931e-116">Installatie van clientapparaat</span><span class="sxs-lookup"><span data-stu-id="3931e-116">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="3931e-117">Systeemextensies goedkeuren</span><span class="sxs-lookup"><span data-stu-id="3931e-117">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="3931e-118">Systeemconfiguratieprofielen maken</span><span class="sxs-lookup"><span data-stu-id="3931e-118">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="3931e-119">Toepassing publiceren</span><span class="sxs-lookup"><span data-stu-id="3931e-119">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="3931e-120">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="3931e-120">Prerequisites and system requirements</span></span>

<span data-ttu-id="3931e-121">Voordat u aan de slag gaat, bekijkt u de hoofdpagina van Microsoft Defender voor Eindpunt op [macOS](microsoft-defender-endpoint-mac.md) voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.</span><span class="sxs-lookup"><span data-stu-id="3931e-121">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="overview"></a><span data-ttu-id="3931e-122">Overzicht</span><span class="sxs-lookup"><span data-stu-id="3931e-122">Overview</span></span>

<span data-ttu-id="3931e-123">In de volgende tabel vindt u een overzicht van de stappen die u moet ondernemen om Microsoft Defender voor Eindpunt op Macs te implementeren en te beheren via Intune.</span><span class="sxs-lookup"><span data-stu-id="3931e-123">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="3931e-124">Hieronder vindt u meer gedetailleerde stappen.</span><span class="sxs-lookup"><span data-stu-id="3931e-124">More detailed steps are available below.</span></span>

| <span data-ttu-id="3931e-125">Stap</span><span class="sxs-lookup"><span data-stu-id="3931e-125">Step</span></span> | <span data-ttu-id="3931e-126">Voorbeeldbestandsnamen</span><span class="sxs-lookup"><span data-stu-id="3931e-126">Sample file names</span></span> | <span data-ttu-id="3931e-127">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="3931e-127">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="3931e-128">Installatie- en onboarding-pakketten downloaden</span><span class="sxs-lookup"><span data-stu-id="3931e-128">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="3931e-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="3931e-130">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="3931e-130">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="3931e-131">Systeemextensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3931e-131">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="3931e-132">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-132">MDATP_SysExt.xml</span></span> | <span data-ttu-id="3931e-133">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="3931e-133">N/A</span></span> |
| [<span data-ttu-id="3931e-134">Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3931e-134">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="3931e-135">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-135">MDATP_KExt.xml</span></span> | <span data-ttu-id="3931e-136">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="3931e-136">N/A</span></span> |
| [<span data-ttu-id="3931e-137">Volledige schijftoegang verlenen aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3931e-137">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#create-system-configuration-profiles-step-8) | <span data-ttu-id="3931e-138">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-138">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="3931e-139">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="3931e-139">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="3931e-140">Netwerkextensiebeleid</span><span class="sxs-lookup"><span data-stu-id="3931e-140">Network Extension policy</span></span>](#create-system-configuration-profiles-step-9) | <span data-ttu-id="3931e-141">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-141">MDATP_NetExt.xml</span></span> | <span data-ttu-id="3931e-142">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="3931e-142">N/A</span></span> |
| [<span data-ttu-id="3931e-143">Microsoft AutoUpdate configureren (MAU)</span><span class="sxs-lookup"><span data-stu-id="3931e-143">Configure Microsoft AutoUpdate (MAU)</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | <span data-ttu-id="3931e-144">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-144">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="3931e-145">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="3931e-145">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="3931e-146">Configuratie-instellingen voor Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="3931e-146">Microsoft Defender for Endpoint configuration settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> <span data-ttu-id="3931e-147">**Opmerking:** Als u van plan bent een AV van derden voor macOS uit te voeren, stelt u dit `passiveMode` in op `true` .</span><span class="sxs-lookup"><span data-stu-id="3931e-147">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="3931e-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="3931e-149">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="3931e-149">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="3931e-150">Microsoft Defender configureren voor endpoint- en MS AutoUpdate-meldingen (MAU)</span><span class="sxs-lookup"><span data-stu-id="3931e-150">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](#create-system-configuration-profiles-step-10) | <span data-ttu-id="3931e-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="3931e-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="3931e-152">com.microsoft.autoupdate2 of com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="3931e-152">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="3931e-153">Installatie- en onboarding-pakketten downloaden</span><span class="sxs-lookup"><span data-stu-id="3931e-153">Download installation and onboarding packages</span></span>

<span data-ttu-id="3931e-154">Download de installatie- en onboarding-pakketten van het Microsoft Defender-beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="3931e-154">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="3931e-155">Ga in het Microsoft Defender-beveiligingscentrum naar **Instellingen**  >  **Apparaatbeheer**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="3931e-155">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="3931e-156">Stel het besturingssysteem in op **macOS** en de implementatiemethode op **Mobile Device Management / Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="3931e-156">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Schermafbeelding van onboarding-instellingen](images/atp-mac-install.png)

3. <span data-ttu-id="3931e-158">Selecteer **Installatiepakket downloaden.**</span><span class="sxs-lookup"><span data-stu-id="3931e-158">Select **Download installation package**.</span></span> <span data-ttu-id="3931e-159">Sla deze op _als wdav.pkg in_ een lokale adreslijst.</span><span class="sxs-lookup"><span data-stu-id="3931e-159">Save it as _wdav.pkg_ to a local directory.</span></span>

4. <span data-ttu-id="3931e-160">Selecteer **Onboarding-pakket downloaden.**</span><span class="sxs-lookup"><span data-stu-id="3931e-160">Select **Download onboarding package**.</span></span> <span data-ttu-id="3931e-161">Sla deze op als _WindowsDefenderATPOnboardingPackage.zip_ in dezelfde adreslijst.</span><span class="sxs-lookup"><span data-stu-id="3931e-161">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

5. <span data-ttu-id="3931e-162">Download **IntuneAppUtil** van [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos) .</span><span class="sxs-lookup"><span data-stu-id="3931e-162">Download **IntuneAppUtil** from [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos).</span></span>

6. <span data-ttu-id="3931e-163">Controleer in een opdrachtprompt of u de drie bestanden hebt.</span><span class="sxs-lookup"><span data-stu-id="3931e-163">From a command prompt, verify that you have the three files.</span></span>
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. <span data-ttu-id="3931e-164">Haal de inhoud van de ZIP-bestanden op:</span><span class="sxs-lookup"><span data-stu-id="3931e-164">Extract the contents of the .zip files:</span></span>

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

8. <span data-ttu-id="3931e-165">Maak Van IntuneAppUtil een uitvoerbaar:</span><span class="sxs-lookup"><span data-stu-id="3931e-165">Make IntuneAppUtil an executable:</span></span>

    ```bash
    chmod +x IntuneAppUtil
    ```

9. <span data-ttu-id="3931e-166">Maak het wdav.pkg.intunemac-pakket van wdav.pkg:</span><span class="sxs-lookup"><span data-stu-id="3931e-166">Create the wdav.pkg.intunemac package from wdav.pkg:</span></span>

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a><span data-ttu-id="3931e-167">Installatie van clientapparaat</span><span class="sxs-lookup"><span data-stu-id="3931e-167">Client device setup</span></span>

<span data-ttu-id="3931e-168">U hebt geen speciale inrichting nodig voor een Mac-apparaat buiten een [standaardbedrijfsportalinstallatie.](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="3931e-168">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="3931e-169">Bevestig apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="3931e-169">Confirm device management.</span></span>

   ![Schermopname apparaatbeheer bevestigen](images/mdatp-3-confirmdevicemgmt.png)

    <span data-ttu-id="3931e-171">Selecteer **Systeemvoorkeuren** openen, zoek **Managementprofiel** in de lijst en selecteer **Goedkeuren...**. Uw managementprofiel wordt weergegeven als **Geverifieerd:**</span><span class="sxs-lookup"><span data-stu-id="3931e-171">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Schermafbeelding van managementprofiel](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="3931e-173">Selecteer **Doorgaan** en voltooi de inschrijving.</span><span class="sxs-lookup"><span data-stu-id="3931e-173">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="3931e-174">U kunt nu meer apparaten registreren.</span><span class="sxs-lookup"><span data-stu-id="3931e-174">You may now enroll more devices.</span></span> <span data-ttu-id="3931e-175">U kunt ze later ook registreren, nadat u klaar bent met het inrichten van systeemconfiguraties en toepassingspakketten.</span><span class="sxs-lookup"><span data-stu-id="3931e-175">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="3931e-176">Open in Intune **Apparaten**  >  **beheren alle**  >  **apparaten**.</span><span class="sxs-lookup"><span data-stu-id="3931e-176">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="3931e-177">Hier ziet u uw apparaat tussen de weergegeven apparaten:</span><span class="sxs-lookup"><span data-stu-id="3931e-177">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3931e-178">![Schermopname apparaten toevoegen](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-178">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="approve-system-extensions"></a><span data-ttu-id="3931e-179">Systeemextensies goedkeuren</span><span class="sxs-lookup"><span data-stu-id="3931e-179">Approve System Extensions</span></span>

<span data-ttu-id="3931e-180">De systeemextensies goedkeuren:</span><span class="sxs-lookup"><span data-stu-id="3931e-180">To approve the system extensions:</span></span>

1. <span data-ttu-id="3931e-181">Open in Intune   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="3931e-181">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="3931e-182">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="3931e-182">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="3931e-183">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="3931e-183">Choose a name for the profile.</span></span> <span data-ttu-id="3931e-184">**Platform=macOS wijzigen** in **Profieltype=Extensies**.</span><span class="sxs-lookup"><span data-stu-id="3931e-184">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="3931e-185">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="3931e-185">Select **Create**.</span></span>

3. <span data-ttu-id="3931e-186">Geef op **het** tabblad Basisbeginselen een naam op voor dit nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="3931e-186">In the **Basics** tab, give a name to this new profile.</span></span>

4. <span data-ttu-id="3931e-187">Voeg op **het tabblad Configuratie-instellingen** de volgende vermeldingen toe in **de sectie Toegestane systeemextensies:**</span><span class="sxs-lookup"><span data-stu-id="3931e-187">In the **Configuration settings** tab, add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="3931e-188">Bundelaanduiding</span><span class="sxs-lookup"><span data-stu-id="3931e-188">Bundle identifier</span></span>         | <span data-ttu-id="3931e-189">Team-id</span><span class="sxs-lookup"><span data-stu-id="3931e-189">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="3931e-190">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="3931e-190">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="3931e-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3931e-191">UBF8T346G9</span></span>
    <span data-ttu-id="3931e-192">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="3931e-192">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="3931e-193">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3931e-193">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-194">![Schermafbeelding van de extensie-instellingen in Configuratie-instellingen op het tabblad Basisbeginselen](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-194">![Screenshot of the extension settings in Configuration settings on the Basics tab](images/mac-system-extension-intune2.png)</span></span>

5. <span data-ttu-id="3931e-195">Wijs **dit profiel op het** tabblad Opdrachten toe aan alle gebruikers & alle **apparaten.**</span><span class="sxs-lookup"><span data-stu-id="3931e-195">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>

6. <span data-ttu-id="3931e-196">Controleer en maak dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="3931e-196">Review and create this configuration profile.</span></span>

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="3931e-197">Systeemconfiguratieprofielen maken</span><span class="sxs-lookup"><span data-stu-id="3931e-197">Create System Configuration profiles</span></span>

1. <span data-ttu-id="3931e-198">Open in Intune   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="3931e-198">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="3931e-199">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="3931e-199">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="3931e-200">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="3931e-200">Choose a name for the profile.</span></span> <span data-ttu-id="3931e-201">**Platform=macOS wijzigen** in **Profieltype=Aangepast**.</span><span class="sxs-lookup"><span data-stu-id="3931e-201">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="3931e-202">Selecteer **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="3931e-202">Select **Configure**.</span></span>

3. <span data-ttu-id="3931e-203">Open het configuratieprofiel en upload intune/kext.xml.</span><span class="sxs-lookup"><span data-stu-id="3931e-203">Open the configuration profile and upload intune/kext.xml.</span></span> <span data-ttu-id="3931e-204">Dit bestand is gemaakt in een van de voorgaande secties.</span><span class="sxs-lookup"><span data-stu-id="3931e-204">This file was created in one of the preceding sections.</span></span>

4. <span data-ttu-id="3931e-205">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="3931e-205">Select **OK**.</span></span>

    ![Een configuratie importeren uit een bestand voor aangepast configuratieprofiel](images/mdatp-6-systemconfigurationprofiles.png)

5. <span data-ttu-id="3931e-207">Selecteer **Opdrachten**  >  **beheren.**</span><span class="sxs-lookup"><span data-stu-id="3931e-207">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="3931e-208">Selecteer op **het** tabblad Opnemen de optie Toewijzen aan **alle & alle apparaten.**</span><span class="sxs-lookup"><span data-stu-id="3931e-208">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

6. <span data-ttu-id="3931e-209">Herhaal stap 1 tot en met 5 voor meer profielen.</span><span class="sxs-lookup"><span data-stu-id="3931e-209">Repeat steps 1 through 5 for more profiles.</span></span>

7. <span data-ttu-id="3931e-210">Maak een ander profiel, geef het een naam en upload het intune/WindowsDefenderATPOnboarding.xml bestand.</span><span class="sxs-lookup"><span data-stu-id="3931e-210">Create another profile, give it a name, and upload the intune/WindowsDefenderATPOnboarding.xml file.</span></span>

8. <span data-ttu-id="3931e-211">Download **fulldisk.mobileconfig vanuit** [onze GitHub-opslagplaats](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) en sla deze op **alstcc.xml.**</span><span class="sxs-lookup"><span data-stu-id="3931e-211">Download **fulldisk.mobileconfig** from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and save it as **tcc.xml**.</span></span> <span data-ttu-id="3931e-212">Maak een ander profiel, geef het een naam en upload dit bestand naar het bestand.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span><span class="sxs-lookup"><span data-stu-id="3931e-212">Create another profile, give it any name and upload this file to it.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span></span>

   > [!CAUTION]
   > <span data-ttu-id="3931e-213">macOS 10.15 (Catalina) bevat nieuwe beveiligings- en privacyverbeteringen.</span><span class="sxs-lookup"><span data-stu-id="3931e-213">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="3931e-214">Vanaf deze versie hebben toepassingen standaard geen toegang tot bepaalde locaties op schijf (zoals Documenten, Downloads, Bureaublad, enzovoort) zonder expliciete toestemming.</span><span class="sxs-lookup"><span data-stu-id="3931e-214">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="3931e-215">Bij afwezigheid van deze toestemming kan Microsoft Defender voor Eindpunt uw apparaat niet volledig beveiligen.</span><span class="sxs-lookup"><span data-stu-id="3931e-215">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="3931e-216">Dit configuratieprofiel verleent Volledige schijftoegang aan Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="3931e-216">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3931e-217">Als u Eerder Microsoft Defender voor Eindpunt hebt geconfigureerd via Intune, raden we u aan de implementatie bij te werken met dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="3931e-217">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

9. <span data-ttu-id="3931e-218">Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoorden controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="3931e-218">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="3931e-219">Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3931e-219">The following policy allows the network extension to perform this functionality.</span></span> <span data-ttu-id="3931e-220">Download **netfilter.mobileconfig** vanuit onze [GitHub-opslagplaats,](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)sla deze op als netext.xml en implementeer het met dezelfde stappen als in de vorige secties.</span><span class="sxs-lookup"><span data-stu-id="3931e-220">Download **netfilter.mobileconfig** from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig), save it as netext.xml and deploy it using the same steps as in the previous sections.</span></span> <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. <span data-ttu-id="3931e-221">Als u wilt toestaan dat Microsoft Defender voor Eindpunt op macOS en Microsoft Auto Update meldingen in de gebruikersinterface weergeven op macOS 10.15 (Catalina), downloadt u vanuit onze `notif.mobileconfig` [GitHub-opslagplaats](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) en importeert u deze als een aangepaste payload.</span><span class="sxs-lookup"><span data-stu-id="3931e-221">To allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina), download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) and import it as a custom payload.</span></span> <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. <span data-ttu-id="3931e-222">Selecteer **Opdrachten > beheren.**</span><span class="sxs-lookup"><span data-stu-id="3931e-222">Select **Manage > Assignments**.</span></span>  <span data-ttu-id="3931e-223">Selecteer op **het** tabblad Opnemen de optie Toewijzen aan **alle & alle apparaten.**</span><span class="sxs-lookup"><span data-stu-id="3931e-223">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

<span data-ttu-id="3931e-224">Wanneer de wijzigingen in Intune zijn doorgevoerd naar de geregistreerde apparaten, kunt u deze weergeven onder  >  **Apparaatstatus controleren:**</span><span class="sxs-lookup"><span data-stu-id="3931e-224">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3931e-225">![Weergave van apparaatstatus in monitor](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-225">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="3931e-226">Toepassing publiceren</span><span class="sxs-lookup"><span data-stu-id="3931e-226">Publish application</span></span>

1. <span data-ttu-id="3931e-227">Open in Intune het **blade > Client-apps** beheren.</span><span class="sxs-lookup"><span data-stu-id="3931e-227">In Intune, open the **Manage > Client apps** blade.</span></span> <span data-ttu-id="3931e-228">Selecteer **Apps > Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="3931e-228">Select **Apps > Add**.</span></span>

2. <span data-ttu-id="3931e-229">Selecteer **App type=Other/Line-of-business app**.</span><span class="sxs-lookup"><span data-stu-id="3931e-229">Select **App type=Other/Line-of-business app**.</span></span>

3. <span data-ttu-id="3931e-230">Selecteer **file=wdav.pkg.intunemac**.</span><span class="sxs-lookup"><span data-stu-id="3931e-230">Select **file=wdav.pkg.intunemac**.</span></span> <span data-ttu-id="3931e-231">Selecteer **OK om** te uploaden.</span><span class="sxs-lookup"><span data-stu-id="3931e-231">Select **OK** to upload.</span></span>

4. <span data-ttu-id="3931e-232">Selecteer **Configureren** en voeg de vereiste informatie toe.</span><span class="sxs-lookup"><span data-stu-id="3931e-232">Select **Configure** and add the required information.</span></span>

5. <span data-ttu-id="3931e-233">Gebruik **macOS High Sierra 10.14** als minimaal besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="3931e-233">Use **macOS High Sierra 10.14** as the minimum OS.</span></span>

6. <span data-ttu-id="3931e-234">Stel *App-versie negeren in* op **Ja.**</span><span class="sxs-lookup"><span data-stu-id="3931e-234">Set *Ignore app version* to **Yes**.</span></span> <span data-ttu-id="3931e-235">Andere instellingen kunnen willekeurige waarden zijn.</span><span class="sxs-lookup"><span data-stu-id="3931e-235">Other settings can be any arbitrary value.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="3931e-236">Het *instellen van App-versie negeren* op **Geen** heeft invloed op de mogelijkheid van de toepassing om updates te ontvangen via Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="3931e-236">Setting *Ignore app version* to **No** impacts the ability of the application to receive updates through Microsoft AutoUpdate.</span></span> <span data-ttu-id="3931e-237">Zie [Updates implementeren voor Microsoft Defender voor Eindpunt op macOS](mac-updates.md) voor meer informatie over hoe het product wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3931e-237">See [Deploy updates for Microsoft Defender for Endpoint on macOS](mac-updates.md) for additional information about how the product is updated.</span></span>
    >
    > <span data-ttu-id="3931e-238">Als de versie die door Intune is geüpload lager is dan de versie op het apparaat, wordt de onderste versie geïnstalleerd, wat microsoft Defender voor Eindpunt effectief verlaagt.</span><span class="sxs-lookup"><span data-stu-id="3931e-238">If the version uploaded by Intune is lower than the version on the device, then the lower version will be installed, effectively downgrading Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3931e-239">Dit kan leiden tot een niet-werkende toepassing.</span><span class="sxs-lookup"><span data-stu-id="3931e-239">This could result in a non-functioning application.</span></span> <span data-ttu-id="3931e-240">Zie [Updates implementeren voor Microsoft Defender voor Eindpunt op macOS](mac-updates.md) voor meer informatie over hoe het product wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3931e-240">See [Deploy updates for Microsoft Defender for Endpoint on macOS](mac-updates.md) for additional information about how the product is updated.</span></span> <span data-ttu-id="3931e-241">Als u Microsoft Defender voor Eindpunt hebt geïmplementeerd met *App-versie* negeren ingesteld op **Nee,** wijzigt u deze in **Ja.**</span><span class="sxs-lookup"><span data-stu-id="3931e-241">If you deployed Microsoft Defender for Endpoint with *Ignore app version* set to **No**, please change it to **Yes**.</span></span> <span data-ttu-id="3931e-242">Als Microsoft Defender voor Eindpunt nog steeds niet kan worden geïnstalleerd op een clientapparaat, verwijdert u Microsoft Defender voor Eindpunt en drukt u op het bijgewerkte beleid.</span><span class="sxs-lookup"><span data-stu-id="3931e-242">If Microsoft Defender for Endpoint still cannot be installed on a client device, then uninstall Microsoft Defender for Endpoint and push the updated policy.</span></span>
     
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-243">![Weergave van app-informatie in App-add](images/mdatp-8-intuneappinfo.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-243">![Display of App information in App add](images/mdatp-8-intuneappinfo.png)</span></span>

7. <span data-ttu-id="3931e-244">Selecteer **OK** en **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="3931e-244">Select **OK** and **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-245">![Apparaatstatus weergegeven in het venster Meldingen](images/mdatp-9-intunepkginfo.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-245">![Device status shown in Notifications window](images/mdatp-9-intunepkginfo.png)</span></span>

8. <span data-ttu-id="3931e-246">Het kan even duren voordat u het pakket hebt geüpload.</span><span class="sxs-lookup"><span data-stu-id="3931e-246">It may take a few moments to upload the package.</span></span> <span data-ttu-id="3931e-247">Nadat het klaar is, selecteert u het pakket in de lijst en gaat **u naar Opdrachten en** groep **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="3931e-247">After it's done, select the package from the list and go to **Assignments** and **Add group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-248">![Schermafbeelding van client-apps](images/mdatp-10-clientapps.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-248">![Client apps screenshot](images/mdatp-10-clientapps.png)</span></span>

9. <span data-ttu-id="3931e-249">Het **type Toewijzing wijzigen** in **Vereist.**</span><span class="sxs-lookup"><span data-stu-id="3931e-249">Change **Assignment type** to **Required**.</span></span>

10. <span data-ttu-id="3931e-250">Selecteer **Opgenomen groepen.**</span><span class="sxs-lookup"><span data-stu-id="3931e-250">Select **Included Groups**.</span></span> <span data-ttu-id="3931e-251">Selecteer **Deze app verplicht maken voor alle apparaten=Ja.**</span><span class="sxs-lookup"><span data-stu-id="3931e-251">Select **Make this app required for all devices=Yes**.</span></span> <span data-ttu-id="3931e-252">Selecteer **Groep selecteren om een groep** op te nemen en toe te voegen die de gebruikers bevat die u wilt targeten.</span><span class="sxs-lookup"><span data-stu-id="3931e-252">Select **Select group to include** and add a group that contains the users you want to target.</span></span> <span data-ttu-id="3931e-253">Selecteer **OK** en **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="3931e-253">Select **OK** and **Save**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-254">![Schermafbeelding van intune-opdrachten](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-254">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

11. <span data-ttu-id="3931e-255">Na enige tijd wordt de toepassing gepubliceerd op alle geregistreerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="3931e-255">After some time the application will be published to all enrolled devices.</span></span> <span data-ttu-id="3931e-256">U kunt het weergeven **in** Monitor  >  **Device**, onder **Status apparaat installeren:**</span><span class="sxs-lookup"><span data-stu-id="3931e-256">You can see it listed in **Monitor** > **Device**, under **Device install status**:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-257">![Schermafbeelding van de status van intune-apparaat](images/mdatp-12-deviceinstall.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-257">![Intune device status screenshot](images/mdatp-12-deviceinstall.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="3931e-258">Status van clientapparaat controleren</span><span class="sxs-lookup"><span data-stu-id="3931e-258">Verify client device state</span></span>

1. <span data-ttu-id="3931e-259">Nadat de configuratieprofielen op uw apparaten zijn geïmplementeerd, opent u Systeemvoorkeurenprofielen  >   op uw Mac-apparaat.</span><span class="sxs-lookup"><span data-stu-id="3931e-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    <span data-ttu-id="3931e-260">![Schermopname systeemvoorkeuren](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span><br/>
    <span data-ttu-id="3931e-261">![Schermopname systeemvoorkeurenprofielen](images/mdatp-14-systempreferencesprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-261">![System Preferences Profiles screenshot](images/mdatp-14-systempreferencesprofiles.png)</span></span>

2. <span data-ttu-id="3931e-262">Controleer of de volgende configuratieprofielen aanwezig en geïnstalleerd zijn.</span><span class="sxs-lookup"><span data-stu-id="3931e-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="3931e-263">Het **managementprofiel** moet het Intune-systeemprofiel zijn.</span><span class="sxs-lookup"><span data-stu-id="3931e-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="3931e-264">_Wdav-config_ en _wdav-kext_ zijn systeemconfiguratieprofielen die zijn toegevoegd in Intune: ![ Schermafbeelding profielen](images/mdatp-15-managementprofileconfig.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune: ![Profiles screenshot](images/mdatp-15-managementprofileconfig.png)</span></span>

3. <span data-ttu-id="3931e-265">U ziet ook het Microsoft Defender-pictogram in de rechterbovenhoek:</span><span class="sxs-lookup"><span data-stu-id="3931e-265">You should also see the Microsoft Defender icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3931e-266">![Microsoft Defender-pictogram in schermafbeelding van statusbalk](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="3931e-266">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3931e-267">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="3931e-267">Troubleshooting</span></span>

<span data-ttu-id="3931e-268">Probleem: Er is geen licentie gevonden</span><span class="sxs-lookup"><span data-stu-id="3931e-268">Issue: No license found</span></span>

<span data-ttu-id="3931e-269">Oplossing: Volg de bovenstaande stappen om een apparaatprofiel te maken met WindowsDefenderATPOnboarding.xml</span><span class="sxs-lookup"><span data-stu-id="3931e-269">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="3931e-270">Installatieproblemen met logboekregistratie</span><span class="sxs-lookup"><span data-stu-id="3931e-270">Logging installation issues</span></span>

<span data-ttu-id="3931e-271">Zie Installatieproblemen bij logboekregistratie voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma is gemaakt wanneer er een fout [optreedt.](mac-resources.md#logging-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="3931e-271">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="3931e-272">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="3931e-272">Uninstallation</span></span>

<span data-ttu-id="3931e-273">Zie [Verwijderen voor](mac-resources.md#uninstalling) meer informatie over het verwijderen van Microsoft Defender voor Eindpunt op macOS van clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="3931e-273">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
