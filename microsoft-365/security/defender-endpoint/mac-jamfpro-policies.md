---
title: Het Microsoft Defender voor Eindpunt instellen voor macOS-beleid in Jamf Pro
description: Meer informatie over het instellen van het Microsoft Defender voor eindpunt voor macOS-beleid in Jamf Pro
keywords: beleid, microsoft, defender, Microsoft Defender voor Eindpunt, Mac, installatie, implementatie, verwijdering, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b6c2c9fe82486030814e89a0ff655d8f631064e4
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062284"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="f08a0-104">Het Microsoft Defender voor Eindpunt instellen voor macOS-beleid in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="f08a0-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f08a0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f08a0-105">**Applies to:**</span></span>

- [<span data-ttu-id="f08a0-106">Defender voor Eindpunt op Mac</span><span class="sxs-lookup"><span data-stu-id="f08a0-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="f08a0-107">Deze pagina begeleidt u bij de stappen die u moet ondernemen om macOS-beleid in te stellen in Pro.</span><span class="sxs-lookup"><span data-stu-id="f08a0-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="f08a0-108">U moet de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="f08a0-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="f08a0-109">Het Onboarding-pakket voor Microsoft Defender voor eindpunten kopen</span><span class="sxs-lookup"><span data-stu-id="f08a0-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="f08a0-110">Een configuratieprofiel maken in Jamf Pro met behulp van het onboarding-pakket</span><span class="sxs-lookup"><span data-stu-id="f08a0-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="f08a0-111">Microsoft Defender configureren voor eindpuntinstellingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="f08a0-112">Instellingen voor meldingen van Microsoft Defender voor eindpunt configureren</span><span class="sxs-lookup"><span data-stu-id="f08a0-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="f08a0-113">Microsoft AutoUpdate configureren (MAU)</span><span class="sxs-lookup"><span data-stu-id="f08a0-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="f08a0-114">Volledige schijftoegang verlenen aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f08a0-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="f08a0-115">Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f08a0-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="f08a0-116">Systeemextensies goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f08a0-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="f08a0-117">Netwerkextensie configureren</span><span class="sxs-lookup"><span data-stu-id="f08a0-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="f08a0-118">Scans plannen met Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="f08a0-119">Microsoft Defender voor eindpunt implementeren in macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="f08a0-120">Stap 1: Het Onboarding-pakket voor Microsoft Defender voor eindpunten kopen</span><span class="sxs-lookup"><span data-stu-id="f08a0-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="f08a0-121">Ga [Microsoft Defender-beveiligingscentrum](https://securitycenter.microsoft.com )naar Instellingen > **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="f08a0-122">Selecteer macOS als besturingssysteem en Mobile Device Management /Microsoft Intune als implementatiemethode.</span><span class="sxs-lookup"><span data-stu-id="f08a0-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Afbeelding van Microsoft Defender-beveiligingscentrum](images/onboarding-macos.png)

3. <span data-ttu-id="f08a0-124">Selecteer **Onboarding-pakket downloaden** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="f08a0-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="f08a0-125">Extract `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="f08a0-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="f08a0-126">Kopieer het bestand naar de gewenste locatie.</span><span class="sxs-lookup"><span data-stu-id="f08a0-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="f08a0-127">Bijvoorbeeld. `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`</span><span class="sxs-lookup"><span data-stu-id="f08a0-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="f08a0-128">Stap 2: Een configuratieprofiel maken in Jamf Pro met behulp van het onboarding-pakket</span><span class="sxs-lookup"><span data-stu-id="f08a0-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="f08a0-129">Zoek het bestand `WindowsDefenderATPOnboarding.plist` in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="f08a0-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Afbeelding van WindowsDefenderATPOnboarding-bestand](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="f08a0-131">Selecteer nieuw in het Pro **Jamf.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Afbeelding van het maken van een nieuw Jamf-Pro dashboard](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="f08a0-133">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-133">Enter the following details:</span></span>

   <span data-ttu-id="f08a0-134">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-134">**General**</span></span>
   - <span data-ttu-id="f08a0-135">Naam: MDATP-onboarding voor macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="f08a0-136">Beschrijving: MDATP EDR onboarding voor macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="f08a0-137">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="f08a0-137">Category: None</span></span>
   - <span data-ttu-id="f08a0-138">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="f08a0-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="f08a0-139">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="f08a0-139">Level: Computer Level</span></span>

4. <span data-ttu-id="f08a0-140">Selecteer **in & Aangepaste Instellingen** **configureren.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Afbeelding van de configureren app en aangepaste instellingen](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="f08a0-142">Selecteer **Upload Bestand (PLIST-bestand)** en voer in **Voorkeursdomein** de volgende opties in: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="f08a0-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Afbeelding van het uploadbestand van de jamfpro-plist](images/jamfpro-plist-upload.png)

    ![Afbeelding van bestandsbestandsbestand uploaden Lijstbestand](images/jamfpro-plist-file.png)

6. <span data-ttu-id="f08a0-145">Selecteer **Openen** en selecteer het onboarding-bestand.</span><span class="sxs-lookup"><span data-stu-id="f08a0-145">Select **Open** and select the onboarding file.</span></span>

    ![Afbeelding van onboarding-bestand](images/jamfpro-plist-file-onboard.png)

7. <span data-ttu-id="f08a0-147">Selecteer **Upload**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-147">Select **Upload**.</span></span> 

    ![Afbeelding van het uploaden van een plistbestand](images/jamfpro-upload-plist.png)

8. <span data-ttu-id="f08a0-149">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-149">Select the **Scope** tab.</span></span>

    ![Afbeelding van het tabblad Bereik](images/jamfpro-scope-tab.png)

9. <span data-ttu-id="f08a0-151">Selecteer de doelcomputers.</span><span class="sxs-lookup"><span data-stu-id="f08a0-151">Select the target computers.</span></span>

    ![Afbeelding van doelcomputers](images/jamfpro-target-computer.png)

    ![Afbeelding van doelen](images/jamfpro-targets.png) 

10. <span data-ttu-id="f08a0-154">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-154">Select **Save**.</span></span>

    ![Afbeelding van implementatiedoelcomputers](images/jamfpro-deployment-target.png)

    ![Afbeelding van geselecteerde doelcomputers](images/jamfpro-target-selected.png)

11. <span data-ttu-id="f08a0-157">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-157">Select **Done**.</span></span>

    ![Afbeelding van doelgroepcomputers](images/jamfpro-target-group.png)

    ![Lijst met configuratieprofielen](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="f08a0-160">Stap 3: Microsoft Defender configureren voor eindpuntinstellingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

<span data-ttu-id="f08a0-161">U kunt JAMF Pro GUI gebruiken om afzonderlijke instellingen van de Microsoft Defender-configuratie te bewerken of de oudere methode gebruiken door een configuratie Plist te maken in een teksteditor en deze te uploaden naar JAMF-Pro.</span><span class="sxs-lookup"><span data-stu-id="f08a0-161">You can either use JAMF Pro GUI to edit individual settings of the Microsoft Defender configuration, or use the legacy method by creating a configuration Plist in a text editor, and uploading it to JAMF Pro.</span></span>

<span data-ttu-id="f08a0-162">Houd er rekening mee dat u exact `com.microsoft.wdav` moet gebruiken als het **voorkeursdomein**, Microsoft Defender gebruikt alleen deze naam en om `com.microsoft.wdav.ext` de beheerde instellingen te laden!</span><span class="sxs-lookup"><span data-stu-id="f08a0-162">Note that you must use exact `com.microsoft.wdav` as the **Preference Domain**, Microsoft Defender uses only this name and `com.microsoft.wdav.ext` to load its managed settings!</span></span>

<span data-ttu-id="f08a0-163">(De versie kan in zeldzame gevallen worden gebruikt wanneer u liever gui-methode gebruikt, maar ook een instelling moet configureren die nog niet aan het `com.microsoft.wdav.ext` schema is toegevoegd.)</span><span class="sxs-lookup"><span data-stu-id="f08a0-163">(The `com.microsoft.wdav.ext` version may be used in rare cases when you prefer to use GUI method, but also need to configure a setting that has not been added to the schema yet.)</span></span>

### <a name="gui-method"></a><span data-ttu-id="f08a0-164">GUI-methode</span><span class="sxs-lookup"><span data-stu-id="f08a0-164">GUI method</span></span>

1. <span data-ttu-id="f08a0-165">Download schema.jsbestand uit [de opslagplaats](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) van Defender GitHub opslaan in een lokaal bestand:</span><span class="sxs-lookup"><span data-stu-id="f08a0-165">Download schema.json file from [Defender's GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) and save it to a local file:</span></span>

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. <span data-ttu-id="f08a0-166">Maak een nieuw configuratieprofiel onder Computers -> Configuratieprofielen en voer de volgende details in op het **tabblad** Algemeen:</span><span class="sxs-lookup"><span data-stu-id="f08a0-166">Create a new Configuration Profile under Computers -> Configuration Profiles, enter the following details on the **General** tab:</span></span>

    ![Nieuw profiel](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - <span data-ttu-id="f08a0-168">Naam: MDATP MDAV-configuratie-instellingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-168">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="f08a0-169">Beschrijving:\<blank\></span><span class="sxs-lookup"><span data-stu-id="f08a0-169">Description:\<blank\></span></span>
    - <span data-ttu-id="f08a0-170">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-170">Category: None (default)</span></span>
    - <span data-ttu-id="f08a0-171">Niveau: Computerniveau (standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-171">Level: Computer Level (default)</span></span>
    - <span data-ttu-id="f08a0-172">Distributiemethode: Automatisch installeren (standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-172">Distribution Method: Install Automatically (default)</span></span>

3. <span data-ttu-id="f08a0-173">Schuif omlaag naar het **tabblad & Aangepaste Instellingen,** selecteer Externe  **toepassingen,** klik op Toevoegen en gebruik Aangepast **schema** als bron om te gebruiken voor het voorkeursdomein.</span><span class="sxs-lookup"><span data-stu-id="f08a0-173">Scroll down to the **Application & Custom Settings** tab, select **External Applications**, click **Add** and use **Custom Schema** as Source to use for the preference domain.</span></span>

    ![Aangepast schema toevoegen](images/4137189bc3204bb09eed3aabc41afd78.png)

4. <span data-ttu-id="f08a0-175">Voer `com.microsoft.wdav` het voorkeursdomein in,  klik op **Schema** toevoegen en Upload de schema.jsbestand dat is gedownload in stap 1.</span><span class="sxs-lookup"><span data-stu-id="f08a0-175">Enter `com.microsoft.wdav` as the Preference Domain, click on **Add Schema** and **Upload** the schema.json file downloaded on Step 1.</span></span> <span data-ttu-id="f08a0-176">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-176">Click **Save**.</span></span>

    ![Upload schema](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. <span data-ttu-id="f08a0-178">U kunt alle ondersteunde configuratie-instellingen van Microsoft Defender hieronder zien onder **Voorkeursdomeineigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-178">You can see all supported Microsoft Defender configuration settings below, under **Preference Domain Properties**.</span></span> <span data-ttu-id="f08a0-179">Klik **op Eigenschappen toevoegen/verwijderen** om de instellingen te selecteren die u wilt beheren en klik op **Ok** om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="f08a0-179">Click **Add/Remove properties** to select the settings that you want to be managed, and click **Ok** to save your changes.</span></span> <span data-ttu-id="f08a0-180">(Instellingen niet-geselecteerd links niet wordt opgenomen in de beheerde configuratie, kan een eindgebruiker deze instellingen configureren op hun machines.)</span><span class="sxs-lookup"><span data-stu-id="f08a0-180">(Settings left unselected will not be included into the managed configuration, an end user will be able to configure those settings on their machines.)</span></span>

    ![Beheerde instellingen selecteren](images/817b3b760d11467abe9bdd519513f54f.png)

6. <span data-ttu-id="f08a0-182">Waarden van de instellingen wijzigen in gewenste waarden.</span><span class="sxs-lookup"><span data-stu-id="f08a0-182">Change values of the settings to desired values.</span></span> <span data-ttu-id="f08a0-183">U kunt op **Meer informatie klikken** om documentatie voor een bepaalde instelling op te halen.</span><span class="sxs-lookup"><span data-stu-id="f08a0-183">You can click **More information** to get documentation for a particular setting.</span></span> <span data-ttu-id="f08a0-184">(U kunt op **Plist-voorbeeld klikken** om te controleren hoe de configuratie-plist eruit zal zien.</span><span class="sxs-lookup"><span data-stu-id="f08a0-184">(You may click **Plist preview** to inspect what the configuration plist will look like.</span></span> <span data-ttu-id="f08a0-185">Klik **op Formuliereditor** om terug te keren naar de visuele editor.)</span><span class="sxs-lookup"><span data-stu-id="f08a0-185">Click **Form editor** to return to the visual editor.)</span></span>

    ![Instellingenwaarden wijzigen](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. <span data-ttu-id="f08a0-187">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-187">Select the **Scope** tab.</span></span>

    ![Configuratieprofielbereik](images/9fc17529e5577eefd773c658ec576a7d.png)

8. <span data-ttu-id="f08a0-189">Selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-189">Select **Contoso's Machine Group**.</span></span>

9. <span data-ttu-id="f08a0-190">Selecteer **Toevoegen** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-190">Select **Add**, then select **Save**.</span></span>

    ![Configuratie-instellingen - toevoegen](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Configuratie-instellingen - opslaan](images/6f093e42856753a3955cab7ee14f12d9.png)

10. <span data-ttu-id="f08a0-193">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-193">Select **Done**.</span></span> <span data-ttu-id="f08a0-194">U ziet het nieuwe **configuratieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-194">You'll see the new **Configuration profile**.</span></span>

    ![Configuratie-instellingen - klaar](images/dd55405106da0dfc2f50f8d4525b01c8.png)

<span data-ttu-id="f08a0-196">Microsoft Defender voegt na een tijd nieuwe instellingen toe.</span><span class="sxs-lookup"><span data-stu-id="f08a0-196">Microsoft Defender adds new settings over time.</span></span> <span data-ttu-id="f08a0-197">Deze nieuwe instellingen worden toegevoegd aan het schema en er wordt een nieuwe versie gepubliceerd naar Github.</span><span class="sxs-lookup"><span data-stu-id="f08a0-197">These new settings will be added to the schema, and a new version will be published to Github.</span></span>
<span data-ttu-id="f08a0-198">U hoeft alleen maar updates te hebben door een bijgewerkt schema te downloaden, een bestaand configuratieprofiel te bewerken en **schema** bewerken op het tabblad & **Aangepaste Instellingen** bewerken.</span><span class="sxs-lookup"><span data-stu-id="f08a0-198">All you need to do to have updates is to download an updated schema, edit existing configuration profile, and **Edit schema** at the **Application & Custom Settings** tab.</span></span>

### <a name="legacy-method"></a><span data-ttu-id="f08a0-199">Oudere methode</span><span class="sxs-lookup"><span data-stu-id="f08a0-199">Legacy method</span></span>

1. <span data-ttu-id="f08a0-200">Gebruik de volgende configuratie-instellingen voor Microsoft Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="f08a0-200">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="f08a0-201">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="f08a0-201">enableRealTimeProtection</span></span>
    - <span data-ttu-id="f08a0-202">passiveMode</span><span class="sxs-lookup"><span data-stu-id="f08a0-202">passiveMode</span></span>

    >[!NOTE]
    ><span data-ttu-id="f08a0-203">Als u van plan bent een AV van derden voor macOS uit te voeren, is deze standaard niet `true` ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f08a0-203">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="f08a0-204">uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-204">exclusions</span></span>
    - <span data-ttu-id="f08a0-205">excludedPath</span><span class="sxs-lookup"><span data-stu-id="f08a0-205">excludedPath</span></span>
    - <span data-ttu-id="f08a0-206">uitgeslotenFileExtension</span><span class="sxs-lookup"><span data-stu-id="f08a0-206">excludedFileExtension</span></span>
    - <span data-ttu-id="f08a0-207">uitgeslotenFileName</span><span class="sxs-lookup"><span data-stu-id="f08a0-207">excludedFileName</span></span>
    - <span data-ttu-id="f08a0-208">uitsluitingenMergePolicy</span><span class="sxs-lookup"><span data-stu-id="f08a0-208">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="f08a0-209">toegestaanThreats</span><span class="sxs-lookup"><span data-stu-id="f08a0-209">allowedThreats</span></span>

    >[!NOTE]
    ><span data-ttu-id="f08a0-210">EICAR is opgenomen in het voorbeeld, als u een proof-of-concept doormaakt, verwijdert u deze vooral als u EICAR test.</span><span class="sxs-lookup"><span data-stu-id="f08a0-210">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>

    - <span data-ttu-id="f08a0-211">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="f08a0-211">disallowedThreatActions</span></span>
    - <span data-ttu-id="f08a0-212">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="f08a0-212">potentially_unwanted_application</span></span>
    - <span data-ttu-id="f08a0-213">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="f08a0-213">archive_bomb</span></span>
    - <span data-ttu-id="f08a0-214">cloudService</span><span class="sxs-lookup"><span data-stu-id="f08a0-214">cloudService</span></span>
    - <span data-ttu-id="f08a0-215">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="f08a0-215">automaticSampleSubmission</span></span>
    - <span data-ttu-id="f08a0-216">tags</span><span class="sxs-lookup"><span data-stu-id="f08a0-216">tags</span></span>
    - <span data-ttu-id="f08a0-217">StatusMenuIcon verbergen</span><span class="sxs-lookup"><span data-stu-id="f08a0-217">hideStatusMenuIcon</span></span>

     <span data-ttu-id="f08a0-218">Zie Eigenschappenlijst voor [configuratieprofiel Van Jamf voor meer informatie.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="f08a0-218">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="f08a0-219">Sla het bestand op als `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="f08a0-219">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>

3. <span data-ttu-id="f08a0-220">Open in het dashboard Pro Jamf computers **en** daar **configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-220">In the Jamf Pro dashboard, open **Computers**, and there **Configuration Profiles**.</span></span> <span data-ttu-id="f08a0-221">Klik op \**Nieuw(* en ga naar het **tabblad** Algemeen.</span><span class="sxs-lookup"><span data-stu-id="f08a0-221">Click \**New(* and switch to the **General** tab.</span></span>

    ![Nieuw profiel](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="f08a0-223">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-223">Enter the following details:</span></span>

    <span data-ttu-id="f08a0-224">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-224">**General**</span></span>
    
    - <span data-ttu-id="f08a0-225">Naam: MDATP MDAV-configuratie-instellingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-225">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="f08a0-226">Beschrijving:\<blank\></span><span class="sxs-lookup"><span data-stu-id="f08a0-226">Description:\<blank\></span></span>
    - <span data-ttu-id="f08a0-227">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-227">Category: None (default)</span></span>
    - <span data-ttu-id="f08a0-228">Distributiemethode: Automatisch installeren(standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-228">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="f08a0-229">Niveau: Computerniveau(standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-229">Level: Computer Level(default)</span></span>

    ![Afbeelding van MDATP MDAV-configuratie-instellingen](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="f08a0-231">Selecteer **in & Aangepaste Instellingen** **configureren.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-231">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Afbeelding van app en aangepaste instellingen](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="f08a0-233">Selecteer **Upload Bestand (PLIST-bestand)**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-233">Select **Upload File (PLIST file)**.</span></span>

    ![Afbeelding van configuratie-instellingen plistbestand](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="f08a0-235">Typ **in Het domein** Voorkeuren en selecteer Upload `com.microsoft.wdav` **PLIST-bestand.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-235">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Afbeelding van het domein configuratie-instellingenvoorkeuren](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="f08a0-237">Selecteer **Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-237">Select **Choose File**.</span></span>

    ![Afbeelding van configuratie-instellingen kies bestand](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="f08a0-239">Selecteer de **MDATP_MDAV_configuration_settings.plist** en selecteer **Openen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-239">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Afbeelding van configuratie-instellingen voor mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="f08a0-241">Selecteer **Upload**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-241">Select **Upload**.</span></span>

    ![Afbeelding van het uploaden van configuratie-instellingen](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Afbeelding van de uploadafbeelding van configuratie-instellingen](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="f08a0-244">Als u het Intune-bestand uploadt, krijgt u de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="f08a0-244">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="f08a0-245">![Afbeelding van configuratie-instellingen intune-bestand uploaden](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="f08a0-245">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="f08a0-246">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-246">Select **Save**.</span></span> 

    ![Afbeelding van configuratie-instellingen Afbeelding opslaan](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="f08a0-248">Het bestand wordt geüpload.</span><span class="sxs-lookup"><span data-stu-id="f08a0-248">The file is uploaded.</span></span>

    ![Afbeelding van het bestand met configuratie-instellingen dat is geüpload](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Afbeelding van het bestand met configuratie-instellingen dat is geüpload](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="f08a0-251">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-251">Select the **Scope** tab.</span></span>

    ![Afbeelding van het bereik van configuratie-instellingen](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="f08a0-253">Selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-253">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="f08a0-254">Selecteer **Toevoegen** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-254">Select **Add**, then select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingen addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Afbeelding van configuratie-instellingen opslaan add](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="f08a0-257">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-257">Select **Done**.</span></span> <span data-ttu-id="f08a0-258">U ziet het nieuwe **configuratieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-258">You'll see the new **Configuration profile**.</span></span>

    ![Afbeelding van configuratie-instellingen config profielafbeelding](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="f08a0-260">Stap 4: Instellingen voor meldingen configureren</span><span class="sxs-lookup"><span data-stu-id="f08a0-260">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="f08a0-261">Deze stappen zijn van toepassing op macOS 10.15 (Catalina) of hoger.</span><span class="sxs-lookup"><span data-stu-id="f08a0-261">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="f08a0-262">Selecteer in het Pro Dashboard Van Jamf de optie **Computers** en vervolgens **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-262">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="f08a0-263">Klik **op Nieuw** en voer de volgende details in voor **Opties:**</span><span class="sxs-lookup"><span data-stu-id="f08a0-263">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="f08a0-264">Tabblad **Algemeen**:</span><span class="sxs-lookup"><span data-stu-id="f08a0-264">Tab **General**:</span></span> 
        - <span data-ttu-id="f08a0-265">**Naam**: MDATP MDAV-meldingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-265">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="f08a0-266">**Beschrijving**: macOS 10.15 (Catalina) of hoger</span><span class="sxs-lookup"><span data-stu-id="f08a0-266">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="f08a0-267">**Categorie:** Geen *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-267">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="f08a0-268">**Distributiemethode:** Automatisch installeren *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-268">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="f08a0-269">**Niveau:** Computerniveau *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-269">**Level**: Computer Level *(default)*</span></span>

        ![Afbeelding van het nieuwe macOS-configuratieprofielscherm](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="f08a0-271">**Tabmeldingen,** klik **op Toevoegen** en voer de volgende waarden in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-271">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="f08a0-272">**Bundel-id:**`com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="f08a0-272">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="f08a0-273">**Kritieke waarschuwingen:** Klik op **Uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-273">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="f08a0-274">**Meldingen:** Klik op **Inschakelen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-274">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="f08a0-275">**Type bannerwaarschuwing:** Selecteer **Opnemen** en **Tijdelijk** *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-275">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="f08a0-276">**Meldingen op vergrendelingsscherm**: Klik op **Verbergen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-276">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="f08a0-277">**Meldingen in het systeemcentrum:** klik op **Weergeven**</span><span class="sxs-lookup"><span data-stu-id="f08a0-277">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="f08a0-278">**Pictogram badge-app:** klik op **Weergeven**</span><span class="sxs-lookup"><span data-stu-id="f08a0-278">**Badge app icon**: Click **Display**</span></span>

        ![Afbeelding van configuratie-instellingen mdatpmdav-meldingenvak](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="f08a0-280">**TabMeldingen**, klik nog **een** keer op Toevoegen, schuif omlaag naar **Nieuwe meldingen Instellingen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-280">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="f08a0-281">**Bundel-id:**`com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="f08a0-281">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="f08a0-282">De rest van de instellingen configureren op dezelfde waarden als hierboven</span><span class="sxs-lookup"><span data-stu-id="f08a0-282">Configure the rest of the settings to the same values as above</span></span>

        ![Afbeelding van configuratie-instellingen mdatpmdav-meldingen mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="f08a0-284">Houd er rekening mee dat u nu twee 'tabellen' met meldingsconfiguraties hebt, een voor **Bundel-id: com.microsoft.wdav.tray** en een voor **Bundel-id: com.microsoft.autoupdate2**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-284">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="f08a0-285">Hoewel u waarschuwingsinstellingen kunt configureren op basis van uw vereisten,  moeten bundel-1D's exact hetzelfde zijn als eerder beschreven en moet de schakelknop Opnemen zijn **aan** voor **meldingen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-285">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="f08a0-286">Selecteer het **tabblad** Bereik en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-286">Select the **Scope** tab, then select **Add**.</span></span>

    ![Afbeelding van het bereik van configuratie-instellingen](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="f08a0-288">Selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-288">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="f08a0-289">Selecteer **Toevoegen** en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-289">Select **Add**, then select **Save**.</span></span>
    
    ![Afbeelding van configuratie-instellingen contoso machine grp opslaan](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Afbeelding van configuratie-instellingen toevoegen opslaan](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="f08a0-292">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-292">Select **Done**.</span></span> <span data-ttu-id="f08a0-293">U ziet het nieuwe **configuratieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-293">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="f08a0-294">![Afbeelding van configuratie-instelling klaar img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="f08a0-294">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="f08a0-295">Stap 5: Microsoft AutoUpdate configureren (MAU)</span><span class="sxs-lookup"><span data-stu-id="f08a0-295">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="f08a0-296">Gebruik de volgende configuratie-instellingen voor Microsoft Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="f08a0-296">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="f08a0-297">Sla het op als `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="f08a0-297">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="f08a0-298">Selecteer algemeen in Pro **Jamf-dashboard.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-298">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Afbeelding van configuratie-instelling algemene afbeelding](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="f08a0-300">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-300">Enter the following details:</span></span>

    <span data-ttu-id="f08a0-301">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-301">**General**</span></span> 
    
    - <span data-ttu-id="f08a0-302">Naam: MDATP MDAV MAU-instellingen</span><span class="sxs-lookup"><span data-stu-id="f08a0-302">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="f08a0-303">Beschrijving: Microsoft AutoUpdate-instellingen voor MDATP voor macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-303">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="f08a0-304">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-304">Category: None (default)</span></span>
    - <span data-ttu-id="f08a0-305">Distributiemethode: Automatisch installeren(standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-305">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="f08a0-306">Niveau: Computerniveau(standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-306">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="f08a0-307">Selecteer **in & Aangepaste Instellingen** **configureren.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-307">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Afbeelding van de configuratie-app en aangepaste instellingen](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="f08a0-309">Selecteer **Upload Bestand (PLIST-bestand)**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-309">Select **Upload File (PLIST file)**.</span></span>

    ![Afbeelding van configuratie-instelling plist](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="f08a0-311">Selecteer **in Voorkeursdomein:** `com.microsoft.autoupdate2` en selecteer Upload **PLIST-bestand.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-311">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Afbeelding van configuratie-instelling pref-domein](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="f08a0-313">Selecteer **Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-313">Select **Choose File**.</span></span>

    ![Afbeelding van configuratie-instelling kiesbestand](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="f08a0-315">Selecteer **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-315">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Afbeelding van configuratie-instelling mdatpmdavmau-instellingen](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="f08a0-317">Selecteer **Upload**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-317">Select **Upload**.</span></span>
    <span data-ttu-id="f08a0-318">![Afbeelding van configuratie-instellinglimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="f08a0-318">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Afbeelding van configuratie-uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="f08a0-320">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-320">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instelling saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="f08a0-322">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-322">Select the **Scope** tab.</span></span>
   
     ![Afbeelding van configuratie-instelling scopetab](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="f08a0-324">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-324">Select **Add**.</span></span>
    
    ![Afbeelding van configuratie-instelling addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Afbeelding van configuratie-instelling addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Afbeelding van configuratie-instelling addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="f08a0-328">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-328">Select **Done**.</span></span>
    
    ![Afbeelding van configuratie-instelling doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f08a0-330">Stap 6: Volledige schijftoegang verlenen aan Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="f08a0-330">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="f08a0-331">Selecteer configuratieprofielen in Pro Dashboard **Jamf.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-331">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Afbeelding van configuratie-instelling configprofiel](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="f08a0-333">Selecteer **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-333">Select **+ New**.</span></span> 

3. <span data-ttu-id="f08a0-334">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-334">Enter the following details:</span></span>

    <span data-ttu-id="f08a0-335">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-335">**General**</span></span> 
    - <span data-ttu-id="f08a0-336">Naam: MDATP MDAV - Volledige schijftoegang verlenen aan EDR en AV</span><span class="sxs-lookup"><span data-stu-id="f08a0-336">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="f08a0-337">Beschrijving: In macOS Catalina of nieuwer, het nieuwe beleid voor privacyvoorkeuren</span><span class="sxs-lookup"><span data-stu-id="f08a0-337">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="f08a0-338">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="f08a0-338">Category: None</span></span>
    - <span data-ttu-id="f08a0-339">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="f08a0-339">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="f08a0-340">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="f08a0-340">Level: Computer level</span></span>


    ![Afbeelding van configuratie-instelling algemeen](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="f08a0-342">Selecteer **in Beleidsbesturingselement Privacyvoorkeuren configureren** **de optie Configureren.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-342">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Afbeelding van configuratie-privacybeleid](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="f08a0-344">Voer **in Beleidsbeheer privacyvoorkeuren** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-344">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="f08a0-345">Id: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="f08a0-345">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="f08a0-346">Id-type: bundel-id</span><span class="sxs-lookup"><span data-stu-id="f08a0-346">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="f08a0-347">Codevereiste: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f08a0-347">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Afbeelding van configuratie-instelling privacyvoorkeursbeleidsgegevens](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="f08a0-349">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-349">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instelling Systeembeleid alle bestanden toevoegen](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="f08a0-351">Onder App of service: Instellen op **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="f08a0-351">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="f08a0-352">Onder 'toegang': Instellen op **Toestaan**</span><span class="sxs-lookup"><span data-stu-id="f08a0-352">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="f08a0-353">Selecteer **Opslaan** (niet de optie rechtsonder).</span><span class="sxs-lookup"><span data-stu-id="f08a0-353">Select **Save** (not the one at the bottom right).</span></span>

    ![Afbeelding van configuratie-instelling sla afbeeldingen op](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="f08a0-355">Klik op `+` het bord naast App Access **om** een nieuw item toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="f08a0-355">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Afbeelding van de configuratie-instelling app-toegang](images/tcc-add-entry.png)

9. <span data-ttu-id="f08a0-357">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-357">Enter the following details:</span></span>

    - <span data-ttu-id="f08a0-358">Id: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="f08a0-358">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="f08a0-359">Id-type: bundel-id</span><span class="sxs-lookup"><span data-stu-id="f08a0-359">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="f08a0-360">Codevereiste: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f08a0-360">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="f08a0-361">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-361">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instelling tCC epsext-invoer](images/tcc-epsext-entry.png)

    - <span data-ttu-id="f08a0-363">Onder App of service: Instellen op **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="f08a0-363">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="f08a0-364">Onder 'toegang': Instellen op **Toestaan**</span><span class="sxs-lookup"><span data-stu-id="f08a0-364">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="f08a0-365">Selecteer **Opslaan** (niet de optie rechtsonder).</span><span class="sxs-lookup"><span data-stu-id="f08a0-365">Select **Save** (not the one at the bottom right).</span></span>

    ![Afbeelding van configuratie-instelling tCC epsext afbeelding2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="f08a0-367">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-367">Select the **Scope** tab.</span></span>

    ![Afbeelding van het configuratiebereik](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="f08a0-369">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-369">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instellings-addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="f08a0-371">Selecteer **Computergroepen >** **onder Groepsnaam** > **selecteer Contoso's MachineGroup.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-371">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Afbeelding van configuratie-instelling contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="f08a0-373">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-373">Select **Add**.</span></span> 

16. <span data-ttu-id="f08a0-374">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-374">Select **Save**.</span></span> 
    
17. <span data-ttu-id="f08a0-375">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-375">Select **Done**.</span></span>
    
    ![Afbeelding van configuratie-instelling donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Afbeelding van configuratie-instelling donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="f08a0-378">U kunt ook [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf-Pro| Methode 2: Upload configuratieprofiel naar Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)Pro.</span><span class="sxs-lookup"><span data-stu-id="f08a0-378">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="f08a0-379">Stap 7: Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f08a0-379">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="f08a0-380">Apple Silicon (M1) apparaten bieden geen ondersteuning voor KEXT.</span><span class="sxs-lookup"><span data-stu-id="f08a0-380">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="f08a0-381">De installatie van een configuratieprofiel met KEXT-beleid mislukt op deze apparaten.</span><span class="sxs-lookup"><span data-stu-id="f08a0-381">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="f08a0-382">Selecteer in **de configuratieprofielen** **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-382">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="f08a0-384">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-384">Enter the following details:</span></span>

    <span data-ttu-id="f08a0-385">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-385">**General**</span></span> 
    
    - <span data-ttu-id="f08a0-386">Naam: MDATP MDAV Kernel Extension</span><span class="sxs-lookup"><span data-stu-id="f08a0-386">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="f08a0-387">Beschrijving: MDATP kernel extension (kext)</span><span class="sxs-lookup"><span data-stu-id="f08a0-387">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="f08a0-388">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="f08a0-388">Category: None</span></span>
    - <span data-ttu-id="f08a0-389">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="f08a0-389">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="f08a0-390">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="f08a0-390">Level: Computer Level</span></span>

    ![Afbeelding van configuratie-instellingen mdatpmdav-kernel](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="f08a0-392">Selecteer **configureren goedgekeurde kernelextensies** **configureren.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-392">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Afbeelding van configuratie-instellingen goedgekeurd kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="f08a0-394">Voer **in Goedgekeurde kernelextensies** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-394">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="f08a0-395">Weergavenaam: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="f08a0-395">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="f08a0-396">Team-id: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="f08a0-396">Team ID: UBF8T346G9</span></span>

    ![Afbeelding van de uitbreiding configuratie-instellingen appr kernel](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="f08a0-398">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-398">Select the **Scope** tab.</span></span>

    ![Afbeelding van het tabblad Configuratie-instellingenbereik img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="f08a0-400">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-400">Select **+ Add**.</span></span>

7. <span data-ttu-id="f08a0-401">Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-401">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="f08a0-402">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-402">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instellingen om afbeeldingen toe te voegen](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="f08a0-404">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-404">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingen saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="f08a0-406">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-406">Select **Done**.</span></span>

    ![Afbeelding van configuratie-instellingen doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="f08a0-408">U kunt ook [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf-Pro| Methode 2: Upload configuratieprofiel naar Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)Pro.</span><span class="sxs-lookup"><span data-stu-id="f08a0-408">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="f08a0-409">Stap 8: Systeemextensies goedkeuren voor Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="f08a0-409">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="f08a0-410">Selecteer in **de configuratieprofielen** **+ Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-410">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="f08a0-412">Voer de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-412">Enter the following details:</span></span>

    <span data-ttu-id="f08a0-413">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-413">**General**</span></span>
    
    - <span data-ttu-id="f08a0-414">Naam: MDATP MDAV System Extensions</span><span class="sxs-lookup"><span data-stu-id="f08a0-414">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="f08a0-415">Beschrijving: MDATP-systeemextensies</span><span class="sxs-lookup"><span data-stu-id="f08a0-415">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="f08a0-416">Categorie: Geen</span><span class="sxs-lookup"><span data-stu-id="f08a0-416">Category: None</span></span>
    - <span data-ttu-id="f08a0-417">Distributiemethode: Automatisch installeren</span><span class="sxs-lookup"><span data-stu-id="f08a0-417">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="f08a0-418">Niveau: Computerniveau</span><span class="sxs-lookup"><span data-stu-id="f08a0-418">Level: Computer Level</span></span>

    ![Afbeelding van configuratie-instellingen sysext nieuwe prof](images/sysext-new-profile.png)

3. <span data-ttu-id="f08a0-420">Selecteer **configureren in Systeemextensies.** </span><span class="sxs-lookup"><span data-stu-id="f08a0-420">In **System Extensions** select **Configure**.</span></span>

   ![Afbeelding van configuratie-instellingen sysext config](images/sysext-configure.png)

4. <span data-ttu-id="f08a0-422">Voer **in Systeemextensies** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-422">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="f08a0-423">Weergavenaam: Microsoft Corp. Systeemextensies</span><span class="sxs-lookup"><span data-stu-id="f08a0-423">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="f08a0-424">Systeemextensietypen: Toegestane systeemextensies</span><span class="sxs-lookup"><span data-stu-id="f08a0-424">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="f08a0-425">Teamaanduiding: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="f08a0-425">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="f08a0-426">Toegestane systeemextensies:</span><span class="sxs-lookup"><span data-stu-id="f08a0-426">Allowed System Extensions:</span></span>
     - <span data-ttu-id="f08a0-427">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="f08a0-427">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="f08a0-428">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="f08a0-428">**com.microsoft.wdav.netext**</span></span>

    ![Afbeelding van configuratie-instellingen sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="f08a0-430">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-430">Select the **Scope** tab.</span></span>

    ![Afbeelding van het bereik van configuratie-instellingen](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="f08a0-432">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-432">Select **+ Add**.</span></span>

7. <span data-ttu-id="f08a0-433">Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-433">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="f08a0-434">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-434">Select **+ Add**.</span></span>

   ![Afbeelding van addima configuratie-instellingen](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="f08a0-436">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-436">Select **Save**.</span></span>

   ![Afbeelding van sysext-bereik configuratie-instellingen](images/sysext-scope.png)

10. <span data-ttu-id="f08a0-438">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-438">Select **Done**.</span></span>

    ![Afbeelding van configuratie-instellingen sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="f08a0-440">Stap 9: Netwerkextensie configureren</span><span class="sxs-lookup"><span data-stu-id="f08a0-440">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="f08a0-441">Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoord controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="f08a0-441">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="f08a0-442">Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="f08a0-442">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="f08a0-443">Deze stappen zijn van toepassing op macOS 10.15 (Catalina) of hoger.</span><span class="sxs-lookup"><span data-stu-id="f08a0-443">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="f08a0-444">Selecteer in het Pro Dashboard Van Jamf de optie **Computers** en vervolgens **Configuratieprofielen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-444">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="f08a0-445">Klik **op Nieuw** en voer de volgende details in voor **Opties:**</span><span class="sxs-lookup"><span data-stu-id="f08a0-445">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="f08a0-446">Tabblad **Algemeen**:</span><span class="sxs-lookup"><span data-stu-id="f08a0-446">Tab **General**:</span></span> 
        - <span data-ttu-id="f08a0-447">**Naam**: Microsoft Defender ATP Network Extension</span><span class="sxs-lookup"><span data-stu-id="f08a0-447">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="f08a0-448">**Beschrijving**: macOS 10.15 (Catalina) of hoger</span><span class="sxs-lookup"><span data-stu-id="f08a0-448">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="f08a0-449">**Categorie:** Geen *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-449">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="f08a0-450">**Distributiemethode:** Automatisch installeren *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-450">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="f08a0-451">**Niveau:** Computerniveau *(standaard)*</span><span class="sxs-lookup"><span data-stu-id="f08a0-451">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="f08a0-452">**Tab-inhoudsfilter:**</span><span class="sxs-lookup"><span data-stu-id="f08a0-452">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="f08a0-453">**Filternaam:** Microsoft Defender ATP-inhoudsfilter</span><span class="sxs-lookup"><span data-stu-id="f08a0-453">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="f08a0-454">**Id**: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="f08a0-454">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="f08a0-455">Serviceadres , **Organisatie**, **Gebruikersnaam**, **Wachtwoord**, **Certificaat** leeg laten (**Opnemen** is *niet* geselecteerd) </span><span class="sxs-lookup"><span data-stu-id="f08a0-455">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="f08a0-456">**Filterorder**: Inspector</span><span class="sxs-lookup"><span data-stu-id="f08a0-456">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="f08a0-457">**Socket Filter**: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="f08a0-457">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="f08a0-458">**Vereiste socketfilter**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f08a0-458">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="f08a0-459">Velden **voor netwerkfilter** leeg laten (**Opnemen** is *niet* geselecteerd)</span><span class="sxs-lookup"><span data-stu-id="f08a0-459">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="f08a0-460">Houd er rekening mee dat **id,** **socketfilter** en **socketfilter de** exacte waarden vereist zijn, zoals hierboven is aangegeven.</span><span class="sxs-lookup"><span data-stu-id="f08a0-460">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Afbeelding van configuratie-instelling mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="f08a0-462">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-462">Select the **Scope** tab.</span></span>

   ![Afbeelding van het sco-tabblad configuratie-instellingen](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="f08a0-464">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-464">Select **+ Add**.</span></span>

5. <span data-ttu-id="f08a0-465">Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-465">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="f08a0-466">Selecteer **+ Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-466">Select **+ Add**.</span></span>

    ![Afbeelding van configuratie-instellingen adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="f08a0-468">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-468">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingen savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="f08a0-470">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-470">Select **Done**.</span></span>

    ![Afbeelding van configuratie-instellingen netextfinal](images/netext-final.png)

<span data-ttu-id="f08a0-472">U kunt ook [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf-Pro| Methode 2: Upload configuratieprofiel naar Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)Pro.</span><span class="sxs-lookup"><span data-stu-id="f08a0-472">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f08a0-473">Stap 10: Scans plannen met Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-473">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="f08a0-474">Volg de instructies over [Scans plannen met Microsoft Defender voor Eindpunt op macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span><span class="sxs-lookup"><span data-stu-id="f08a0-474">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f08a0-475">Stap 11: Microsoft Defender voor eindpunt implementeren in macOS</span><span class="sxs-lookup"><span data-stu-id="f08a0-475">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="f08a0-476">Ga naar de plaats waar u hebt `wdav.pkg` opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="f08a0-476">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Afbeelding van verkenner wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="f08a0-478">Wijzig de naam in `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="f08a0-478">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Afbeelding van verkenner1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="f08a0-480">Open het jamf-Pro dashboard.</span><span class="sxs-lookup"><span data-stu-id="f08a0-480">Open the Jamf Pro dashboard.</span></span>

    ![Afbeelding van configuratie-instellingen jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="f08a0-482">Selecteer uw computer en klik op het tandwielpictogram bovenaan en selecteer **vervolgens Computerbeheer.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-482">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Afbeelding van configuratie-instellingen compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="f08a0-484">Selecteer **in Pakketten**+ **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-484">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="f08a0-485">![Een afbeelding met vogelbeschrijving automatisch gegenereerd pakket nieuw](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="f08a0-485">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="f08a0-486">Voer **in Nieuw pakket** de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-486">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="f08a0-487">**Tabblad Algemeen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-487">**General tab**</span></span>
    - <span data-ttu-id="f08a0-488">Weergavenaam: Laat deze nu leeg.</span><span class="sxs-lookup"><span data-stu-id="f08a0-488">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="f08a0-489">Omdat deze opnieuw wordt ingesteld wanneer u uw pkg kiest.</span><span class="sxs-lookup"><span data-stu-id="f08a0-489">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="f08a0-490">Categorie: Geen (standaard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-490">Category: None (default)</span></span>
    - <span data-ttu-id="f08a0-491">Bestandsnaam: Bestand kiezen</span><span class="sxs-lookup"><span data-stu-id="f08a0-491">Filename: Choose File</span></span>

    ![Afbeelding van het algemene tabblad Configuratie-instellingen](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="f08a0-493">Open het bestand en wijs het aan `wdav.pkg` of `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="f08a0-493">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Schermafbeelding van een computerscherm Beschrijving automatisch gegenereerd](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="f08a0-495">Selecteer **Openen**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-495">Select **Open**.</span></span> <span data-ttu-id="f08a0-496">Stel de **weergavenaam in** op **Microsoft Defender Advanced Threat Protection en Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-496">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="f08a0-497">**Manifestbestand** is niet vereist.</span><span class="sxs-lookup"><span data-stu-id="f08a0-497">**Manifest File** is not required.</span></span> <span data-ttu-id="f08a0-498">Microsoft Defender voor Eindpunt werkt zonder Manifestbestand.</span><span class="sxs-lookup"><span data-stu-id="f08a0-498">Microsoft Defender for Endpoint works without Manifest File.</span></span>
    
    <span data-ttu-id="f08a0-499">**Tabblad Opties**</span><span class="sxs-lookup"><span data-stu-id="f08a0-499">**Options tab**</span></span><br> <span data-ttu-id="f08a0-500">Standaardwaarden behouden.</span><span class="sxs-lookup"><span data-stu-id="f08a0-500">Keep default values.</span></span>

    <span data-ttu-id="f08a0-501">**Tabblad Beperkingen**</span><span class="sxs-lookup"><span data-stu-id="f08a0-501">**Limitations tab**</span></span><br> <span data-ttu-id="f08a0-502">Standaardwaarden behouden.</span><span class="sxs-lookup"><span data-stu-id="f08a0-502">Keep default values.</span></span>
    
     ![Afbeelding van het beperkingstabblad configuratie-instellingen](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="f08a0-504">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-504">Select **Save**.</span></span> <span data-ttu-id="f08a0-505">Het pakket wordt geüpload naar Pro.</span><span class="sxs-lookup"><span data-stu-id="f08a0-505">The package is uploaded to Jamf Pro.</span></span> 

   ![Afbeelding van configuratie-instellingen pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="f08a0-507">Het kan enkele minuten duren voordat het pakket beschikbaar is voor implementatie.</span><span class="sxs-lookup"><span data-stu-id="f08a0-507">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Afbeelding van configuratie-instellingen pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="f08a0-509">Ga naar de **pagina Beleid.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-509">Navigate to the **Policies** page.</span></span>

    ![Afbeelding van configuratie-instellingen polocies](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="f08a0-511">Selecteer **+ Nieuw om** een nieuw beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="f08a0-511">Select **+ New** to create a new policy.</span></span>

    ![Afbeelding van nieuwe configuratie-instellingen](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="f08a0-513">Voer **in het** algemeen de volgende details in:</span><span class="sxs-lookup"><span data-stu-id="f08a0-513">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="f08a0-514">Weergavenaam: MDATP Onboarding Contoso 200329 v100.86.92 of hoger</span><span class="sxs-lookup"><span data-stu-id="f08a0-514">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="f08a0-515">Afbeelding van configuratie-instellingenmdatponboard</span><span class="sxs-lookup"><span data-stu-id="f08a0-515">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="f08a0-516">Selecteer **Terugkerend inchecken.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-516">Select **Recurring Check-in**.</span></span> 
    
    ![Afbeelding van configuratie-instellingen die opnieuw worden checkin](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="f08a0-518">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-518">Select **Save**.</span></span> 
 
14. <span data-ttu-id="f08a0-519">Selecteer **Pakketten > Configureren.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-519">Select **Packages > Configure**.</span></span>
 
    ![Afbeelding van configuratie-instellingenpakket configureren](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="f08a0-521">Selecteer de **knop Toevoegen** naast Microsoft Defender Advanced Threat Protection **en Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-521">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Afbeelding van configuratie-instellingen die MDATP en MDA toevoegen](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="f08a0-523">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-523">Select **Save**.</span></span>

    ![Afbeelding van configuratie-instellingensavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="f08a0-525">Selecteer het **tabblad Bereik.**</span><span class="sxs-lookup"><span data-stu-id="f08a0-525">Select the **Scope** tab.</span></span>  

    ![Afbeelding van scptab configuratie-instellingen](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="f08a0-527">Selecteer de doelcomputers.</span><span class="sxs-lookup"><span data-stu-id="f08a0-527">Select the target computers.</span></span>

    ![Afbeelding van configuratie-instellingen tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="f08a0-529">**Bereik**</span><span class="sxs-lookup"><span data-stu-id="f08a0-529">**Scope**</span></span>
    
    <span data-ttu-id="f08a0-530">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-530">Select **Add**.</span></span>
    
    ![Afbeelding van configuratie-instellingen ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Afbeelding van configuratie-instellingen ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="f08a0-533">**SelfService**</span><span class="sxs-lookup"><span data-stu-id="f08a0-533">**Self-Service**</span></span>
    
    ![Afbeelding van selfservice configuratie-instellingen](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="f08a0-535">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f08a0-535">Select **Done**.</span></span> 

    ![Afbeelding van configuratie-instellingen do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Afbeelding van configuratie-instellingen do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




