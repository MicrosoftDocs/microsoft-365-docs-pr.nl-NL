---
title: SharePoint Syntex instellen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Inhoudsbegrip instellen in Project Cortex
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087569"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="bb681-103">SharePoint Syntex instellen</span><span class="sxs-lookup"><span data-stu-id="bb681-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="bb681-104">Beheerders kunnen het Microsoft 365-beheercentrum gebruiken om [Microsoft SharePoint Syntex](index.md) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="bb681-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="bb681-105">Houd rekening met het volgende voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="bb681-105">Consider the following before you start:</span></span>

- <span data-ttu-id="bb681-p101">Which SharePoint sites will you enable form processing? All of them, some, or select sites?</span><span class="sxs-lookup"><span data-stu-id="bb681-p101">Which SharePoint sites will you enable form processing? All of them, some, or select sites?</span></span>
- <span data-ttu-id="bb681-108">Wat is de naam van uw standaard inhoudscentrum?</span><span class="sxs-lookup"><span data-stu-id="bb681-108">What will you name of your default content center?</span></span>

<span data-ttu-id="bb681-109">U kunt de instellingen wijzigen na de eerste installatie in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="bb681-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="bb681-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:</span><span class="sxs-lookup"><span data-stu-id="bb681-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="bb681-112">De SharePoint-sites waarvoor u de formulierverwerking wilt inschakelen; alle sites, enkele sites of specifieke sites</span><span class="sxs-lookup"><span data-stu-id="bb681-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="bb681-113">Uw inhoudscentrum en de naam van de primaire beheerder van de site</span><span class="sxs-lookup"><span data-stu-id="bb681-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="bb681-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="bb681-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="bb681-115">U moet beschikken over de machtigingen van een globale beheerder of SharePoint-beheerder om toegang te krijgen tot het Microsoft 365-beheercentrum en inhoudsbegrip in te stellen.</span><span class="sxs-lookup"><span data-stu-id="bb681-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="bb681-116">Als beheerder kunt u ook op elk gewenst moment wijzigingen aanbrengen in de geselecteerde instellingen en de beheerinstellingen voor inhoudsbegrip in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="bb681-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="bb681-117">SharePoint Syntex instellen</span><span class="sxs-lookup"><span data-stu-id="bb681-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="bb681-118">Selecteer **Instellingen** in het Microsoft 365-beheercentrum en bekijk het gedeelte **Bestanden en inhoud**.</span><span class="sxs-lookup"><span data-stu-id="bb681-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="bb681-119">Selecteer onder **Bestanden en inhoud** de optie **Inhoudsbegrip automatiseren**.</span><span class="sxs-lookup"><span data-stu-id="bb681-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="bb681-120">Klik op de pagina **Inhoudsbegrip automatiseren** op **Aan de slag** om het installatieproces te doorlopen.</span><span class="sxs-lookup"><span data-stu-id="bb681-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bb681-121">![Installatie starten](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="bb681-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="bb681-p103">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span><span class="sxs-lookup"><span data-stu-id="bb681-p103">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="bb681-124">Bij **Welke SharePoint-bibliotheken moeten de optie weergeven voor het maken van een formulierverwerkingsmodel**, kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="bb681-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="bb681-125">**Alle SharePoint-bibliotheken** om de optie beschikbaar te maken voor alle SharePoint-bibliotheken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bb681-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="bb681-126">**Alleen bibliotheken op geselecteerde sites**; selecteer vervolgens de sites waar u de optie beschikbaar wilt maken of upload een lijst met maximaal 50 sites.</span><span class="sxs-lookup"><span data-stu-id="bb681-126">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="bb681-127">**Geen SharePoint-bibliotheken** als u de optie niet beschikbaar wilt maken voor sites (u kunt dit wijzigen na de installatie).</span><span class="sxs-lookup"><span data-stu-id="bb681-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb681-128">![Formulierverwerking configureren](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="bb681-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="bb681-129">Het verwijderen van een site nadat deze is toegevoegd is niet van invloed op bestaande modellen die zijn toegepast op de bibliotheken in die site, of de mogelijkheid om documentbegrip toe te passen op een bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="bb681-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="bb681-130">Op de pagina **Inhoudscentrum maken** kunt u een SharePoint-inhoudscentrumsite maken waar gebruikers documentbegripmodellen kunnen maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="bb681-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="bb681-131">Typ voor **Sitenaam** de naam die u de inhoudscentrumsite wilt geven.</span><span class="sxs-lookup"><span data-stu-id="bb681-131">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="bb681-p104">The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="bb681-p104">The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="bb681-134">![Inhoudscentrum maken](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="bb681-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="bb681-135">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="bb681-135">Select **Next**.</span></span>

6. <span data-ttu-id="bb681-p105">On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.</span><span class="sxs-lookup"><span data-stu-id="bb681-p105">On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="bb681-138">Klik op **Gereed** op de bevestigingspagina.</span><span class="sxs-lookup"><span data-stu-id="bb681-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="bb681-p106">You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings.</span><span class="sxs-lookup"><span data-stu-id="bb681-p106">You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="bb681-141">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="bb681-141">Assign licenses</span></span>

<span data-ttu-id="bb681-142">Nadat u SharePoint Syntex hebt geconfigureerd, moet u licenties toewijzen voor de gebruikers die een SharePoint Syntex-functie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bb681-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="bb681-143">Licenties toewijzen:</span><span class="sxs-lookup"><span data-stu-id="bb681-143">To assign licenses:</span></span>

1. <span data-ttu-id="bb681-144">Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="bb681-144">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="bb681-145">Selecteer de gebruikers aan wie u een licentie wilt toewijzen en klik op **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="bb681-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="bb681-146">Selecteer **Meer toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="bb681-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="bb681-p107">Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span><span class="sxs-lookup"><span data-stu-id="bb681-p107">Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bb681-149">![SharePoint Syntex-licenties in het Microsoft 365-beheercentrum](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="bb681-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="bb681-150">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bb681-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="bb681-151">AI Builder-credits</span><span class="sxs-lookup"><span data-stu-id="bb681-151">AI Builder credits</span></span>

<span data-ttu-id="bb681-p108">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span><span class="sxs-lookup"><span data-stu-id="bb681-p108">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="bb681-154">U kunt een schatting maken van de benodigde AI Builder-capaciteit [AI Builder-calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="bb681-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="bb681-155">Ga naar het [Power platform-beheercentrum](https://admin.powerplatform.microsoft.com/resources/capacity) om uw credits en gebruiksgegevens te bekijken.</span><span class="sxs-lookup"><span data-stu-id="bb681-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb681-156">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bb681-156">See also</span></span>

[<span data-ttu-id="bb681-157">Overzicht van het formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="bb681-157">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="bb681-158">Stap voor stap: een documentbegripmodel maken (video)</span><span class="sxs-lookup"><span data-stu-id="bb681-158">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

