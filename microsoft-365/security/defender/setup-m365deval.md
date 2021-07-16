---
title: Uw testlaboratorium Microsoft 365 Defender testomgeving instellen
description: Access Microsoft 365 Beveiligingscentrum en stel vervolgens uw Microsoft 365 Defender proeflaboratorium in
keywords: Microsoft 365 Defender proeffase instellen, Microsoft 365 Defender proefinstallatie, Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium instellen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454731"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="9c740-104">Uw proefversie Microsoft 365 Defender in een labomgeving instellen</span><span class="sxs-lookup"><span data-stu-id="9c740-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9c740-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9c740-105">**Applies to:**</span></span>
- <span data-ttu-id="9c740-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c740-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="9c740-107">In dit onderwerp wordt u begeleid bij het instellen van een speciale labomgeving.</span><span class="sxs-lookup"><span data-stu-id="9c740-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="9c740-108">Zie de nieuwe handleiding Evalueren en Microsoft 365 Defender voor informatie over het instellen van [een proefversie in productie.](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9c740-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="9c740-109">Een proef tenant Office 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="9c740-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="9c740-110">Als u al een bestaand abonnement Office 365 of Azure Active Directory hebt, kunt u de stappen voor het maken Office 365 E5 proefversie van tenants overslaan.</span><span class="sxs-lookup"><span data-stu-id="9c740-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="9c740-111">Ga naar de [Office 365 E5 productportal en](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) selecteer **Gratis proefabonnement.**</span><span class="sxs-lookup"><span data-stu-id="9c740-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Gratis of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="9c740-113">Voltooi de proefregistratie door uw e-mailadres (persoonlijk of zakelijk) in te vullen.</span><span class="sxs-lookup"><span data-stu-id="9c740-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="9c740-114">Klik **op Account instellen.**</span><span class="sxs-lookup"><span data-stu-id="9c740-114">Click **Set up account**.</span></span>

   ![Installatiepagina of_Office 365 E5-proefregistratie](../../media/mtp-eval-10.png)

3. <span data-ttu-id="9c740-116">Vul uw voornaam, achternaam, zakelijke telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.</span><span class="sxs-lookup"><span data-stu-id="9c740-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waarin wordt gevraagd om naam, telefoon en bedrijfsgegevens](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="9c740-118">Het land of de regio die u hier hebt ingesteld, bepaalt de datacenterregio waar Office 365 wordt gehost.</span><span class="sxs-lookup"><span data-stu-id="9c740-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="9c740-119">Kies uw verificatievoorkeur: via een sms-bericht of oproep.</span><span class="sxs-lookup"><span data-stu-id="9c740-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="9c740-120">Klik **op Verificatiecode verzenden.**</span><span class="sxs-lookup"><span data-stu-id="9c740-120">Click **Send Verification Code**.</span></span> 

   ![Installatiepagina of_Office 365 E5-proefregistratie waarin wordt gevraagd om verificatievoorkeur](../../media/mtp-eval-12.png)

5. <span data-ttu-id="9c740-122">Stel de aangepaste domeinnaam in voor uw tenant en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="9c740-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waar u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="9c740-124">Stel de eerste identiteit in, die een globale beheerder voor de tenant is.</span><span class="sxs-lookup"><span data-stu-id="9c740-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="9c740-125">Vul Naam **en** **wachtwoord in.**</span><span class="sxs-lookup"><span data-stu-id="9c740-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="9c740-126">Klik op **Registeren**.</span><span class="sxs-lookup"><span data-stu-id="9c740-126">Click **Sign up**.</span></span>

   ![Afbeelding of_Office 365 E5-proefregistratiepagina waar u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)

7. <span data-ttu-id="9c740-128">Klik **op Ga naar Setup om** de proefversie van Office 365 E5 te voltooien.</span><span class="sxs-lookup"><span data-stu-id="9c740-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Afbeelding van Office 365 E5 registratiepagina voor proefversies met de vraag of u op de knop Instellen gaan wilt klikken](../../media/mtp-eval-15.png)

8. <span data-ttu-id="9c740-130">Verbinding maken uw bedrijfsdomein aan de Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="9c740-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="9c740-131">[Optioneel] Kies **Verbinding maken domein dat u al hebt en** typ uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="9c740-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="9c740-132">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9c740-132">Click **Next**.</span></span>

   ![Afbeelding of_Office 365 E5 Setup-pagina waar u uw aanmelding en e-mail moet personaliseren](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="9c740-134">Voeg een TXT- of MX-record toe om het domeineigenschap te valideren.</span><span class="sxs-lookup"><span data-stu-id="9c740-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="9c740-135">Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren.**</span><span class="sxs-lookup"><span data-stu-id="9c740-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Afbeelding of_Office 365 E5-installatiepagina waar u een TXT of MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="9c740-137">[Optioneel] Maak meer gebruikersaccounts voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="9c740-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="9c740-138">U kunt deze stap overslaan door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="9c740-138">You can skip this step by clicking **Next**.</span></span>

    ![Afbeelding of_Office 365 E5-installatiepagina waar u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="9c740-140">[Optioneel] Download Office apps.</span><span class="sxs-lookup"><span data-stu-id="9c740-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="9c740-141">Klik **op Volgende** om deze stap over te slaan.</span><span class="sxs-lookup"><span data-stu-id="9c740-141">Click **Next** to skip this step.</span></span> 

    ![Afbeelding of_Office 365 E5-pagina waar u uw apps Office installeren](../../media/mtp-eval-19.png)

12. <span data-ttu-id="9c740-143">[Optioneel] E-mailberichten migreren.</span><span class="sxs-lookup"><span data-stu-id="9c740-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="9c740-144">Nogmaals, u kunt deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="9c740-144">Again, you can skip this step.</span></span>

    ![Afbeelding of_Office 365 E5 waar u kunt instellen of u e-mailberichten wilt migreren of niet](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="9c740-146">Kies onlineservices.</span><span class="sxs-lookup"><span data-stu-id="9c740-146">Choose online services.</span></span> <span data-ttu-id="9c740-147">Selecteer **Exchange** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="9c740-147">Select **Exchange** and click **Next**.</span></span> 

    ![Afbeelding of_Office 365 E5 waar u uw onlineservices kunt kiezen](../../media/mtp-eval-21.png)

14. <span data-ttu-id="9c740-149">Voeg MX-, CNAME- en TXT-records toe aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="9c740-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="9c740-150">Wanneer u klaar is, selecteert u **Verifiëren.**</span><span class="sxs-lookup"><span data-stu-id="9c740-150">When completed, select **Verify**.</span></span>

    ![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="9c740-152">Gefeliciteerd, u hebt de inrichting van uw Office 365 voltooid.</span><span class="sxs-lookup"><span data-stu-id="9c740-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bevestigingspagina of_Office installatie van 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="9c740-154">Proefabonnement Microsoft 365 inschakelen</span><span class="sxs-lookup"><span data-stu-id="9c740-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="9c740-155">Als u zich aanmeldt voor een proefabonnement, krijgt u 25 gebruikerslicenties voor een maand.</span><span class="sxs-lookup"><span data-stu-id="9c740-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="9c740-156">Zie [Een M365-abonnement](../../commerce/try-or-buy-microsoft-365.md) proberen of kopen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9c740-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="9c740-157">Klik [Microsoft 365-beheer in Microsoft 365-beheer](https://admin.microsoft.com/) **op Facturering** en ga naar Services **aanschaffen.**</span><span class="sxs-lookup"><span data-stu-id="9c740-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="9c740-158">Selecteer **Microsoft 365 E5** en klik op **Gratis proefabonnement starten.**</span><span class="sxs-lookup"><span data-stu-id="9c740-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten](../../media/mtp-eval-24.png)

3. <span data-ttu-id="9c740-160">Kies uw verificatievoorkeur: via een sms-bericht of oproep.</span><span class="sxs-lookup"><span data-stu-id="9c740-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="9c740-161">Nadat u hebt besloten, voert u het telefoonnummer in, selecteert u **Mij sms'en** of **Mij bellen,** afhankelijk van uw selectie.</span><span class="sxs-lookup"><span data-stu-id="9c740-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten met vragen om contactgegevens om code te verzenden om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="9c740-163">Voer de verificatiecode in en klik **op Uw gratis proefabonnement starten.**</span><span class="sxs-lookup"><span data-stu-id="9c740-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversiepagina waar u verificatiecode kunt invullen die het systeem heeft verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)

5. <span data-ttu-id="9c740-165">Klik **op Nu proberen** om uw proefabonnement Microsoft 365 E5 bevestigen.</span><span class="sxs-lookup"><span data-stu-id="9c740-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversiepagina waar u de knop Nu proberen moet kloken om te beginnen](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="9c740-167">Ga naar het **Microsoft 365-beheer Center**  >  **Users Active**  >  **Users**.</span><span class="sxs-lookup"><span data-stu-id="9c740-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="9c740-168">Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren** en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="9c740-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="9c740-169">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9c740-169">Click **Save**.</span></span>

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u een licentie Microsoft 365 E5 selecteren](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="9c740-171">Selecteer nogmaals het globale beheerdersaccount en klik **op Gebruikersnaam beheren.**</span><span class="sxs-lookup"><span data-stu-id="9c740-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u Account kunt selecteren en vervolgens Gebruikersnaam beheren](../../media/mtp-eval-29.png)

8. <span data-ttu-id="9c740-173">[Optioneel] Wijzig het domein van *onmicrosoft.com* in uw eigen domein, afhankelijk van wat u hebt gekozen in de vorige stappen.</span><span class="sxs-lookup"><span data-stu-id="9c740-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="9c740-174">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9c740-174">Click **Save changes**.</span></span>

   ![Afbeelding of_Microsoft pagina 365-beheercentrum waar u uw domeinvoorkeur kunt wijzigen](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="9c740-176">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9c740-176">Next step</span></span>
|[<span data-ttu-id="9c740-177">Fase 3: Configureren & Onboard</span><span class="sxs-lookup"><span data-stu-id="9c740-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="9c740-178">Configureer elke Microsoft 365 Defender voor uw Microsoft 365 Defender proeflaboratorium of testomgeving en aan boord van uw eindpunten.</span><span class="sxs-lookup"><span data-stu-id="9c740-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
