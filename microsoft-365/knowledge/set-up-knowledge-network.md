---
title: 'Kennisbeheer instellen (preview) '
description: Het instellen van kennisbeheer.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612546"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="01ede-103">Kennisbeheer instellen (preview)</span><span class="sxs-lookup"><span data-stu-id="01ede-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="01ede-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="01ede-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="01ede-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="01ede-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="01ede-106">Met het Microsoft 365-Beheercentrum kunt u [kennisbeheer](knowledge-management-overview.md)instellen en configureren.</span><span class="sxs-lookup"><span data-stu-id="01ede-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="01ede-107">Het is belangrijk dat u de beste manier voor het instellen van kennisbeheer in uw omgeving de beste manier plant en configureert.</span><span class="sxs-lookup"><span data-stu-id="01ede-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="01ede-108">U moet bijvoorbeeld overwegingen voor het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="01ede-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="01ede-109">De SharePoint-sites die u voor onderwerpen wilt analyseren.</span><span class="sxs-lookup"><span data-stu-id="01ede-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="01ede-110">De gebruikers van wie u de onderwerpen zichtbaar wilt maken.</span><span class="sxs-lookup"><span data-stu-id="01ede-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="01ede-111">Welke gebruikers u machtigingen wilt geven om onderwerpen te beheren in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="01ede-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="01ede-112">Welke gebruikers u machtigingen wilt geven om onderwerpen te maken of te bewerken in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="01ede-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="01ede-113">De naam van het onderwerp dat u wilt geven.</span><span class="sxs-lookup"><span data-stu-id="01ede-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="01ede-114">Het kan handig zijn om beveiligingsgroepen te maken om uw gebruikers de benodigde machtigingen voor het weergeven van onderwerpen te zien, onderwerp te beheren en onderwerpen te maken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="01ede-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="01ede-115">Een beheerder kan ook [op elk gewenst moment na de installatie wijzigingen aanbrengen](manage-knowledge-network.md) in de instellingen voorkennis beheer in het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="01ede-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="01ede-116">Vereisten</span><span class="sxs-lookup"><span data-stu-id="01ede-116">Requirements</span></span> 
<span data-ttu-id="01ede-117">U moet een globale beheerder of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-Beheercentrum en om bedrijfsinformatie in te stellen.</span><span class="sxs-lookup"><span data-stu-id="01ede-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="01ede-118">Uw kennis netwerk instellen</span><span class="sxs-lookup"><span data-stu-id="01ede-118">Set up your knowledge network</span></span>

<span data-ttu-id="01ede-119">Het instellen van uw kennis netwerk begeleidt u door het volgende:</span><span class="sxs-lookup"><span data-stu-id="01ede-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="01ede-120">Onderwerp detecteren: het selecteren van onderwerpen bronnen en onderwerpen voor het opzeggen van detectie.</span><span class="sxs-lookup"><span data-stu-id="01ede-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="01ede-121">Onderwerp zichtbaar: wanneer u een gebruiker selecteert, kunt u deze onderwerpen als aandachtspunten weergeven op de tabbladen zoeken en onderwerp.</span><span class="sxs-lookup"><span data-stu-id="01ede-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="01ede-122">Onderwerp machtigingen: selecteren wie onderwerpen kan maken, bewerken en beheren.</span><span class="sxs-lookup"><span data-stu-id="01ede-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="01ede-123">Onderwerpen centrum: het onderwerpen centrum maken.</span><span class="sxs-lookup"><span data-stu-id="01ede-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="01ede-124">Controleren: de instellingen controleren en toepassen.</span><span class="sxs-lookup"><span data-stu-id="01ede-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="01ede-125">Uw kennis netwerk instellen:</span><span class="sxs-lookup"><span data-stu-id="01ede-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="01ede-126">In het Microsoft 365-Beheercentrum (admin.microsoft.com), selecteert u **instellingen**en vervolgens de afdelings informatie van de **organisatie** weergeven.</span><span class="sxs-lookup"><span data-stu-id="01ede-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="01ede-127">Klik in de sectie **kennis van organisatie** op **personen verbinden met kennis**.</span><span class="sxs-lookup"><span data-stu-id="01ede-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="01ede-129">Klik op de pagina **personen verbinden met kennis** op aan de slag om u door te **gaan** met het instellen van het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="01ede-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Aan de slag](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="01ede-131">Ga naar de pagina **Kies hoe u de pagina wilt zoeken** in het onderwerp: detectie van een kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="01ede-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="01ede-132">Selecteer in de sectie **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie.</span><span class="sxs-lookup"><span data-stu-id="01ede-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="01ede-133">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="01ede-133">This includes:</span></span></br>
    <span data-ttu-id="01ede-134">a.</span><span class="sxs-lookup"><span data-stu-id="01ede-134">a.</span></span> <span data-ttu-id="01ede-135">**Alle sites**: alle SharePoint-sites in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="01ede-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="01ede-136">Hiermee worden de huidige en toekomstige sites vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="01ede-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="01ede-137">b.</span><span class="sxs-lookup"><span data-stu-id="01ede-137">b.</span></span> <span data-ttu-id="01ede-138">**Alles, met uitzondering van geselecteerde sites**: Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="01ede-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="01ede-139">U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking.</span><span class="sxs-lookup"><span data-stu-id="01ede-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="01ede-140">Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="01ede-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="01ede-141">c.</span><span class="sxs-lookup"><span data-stu-id="01ede-141">c.</span></span> <span data-ttu-id="01ede-142">**Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="01ede-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="01ede-143">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="01ede-143">You can also upload a list of sites.</span></span> <span data-ttu-id="01ede-144">Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="01ede-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="01ede-146">In de sectie **onderwerpen uitsluiten van naam** kunt u kiezen of u namen wilt opnemen van onderwerpen die u niet wilt opnemen in de gedetecteerde resultaten.</span><span class="sxs-lookup"><span data-stu-id="01ede-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="01ede-147">Gebruik deze instelling om te voorkomen dat vertrouwelijke onderwerpen worden opgenomen als onderdeel van het kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="01ede-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="01ede-148">De opties zijn:</span><span class="sxs-lookup"><span data-stu-id="01ede-148">Your options include:</span></span></br>
    <span data-ttu-id="01ede-149">a.</span><span class="sxs-lookup"><span data-stu-id="01ede-149">a.</span></span> <span data-ttu-id="01ede-150">**Geen onderwerpen uitsluiten**</span><span class="sxs-lookup"><span data-stu-id="01ede-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="01ede-151">b.</span><span class="sxs-lookup"><span data-stu-id="01ede-151">b.</span></span> <span data-ttu-id="01ede-152">**Onderwerp met deze voorwaarden uitsluiten**: als u onderwerpen hebt die u niet wilt weergeven aan gebruikers als onderdeel van het kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="01ede-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="01ede-153">-De opgegeven sjabloon downloaden.</span><span class="sxs-lookup"><span data-stu-id="01ede-153">- Download the provided template.</span></span>
   <span data-ttu-id="01ede-154">-Voer de namen van de onderwerpen in die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="01ede-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="01ede-155">U moet het type overeenkomst als gelijk of gedeeltelijk opgeven.</span><span class="sxs-lookup"><span data-stu-id="01ede-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="01ede-156">Met exact vergelijken worden de onderwerpen die aan de exacte term voldoen, uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="01ede-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="01ede-157">Gedeeltelijke overeenkomst is strict, en houdt in dat onderwerpen die de term bevatten, niet worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="01ede-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="01ede-158">Als u bijvoorbeeld *doc* opgeeft als de naam van het onderwerp, wordt *document assemblage* uitgesloten voor de *dokweergave* .</span><span class="sxs-lookup"><span data-stu-id="01ede-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="01ede-159">Onderwerp namen zijn hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="01ede-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="01ede-160">-Selecteer  **+**   deze optie om het voltooide CSV-bestand te importeren.</span><span class="sxs-lookup"><span data-stu-id="01ede-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="01ede-161">Selecteer vervolgens **uploaden**.</span><span class="sxs-lookup"><span data-stu-id="01ede-161">Then select **Upload**.</span></span> <span data-ttu-id="01ede-162">U ziet een groen vinkje als het bestand is verwerkt.</span><span class="sxs-lookup"><span data-stu-id="01ede-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="01ede-163">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="01ede-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="01ede-164">In de pagina **wie kan de onderwerpen zien en waar ze deze kunnen zien** , wordt de zichtbaarheid van het onderwerp geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="01ede-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="01ede-165">In de instelling **wie kan de onderwerpen zien in de instelling van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, onderwerp Answers in Search en topic Pages.</span><span class="sxs-lookup"><span data-stu-id="01ede-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="01ede-166">U kunt kiezen voor:</span><span class="sxs-lookup"><span data-stu-id="01ede-166">You can select:</span></span></br>
    <span data-ttu-id="01ede-167">a.</span><span class="sxs-lookup"><span data-stu-id="01ede-167">a.</span></span> <span data-ttu-id="01ede-168">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="01ede-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="01ede-169">b.</span><span class="sxs-lookup"><span data-stu-id="01ede-169">b.</span></span> <span data-ttu-id="01ede-170">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="01ede-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="01ede-171">c.</span><span class="sxs-lookup"><span data-stu-id="01ede-171">c.</span></span> <span data-ttu-id="01ede-172">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="01ede-172">**No one**</span></span></br>

    ![Wie kan onderwerpen zien?](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="01ede-174">Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een licentie voorkennis beheer die aan hen zijn toegewezen, onderwerpen kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="01ede-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="01ede-175">Op de pagina **machtigingen voor onderwerp beheren** kiest u wie onderwerpen kan maken, bewerken en beheren.</span><span class="sxs-lookup"><span data-stu-id="01ede-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="01ede-176">In de sectie **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="01ede-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="01ede-177">a.</span><span class="sxs-lookup"><span data-stu-id="01ede-177">a.</span></span> <span data-ttu-id="01ede-178">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="01ede-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="01ede-179">b.</span><span class="sxs-lookup"><span data-stu-id="01ede-179">b.</span></span> <span data-ttu-id="01ede-180">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="01ede-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="01ede-181">In de sectie **wie kan secties beheren** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="01ede-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="01ede-182">a.</span><span class="sxs-lookup"><span data-stu-id="01ede-182">a.</span></span> <span data-ttu-id="01ede-183">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="01ede-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="01ede-184">b.</span><span class="sxs-lookup"><span data-stu-id="01ede-184">b.</span></span> <span data-ttu-id="01ede-185">**Geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="01ede-185">**Selected people or security groups**</span></span></br>

    ![Machtigingen voor onderwerp beheren](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="01ede-187">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="01ede-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="01ede-188">Op de pagina **topic maken** kunt u de site van het onderwerp maken waarin de onderwerpen kunnen worden weergegeven en de onderwerpen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="01ede-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="01ede-189">Typ in het vak **naam van onderwerp centrum** een naam voor het onderwerp Center.</span><span class="sxs-lookup"><span data-stu-id="01ede-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="01ede-190">U kunt desgewenst een korte beschrijving typen in het vak **Beschrijving van site** .</span><span class="sxs-lookup"><span data-stu-id="01ede-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="01ede-191">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="01ede-191">Select **Next**.</span></span></br>

   ![Kennis centrum maken](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="01ede-193">Op de pagina **controleren en voltooien** ziet u de geselecteerde instelling en kiest u om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="01ede-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="01ede-194">Als u tevreden bent met uw selecties, selecteert u **activeren**.</span><span class="sxs-lookup"><span data-stu-id="01ede-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Voltooien en controleren](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="01ede-196">De pagina voor **geactiveerde kennis netwerk** wordt weergegeven en u wordt bevestigd dat het systeem nu begint met het analyseren van de geselecteerde sites voor onderwerpen en de site van de Knowledge Center-site maakt.</span><span class="sxs-lookup"><span data-stu-id="01ede-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="01ede-197">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="01ede-197">Select **Done**.</span></span></br>

    ![Gestart](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="01ede-199">U gaat terug naar de pagina contact **personen verbinden met kennis** .</span><span class="sxs-lookup"><span data-stu-id="01ede-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="01ede-200">Op deze pagina kunt u **beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="01ede-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Instellingen toegepast](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="01ede-202">Na de installatie kan een beheerder op elk moment [wijzigingen aanbrengen in uw geselecteerde instellingen voorkennis beheer](manage-knowledge-network.md) , door terug te gaan naar deze pagina.</span><span class="sxs-lookup"><span data-stu-id="01ede-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="01ede-203">Zie ook</span><span class="sxs-lookup"><span data-stu-id="01ede-203">See also</span></span>



  






