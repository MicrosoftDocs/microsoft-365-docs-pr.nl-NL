---
title: SharePoint Syntex instellen
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Inhoudsbegrip instellen in Project Cortex
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683547"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="2634e-103">SharePoint Syntex instellen</span><span class="sxs-lookup"><span data-stu-id="2634e-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="2634e-104">Beheerders kunnen het Microsoft 365-beheercentrum gebruiken om [Microsoft SharePoint Syntex](index.md) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2634e-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="2634e-105">Houd rekening met het volgende voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="2634e-105">Consider the following before you start:</span></span>

- <span data-ttu-id="2634e-106">Op welke SharePoint-sites schakelt u het verwerken van formulieren in?</span><span class="sxs-lookup"><span data-stu-id="2634e-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="2634e-107">Op alle sites, enkele sites of alleen specifieke sites?</span><span class="sxs-lookup"><span data-stu-id="2634e-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="2634e-108">Welke naam geeft u aan uw standaard inhoudscentrum?</span><span class="sxs-lookup"><span data-stu-id="2634e-108">What will you name your default content center?</span></span>

<span data-ttu-id="2634e-109">U kunt de instellingen wijzigen na de eerste installatie in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2634e-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="2634e-p102">Plan voor het instellen de beste manier om inzicht in inhoud in uw omgeving in te stellen en te configureren. U moet bijvoorbeeld de volgende beslissingen nemen:</span><span class="sxs-lookup"><span data-stu-id="2634e-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="2634e-112">De SharePoint-sites waarvoor u de formulierverwerking wilt inschakelen; alle sites, enkele sites of specifieke sites</span><span class="sxs-lookup"><span data-stu-id="2634e-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="2634e-113">De naam en beheerders van het inhoudscentrum</span><span class="sxs-lookup"><span data-stu-id="2634e-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="2634e-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2634e-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="2634e-115">Je moet beschikken over de machtigingen van een globale beheerder of SharePoint-beheerder om toegang te krijgen tot het Microsoft 365-beheercentrum en SharePoint Syntex in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2634e-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="2634e-116">Als beheerder kunt u ook op elk gewenst moment wijzigingen aanbrengen in de geselecteerde instellingen en de beheerinstellingen voor inhoudsbegrip in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2634e-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

<span data-ttu-id="2634e-117">Als u van plan bent een aanpaste Power Platform-omgeving te gebruiken, [moet u de *AI Builder voor Project Cortex*-app in deze omgeving](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) installeren en [AI Builder-credits toewijzen](/power-platform/admin/capacity-add-on) voordat u formulierverwerkingsmodellen kunt maken.</span><span class="sxs-lookup"><span data-stu-id="2634e-117">If you plan to use a custom Power Platform environment, you must [install the *AI Builder for Project Cortex* app in this environment](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) and [allocate AI Builder credits](/power-platform/admin/capacity-add-on) to it before you can create form processing models.</span></span>

### <a name="licensing"></a><span data-ttu-id="2634e-118">Licentieverlening</span><span class="sxs-lookup"><span data-stu-id="2634e-118">Licensing</span></span>

<span data-ttu-id="2634e-119">Als u SharePoint Syntex wilt gebruiken, moet uw organisatie een abonnement op SharePoint Syntex hebben en moeten aan elke gebruiker de volgende licenties zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="2634e-119">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="2634e-120">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2634e-120">SharePoint Syntex</span></span>
- <span data-ttu-id="2634e-121">SharePoint Syntex - SPO-type</span><span class="sxs-lookup"><span data-stu-id="2634e-121">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="2634e-122">Common Data Service voor SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2634e-122">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="2634e-123">Als u uw SharePoint Syntex-abonnement in de toekomst opzegt (of als uw proefabonnement verloopt), kunnen gebruikers geen modellen voor documentbegrip of formulierverwerking meer maken of gebruiken en is de sjabloon voor het inhoudscentrum niet meer beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2634e-123">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="2634e-124">Bovendien zijn rapporten voor het termopslag, SKOS-taxonomieimports en push-inhoudstype niet meer beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2634e-124">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="2634e-125">Er wordt geen inhoud verwijderd en sitemachtigingen worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2634e-125">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="2634e-126">AI Builder-credits</span><span class="sxs-lookup"><span data-stu-id="2634e-126">AI Builder credits</span></span>

<span data-ttu-id="2634e-127">Als u 300 of meer SharePoint Syntex-licenties voor SharePoint Syntex in uw organisatie hebt, worden er 1 miljoen AI Builder-credits aan u toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2634e-127">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="2634e-128">Als u minder dan 300 licenties hebt, moet u AI Builder-credits kopen om formulierverwerking te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2634e-128">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="2634e-129">U kunt een schatting maken van de benodigde AI Builder-capaciteit [AI Builder-calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="2634e-129">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="2634e-130">Als u een aangepaste Power Platform-omgeving wilt gebruiken, moet u [tegoeden toewijzen aan die omgeving](/power-platform/admin/capacity-add-on).</span><span class="sxs-lookup"><span data-stu-id="2634e-130">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="2634e-131">Ga naar het [Power platform-beheercentrum](https://admin.powerplatform.microsoft.com/resources/capacity) om uw credits en gebruiksgegevens te bekijken.</span><span class="sxs-lookup"><span data-stu-id="2634e-131">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="2634e-132">SharePoint Syntex instellen</span><span class="sxs-lookup"><span data-stu-id="2634e-132">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="2634e-133">Selecteer **Instellingen** in het Microsoft 365-beheercentrum en bekijk het gedeelte **Bestanden en inhoud**.</span><span class="sxs-lookup"><span data-stu-id="2634e-133">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="2634e-134">Selecteer onder **Bestanden en inhoud** de optie **Inhoudsbegrip automatiseren**.</span><span class="sxs-lookup"><span data-stu-id="2634e-134">In the **Files and content** section, select **Automate content understanding**.</span></span> <span data-ttu-id="2634e-135">Uw huidige beschikbaarheid van AI Builder-credit weergegeven in de sectie **In één oogopslag**.</span><span class="sxs-lookup"><span data-stu-id="2634e-135">Note that your current AI Builder credit availability is shown in the **At a glance** section.</span></span><br/>

3. <span data-ttu-id="2634e-136">Klik op de pagina **Inhoudsbegrip automatiseren** op **Aan de slag** om het installatieproces te doorlopen.</span><span class="sxs-lookup"><span data-stu-id="2634e-136">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span> <br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2634e-137">![Installatie starten](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="2634e-137">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="2634e-138">Op de pagina **Formulierverwerking configureren** kunt u kiezen of u wilt dat gebruikers formulierverwerkingsmodellen kunnen maken in specifieke SharePoint-documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="2634e-138">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="2634e-139">Er is een menuoptie beschikbaar op het lint van de documentbibliotheek voor het **maken van een formulierverwerkingsmodel** in SharePoint-documentbibliotheken waarin dit is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2634e-139">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="2634e-140">Bij **Welke SharePoint-bibliotheken moeten de optie weergeven voor het maken van een formulierverwerkingsmodel**, kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="2634e-140">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="2634e-141">**Bibliotheken op alle SharePoint-sites** om de optie beschikbaar te maken voor alle SharePoint-bibliotheken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2634e-141">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="2634e-142">**Bibliotheken op geselecteerde SharePoint-sites**; selecteer vervolgens de sites waar u de optie beschikbaar wilt maken of upload een lijst met maximaal 50 sites.</span><span class="sxs-lookup"><span data-stu-id="2634e-142">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="2634e-143">**Geen SharePoint-bibliotheken** als u de optie niet beschikbaar wilt maken voor sites (u kunt dit wijzigen na de installatie).</span><span class="sxs-lookup"><span data-stu-id="2634e-143">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2634e-144">![Opties voor formulierverwerkingssites configureren](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="2634e-144">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="2634e-145">Het verwijderen van een site nadat deze is toegevoegd is niet van invloed op bestaande modellen die zijn toegepast op de bibliotheken in die site, of de mogelijkheid om documentbegrip toe te passen op een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="2634e-145">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="2634e-146">Als u meerdere Power Platform-omgevingen hebt geconfigureerd, kunt u kiezen welke u wilt gebruiken voor de formulierverwerking.</span><span class="sxs-lookup"><span data-stu-id="2634e-146">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="2634e-147">(Deze optie wordt niet weergegeven als u slechts één omgeving hebt.)</span><span class="sxs-lookup"><span data-stu-id="2634e-147">(This option will not appear if you only have one environment.)</span></span>

    ![Opties voor Power Platform-formulierverwerking configureren](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="2634e-149">Voor de **Power Platform-omgeving** kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="2634e-149">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="2634e-150">**Gebruik de standaardomgeving** om uw Power Platform-standaardomgeving te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2634e-150">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="2634e-151">**Gebruik een aangepaste omgeving** om een aangepaste omgeving te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2634e-151">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="2634e-152">Kies de omgeving die u wilt gebruiken uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="2634e-152">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="2634e-153">([Zie de vereisten voor een aangepaste omgeving](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span><span class="sxs-lookup"><span data-stu-id="2634e-153">([See the requirements for a custom environment](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span></span>

    <span data-ttu-id="2634e-154">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2634e-154">Click **Next**.</span></span>

5. <span data-ttu-id="2634e-155">Op de pagina **Inhoudscentrum maken** kunt u een SharePoint-inhoudscentrumsite maken waar gebruikers documentbegripmodellen kunnen maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="2634e-155">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="2634e-156">Typ voor **Sitenaam** de naam die u de inhoudscentrumsite wilt geven.</span><span class="sxs-lookup"><span data-stu-id="2634e-156">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="2634e-157">Bij **Siteadres** wordt de URL voor uw site weergegeven op basis van wat u hebt opgegeven als sitenaam.</span><span class="sxs-lookup"><span data-stu-id="2634e-157">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="2634e-158">Klik op **Bewerken** om dit te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2634e-158">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="2634e-159">![Inhoudscentrum maken](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="2634e-159">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="2634e-160">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="2634e-160">Select **Next**.</span></span>

6. <span data-ttu-id="2634e-161">Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="2634e-161">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2634e-162">Selecteer **Activeren** wanneer u tevreden bent met uw selecties.</span><span class="sxs-lookup"><span data-stu-id="2634e-162">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="2634e-163">Klik op **Gereed** op de bevestigingspagina.</span><span class="sxs-lookup"><span data-stu-id="2634e-163">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="2634e-164">U gaat terug naar de pagina **Inhoudsbegrip automatiseren**.</span><span class="sxs-lookup"><span data-stu-id="2634e-164">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="2634e-165">Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="2634e-165">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="2634e-166">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="2634e-166">Assign licenses</span></span>

<span data-ttu-id="2634e-167">Nadat u SharePoint Syntex hebt geconfigureerd, moet u licenties toewijzen voor de gebruikers die een SharePoint Syntex-functie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2634e-167">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="2634e-168">Licenties toewijzen:</span><span class="sxs-lookup"><span data-stu-id="2634e-168">To assign licenses:</span></span>

1. <span data-ttu-id="2634e-169">Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="2634e-169">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="2634e-170">Selecteer de gebruikers aan wie u een licentie wilt toewijzen en kies **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="2634e-170">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="2634e-171">Kies **Apps** in het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="2634e-171">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="2634e-172">Selecteer **Apps voor SharePoint Syntex weergeven**.</span><span class="sxs-lookup"><span data-stu-id="2634e-172">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="2634e-173">Zorg ervoor dat onder **Apps** **Algemene Gegevens sService voor SharePoint Syntex**, **SharePoint Syntex** en **SharePoint Syntex-SPO type** allemaal zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2634e-173">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2634e-174">![SharePoint Syntex-licenties in het Microsoft 365-beheercentrum](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="2634e-174">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="2634e-175">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2634e-175">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2634e-176">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2634e-176">See also</span></span>

[<span data-ttu-id="2634e-177">Overzicht van het formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="2634e-177">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="2634e-178">Stap voor stap: een documentbegripmodel maken (video)</span><span class="sxs-lookup"><span data-stu-id="2634e-178">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

[<span data-ttu-id="2634e-179">Omgevingen maken en beheren in het Power Platform-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="2634e-179">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
