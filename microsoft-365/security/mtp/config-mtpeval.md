---
title: Microsoft Threat Protection-pijlers configureren voor de proeflabomgeving
description: Microsoft Threat Protection-pijlers, Office 365 ATP, Azure ATP, Microsoft Cloud App Security en Microsoft Defender ATP configureren voor uw proeflabomgeving
keywords: microsoft Threat Protection trial, Microsoft Threat Protection trial configuration configureren, Microsoft Threat Protection pillars, Microsoft Threat Protection pillars configureren
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049507"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="e66fb-104">Microsoft Threat Protection-pijlers configureren voor uw proeflabomgeving</span><span class="sxs-lookup"><span data-stu-id="e66fb-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="e66fb-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="e66fb-105">**Applies to:**</span></span>
- <span data-ttu-id="e66fb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e66fb-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="e66fb-107">Het maken van een Microsoft Threat Protection trial lab omgeving en het implementeren ervan is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="e66fb-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw proefversie van Microsoft Threat Protection voorbereiden" />
      <br/><span data-ttu-id="e66fb-109">Fase 1: Voorbereiden</a></span><span class="sxs-lookup"><span data-stu-id="e66fb-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw proefversie van Microsoft Threat Protection instellen" />
      <br/><span data-ttu-id="e66fb-111">Fase 2: Setup</a></span><span class="sxs-lookup"><span data-stu-id="e66fb-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-labomgeving en eindpunten aan boord" />
      <br/><span data-ttu-id="e66fb-113">Fase 3: & configureren</a></span><span class="sxs-lookup"><span data-stu-id="e66fb-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="e66fb-114">U bevindt zich momenteel in de configuratiefase.</span><span class="sxs-lookup"><span data-stu-id="e66fb-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="e66fb-115">Voorbereiding is de sleutel tot een succesvolle implementatie.</span><span class="sxs-lookup"><span data-stu-id="e66fb-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="e66fb-116">In dit artikel wordt u begeleid op de punten die u moet overwegen bij de voorbereiding van de implementatie van Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e66fb-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="e66fb-117">Pijlers van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e66fb-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="e66fb-118">Microsoft Threat Protection bestaat uit vier pijlers.</span><span class="sxs-lookup"><span data-stu-id="e66fb-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="e66fb-119">Hoewel één pijler al waarde kan bieden aan de beveiliging van uw netwerkorganisatie, geeft het inschakelen van de vier pijlers van Microsoft Threat Protection uw organisatie de meeste waarde.</span><span class="sxs-lookup"><span data-stu-id="e66fb-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Afbeelding of_page](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="e66fb-121">In deze sectie u het volgende configureren:</span><span class="sxs-lookup"><span data-stu-id="e66fb-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="e66fb-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e66fb-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="e66fb-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e66fb-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="e66fb-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e66fb-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="e66fb-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e66fb-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="e66fb-126">Geavanceerde bedreigingsbeveiliging van Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="e66fb-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="e66fb-127">Sla deze stap over als u Office 365 Advanced Threat Protection al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e66fb-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="e66fb-128">Er is een PowerShell-module genaamd de *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* die helpt bij het bepalen van een aantal van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="e66fb-129">Wanneer u wordt uitgevoerd als beheerder in uw tenant, helpt get-ORCAReport bij het genereren van een beoordeling van de anti-spam-, anti-phish- en andere instellingen voor berichthygiëne.</span><span class="sxs-lookup"><span data-stu-id="e66fb-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="e66fb-130">U deze https://www.powershellgallery.com/packages/ORCA/module downloaden van.</span><span class="sxs-lookup"><span data-stu-id="e66fb-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="e66fb-131">Navigeer naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat Management** > **Policy**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="e66fb-132">![Afbeelding of_page](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="e66fb-133">Klik op **ATP anti-phishing**, selecteer **Maken** en vul de beleidsnaam en beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="e66fb-134">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-134">Click **Next**.</span></span>
<span data-ttu-id="e66fb-135">![Afbeelding of_page](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="e66fb-136">Bewerk uw Advanced ATP anti-phishing beleid.</span><span class="sxs-lookup"><span data-stu-id="e66fb-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="e66fb-137">**Geavanceerde phishingdrempel wijzigen** in 2 - **Agressief**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="e66fb-138">Klik **op** de vervolgkeuzelijst Een voorwaarde toevoegen en selecteer uw domein(en) als geadresseerddomein.</span><span class="sxs-lookup"><span data-stu-id="e66fb-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="e66fb-139">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-139">Click **Next**.</span></span>
<span data-ttu-id="e66fb-140">![Afbeelding of_page](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="e66fb-141">Bekijk uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-141">Review your settings.</span></span> <span data-ttu-id="e66fb-142">Klik **op Dit beleid maken** om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="e66fb-143">![Afbeelding of_page](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="e66fb-144">Selecteer **ATP Safe-bijlagen** en selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="e66fb-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="e66fb-145">![Afbeelding of_page](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="e66fb-146">Klik op het +-pictogram om een nieuw beleid voor veilige bijlagen te maken en pas het toe als ontvangerdomein op uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="e66fb-147">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-147">Click **Save**.</span></span>
<span data-ttu-id="e66fb-148">![Afbeelding of_page](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="e66fb-149">Selecteer vervolgens het beleid **voor veilige koppelingen van ATP** en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="e66fb-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="e66fb-150">Zorg ervoor dat de optie **Niet volgen wanneer gebruikers op veilige koppelingen klikken** niet is geselecteerd, terwijl de rest van de opties is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="e66fb-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="e66fb-151">Zie [Instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e66fb-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="e66fb-152">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-152">Click **Save**.</span></span> 
<span data-ttu-id="e66fb-153">![Afbeelding of_page](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="e66fb-154">Selecteer vervolgens het **beleid voor malwarebestrijding,** selecteer de standaardinstelling en kies het potloodpictogram.</span><span class="sxs-lookup"><span data-stu-id="e66fb-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="e66fb-155">Klik **op Instellingen** en selecteer Ja en gebruik de **standaardmeldingstekst** om **reactie op malwaredetectie**in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="e66fb-156">Schakel het **filter voor algemene bijlagetypen** in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="e66fb-157">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-157">Click **Save**.</span></span>
<br><span data-ttu-id="e66fb-158">![Afbeelding of_page](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="e66fb-159">Navigeer naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** en schakel Controle in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="e66fb-160">![Afbeelding of_page](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="e66fb-161">Integreer Office 365 ATP met Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e66fb-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="e66fb-162">Navigeer naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** en selecteer **WDATP-instellingen** in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="e66fb-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="e66fb-163">Schakel in het dialoogvenster Microsoft Defender ATP-verbinding **Verbinding maken met Windows ATP**in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="e66fb-164">![Afbeelding of_page](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="e66fb-165">Azure Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="e66fb-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="e66fb-166">Deze stap overslaan als u Azure Advanced Threat Protection al hebt ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e66fb-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="e66fb-167">Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info) > selecteer Meer **bronnen** > **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="e66fb-168">![Afbeelding of_page](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="e66fb-169">Klik **op Maken** om de wizard Azure Advanced Threat Protection te starten.</span><span class="sxs-lookup"><span data-stu-id="e66fb-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="e66fb-170">![Afbeelding of_page](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="e66fb-171">Kies **Een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest.**</span><span class="sxs-lookup"><span data-stu-id="e66fb-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="e66fb-172">![Afbeelding of_page](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="e66fb-173">Voer uw on-premises active directory-referenties in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="e66fb-174">Dit kan elk gebruikersaccount zijn dat leestoegang heeft tot Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e66fb-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="e66fb-175">![Afbeelding of_page](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="e66fb-176">Kies vervolgens **Sensorsetup downloaden** en het bestand overbrengen naar uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="e66fb-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="e66fb-177">![Afbeelding of_page](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="e66fb-178">Voer de Azure ATP-sensorsetup uit en begin met het volgen van de wizard.</span><span class="sxs-lookup"><span data-stu-id="e66fb-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="e66fb-179">![Afbeelding of_page](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="e66fb-180">Klik op **Volgende** bij het type sensorimplementatie.</span><span class="sxs-lookup"><span data-stu-id="e66fb-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="e66fb-181">![Afbeelding of_page](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="e66fb-182">Kopieer de toegangssleutel zoals u deze vervolgens in de wizard moet invoeren.</span><span class="sxs-lookup"><span data-stu-id="e66fb-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="e66fb-183">![Afbeelding of_page](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="e66fb-184">Kopieer de toegangssleutel naar de wizard en klik op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="e66fb-185">![Afbeelding of_page](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="e66fb-186">Gefeliciteerd, u hebt Azure Advanced Threat Protection geconfigureerd op uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="e66fb-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="e66fb-187">![Afbeelding of_page](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="e66fb-188">Selecteer windows **defender ATP**in de sectie Azure Azure [Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) en schakel de schakelaar in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="e66fb-189">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-189">Click **Save**.</span></span> 
<span data-ttu-id="e66fb-190">![Afbeelding of_page](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="e66fb-191">Windows Defender ATP is omgedoopt tot Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e66fb-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="e66fb-192">Rebranding veranderingen in al onze portals worden uitgerold voor consistentie.</span><span class="sxs-lookup"><span data-stu-id="e66fb-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="e66fb-193">Beveiliging van Microsoft Cloud-apps configureren</span><span class="sxs-lookup"><span data-stu-id="e66fb-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="e66fb-194">Sla deze stap over als u Microsoft Cloud App Security al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e66fb-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="e66fb-195">Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Meer resources** > **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="e66fb-196">![Afbeelding of_page](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="e66fb-197">Selecteer **Azure ATP-gegevensintegratie inschakelen**bij de informatieprompt om Azure ATP te integreren.</span><span class="sxs-lookup"><span data-stu-id="e66fb-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="e66fb-198">![Afbeelding of_page](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="e66fb-199">Als u deze prompt niet ziet, kan dit betekenen dat uw Azure ATP-gegevensintegratie al is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e66fb-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="e66fb-200">Als u het echter niet zeker weet, neemt u contact op met uw IT-beheerder om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="e66fb-201">Ga naar **Instellingen,** schakel de inschakelactie op **Azure ATP-integratie** in en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="e66fb-202">![Afbeelding of_page](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="e66fb-203">Voor nieuwe Azure ATP-exemplaren wordt deze integratie-schakelaar automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e66fb-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="e66fb-204">Controleer of uw Azure ATP-integratie is ingeschakeld voordat u doorgaat met de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="e66fb-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="e66fb-205">Selecteer onder de instellingen voor detectie van de cloud de OPTIE **Microsoft Defender ATP-integratie**en schakel vervolgens de integratie in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="e66fb-206">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-206">Click **Save**.</span></span>
<span data-ttu-id="e66fb-207">![Afbeelding of_page](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="e66fb-208">Selecteer onder Instellingen voor detectie van de cloud de optie **Gebruikersverrijking**en schakel vervolgens de integratie met Azure Active Directory in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="e66fb-209">![Afbeelding of_page](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e66fb-210">Geavanceerde bedreigingsbeveiliging van Microsoft Defender configureren</span><span class="sxs-lookup"><span data-stu-id="e66fb-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="e66fb-211">Sla deze stap over als u Microsoft Defender Advanced Threat Protection al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e66fb-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="e66fb-212">Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Meer bronnen** > **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="e66fb-213">Klik **op Openen**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-213">Click **Open**.</span></span>
<br><span data-ttu-id="e66fb-214">![Afbeelding of_page](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="e66fb-215">Volg de wizard Geavanceerde bedreigingsbeveiliging van Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e66fb-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="e66fb-216">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-216">Click **Next**.</span></span> 
<br><span data-ttu-id="e66fb-217">![Afbeelding of_page](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="e66fb-218">Kies op basis van de locatie voor gegevensopslag, het beleid voor gegevensbehoud, de grootte van de organisatie en de opt-in voor preview-functies.</span><span class="sxs-lookup"><span data-stu-id="e66fb-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="e66fb-219">![Afbeelding of_page](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="e66fb-220">U sommige instellingen, zoals de locatie voor gegevensopslag, niet achteraf wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="e66fb-221">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-221">Click **Next**.</span></span> 

4. <span data-ttu-id="e66fb-222">Klik **op Doorgaan** en informeer uw Microsoft Defender ATP-tenant.</span><span class="sxs-lookup"><span data-stu-id="e66fb-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="e66fb-223">![Afbeelding of_page](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="e66fb-224">Je eindpunten aan boord via Groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren naar Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e66fb-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="e66fb-225">Voor de eenvoud maakt deze gids gebruik van het lokale script.</span><span class="sxs-lookup"><span data-stu-id="e66fb-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="e66fb-226">Klik **op Pakket downloaden** en kopieer het onboardingscript naar uw eindpunt(en).</span><span class="sxs-lookup"><span data-stu-id="e66fb-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="e66fb-227">![Afbeelding of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="e66fb-228">Voer op uw eindpunt het onboarding-script uit als beheerder en kies Y.</span><span class="sxs-lookup"><span data-stu-id="e66fb-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="e66fb-229">![Afbeelding of_page](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="e66fb-230">Gefeliciteerd, je hebt je eerste eindpunt aan boord.</span><span class="sxs-lookup"><span data-stu-id="e66fb-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Afbeelding of_page](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="e66fb-232">Kopieer de detectietest vanuit de wizard Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e66fb-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="e66fb-233">![Afbeelding of_page](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="e66fb-234">Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer het uit.</span><span class="sxs-lookup"><span data-stu-id="e66fb-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="e66fb-235">![Afbeelding of_page](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="e66fb-236">Selecteer **Microsoft Defender ATP gebruiken** in de wizard.</span><span class="sxs-lookup"><span data-stu-id="e66fb-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="e66fb-237">![Afbeelding of_page](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="e66fb-238">Ga naar het [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="e66fb-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="e66fb-239">Ga naar **Instellingen** en selecteer **Geavanceerde functies**.</span><span class="sxs-lookup"><span data-stu-id="e66fb-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="e66fb-240">![Afbeelding of_page](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="e66fb-241">Schakel de integratie met **Azure Advanced Threat Protection**in.</span><span class="sxs-lookup"><span data-stu-id="e66fb-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="e66fb-242">![Afbeelding of_page](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="e66fb-243">Schakel de integratie met **Office 365 Threat Intelligence in.**</span><span class="sxs-lookup"><span data-stu-id="e66fb-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="e66fb-244">![Afbeelding of_page](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="e66fb-245">Integratie met **Microsoft Cloud App Security**inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="e66fb-246">![Afbeelding of_page](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="e66fb-247">Schuif omlaag en klik op **Voorkeuren opslaan** om de nieuwe integraties te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="e66fb-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="e66fb-248">![Afbeelding of_page](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="e66fb-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="e66fb-249">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e66fb-249">Next steps</span></span>
<span data-ttu-id="e66fb-250">[Schakel Microsoft Threat Protection in](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) en [genereer vervolgens een testwaarschuwing.](generate-test-alert.md)</span><span class="sxs-lookup"><span data-stu-id="e66fb-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
