---
title: Handmatige implementatie voor Microsoft Defender ATP voor macOS
description: Microsoft Defender ATP voor macOS handmatig installeren vanaf de opdrachtregel.
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187443"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="4b41d-104">Handmatige implementatie voor Microsoft Defender voor Eindpunt voor macOS</span><span class="sxs-lookup"><span data-stu-id="4b41d-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b41d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4b41d-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b41d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b41d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4b41d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b41d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4b41d-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4b41d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4b41d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4b41d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4b41d-110">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt voor macOS handmatig implementeert.</span><span class="sxs-lookup"><span data-stu-id="4b41d-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="4b41d-111">Voor een geslaagde implementatie moet u alle volgende stappen voltooien:</span><span class="sxs-lookup"><span data-stu-id="4b41d-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="4b41d-112">Installatie- en onboarding-pakketten downloaden</span><span class="sxs-lookup"><span data-stu-id="4b41d-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="4b41d-113">Toepassingsinstallatie (macOS 10.15 en oudere versies)</span><span class="sxs-lookup"><span data-stu-id="4b41d-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="4b41d-114">Toepassingsinstallatie (macOS 11 en nieuwere versies)</span><span class="sxs-lookup"><span data-stu-id="4b41d-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="4b41d-115">Clientconfiguratie</span><span class="sxs-lookup"><span data-stu-id="4b41d-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="4b41d-116">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="4b41d-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="4b41d-117">Voordat u aan de slag gaat, bekijkt u de hoofdpagina van Microsoft Defender voor Eindpunt voor [macOS](microsoft-defender-endpoint-mac.md) voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.</span><span class="sxs-lookup"><span data-stu-id="4b41d-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="4b41d-118">Installatie- en onboarding-pakketten downloaden</span><span class="sxs-lookup"><span data-stu-id="4b41d-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="4b41d-119">Download de installatie- en onboarding-pakketten van het Microsoft Defender-beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="4b41d-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="4b41d-120">Ga in het Microsoft Defender-beveiligingscentrum naar **Instellingen > Apparaatbeheer > Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="4b41d-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="4b41d-121">Stel in sectie 1 van de pagina het besturingssysteem in op **macOS** en Implementatiemethode op **Lokaal script.**</span><span class="sxs-lookup"><span data-stu-id="4b41d-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="4b41d-122">Selecteer installatiepakket downloaden in sectie 2 van **de pagina.**</span><span class="sxs-lookup"><span data-stu-id="4b41d-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="4b41d-123">Sla deze op als wdav.pkg in een lokale adreslijst.</span><span class="sxs-lookup"><span data-stu-id="4b41d-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="4b41d-124">Selecteer **onboardingpakket** downloaden in sectie 2 van de pagina.</span><span class="sxs-lookup"><span data-stu-id="4b41d-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="4b41d-125">Sla deze op als WindowsDefenderATPOnboardingPackage.zip in dezelfde adreslijst.</span><span class="sxs-lookup"><span data-stu-id="4b41d-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Schermafbeelding van het Microsoft Defender-beveiligingscentrum](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="4b41d-127">Controleer in een opdrachtprompt of u de twee bestanden hebt.</span><span class="sxs-lookup"><span data-stu-id="4b41d-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="4b41d-128">Toepassingsinstallatie (macOS 10.15 en oudere versies)</span><span class="sxs-lookup"><span data-stu-id="4b41d-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="4b41d-129">Als u dit proces wilt voltooien, moet u beheerdersbevoegdheden hebben op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="4b41d-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="4b41d-130">Ga naar de gedownloade wdav.pkg in Finder en open het.</span><span class="sxs-lookup"><span data-stu-id="4b41d-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Schermafbeelding van app-installatie1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="4b41d-132">Selecteer **Doorgaan,** ga akkoord met de licentievoorwaarden en voer het wachtwoord in wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="4b41d-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Schermafbeelding van app-installatie2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="4b41d-134">U wordt gevraagd om toe te staan dat een stuurprogramma van Microsoft wordt geïnstalleerd ('Systeemextensie geblokkeerd' of 'Installatie is in de wacht gezet' of beide.</span><span class="sxs-lookup"><span data-stu-id="4b41d-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="4b41d-135">Het stuurprogramma moet zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="4b41d-135">The driver must be allowed to be installed.</span></span>

   ![Schermafbeelding van app-installatie](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="4b41d-137">Selecteer **Beveiligingsvoorkeuren openen** **of Systeemvoorkeuren openen > beveiliging & privacy**.</span><span class="sxs-lookup"><span data-stu-id="4b41d-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="4b41d-138">Selecteer **Toestaan:**</span><span class="sxs-lookup"><span data-stu-id="4b41d-138">Select **Allow**:</span></span>

    ![Schermopname van het beveiligings- en privacyvenster](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="4b41d-140">De installatie gaat verder.</span><span class="sxs-lookup"><span data-stu-id="4b41d-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="4b41d-141">Als u Toestaan niet **selecteert,** gaat de installatie na 5 minuten verder.</span><span class="sxs-lookup"><span data-stu-id="4b41d-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="4b41d-142">Microsoft Defender voor Eindpunt wordt geladen, maar sommige functies, zoals realtimebeveiliging, worden uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4b41d-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="4b41d-143">Zie [Problemen met kernelextensie oplossen](mac-support-kext.md) voor informatie over hoe u dit kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="4b41d-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="4b41d-144">macOS kan een verzoek indienen om het apparaat opnieuw op te starten bij de eerste installatie van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4b41d-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4b41d-145">Realtimebeveiliging is pas beschikbaar als het apparaat opnieuw is opgestart.</span><span class="sxs-lookup"><span data-stu-id="4b41d-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="4b41d-146">Toepassingsinstallatie (macOS 11 en nieuwere versies)</span><span class="sxs-lookup"><span data-stu-id="4b41d-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="4b41d-147">Als u dit proces wilt voltooien, moet u beheerdersbevoegdheden hebben op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="4b41d-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="4b41d-148">Ga naar de gedownloade wdav.pkg in Finder en open het.</span><span class="sxs-lookup"><span data-stu-id="4b41d-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Schermafbeelding van app-installatie](images/big-sur-install-1.png)

2. <span data-ttu-id="4b41d-150">Selecteer **Doorgaan,** ga akkoord met de licentievoorwaarden en voer het wachtwoord in wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="4b41d-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="4b41d-151">Aan het einde van het installatieproces wordt u gepromoveerd om de systeemextensies goed te keuren die door het product worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4b41d-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="4b41d-152">Selecteer **Beveiligingsvoorkeuren openen.**</span><span class="sxs-lookup"><span data-stu-id="4b41d-152">Select **Open Security Preferences**.</span></span>

    ![Goedkeuring van systeemextensie](images/big-sur-install-2.png)

4. <span data-ttu-id="4b41d-154">Selecteer in **het & Privacy** van beveiliging de optie **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="4b41d-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Beveiligingsvoorkeuren voor systeemextensie1](images/big-sur-install-3.png)

5. <span data-ttu-id="4b41d-156">Herhaal stap 3 & 4 voor alle systeemextensies die zijn gedistribueerd met Microsoft Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="4b41d-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="4b41d-157">Als onderdeel van de mogelijkheden voor endpointdetectie en -reactie controleert Microsoft Defender voor Endpoint voor Mac socketverkeer en rapporteert deze informatie aan de microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="4b41d-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="4b41d-158">Wanneer u wordt gevraagd Microsoft Defender te verlenen voor eindpuntmachtigingen voor het filteren van netwerkverkeer, selecteert u **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="4b41d-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Beveiligingsvoorkeuren voor systeemextensie2](images/big-sur-install-4.png)

7. <span data-ttu-id="4b41d-160">Open **Systeemvoorkeuren**& privacy en ga naar het tabblad Privacy. Verleen volledige schijftoegangsmachtigingen aan Microsoft Defender  >   **ATP** en Microsoft **Defender ATP-eindpuntbeveiligingsextensie**.  </span><span class="sxs-lookup"><span data-stu-id="4b41d-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Volledige schijftoegang](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="4b41d-162">Clientconfiguratie</span><span class="sxs-lookup"><span data-stu-id="4b41d-162">Client configuration</span></span>

1. <span data-ttu-id="4b41d-163">Kopieer wdav.pkg en MicrosoftDefenderATPOnboardingMacOs.py naar het apparaat waar u Microsoft Defender voor Eindpunt voor macOS implementeert.</span><span class="sxs-lookup"><span data-stu-id="4b41d-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="4b41d-164">Het clientapparaat is niet gekoppeld aan orgId.</span><span class="sxs-lookup"><span data-stu-id="4b41d-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="4b41d-165">Houd er rekening mee *dat het orgId-kenmerk* leeg is.</span><span class="sxs-lookup"><span data-stu-id="4b41d-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="4b41d-166">Voer het Python-script uit om het configuratiebestand te installeren:</span><span class="sxs-lookup"><span data-stu-id="4b41d-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="4b41d-167">Controleer of het apparaat nu is gekoppeld aan uw organisatie en rapporteer een geldige *orgId:*</span><span class="sxs-lookup"><span data-stu-id="4b41d-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="4b41d-168">Na de installatie ziet u het Microsoft Defender-pictogram in de statusbalk van macOS in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="4b41d-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![Microsoft Defender-pictogram in schermafbeelding van statusbalk](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="4b41d-170">Volledige schijftoegang toestaan</span><span class="sxs-lookup"><span data-stu-id="4b41d-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="4b41d-171">macOS 10.15 (Catalina) bevat nieuwe beveiligings- en privacyverbeteringen.</span><span class="sxs-lookup"><span data-stu-id="4b41d-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="4b41d-172">Vanaf deze versie hebben toepassingen standaard geen toegang tot bepaalde locaties op schijf (zoals Documenten, Downloads, Bureaublad, enzovoort) zonder expliciete toestemming.</span><span class="sxs-lookup"><span data-stu-id="4b41d-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="4b41d-173">Bij afwezigheid van deze toestemming kan Microsoft Defender voor Eindpunt uw apparaat niet volledig beveiligen.</span><span class="sxs-lookup"><span data-stu-id="4b41d-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="4b41d-174">Als u toestemming wilt verlenen, opent u Systeemvoorkeuren -> Beveiliging & Privacy -> Privacy -> Volledige schijftoegang.</span><span class="sxs-lookup"><span data-stu-id="4b41d-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="4b41d-175">Klik op het vergrendelingspictogram om wijzigingen aan te brengen (onder aan het dialoogvenster).</span><span class="sxs-lookup"><span data-stu-id="4b41d-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="4b41d-176">Selecteer Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4b41d-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="4b41d-177">Installatieproblemen met logboekregistratie</span><span class="sxs-lookup"><span data-stu-id="4b41d-177">Logging installation issues</span></span>

<span data-ttu-id="4b41d-178">Zie [Installatieproblemen registreren](mac-resources.md#logging-installation-issues) voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma wordt gemaakt wanneer er een fout optreedt.</span><span class="sxs-lookup"><span data-stu-id="4b41d-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="4b41d-179">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="4b41d-179">Uninstallation</span></span>

<span data-ttu-id="4b41d-180">Zie [Verwijderen voor](mac-resources.md#uninstalling) meer informatie over het verwijderen van Microsoft Defender voor Eindpunt voor macOS van clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="4b41d-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
