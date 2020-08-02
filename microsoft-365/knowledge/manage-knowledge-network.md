---
title: 'Uw kennisbeheernetwerk beheren(Voorbeeld) '
description: Hoe het opzetten van Kennismanagement.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540116"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="fd0a2-103">Beheer uw kennisbeheernetwerk (Preview)</span><span class="sxs-lookup"><span data-stu-id="fd0a2-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="fd0a2-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="fd0a2-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="fd0a2-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="fd0a2-106">Nadat u kennisbeheer hebt [ingesteld,](set-up-knowledge-network.md)kan een beheerder op elk gewenst moment daarna uw configuratie-instellingen aanpassen via het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="fd0a2-107">Het kan bijvoorbeeld nodig zijn om uw instellingen aan te passen voor een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="fd0a2-108">Voeg nieuwe SharePoint-bronnen toe aan mijnonderwerpen.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="fd0a2-109">Wijzig welke gebruikers toegang hebben tot onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="fd0a2-110">Wijzig welke gebruikers machtigingen hebben om taken uit te voeren in het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="fd0a2-111">De naam van uw onderwerpcentrum wijzigen</span><span class="sxs-lookup"><span data-stu-id="fd0a2-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="fd0a2-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="fd0a2-112">Requirements</span></span> 
<span data-ttu-id="fd0a2-113">U moet globale beheerders- of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-beheercentrum en organisatorische kennistaken te beheren.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="fd0a2-114">Ga alst u naar instellingen voor kennisbeheer:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="fd0a2-115">Selecteer **Setup**in het Microsoft 365-beheercentrum en bekijk de sectie **Organisatiekennis.**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="fd0a2-116">Klik in de sectie **Organisatorische kennis** op **Mensen verbinden met kennis.**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="fd0a2-118">Selecteer **beheren** om het deelvenster **Instellingen** voor kennis te openen op de pagina Personen verbinden **met kennis.**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![kennisnetwerkinstellingen](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="fd0a2-120">Wijzigen hoe het kennisnetwerk onderwerpen kan vinden</span><span class="sxs-lookup"><span data-stu-id="fd0a2-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="fd0a2-121">Selecteer het tabblad **Onderwerpdetectie** als u uw keuzes voor SharePoint-onderwerpbronnen wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="fd0a2-122">Met deze instelling u de SharePoint-sites in uw tenant selecteren die worden gecrawld en gedolven voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="fd0a2-123">Selecteer op het tabblad **Onderwerpdetectie** onder **SharePoint-onderwerpbronnen selecteren**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="fd0a2-124">Selecteer op de pagina **SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie als bronnen voor uw onderwerpen worden gecrawld.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="fd0a2-125">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-125">This includes:</span></span></br>
    <span data-ttu-id="fd0a2-126">a.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-126">a.</span></span> <span data-ttu-id="fd0a2-127">**Alle sites:** Alle SharePoint-sites in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="fd0a2-128">Dit vangt huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="fd0a2-129">b.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-129">b.</span></span> <span data-ttu-id="fd0a2-130">**Alles, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="fd0a2-131">U ook een lijst uploaden met sites die u wilt afmelden voor detectie.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="fd0a2-132">Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="fd0a2-133">c.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-133">c.</span></span> <span data-ttu-id="fd0a2-134">**Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="fd0a2-135">U ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-135">You can also upload a list of sites.</span></span> <span data-ttu-id="fd0a2-136">Sites die in de toekomst zijn gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Kiezen hoe u onderwerpen vinden](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="fd0a2-138">Als u een aantal sites hebt die u wilt uitsluiten (als u **Alles selecteert, behalve geselecteerde sites)** of opneemt (als u Alleen geselecteerde sites **hebt**geselecteerd), u ervoor kiezen om een CSV-bestand te uploaden met de sitenamen en URL's.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="fd0a2-139">U **sitesjabloon downloaden (csv)** selecteren als u het CSV-sjabloonbestand wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="fd0a2-140">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="fd0a2-141">Wijzigen wie onderwerpen in uw organisatie kan zien</span><span class="sxs-lookup"><span data-stu-id="fd0a2-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="fd0a2-142">Selecteer het tabblad **Onderwerpdetectie** als u wilt bijwerken wie in uw organisatie gedetecteerde onderwerpen in zoekresultaten kan zien en wanneer onderwerpen worden gemarkeerd in inhoud zoals SharePoint-pagina's.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="fd0a2-143">Selecteer op het tabblad **Onderwerpdetectie** onder **Wie onderwerpen in het kennisnetwerk kan zien**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="fd0a2-144">Op de pagina Wie kan onderwerpen zien op de pagina **kennisnetwerk,** kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, onderwerpantwoorden in zoekopdrachten en onderwerppagina's.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="fd0a2-145">U kiezen:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-145">You can select:</span></span></br>
    <span data-ttu-id="fd0a2-146">a.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-146">a.</span></span> <span data-ttu-id="fd0a2-147">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fd0a2-148">b.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-148">b.</span></span> <span data-ttu-id="fd0a2-149">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="fd0a2-150">c.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-150">c.</span></span> <span data-ttu-id="fd0a2-151">**Niemand.**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-151">**No one**</span></span></br>

    ![Wie kan onderwerpen zien](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="fd0a2-153">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="fd0a2-154">Met deze instelling u een gebruiker in uw organisatie selecteren, maar alleen gebruikers die kennisbeheerlicenties aan hen hebben toegewezen, kunnen onderwerpen bekijken.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="fd0a2-155">Wijzigen wie machtigingen heeft om taken uit te voeren in het onderwerpcentrum</span><span class="sxs-lookup"><span data-stu-id="fd0a2-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="fd0a2-156">Selecteer het tabblad **Onderwerpmachtigingen** als u wilt bijwerken wie machtigingen heeft om het volgende te doen op de pagina met onderwerpcentrum:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="fd0a2-157">Welke gebruikers onderwerpen kunnen maken en bewerken: maak nieuwe onderwerpen die niet zijn gevonden tijdens de detectie of bewerk bestaande onderwerppaginadetails.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="fd0a2-158">Welke gebruikers onderwerpen kunnen beheren: Ontdekte onderwerpen bevestigen of afwijzen.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="fd0a2-159">Ga als u aan de informatie over wie machtigingen heeft om onderwerpen te maken en te bewerken:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="fd0a2-160">Selecteer op het tabblad **Onderwerpmachtigingen** onder **Wie onderwerpen kan maken en bewerken**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="fd0a2-161">Op de pagina **Wie kan onderwerpen maken en bewerken,** u het:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="fd0a2-162">a.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-162">a.</span></span> <span data-ttu-id="fd0a2-163">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fd0a2-164">b.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-164">b.</span></span> <span data-ttu-id="fd0a2-165">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-165">**Only selected people or security groups**</span></span></br>

    ![Onderwerpen maken en bewerken](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="fd0a2-167">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-167">Select **Save**.</span></span></br>

<span data-ttu-id="fd0a2-168">Ga als u als gaat over het bijwerken van wie machtigingen heeft om onderwerpen te beheren:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="fd0a2-169">Selecteer op het tabblad **Onderwerpmachtigingen** onder **Wie onderwerpen kan beheren**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="fd0a2-170">Op de pagina **Wie kan onderwerpen beheren,** u het:</span><span class="sxs-lookup"><span data-stu-id="fd0a2-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="fd0a2-171">a.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-171">a.</span></span> <span data-ttu-id="fd0a2-172">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="fd0a2-173">b.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-173">b.</span></span> <span data-ttu-id="fd0a2-174">**Geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-174">**Selected people or security groups**</span></span></br>

    ![Onderwerpen beheren](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="fd0a2-176">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="fd0a2-177">De naam van het onderwerpcentrum bijwerken</span><span class="sxs-lookup"><span data-stu-id="fd0a2-177">Update your topic center name</span></span>

<span data-ttu-id="fd0a2-178">Selecteer het tabblad **Onderwerpcentrum** als u de naam van het onderwerpcentrum wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="fd0a2-179">Selecteer op het tabblad **Onderwerpcentrum** onder **Naam van het onderwerpcentrum**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="fd0a2-180">Typ op de **pagina Onderwerpcentrumnaam bewerken** in het **vak Onderwerpcentrumnaam** de nieuwe naam voor het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="fd0a2-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="fd0a2-181">Selecteer **Opslaan**</span><span class="sxs-lookup"><span data-stu-id="fd0a2-181">Select **Save**</span></span>

    ![Naam van het onderwerpcentrum bewerken](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="fd0a2-183">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fd0a2-183">See also</span></span>



  






