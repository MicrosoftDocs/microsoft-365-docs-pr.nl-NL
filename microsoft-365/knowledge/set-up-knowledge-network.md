---
title: 'Kennisbeheer instellen (Voorbeeld) '
description: Hoe het opzetten van Kennismanagement.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540128"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="0084e-103">Kennisbeheer instellen (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="0084e-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="0084e-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="0084e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="0084e-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="0084e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="0084e-106">U het Microsoft 365-beheercentrum gebruiken om [Kennisbeheer](knowledge-management-overview.md)in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="0084e-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="0084e-107">Het is belangrijk om de beste manier te plannen om Kennisbeheer in uw omgeving in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="0084e-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="0084e-108">U moet bijvoorbeeld overwegingen maken over het volgende:</span><span class="sxs-lookup"><span data-stu-id="0084e-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="0084e-109">Welke SharePoint-sites u wilt analyseren voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="0084e-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="0084e-110">Voor welke gebruikers u onderwerpen zichtbaar wilt maken.</span><span class="sxs-lookup"><span data-stu-id="0084e-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="0084e-111">Welke gebruikers u machtigingen wilt geven om onderwerpen in het onderwerpcentrum te beheren.</span><span class="sxs-lookup"><span data-stu-id="0084e-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="0084e-112">Welke gebruikers u machtigingen wilt geven om onderwerpen in het onderwerpcentrum te maken of te bewerken.</span><span class="sxs-lookup"><span data-stu-id="0084e-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="0084e-113">Welke naam u uw onderwerpcentrum wilt geven.</span><span class="sxs-lookup"><span data-stu-id="0084e-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="0084e-114">Mogelijk vindt u het handig om beveiligingsgroepen te maken om uw gebruikers de machtigingen toe te wijzen die nodig zijn om onderwerpen te bekijken, onderwerpen te beheren en onderwerpen te maken en te bewerken.</span><span class="sxs-lookup"><span data-stu-id="0084e-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="0084e-115">Een beheerder kan ook [wijzigingen aanbrengen in uw geselecteerde instellingen op elk gewenst moment na de installatie](manage-knowledge-network.md) via de instellingen voor kennisbeheer in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0084e-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="0084e-116">Vereisten</span><span class="sxs-lookup"><span data-stu-id="0084e-116">Requirements</span></span> 
<span data-ttu-id="0084e-117">U moet globale beheerders- of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-beheercentrum en organisatorische kennistaken in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0084e-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="0084e-118">Uw kennisnetwerk opzetten</span><span class="sxs-lookup"><span data-stu-id="0084e-118">Set up your knowledge network</span></span>

<span data-ttu-id="0084e-119">Het opzetten van uw kennisnetwerk leidt u door het volgende:</span><span class="sxs-lookup"><span data-stu-id="0084e-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="0084e-120">Onderwerpdetectie: Onderwerpbronnen en onderwerpen selecteren om uit te sluiten van detectie.</span><span class="sxs-lookup"><span data-stu-id="0084e-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="0084e-121">Zichtbaarheid van het onderwerp: selecteren wie onderwerpen als hoogtepunten kan bekijken, in zoek- en onderwerppagina's.</span><span class="sxs-lookup"><span data-stu-id="0084e-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="0084e-122">Onderwerpmachtigingen: selecteren wie onderwerpen kan maken, bewerken en beheren.</span><span class="sxs-lookup"><span data-stu-id="0084e-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="0084e-123">Onderwerpcentrum: maak uw onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="0084e-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="0084e-124">Review: Controleer en pas je instellingen toe.</span><span class="sxs-lookup"><span data-stu-id="0084e-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="0084e-125">Ga als u naar het opzetten van uw kennisnetwerk:</span><span class="sxs-lookup"><span data-stu-id="0084e-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="0084e-126">Selecteer **Setup**in het Microsoft 365-beheercentrum (admin.microsoft.com) en bekijk de sectie **Organisatiekennis.**</span><span class="sxs-lookup"><span data-stu-id="0084e-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="0084e-127">Klik in de sectie **Organisatorische kennis** op **Mensen verbinden met kennis.**</span><span class="sxs-lookup"><span data-stu-id="0084e-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="0084e-129">Klik **op** de pagina Mensen verbinden met kennis op De klik **op Aan** de slag om u door het installatieproces te leiden.</span><span class="sxs-lookup"><span data-stu-id="0084e-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Aan de slag](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="0084e-131">Op de pagina **Kies hoe het kennisnetwerk onderwerpen kan vinden,** configureert u onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0084e-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="0084e-132">Selecteer in de sectie **SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie als bronnen voor uw onderwerpen worden gecrawld.</span><span class="sxs-lookup"><span data-stu-id="0084e-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0084e-133">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="0084e-133">This includes:</span></span></br>
    <span data-ttu-id="0084e-134">a.</span><span class="sxs-lookup"><span data-stu-id="0084e-134">a.</span></span> <span data-ttu-id="0084e-135">**Alle sites:** Alle SharePoint-sites in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0084e-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="0084e-136">Dit vangt huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="0084e-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="0084e-137">b.</span><span class="sxs-lookup"><span data-stu-id="0084e-137">b.</span></span> <span data-ttu-id="0084e-138">**Alles, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0084e-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0084e-139">U ook een lijst uploaden met sites die u wilt afmelden voor detectie.</span><span class="sxs-lookup"><span data-stu-id="0084e-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="0084e-140">Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0084e-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="0084e-141">c.</span><span class="sxs-lookup"><span data-stu-id="0084e-141">c.</span></span> <span data-ttu-id="0084e-142">**Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="0084e-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0084e-143">U ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="0084e-143">You can also upload a list of sites.</span></span> <span data-ttu-id="0084e-144">Sites die in de toekomst zijn gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0084e-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Kiezen hoe u onderwerpen vinden](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="0084e-146">In de sectie **Onderwerpen uitsluiten op naam** u ervoor kiezen namen op te nemen van onderwerpen die u niet wilt in de gedetecteerde resultaten.</span><span class="sxs-lookup"><span data-stu-id="0084e-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="0084e-147">Gebruik deze instelling om te voorkomen dat gevoelige onderwerpen worden opgenomen als onderdeel van het kennisnetwerk.</span><span class="sxs-lookup"><span data-stu-id="0084e-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="0084e-148">Uw opties zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="0084e-148">Your options include:</span></span></br>
    <span data-ttu-id="0084e-149">a.</span><span class="sxs-lookup"><span data-stu-id="0084e-149">a.</span></span> <span data-ttu-id="0084e-150">**Sluit onderwerpen niet uit**</span><span class="sxs-lookup"><span data-stu-id="0084e-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="0084e-151">b.</span><span class="sxs-lookup"><span data-stu-id="0084e-151">b.</span></span> <span data-ttu-id="0084e-152">**Onderwerp uitsluiten dat deze termen bevat:** Als u onderwerpen hebt die u niet aan gebruikers wilt laten zien als onderdeel van het kennisnetwerk.</span><span class="sxs-lookup"><span data-stu-id="0084e-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="0084e-153">- Download de meegeleverde template.</span><span class="sxs-lookup"><span data-stu-id="0084e-153">- Download the provided template.</span></span>
   <span data-ttu-id="0084e-154">- Voer de onderwerpnamen in die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0084e-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="0084e-155">U moet het type overeenkomst als exact of gedeeltelijk opgeven.</span><span class="sxs-lookup"><span data-stu-id="0084e-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="0084e-156">Exacte overeenkomst betekent dat onderwerpen die passen bij de exacte term worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="0084e-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="0084e-157">Gedeeltelijke overeenkomst is strenger en betekent dat onderwerpen die de term bevatten, worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="0084e-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="0084e-158">Als u bijvoorbeeld *Doc* als onderwerpnaam invoert, wordt *doc-assemblage* uitgesloten terwijl *Docker* dat niet doet.</span><span class="sxs-lookup"><span data-stu-id="0084e-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="0084e-159">De namen van het onderwerp zijn geval ongevoelig.</span><span class="sxs-lookup"><span data-stu-id="0084e-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="0084e-160">- Selecteer  **+**   om het ingevulde CSV-bestand te importeren.</span><span class="sxs-lookup"><span data-stu-id="0084e-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="0084e-161">Selecteer vervolgens **Uploaden**.</span><span class="sxs-lookup"><span data-stu-id="0084e-161">Then select **Upload**.</span></span> <span data-ttu-id="0084e-162">U ziet een groen vinkje als uw bestand is verwerkt.</span><span class="sxs-lookup"><span data-stu-id="0084e-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="0084e-163">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0084e-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="0084e-164">Op de **wie kan onderwerpen zien en waar ze ze kunnen zien** pagina, zult u configureren onderwerp zichtbaarheid.</span><span class="sxs-lookup"><span data-stu-id="0084e-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="0084e-165">In de instelling Wie kunnen onderwerpen zien in de instelling **kennisnetwerk,** kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, onderwerpantwoorden in zoekopdrachten en onderwerppagina's.</span><span class="sxs-lookup"><span data-stu-id="0084e-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="0084e-166">U kiezen:</span><span class="sxs-lookup"><span data-stu-id="0084e-166">You can select:</span></span></br>
    <span data-ttu-id="0084e-167">a.</span><span class="sxs-lookup"><span data-stu-id="0084e-167">a.</span></span> <span data-ttu-id="0084e-168">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="0084e-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="0084e-169">b.</span><span class="sxs-lookup"><span data-stu-id="0084e-169">b.</span></span> <span data-ttu-id="0084e-170">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="0084e-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="0084e-171">c.</span><span class="sxs-lookup"><span data-stu-id="0084e-171">c.</span></span> <span data-ttu-id="0084e-172">**Niemand.**</span><span class="sxs-lookup"><span data-stu-id="0084e-172">**No one**</span></span></br>

    ![Wie kan onderwerpen zien](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="0084e-174">Met deze instelling u een gebruiker in uw organisatie selecteren, maar alleen gebruikers die kennisbeheerlicenties aan hen hebben toegewezen, kunnen onderwerpen bekijken.</span><span class="sxs-lookup"><span data-stu-id="0084e-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="0084e-175">Op de pagina **Machtigingen voor onderwerpbeheer** kiest u wie onderwerpen kan maken, bewerken of beheren.</span><span class="sxs-lookup"><span data-stu-id="0084e-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="0084e-176">In de sectie **Wie kan onderwerpen maken en bewerken,** u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="0084e-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="0084e-177">a.</span><span class="sxs-lookup"><span data-stu-id="0084e-177">a.</span></span> <span data-ttu-id="0084e-178">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="0084e-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="0084e-179">b.</span><span class="sxs-lookup"><span data-stu-id="0084e-179">b.</span></span> <span data-ttu-id="0084e-180">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="0084e-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="0084e-181">In de sectie **Wie kan onderwerpen beheren,** u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="0084e-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="0084e-182">a.</span><span class="sxs-lookup"><span data-stu-id="0084e-182">a.</span></span> <span data-ttu-id="0084e-183">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="0084e-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="0084e-184">b.</span><span class="sxs-lookup"><span data-stu-id="0084e-184">b.</span></span> <span data-ttu-id="0084e-185">**Geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="0084e-185">**Selected people or security groups**</span></span></br>

    ![Machtigingen voor onderwerpbeheer](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="0084e-187">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0084e-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="0084e-188">Op de pagina **Onderwerpcentrum maken** u uw onderwerpcentrumsite maken waarin onderwerppagina's kunnen worden bekeken en onderwerpen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="0084e-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="0084e-189">Typ in het **vak Naam van het onderwerpcentrum** een naam voor het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="0084e-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="0084e-190">U optioneel een korte beschrijving typen in het vak **Sitebeschrijving.**</span><span class="sxs-lookup"><span data-stu-id="0084e-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="0084e-191">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0084e-191">Select **Next**.</span></span></br>

   ![Kenniscentrum maken](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="0084e-193">Op de pagina **Controleren en eindigen** u de geselecteerde instelling bekijken en ervoor kiezen wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="0084e-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="0084e-194">Als u tevreden bent met uw selecties, selecteert u **Activeren**.</span><span class="sxs-lookup"><span data-stu-id="0084e-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Afwerking en beoordeling](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="0084e-196">De geactiveerde pagina **kennisnetwerk** wordt weergegeven, die bevestigt dat het systeem nu begint met het analyseren van uw geselecteerde sites op onderwerpen en het maken van de Knowledge Center-site.</span><span class="sxs-lookup"><span data-stu-id="0084e-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="0084e-197">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0084e-197">Select **Done**.</span></span></br>

    ![Geactiveerd](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="0084e-199">Je wordt teruggestuurd naar je **contact met mensen die met elkaar in contact** komen.</span><span class="sxs-lookup"><span data-stu-id="0084e-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="0084e-200">Op deze pagina u **Beheren** selecteren om wijzigingen aan te brengen in uw configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="0084e-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Instellingen toegepast](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="0084e-202">Na de installatie kan een beheerder op elk gewenst moment [wijzigingen aanbrengen in de geselecteerde instellingen voor kennisbeheer](manage-knowledge-network.md) door terug te keren naar deze pagina.</span><span class="sxs-lookup"><span data-stu-id="0084e-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="0084e-203">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0084e-203">See also</span></span>



  






