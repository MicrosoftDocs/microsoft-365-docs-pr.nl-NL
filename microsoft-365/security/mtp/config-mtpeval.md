---
title: Microsoft 365 Defender-pijlers configureren voor de proefversie of prototypeomgeving
description: Microsoft 365 Defender-pijlers configureren, zoals Microsoft Defender for Office 365, Microsoft Defender for Identity, Microsoft Cloud app Security en Microsoft Defender for Endpoint, voor uw proefabonnement op de testomgeving.
keywords: Configureer de Microsoft Threat Protection-proefversie, configuratie van Microsoft Threat Protection, Configureer prototypeproject voor Microsoft Threat Protection, Microsoft Threat Protection, pijlers voor Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131295"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="6e06f-104">Microsoft 365 Defender-pijlers configureren voor uw proefversie of pilot omgeving</span><span class="sxs-lookup"><span data-stu-id="6e06f-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6e06f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6e06f-105">**Applies to:**</span></span>
- <span data-ttu-id="6e06f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e06f-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="6e06f-107">U maakt een Microsoft 365-proefabonnement voor proef omgevingen of pilot omgevingen en de implementatie ervan is een proces van drie fasen:</span><span class="sxs-lookup"><span data-stu-id="6e06f-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="6e06f-108">[![Fase 1: voorbereiding](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="6e06f-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="6e06f-109">Fase 1: voorbereiding</span><span class="sxs-lookup"><span data-stu-id="6e06f-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="6e06f-110">[![Fase 2: instellen](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="6e06f-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="6e06f-111">Fase 2: instellen</span><span class="sxs-lookup"><span data-stu-id="6e06f-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: onboarding](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="6e06f-113">Fase 3: onboarding</span><span class="sxs-lookup"><span data-stu-id="6e06f-113">Phase 3: Onboard</span></span> | <span data-ttu-id="6e06f-114">[![Terug naar de pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="6e06f-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="6e06f-115">Terug naar de pilot Playbook</span><span class="sxs-lookup"><span data-stu-id="6e06f-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="6e06f-116">*Dat is alles!*</span><span class="sxs-lookup"><span data-stu-id="6e06f-116">*You are here!*</span></span> | |

<span data-ttu-id="6e06f-117">U bevindt zich momenteel in de configuratiefase.</span><span class="sxs-lookup"><span data-stu-id="6e06f-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="6e06f-118">De voorbereiding is essentieel voor een succesvolle implementatie.</span><span class="sxs-lookup"><span data-stu-id="6e06f-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="6e06f-119">In dit artikel wordt u begeleid over de punten waarmee u rekening moet houden wanneer u Microsoft Defender voor eindpunten gaat voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="6e06f-120">Microsoft 365 Defender-pijlers</span><span class="sxs-lookup"><span data-stu-id="6e06f-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="6e06f-121">Microsoft 365 Defender bestaat uit vier pijlers.</span><span class="sxs-lookup"><span data-stu-id="6e06f-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="6e06f-122">Hoewel één van de voorwaarden van de veiligheid van uw netwerkorganisatie al waarden kan bieden, bieden de vier Microsoft 365 Defender-pijltjes de meeste waarden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Afbeelding of_Microsoft 365, oplossing voor gebruikers, Microsoft Defender for-eindpunten, Microsoft Defender for endpoints, voor Cloud-apps, Microsoft Cloud app Security en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="6e06f-124">In deze sectie wordt u begeleid bij de configuratie:</span><span class="sxs-lookup"><span data-stu-id="6e06f-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="6e06f-125">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6e06f-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="6e06f-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6e06f-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="6e06f-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6e06f-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="6e06f-128">Microsoft Defender voor Eindpunt </span><span class="sxs-lookup"><span data-stu-id="6e06f-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="6e06f-129">Microsoft Defender voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="6e06f-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="6e06f-130">Sla deze stap over als u al Defender voor Office 365 hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6e06f-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="6e06f-131">Er is een PowerShell-module genaamd *Office 365 Advanced Threat Protection recommended configuration Analyzer (Orca)* waarmee enkele van deze instellingen kunnen worden vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="6e06f-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="6e06f-132">Als u een beheerder van de Tenant uitvoert, kunt u met Get-ORCAReport een beoordeling maken van de antispam, anti-spam en andere instellingen voor bericht hygiëne.</span><span class="sxs-lookup"><span data-stu-id="6e06f-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="6e06f-133">U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="6e06f-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="6e06f-134">Ga naar de [beveiligings & beleid voor nalevings centrum van Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Afbeelding of_Office 365 beveiligings & beleidsregels voor het beleid voor nalevings centrum](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="6e06f-136">Klik op **anti malafide**, selecteer **maken** en vul de Beleidsnaam en beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="6e06f-137">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-137">Click **Next**.</span></span>

   ![Afbeelding of_Office 365 beveiligings & beleids pagina voor naleving van het nalevings centrum, waarin u uw beleid kunt benoemen](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="6e06f-139">Uw geavanceerde anti phishingfilter bewerken in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e06f-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6e06f-140">Wijzig de **Geavanceerde fraude drempel** in **2-agressief**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="6e06f-141">Klik op het vervolgkeuzemenu **een voorwaarde toevoegen** en selecteer uw domein (en) als domein van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="6e06f-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="6e06f-142">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-142">Click **Next**.</span></span>

   ![Afbeelding of_Office 365 beveiligings & beleid voor naleving van het anti-phishingfilter waarop u een voorwaarde voor de toepassing kunt toevoegen](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="6e06f-144">Controleer uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-144">Review your settings.</span></span> <span data-ttu-id="6e06f-145">Klik op **dit beleid maken** om te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-145">Click **Create this policy** to confirm.</span></span> 

   ![Afbeelding of_Office 365 beveiligings & beleidsregels voor nalevings centrum waar u de instellingen kunt controleren en klikt u op de knop dit beleid maken](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="6e06f-147">Selecteer **veilige bijlagen** en selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams** .</span><span class="sxs-lookup"><span data-stu-id="6e06f-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Afbeelding of_Office 365 beveiligings & compliance Center waarop u ATP kunt inschakelen voor SharePoint, OneDrive en Microsoft teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="6e06f-149">Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken, wanneer u dit wilt toepassen als het domein van de geadresseerde voor uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="6e06f-150">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-150">Click **Save**.</span></span>

   ![Afbeelding of_Office 365 beveiligings & compliance Center-pagina waar u een nieuw beleid voor het maken van een veilige bijlage kunt maken](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="6e06f-152">Selecteer vervolgens het beleid voor **veilige koppelingen** en klik op het potloodpictogram om het standaardbeleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="6e06f-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="6e06f-153">Zorg ervoor dat de optie **niet bijhouden wanneer gebruikers op optie voor veilige koppelingen klikken** niet is geselecteerd, terwijl de andere opties zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6e06f-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="6e06f-154">Zie [instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6e06f-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="6e06f-155">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-155">Click **Save**.</span></span> 

   ![Afbeelding of_Office 365 beveiligings & compliance Center waarin wordt aangegeven dat de optie niet wordt bijgehouden wanneer gebruikers op veilig klikken niet is geselecteerd.](../../media/mtp-eval-38.png)

9. <span data-ttu-id="6e06f-157">Selecteer vervolgens het **anti-malwarebeleid** , selecteer het standaardbeleid en kies het potloodpictogram.</span><span class="sxs-lookup"><span data-stu-id="6e06f-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="6e06f-158">Klik op **instellingen** en selecteer **Ja en gebruik de standaard Meldingstekst om het** detecteren van **malware** te activeren.</span><span class="sxs-lookup"><span data-stu-id="6e06f-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="6e06f-159">Schakel het **filter common Attachment types** in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="6e06f-160">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-160">Click **Save**.</span></span>

    ![Afbeelding of_Office 365 beveiligings & pagina nalevings centrum waarin wordt aangegeven dat de antwoord op de malware-detectie is ingeschakeld met standaard melding en dat het filter common Attachment types is ingeschakeld.](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="6e06f-162">Ga naar het [Office 365-beveiligings & compliance](https://protection.office.com/homepage)  >  **Search**  >  **audit log Search** en Schakel controle in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Afbeelding of_Office 365 beveiligings & compliance Center waarop u de zoekopdracht in het audit logboek kunt inschakelen](../../media/mtp-eval-40.png)

12. <span data-ttu-id="6e06f-164">Microsoft Defender voor Office 365 integreren met Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6e06f-165">Ga naar de [beveiligings & van het compliance Center-Beheercentrum van Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** en selecteer **Microsoft Defender for Endpoint Settings** in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="6e06f-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="6e06f-166">Schakel in het dialoogvenster verbindingsfunctie van Defender voor eindpunt het selectievakje **verbinding maken met Microsoft Defender voor eindpunt** in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Afbeelding of_Office 365 beveiligings & compliance Center waarop u Microsoft Defender for Endpoint-verbinding kunt inschakelen](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="6e06f-168">Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="6e06f-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="6e06f-169">Sla deze stap over als u Microsoft Defender al hebt ingeschakeld voor identiteit</span><span class="sxs-lookup"><span data-stu-id="6e06f-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="6e06f-170">Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/info) > Selecteer **meer resources**  >  **Microsoft Defender for Identity**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Pagina of_Microsoft 365-Beveiligingscentrum met de optie voor het openen van Microsoft Defender voor identiteit](../../media/mtp-eval-42.png)

2. <span data-ttu-id="6e06f-172">Klik op **maken** om de wizard Microsoft Defender for Identity te starten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Afbeelding van de wizardpagina voor het verwijderen van de wizard of_Microsoft voor de identiteit waarop u moet klikken op de knop maken](../../media/mtp-eval-43.png)

3. <span data-ttu-id="6e06f-174">Kies **een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Afbeelding of_Microsoft Defender voor de welkomstpagina van de identiteit](../../media/mtp-eval-44.png)

4. <span data-ttu-id="6e06f-176">Voer uw on-premises Active Directory-referenties in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="6e06f-177">Dit kan elk gebruikersaccount zijn met leestoegang tot Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e06f-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Afbeelding of_Microsoft Defender voor de identiteit Directory Services-pagina waar u uw referenties moet invoeren](../../media/mtp-eval-45.png)

5. <span data-ttu-id="6e06f-179">Kies vervolgens **Update sensoren** en zet bestand over naar uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="6e06f-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Afbeelding of_Microsoft Defender voor de identiteits pagina waar u de instellingen van een sensor downloaden kunt selecteren](../../media/mtp-eval-46.png)

6. <span data-ttu-id="6e06f-181">Start de Microsoft Defender voor de installatie van de identiteits sensor en voer de wizard uit.</span><span class="sxs-lookup"><span data-stu-id="6e06f-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Afbeelding of_Microsoft Defender voor identiteits pagina waarop u moet klikken op volgende om de wizard Microsoft Defender for Identity sensor te volgen](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="6e06f-183">Klik op **volgende** bij het implementatietype van de sensor.</span><span class="sxs-lookup"><span data-stu-id="6e06f-183">Click **Next** at the sensor deployment type.</span></span>

   ![Afbeelding of_Microsoft Defender voor identiteits pagina waarop u moet klikken op volgende om naar de volgende pagina te gaan](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="6e06f-185">Kopieer de toegangscode omdat u deze moet typen, naast de wizard.</span><span class="sxs-lookup"><span data-stu-id="6e06f-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Afbeelding of_the sensoren waar u de toegangstoets moet typen die u moet typen op de volgende pagina van de wizard voor het instellen van de installatie van Microsoft Defender voor Identity-sensor](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="6e06f-187">Kopieer de toegangstoets in de wizard en klik op **installeren**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Of_Microsoft afbeelding van de pagina van de wizard van de Identity-sensor voor de pagina waar u de toegangstoets moet invoeren en klik vervolgens op de knop installeren.](../../media/mtp-eval-50.png)

10. <span data-ttu-id="6e06f-189">Gefeliciteerd, u hebt Microsoft Defender geconfigureerd voor de identiteit op uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="6e06f-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Afbeelding van de installatie van de wizard of_Microsoft Defender voor de Identity-sensor waarop u moet klikken op de knop Voltooien](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="6e06f-191">Selecteer in de sectie [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings \* \* Microsoft Defender for Endpoint \* \* en zet vervolgens de wisselknop.</span><span class="sxs-lookup"><span data-stu-id="6e06f-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="6e06f-192">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-192">Click **Save**.</span></span> 

    ![Afbeelding of_the Microsoft Defender for Identity Settings-pagina waar u de wisselknop Microsoft Defender for Endpoint moet inschakelen](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="6e06f-194">Windows Defender ATP is opnieuw als Microsoft Defender voor eindpunt aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6e06f-195">Wijzigingen die u in alle portals aanbrengt, worden doorgevoerd in de consistentie.</span><span class="sxs-lookup"><span data-stu-id="6e06f-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="6e06f-196">Beveiligingsupdates voor Microsoft Cloud app configureren</span><span class="sxs-lookup"><span data-stu-id="6e06f-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="6e06f-197">Sla deze stap over als u de beveiligingsversie van de Microsoft Cloud-app al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6e06f-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="6e06f-198">Ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/info)voor  >  **meer informatie** over beveiliging van de  >  **Microsoft Cloud-app**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Pagina of_Microsoft 365 Beveiligingscentrum, waarop u de Microsoft Cloud app Card kunt zien en moet klikken op de knop openen](../../media/mtp-eval-53.png)

2. <span data-ttu-id="6e06f-200">Als u op de informatie vragen om Microsoft Defender for Identity te integreren, selecteert u **Microsoft Defender inschakelen voor Identity Data Integration**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Afbeelding of_the informatie vraagt om Microsoft Defender te integreren voor de identiteit waar u de koppeling Microsoft Defender voor Identity Data Integration moet selecteren](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="6e06f-202">Als u deze vraag niet ziet, betekent dit dat uw Microsoft Defender voor Identity Data Integration al is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6e06f-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="6e06f-203">Als u dat nog niet weet, neemt u contact op met uw IT-beheerder om te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="6e06f-204">Ga naar **instellingen**, schakel de wisselknop **Microsoft Defender voor Identity Integration** in en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Afbeelding van of_the pagina instellingen waar u de wisselknop Microsoft Defender voor Identity Integration moet inschakelen en klik op opslaan](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="6e06f-206">Voor nieuwe Microsoft Defender voor identiteits exemplaren wordt deze schakeloptie voor integratie automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6e06f-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="6e06f-207">Controleer of uw Microsoft Defender voor Identity-integratie is ingeschakeld voordat u verder gaat met de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="6e06f-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="6e06f-208">Selecteer onder de instellingen voor Cloud detectie de optie **Microsoft Defender for Endpoint Integration** en schakel vervolgens de integratie in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="6e06f-209">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-209">Click **Save**.</span></span>

   ![Afbeelding of_the Microsoft Defender voor eindpunt voor pagina met het selectievakje niet-goedgekeurde apps blokkeren onder Microsoft Defender voor eindpunt-integratie is geselecteerd.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="6e06f-212">Selecteer onder instellingen voor Cloud detectie de optie **gebruikers verrijking** en schakel vervolgens integratie met Azure Active Directory in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Afbeelding van de sectie voor het verrijking van gebruikers waarbij het selectievakje verrijkte gebruikers-id's met Azure Active Directory-gebruikersnamen is geselecteerd](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="6e06f-214">Microsoft Defender voor eindpunt configureren</span><span class="sxs-lookup"><span data-stu-id="6e06f-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="6e06f-215">Sla deze stap over als u Microsoft Defender voor eindpunten al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6e06f-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="6e06f-216">Ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/info)  >  **meer bronnen**  >  **Microsoft Defender-Beveiligingscentrum**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="6e06f-217">Klik op **openen**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-217">Click **Open**.</span></span>

   ![De optie afbeelding of_Microsoft Defender-Beveiligingscentrum op de pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="6e06f-219">Volg de wizard Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="6e06f-220">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-220">Click **Next**.</span></span> 

   ![Pagina of_the van de welkomst wizard van het Microsoft Defender-Beveiligingscentrum](../../media/mtp-eval-59.png)

3. <span data-ttu-id="6e06f-222">Kies op basis van de gewenste locatie voor gegevensopslag, het bewaarbeleid voor de gegevens, de organisatie grootte en opt-in voor Voorbeeldfuncties.</span><span class="sxs-lookup"><span data-stu-id="6e06f-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Afbeelding of_the pagina voor het selecteren van het land voor de opslag van de gegevens, het bewaarbeleid en de grootte van de organisatie.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="6e06f-225">U kunt een aantal instellingen, zoals de opslaglocatie van de gegevens, achteraf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="6e06f-226">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-226">Click **Next**.</span></span> 

4. <span data-ttu-id="6e06f-227">Klik op **Doorgaan** om uw Microsoft Defender for Endpoint-Tenant in te richten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Afbeelding of_the pagina waarin u wordt gevraagd Klik op de knop Doorgaan om een Cloud exemplaar te maken](../../media/mtp-eval-61.png)

5. <span data-ttu-id="6e06f-229">Haal de eindpunten binnen via Groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren naar Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6e06f-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6e06f-230">Voor de eenvoud wordt in deze handleiding het lokale script gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="6e06f-231">Klik op **pakket downloaden** en kopieer het onboarding-script naar uw eindpunt (en).</span><span class="sxs-lookup"><span data-stu-id="6e06f-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Afbeelding of_page u wordt gevraagd op de knop pakket downloaden te klikken om het onboarding-script naar uw eindpunt of eindpunten te kopiëren.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="6e06f-233">Voer op het eindpunt het onboarding-script uit als beheerder en kies Y.</span><span class="sxs-lookup"><span data-stu-id="6e06f-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Afbeelding of_the commandline waarbij u het onboarding-script uitvoert en kies Y om door te gaan](../../media/mtp-eval-63.png)

8. <span data-ttu-id="6e06f-235">Gefeliciteerd, u hebt het eerste eindpunt geboardd.</span><span class="sxs-lookup"><span data-stu-id="6e06f-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Afbeelding of_the commandline waarbij u de bevestiging ontvangt dat u het eerste eindpunt hebt binnengebracht.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="6e06f-238">Kopieer-Plak de detectietest via de wizard Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6e06f-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Afbeelding of_the een detectietest stap uitvoeren waarbij u op kopiëren klikt om het opsporings testscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)

10. <span data-ttu-id="6e06f-240">Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="6e06f-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Afbeelding of_command aanwijzing waar u het PowerShell-script moet kopiëren naar een opdrachtprompt met verhoogde bevoegdheid en deze kunt uitvoeren](../../media/mtp-eval-66.png)

11. <span data-ttu-id="6e06f-242">Selecteer in de wizard aan de **slag met Microsoft Defender voor eindpunt** .</span><span class="sxs-lookup"><span data-stu-id="6e06f-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Afbeelding of_the bevestigingsprompt van de wizard waarop u moet klikken met Microsoft Defender voor eindpunt](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="6e06f-244">Ga naar het [Microsoft Defender-Beveiligingscentrum](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="6e06f-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="6e06f-245">Ga naar **instellingen** en selecteer **geavanceerde functies**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Afbeelding of_Microsoft menu instellingen van het Beveiligingscentrum van Defender, waarin u geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)

13. <span data-ttu-id="6e06f-247">Schakel de integratie met **Microsoft Defender for Identity** in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Afbeelding van geavanceerde functies in de of_Microsoft van het Defender-Beveiligingscentrum, Microsoft Defender for Identity Option Option en moet worden ingeschakeld](../../media/mtp-eval-69.png)

14. <span data-ttu-id="6e06f-249">Schakel de integratie met **Office 365 Threat Intelligence** in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Afbeelding van geavanceerde functies in de of_Microsoft van het Defender-Beveiligingscentrum, de optie Office 365 Threat Intelligence, die u moet inschakelen](../../media/mtp-eval-70.png)

15. <span data-ttu-id="6e06f-251">Schakel integratie met **Microsoft Cloud app Security** in.</span><span class="sxs-lookup"><span data-stu-id="6e06f-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Afbeelding of_Microsoft geavanceerde functies in het Beveiligingscentrum van Defender, de optie voor beveiliging van de Microsoft Cloud-app, die u moet inschakelen](../../media/mtp-eval-71.png)

16. <span data-ttu-id="6e06f-253">Schuif omlaag en klik op **Voorkeuren opslaan** om de nieuwe integraties te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Afbeelding of_Save knop Voorkeuren waarop u moet klikken](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="6e06f-255">De Microsoft 365 Defender-service starten</span><span class="sxs-lookup"><span data-stu-id="6e06f-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="6e06f-256">Vanaf 1 juni 2020 maakt Microsoft de functies van Microsoft 365 Defender automatisch voor alle in aanmerking komende tenants.</span><span class="sxs-lookup"><span data-stu-id="6e06f-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="6e06f-257">Zie het [artikel Microsoft Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) voor meer informatie over licenties.</span><span class="sxs-lookup"><span data-stu-id="6e06f-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="6e06f-258">Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="6e06f-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="6e06f-259">Ga naar **instellingen** en selecteer **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="6e06f-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="6e06f-260">Schermafbeelding of_Microsoft 365 van de optie schermafbeelding van de pagina met instellingen voor Microsoft 365 Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="6e06f-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="6e06f-261">Zie [Microsoft 365 Defender inschakelen](mtp-enable.md)voor uitgebreide informatie.</span><span class="sxs-lookup"><span data-stu-id="6e06f-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="6e06f-262">Gefeliciteerd!</span><span class="sxs-lookup"><span data-stu-id="6e06f-262">Congratulations!</span></span> <span data-ttu-id="6e06f-263">U hebt zojuist een proefabonnement voor Microsoft 365 Defender gemaakt of een testomgeving.</span><span class="sxs-lookup"><span data-stu-id="6e06f-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="6e06f-264">U kunt nu vertrouwd raken met de gebruikersinterface van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6e06f-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="6e06f-265">Lees hier wat u kunt zien van de volgende Microsoft 365-interactieve handleiding en leer hoe u elk dashboard gebruikt voor uw dagelijkse beveiligingsbewerkingen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="6e06f-266">Vervolgens kunt u een aanval simuleren en kijken hoe de functies voor cross product detectie, waarschuwingen maken en automatisch reageren op een aanval met een bestand op een eindpunt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="6e06f-267">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6e06f-267">Next step</span></span>
|[<span data-ttu-id="6e06f-268">Simulatie fase aanval</span><span class="sxs-lookup"><span data-stu-id="6e06f-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="6e06f-269">Voer de simulatie van een aanval uit voor de testomgeving van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6e06f-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
