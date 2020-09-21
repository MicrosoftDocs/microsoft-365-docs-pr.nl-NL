---
title: Uw Microsoft Threat Protection-proefversie Lab of pilot omgeving instellen
description: Ga naar Microsoft 365-Beveiligingscentrum en stel uw omgeving voor Microsoft Threat Protection trial Lab in
keywords: Instellingen voor Microsoft Threat Protection-proefabonnement, Microsoft Threat Protection voor de proefversie, Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab instellen
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
ms.openlocfilehash: c3323192e0095ad6693241390cff81d42be9cce1
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956241"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="4dacb-104">Uw Microsoft Threat Protection proef lab-omgeving instellen</span><span class="sxs-lookup"><span data-stu-id="4dacb-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="4dacb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4dacb-105">**Applies to:**</span></span>
- <span data-ttu-id="4dacb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4dacb-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="4dacb-107">U maakt een Microsoft Threat Protection-proefversie voor proef omgevingen of pilot omgevingen en de implementatie hiervan is een proces van drie fasen:</span><span class="sxs-lookup"><span data-stu-id="4dacb-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Uw Microsoft Threat Protection evaluatie lab of testomgeving voorbereiden" />
      <br/><span data-ttu-id="4dacb-109">Fase 1: voorbereiding </a></span><span class="sxs-lookup"><span data-stu-id="4dacb-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Uw Microsoft Threat Protection-proefversie Lab of pilot omgeving instellen" />
      <br/><span data-ttu-id="4dacb-111">Fase 2: instellen </a></span><span class="sxs-lookup"><span data-stu-id="4dacb-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints" title="
Configureer elke Microsoft Threat Protection-pijler voor uw proefabonnement voor Microsoft Threat Protection of een proef omgeving en haal uw eindpunten over." />
      <br/><span data-ttu-id="4dacb-113">Fase 3: & onboard configureren </a></span><span class="sxs-lookup"><span data-stu-id="4dacb-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="4dacb-114">U bevindt zich momenteel in de configuratiefase.</span><span class="sxs-lookup"><span data-stu-id="4dacb-114">You're currently in the set up phase.</span></span> <span data-ttu-id="4dacb-115">Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum en vervolgens uw proefabonnement of pilot omgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="4dacb-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="4dacb-116">Registreer u voor een Office 365-of Azure Active Directory-abonnement om een *. onmicrosoft.com* -Tenant te genereren die u kunt gebruiken om zich aan te melden voor uw microsoft 365 E5-licentie.</span><span class="sxs-lookup"><span data-stu-id="4dacb-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="4dacb-117">Als u al een bestaand abonnement voor Office 365 of Azure Active Directory hebt, kunt u de stappen voor het maken van een proefversie van Office 365 E5 overslaan.</span><span class="sxs-lookup"><span data-stu-id="4dacb-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="4dacb-118">In deze fase wordt u begeleid bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="4dacb-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="4dacb-119">Een Office 365 E5-proef Tenant maken</span><span class="sxs-lookup"><span data-stu-id="4dacb-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="4dacb-120">Microsoft 365-proefabonnement inschakelen</span><span class="sxs-lookup"><span data-stu-id="4dacb-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="4dacb-121">Een Office 365 E5-proef Tenant maken</span><span class="sxs-lookup"><span data-stu-id="4dacb-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="4dacb-122">Als u al een bestaand Office 365-of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van de proefversie van Office 365 E5 overslaan.</span><span class="sxs-lookup"><span data-stu-id="4dacb-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="4dacb-123">Ga naar de [Office 365 E5-product Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **gratis proefversie**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="4dacb-124">![Gratis proef pagina voor afbeelding of_Office 365 E5](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="4dacb-125">Voltooi de registratie van het proefabonnement door uw e-mailadres (persoonlijk of zakelijk) in te voeren.</span><span class="sxs-lookup"><span data-stu-id="4dacb-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="4dacb-126">Klik op **account instellen**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-126">Click **Set up account**.</span></span>
<span data-ttu-id="4dacb-127">![Installatiepagina voor het instellen van of_Office 365 E5 proef registratie](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="4dacb-128">Vul uw voornaam, achternaam, zakelijk telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.</span><span class="sxs-lookup"><span data-stu-id="4dacb-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  
<br>![Afbeelding of_Office 365 E5-registratiepagina voor het instellen van een naam, telefoon en bedrijf vragen](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="4dacb-130">In het land of de regio die u hebt ingesteld, wordt het datacenter regio weergegeven waarop uw Office 365 wordt gehost.</span><span class="sxs-lookup"><span data-stu-id="4dacb-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="4dacb-131">Kies uw verificatie voorkeur: via een SMS-bericht of-oproep.</span><span class="sxs-lookup"><span data-stu-id="4dacb-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="4dacb-132">Klik op **verificatie code verzenden**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="4dacb-133">![Voor of_Office beeld van een pagina voor het instellen van een proefabonnement voor 365 E5 voor de verificatie](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="4dacb-134">Stel de aangepaste domeinnaam voor de Tenant in en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="4dacb-135">![Voorbeeld van een pagina voor het instellen van een proefabonnement op of_Office 365 E5 waarop u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="4dacb-136">U kunt de eerste identiteit instellen, wat een globale beheerder voor de Tenant wordt.</span><span class="sxs-lookup"><span data-stu-id="4dacb-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="4dacb-137">Voer **naam** en **wachtwoord**in.</span><span class="sxs-lookup"><span data-stu-id="4dacb-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="4dacb-138">Klik op **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-138">Click **Sign up**.</span></span>
<span data-ttu-id="4dacb-139">![Voorbeeld van een pagina voor het instellen van een proefabonnement op of_Office 365 E5 waarop u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="4dacb-140">Klik op **Ga naar Setup** om de inlevering van de Office 365 E5-proefversie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="4dacb-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="4dacb-141">![Afbeelding van het instellen van de proef instelling voor het registreren van Office 365 E5 u vragen om te klikken op de knop Ga naar instellen](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="4dacb-142">Verbind uw bedrijfsdomein met de Office 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="4dacb-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="4dacb-143">Option Kies **al uw eigen domein verbinden** en typ uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="4dacb-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="4dacb-144">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-144">Click **Next**.</span></span>
<br><span data-ttu-id="4dacb-145">![Installatiepagina voor afbeelding of_Office 365 E5 waarop u uw aanmeldings-en e-mailadres aan uw persoonlijke voorkeur kunt aanpassen](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="4dacb-146">Een TXT-of MX-record toevoegen om de eigendom van het domein te valideren.</span><span class="sxs-lookup"><span data-stu-id="4dacb-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="4dacb-147">Wanneer u de TXT-of MX-record aan uw domein hebt toegevoegd, selecteert u **verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="4dacb-148">![Installatiepagina voor afbeelding of_Office 365 E5 waarop u een TXT of MX-record moet toevoegen om uw domein te bevestigen](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="4dacb-149">Option Maak meer gebruikersaccounts voor uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="4dacb-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="4dacb-150">U kunt deze stap overslaan door te klikken op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="4dacb-151">![Installatiepagina van of_Office 365 E5 waarop u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="4dacb-152">Option Download Office-apps.</span><span class="sxs-lookup"><span data-stu-id="4dacb-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="4dacb-153">Klik op **volgende** om deze stap over te slaan.</span><span class="sxs-lookup"><span data-stu-id="4dacb-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="4dacb-154">![Pagina of_Office 365 E5 waarop u uw Office-apps kunt installeren](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="4dacb-155">Option E-mailberichten migreren.</span><span class="sxs-lookup"><span data-stu-id="4dacb-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="4dacb-156">U kunt deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="4dacb-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="4dacb-157">![Afbeelding of_Office 365 E5 waarop u kunt instellen of u e-mailberichten wilt migreren](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="4dacb-158">Kies Online Services.</span><span class="sxs-lookup"><span data-stu-id="4dacb-158">Choose online services.</span></span> <span data-ttu-id="4dacb-159">Selecteer **Exchange** en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="4dacb-160">![Afbeelding of_Office 365 E5 waar u uw Online Services kunt kiezen](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="4dacb-161">MX-, CNAME-en TXT-records toevoegen aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="4dacb-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="4dacb-162">Wanneer u klaar bent, selecteert u **verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="4dacb-163">![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="4dacb-164">Gefeliciteerd, u hebt het inrichten voor de Office 365-Tenant voltooid.</span><span class="sxs-lookup"><span data-stu-id="4dacb-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="4dacb-165">![Afbeelding of_Office 365 E5-bevestigingspagina voor de voltooiing van instellingen](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="4dacb-166">Microsoft 365-proefabonnement inschakelen</span><span class="sxs-lookup"><span data-stu-id="4dacb-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="4dacb-167">Als u zich aanmeldt voor een proefversie, geeft u 25 gebruikerslicenties voor een maand te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4dacb-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="4dacb-168">Zie [een M365-abonnement uitproberen of kopen](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4dacb-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="4dacb-169">Klik in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/)op **facturering** en ga vervolgens naar **Services aanschaffen**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="4dacb-170">Selecteer **Microsoft 365 E5** en klik op **gratis proefversie starten**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="4dacb-171">![Afbeelding of_Microsoft 365 E5 gratis proefversie starten](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="4dacb-172">Kies uw verificatie voorkeur: via een SMS-bericht of-oproep.</span><span class="sxs-lookup"><span data-stu-id="4dacb-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="4dacb-173">Als u hebt besloten, voert u het telefoonnummer in en selecteert u de **tekst mij** of **Bel mij** afhankelijk van uw selectie.</span><span class="sxs-lookup"><span data-stu-id="4dacb-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="4dacb-174">![Afbeelding of_Microsoft 365 E5 de gratis proef pagina voor het starten van een proefabonnement voor contactgegevens om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="4dacb-175">Voer de verificatiecode in en klik op **Start uw gratis proefperiode**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="4dacb-176">![Afbeelding of_Microsoft 365 E5-proef pagina voor het starten van een gratis proefperiode waarop u verificatiecode kunt invullen waarbij het systeem wordt verzonden om bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="4dacb-177">Klik op **nu proberen** om uw microsoft 365 E5-proefabonnement te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="4dacb-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="4dacb-178">![Afbeelding of_Microsoft 365 E5 start de pagina gratis proefperiode waarop u de knop nu starten moet klokken om te beginnen](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="4dacb-179">Ga naar de gebruikers van het **Microsoft 365-Beheercentrum**  >  **Users**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="4dacb-180">Selecteer uw gebruikersaccount, selecteer **productlicenties beheren**en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="4dacb-181">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-181">Click **Save**.</span></span>
<span data-ttu-id="4dacb-182">![Afbeelding of_Microsoft pagina van het Beheercentrum van 365, waarop u Microsoft 365 E5-licentie kunt selecteren](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="4dacb-183">Selecteer opnieuw het account van de globale beheerder en klik op **gebruikersnaam beheren**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="4dacb-184">![Afbeelding of_Microsoft pagina van het Beheercentrum van 365, waarop u account kunt selecteren en vervolgens gebruikersnaam kunt beheren](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="4dacb-185">Option Wijzig het domein in *onmicrosoft.com* in uw eigen domein, afhankelijk van de optie die u in de vorige stappen hebt gekozen.</span><span class="sxs-lookup"><span data-stu-id="4dacb-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="4dacb-186">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4dacb-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="4dacb-187">![Afbeelding of_Microsoft pagina van het Beheercentrum van 365, waarop u de voorkeuren van uw domein kunt wijzigen](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="4dacb-188">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4dacb-188">Next step</span></span>
|<span data-ttu-id="4dacb-189">![Fase 3: & onboard configureren](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="4dacb-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="4dacb-190">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="4dacb-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="4dacb-191">Configureer elke Microsoft Threat Protection-pijler voor uw proefabonnement voor Microsoft Threat Protection of een proef omgeving en haal uw eindpunten over.</span><span class="sxs-lookup"><span data-stu-id="4dacb-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
