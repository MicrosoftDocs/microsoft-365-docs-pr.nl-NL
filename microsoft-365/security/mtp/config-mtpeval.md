---
title: Microsoft 365 Defender-pilaren configureren voor de testtest of testomgeving
description: Configureer Microsoft 365 Defender-pilaren, zoals Microsoft Defender voor Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security en Microsoft Defender for Endpoint, voor uw testtestomgeving of pilotomgeving.
keywords: Configureer de proefversie van Microsoft Threat Protection, de configuratie van de proefversie van Microsoft Threat Protection, configureer het Microsoft Threat Protection-pilotproject, configureer Microsoft Threat Protection-pilaren, Microsoft Threat Protection-pilaren
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932236"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="7321d-104">Microsoft 365 Defender-pilaren configureren voor uw testomgeving of testomgeving</span><span class="sxs-lookup"><span data-stu-id="7321d-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7321d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7321d-105">**Applies to:**</span></span>
- <span data-ttu-id="7321d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7321d-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="7321d-107">Het maken van een testtest of pilotomgeving van Microsoft 365 Defender en deze implementeren bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="7321d-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="7321d-108">[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="7321d-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="7321d-109">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="7321d-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="7321d-110">[![Fase 2: Instellen](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="7321d-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="7321d-111">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="7321d-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="7321d-113">Fase 3: Onboard</span><span class="sxs-lookup"><span data-stu-id="7321d-113">Phase 3: Onboard</span></span> | <span data-ttu-id="7321d-114">[![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="7321d-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="7321d-115">Terug naar pilot playbook</span><span class="sxs-lookup"><span data-stu-id="7321d-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="7321d-116">*U bent hier!*</span><span class="sxs-lookup"><span data-stu-id="7321d-116">*You are here!*</span></span> | |

<span data-ttu-id="7321d-117">U zit momenteel in de configuratiefase.</span><span class="sxs-lookup"><span data-stu-id="7321d-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="7321d-118">Voorbereiding is belangrijk voor elke succesvolle implementatie.</span><span class="sxs-lookup"><span data-stu-id="7321d-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="7321d-119">In dit artikel wordt u op de punten geleid die u moet overwegen wanneer u zich voorbereidt op de implementatie van Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7321d-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="7321d-120">Microsoft 365 Defender-pilaren</span><span class="sxs-lookup"><span data-stu-id="7321d-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="7321d-121">Microsoft 365 Defender bestaat uit vier pilaren.</span><span class="sxs-lookup"><span data-stu-id="7321d-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="7321d-122">Hoewel één mogelijkheid al waarde kan leveren aan de beveiliging van uw netwerkorganisatie, geeft het inschakelen van de vier pilaren van Microsoft 365 Defender uw organisatie de meeste waarde.</span><span class="sxs-lookup"><span data-stu-id="7321d-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Afbeelding of_Microsoft 365 Defender-oplossing voor gebruikers, Microsoft Defender for Identity, voor eindpunten Microsoft Defender voor eindpunt, voor cloud-apps, Microsoft Cloud App-beveiliging en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="7321d-124">In deze sectie wordt u begeleid bij het configureren:</span><span class="sxs-lookup"><span data-stu-id="7321d-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="7321d-125">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="7321d-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="7321d-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7321d-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="7321d-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7321d-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="7321d-128">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7321d-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="7321d-129">Microsoft Defender voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="7321d-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="7321d-130">Sla deze stap over als Defender al is ingeschakeld voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="7321d-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="7321d-131">Er is een PowerShell-module, de *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* waarmee een aantal van deze instellingen kan worden bepaald.</span><span class="sxs-lookup"><span data-stu-id="7321d-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="7321d-132">Wanneer get-ORCAReport wordt uitgevoerd als beheerder in uw tenant, wordt een evaluatie gegenereerd van de instellingen voor antispam, anti-phish en andere instellingen voor berichtverhandeling.</span><span class="sxs-lookup"><span data-stu-id="7321d-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="7321d-133">U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="7321d-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="7321d-134">[Navigeer naar het bedreigingsbeheerbeleid van & Office 365-beveiligingscentrum.](https://protection.office.com/homepage)  >    >  </span><span class="sxs-lookup"><span data-stu-id="7321d-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Afbeelding of_Office 365-beveiligingspagina & compliancecentrum risicobeheerbeleid](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="7321d-136">Klik **op Anti-phishing,** selecteer **Maken** en vul de beleidsnaam en beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="7321d-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="7321d-137">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7321d-137">Click **Next**.</span></span>

   ![Afbeelding of_Office 365-pagina & beveiligingscentrum anti-phishingbeleid, waar u uw beleid een naam kunt geven](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="7321d-139">Bewerk uw geavanceerde anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="7321d-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7321d-140">Wijzig **de geavanceerde drempelwaarde voor phishing** in **2 - Aggressive**.</span><span class="sxs-lookup"><span data-stu-id="7321d-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="7321d-141">Klik op **de vervolgkeuzelijst** Een voorwaarde toevoegen en selecteer uw domein(en) als domein van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="7321d-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="7321d-142">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7321d-142">Click **Next**.</span></span>

   ![Afbeelding of_Office 365-pagina & beveiligingscentrum anti-phishingbeleid, waar u een voorwaarde voor de toepassing kunt toevoegen](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="7321d-144">Controleer uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="7321d-144">Review your settings.</span></span> <span data-ttu-id="7321d-145">Klik **op Dit beleid maken om** te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="7321d-145">Click **Create this policy** to confirm.</span></span> 

   ![Afbeelding of_Office 365-pagina met beveiligingsinstellingen & compliancecentrum anti-phishingbeleid, waar u uw instellingen kunt bekijken en op de knop Dit beleid maken kunt klikken](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="7321d-147">Selecteer **Veilige bijlagen en** selecteer de optie **ATP voor SharePoint, OneDrive en Microsoft Teams** in turn on.</span><span class="sxs-lookup"><span data-stu-id="7321d-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Afbeelding of_Office 365-pagina & beveiligingscentrum waar u ATP voor SharePoint, OneDrive en Microsoft Teams kunt in-](../../media/mtp-eval-36.png)

6. <span data-ttu-id="7321d-149">Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken en dit toe te passen als domein van de geadresseerde op uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="7321d-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="7321d-150">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7321d-150">Click **Save**.</span></span>

   ![Afbeelding of_Office 365-pagina &-compliancecentrum waar u een nieuw beleid voor veilige bijlagen kunt maken](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="7321d-152">Selecteer vervolgens het beleid voor **veilige** koppelingen en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="7321d-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="7321d-153">Zorg ervoor dat de **optie Niet bijhouden wanneer gebruikers op** veilige koppelingen klikken niet is geselecteerd, terwijl de rest van de opties zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="7321d-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="7321d-154">Zie [instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7321d-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="7321d-155">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7321d-155">Click **Save**.</span></span> 

   ![Afbeelding of_Office 365-pagina & Compliancecentrum waarin wordt weergegeven dat de optie Niet bijhouden wanneer gebruikers op Veilig klikken zijn geselecteerd](../../media/mtp-eval-38.png)

9. <span data-ttu-id="7321d-157">Selecteer vervolgens het **antimalwarebeleid,** selecteer het standaardpictogram en kies het potloodpictogram.</span><span class="sxs-lookup"><span data-stu-id="7321d-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="7321d-158">Klik **op Instellingen** en selecteer Ja en gebruik de **standaardmeldingstekst** om de reactie **op malwaredetectie in teschakelen.**</span><span class="sxs-lookup"><span data-stu-id="7321d-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="7321d-159">Schakel het **filter Algemene bijlagetypen** in.</span><span class="sxs-lookup"><span data-stu-id="7321d-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="7321d-160">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7321d-160">Click **Save**.</span></span>

    ![Afbeelding van of_Office 365-pagina & Compliancecentrum waarop wordt weergegeven dat de reactie op malwaredetectie is ingeschakeld met standaardmeldingen en dat het filter voor veelgebruikte bijlagetypen is ingeschakeld](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="7321d-162">Ga naar [het Office 365-beveiligings- & zoeken](https://protection.office.com/homepage)in het auditlogboek van het Office 365-beveiligingscentrum en schakel Controle  >    >   in.</span><span class="sxs-lookup"><span data-stu-id="7321d-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Afbeelding of_Office 365-pagina & compliancecentrum waar u de zoekfunctie in het auditlogboek kunt in-](../../media/mtp-eval-40.png)

12. <span data-ttu-id="7321d-164">Integreer Microsoft Defender voor Office 365 met Microsoft Defender voor het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7321d-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7321d-165">Ga naar [de Office 365-beveiligings- & Compliancecentrum](https://protection.office.com/homepage)  >  **BedreigingsbeheerVerkenner** en selecteer Instellingen van  >   Microsoft Defender **for Endpoint** in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="7321d-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="7321d-166">Schakel in het dialoogvenster Verbinding maken met Defender voor eindpunt **verbinding in met Microsoft Defender voor eindpunt.**</span><span class="sxs-lookup"><span data-stu-id="7321d-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Afbeelding of_Office 365-pagina &-compliancecentrum waarop u de verbinding met Microsoft Defender for Endpoint kunt in- of uit](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="7321d-168">Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="7321d-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="7321d-169">Sla deze stap over als Microsoft Defender voor identiteit al is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="7321d-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="7321d-170">Ga naar [het Microsoft 365-beveiligingscentrum >](https://security.microsoft.com/info) Microsoft Defender voor identiteit meer **bronnen** te  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="7321d-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Afbeelding of_Microsoft de pagina 365-beveiligingscentrum met een optie om Microsoft Defender voor identiteit te openen](../../media/mtp-eval-42.png)

2. <span data-ttu-id="7321d-172">Klik **op Maken** om de wizard Microsoft Defender voor identiteit te starten.</span><span class="sxs-lookup"><span data-stu-id="7321d-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Afbeelding of_Microsoft de pagina van de wizard Defender voor identiteit waarop u moet klikken op de knop Maken](../../media/mtp-eval-43.png)

3. <span data-ttu-id="7321d-174">Kies **Geef een gebruikersnaam en wachtwoord op om verbinding te maken met uw Active Directory-forest.**</span><span class="sxs-lookup"><span data-stu-id="7321d-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Welkomstpagina of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="7321d-176">Voer uw on-premises Active Directory-referenties in.</span><span class="sxs-lookup"><span data-stu-id="7321d-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="7321d-177">Dit kan elk gebruikersaccount zijn dat leestoegang tot Active Directory heeft.</span><span class="sxs-lookup"><span data-stu-id="7321d-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Afbeelding of_Microsoft de pagina Defender for Identity Directory services waar u uw referenties moet plaatsen](../../media/mtp-eval-45.png)

5. <span data-ttu-id="7321d-179">Kies vervolgens **Sensor instellen en** breng het bestand over naar uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="7321d-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Afbeelding of_Microsoft de pagina Defender for Identity waar u Sensorinstallatie voor downloaden kunt selecteren](../../media/mtp-eval-46.png)

6. <span data-ttu-id="7321d-181">Voer de installatie van Microsoft Defender voor identiteits sensor uit en begin de wizard te volgen.</span><span class="sxs-lookup"><span data-stu-id="7321d-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Afbeelding of_Microsoft de pagina Defender for Identity waarop u moet klikken om de wizard Microsoft Defender for Identity te volgen](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="7321d-183">Klik **op Volgende** bij het implementatietype sensor.</span><span class="sxs-lookup"><span data-stu-id="7321d-183">Click **Next** at the sensor deployment type.</span></span>

   ![Afbeelding of_Microsoft de pagina Defender for Identity waar u moet klikken om naar de volgende pagina te gaan](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="7321d-185">Kopieer de toegangstoets, omdat u deze vervolgens in de wizard moet invoeren.</span><span class="sxs-lookup"><span data-stu-id="7321d-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Afbeelding of_the sensorenpagina waar u de toegangstoets moet kopiëren die u moet invoeren op de volgende pagina van de wizard Voor identiteits sensorinstellingen van Microsoft Defender for Identity](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="7321d-187">Kopieer de toegangssleutel naar de wizard en klik op **Installeren.**</span><span class="sxs-lookup"><span data-stu-id="7321d-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Afbeelding of_Microsoft pagina van de wizard Defender for Identity sensor waar u de toegangstoets moet geven en klik vervolgens op de knop Installeren](../../media/mtp-eval-50.png)

10. <span data-ttu-id="7321d-189">Gefeliciteerd, u hebt Microsoft Defender voor identiteit geconfigureerd op uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="7321d-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="7321d-191">Selecteer [\*\*Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2040449) voor eindpunt \*\* in de sectie Instellingen voor Microsoft Defender voor identiteit en schakel de schakelknop in.</span><span class="sxs-lookup"><span data-stu-id="7321d-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="7321d-192">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7321d-192">Click **Save**.</span></span> 

    ![Afbeelding of_the de pagina met identiteitsinstellingen van Microsoft Defender waar u de schakelknop Microsoft Defender for Endpoint moet in- of uitschakelen](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="7321d-194">Windows Defender ATP heeft de naam Microsoft Defender voor het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7321d-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7321d-195">Voor consistentie wordt de nieuwe naam van wijzigingen in al onze portals uitgerold.</span><span class="sxs-lookup"><span data-stu-id="7321d-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="7321d-196">Beveiliging van Microsoft Cloud-apps configureren</span><span class="sxs-lookup"><span data-stu-id="7321d-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="7321d-197">Sla deze stap over als u Microsoft Cloud App-beveiliging al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7321d-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="7321d-198">[Navigeer naar Het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/info)meer bronnen  >  **voor** Microsoft  >  **Cloud App-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="7321d-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Afbeelding of_Microsoft de pagina 365-beveiligingscentrum waar u de kaart Microsoft Cloud App kunt zien en waarop u moet klikken op de knop Openen](../../media/mtp-eval-53.png)

2. <span data-ttu-id="7321d-200">Bij de informatieprompt voor integratie van Microsoft Defender voor identiteit, selecteert u Integratie van Microsoft Defender voor **identiteitsgegevens inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="7321d-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Afbeelding of_the informatieprompt voor integratie van Microsoft Defender voor identiteit, waar u de koppeling Koppeling voor integratie van gegevens van Microsoft Defender voor identiteit inschakelen moet selecteren](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="7321d-202">Als u deze prompt niet ziet, kan het betekenen dat de integratie van uw Microsoft Defender voor identiteitsgegevens al is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7321d-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="7321d-203">Als u het echter niet zeker weet, neem dan contact op met uw IT-beheerder om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="7321d-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="7321d-204">Ga naar **Instellingen,** schakel de schakelknop Voor identiteitsintegratie **van Microsoft Defender** in en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="7321d-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Afbeelding of_the instellingenpagina waar u de schakelknop voor integratie met Microsoft Defender voor identiteit moet in schakelen en vervolgens op Opslaan moet klikken](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="7321d-206">Voor nieuwe Microsoft Defender voor identiteits-exemplaren is deze schakelknop voor integratie automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7321d-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="7321d-207">Controleer of uw integratie met Microsoft Defender voor identiteit is ingeschakeld voordat u verdergaat met de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="7321d-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="7321d-208">Selecteer onder de clouddetectie-instellingen **Microsoft Defender voor eindpuntintegratie** en schakel vervolgens de integratie in.</span><span class="sxs-lookup"><span data-stu-id="7321d-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="7321d-209">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7321d-209">Click **Save**.</span></span>

   ![Afbeelding of_the microsoft Defender for Endpoint-pagina waar het selectievakje voor niet-geanctioneerde apps blokkeren onder Integratie met Microsoft Defender voor eindpunt is ingeschakeld.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="7321d-212">Selecteer onder Clouddetectie-instellingen **de optie Gegevensverrijking van** gebruiker en schakel vervolgens de integratie met Azure Active Directory in.</span><span class="sxs-lookup"><span data-stu-id="7321d-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Afbeelding van de sectie Gegevensverrijking van gebruikers waarin het selectievakje voor het verrijken van gevonden gebruikers-id's met Azure Active Directory-gebruikers is ingeschakeld](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="7321d-214">Microsoft Defender voor eindpunt configureren</span><span class="sxs-lookup"><span data-stu-id="7321d-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="7321d-215">Sla deze stap over als u Microsoft Defender voor eindpunt al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7321d-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="7321d-216">Ga naar [het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/info)  >  **Meer bronnen** Microsoft  >  **Defender-beveiligingscentrum.**</span><span class="sxs-lookup"><span data-stu-id="7321d-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="7321d-217">Klik **op Openen.**</span><span class="sxs-lookup"><span data-stu-id="7321d-217">Click **Open**.</span></span>

   ![Afbeelding of_Microsoft de optie Defender-beveiligingscentrum op de pagina Microsoft 365-beveiligingscentrum](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="7321d-219">Volg de wizard Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7321d-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="7321d-220">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7321d-220">Click **Next**.</span></span> 

   ![Afbeelding of_the welkomstwizard van het Microsoft Defender-beveiligingscentrum](../../media/mtp-eval-59.png)

3. <span data-ttu-id="7321d-222">Kies op basis van uw voorkeurslocatie voor gegevensopslag, bewaarbeleid, organisatiegrootte en opt-in voor voorbeeldfuncties.</span><span class="sxs-lookup"><span data-stu-id="7321d-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Afbeelding of_the pagina om uw land voor gegevensopslag, bewaarbeleid en de grootte van de organisatie te selecteren.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="7321d-225">U kunt sommige instellingen, zoals de opslaglocatie van gegevens, later niet meer wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7321d-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="7321d-226">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="7321d-226">Click **Next**.</span></span> 

4. <span data-ttu-id="7321d-227">Klik **op Doorgaan** om de tenant Microsoft Defender for Endpoint in te stellen.</span><span class="sxs-lookup"><span data-stu-id="7321d-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Afbeelding of_the pagina met de vraag of u op de knop Doorgaan klikt om uw cloud-exemplaar te maken](../../media/mtp-eval-61.png)

5. <span data-ttu-id="7321d-229">Werk uw eindpunten in via groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren naar Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7321d-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7321d-230">Om het eenvoudig te houden, wordt in deze handleiding het lokale script gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7321d-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="7321d-231">Klik **op Pakket downloaden** en kopieer het onboarding-script naar uw eindpunt(en).</span><span class="sxs-lookup"><span data-stu-id="7321d-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Afbeelding of_page u wordt gevraagd op de knop Pakket downloaden te klikken om het onboarding-script naar uw eindpunt of eindpunten te kopiëren](../../media/mtp-eval-62.png)

7. <span data-ttu-id="7321d-233">Voer op uw eindpunt het onboarding-script uit als beheerder en kies Y.</span><span class="sxs-lookup"><span data-stu-id="7321d-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Afbeelding of_the opdrachtlijn waar u het onboarding-script kunt uitvoeren en kies Y om verder te gaan](../../media/mtp-eval-63.png)

8. <span data-ttu-id="7321d-235">Gefeliciteerd, u hebt uw eerste eindpunt binnengelaten.</span><span class="sxs-lookup"><span data-stu-id="7321d-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Afbeelding of_the opdrachtlijn waar u de bevestiging krijgt dat u uw eerste eindpunt hebt onboarded.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="7321d-238">Kopieer en plak de detectietest van de wizard Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7321d-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Afbeelding of_the een detectieteststap uit te voeren, waarbij u op Kopiëren klikt om het detectietestscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)

10. <span data-ttu-id="7321d-240">Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer het uit.</span><span class="sxs-lookup"><span data-stu-id="7321d-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Afbeelding of_command prompt waar u het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid moet kopiëren en uitvoeren](../../media/mtp-eval-66.png)

11. <span data-ttu-id="7321d-242">Selecteer **Microsoft Defender voor eindpunt gebruiken in** de wizard.</span><span class="sxs-lookup"><span data-stu-id="7321d-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Afbeelding of_the bevestigingsprompt van de wizard waar u moet klikken op Aan de slag met Microsoft Defender voor eindpunt](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="7321d-244">Ga naar het [Microsoft Defender-beveiligingscentrum.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="7321d-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="7321d-245">Ga naar **Instellingen** en selecteer geavanceerde **functies.**</span><span class="sxs-lookup"><span data-stu-id="7321d-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Afbeelding of_Microsoft menu Instellingen van Defender-beveiligingscentrum waar u Geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)

13. <span data-ttu-id="7321d-247">Schakel de integratie met **Microsoft Defender for Identity in.**</span><span class="sxs-lookup"><span data-stu-id="7321d-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender-beveiligingscentrum, optie Microsoft Defender voor identiteit die u moet in- of uitschakelen](../../media/mtp-eval-69.png)

14. <span data-ttu-id="7321d-249">Schakel de integratie met **Office 365 Threat Intelligence in.**</span><span class="sxs-lookup"><span data-stu-id="7321d-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender-beveiligingscentrum, optie bedreigingsinformatie van Office 365 die u moet in- of uitschakelen](../../media/mtp-eval-70.png)

15. <span data-ttu-id="7321d-251">Schakel integratie met **Microsoft Cloud App Security in.**</span><span class="sxs-lookup"><span data-stu-id="7321d-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender-beveiligingscentrum, optie voor beveiliging in Microsoft Cloud-apps die u moet in- of uitschakelen](../../media/mtp-eval-71.png)

16. <span data-ttu-id="7321d-253">Schuif omlaag en klik op **Voorkeuren voor opslaan om** de nieuwe integraties te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="7321d-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Knop of_Save voorkeuren waar u op moet klikken](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="7321d-255">De Microsoft 365 Defender-service starten</span><span class="sxs-lookup"><span data-stu-id="7321d-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="7321d-256">Vanaf 1 juni 2020 schakelt Microsoft microsoft 365 Defender-functies automatisch in voor alle in aanmerking komende tenants.</span><span class="sxs-lookup"><span data-stu-id="7321d-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="7321d-257">Zie dit [artikel in de Microsoft Tech Community over de licentie die in aanmerking](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) komt voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7321d-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="7321d-258">Ga naar [het Microsoft 365-beveiligingscentrum.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="7321d-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="7321d-259">Ga naar **Instellingen** en selecteer **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="7321d-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="7321d-260">Afbeelding of_Microsoft 365 Defender-optie schermafbeelding van de pagina Instellingen van het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="7321d-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="7321d-261">Zie [Microsoft 365 Defender](mtp-enable.md)in te zetten voor een uitgebreidere informatie.</span><span class="sxs-lookup"><span data-stu-id="7321d-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="7321d-262">Gefeliciteerd!</span><span class="sxs-lookup"><span data-stu-id="7321d-262">Congratulations!</span></span> <span data-ttu-id="7321d-263">U hebt zojuist een testomgeving of testomgeving met Microsoft 365 Defender gemaakt!</span><span class="sxs-lookup"><span data-stu-id="7321d-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="7321d-264">Nu kunt u vertrouwd raken met de gebruikersinterface van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7321d-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="7321d-265">Bekijk wat u kunt leren van de volgende interactieve handleiding van Microsoft 365 Defender en leer hoe u elk dashboard kunt gebruiken voor uw dagelijkse beveiligingsbewerkingstaken.</span><span class="sxs-lookup"><span data-stu-id="7321d-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="7321d-266">Vervolgens kunt u een aanval simuleren en zien hoe de mogelijkheden van de verschillende producten een eindpunt detecteren, maken en automatisch reageren op een bestandsloze aanval op een eindpunt.</span><span class="sxs-lookup"><span data-stu-id="7321d-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="7321d-267">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="7321d-267">Next step</span></span>
|[<span data-ttu-id="7321d-268">Testfase van aanvallen</span><span class="sxs-lookup"><span data-stu-id="7321d-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="7321d-269">Voer de testomgeving met Microsoft 365 Defender uit voor de aanval.</span><span class="sxs-lookup"><span data-stu-id="7321d-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
