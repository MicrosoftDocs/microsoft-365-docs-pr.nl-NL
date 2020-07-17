---
title: Uw Microsoft Threat Protection-proefomgeving instellen
description: Toegang tot Microsoft 365 Security Center en vervolgens uw Microsoft Threat Protection-proeflabomgeving instellen
keywords: Microsoft Threat Protection trial setup, probeer Microsoft Threat Protection, Microsoft Threat Protection evaluatie lab setup
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
ms.openlocfilehash: 6cba773d0c4bea259db151d5a8f1d8e03954a045
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717293"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="0947b-104">Uw Microsoft Threat Protection-proefomgeving instellen</span><span class="sxs-lookup"><span data-stu-id="0947b-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="0947b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0947b-105">**Applies to:**</span></span>
- <span data-ttu-id="0947b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0947b-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="0947b-107">Het maken van een Microsoft Threat Protection-proeflabomgeving en het implementeren ervan is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="0947b-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-evaluatielab voorbereiden" />
      <br/><span data-ttu-id="0947b-109">Fase 1: Voorbereiden</a></span><span class="sxs-lookup"><span data-stu-id="0947b-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-evaluatielab instellen" />
      <br/><span data-ttu-id="0947b-111">Fase 2: Setup</a></span><span class="sxs-lookup"><span data-stu-id="0947b-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-proeflabomgeving en aan boord van uw eindpunten" />
      <br/><span data-ttu-id="0947b-113">Fase 3: & onboard configureren</a></span><span class="sxs-lookup"><span data-stu-id="0947b-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="0947b-114">U bevindt zich momenteel in de opgezette fase.</span><span class="sxs-lookup"><span data-stu-id="0947b-114">You are currently in the set up phase.</span></span> <span data-ttu-id="0947b-115">Neem de eerste stappen om toegang te krijgen tot Microsoft 365 Security Center en stel vervolgens uw proeflabomgeving in.</span><span class="sxs-lookup"><span data-stu-id="0947b-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="0947b-116">Meld u aan voor een Office 365- of Azure Active Directory-abonnement om een *.onmicrosoft.com* tenant te genereren waarmee u zich aanmelden voor uw Microsoft 365 E5-licentie.</span><span class="sxs-lookup"><span data-stu-id="0947b-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="0947b-117">Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, u de stappen voor het maken van proef tenant voor Office 365 E5 overslaan.</span><span class="sxs-lookup"><span data-stu-id="0947b-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="0947b-118">In deze fase wordt u begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="0947b-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="0947b-119">Een proef tenant voor Office 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="0947b-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="0947b-120">Microsoft 365-proefabonnement inschakelen</span><span class="sxs-lookup"><span data-stu-id="0947b-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="0947b-121">Een proef tenant voor Office 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="0947b-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="0947b-122">Als u al een bestaand Office 365- of Azure Active Directory-abonnement hebt, u de stappen voor het maken van proef tenant voor Office 365 E5 overslaan.</span><span class="sxs-lookup"><span data-stu-id="0947b-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="0947b-123">Ga naar de [Office 365 E5-productportal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **Gratis proefversie**.</span><span class="sxs-lookup"><span data-stu-id="0947b-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="0947b-124">![Afbeelding of_Office gratis proefpagina 365 E5](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="0947b-125">Voltooi de proefregistratie door uw e-mailadres (persoonlijk of zakelijk) in te voeren.</span><span class="sxs-lookup"><span data-stu-id="0947b-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="0947b-126">Klik **op Account instellen**.</span><span class="sxs-lookup"><span data-stu-id="0947b-126">Click **Set up account**.</span></span>
<span data-ttu-id="0947b-127">![Image of_Office 365 E5 trial registration setup pagina](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="0947b-128">Vul uw voornaam, achternaam, bedrijfstelefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.</span><span class="sxs-lookup"><span data-stu-id="0947b-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Afbeelding of_Office 365 E5-testregistratie-installatiepagina waarin wordt gevraagd om naam, telefoon en bedrijfsgegevens](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="0947b-130">Het land of de regio die u hier instelt, bepaalt de regio van het datacenter die uw Office 365 ontvangt.</span><span class="sxs-lookup"><span data-stu-id="0947b-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="0947b-131">Kies uw verificatievoorkeur: via een sms of oproep.</span><span class="sxs-lookup"><span data-stu-id="0947b-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="0947b-132">Klik **op Verificatiecode verzenden**.</span><span class="sxs-lookup"><span data-stu-id="0947b-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="0947b-133">![Image of_Office 365 E5 trial registration setup pagina vragen om verificatie voorkeur](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="0947b-134">Stel de aangepaste domeinnaam in voor uw tenant en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0947b-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="0947b-135">![Afbeelding of_Office 365 E5-testregistratieregistratiepagina waar u uw aangepaste domeinnaam instellen](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="0947b-136">Stel de eerste identiteit in die een globale beheerder voor de tenant zal zijn.</span><span class="sxs-lookup"><span data-stu-id="0947b-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="0947b-137">Geef **naam** en **wachtwoord in**.</span><span class="sxs-lookup"><span data-stu-id="0947b-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="0947b-138">Klik **op Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="0947b-138">Click **Sign up**.</span></span>
<span data-ttu-id="0947b-139">![Afbeelding of_Office 365 E5-testregistratie-instellingspagina waar u uw bedrijfsidentiteit instellen](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="0947b-140">Klik **op Ga naar Setup** om de inrichting van office 365 E5-proef tenanten te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0947b-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="0947b-141">![Afbeelding van de installatiepagina van office 365 E5-proefregistratie wordt gevraagd op de knop Installatie gaan te klikken](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="0947b-142">Verbind uw bedrijfsdomein met de Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="0947b-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="0947b-143">[Optioneel] Kies **Een domein verbinden dat u al bezit** en typ uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="0947b-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="0947b-144">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0947b-144">Click **Next**.</span></span>
<br><span data-ttu-id="0947b-145">![Afbeelding of_Office 365 E5 Setup-pagina waar u uw aanmelding en e-mail moet personaliseren](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="0947b-146">U moet een TXT- of MX-record toevoegen om het domeineigendom te valideren.</span><span class="sxs-lookup"><span data-stu-id="0947b-146">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="0947b-147">Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="0947b-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="0947b-148">![Afbeelding of_Office 365 E5-instellingspagina waar u een TXT MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="0947b-149">[Optioneel] Maak meer gebruikersaccounts voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0947b-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="0947b-150">U deze stap overslaan door op **Volgende**te klikken.</span><span class="sxs-lookup"><span data-stu-id="0947b-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="0947b-151">![Afbeelding of_Office 365 E5-instellingspagina waar u meer gebruikers toevoegen](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="0947b-152">[Optioneel] Office-apps downloaden.</span><span class="sxs-lookup"><span data-stu-id="0947b-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="0947b-153">Klik **op Volgende** om deze stap over te slaan.</span><span class="sxs-lookup"><span data-stu-id="0947b-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="0947b-154">![Afbeelding of_Office 365 E5-pagina waar u uw Office-apps installeren](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="0947b-155">[Optioneel] E-mailberichten migreren.</span><span class="sxs-lookup"><span data-stu-id="0947b-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="0947b-156">Nogmaals, u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="0947b-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="0947b-157">![Afbeelding of_Office 365 E5 waar u instellen of e-mailberichten moeten worden gemigreerd of niet](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="0947b-158">Kies online services.</span><span class="sxs-lookup"><span data-stu-id="0947b-158">Choose online services.</span></span> <span data-ttu-id="0947b-159">Selecteer **Exchange** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0947b-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="0947b-160">![Afbeelding of_Office 365 E5 waar u uw online diensten kiezen](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="0947b-161">Voeg MX-, CNAME- en TXT-records toe aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="0947b-161">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="0947b-162">Selecteer **Verifiëren**wanneer u voltooid bent.</span><span class="sxs-lookup"><span data-stu-id="0947b-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="0947b-163">![Afbeelding of_Office 365 E5 hier u uw DNS-records toevoegen](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="0947b-164">Gefeliciteerd, u hebt de inrichting van uw Office 365-tenant voltooid.</span><span class="sxs-lookup"><span data-stu-id="0947b-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="0947b-165">![Bevestigingspagina van image of_Office 365 E5 setup](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="0947b-166">Microsoft 365-proefabonnement inschakelen</span><span class="sxs-lookup"><span data-stu-id="0947b-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="0947b-167">Als u zich aanmeldt voor een proefabonnement, u 25 gebruikerslicenties voor een maand gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0947b-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="0947b-168">Zie [Probeer of koop een M365-abonnement](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0947b-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="0947b-169">Klik in [microsoft 365-beheercentrum](https://admin.microsoft.com/)op **Facturering** en navigeer vervolgens naar **Services kopen**.</span><span class="sxs-lookup"><span data-stu-id="0947b-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="0947b-170">Selecteer **Microsoft 365 E5** en klik op **Gratis proefperiode starten.**</span><span class="sxs-lookup"><span data-stu-id="0947b-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="0947b-171">![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="0947b-172">Kies uw verificatievoorkeur: via een sms of oproep.</span><span class="sxs-lookup"><span data-stu-id="0947b-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="0947b-173">Zodra u hebt besloten, voert u het telefoonnummer in, selecteert u **Sms me** of **Bel mij** afhankelijk van uw selectie.</span><span class="sxs-lookup"><span data-stu-id="0947b-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="0947b-174">![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina vragen om contactgegevens om code te sturen om te bewijzen dat je geen robot bent](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="0947b-175">Voer de verificatiecode in en klik op **Uw gratis proefperiode starten.**</span><span class="sxs-lookup"><span data-stu-id="0947b-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="0947b-176">![Afbeelding of_Microsoft 365 E5 Start gratis proefpagina waar u verificatiecode invullen die het systeem heeft verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="0947b-177">Klik **op Probeer nu** om uw Microsoft 365 E5-proefversie te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="0947b-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="0947b-178">![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten waar u de knop Nu proberen moet klokken om te beginnen](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="0947b-179">Ga naar de gebruikers van **het Microsoft 365-beheercentrum**  >  **Users**  >  **Gebruikers Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="0947b-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="0947b-180">Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren**en wissel de licentie van Office 365 E5 naar **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="0947b-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="0947b-181">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0947b-181">Click **Save**.</span></span>
<span data-ttu-id="0947b-182">![Afbeelding of_Microsoft pagina 365-beheercentrum waar u Microsoft 365 E5-licentie selecteren](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="0947b-183">Selecteer het globale beheerdersaccount opnieuw en klik op **Gebruikersnaam beheren**.</span><span class="sxs-lookup"><span data-stu-id="0947b-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="0947b-184">![Afbeelding of_Microsoft 365-pagina met beheercentrum waar u Account selecteren en vervolgens gebruikersnaam beheren](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="0947b-185">[Optioneel] Wijzig het domein van *onmicrosoft.com* naar uw eigen domein, afhankelijk van wat u hebt gekozen in de vorige stappen.</span><span class="sxs-lookup"><span data-stu-id="0947b-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="0947b-186">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0947b-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="0947b-187">![Afbeelding of_Microsoft 365-pagina beheercentrum waar u uw domeinvoorkeur wijzigen](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="0947b-188">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0947b-188">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="0947b-189">![Fase 3: & onboard configureren](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="0947b-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="0947b-190">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="0947b-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="0947b-191">Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-evaluatielab en aan boord van uw eindpunten.</span><span class="sxs-lookup"><span data-stu-id="0947b-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection evaluation lab and onboard your endpoints.</span></span>
