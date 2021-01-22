---
title: Uw Test lab of pilotomgeving met Microsoft 365 Defender instellen
description: Access Microsoft 365 Security Center then set up your Microsoft 365 Defender trial lab environment
keywords: Microsoft Threat Protection trial setup, Microsoft Threat Protection pilot setup, try Microsoft Threat Protection, Microsoft Threat Protection evaluation lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932980"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="2700f-104">Uw Test labomgeving met Microsoft 365 Defender instellen</span><span class="sxs-lookup"><span data-stu-id="2700f-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2700f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2700f-105">**Applies to:**</span></span>
- <span data-ttu-id="2700f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2700f-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="2700f-107">Het maken van een testtest of pilotomgeving van Microsoft 365 Defender en deze implementeren bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="2700f-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="2700f-108">[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="2700f-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="2700f-109">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="2700f-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Fase 2: Instellen](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="2700f-111">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="2700f-111">Phase 2: Set up</span></span> |<span data-ttu-id="2700f-112">[![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="2700f-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="2700f-113">Fase 3: Onboard</span><span class="sxs-lookup"><span data-stu-id="2700f-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="2700f-114">[![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="2700f-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="2700f-115">Terug naar pilot playbook</span><span class="sxs-lookup"><span data-stu-id="2700f-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="2700f-116">*U bent hier!*</span><span class="sxs-lookup"><span data-stu-id="2700f-116">*You are here!*</span></span>  | | |


<span data-ttu-id="2700f-117">U bent momenteel in de fase van de in te stellen fase.</span><span class="sxs-lookup"><span data-stu-id="2700f-117">You're currently in the set up phase.</span></span> <span data-ttu-id="2700f-118">Ga als eerste te werk om het Microsoft 365-beveiligingscentrum te openen en stel vervolgens uw testtestomgeving of pilotomgeving in.</span><span class="sxs-lookup"><span data-stu-id="2700f-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="2700f-119">Meld u aan voor een Office 365- of Azure Active Directory-abonnement om een *.onmicrosoft.com-tenant* te genereren die u kunt gebruiken om u te registreren voor uw Microsoft 365 E5-licentie.</span><span class="sxs-lookup"><span data-stu-id="2700f-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="2700f-120">Als u al een Office 365- of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van de proefversie van Office 365 E5 of de tenant als pilot overslaan.</span><span class="sxs-lookup"><span data-stu-id="2700f-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="2700f-121">In deze fase kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="2700f-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="2700f-122">Een proefversie-tenant van Office 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="2700f-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="2700f-123">Proefabonnement op Microsoft 365 inschakelen</span><span class="sxs-lookup"><span data-stu-id="2700f-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="2700f-124">Een proefversie-tenant van Office 365 E5 maken</span><span class="sxs-lookup"><span data-stu-id="2700f-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="2700f-125">Als u al een Office 365- of Azure Active Directory-abonnement hebt, kunt u de stappen voor het maken van de office 365 E5-proef tenant overslaan.</span><span class="sxs-lookup"><span data-stu-id="2700f-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="2700f-126">Ga naar de [Office 365 E5-productportal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) en selecteer **een gratis proefversie.**</span><span class="sxs-lookup"><span data-stu-id="2700f-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Afbeelding of_Office gratis proefversie van 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="2700f-128">Voltooi de registratie van het proefabonnement door uw e-mailadres (persoonlijk of zakelijk) in te vullen.</span><span class="sxs-lookup"><span data-stu-id="2700f-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="2700f-129">Klik **op Account instellen.**</span><span class="sxs-lookup"><span data-stu-id="2700f-129">Click **Set up account**.</span></span>

   ![Afbeelding of_Office registratiepagina voor de proefversie van 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="2700f-131">Vul uw voornaam, achternaam, zakelijk telefoonnummer, bedrijfsnaam, bedrijfsgrootte en land of regio in.</span><span class="sxs-lookup"><span data-stu-id="2700f-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Afbeelding of_Office registratiepagina voor de proefversie van 365 E5 waarin om naam, telefoon en bedrijfsgegevens wordt gevraagd](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="2700f-133">Het land of de regio die u hier hebt ingesteld, bepaalt de regio van het datacenter waar Uw Office 365 wordt gehost.</span><span class="sxs-lookup"><span data-stu-id="2700f-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="2700f-134">Kies uw verificatievoorkeur: via een sms-bericht of gesprek.</span><span class="sxs-lookup"><span data-stu-id="2700f-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="2700f-135">Klik **op Verificatiecode verzenden.**</span><span class="sxs-lookup"><span data-stu-id="2700f-135">Click **Send Verification Code**.</span></span> 

   ![Afbeelding of_Office registratiepagina voor de proefversie van 365 E5 waarin om verificatievoorkeur wordt gevraagd](../../media/mtp-eval-12.png)

5. <span data-ttu-id="2700f-137">Stel de aangepaste domeinnaam voor uw tenant in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="2700f-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Afbeelding of_Office de registratiepagina voor proefversies van 365 E5 waar u uw aangepaste domeinnaam kunt instellen](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="2700f-139">Stel de eerste identiteit in, die een globale beheerder voor de tenant wordt.</span><span class="sxs-lookup"><span data-stu-id="2700f-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="2700f-140">Vul Naam **en** **wachtwoord in.**</span><span class="sxs-lookup"><span data-stu-id="2700f-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="2700f-141">Klik **op Registreren.**</span><span class="sxs-lookup"><span data-stu-id="2700f-141">Click **Sign up**.</span></span>

   ![Afbeelding of_Office registratiepagina voor proefversie 365 E5 waar u uw bedrijfsidentiteit kunt instellen](../../media/mtp-eval-14.png)

7. <span data-ttu-id="2700f-143">Klik **op Ga naar Setup om** de inrichting van de proef tenant van Office 365 E5 te voltooien.</span><span class="sxs-lookup"><span data-stu-id="2700f-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Afbeelding van de registratiepagina voor proefversie van Office 365 E5 met de vraag of u wilt klikken op de knop Instellen](../../media/mtp-eval-15.png)

8. <span data-ttu-id="2700f-145">Verbind uw bedrijfsdomein met de Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="2700f-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="2700f-146">[Optioneel] Kies **Verbinding maken met een domein waar u al eigenaar van bent** en typ uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="2700f-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="2700f-147">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2700f-147">Click **Next**.</span></span>

   ![Afbeelding of_Office 365 E5-installatiepagina waar u uw aanmelding en e-mail aan uw persoonlijke voorkeur moet personaliseren](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="2700f-149">Voeg een TXT- of MX-record toe om het eigendom van het domein te valideren.</span><span class="sxs-lookup"><span data-stu-id="2700f-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="2700f-150">Nadat u de TXT- of MX-record aan uw domein hebt toegevoegd, selecteert u **Verifiëren.**</span><span class="sxs-lookup"><span data-stu-id="2700f-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Afbeelding of_Office 365 E5-installatiepagina waar u een TXT of MX-record moet toevoegen om uw domein te verifiëren](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="2700f-152">[Optioneel] Maak meer gebruikersaccounts voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="2700f-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="2700f-153">U kunt deze stap overslaan door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="2700f-153">You can skip this step by clicking **Next**.</span></span>

    ![Afbeelding of_Office 365 E5-installatiepagina waar u meer gebruikers kunt toevoegen](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="2700f-155">[Optioneel] Download Office-apps.</span><span class="sxs-lookup"><span data-stu-id="2700f-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="2700f-156">Klik **op Volgende** om deze stap over te slaan.</span><span class="sxs-lookup"><span data-stu-id="2700f-156">Click **Next** to skip this step.</span></span> 

    ![Afbeelding of_Office 365 E5-pagina waarop u uw Office-apps kunt installeren](../../media/mtp-eval-19.png)

12. <span data-ttu-id="2700f-158">[Optioneel] E-mailberichten migreren.</span><span class="sxs-lookup"><span data-stu-id="2700f-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="2700f-159">Nogmaals, u kunt deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="2700f-159">Again, you can skip this step.</span></span>

    ![Afbeelding of_Office 365 E5, waar u kunt instellen of u wel of niet e-mailberichten wilt migreren](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="2700f-161">Kies onlineservices.</span><span class="sxs-lookup"><span data-stu-id="2700f-161">Choose online services.</span></span> <span data-ttu-id="2700f-162">Selecteer **Exchange en** klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="2700f-162">Select **Exchange** and click **Next**.</span></span> 

    ![Afbeelding of_Office 365 E5, waar u uw onlineservices kunt kiezen](../../media/mtp-eval-21.png)

14. <span data-ttu-id="2700f-164">Voeg MX-, CNAME- en TXT-records toe aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="2700f-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="2700f-165">Als u klaar is, selecteert u **Verifiëren.**</span><span class="sxs-lookup"><span data-stu-id="2700f-165">When completed, select **Verify**.</span></span>

    ![Afbeelding of_Office 365 E5 hier kunt u uw DNS-records toevoegen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="2700f-167">Gefeliciteerd, u hebt de inrichting van uw Office 365-tenant voltooid.</span><span class="sxs-lookup"><span data-stu-id="2700f-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bevestigingspagina of_Office 365 E5 instellen](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="2700f-169">Proefabonnement op Microsoft 365 inschakelen</span><span class="sxs-lookup"><span data-stu-id="2700f-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="2700f-170">Als u zich aanmeldt voor een proefabonnement, krijgt u 25 gebruikerslicenties die u per maand kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2700f-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="2700f-171">Zie [Een M365-abonnement proberen of kopen](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2700f-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="2700f-172">Klik [in het Microsoft 365-beheercentrum](https://admin.microsoft.com/)op **Facturering** en ga naar **Services aanschaffen.**</span><span class="sxs-lookup"><span data-stu-id="2700f-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="2700f-173">Selecteer **Microsoft 365 E5 en** klik op Gratis **proefversie starten.**</span><span class="sxs-lookup"><span data-stu-id="2700f-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Afbeelding of_Microsoft gratis proefversie van 365 E5 starten](../../media/mtp-eval-24.png)

3. <span data-ttu-id="2700f-175">Kies uw verificatievoorkeur: via een sms-bericht of gesprek.</span><span class="sxs-lookup"><span data-stu-id="2700f-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="2700f-176">Zodra u hebt besloten, voert u het telefoonnummer in, selecteert u Sms **me** of **Bel me,** afhankelijk van uw selectie.</span><span class="sxs-lookup"><span data-stu-id="2700f-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Afbeelding of_Microsoft 365 E5 Start gratis proefversie met vragen om contactgegevens om code te verzenden om te bewijzen dat u geen robot bent](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="2700f-178">Voer de verificatiecode in en klik **op Uw gratis proefabonnement starten.**</span><span class="sxs-lookup"><span data-stu-id="2700f-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Afbeelding of_Microsoft 365 E5 Start een gratis proefversiepagina waar u verificatiecode kunt invullen die door het systeem is verzonden om te bewijzen dat u geen robot bent](../../media/mtp-eval-26.png)

5. <span data-ttu-id="2700f-180">Klik **op Nu proberen** om uw proefabonnement op Microsoft 365 E5 te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="2700f-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Afbeelding of_Microsoft 365 E5 Gratis proefversiepagina starten, waar u met de knop Nu proberen moet kloken om te beginnen](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="2700f-182">Ga naar het **Microsoft 365-beheercentrum**  >  **gebruikers die** actief  >  **zijn.**</span><span class="sxs-lookup"><span data-stu-id="2700f-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="2700f-183">Selecteer uw gebruikersaccount, selecteer **Productlicenties beheren** en verwissel de licentie van Office 365 E5 naar **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="2700f-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="2700f-184">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2700f-184">Click **Save**.</span></span>

   ![Afbeelding of_Microsoft 365-beheercentrumpagina waar u een Microsoft 365 E5-licentie kunt selecteren](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="2700f-186">Selecteer nogmaals het globale beheerdersaccount en klik op **Gebruikersnaam beheren.**</span><span class="sxs-lookup"><span data-stu-id="2700f-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Afbeelding of_Microsoft de pagina 365-beheercentrum waar u Account kunt selecteren en vervolgens gebruikersnaam beheren](../../media/mtp-eval-29.png)

8. <span data-ttu-id="2700f-188">[Optioneel] Wijzig het domein van *onmicrosoft.com* in uw eigen domein, afhankelijk van wat u in de vorige stappen hebt gekozen.</span><span class="sxs-lookup"><span data-stu-id="2700f-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="2700f-189">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2700f-189">Click **Save changes**.</span></span>

   ![Afbeelding of_Microsoft 365-beheercentrumpagina waar u uw domeinvoorkeur kunt wijzigen](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="2700f-191">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2700f-191">Next step</span></span>
|[<span data-ttu-id="2700f-192">Fase 3: & onboard</span><span class="sxs-lookup"><span data-stu-id="2700f-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="2700f-193">Configureer elke Microsoft 365 Defender-testomgeving voor uw Test lab of pilotomgeving van Microsoft 365 Defender en onboard uw eindpunten.</span><span class="sxs-lookup"><span data-stu-id="2700f-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
