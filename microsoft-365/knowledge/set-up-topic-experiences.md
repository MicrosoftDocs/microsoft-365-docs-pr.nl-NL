---
title: Microsoft Viva-onderwerpen instellen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informatie over het instellen van Microsoft Viva-onderwerpen
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150498"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="f551f-103">Microsoft Viva-onderwerpen instellen</span><span class="sxs-lookup"><span data-stu-id="f551f-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="f551f-104">U kunt het Microsoft 365-beheercentrum gebruiken om Onderwerpen in te stellen en te [configureren.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f551f-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="f551f-105">Het is belangrijk om de beste manier te plannen voor het instellen en configureren van onderwerpen in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="f551f-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="f551f-106">Lees de Onderwerpen over [Microsoft Viva voordat](plan-topic-experiences.md) u aan de procedures in dit artikel begint.</span><span class="sxs-lookup"><span data-stu-id="f551f-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="f551f-107">U moet zijn [geabonneerd op Viva-onderwerpen](https://www.microsoft.com/microsoft-viva/topics) en een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-beheercentrum en Onderwerpen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f551f-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="f551f-108">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="f551f-108">Video demonstration</span></span>

<span data-ttu-id="f551f-109">In deze video ziet u het proces voor het instellen van Onderwerpen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f551f-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="f551f-110">Onderwerpen instellen</span><span class="sxs-lookup"><span data-stu-id="f551f-110">Set up Topics</span></span>

<span data-ttu-id="f551f-111">Onderwerpen instellen</span><span class="sxs-lookup"><span data-stu-id="f551f-111">To set up Topics</span></span>

1. <span data-ttu-id="f551f-112">Selecteer Setup [in het Microsoft 365-beheercentrum](https://admin.microsoft.com) **en** bekijk de sectie **Bestanden en** inhoud.</span><span class="sxs-lookup"><span data-stu-id="f551f-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="f551f-113">Klik in **de sectie Bestanden en** inhoud op Personen verbinden met **kennis.**</span><span class="sxs-lookup"><span data-stu-id="f551f-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Personen verbinden met kennis](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="f551f-115">Klik op **de pagina Personen** verbinden met kennis op **Aan** de slag om u bij het installatieproces te helpen.</span><span class="sxs-lookup"><span data-stu-id="f551f-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Aan de slag](../media/k-get-started.png) 

4. <span data-ttu-id="f551f-117">Op de **pagina Kiezen hoe Viva-onderwerpen onderwerpen kunnen vinden,** configureert u onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="f551f-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="f551f-118">Selecteer in **de sectie SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie worden verkend als bronnen voor uw onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f551f-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="f551f-119">Kies uit:</span><span class="sxs-lookup"><span data-stu-id="f551f-119">Choose from:</span></span>
    - <span data-ttu-id="f551f-120">**Alle sites:** alle SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f551f-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="f551f-121">Dit geldt ook voor huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="f551f-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="f551f-122">**Alle, behalve geselecteerde sites:** typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="f551f-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="f551f-123">U kunt ook een lijst met sites uploaden die u niet wilt ontdekken.</span><span class="sxs-lookup"><span data-stu-id="f551f-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="f551f-124">Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="f551f-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="f551f-125">**Alleen geselecteerde sites:** typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="f551f-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="f551f-126">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="f551f-126">You can also upload a list of sites.</span></span> <span data-ttu-id="f551f-127">Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="f551f-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="f551f-128">**Geen sites:** Geen SharePoint-sites opnemen.</span><span class="sxs-lookup"><span data-stu-id="f551f-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Kiezen hoe u onderwerpen wilt zoeken](../media/ksetup1.png) 
   
5. <span data-ttu-id="f551f-130">In de **sectie Onderwerpen uitsluiten op** naam kunt u namen toevoegen van onderwerpen die u wilt uitsluiten van onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="f551f-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="f551f-131">Gebruik deze instelling om te voorkomen dat gevoelige informatie wordt opgenomen als onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f551f-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="f551f-132">De volgende opties zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="f551f-132">The options are:</span></span>
    - <span data-ttu-id="f551f-133">**Onderwerpen niet uitsluiten**</span><span class="sxs-lookup"><span data-stu-id="f551f-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="f551f-134">**Onderwerpen uitsluiten op naam**</span><span class="sxs-lookup"><span data-stu-id="f551f-134">**Exclude topics by name**</span></span>

    ![Onderwerpen uitsluiten](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="f551f-136">(Knowledge Managers kunnen na detectie ook onderwerpen uitsluiten in het onderwerpcentrum.)</span><span class="sxs-lookup"><span data-stu-id="f551f-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="f551f-137">Onderwerpen uitsluiten op naam</span><span class="sxs-lookup"><span data-stu-id="f551f-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="f551f-138">Als u onderwerpen wilt uitsluiten, selecteert u Onderwerpen uitsluiten op **naam,** downloadt u de CSV-sjabloon en werk u deze bij met de lijst met onderwerpen die u wilt uitsluiten van uw discovery-resultaten.</span><span class="sxs-lookup"><span data-stu-id="f551f-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

    <span data-ttu-id="f551f-140">Voer in de CSV-sjabloon de volgende informatie in over de onderwerpen die u wilt uitsluiten:</span><span class="sxs-lookup"><span data-stu-id="f551f-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="f551f-141">**Naam:** typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="f551f-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="f551f-142">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="f551f-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="f551f-143">Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen (bijvoorbeeld *Contoso* of *ATL).*</span><span class="sxs-lookup"><span data-stu-id="f551f-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="f551f-144">Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een bepaald woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="f551f-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="f551f-145">Met een *boog worden bijvoorbeeld* alle onderwerpen met de woordbogen uitgesloten, zoals Boogcirkel, *Arc-boog* of *Trainingsbogen.*   Onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, worden niet *uitgesloten.*</span><span class="sxs-lookup"><span data-stu-id="f551f-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="f551f-146">**Staat voor (optioneel:** als u een acroniem wilt uitsluiten, typt u de woorden voor het acroniem).</span><span class="sxs-lookup"><span data-stu-id="f551f-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="f551f-147">**MatchType-Exact/Gedeeltelijk:** typ of de naam die u hebt ingevoerd *een exact* of *gedeeltelijk* overeenkomsttype is.</span><span class="sxs-lookup"><span data-stu-id="f551f-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="f551f-148">Nadat u het CSV-bestand hebt voltooid en opgeslagen, selecteert u **Bladeren** om het te zoeken en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f551f-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="f551f-149">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f551f-149">Select **Next**.</span></span>

6. <span data-ttu-id="f551f-150">Op de **pagina Wie kan onderwerpen zien en waar** zij deze kunnen zien, configureert u de zichtbaarheid van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="f551f-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="f551f-151">In de **instelling Wie kan de** onderwerpen bekijken, kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, antwoorden op onderwerp in zoekopdrachten en onderwerppagina's.</span><span class="sxs-lookup"><span data-stu-id="f551f-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="f551f-152">U kunt het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="f551f-152">You can select:</span></span>
    - <span data-ttu-id="f551f-153">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="f551f-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="f551f-154">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f551f-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="f551f-155">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="f551f-155">**No one**</span></span>

    ![Wie kan onderwerpen zien?](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="f551f-157">Hoewel u met deze instelling elke gebruiker in uw organisatie kunt selecteren, kunnen alleen gebruikers aan wie een licentie voor onderwerpervaringen is toegewezen onderwerpen bekijken.</span><span class="sxs-lookup"><span data-stu-id="f551f-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="f551f-158">Op de **pagina Machtigingen voor** onderwerpbeheer kiest u wie onderwerpen mag maken, bewerken of beheren.</span><span class="sxs-lookup"><span data-stu-id="f551f-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="f551f-159">In de **sectie Wie kan onderwerpen maken en bewerken,** kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="f551f-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="f551f-160">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="f551f-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="f551f-161">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f551f-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="f551f-162">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="f551f-162">**No one**</span></span>

    ![Machtigingen voor onderwerpbeheer, wie onderwerpen kan maken en bewerken](../media/ksetup3.png) 

8. <span data-ttu-id="f551f-164">In de **sectie Wie kan onderwerpen beheren,** kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="f551f-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="f551f-165">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="f551f-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="f551f-166">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f551f-166">**Only selected people or security groups**</span></span>

    ![Machtigingen voor onderwerpbeheer](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="f551f-168">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f551f-168">Select **Next**.</span></span>

9. <span data-ttu-id="f551f-169">Op de **pagina Onderwerpcentrum** maken kunt u uw onderwerpcentrumsite maken waarin onderwerppagina's kunnen worden bekeken en onderwerpen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="f551f-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="f551f-170">Typ in **het vak Sitenaam** een naam voor het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="f551f-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="f551f-171">U kunt desgewenst een korte beschrijving typen in het **vak** Beschrijving.</span><span class="sxs-lookup"><span data-stu-id="f551f-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="f551f-172">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f551f-172">Select **Next**.</span></span>

   ![Knowledge Center maken](../media/ksetup4.png)  

10. <span data-ttu-id="f551f-174">Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="f551f-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="f551f-175">Selecteer **Activeren** wanneer u tevreden bent met uw selecties.</span><span class="sxs-lookup"><span data-stu-id="f551f-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="f551f-176">De **pagina die is** geactiveerd voor Viva-onderwerpen wordt weergegeven, en bevestigt dat het systeem nu de geselecteerde sites gaat analyseren voor onderwerpen en de onderwerpcentrumsite gaat maken.</span><span class="sxs-lookup"><span data-stu-id="f551f-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="f551f-177">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f551f-177">Select **Done**.</span></span>

12. <span data-ttu-id="f551f-178">U keert terug naar de **pagina Personen verbinden met kennis.**</span><span class="sxs-lookup"><span data-stu-id="f551f-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="f551f-179">Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="f551f-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Instellingen toegepast](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="f551f-181">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="f551f-181">Assign licenses</span></span>

<span data-ttu-id="f551f-182">Nadat u onderwerpervaringen hebt geconfigureerd, moet u licenties toewijzen voor de gebruikers die Onderwerpen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f551f-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="f551f-183">Alleen gebruikers met een licentie kunnen informatie zien over onderwerpen zoals highlights, onderwerpkaarten, onderwerppagina's en het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="f551f-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="f551f-184">Licenties toewijzen:</span><span class="sxs-lookup"><span data-stu-id="f551f-184">To assign licenses:</span></span>

1. <span data-ttu-id="f551f-185">Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="f551f-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="f551f-186">Selecteer de gebruikers die u een licentie wilt geven en klik op **Licenties en apps.**</span><span class="sxs-lookup"><span data-stu-id="f551f-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="f551f-187">Zorg **ervoor** dat **Graph Connectors Zoeken met Index** en **Onderwerpervaringen** zijn geselecteerd onder Apps.</span><span class="sxs-lookup"><span data-stu-id="f551f-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="f551f-188">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f551f-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="f551f-189">Onderwerpervaringen beheren</span><span class="sxs-lookup"><span data-stu-id="f551f-189">Manage topic experiences</span></span>

<span data-ttu-id="f551f-190">Nadat u Onderwerpen hebt ingesteld, kunt u de instellingen wijzigen die u tijdens de installatie hebt gekozen in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="f551f-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="f551f-191">Zie de volgende verwijzingen:</span><span class="sxs-lookup"><span data-stu-id="f551f-191">See the following references:</span></span>

- [<span data-ttu-id="f551f-192">Onderwerpdetectie beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f551f-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="f551f-193">Zichtbaarheid van onderwerpen beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f551f-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="f551f-194">Onderwerpmachtigingen beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f551f-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="f551f-195">De naam van het onderwerpcentrum wijzigen in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f551f-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="f551f-196">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f551f-196">See also</span></span>

[<span data-ttu-id="f551f-197">Overzicht van onderwerpervaringen</span><span class="sxs-lookup"><span data-stu-id="f551f-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
