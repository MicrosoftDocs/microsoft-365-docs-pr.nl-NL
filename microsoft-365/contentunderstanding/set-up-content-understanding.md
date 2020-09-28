---
title: SharePoint-Syntex instellen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Inzicht in inhoud instellen in Project cortex
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294839"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="2e46e-103">SharePoint-Syntex instellen</span><span class="sxs-lookup"><span data-stu-id="2e46e-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="2e46e-104">Beheerders kunnen het Microsoft 365-Beheercentrum gebruiken voor het instellen van en Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="2e46e-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="2e46e-105">Voordat u begint, moet u rekening houden met het volgende:</span><span class="sxs-lookup"><span data-stu-id="2e46e-105">Consider the following before you start:</span></span>

- <span data-ttu-id="2e46e-106">Welke SharePoint-sites gebruikt u om de formulierverwerking in te schakelen?</span><span class="sxs-lookup"><span data-stu-id="2e46e-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="2e46e-107">Allemaal, of selecteer sites?</span><span class="sxs-lookup"><span data-stu-id="2e46e-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="2e46e-108">Wat is de naam van uw inhouds centrum en wie is de primaire sitebeheerder?</span><span class="sxs-lookup"><span data-stu-id="2e46e-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="2e46e-109">U kunt de instellingen wijzigen na de eerste configuratie in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2e46e-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="2e46e-110">De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project.</span><span class="sxs-lookup"><span data-stu-id="2e46e-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="2e46e-111">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="2e46e-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="2e46e-112">Zorg er eerst voor dat u op de hoogte bent van de beste manier om inhoud in uw omgeving in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="2e46e-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="2e46e-113">U moet bijvoorbeeld overwegingen doen voor de volgende namen:</span><span class="sxs-lookup"><span data-stu-id="2e46e-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="2e46e-114">De SharePoint-sites die u wilt gebruiken voor het bewerken van formulieren: al deze, bepaalde of geselecteerde sites</span><span class="sxs-lookup"><span data-stu-id="2e46e-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="2e46e-115">Uw inhouds centrum en de naam van de primaire sitebeheerder</span><span class="sxs-lookup"><span data-stu-id="2e46e-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="2e46e-116">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2e46e-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="2e46e-117">U moet beschikken over de machtigingen van een globale beheerder of SharePoint-beheerder om toegang te krijgen tot het Microsoft 365-Beheercentrum en de informatie over de inhoud ervan kunt instellen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="2e46e-118">Als beheerder kunt u ook op elk gewenst moment na de installatie wijzigingen aanbrengen in de geselecteerde instellingen en in de inhoud van de beheerinstellingen in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2e46e-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="2e46e-119">SharePoint Syntex instellen</span><span class="sxs-lookup"><span data-stu-id="2e46e-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="2e46e-120">Selecteer in het Microsoft 365-Beheercentrum de optie **instellen**en bekijk vervolgens de sectie **bedrijfsinformatie** .</span><span class="sxs-lookup"><span data-stu-id="2e46e-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="2e46e-121">Selecteer in de sectie **kennis van organisatie** de optie **inhouds inzicht automatiseren**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Pagina voor het instellen van de organisatie](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="2e46e-123">Klik op de pagina **SharePoint Syntex automatiseren** op aan de **slag** om het installatieproces te doorlopen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Beginnen met instellen](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="2e46e-125">Kies op de pagina afbeeldingen label inschakelen de optie als u [afbeeldingen](image-tagging.md)wilt toestaan.</span><span class="sxs-lookup"><span data-stu-id="2e46e-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Schermafbeelding van opties voor markeren van afbeeldingen](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="2e46e-127">Op de pagina voor het verwerken van de **formulier** kunt u aangeven of u de gebruikers van AI Builder de mogelijkheid wilt bieden om formulier verwerkings modellen te maken met specifieke documentenbibliotheken van SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2e46e-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="2e46e-128">Er is een menuoptie beschikbaar op het lint van de documentbibliotheek om **een formulier verwerkings model te maken** in SharePoint-documentbibliotheken waarin dit is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2e46e-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="2e46e-129">Voor **welke SharePoint-bibliotheken moet de optie voor het maken van een formulier voor het bewerken van een formulier worden weergegeven**:</span><span class="sxs-lookup"><span data-stu-id="2e46e-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="2e46e-130">**Alle SharePoint-bibliotheken** als u deze beschikbaar wilt maken voor alle SharePoint-bibliotheken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2e46e-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="2e46e-131">**Alleen bibliotheken op geselecteerde sites**en selecteer vervolgens de sites waarvan u de site beschikbaar wilt maken.</span><span class="sxs-lookup"><span data-stu-id="2e46e-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Formulierverwerking configureren](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="2e46e-133">Als u deze instelling inschakelt voor een SharePoint-documentbibliotheek, heeft dit geen invloed op bestaande modellen die zijn toegepast op de bibliotheek of de mogelijkheid om documenten toe te passen op een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="2e46e-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="2e46e-134">Op de pagina **inhouds centrum maken** kunt u een SharePoint-inhouds centrum site maken waarop uw gebruikers document leren maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="2e46e-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="2e46e-135">a.</span><span class="sxs-lookup"><span data-stu-id="2e46e-135">a.</span></span> <span data-ttu-id="2e46e-136">Voor de naam van de **site**typt u de naam die uw inhouds centrum site moet opgeven.</span><span class="sxs-lookup"><span data-stu-id="2e46e-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="2e46e-137">b.</span><span class="sxs-lookup"><span data-stu-id="2e46e-137">b.</span></span> <span data-ttu-id="2e46e-138">Het **adres** van de site toont de URL voor uw site, op basis van de optie die u hebt geselecteerd voor de sitenaam.</span><span class="sxs-lookup"><span data-stu-id="2e46e-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="2e46e-139">Als u dit wilt wijzigen, klikt u op **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-139">If you want to change it, click **Edit**.</span></span></br>

      ![Inhouds centrum maken](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="2e46e-141">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-141">Select **Next**.</span></span>

7. <span data-ttu-id="2e46e-142">Op de pagina **controleren en voltooien** ziet u de geselecteerde instelling en kiest u om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2e46e-143">Als u tevreden bent met uw selecties, selecteert u **activeren**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="2e46e-144">Klik op de pagina confirmation op **done**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="2e46e-145">U gaat terug naar de pagina informatie **over het automatiseren** van de inhoud.</span><span class="sxs-lookup"><span data-stu-id="2e46e-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="2e46e-146">Op deze pagina kunt u **beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="2e46e-147">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="2e46e-147">Assign licenses</span></span>

<span data-ttu-id="2e46e-148">Als u een SharePoint-Syntex hebt geconfigureerd, moet u een licentie toewijzen voor de gebruikers die de functies voor formulierverwerking en document leren gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2e46e-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="2e46e-149">Licenties toewijzen:</span><span class="sxs-lookup"><span data-stu-id="2e46e-149">To assign licenses:</span></span>

1. <span data-ttu-id="2e46e-150">Klik in het Microsoft 365-Beheercentrum onder **gebruikers**op **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="2e46e-151">Selecteer de gebruikers voor wie u een licentie wilt instellen en klik op **productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="2e46e-152">Selecteer **meer toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="2e46e-153">Selecteer **intelligente inhouds Services**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="2e46e-154">Zorg ervoor dat onder **apps**de optie **common data service voor Intelligent Content Services** en **intelligente inhouds** service beide is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2e46e-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![SharePoint Syntex-licenties in het Microsoft 365-Beheercentrum](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="2e46e-156">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="2e46e-157">Tegoed van AI Builder</span><span class="sxs-lookup"><span data-stu-id="2e46e-157">AI Builder credits</span></span>

<span data-ttu-id="2e46e-158">Als u een 300 of meer SharePoint-Syntex-licenties voor SharePoint Syntex in uw organisatie hebt, worden er dan 1.000.000 AI Builder-tegoed toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="2e46e-159">Als u minder dan 300 licenties hebt, moet u de tegoed van de AI-Builders aanschaffen om de verwerking van formulieren te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2e46e-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="2e46e-160">U kunt de capaciteit van de AI Builder voor u ramen met de [AI Builder-rekenmachine](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="2e46e-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

1. <span data-ttu-id="2e46e-161">Ga naar het [Power platform-Beheercentrum](https://admin.powerplatform.microsoft.com/resources/capacity) om uw tegoed en gebruik te controleren.</span><span class="sxs-lookup"><span data-stu-id="2e46e-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e46e-162">Het inschakelen van deze instelling voor een SharePoint-documentbibliotheek heeft geen invloed op bestaande modellen die zijn toegepast op de bibliotheek of de mogelijkheid om documenten toe te passen op een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="2e46e-162">Enable this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
2. <span data-ttu-id="2e46e-163">Op de pagina **inhouds centrum maken** kunt u een SharePoint-inhouds centrum site maken waarvoor gebruikers document kunnen maken en beheren met modellen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-163">From the **Create Content Center** page, you can create a SharePoint content center site for which users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="2e46e-164">a.</span><span class="sxs-lookup"><span data-stu-id="2e46e-164">a.</span></span> <span data-ttu-id="2e46e-165">Voor de naam van de **site**typt u de gewenste naam voor de inhouds centrum site.</span><span class="sxs-lookup"><span data-stu-id="2e46e-165">For **Site name**, type the name you want for the content center site.</span></span></br>
    <span data-ttu-id="2e46e-166">b.</span><span class="sxs-lookup"><span data-stu-id="2e46e-166">b.</span></span> <span data-ttu-id="2e46e-167">Het **site adres** toont de URL voor uw site, op basis van de naam van de site.</span><span class="sxs-lookup"><span data-stu-id="2e46e-167">The **Site address** shows the URL for your site, based on the site name.</span></span></br>

    > [!NOTE] 
    > <span data-ttu-id="2e46e-168">U kunt alle ondersteunde talen selecteren, maar u kunt de inhoud van modellen niet alleen maken voor Engels.</span><span class="sxs-lookup"><span data-stu-id="2e46e-168">While you can select any supported language, content understanding models can only be created for English.</span></span></br>

      ![Inhouds centrum maken](../media/content-understanding/admin-cu-create-cc.png)</br>

3. <span data-ttu-id="2e46e-170">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-170">Select **Next**.</span></span>

4. <span data-ttu-id="2e46e-171">Bekijk op de pagina **Voltooien en controleren** de geselecteerde instelling en kies ervoor om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-171">On the **Finish and review** page, look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2e46e-172">Als u tevreden bent met uw selecties, selecteert u **activeren**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-172">If you are satisfied with your selections, select **Activate**.</span></span>

5. <span data-ttu-id="2e46e-173">Op de pagina met **geactiveerde pagina wat is geactiveerd** , wordt bevestigd dat het systeem uw voorkeuren voor formulierverwerking toevoegt en de inhouds centrum site heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2e46e-173">The **Content understanding activated** page displays, confirming the system added your form processing preferences and created the Content Center site.</span></span> <span data-ttu-id="2e46e-174">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="2e46e-174">Select **Done**.</span></span>

6. <span data-ttu-id="2e46e-175">U gaat terug naar de pagina informatie **over het automatiseren** van de inhoud.</span><span class="sxs-lookup"><span data-stu-id="2e46e-175">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="2e46e-176">Op deze pagina kunt u **beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="2e46e-176">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2e46e-177">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2e46e-177">See also</span></span>

[<span data-ttu-id="2e46e-178">Overzicht van het formulier verwerkings model</span><span class="sxs-lookup"><span data-stu-id="2e46e-178">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="2e46e-179">Stapsgewijze procedure: een document maken in overeenstemming met model (video)</span><span class="sxs-lookup"><span data-stu-id="2e46e-179">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

