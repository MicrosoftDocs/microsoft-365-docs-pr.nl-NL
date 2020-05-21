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
ms.openlocfilehash: a41510deb8bad39e2f871babfbcb91a2e43f6dd8
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330837"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="b590c-104">Microsoft Threat Protection-pijlers configureren voor uw proeflabomgeving</span><span class="sxs-lookup"><span data-stu-id="b590c-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="b590c-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="b590c-105">**Applies to:**</span></span>
- <span data-ttu-id="b590c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b590c-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="b590c-107">Het maken van een Microsoft Threat Protection trial lab omgeving en het implementeren ervan is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="b590c-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw proefversie van Microsoft Threat Protection voorbereiden" />
      <br/><span data-ttu-id="b590c-109">Fase 1: Voorbereiden</a></span><span class="sxs-lookup"><span data-stu-id="b590c-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw proefversie van Microsoft Threat Protection instellen" />
      <br/><span data-ttu-id="b590c-111">Fase 2: Setup</a></span><span class="sxs-lookup"><span data-stu-id="b590c-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-labomgeving en eindpunten aan boord" />
      <br/><span data-ttu-id="b590c-113">Fase 3: & configureren</a></span><span class="sxs-lookup"><span data-stu-id="b590c-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="b590c-114">U bevindt zich momenteel in de configuratiefase.</span><span class="sxs-lookup"><span data-stu-id="b590c-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="b590c-115">Voorbereiding is de sleutel tot een succesvolle implementatie.</span><span class="sxs-lookup"><span data-stu-id="b590c-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="b590c-116">In dit artikel wordt u begeleid op de punten die u moet overwegen bij de voorbereiding van de implementatie van Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b590c-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="b590c-117">Pijlers van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b590c-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="b590c-118">Microsoft Threat Protection bestaat uit vier pijlers.</span><span class="sxs-lookup"><span data-stu-id="b590c-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="b590c-119">Hoewel één pijler al waarde kan bieden aan de beveiliging van uw netwerkorganisatie, geeft het inschakelen van de vier pijlers van Microsoft Threat Protection uw organisatie de meeste waarde.</span><span class="sxs-lookup"><span data-stu-id="b590c-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="b590c-120">Image of_Microsoft Threat Protection-oplossing voor gebruikers, Azure Advanced Threat Protection, voor eindpunten Microsoft Defender Advanced Threat Protection, voor cloud-apps, Microsoft Cloud App Security en voor gegevens, Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b590c-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="b590c-121">In deze sectie u het volgende configureren:</span><span class="sxs-lookup"><span data-stu-id="b590c-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="b590c-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b590c-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="b590c-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b590c-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="b590c-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b590c-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="b590c-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b590c-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="b590c-126">Geavanceerde bedreigingsbeveiliging van Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="b590c-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="b590c-127">Sla deze stap over als u Office 365 Advanced Threat Protection al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b590c-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="b590c-128">Er is een PowerShell-module genaamd de *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* die helpt bij het bepalen van een aantal van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="b590c-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="b590c-129">Wanneer u wordt uitgevoerd als beheerder in uw tenant, helpt get-ORCAReport bij het genereren van een beoordeling van de anti-spam-, anti-phish- en andere instellingen voor berichthygiëne.</span><span class="sxs-lookup"><span data-stu-id="b590c-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="b590c-130">U deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="b590c-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="b590c-131">Navigeer naar [office 365-beveiliging &](https://protection.office.com/homepage)  >  **het threat**  >  **managementbeleid**van het Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="b590c-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="b590c-132">![Afbeelding of_Office 365 Beleidspagina & van het Compliance Center Threat Management](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-132">![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="b590c-133">Klik op **ATP anti-phishing**, selecteer **Maken** en vul de beleidsnaam en beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="b590c-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="b590c-134">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b590c-134">Click **Next**.</span></span>
<span data-ttu-id="b590c-135">![Afbeelding of_Office 365 Beveiligings& Compliance Center anti-phishing beleidspagina waar u uw beleid noemen](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-135">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="b590c-136">Bewerk uw Advanced ATP anti-phishing beleid.</span><span class="sxs-lookup"><span data-stu-id="b590c-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="b590c-137">**Geavanceerde phishingdrempel wijzigen** in 2 - **Agressief**.</span><span class="sxs-lookup"><span data-stu-id="b590c-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="b590c-138">Klik **op** de vervolgkeuzelijst Een voorwaarde toevoegen en selecteer uw domein(en) als geadresseerddomein.</span><span class="sxs-lookup"><span data-stu-id="b590c-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="b590c-139">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b590c-139">Click **Next**.</span></span>
<span data-ttu-id="b590c-140">![Afbeelding of_Office 365 Beveiligings& Compliance Center anti-phishing beleidspagina waar u een voorwaarde voor de toepassing ervan toevoegen](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-140">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="b590c-141">Bekijk uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="b590c-141">Review your settings.</span></span> <span data-ttu-id="b590c-142">Klik **op Dit beleid maken** om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="b590c-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="b590c-143">![Afbeelding of_Office 365 Beveiligings& Compliance Center anti-phishing beleidspagina waar u uw instellingen bekijken en op deze beleidsknop maken klikken](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-143">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="b590c-144">Selecteer **ATP Safe-bijlagen** en selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="b590c-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="b590c-145">![Pagina Image of_Office 365 Security & Compliance Center, waar u ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-145">![Image of_Office 365 Security & Compliance Center page where you can turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="b590c-146">Klik op het +-pictogram om een nieuw beleid voor veilige bijlagen te maken en pas het toe als ontvangerdomein op uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="b590c-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="b590c-147">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-147">Click **Save**.</span></span>
<span data-ttu-id="b590c-148">![Pagina Image of_Office 365 Security & Compliance Center, waar u een nieuw beleid voor veilige bijlagen maken](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-148">![Image of_Office 365 Security & Compliance Center page where you can create a new create a new safe attachment policy](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="b590c-149">Selecteer vervolgens het beleid **voor veilige koppelingen van ATP** en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.</span><span class="sxs-lookup"><span data-stu-id="b590c-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="b590c-150">Zorg ervoor dat de optie **Niet volgen wanneer gebruikers op veilige koppelingen klikken** niet is geselecteerd, terwijl de rest van de opties is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b590c-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="b590c-151">Zie [Instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b590c-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="b590c-152">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-152">Click **Save**.</span></span> 
<span data-ttu-id="b590c-153">![Afbeelding of_Office 365 Pagina beveiliging & Compliance Center waaruit blijkt dat de optie Niet bijhouden wanneer gebruikers op veilig klikken niet is geselecteerd](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-153">![Image of_Office 365 Security & Compliance Center page which shows that the option Do not track when users click safe is not selected](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="b590c-154">Selecteer vervolgens het **beleid voor malwarebestrijding,** selecteer de standaardinstelling en kies het potloodpictogram.</span><span class="sxs-lookup"><span data-stu-id="b590c-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="b590c-155">Klik **op Instellingen** en selecteer Ja en gebruik de **standaardmeldingstekst** om **reactie op malwaredetectie**in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="b590c-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="b590c-156">Schakel het **filter voor algemene bijlagetypen** in.</span><span class="sxs-lookup"><span data-stu-id="b590c-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="b590c-157">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-157">Click **Save**.</span></span>
<br><span data-ttu-id="b590c-158">![Image of_Office 365 Security & Compliance Center-pagina waaruit blijkt dat de reactie van de malwaredetectie is ingeschakeld met standaardmelding en het filter voor algemene bijlagen is ingeschakeld](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-158">![Image of_Office 365 Security & Compliance Center page which shows that the malware detection response is turned on with default notification and the common attachment types filter is turned on](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="b590c-159">Navigeer naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Search**Audit  >  **Log search** en schakel Controle in.</span><span class="sxs-lookup"><span data-stu-id="b590c-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="b590c-160">![Afbeelding of_Office 365 pagina beveiligings& Compliance Center, waar u de zoekopdracht Controlelogboek inschakelen](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-160">![Image of_Office 365 Security & Compliance Center page where you can turn on the Audit log search](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="b590c-161">Integreer Office 365 ATP met Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b590c-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="b590c-162">Navigeer naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **management**  >  **Explorer** en selecteer **WDATP-instellingen** in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="b590c-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="b590c-163">Schakel in het dialoogvenster Microsoft Defender ATP-verbinding **Verbinding maken met Windows ATP**in.</span><span class="sxs-lookup"><span data-stu-id="b590c-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="b590c-164">![Pagina Image of_Office 365 Security & Compliance Center waarop u de ATP-verbinding van Windows Defender inschakelen](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-164">![Image of_Office 365 Security & Compliance Center page where you can turn Windows Defender ATP connection on](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="b590c-165">Azure Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="b590c-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="b590c-166">Deze stap overslaan als u Azure Advanced Threat Protection al hebt ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="b590c-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="b590c-167">Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info) > selecteer Meer **bronnen**Azure Advanced  >  **Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="b590c-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="b590c-168">![Afbeelding of_Microsoft 365 Security Center-pagina waar de optie is om Azure Advanced Threat Protection te openen](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-168">![Image of_Microsoft 365 Security Center page where there's an option to open Azure Advanced Threat Protection](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="b590c-169">Klik **op Maken** om de wizard Azure Advanced Threat Protection te starten.</span><span class="sxs-lookup"><span data-stu-id="b590c-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="b590c-170">![Afbeelding of_Azure wizard Pagina Geavanceerde bedreigingsbeveiliging waarop u op Knop Maken moet klikken](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-170">![Image of_Azure Advanced Threat Protection wizard page where you should click Create button](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="b590c-171">Kies **Een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest.**</span><span class="sxs-lookup"><span data-stu-id="b590c-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="b590c-172">![Afbeelding of_Azure welkomstpagina voor Advanced Threat Protection](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-172">![Image of_Azure Advanced Threat Protection welcome page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="b590c-173">Voer uw on-premises active directory-referenties in.</span><span class="sxs-lookup"><span data-stu-id="b590c-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="b590c-174">Dit kan elk gebruikersaccount zijn dat leestoegang heeft tot Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b590c-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="b590c-175">![Afbeelding of_Azure pagina advanced threat protection directory services waar u uw referenties moet plaatsen](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-175">![Image of_Azure Advanced Threat Protection Directory services page where you should put your credentials](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="b590c-176">Kies vervolgens **Sensorsetup downloaden** en het bestand overbrengen naar uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="b590c-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="b590c-177">![Pagina Image of_Azure Advanced Threat Protection waar u Sensor setup downloaden selecteren](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-177">![Image of_Azure Advanced Threat Protection page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="b590c-178">Voer de Azure ATP-sensorsetup uit en begin met het volgen van de wizard.</span><span class="sxs-lookup"><span data-stu-id="b590c-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="b590c-179">![Pagina Afbeelding of_Azure Advanced Threat Protection, waar u naast de wizard Azure ATP-sensor moet klikken](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-179">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="b590c-180">Klik op **Volgende** bij het type sensorimplementatie.</span><span class="sxs-lookup"><span data-stu-id="b590c-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="b590c-181">![Pagina Afbeelding of_Azure Advanced Threat Protection, waar u naast de wizard Azure ATP-sensor moet klikken](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-181">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="b590c-182">Kopieer de toegangssleutel zoals u deze vervolgens in de wizard moet invoeren.</span><span class="sxs-lookup"><span data-stu-id="b590c-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="b590c-183">![Afbeelding of_the op sensoren pagina waar u de toegangssleutel moet kopiëren die u moet invoeren in de volgende wizard Azure ATP-sensorinstelling](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-183">![Image of_the sensors page where you should copy the access key that you need to enter in the next Azure ATP sensor setup wizard page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="b590c-184">Kopieer de toegangssleutel naar de wizard en klik op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="b590c-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="b590c-185">![Afbeelding of_Azure wizard van de Azure ATP-sensor van Advanced Threat Protection, waar u de toegangssleutel moet verstrekken en vervolgens op de installatieknop moet klikken](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-185">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="b590c-186">Gefeliciteerd, u hebt Azure Advanced Threat Protection geconfigureerd op uw domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="b590c-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="b590c-187">![Image of_Azure Advanced Threat Protection Azure ATP-sensorwizard installatievoltooiing waar u op de knop Voltooien moet klikken](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-187">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="b590c-188">Selecteer windows **defender ATP**in de sectie Azure Azure [Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) en schakel de schakelaar in.</span><span class="sxs-lookup"><span data-stu-id="b590c-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="b590c-189">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-189">Click **Save**.</span></span> 
<span data-ttu-id="b590c-190">![Pagina of_the Azure Azure ATP-instellingen waar u de ATP-schakelaar van Windows Defender moet inschakelen](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-190">![Image of_the Azure Azure ATP settings page where you should turn the Windows Defender ATP toggle on](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="b590c-191">Windows Defender ATP is omgedoopt tot Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b590c-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="b590c-192">Rebranding veranderingen in al onze portals worden uitgerold voor consistentie.</span><span class="sxs-lookup"><span data-stu-id="b590c-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="b590c-193">Beveiliging van Microsoft Cloud-apps configureren</span><span class="sxs-lookup"><span data-stu-id="b590c-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="b590c-194">Sla deze stap over als u Microsoft Cloud App Security al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b590c-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="b590c-195">Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info)Meer  >  **resources**Microsoft Cloud  >  **App Security**.</span><span class="sxs-lookup"><span data-stu-id="b590c-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="b590c-196">![Afbeelding of_Microsoft 365 Security Center-pagina waar u de Microsoft Cloud App-kaart zien en op de geopende knop klikken](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-196">![Image of_Microsoft 365 Security Center page where you can see Microsoft Cloud App card and should click the open button](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="b590c-197">Selecteer **Azure ATP-gegevensintegratie inschakelen**bij de informatieprompt om Azure ATP te integreren.</span><span class="sxs-lookup"><span data-stu-id="b590c-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="b590c-198">![Afbeelding of_the informatieprompt om Azure ATP te integreren, waarbij u de koppeling Azure ATP-gegevensintegratie inschakelen moet selecteren](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-198">![Image of_the information prompt to integrate Azure ATP where you should select the Enable Azure ATP data integration link](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="b590c-199">Als u deze prompt niet ziet, kan dit betekenen dat uw Azure ATP-gegevensintegratie al is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b590c-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="b590c-200">Als u het echter niet zeker weet, neemt u contact op met uw IT-beheerder om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="b590c-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="b590c-201">Ga naar **Instellingen,** schakel de inschakelactie op **Azure ATP-integratie** in en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="b590c-202">![Pagina of_the instellingen van afbeelding waar u de azure ATP-integratie-schakelaar moet inschakelen en vervolgens op Opslaan moet klikken](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-202">![Image of_the settings page where you should turn the Azure ATP integration toggle on then click save](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="b590c-203">Voor nieuwe Azure ATP-exemplaren wordt deze integratie-schakelaar automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b590c-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="b590c-204">Controleer of uw Azure ATP-integratie is ingeschakeld voordat u doorgaat met de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="b590c-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="b590c-205">Selecteer onder de instellingen voor detectie van de cloud de OPTIE **Microsoft Defender ATP-integratie**en schakel vervolgens de integratie in.</span><span class="sxs-lookup"><span data-stu-id="b590c-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="b590c-206">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-206">Click **Save**.</span></span>
<span data-ttu-id="b590c-207">![Afbeelding of_the Microsoft Defender ATP-pagina waar het selectievakje voor niet-goedgekeurde apps onder Microsoft Defender ATP-integratie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b590c-207">![Image of_the Microsoft Defender ATP page where the block unsanctioned apps checkbox under Microsoft Defender ATP integration is selected.</span></span> <span data-ttu-id="b590c-208">Klik op Opslaan.](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-208">Click save.](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="b590c-209">Selecteer onder Instellingen voor detectie van de cloud de optie **Gebruikersverrijking**en schakel vervolgens de integratie met Azure Active Directory in.</span><span class="sxs-lookup"><span data-stu-id="b590c-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="b590c-210">![Afbeelding van de sectie Gebruikersverrijking waarin het selectievakje gedetecteerde gebruikers-id's verrijken met Azure Active Directory-gebruikersnamen is ingeschakeld](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-210">![Image of User enrichment section where the enrich discovered user identifiers with Azure Active Directory usernames checkbox is selected](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="b590c-211">Geavanceerde bedreigingsbeveiliging van Microsoft Defender configureren</span><span class="sxs-lookup"><span data-stu-id="b590c-211">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="b590c-212">Sla deze stap over als u Microsoft Defender Advanced Threat Protection al hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b590c-212">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="b590c-213">Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info)Meer  >  **bronnen**Microsoft Defender  >  **Security Center**.</span><span class="sxs-lookup"><span data-stu-id="b590c-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="b590c-214">Klik **op Openen**.</span><span class="sxs-lookup"><span data-stu-id="b590c-214">Click **Open**.</span></span>
<br><span data-ttu-id="b590c-215">![Afbeelding of_Microsoft Defender Security Center-optie op de pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-215">![Image of_Microsoft Defender Security Center option in the Microsoft 365 Security Center page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="b590c-216">Volg de wizard Geavanceerde bedreigingsbeveiliging van Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b590c-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="b590c-217">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b590c-217">Click **Next**.</span></span> 
<br><span data-ttu-id="b590c-218">![Afbeelding of_the microsoft Defender Security Center welkomstwizardpagina](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-218">![Image of_the Microsoft Defender Security Center welcome wizard page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="b590c-219">Kies op basis van de locatie voor gegevensopslag, het beleid voor gegevensbehoud, de grootte van de organisatie en de opt-in voor preview-functies.</span><span class="sxs-lookup"><span data-stu-id="b590c-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="b590c-220">![Afbeelding of_the pagina om uw gegevensopslagland, bewaarbeleid en organisatiegrootte te selecteren.</span><span class="sxs-lookup"><span data-stu-id="b590c-220">![Image of_the page to select your data storage country, retention policy, and organization size.</span></span> <span data-ttu-id="b590c-221">Klik op de volgende wanneer u klaar bent met selecteren.](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-221">Click next when you're done selecting.](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="b590c-222">U sommige instellingen, zoals de locatie voor gegevensopslag, niet achteraf wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b590c-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="b590c-223">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b590c-223">Click **Next**.</span></span> 

4. <span data-ttu-id="b590c-224">Klik **op Doorgaan** en informeer uw Microsoft Defender ATP-tenant.</span><span class="sxs-lookup"><span data-stu-id="b590c-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="b590c-225">![Afbeelding of_the pagina waarin u wordt gevraagd op de knop Doorgaan te klikken om uw cloudexemplaar te maken](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-225">![Image of_the page prompting you click the continue button to create your cloud instance](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="b590c-226">Je eindpunten aan boord via Groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren naar Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b590c-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="b590c-227">Voor de eenvoud maakt deze gids gebruik van het lokale script.</span><span class="sxs-lookup"><span data-stu-id="b590c-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="b590c-228">Klik **op Pakket downloaden** en kopieer het onboardingscript naar uw eindpunt(en).</span><span class="sxs-lookup"><span data-stu-id="b590c-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="b590c-229">![Afbeelding of_page u vraagt op de knop Pakket downloaden om het onboardingscript naar uw eindpunt of eindpunten te kopiëren](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-229">![Image of_page prompting you click the Download package button to copy the onboarding script to your endpoint or endpoints](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="b590c-230">Voer op uw eindpunt het onboarding-script uit als beheerder en kies Y.</span><span class="sxs-lookup"><span data-stu-id="b590c-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="b590c-231">![Afbeelding of_the commandline waar u het onboarding-script uitvoert en Y kiest om door te gaan](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-231">![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="b590c-232">Gefeliciteerd, je hebt je eerste eindpunt aan boord.</span><span class="sxs-lookup"><span data-stu-id="b590c-232">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Afbeelding of_the commandline waar u de bevestiging krijgt dat u aan boord van uw eerste eindpunt bent.](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="b590c-235">Kopieer de detectietest vanuit de wizard Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b590c-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="b590c-236">![Afbeelding of_the een detectieteststap uitvoeren waarbij u op Kopiëren klikt om het detectietestscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-236">![Image of_the run a detection test step where you should click Copy to copy the detection test script that you should paste in the command prompt](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="b590c-237">Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer het uit.</span><span class="sxs-lookup"><span data-stu-id="b590c-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="b590c-238">![Afbeelding of_command prompt waar u het PowerShell-script moet kopiëren naar een opdrachtprompt met verhoogde bevoegdheid en deze moet uitvoeren](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-238">![Image of_command prompt where you should copy the PowerShell script to an elevated command prompt and run it](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="b590c-239">Selecteer **Microsoft Defender ATP gebruiken** in de wizard.</span><span class="sxs-lookup"><span data-stu-id="b590c-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="b590c-240">![Afbeelding of_the bevestigingsprompt van de wizard waarin u moet klikken op Microsoft Defender ATP gebruiken](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-240">![Image of_the confirmation prompt from the wizard where you should click Start using Microsoft Defender ATP](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="b590c-241">Ga naar het [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="b590c-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="b590c-242">Ga naar **Instellingen** en selecteer **Geavanceerde functies**.</span><span class="sxs-lookup"><span data-stu-id="b590c-242">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="b590c-243">![Menu Instellingen voor het pop-of_Microsoft-beveiligingscentrum van Defender, waar u geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-243">![Image of_Microsoft Defender Security Center Settings menu where you should select Advanced features](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="b590c-244">Schakel de integratie met **Azure Advanced Threat Protection**in.</span><span class="sxs-lookup"><span data-stu-id="b590c-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="b590c-245">![Afbeelding of_Microsoft Defender Security Center Geavanceerde functies, Azure Advanced Threat Protection-optie schakelen die u moet inschakelen](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-245">![Image of_Microsoft Defender Security Center Advanced features, Azure Advanced Threat Protection option toggle that you need to turn on](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="b590c-246">Schakel de integratie met **Office 365 Threat Intelligence in.**</span><span class="sxs-lookup"><span data-stu-id="b590c-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="b590c-247">![Afbeelding of_Microsoft Defender Security Center Geavanceerde functies, Office 365 Threat Intelligence-optie ingeschakeld die u moet inschakelen](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-247">![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="b590c-248">Integratie met **Microsoft Cloud App Security**inschakelen.</span><span class="sxs-lookup"><span data-stu-id="b590c-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="b590c-249">![Afbeelding of_Microsoft Defender Security Center Geavanceerde functies, Microsoft Cloud App Security-optie schakelen die u moet inschakelen](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-249">![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security option toggle that you need to turn on](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="b590c-250">Schuif omlaag en klik op **Voorkeuren opslaan** om de nieuwe integraties te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="b590c-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="b590c-251">![Knop afbeelding of_Save voorkeuren waarop u moet klikken](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-251">![Image of_Save preferences button that you need to click](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b590c-252">Microsoft Threat Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="b590c-252">Turn on Microsoft Threat Protection</span></span>
1. <span data-ttu-id="b590c-253">Ga naar [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="b590c-253">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="b590c-254">Navigeer naar **Instellingen** en selecteer **Microsoft Bedreigingsbeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="b590c-254">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>
<br><span data-ttu-id="b590c-255">![Afbeelding of_Microsoft optie Bedreigingsbescherming van de pagina Instellingen van het Microsoft 365 Security Center](../../media/mtp-eval-72b.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-255">![Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page ](../../media/mtp-eval-72b.png)</span></span> <br>

2. <span data-ttu-id="b590c-256">Schakel het selectievakje **Microsoft Bedreigingsbeveiliging inschakelen in** en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b590c-256">Select the **Turn on Microsoft Threat Protection** checkbox, then click **Save**.</span></span>
<br><span data-ttu-id="b590c-257">![Afbeelding of_Microsoft optie Bedreigingsbescherming van de pagina Instellingen van het Microsoft 365 Security Center](../../media/mtp-eval-72c.png)</span><span class="sxs-lookup"><span data-stu-id="b590c-257">![Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page ](../../media/mtp-eval-72c.png)</span></span> <br>

<span data-ttu-id="b590c-258">Gefeliciteerd!</span><span class="sxs-lookup"><span data-stu-id="b590c-258">Congratulations!</span></span> <span data-ttu-id="b590c-259">U hebt zojuist uw Microsoft Threat Protection trial lab-omgeving gemaakt!</span><span class="sxs-lookup"><span data-stu-id="b590c-259">You've just created your Microsoft Threat Protection trial lab environment!</span></span> <span data-ttu-id="b590c-260">U nu een aanval simuleren en zien hoe de cross-productmogelijkheden detecteren, waarschuwingen maken en automatisch reageren op een bestandsloze aanval op een eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b590c-260">You can now simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b590c-261">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b590c-261">Next steps</span></span>
<span data-ttu-id="b590c-262">[Een testwaarschuwing genereren](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="b590c-262">[Generate a test alert](generate-test-alert.md).</span></span>
