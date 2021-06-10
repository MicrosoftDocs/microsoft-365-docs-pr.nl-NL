---
title: De Microsoft 365 Defender configureren voor het proeflab of de testomgeving
description: Configureer Microsoft 365 Defender-pilaren, zoals Microsoft Defender voor Office 365, Microsoft Defender voor identiteit, Microsoft Cloud App Security en Microsoft Defender voor eindpunt, voor uw proeflab of testomgeving.
keywords: configureer Microsoft 365 Defender trial, Microsoft 365 Defender trial configuration, configure Microsoft 365 Defender pilot project, configure Microsoft 365 Defender pillars, Microsoft 365 Defender pillars
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 05bdc9cbb678a3d6c1cee726fc4d8c2e45d2d360
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933503"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="c6e21-104">De Microsoft 365 Defender-pilaren configureren voor uw proeflaboratorium of testomgeving</span><span class="sxs-lookup"><span data-stu-id="c6e21-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c6e21-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c6e21-105">**Applies to:**</span></span>
- <span data-ttu-id="c6e21-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6e21-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="c6e21-107">Het maken Microsoft 365 proeflaboratorium of testomgeving van Defender en deze implementeren is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="c6e21-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="c6e21-108">[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="c6e21-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="c6e21-109">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="c6e21-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="c6e21-110">[![Fase 2: Instellen](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="c6e21-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="c6e21-111">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="c6e21-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Fase 3: Onboarden](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="c6e21-113">Fase 3: Onboarden</span><span class="sxs-lookup"><span data-stu-id="c6e21-113">Phase 3: Onboard</span></span> | <span data-ttu-id="c6e21-114">[![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="c6e21-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="c6e21-115">Terug naar pilot playbook</span><span class="sxs-lookup"><span data-stu-id="c6e21-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="c6e21-116">*U bent er!*</span><span class="sxs-lookup"><span data-stu-id="c6e21-116">*You are here!*</span></span> | |

<span data-ttu-id="c6e21-117">U bent momenteel in de configuratiefase.</span><span class="sxs-lookup"><span data-stu-id="c6e21-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="c6e21-118">Voorbereiding is essentieel voor een geslaagde implementatie.</span><span class="sxs-lookup"><span data-stu-id="c6e21-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="c6e21-119">In dit artikel wordt u begeleid over de punten die u moet overwegen terwijl u zich voorbereidt op de implementatie van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="c6e21-120">Microsoft 365 Defender-pilaren</span><span class="sxs-lookup"><span data-stu-id="c6e21-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="c6e21-121">Microsoft 365 Defender bestaat uit vier pilaren.</span><span class="sxs-lookup"><span data-stu-id="c6e21-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="c6e21-122">Hoewel één pijler al waarde kan bieden voor de beveiliging van uw netwerkorganisatie, biedt het inschakelen van de vier Microsoft 365 Defender-pijlers de meeste waarde voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c6e21-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="c6e21-124">In deze sectie wordt u begeleid bij het configureren:</span><span class="sxs-lookup"><span data-stu-id="c6e21-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="c6e21-125">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c6e21-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="c6e21-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c6e21-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="c6e21-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6e21-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="c6e21-128">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c6e21-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="c6e21-129">Microsoft Defender configureren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c6e21-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="c6e21-130">Sla deze stap over als u Defender al hebt ingeschakeld voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6e21-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="c6e21-131">Er is een PowerShell-module genaamd *de Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* waarmee u bepaalde van deze instellingen kunt bepalen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="c6e21-132">Wanneer u wordt uitgevoerd als een beheerder in uw tenant, helpt get-ORCAReport bij het genereren van een beoordeling van de instellingen voor antispam, anti-phish en andere berichthygiëne.</span><span class="sxs-lookup"><span data-stu-id="c6e21-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="c6e21-133">U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="c6e21-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="c6e21-134">Navigeer [naar Office 365 beveiligingsbeleid & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Pagina of_Office beveiligingsbeleid van 365 & compliancecentrum bedreigingsbeheer](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="c6e21-136">Klik **op Anti-phishing,** selecteer **Maken** en vul de naam en beschrijving van het beleid in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="c6e21-137">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-137">Click **Next**.</span></span>

   ![Afbeelding of_Office 365-beveiligingspagina & anti-phishingbeleidspagina van het Compliancecentrum, waar u uw beleid een naam kunt geven](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="c6e21-139">Bewerk uw geavanceerde anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6e21-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c6e21-140">Geavanceerde **phishingdrempel wijzigen** in **2 - Agressief.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="c6e21-141">Klik op **de vervolgkeuzelijst** Een voorwaarde toevoegen en selecteer uw domein(en) als geadresseerdedomein.</span><span class="sxs-lookup"><span data-stu-id="c6e21-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="c6e21-142">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-142">Click **Next**.</span></span>

   ![Afbeelding of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="c6e21-144">Controleer uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-144">Review your settings.</span></span> <span data-ttu-id="c6e21-145">Klik **op Dit beleid maken om** dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-145">Click **Create this policy** to confirm.</span></span> 

   ![Afbeelding of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="c6e21-147">Selecteer **Safe bijlagen en** selecteer de optie ATP in **SharePoint, OneDrive en Microsoft Teams** in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Afbeelding of_Office pagina 365 Beveiligings- & compliancecentrum waar u ATP kunt in- SharePoint, OneDrive en Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="c6e21-149">Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken en pas dit toe als geadresseerdedomein op uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="c6e21-150">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-150">Click **Save**.</span></span>

   ![Afbeelding of_Office pagina 365 Beveiligingscentrum & waar u een nieuw beleid voor veilige bijlagen kunt maken](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="c6e21-152">Selecteer vervolgens het Safe **koppelingenbeleid** en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="c6e21-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="c6e21-153">Zorg ervoor dat de optie **Niet bijhouden wanneer gebruikers op** veilige koppelingen klikken niet is geselecteerd, terwijl de overige opties zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="c6e21-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="c6e21-154">Zie [Safe Instellingen voor koppelingen](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6e21-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="c6e21-155">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-155">Click **Save**.</span></span> 

   ![Afbeelding of_Office pagina 365 Beveiligingscentrum & waarin wordt weergegeven dat de optie Niet bijhouden wanneer gebruikers op veilig klikken niet is geselecteerd](../../media/mtp-eval-38.png)

9. <span data-ttu-id="c6e21-157">Selecteer vervolgens het **anti-malwarebeleid,** selecteer de standaardinstelling en kies het potloodpictogram.</span><span class="sxs-lookup"><span data-stu-id="c6e21-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="c6e21-158">Klik **Instellingen** en selecteer **Ja en gebruik de standaardmeldingstekst om** Reactie op **malwaredetectie in te stellen.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="c6e21-159">Schakel het **filter Algemene bijlagetypen** in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="c6e21-160">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-160">Click **Save**.</span></span>

    ![Afbeelding of_Office pagina Beveiligings- & compliancecentrum van 365, waaruit blijkt dat de reactie op malwaredetectie is ingeschakeld met standaardmelding en dat het filter voor algemene bijlagetypen is ingeschakeld](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="c6e21-162">[Navigeer naar Office 365 beveiligingscentrum & zoeken](https://protection.office.com/homepage)in het zoeklogboek van het compliancecentrum en schakel  >    >   Auditing in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Afbeelding of_Office pagina 365 Beveiligingscentrum & waar u de zoekopdracht Auditlogboek kunt in-](../../media/mtp-eval-40.png)

12. <span data-ttu-id="c6e21-164">Integreer Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c6e21-165">[Navigeer naar Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer en selecteer Microsoft Defender voor Eindpunt Instellingen in de rechterbovenhoek van het  >    >   scherm. </span><span class="sxs-lookup"><span data-stu-id="c6e21-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="c6e21-166">Schakel in het dialoogvenster Verbinding met Defender voor eindpunt de Verbinding maken **microsoft Defender voor eindpunt in.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Afbeelding of_Office 365-beveiligings- & pagina compliancecentrum waarin u Verbinding met Microsoft Defender voor eindpunt kunt in-](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="c6e21-168">Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="c6e21-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="c6e21-169">Sla deze stap over als u Microsoft Defender voor identiteit al hebt ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="c6e21-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="c6e21-170">Ga naar [Microsoft 365 beveiligingscentrum >](https://security.microsoft.com/info) selecteer **Meer resources** Microsoft Defender voor  >  **identiteit.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Afbeelding of_Microsoft 365-beveiligingscentrum met een optie om Microsoft Defender voor identiteit te openen](../../media/mtp-eval-42.png)

2. <span data-ttu-id="c6e21-172">Klik **op Maken** om de wizard Microsoft Defender voor identiteit te starten.</span><span class="sxs-lookup"><span data-stu-id="c6e21-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Afbeelding of_Microsoft wizard Defender voor identiteit waar u op knop Maken moet klikken](../../media/mtp-eval-43.png)

3. <span data-ttu-id="c6e21-174">Kies **Een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Welkomstpagina of_Microsoft Defender voor identiteit](../../media/mtp-eval-44.png)

4. <span data-ttu-id="c6e21-176">Voer uw on-premises Active Directory-referenties in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="c6e21-177">Dit kan elk gebruikersaccount zijn dat leestoegang heeft tot Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6e21-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Afbeelding of_Microsoft defender voor identiteitslijstservicespagina waar u uw referenties moet plaatsen](../../media/mtp-eval-45.png)

5. <span data-ttu-id="c6e21-179">Kies vervolgens **Sensor instellen downloaden en** bestand overbrengen naar uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="c6e21-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Afbeelding of_Microsoft defender voor identiteitspagina waar u Sensorinstallatie downloaden kunt selecteren](../../media/mtp-eval-46.png)

6. <span data-ttu-id="c6e21-181">Voer de installatie van de Microsoft Defender voor identiteits sensor uit en begin de wizard te volgen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Afbeelding of_Microsoft defender voor identiteitspagina waar u naast moet klikken om de sensorwizard van Microsoft Defender voor identiteit te volgen](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="c6e21-183">Klik **op Volgende** bij het type sensorimplementatie.</span><span class="sxs-lookup"><span data-stu-id="c6e21-183">Click **Next** at the sensor deployment type.</span></span>

   ![Afbeelding of_Microsoft defender voor identiteitspagina waar u naast moet klikken om naar de volgende pagina te gaan](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="c6e21-185">Kopieer de toegangssleutel omdat u deze vervolgens moet invoeren in de wizard.</span><span class="sxs-lookup"><span data-stu-id="c6e21-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Afbeelding of_the pagina met sensoren waar u de toegangstoets moet kopiëren die u moet invoeren op de volgende pagina met de installatiewizard van de Microsoft Defender voor identiteits sensor](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="c6e21-187">Kopieer de toegangssleutel naar de wizard en klik op **Installeren.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Afbeelding of_Microsoft wizard Wizard Defender voor identiteits sensor waar u de toegangssleutel moet verstrekken en klik vervolgens op de knop Installeren](../../media/mtp-eval-50.png)

10. <span data-ttu-id="c6e21-189">Gefeliciteerd, u hebt Microsoft Defender voor identiteit geconfigureerd op uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="c6e21-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Afbeelding of_Microsoft installatie van de wizard Installatie van de defender voor identiteits sensor, waarbij u op de knop Voltooien moet klikken](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="c6e21-191">Selecteer onder [de sectie Instellingen](https://go.microsoft.com/fwlink/?linkid=2040449) voor Microsoft Defender voor identiteit de optie \*\*Microsoft Defender voor Eindpunt \*\*, en schakel de schakelaar in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="c6e21-192">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-192">Click **Save**.</span></span> 

    ![Afbeelding of_the pagina met instellingen voor Microsoft Defender voor identiteit waarin u de schakelknop Microsoft Defender voor eindpunt moet in-](../../media/mtp-eval-52.png)


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="c6e21-194">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6e21-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="c6e21-195">Sla deze stap over als u deze stap al hebt Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c6e21-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="c6e21-196">Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/info)  >  **Meer resources Microsoft Cloud App Security.**  >  </span><span class="sxs-lookup"><span data-stu-id="c6e21-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Afbeelding of_Microsoft 365-beveiligingscentrumpagina waar u de Kaart van Microsoft Cloud App kunt zien en op de knop Openen moet klikken](../../media/mtp-eval-53.png)

2. <span data-ttu-id="c6e21-198">Selecteer Microsoft Defender inschakelen voor **identiteitsgegevensintegratie** bij de informatieprompt voor het integreren van Microsoft Defender voor identiteit.</span><span class="sxs-lookup"><span data-stu-id="c6e21-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Afbeelding of_the informatieprompt om Microsoft Defender voor identiteit te integreren, waarbij u de koppeling Microsoft Defender voor integratie van identiteitsgegevens inschakelen moet selecteren](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="c6e21-200">Als u deze prompt niet ziet, kan dit betekenen dat uw Microsoft Defender voor identiteitsgegevensintegratie al is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6e21-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="c6e21-201">Als u het echter niet zeker weet, neem dan contact op met uw IT-beheerder om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="c6e21-202">Ga naar **Instellingen,** schakel de schakelknop **Microsoft Defender voor identiteitsintegratie** in en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Afbeelding of_the pagina met instellingen waar u de schakelknop Voor identiteitsintegratie van Microsoft Defender in moet schakelen en klik vervolgens op Opslaan](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="c6e21-204">Voor nieuwe Microsoft Defender voor identiteits-exemplaren wordt deze schakelknop voor integratie automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6e21-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="c6e21-205">Controleer of uw Microsoft Defender voor identiteitsintegratie is ingeschakeld voordat u verdergaat met de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="c6e21-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="c6e21-206">Selecteer onder de instellingen voor clouddetectie de optie **Microsoft Defender voor endpoint-integratie** en schakel de integratie in.</span><span class="sxs-lookup"><span data-stu-id="c6e21-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="c6e21-207">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-207">Click **Save**.</span></span>

   ![Afbeelding of_the microsoft Defender voor eindpuntpagina waarin het selectievakje Niet-geanctioneerde apps blokkeren onder Microsoft Defender voor endpoint-integratie is geselecteerd.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="c6e21-210">Selecteer onder Instellingen voor clouddetectie de optie **Gebruikersverrijking** en schakel vervolgens de integratie met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6e21-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Afbeelding van de sectie Gebruikersverrijking waarin het selectievakje verrijkende gevonden gebruikersaanduidingen met Azure Active Directory gebruikersnamen is geselecteerd](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="c6e21-212">Microsoft Defender configureren voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="c6e21-212">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="c6e21-213">Sla deze stap over als u Microsoft Defender voor Eindpunt al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c6e21-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="c6e21-214">Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/info)  >  **Meer resources**  >  **Microsoft Defender-beveiligingscentrum.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="c6e21-215">Klik **op Openen.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-215">Click **Open**.</span></span>

   ![Afbeelding of_Microsoft defender-beveiligingscentrum op de pagina Microsoft 365 beveiligingscentrum](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="c6e21-217">Volg de wizard Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="c6e21-218">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-218">Click **Next**.</span></span> 

   ![Pagina of_the Microsoft Defender-beveiligingscentrum welkomstwizard](../../media/mtp-eval-59.png)

3. <span data-ttu-id="c6e21-220">Kies op basis van uw voorkeurslocatie voor gegevensopslag, beleid voor gegevensretentie, organisatiegrootte en opt-in voor voorbeeldfuncties.</span><span class="sxs-lookup"><span data-stu-id="c6e21-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Afbeelding of_the pagina om uw land voor gegevensopslag, bewaarbeleid en organisatiegrootte te selecteren.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="c6e21-223">U kunt sommige instellingen, zoals de locatie voor gegevensopslag, achteraf niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-223">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="c6e21-224">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c6e21-224">Click **Next**.</span></span> 

4. <span data-ttu-id="c6e21-225">Klik **op Doorgaan** en de Microsoft Defender voor Eindpunt-tenant wordt ingericht.</span><span class="sxs-lookup"><span data-stu-id="c6e21-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Afbeelding of_the pagina met de vraag of u op de knop Doorgaan klikt om uw cloud-exemplaar te maken](../../media/mtp-eval-61.png)

5. <span data-ttu-id="c6e21-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6e21-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c6e21-228">Voor de eenvoud wordt in deze handleiding het lokale script gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="c6e21-229">Klik **op Pakket downloaden** en kopieer het onboarding-script naar uw eindpunten.</span><span class="sxs-lookup"><span data-stu-id="c6e21-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Afbeelding of_page u op de knop Pakket downloaden klikt om het onboarding-script naar uw eindpunt of eindpunten te kopiëren](../../media/mtp-eval-62.png)

7. <span data-ttu-id="c6e21-231">Voer op het eindpunt het onboarding-script uit als beheerder en kies Y.</span><span class="sxs-lookup"><span data-stu-id="c6e21-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Afbeelding of_the commandline waar u het onboarding-script uitwerkt en Y kiest om door te gaan](../../media/mtp-eval-63.png)

8. <span data-ttu-id="c6e21-233">Gefeliciteerd, u hebt uw eerste eindpunt aan boord.</span><span class="sxs-lookup"><span data-stu-id="c6e21-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Afbeelding of_the commandline waar u de bevestiging krijgt dat u uw eerste eindpunt hebt onboarded.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="c6e21-236">Kopieer de detectietest vanuit de wizard Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Afbeelding of_the een detectieteststap uitvoeren waarbij u op Kopiëren moet klikken om het detectietestscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)

10. <span data-ttu-id="c6e21-238">Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde opdracht en voer het uit.</span><span class="sxs-lookup"><span data-stu-id="c6e21-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command prompt where you should copy the PowerShell script to an elevated command prompt and run it](../../media/mtp-eval-66.png)

11. <span data-ttu-id="c6e21-240">Selecteer **Start using Microsoft Defender for Endpoint from** the Wizard.</span><span class="sxs-lookup"><span data-stu-id="c6e21-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Afbeelding of_the bevestigingsprompt van de wizard waarin u op Start using Microsoft Defender for Endpoint klikt](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="c6e21-242">Ga naar de [Microsoft Defender-beveiligingscentrum.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="c6e21-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="c6e21-243">Ga naar **Instellingen** en selecteer geavanceerde **functies.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-243">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Afbeelding of_Microsoft Defender Security Center Instellingen menu waarin u Geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)

13. <span data-ttu-id="c6e21-245">Schakel de integratie met **Microsoft Defender voor identiteit in.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender Security Center, optie microsoft Defender voor identiteit die u moet in- of uitschakelen](../../media/mtp-eval-69.png)

14. <span data-ttu-id="c6e21-247">Schakel de integratie in met **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)

15. <span data-ttu-id="c6e21-249">Schakel integratie met **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender Security Center, Microsoft Cloud App Security optie die u moet in-](../../media/mtp-eval-71.png)

16. <span data-ttu-id="c6e21-251">Schuif omlaag en klik **op Voorkeuren opslaan om** de nieuwe integraties te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="c6e21-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Knop of_Save afbeeldingsvoorkeuren waar u op moet klikken](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="c6e21-253">De Microsoft 365 Defender-service starten</span><span class="sxs-lookup"><span data-stu-id="c6e21-253">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="c6e21-254">Vanaf 1 juni 2020 worden door Microsoft automatisch Microsoft 365 Defender-functies voor alle in aanmerking komende tenants.</span><span class="sxs-lookup"><span data-stu-id="c6e21-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="c6e21-255">Zie dit [Artikel van de Microsoft Tech Community over het in aanmerking komen voor](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) licenties voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6e21-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="c6e21-256">Ga naar [Microsoft 365 Beveiligingscentrum.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="c6e21-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="c6e21-257">Navigeer **naar Instellingen** en selecteer Microsoft 365 **Defender.**</span><span class="sxs-lookup"><span data-stu-id="c6e21-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="c6e21-258">Afbeelding of_Microsoft 365 Defender-optie schermafbeelding van de Microsoft 365 beveiligingscentrum Instellingen pagina</span><span class="sxs-lookup"><span data-stu-id="c6e21-258">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="c6e21-259">Zie De Microsoft 365 [Defender in- Microsoft 365 voor een uitgebreidere richtlijn.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="c6e21-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span> 

<span data-ttu-id="c6e21-260">Gefeliciteerd!</span><span class="sxs-lookup"><span data-stu-id="c6e21-260">Congratulations!</span></span> <span data-ttu-id="c6e21-261">U hebt zojuist uw Microsoft 365 proeflaboratorium of testomgeving van Defender gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="c6e21-262">Nu kunt u vertrouwd raken met de Microsoft 365 Defender-gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="c6e21-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="c6e21-263">Bekijk wat u kunt leren van de volgende Microsoft 365 interactieve handleiding van Defender en weet hoe u elk dashboard kunt gebruiken voor uw dagelijkse beveiligingstaken.</span><span class="sxs-lookup"><span data-stu-id="c6e21-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="c6e21-264">Bekijk de interactieve handleiding</span><span class="sxs-lookup"><span data-stu-id="c6e21-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="c6e21-265">Vervolgens kunt u een aanval simuleren en zien hoe de verschillende productmogelijkheden waarschuwingen detecteren, maken en automatisch reageren op een bestandloze aanval op een eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c6e21-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="c6e21-266">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c6e21-266">Next step</span></span>

- <span data-ttu-id="c6e21-267">[Een testwaarschuwing genereren:](generate-test-alert.md) voer een aanvalssimulatie uit in Microsoft 365 Defender-proeflaboratorium.</span><span class="sxs-lookup"><span data-stu-id="c6e21-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>