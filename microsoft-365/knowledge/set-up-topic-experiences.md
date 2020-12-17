---
title: Onderwerpen over functies instellen in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het instellen van onderwerps functies in Microsoft 365
ms.openlocfilehash: e11f0b75556a4a8ac0ffa40269d7166258128daf
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698553"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="9d697-103">Onderwerpen over functies instellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d697-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="9d697-104">Met het Microsoft 365-Beheercentrum kunt u [topic Experience](topic-experiences-overview.md)instellen en configureren.</span><span class="sxs-lookup"><span data-stu-id="9d697-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="9d697-105">Het is belangrijk dat u de beste manier voor het plannen en configureren van onderwerpen in uw omgeving van plan bent.</span><span class="sxs-lookup"><span data-stu-id="9d697-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="9d697-106">Zorg ervoor dat u de ervaringen van het [plan](plan-topic-experiences.md) vindt voordat u de procedures in dit artikel start.</span><span class="sxs-lookup"><span data-stu-id="9d697-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="9d697-107">U moet een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-Beheercentrum en de functies voor het onderwerp in te stellen.</span><span class="sxs-lookup"><span data-stu-id="9d697-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="9d697-108">Ervaring met het onderwerp instellen</span><span class="sxs-lookup"><span data-stu-id="9d697-108">Set up topic experiences</span></span>

<span data-ttu-id="9d697-109">Topic Experience instellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d697-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="9d697-110">Selecteer in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com)de optie **Setup** en vervolgens de sectie **bestanden en inhoud** weergeven.</span><span class="sxs-lookup"><span data-stu-id="9d697-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="9d697-111">Klik in de sectie **bestanden en inhoud** op **personen verbinden met kennis**.</span><span class="sxs-lookup"><span data-stu-id="9d697-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Mensen verbinden met kennis](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="9d697-113">Klik op de pagina **personen verbinden met kennis** op aan de slag om u door te **gaan** met het instellen van het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="9d697-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Aan de slag](../media/k-get-started.png) 

4. <span data-ttu-id="9d697-115">Ga naar de pagina **Kies hoe u de pagina wilt zoeken** in het onderwerp: detectie van een kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="9d697-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="9d697-116">Selecteer in de sectie **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie.</span><span class="sxs-lookup"><span data-stu-id="9d697-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="9d697-117">Kies uit:</span><span class="sxs-lookup"><span data-stu-id="9d697-117">Choose from:</span></span>
    - <span data-ttu-id="9d697-118">**Alle sites**: alle SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9d697-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="9d697-119">Dit geldt ook voor huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="9d697-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="9d697-120">**Alles, met uitzondering van geselecteerde sites**: Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="9d697-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="9d697-121">U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking.</span><span class="sxs-lookup"><span data-stu-id="9d697-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="9d697-122">Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="9d697-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="9d697-123">**Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="9d697-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="9d697-124">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="9d697-124">You can also upload a list of sites.</span></span> <span data-ttu-id="9d697-125">Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="9d697-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="9d697-126">**Geen sites**: geen SharePoint-sites opnemen.</span><span class="sxs-lookup"><span data-stu-id="9d697-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/ksetup1.png) 
   
5. <span data-ttu-id="9d697-128">In de sectie **onderwerpen uitsluiten van naam** kunt u namen van onderwerpen toevoegen die u wilt uitsluiten van het detecteren van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="9d697-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="9d697-129">Met deze instelling kunt u voorkomen dat vertrouwelijke informatie wordt opgenomen in de onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="9d697-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="9d697-130">De opties zijn:</span><span class="sxs-lookup"><span data-stu-id="9d697-130">The options are:</span></span>
    - <span data-ttu-id="9d697-131">**Geen onderwerpen uitsluiten**</span><span class="sxs-lookup"><span data-stu-id="9d697-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="9d697-132">**Onderwerpen uitsluiten op naam**</span><span class="sxs-lookup"><span data-stu-id="9d697-132">**Exclude topics by name**</span></span>

    ![Onderwerpen uitsluiten](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="9d697-134">(Kennis managers kunnen onderwerpen in het onderwerp centrum ook uitsluiten na ontdekking.)</span><span class="sxs-lookup"><span data-stu-id="9d697-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="9d697-135">Onderwerpen uitsluiten op naam</span><span class="sxs-lookup"><span data-stu-id="9d697-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="9d697-136">Als **u onderwerpen moet** uitsluiten, selecteert u de sjabloon. csv downloaden en bijwerken met de lijst met onderwerpen die u wilt uitsluiten van de resultaten van de zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="9d697-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/exclude-topics-csv.png) 

    <span data-ttu-id="9d697-138">Voer de volgende informatie over de onderwerpen die u wilt uitsluiten in het CSV-sjabloon in:</span><span class="sxs-lookup"><span data-stu-id="9d697-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="9d697-139">**Naam**: Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="9d697-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="9d697-140">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="9d697-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="9d697-141">Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.</span><span class="sxs-lookup"><span data-stu-id="9d697-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="9d697-142">Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="9d697-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="9d697-143">Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel*, *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur*, niet worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="9d697-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="9d697-144">**Staat voor (optioneel)**: als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.</span><span class="sxs-lookup"><span data-stu-id="9d697-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="9d697-145">**MatchType-exact/gedeeltelijk**: Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.</span><span class="sxs-lookup"><span data-stu-id="9d697-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="9d697-146">Wanneer u het CSV-bestand hebt voltooid en opgeslagen, selecteert u **Bladeren** om naar het bestand te zoeken en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="9d697-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="9d697-147">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9d697-147">Select **Next**.</span></span>

6. <span data-ttu-id="9d697-148">Als u in de sectie **wie kan de onderwerpen zien en waar kan ze** de pagina zien, wordt de zichtbaarheid van het onderwerp geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="9d697-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="9d697-149">In de instelling **wie kan de onderwerpen zien in de instelling van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, onderwerp Answers in Search en topic Pages.</span><span class="sxs-lookup"><span data-stu-id="9d697-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="9d697-150">U kunt kiezen voor:</span><span class="sxs-lookup"><span data-stu-id="9d697-150">You can select:</span></span>
    - <span data-ttu-id="9d697-151">**Iedereen binnen mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="9d697-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="9d697-152">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="9d697-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="9d697-153">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="9d697-153">**No one**</span></span>

    ![Wie kan onderwerpen zien?](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="9d697-155">Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een onderwerp licenties die aan hen zijn toegewezen, onderwerpen kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="9d697-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="9d697-156">Op de pagina **machtigingen voor onderwerp beheren** kiest u wie onderwerpen kan maken, bewerken en beheren.</span><span class="sxs-lookup"><span data-stu-id="9d697-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="9d697-157">In de sectie **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="9d697-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="9d697-158">**Iedereen binnen mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="9d697-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="9d697-159">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="9d697-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="9d697-160">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="9d697-160">**No one**</span></span>

    ![Machtigingen voor het beheer van onderwerpen, die onderwerpen kunnen maken en bewerken](../media/ksetup3.png) 

8. <span data-ttu-id="9d697-162">In de sectie **wie kan secties beheren** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="9d697-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="9d697-163">**Iedereen binnen mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="9d697-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="9d697-164">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="9d697-164">**Only selected people or security groups**</span></span>

    ![Machtigingen voor onderwerp beheren](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="9d697-166">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9d697-166">Select **Next**.</span></span>

9. <span data-ttu-id="9d697-167">Op de pagina **topic maken** kunt u de site van het onderwerp maken waarin de onderwerpen kunnen worden weergegeven en de onderwerpen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="9d697-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="9d697-168">Typ in het vak **site naam** een naam voor het onderwerp Center.</span><span class="sxs-lookup"><span data-stu-id="9d697-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="9d697-169">U kunt desgewenst een korte beschrijving typen in het vak **Beschrijving** .</span><span class="sxs-lookup"><span data-stu-id="9d697-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="9d697-170">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9d697-170">Select **Next**.</span></span>

   ![Kennis centrum maken](../media/ksetup4.png)  

10. <span data-ttu-id="9d697-172">Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="9d697-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="9d697-173">Selecteer **Activeren** wanneer u tevreden bent met uw selecties.</span><span class="sxs-lookup"><span data-stu-id="9d697-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="9d697-174">De pagina voor **geactiveerde kennis netwerk** wordt weergegeven en u wordt bevestigd dat het systeem nu begint met het analyseren van de geselecteerde sites voor onderwerpen en de site van de Knowledge Center-site maakt.</span><span class="sxs-lookup"><span data-stu-id="9d697-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="9d697-175">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="9d697-175">Select **Done**.</span></span>

12. <span data-ttu-id="9d697-176">U gaat terug naar de pagina contact **personen verbinden met kennis** .</span><span class="sxs-lookup"><span data-stu-id="9d697-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="9d697-177">Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="9d697-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Instellingen toegepast](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="9d697-179">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="9d697-179">Assign licenses</span></span>

<span data-ttu-id="9d697-180">Wanneer u onderwerpen hebt geconfigureerd, moet u een licentie toewijzen voor de gebruikers die gebruikmaken van de functies van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="9d697-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="9d697-181">Alleen gebruikers met een licentie kunnen informatie over onderwerpen, waaronder hooglichten, topic cards, topic pagina's en het onderwerp centrum zien.</span><span class="sxs-lookup"><span data-stu-id="9d697-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="9d697-182">Licenties toewijzen:</span><span class="sxs-lookup"><span data-stu-id="9d697-182">To assign licenses:</span></span>

1. <span data-ttu-id="9d697-183">Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="9d697-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="9d697-184">Selecteer de gebruikers aan wie u een licentie wilt toewijzen en klik op **Productlicenties beheren**.</span><span class="sxs-lookup"><span data-stu-id="9d697-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="9d697-185">Selecteer **Meer toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="9d697-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="9d697-186">Selecteer onder **licenties** de optie **onderwerp**.</span><span class="sxs-lookup"><span data-stu-id="9d697-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="9d697-187">Zorg ervoor dat onder **apps** de optie **Graph-verbindingslijnen zoeken met** de functies index en **onderwerp** zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="9d697-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9d697-188">![SharePoint Syntex-licenties in het Microsoft 365-beheercentrum](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="9d697-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="9d697-189">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9d697-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="9d697-190">Onderwerp ervaring beheren</span><span class="sxs-lookup"><span data-stu-id="9d697-190">Manage topic experiences</span></span>

<span data-ttu-id="9d697-191">Wanneer u de ervaringen met het onderwerp hebt ingesteld, kunt u de instellingen wijzigen die u tijdens de installatie hebt gekozen in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="9d697-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="9d697-192">Zie de volgende verwijzingen:</span><span class="sxs-lookup"><span data-stu-id="9d697-192">See the following references:</span></span>

- [<span data-ttu-id="9d697-193">Detectie van onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d697-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="9d697-194">De zichtbaarheid van een onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d697-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="9d697-195">Machtigingen voor onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d697-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="9d697-196">De naam van het onderwerp centreren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d697-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="9d697-197">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9d697-197">See also</span></span>

[<span data-ttu-id="9d697-198">Overzicht van onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9d697-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
