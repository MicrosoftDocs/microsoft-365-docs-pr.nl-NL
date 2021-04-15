---
title: Microsoft Defender ATP voor macOS-beleid instellen in Jamf Pro
description: Meer informatie over het instellen van microsoft Defender ATP voor macOS-beleid in Jamf Pro
keywords: beleid, microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 79f5837ae6bae6e6a9d952d90605f4cf7b31262e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765129"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="65974-104">Microsoft Defender voor Eindpunt instellen voor macOS-beleid in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="65974-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="65974-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="65974-105">**Applies to:**</span></span>

- [<span data-ttu-id="65974-106">Defender voor Eindpunt op Mac</span><span class="sxs-lookup"><span data-stu-id="65974-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="65974-107">Deze pagina begeleidt u bij de stappen die u moet ondernemen om macOS-beleid in Te stellen in Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="65974-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="65974-108">U moet de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="65974-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="65974-109">Het Onboarding-pakket voor Microsoft Defender voor eindpunten kopen</span><span class="sxs-lookup"><span data-stu-id="65974-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="65974-110">Een configuratieprofiel maken in Jamf Pro met behulp van het onboarding-pakket</span><span class="sxs-lookup"><span data-stu-id="65974-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="65974-111">Microsoft Defender configureren voor eindpuntinstellingen</span><span class="sxs-lookup"><span data-stu-id="65974-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="65974-112">Instellingen voor meldingen van Microsoft Defender voor eindpunt configureren</span><span class="sxs-lookup"><span data-stu-id="65974-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="65974-113">Microsoft AutoUpdate configureren (MAU)</span><span class="sxs-lookup"><span data-stu-id="65974-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="65974-114">Volledige schijftoegang verlenen aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="65974-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="65974-115">Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="65974-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="65974-116">Systeemextensies goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="65974-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="65974-117">Netwerkextensie configureren</span><span class="sxs-lookup"><span data-stu-id="65974-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="65974-118">Scans plannen met Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="65974-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="65974-119">Microsoft Defender voor eindpunt implementeren in macOS</span><span class="sxs-lookup"><span data-stu-id="65974-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="65974-120">Stap 1: Het Onboarding-pakket voor Microsoft Defender voor eindpunten kopen</span><span class="sxs-lookup"><span data-stu-id="65974-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="65974-121">Ga [in het Microsoft Defender-beveiligingscentrum](https://securitycenter.microsoft.com )naar Instellingen > **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="65974-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="65974-122">Selecteer macOS als besturingssysteem en Mobile Device Management / Microsoft Intune als implementatiemethode.</span><span class="sxs-lookup"><span data-stu-id="65974-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Afbeelding van Microsoft Defender-beveiligingscentrum](images/onboarding-macos.png)

3. <span data-ttu-id="65974-124">Selecteer **Onboarding-pakket downloaden** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="65974-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="65974-125">Extract `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="65974-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="65974-126">Kopieer het bestand naar de gewenste locatie.</span><span class="sxs-lookup"><span data-stu-id="65974-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="65974-127">Bijvoorbeeld. `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`</span><span class="sxs-lookup"><span data-stu-id="65974-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="65974-128">Stap 2: Een configuratieprofiel maken in Jamf Pro met behulp van het onboarding-pakket</span><span class="sxs-lookup"><span data-stu-id="65974-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="65974-129">Zoek het bestand `WindowsDefenderATPOnboarding.plist` in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="65974-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Afbeelding van WindowsDefenderATPOnboarding-bestand](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="65974-131">Selecteer nieuw in het dashboard van Jamf **Pro.**</span><span class="sxs-lookup"><span data-stu-id="65974-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Afbeelding van het maken van een nieuw Jamf Pro-dashboard](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="65974-133">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-133">Enter the following details:</span></span>

   <span data-ttu-id="65974-134">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-134">**General**</span></span>
   - <span data-ttu-id="65974-135">Naam: MDATP-onboarding voor macOS</span><span class="sxs-lookup"><span data-stu-id="65974-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="65974-136">Beschrijving: MDATP EDR onboarding voor macOS</span><span class="sxs-lookup"><span data-stu-id="65974-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="65974-137">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="65974-137">Category: None</span></span>
   - <span data-ttu-id="65974-138">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="65974-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="65974-139">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="65974-139">Level: Computer Level</span></span>

4. <span data-ttu-id="65974-140">Selecteer **configureren & aangepaste instellingen** in **Toepassing.**</span><span class="sxs-lookup"><span data-stu-id="65974-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Afbeelding van de configureren app en aangepaste instellingen](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="65974-142">Selecteer **Bestand uploaden (PLIST-bestand)** en voer in **Voorkeursdomein** in: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="65974-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Afbeelding van het uploadbestand van de jamfpro-plist](images/jamfpro-plist-upload.png)

    ![Afbeelding van bestandsbestandsbestand uploaden Lijstbestand](images/jamfpro-plist-file.png)

7. <span data-ttu-id="65974-145">Selecteer **Openen** en selecteer het onboarding-bestand.</span><span class="sxs-lookup"><span data-stu-id="65974-145">Select **Open** and select the onboarding file.</span></span>

    ![Afbeelding van onboarding-bestand](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="65974-147">Selecteer **Uploaden.**</span><span class="sxs-lookup"><span data-stu-id="65974-147">Select **Upload**.</span></span> 

    ![Afbeelding van het uploaden van een plistbestand](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="65974-149">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-149">Select the **Scope** tab.</span></span>

    ![Afbeelding van het tabblad Bereik](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="65974-151">Selecteer de doelcomputers.</span><span class="sxs-lookup"><span data-stu-id="65974-151">Select the target computers.</span></span>

    ![Afbeelding van doelcomputers](images/jamfpro-target-computer.png)

    ![Afbeelding van doelen](images/jamfpro-targets.png) 

11. <span data-ttu-id="65974-154">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-154">Select **Save**.</span></span>

    ![Afbeelding van implementatiedoelcomputers](images/jamfpro-deployment-target.png)

    ![Afbeelding van geselecteerde doelcomputers](images/jamfpro-target-selected.png)

12. <span data-ttu-id="65974-157">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-157">Select **Done**.</span></span>

    ![Afbeelding van doelgroepcomputers](images/jamfpro-target-group.png)

    ![Lijst met configuratieprofielen](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="65974-160">Stap 3: Microsoft Defender configureren voor eindpuntinstellingen</span><span class="sxs-lookup"><span data-stu-id="65974-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="65974-161">Gebruik de volgende configuratie-instellingen voor Microsoft Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="65974-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="65974-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="65974-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="65974-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="65974-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="65974-164">Als u van plan bent een AV van derden voor macOS uit te voeren, is deze standaard niet `true` ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="65974-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="65974-165">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="65974-165">exclusions</span></span>
    - <span data-ttu-id="65974-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="65974-166">excludedPath</span></span>
    - <span data-ttu-id="65974-167">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="65974-167">excludedFileExtension</span></span>
    - <span data-ttu-id="65974-168">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="65974-168">excludedFileName</span></span>
    - <span data-ttu-id="65974-169">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="65974-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="65974-170">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="65974-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="65974-171">EICAR is opgenomen in het voorbeeld, als u een proof-of-concept doormaakt, verwijdert u deze vooral als u EICAR test.</span><span class="sxs-lookup"><span data-stu-id="65974-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="65974-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="65974-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="65974-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="65974-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="65974-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="65974-174">archive_bomb</span></span>
    - <span data-ttu-id="65974-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="65974-175">cloudService</span></span>
    - <span data-ttu-id="65974-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="65974-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="65974-177">tags</span><span class="sxs-lookup"><span data-stu-id="65974-177">tags</span></span>
    - <span data-ttu-id="65974-178">StatusMenuIcon verbergen</span><span class="sxs-lookup"><span data-stu-id="65974-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="65974-179">Zie Eigenschappenlijst voor [configuratieprofiel Van Jamf voor meer informatie.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="65974-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="65974-180">Sla het bestand op als `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="65974-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="65974-181">Selecteer algemeen in het dashboard van Jamf **Pro.**</span><span class="sxs-lookup"><span data-stu-id="65974-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Afbeelding van het nieuwe Jamf Pro-dashboard](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="65974-183">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-183">Enter the following details:</span></span>

    <span data-ttu-id="65974-184">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-184">**General**</span></span>
    
    - <span data-ttu-id="65974-185">Naam: MDATP MDAV-configuratie-instellingen</span><span class="sxs-lookup"><span data-stu-id="65974-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="65974-186">Beschrijving:\<blank\></span><span class="sxs-lookup"><span data-stu-id="65974-186">Description:\<blank\></span></span>
    - <span data-ttu-id="65974-187">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-187">Category: None (default)</span></span>
    - <span data-ttu-id="65974-188">Distributiemethode: Automatisch installeren(standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="65974-189">Niveau: Computerniveau(standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-189">Level: Computer Level(default)</span></span>

    ![Afbeelding van MDATP MDAV-configuratie-instellingen](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="65974-191">Selecteer **configureren & aangepaste instellingen** in **Toepassing.**</span><span class="sxs-lookup"><span data-stu-id="65974-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Afbeelding van app en aangepaste instellingen](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="65974-193">Selecteer **Bestand uploaden (PLIST-bestand)**.</span><span class="sxs-lookup"><span data-stu-id="65974-193">Select **Upload File (PLIST file)**.</span></span>

    ![Afbeelding van configuratie-instellingen plistbestand](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="65974-195">Typ **in Het domein** Voorkeuren en selecteer vervolgens `com.microsoft.wdav` **PLIST-bestand uploaden.**</span><span class="sxs-lookup"><span data-stu-id="65974-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Afbeelding van het domein configuratie-instellingenvoorkeuren](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="65974-197">Selecteer **Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="65974-197">Select **Choose File**.</span></span>

    ![Afbeelding van configuratie-instellingen kies bestand](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="65974-199">Selecteer de **MDATP_MDAV_configuration_settings.plist** en selecteer **Openen.**</span><span class="sxs-lookup"><span data-stu-id="65974-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Afbeelding van configuratie-instellingen voor mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="65974-201">Selecteer **Uploaden.**</span><span class="sxs-lookup"><span data-stu-id="65974-201">Select **Upload**.</span></span>

    ![Afbeelding van het uploaden van configuratie-instellingen](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Afbeelding van de uploadafbeelding van configuratie-instellingen](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="65974-204">Als u het Intune-bestand uploadt, krijgt u de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="65974-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="65974-205">![Afbeelding van configuratie-instellingen intune-bestand uploaden](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="65974-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="65974-206">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-206">Select **Save**.</span></span> 

    ![Afbeelding van configuratie-instellingen Afbeelding opslaan](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="65974-208">Het bestand wordt geüpload.</span><span class="sxs-lookup"><span data-stu-id="65974-208">The file is uploaded.</span></span>

    ![Afbeelding van het bestand met configuratie-instellingen dat is geüpload](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Afbeelding van het bestand met configuratie-instellingen dat is geüpload](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="65974-211">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-211">Select the **Scope** tab.</span></span>

    ![Afbeelding van het bereik van configuratie-instellingen](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="65974-213">Selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="65974-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="65974-214">Selecteer **Toevoegen** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="65974-214">Select **Add**, then select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingen addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Afbeelding van configuratie-instellingen opslaan add](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="65974-217">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-217">Select **Done**.</span></span> <span data-ttu-id="65974-218">U ziet het nieuwe **configuratieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="65974-218">You'll see the new **Configuration profile**.</span></span>

    ![Afbeelding van configuratie-instellingen config profielafbeelding](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="65974-220">Stap 4: Instellingen voor meldingen configureren</span><span class="sxs-lookup"><span data-stu-id="65974-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="65974-221">Deze stappen zijn van toepassing op macOS 10.15 (Catalina) of hoger.</span><span class="sxs-lookup"><span data-stu-id="65974-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="65974-222">Selecteer in het dashboard Van Jamf Pro de optie **Computers** en vervolgens **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="65974-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="65974-223">Klik **op Nieuw** en voer de volgende details in voor **Opties:**</span><span class="sxs-lookup"><span data-stu-id="65974-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="65974-224">Tabblad **Algemeen**:</span><span class="sxs-lookup"><span data-stu-id="65974-224">Tab **General**:</span></span> 
        - <span data-ttu-id="65974-225">**Naam**: MDATP MDAV-meldingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="65974-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="65974-226">**Beschrijving**: macOS 10.15 (Catalina) of hoger</span><span class="sxs-lookup"><span data-stu-id="65974-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="65974-227">**Categorie:** Geen *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="65974-228">**Distributiemethode:** Automatisch installeren *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="65974-229">**Niveau:** Computerniveau *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-229">**Level**: Computer Level *(default)*</span></span>

        ![Afbeelding van configuratieprofielinstellingen mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="65974-231">**Tabmeldingen,** klik **op Toevoegen** en voer de volgende waarden in:</span><span class="sxs-lookup"><span data-stu-id="65974-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="65974-232">**Bundel-id:**`com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="65974-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="65974-233">**Kritieke waarschuwingen:** Klik op **Uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="65974-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="65974-234">**Meldingen:** Klik op **Inschakelen**</span><span class="sxs-lookup"><span data-stu-id="65974-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="65974-235">**Type bannerwaarschuwing:** Selecteer **Opnemen** en **Tijdelijk** *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="65974-236">**Meldingen op vergrendelingsscherm**: Klik op **Verbergen**</span><span class="sxs-lookup"><span data-stu-id="65974-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="65974-237">**Meldingen in het systeemcentrum:** klik op **Weergeven**</span><span class="sxs-lookup"><span data-stu-id="65974-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="65974-238">**Pictogram badge-app:** klik op **Weergeven**</span><span class="sxs-lookup"><span data-stu-id="65974-238">**Badge app icon**: Click **Display**</span></span>

        ![Afbeelding van configuratie-instellingen mdatpmdav-meldingenvak](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="65974-240">**TabMeldingen**, klik **nog een** keer op Toevoegen, schuif omlaag naar Nieuwe instellingen **voor meldingen**</span><span class="sxs-lookup"><span data-stu-id="65974-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="65974-241">**Bundel-id:**`com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="65974-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="65974-242">De rest van de instellingen configureren op dezelfde waarden als hierboven</span><span class="sxs-lookup"><span data-stu-id="65974-242">Configure the rest of the settings to the same values as above</span></span>

        ![Afbeelding van configuratie-instellingen mdatpmdav-meldingen mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="65974-244">Houd er rekening mee dat u nu twee 'tabellen' met meldingsconfiguraties hebt, een voor **Bundel-id: com.microsoft.wdav.tray** en een voor **Bundel-id: com.microsoft.autoupdate2**.</span><span class="sxs-lookup"><span data-stu-id="65974-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="65974-245">Hoewel u waarschuwingsinstellingen kunt configureren op basis van uw vereisten,  moeten bundel-1D's exact hetzelfde zijn als eerder beschreven en moet de schakelknop Opnemen zijn **aan** voor **meldingen.**</span><span class="sxs-lookup"><span data-stu-id="65974-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="65974-246">Selecteer het **tabblad** Bereik en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![Afbeelding van het bereik van configuratie-instellingen](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="65974-248">Selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="65974-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="65974-249">Selecteer **Toevoegen** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="65974-249">Select **Add**, then select **Save**.</span></span>
    
    ![Afbeelding van configuratie-instellingen contoso machine grp opslaan](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Afbeelding van configuratie-instellingen toevoegen opslaan](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="65974-252">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-252">Select **Done**.</span></span> <span data-ttu-id="65974-253">U ziet het nieuwe **configuratieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="65974-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="65974-254">![Afbeelding van configuratie-instelling klaar img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="65974-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="65974-255">Stap 5: Microsoft AutoUpdate configureren (MAU)</span><span class="sxs-lookup"><span data-stu-id="65974-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="65974-256">Gebruik de volgende configuratie-instellingen voor Microsoft Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="65974-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="65974-257">Sla het op als `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="65974-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="65974-258">Selecteer algemeen in het dashboard van Jamf **Pro.**</span><span class="sxs-lookup"><span data-stu-id="65974-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Afbeelding van configuratie-instelling algemene afbeelding](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="65974-260">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-260">Enter the following details:</span></span>

    <span data-ttu-id="65974-261">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-261">**General**</span></span> 
    
    - <span data-ttu-id="65974-262">Naam: MDATP MDAV MAU-instellingen</span><span class="sxs-lookup"><span data-stu-id="65974-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="65974-263">Beschrijving: Microsoft AutoUpdate-instellingen voor MDATP voor macOS</span><span class="sxs-lookup"><span data-stu-id="65974-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="65974-264">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-264">Category: None (default)</span></span>
    - <span data-ttu-id="65974-265">Distributiemethode: Automatisch installeren(standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="65974-266">Niveau: Computerniveau(standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="65974-267">Selecteer **configureren & aangepaste instellingen** in **Toepassing.**</span><span class="sxs-lookup"><span data-stu-id="65974-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Afbeelding van de configuratie-app en aangepaste instellingen](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="65974-269">Selecteer **Bestand uploaden (PLIST-bestand)**.</span><span class="sxs-lookup"><span data-stu-id="65974-269">Select **Upload File (PLIST file)**.</span></span>

    ![Afbeelding van configuratie-instelling plist](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="65974-271">Selecteer **in Voorkeursdomein** enter: `com.microsoft.autoupdate2` en selecteer vervolgens **PLIST-bestand uploaden.**</span><span class="sxs-lookup"><span data-stu-id="65974-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Afbeelding van configuratie-instelling pref-domein](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="65974-273">Selecteer **Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="65974-273">Select **Choose File**.</span></span>

    ![Afbeelding van configuratie-instelling kiesbestand](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="65974-275">Selecteer **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="65974-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Afbeelding van configuratie-instelling mdatpmdavmau-instellingen](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="65974-277">Selecteer **Uploaden.**</span><span class="sxs-lookup"><span data-stu-id="65974-277">Select **Upload**.</span></span>
    <span data-ttu-id="65974-278">![Afbeelding van configuratie-instellinglimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="65974-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Afbeelding van configuratie-uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="65974-280">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-280">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instelling saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="65974-282">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-282">Select the **Scope** tab.</span></span>
   
     ![Afbeelding van configuratie-instelling scopetab](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="65974-284">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="65974-284">Select **Add**.</span></span>
    
    ![Afbeelding van configuratie-instelling addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Afbeelding van configuratie-instelling addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Afbeelding van configuratie-instelling addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="65974-288">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-288">Select **Done**.</span></span>
    
    ![Afbeelding van configuratie-instelling doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="65974-290">Stap 6: Volledige schijftoegang verlenen aan Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="65974-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="65974-291">Selecteer configuratieprofielen in het Dashboard van Jamf **Pro.**</span><span class="sxs-lookup"><span data-stu-id="65974-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Afbeelding van configuratie-instelling configprofiel](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="65974-293">Selecteer **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="65974-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="65974-294">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-294">Enter the following details:</span></span>

    <span data-ttu-id="65974-295">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-295">**General**</span></span> 
    - <span data-ttu-id="65974-296">Naam: MDATP MDAV - Volledige schijftoegang verlenen aan EDR en AV</span><span class="sxs-lookup"><span data-stu-id="65974-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="65974-297">Beschrijving: In macOS Catalina of nieuwer, het nieuwe beleid voor privacyvoorkeuren</span><span class="sxs-lookup"><span data-stu-id="65974-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="65974-298">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="65974-298">Category: None</span></span>
    - <span data-ttu-id="65974-299">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="65974-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="65974-300">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="65974-300">Level: Computer level</span></span>


    ![Afbeelding van configuratie-instelling algemeen](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="65974-302">Selecteer **in Beleidsbesturingselement Privacyvoorkeuren configureren** **de optie Configureren.**</span><span class="sxs-lookup"><span data-stu-id="65974-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Afbeelding van configuratie-privacybeleid](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="65974-304">Voer **in Beleidsbeheer privacyvoorkeuren** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="65974-305">Id: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="65974-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="65974-306">Id-type: bundel-id</span><span class="sxs-lookup"><span data-stu-id="65974-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="65974-307">Codevereiste: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="65974-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Afbeelding van configuratie-instelling privacyvoorkeursbeleidsgegevens](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="65974-309">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-309">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instelling Systeembeleid alle bestanden toevoegen](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="65974-311">Onder App of service: Instellen op **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="65974-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="65974-312">Onder 'toegang': Instellen op **Toestaan**</span><span class="sxs-lookup"><span data-stu-id="65974-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="65974-313">Selecteer **Opslaan** (niet de optie rechtsonder).</span><span class="sxs-lookup"><span data-stu-id="65974-313">Select **Save** (not the one at the bottom right).</span></span>

    ![Afbeelding van configuratie-instelling sla afbeeldingen op](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="65974-315">Klik op `+` het bord naast App Access **om** een nieuw item toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="65974-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Afbeelding van de configuratie-instelling app-toegang](images/tcc-add-entry.png)

9. <span data-ttu-id="65974-317">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-317">Enter the following details:</span></span>

    - <span data-ttu-id="65974-318">Id: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="65974-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="65974-319">Id-type: bundel-id</span><span class="sxs-lookup"><span data-stu-id="65974-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="65974-320">Codevereiste: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="65974-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="65974-321">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-321">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instelling tCC epsext-invoer](images/tcc-epsext-entry.png)

    - <span data-ttu-id="65974-323">Onder App of service: Instellen op **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="65974-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="65974-324">Onder 'toegang': Instellen op **Toestaan**</span><span class="sxs-lookup"><span data-stu-id="65974-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="65974-325">Selecteer **Opslaan** (niet de optie rechtsonder).</span><span class="sxs-lookup"><span data-stu-id="65974-325">Select **Save** (not the one at the bottom right).</span></span>

    ![Afbeelding van configuratie-instelling tCC epsext afbeelding2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="65974-327">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-327">Select the **Scope** tab.</span></span>

    ![Afbeelding van het configuratiebereik](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="65974-329">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-329">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instellings-addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="65974-331">Selecteer **Computergroepen >** **onder Groepsnaam** > **selecteer Contoso's MachineGroup.**</span><span class="sxs-lookup"><span data-stu-id="65974-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Afbeelding van configuratie-instelling contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="65974-333">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="65974-333">Select **Add**.</span></span> 

16. <span data-ttu-id="65974-334">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="65974-335">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-335">Select **Done**.</span></span>
    
    ![Afbeelding van configuratie-instelling donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Afbeelding van configuratie-instelling donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="65974-338">U kunt ook [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf Pro| Methode 2: Een configuratieprofiel uploaden naar Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="65974-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="65974-339">Stap 7: Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="65974-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="65974-340">Apple Silicon (M1) apparaten bieden geen ondersteuning voor KEXT.</span><span class="sxs-lookup"><span data-stu-id="65974-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="65974-341">De installatie van een configuratieprofiel met KEXT-beleid mislukt op deze apparaten.</span><span class="sxs-lookup"><span data-stu-id="65974-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="65974-342">Selecteer in **de configuratieprofielen** **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="65974-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="65974-344">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-344">Enter the following details:</span></span>

    <span data-ttu-id="65974-345">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-345">**General**</span></span> 
    
    - <span data-ttu-id="65974-346">Naam: MDATP MDAV Kernel Extension</span><span class="sxs-lookup"><span data-stu-id="65974-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="65974-347">Beschrijving: MDATP kernel extension (kext)</span><span class="sxs-lookup"><span data-stu-id="65974-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="65974-348">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="65974-348">Category: None</span></span>
    - <span data-ttu-id="65974-349">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="65974-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="65974-350">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="65974-350">Level: Computer Level</span></span>

    ![Afbeelding van configuratie-instellingen mdatpmdav-kernel](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="65974-352">Selecteer **configureren goedgekeurde kernelextensies** **configureren.**</span><span class="sxs-lookup"><span data-stu-id="65974-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Afbeelding van configuratie-instellingen goedgekeurd kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="65974-354">Voer **in Goedgekeurde kernelextensies** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="65974-355">Weergavenaam: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="65974-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="65974-356">Team-id: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="65974-356">Team ID: UBF8T346G9</span></span>

    ![Afbeelding van de uitbreiding configuratie-instellingen appr kernel](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="65974-358">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-358">Select the **Scope** tab.</span></span>

    ![Afbeelding van het tabblad Configuratie-instellingenbereik img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="65974-360">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="65974-361">Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="65974-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="65974-362">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-362">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instellingen om afbeeldingen toe te voegen](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="65974-364">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-364">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingen saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="65974-366">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-366">Select **Done**.</span></span>

    ![Afbeelding van configuratie-instellingen doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="65974-368">U kunt ook [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf Pro| Methode 2: Een configuratieprofiel uploaden naar Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="65974-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="65974-369">Stap 8: Systeemextensies goedkeuren voor Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="65974-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="65974-370">Selecteer in **de configuratieprofielen** **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="65974-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="65974-372">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-372">Enter the following details:</span></span>

    <span data-ttu-id="65974-373">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-373">**General**</span></span>
    
    - <span data-ttu-id="65974-374">Naam: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="65974-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="65974-375">Beschrijving: MDATP-systeemextensies</span><span class="sxs-lookup"><span data-stu-id="65974-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="65974-376">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="65974-376">Category: None</span></span>
    - <span data-ttu-id="65974-377">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="65974-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="65974-378">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="65974-378">Level: Computer Level</span></span>

    ![Afbeelding van configuratie-instellingen sysext nieuwe prof](images/sysext-new-profile.png)

3. <span data-ttu-id="65974-380">Selecteer **configureren in Systeemextensies.** </span><span class="sxs-lookup"><span data-stu-id="65974-380">In **System Extensions** select **Configure**.</span></span>

   ![Afbeelding van configuratie-instellingen sysext config](images/sysext-configure.png)

4. <span data-ttu-id="65974-382">Voer **in Systeemextensies** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="65974-383">Weergavenaam: Microsoft Corp. Systeemextensies</span><span class="sxs-lookup"><span data-stu-id="65974-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="65974-384">Systeemextensietypen: Toegestane systeemextensies</span><span class="sxs-lookup"><span data-stu-id="65974-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="65974-385">Teamaanduiding: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="65974-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="65974-386">Toegestane systeemextensies:</span><span class="sxs-lookup"><span data-stu-id="65974-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="65974-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="65974-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="65974-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="65974-388">**com.microsoft.wdav.netext**</span></span>

    ![Afbeelding van configuratie-instellingen sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="65974-390">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-390">Select the **Scope** tab.</span></span>

    ![Afbeelding van het bereik van configuratie-instellingen](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="65974-392">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="65974-393">Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="65974-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="65974-394">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-394">Select **+ Add**.</span></span>

   ![Afbeelding van addima configuratie-instellingen](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="65974-396">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-396">Select **Save**.</span></span>

   ![Afbeelding van sysext-bereik configuratie-instellingen](images/sysext-scope.png)

10. <span data-ttu-id="65974-398">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-398">Select **Done**.</span></span>

    ![Afbeelding van configuratie-instellingen sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="65974-400">Stap 9: Netwerkextensie configureren</span><span class="sxs-lookup"><span data-stu-id="65974-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="65974-401">Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoorden controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="65974-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="65974-402">Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="65974-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="65974-403">Deze stappen zijn van toepassing op macOS 10.15 (Catalina) of hoger.</span><span class="sxs-lookup"><span data-stu-id="65974-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="65974-404">Selecteer in het dashboard Van Jamf Pro de optie **Computers** en vervolgens **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="65974-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="65974-405">Klik **op Nieuw** en voer de volgende details in voor **Opties:**</span><span class="sxs-lookup"><span data-stu-id="65974-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="65974-406">Tabblad **Algemeen**:</span><span class="sxs-lookup"><span data-stu-id="65974-406">Tab **General**:</span></span> 
        - <span data-ttu-id="65974-407">**Naam**: Microsoft Defender ATP Network Extension</span><span class="sxs-lookup"><span data-stu-id="65974-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="65974-408">**Beschrijving**: macOS 10.15 (Catalina) of hoger</span><span class="sxs-lookup"><span data-stu-id="65974-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="65974-409">**Categorie:** Geen *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="65974-410">**Distributiemethode:** Automatisch installeren *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="65974-411">**Niveau:** Computerniveau *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="65974-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="65974-412">**Tab-inhoudsfilter:**</span><span class="sxs-lookup"><span data-stu-id="65974-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="65974-413">**Filternaam:** Microsoft Defender ATP-inhoudsfilter</span><span class="sxs-lookup"><span data-stu-id="65974-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="65974-414">**Id**: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="65974-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="65974-415">Serviceadres , **Organisatie**, **Gebruikersnaam**, **Wachtwoord**, **Certificaat** leeg laten (**Opnemen** is *niet* geselecteerd) </span><span class="sxs-lookup"><span data-stu-id="65974-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="65974-416">**Filterorder**: Inspector</span><span class="sxs-lookup"><span data-stu-id="65974-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="65974-417">**Socket Filter**: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="65974-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="65974-418">**Vereiste socketfilter**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="65974-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="65974-419">Velden **voor netwerkfilter** leeg laten (**Opnemen** is *niet* geselecteerd)</span><span class="sxs-lookup"><span data-stu-id="65974-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="65974-420">Houd er rekening mee dat **id,** **socketfilter** en **socketfilter de** exacte waarden vereist zijn, zoals hierboven is aangegeven.</span><span class="sxs-lookup"><span data-stu-id="65974-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Afbeelding van configuratie-instelling mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="65974-422">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-422">Select the **Scope** tab.</span></span>

   ![Afbeelding van het sco-tabblad configuratie-instellingen](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="65974-424">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="65974-425">Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="65974-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="65974-426">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="65974-426">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instellingen adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="65974-428">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-428">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingen savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="65974-430">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-430">Select **Done**.</span></span>

    ![Afbeelding van configuratie-instellingen netextfinal](images/netext-final.png)

<span data-ttu-id="65974-432">U kunt ook [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen zoals beschreven in Aangepaste configuratieprofielen implementeren met [Jamf Pro| Methode 2: Een configuratieprofiel uploaden naar Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="65974-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="65974-433">Stap 10: Scans plannen met Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="65974-433">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="65974-434">Volg de instructies over [Scans plannen met Microsoft Defender voor Eindpunt op macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span><span class="sxs-lookup"><span data-stu-id="65974-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="65974-435">Stap 11: Microsoft Defender voor eindpunt implementeren in macOS</span><span class="sxs-lookup"><span data-stu-id="65974-435">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="65974-436">Ga naar de plaats waar u hebt `wdav.pkg` opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="65974-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Afbeelding van verkenner wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="65974-438">Wijzig de naam in `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="65974-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Afbeelding van verkenner1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="65974-440">Open het Jamf Pro-dashboard.</span><span class="sxs-lookup"><span data-stu-id="65974-440">Open the Jamf Pro dashboard.</span></span>

    ![Afbeelding van configuratie-instellingen jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="65974-442">Selecteer uw computer en klik op het tandwielpictogram bovenaan en selecteer **vervolgens Computerbeheer.**</span><span class="sxs-lookup"><span data-stu-id="65974-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Afbeelding van configuratie-instellingen compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="65974-444">Selecteer **in Pakketten**+ **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="65974-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="65974-445">![Een afbeelding met vogelbeschrijving automatisch gegenereerd pakket nieuw](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="65974-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="65974-446">Voer **in Nieuw pakket** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="65974-447">**Tabblad Algemeen**</span><span class="sxs-lookup"><span data-stu-id="65974-447">**General tab**</span></span>
    - <span data-ttu-id="65974-448">Weergavenaam: Laat deze nu leeg.</span><span class="sxs-lookup"><span data-stu-id="65974-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="65974-449">Omdat deze opnieuw wordt ingesteld wanneer u uw pkg kiest.</span><span class="sxs-lookup"><span data-stu-id="65974-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="65974-450">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="65974-450">Category: None (default)</span></span>
    - <span data-ttu-id="65974-451">Bestandsnaam: Bestand kiezen</span><span class="sxs-lookup"><span data-stu-id="65974-451">Filename: Choose File</span></span>

    ![Afbeelding van het algemene tabblad Configuratie-instellingen](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="65974-453">Open het bestand en wijs het aan `wdav.pkg` of `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="65974-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Schermafbeelding van een computerscherm Beschrijving automatisch gegenereerd](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="65974-455">Selecteer **Openen**.</span><span class="sxs-lookup"><span data-stu-id="65974-455">Select **Open**.</span></span> <span data-ttu-id="65974-456">Stel de **weergavenaam in** op **Microsoft Defender Advanced Threat Protection en Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="65974-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="65974-457">**Manifestbestand** is niet vereist.</span><span class="sxs-lookup"><span data-stu-id="65974-457">**Manifest File** is not required.</span></span> <span data-ttu-id="65974-458">Microsoft Defender Advanced Threat Protection werkt zonder manifestbestand.</span><span class="sxs-lookup"><span data-stu-id="65974-458">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="65974-459">**Tabblad Opties**</span><span class="sxs-lookup"><span data-stu-id="65974-459">**Options tab**</span></span><br> <span data-ttu-id="65974-460">Standaardwaarden behouden.</span><span class="sxs-lookup"><span data-stu-id="65974-460">Keep default values.</span></span>

    <span data-ttu-id="65974-461">**Tabblad Beperkingen**</span><span class="sxs-lookup"><span data-stu-id="65974-461">**Limitations tab**</span></span><br> <span data-ttu-id="65974-462">Standaardwaarden behouden.</span><span class="sxs-lookup"><span data-stu-id="65974-462">Keep default values.</span></span>
    
     ![Afbeelding van het beperkingstabblad configuratie-instellingen](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="65974-464">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-464">Select **Save**.</span></span> <span data-ttu-id="65974-465">Het pakket wordt geüpload naar Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="65974-465">The package is uploaded to Jamf Pro.</span></span> 

   ![Afbeelding van configuratie-instellingen pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="65974-467">Het kan enkele minuten duren voordat het pakket beschikbaar is voor implementatie.</span><span class="sxs-lookup"><span data-stu-id="65974-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Afbeelding van configuratie-instellingen pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="65974-469">Ga naar de **pagina Beleid.**</span><span class="sxs-lookup"><span data-stu-id="65974-469">Navigate to the **Policies** page.</span></span>

    ![Afbeelding van configuratie-instellingen polocies](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="65974-471">Selecteer **+ Nieuw om** een nieuw beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="65974-471">Select **+ New** to create a new policy.</span></span>

    ![Afbeelding van nieuwe configuratie-instellingen](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="65974-473">Voer **in het** algemeen de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="65974-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="65974-474">Weergavenaam: MDATP Onboarding Contoso 200329 v100.86.92 of hoger</span><span class="sxs-lookup"><span data-stu-id="65974-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="65974-475">Afbeelding van configuratie-instellingenmdatponboard</span><span class="sxs-lookup"><span data-stu-id="65974-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="65974-476">Selecteer **Terugkerend inchecken.**</span><span class="sxs-lookup"><span data-stu-id="65974-476">Select **Recurring Check-in**.</span></span> 
    
    ![Afbeelding van configuratie-instellingen die opnieuw worden checkin](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="65974-478">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="65974-479">Selecteer **Pakketten > Configureren.**</span><span class="sxs-lookup"><span data-stu-id="65974-479">Select **Packages > Configure**.</span></span>
 
    ![Afbeelding van configuratie-instellingenpakket configureren](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="65974-481">Selecteer de **knop Toevoegen** naast Microsoft Defender Advanced Threat Protection en Microsoft **Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="65974-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Afbeelding van configuratie-instellingen die MDATP en MDA toevoegen](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="65974-483">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="65974-483">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingensavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="65974-485">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="65974-485">Select the **Scope** tab.</span></span>  

    ![Afbeelding van scptab configuratie-instellingen](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="65974-487">Selecteer de doelcomputers.</span><span class="sxs-lookup"><span data-stu-id="65974-487">Select the target computers.</span></span>

    ![Afbeelding van configuratie-instellingen tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="65974-489">**Bereik**</span><span class="sxs-lookup"><span data-stu-id="65974-489">**Scope**</span></span>
    
    <span data-ttu-id="65974-490">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="65974-490">Select **Add**.</span></span>
    
    ![Afbeelding van configuratie-instellingen ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Afbeelding van configuratie-instellingen ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="65974-493">**SelfService**</span><span class="sxs-lookup"><span data-stu-id="65974-493">**Self-Service**</span></span>
    
    ![Afbeelding van selfservice configuratie-instellingen](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="65974-495">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="65974-495">Select **Done**.</span></span> 

    ![Afbeelding van configuratie-instellingen do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Afbeelding van configuratie-instellingen do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




