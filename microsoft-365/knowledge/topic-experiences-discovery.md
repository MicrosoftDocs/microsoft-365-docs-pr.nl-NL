---
title: 'Uw kennisbeheer netwerk beheren (preview) '
description: Het instellen van kennisbeheer.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 265816a8d3d04b8d10b529f1ea1a0b658aa2931d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988949"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="f6c34-103">Uw kennisbeheer netwerk beheren (preview)</span><span class="sxs-lookup"><span data-stu-id="f6c34-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="f6c34-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="f6c34-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="f6c34-105">[Meer informatie over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f6c34-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="f6c34-106">Nadat u [kennisbeheer hebt ingesteld](set-up-topic-experiences.md), kunt u op elk gewenst moment een beheerder de configuratie-instellingen wijzigen via het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f6c34-106">After you [set up knowledge management](set-up-topic-experiences.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f6c34-107">U moet bijvoorbeeld de instellingen voor de volgende opties wijzigen:</span><span class="sxs-lookup"><span data-stu-id="f6c34-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="f6c34-108">Nieuwe SharePoint-bronnen toevoegen aan mijn onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f6c34-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="f6c34-109">Wijzig welke gebruikers toegang hebben tot onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f6c34-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="f6c34-110">Wijzig welke gebruikers gemachtigd zijn om taken uit te voeren in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="f6c34-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="f6c34-111">De naam van het topic Center wijzigen</span><span class="sxs-lookup"><span data-stu-id="f6c34-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="f6c34-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="f6c34-112">Requirements</span></span> 
<span data-ttu-id="f6c34-113">U moet een globale beheerder of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-Beheercentrum en om organisatie-kennis taken te kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="f6c34-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="f6c34-114">Toegang krijgen tot de instellingen van kennisbeheer:</span><span class="sxs-lookup"><span data-stu-id="f6c34-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="f6c34-115">Selecteer in het Microsoft 365-Beheercentrum de optie **instellen** en bekijk vervolgens de sectie **bedrijfsinformatie** .</span><span class="sxs-lookup"><span data-stu-id="f6c34-115">In the Microsoft 365 admin center, select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="f6c34-116">Klik in de sectie **kennis van organisatie** op **personen verbinden met kennis**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="f6c34-118">Selecteer op de pagina **personen verbinden met kennis** de optie **beheren** om het deelvenster instellingen van het **kennis netwerk** te openen.</span><span class="sxs-lookup"><span data-stu-id="f6c34-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![kennis netwerk-instellingen](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="f6c34-120">Wijzigen hoe het kennis netwerk onderwerpen kan vinden</span><span class="sxs-lookup"><span data-stu-id="f6c34-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="f6c34-121">Selecteer het tabblad detectie van het **onderwerp** als u de keuzes voor de bronnen van het SharePoint-onderwerp wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f6c34-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="f6c34-122">Met deze instelling kunt u de SharePoint-sites in de Tenant selecteren die worden verkend en mined voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f6c34-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="f6c34-123">Selecteer op het tabblad **topic Discovery** onder **Select SharePoint topics** de optie **Edit**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-123">On the **Topic discovery** tab, under **Select SharePoint topic sources** , select **Edit**.</span></span>
2. <span data-ttu-id="f6c34-124">Selecteer op de pagina **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie.</span><span class="sxs-lookup"><span data-stu-id="f6c34-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="f6c34-125">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="f6c34-125">This includes:</span></span></br>
    <span data-ttu-id="f6c34-126">a.</span><span class="sxs-lookup"><span data-stu-id="f6c34-126">a.</span></span> <span data-ttu-id="f6c34-127">**Alle sites** : alle SharePoint-sites in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="f6c34-127">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="f6c34-128">Hiermee worden de huidige en toekomstige sites vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="f6c34-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="f6c34-129">b.</span><span class="sxs-lookup"><span data-stu-id="f6c34-129">b.</span></span> <span data-ttu-id="f6c34-130">**Alles, met uitzondering van geselecteerde sites** : Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="f6c34-130">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="f6c34-131">U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking.</span><span class="sxs-lookup"><span data-stu-id="f6c34-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="f6c34-132">Sites die u later maakt, worden opgenomen als bronnen voor het detecteren van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="f6c34-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="f6c34-133">c.</span><span class="sxs-lookup"><span data-stu-id="f6c34-133">c.</span></span> <span data-ttu-id="f6c34-134">**Alleen geselecteerde sites** : Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="f6c34-134">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="f6c34-135">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="f6c34-135">You can also upload a list of sites.</span></span> <span data-ttu-id="f6c34-136">Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="f6c34-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="f6c34-138">Als u een aantal sites hebt die u wilt uitsluiten (als u **alles selecteert, met uitzondering van geselecteerde sites** ) of opnemen (als u **alleen geselecteerde sites** hebt geselecteerd), kunt u ervoor kiezen om een CSV-bestand met de sitenamen en url's te uploaden.</span><span class="sxs-lookup"><span data-stu-id="f6c34-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites** ) or include (if you selected **Only selected sites** ), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="f6c34-139">Selecteer **sitesjabloon. csv downloaden** als u het CSV-sjabloonbestand wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f6c34-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="f6c34-140">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="f6c34-141">Wijzigen wie de onderwerpen in uw organisatie kunnen zien</span><span class="sxs-lookup"><span data-stu-id="f6c34-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="f6c34-142">Selecteer het tabblad detectie van het **onderwerp** als u wilt bijwerken wie in uw organisatie gedetecteerde onderwerpen kan zien in zoekresultaten en wanneer onderwerpen zijn gemarkeerd met inhoud zoals SharePoint-pagina's.</span><span class="sxs-lookup"><span data-stu-id="f6c34-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="f6c34-143">Selecteer op het tabblad **onderwerp detecteren** onder **wie kan de onderwerpen in het kennis netwerk zien** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network** , select **Edit**.</span></span>
2. <span data-ttu-id="f6c34-144">Op de pagina **wie kan de onderwerpen zien op de pagina van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, topic Answers in Search en topic Pages.</span><span class="sxs-lookup"><span data-stu-id="f6c34-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="f6c34-145">U kunt kiezen voor:</span><span class="sxs-lookup"><span data-stu-id="f6c34-145">You can select:</span></span></br>
    <span data-ttu-id="f6c34-146">a.</span><span class="sxs-lookup"><span data-stu-id="f6c34-146">a.</span></span> <span data-ttu-id="f6c34-147">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="f6c34-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f6c34-148">b.</span><span class="sxs-lookup"><span data-stu-id="f6c34-148">b.</span></span> <span data-ttu-id="f6c34-149">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f6c34-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="f6c34-150">c.</span><span class="sxs-lookup"><span data-stu-id="f6c34-150">c.</span></span> <span data-ttu-id="f6c34-151">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="f6c34-151">**No one**</span></span></br>

    ![Wie kan onderwerpen zien?](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="f6c34-153">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="f6c34-154">Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een licentie voorkennis beheer die aan hen zijn toegewezen, onderwerpen kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="f6c34-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="f6c34-155">Wijzigen wie gemachtigd is om taken uit te voeren in het onderwerp centrum</span><span class="sxs-lookup"><span data-stu-id="f6c34-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="f6c34-156">Selecteer het tabblad **onderwerp machtigingen** als u het volgende wilt bijwerken op de pagina met het onderwerp centrum:</span><span class="sxs-lookup"><span data-stu-id="f6c34-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="f6c34-157">Welke gebruikers kunnen onderwerpen maken en bewerken: nieuwe onderwerpen maken die niet zijn gevonden tijdens het detecteren of bewerken van bestaande Details van een onderwerppagina.</span><span class="sxs-lookup"><span data-stu-id="f6c34-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="f6c34-158">Welke gebruikers onderwerpen kunnen beheren: gedetecteerde of genegeerde onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f6c34-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="f6c34-159">Een update maken van de gebruikers die gemachtigd zijn om onderwerpen te maken en bewerken:</span><span class="sxs-lookup"><span data-stu-id="f6c34-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="f6c34-160">Selecteer op het tabblad **onderwerp machtigingen** onder **wie kan onderwerpen maken en bewerken** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-160">On the **Topic permissions** tab, under **Who can create and edit topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="f6c34-161">Op de pagina **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="f6c34-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="f6c34-162">a.</span><span class="sxs-lookup"><span data-stu-id="f6c34-162">a.</span></span> <span data-ttu-id="f6c34-163">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="f6c34-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f6c34-164">b.</span><span class="sxs-lookup"><span data-stu-id="f6c34-164">b.</span></span> <span data-ttu-id="f6c34-165">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f6c34-165">**Only selected people or security groups**</span></span></br>

    ![Onderwerpen maken en bewerken](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="f6c34-167">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-167">Select **Save**.</span></span></br>

<span data-ttu-id="f6c34-168">Bijwerken met de gebruikers die gemachtigd zijn om onderwerpen te beheren:</span><span class="sxs-lookup"><span data-stu-id="f6c34-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="f6c34-169">Selecteer op het tabblad **machtigingen voor onderwerp** onder **wie kan onderwerpen beheren** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-169">On the **Topic permissions** tab, under **Who can manage topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="f6c34-170">Op de pagina **wie kan onderwerpen beheren** , kunt u de volgende opties kiezen:</span><span class="sxs-lookup"><span data-stu-id="f6c34-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="f6c34-171">a.</span><span class="sxs-lookup"><span data-stu-id="f6c34-171">a.</span></span> <span data-ttu-id="f6c34-172">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="f6c34-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f6c34-173">b.</span><span class="sxs-lookup"><span data-stu-id="f6c34-173">b.</span></span> <span data-ttu-id="f6c34-174">**Geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f6c34-174">**Selected people or security groups**</span></span></br>

    ![Onderwerpen beheren](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="f6c34-176">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="f6c34-177">De naam van uw topic Center bijwerken</span><span class="sxs-lookup"><span data-stu-id="f6c34-177">Update your topic center name</span></span>

<span data-ttu-id="f6c34-178">Selecteer het tabblad **onderwerp centrum** als u de naam van het onderwerp centrum wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f6c34-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="f6c34-179">Selecteer op het tabblad **onderwerp centrum** , onder **naam onderwerp centrum** , de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f6c34-179">On the **Topic center** tab, under **Topic center name** , select **Edit**.</span></span>
2. <span data-ttu-id="f6c34-180">Typ op de paginanaam van het **centrum voor bewerken** , in het vak **naam van onderwerp centrum** , de nieuwe naam voor het onderwerp Center.</span><span class="sxs-lookup"><span data-stu-id="f6c34-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="f6c34-181">Selecteer **Opslaan** .</span><span class="sxs-lookup"><span data-stu-id="f6c34-181">Select **Save**</span></span>

    ![Naam van onderwerp centrum bewerken](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="f6c34-183">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f6c34-183">See also</span></span>



  






