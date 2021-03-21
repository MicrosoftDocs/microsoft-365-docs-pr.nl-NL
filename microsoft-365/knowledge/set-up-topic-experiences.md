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
description: Meer informatie over het instellen van Microsoft Viva-onderwerpen
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929442"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="0e02e-103">Microsoft Viva-onderwerpen instellen</span><span class="sxs-lookup"><span data-stu-id="0e02e-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="0e02e-104">U kunt het Microsoft 365-beheercentrum gebruiken om Onderwerpen in te stellen en te [configureren.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0e02e-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="0e02e-105">Het is belangrijk om de beste manier te plannen om onderwerpen in uw omgeving in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="0e02e-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="0e02e-106">Lees Plan voor [Microsoft Viva-onderwerpen](plan-topic-experiences.md) voordat u de procedures in dit artikel start.</span><span class="sxs-lookup"><span data-stu-id="0e02e-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="0e02e-107">U moet zijn [geabonneerd](https://www.microsoft.com/microsoft-viva/topics) op Viva Topics en een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-beheercentrum en Onderwerpen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="0e02e-108">Als u SharePoint hebt geconfigureerd voor het vereisen van beheerde [apparaten,](/sharepoint/control-access-from-unmanaged-devices)moet u Onderwerpen instellen vanaf een beheerd apparaat.</span><span class="sxs-lookup"><span data-stu-id="0e02e-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="0e02e-109">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="0e02e-109">Video demonstration</span></span>

<span data-ttu-id="0e02e-110">In deze video ziet u het proces voor het instellen van Onderwerpen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e02e-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="0e02e-111">Onderwerpen instellen</span><span class="sxs-lookup"><span data-stu-id="0e02e-111">Set up Topics</span></span>

<span data-ttu-id="0e02e-112">Onderwerpen instellen</span><span class="sxs-lookup"><span data-stu-id="0e02e-112">To set up Topics</span></span>

1. <span data-ttu-id="0e02e-113">Selecteer setup [in het Microsoft 365-beheercentrum](https://admin.microsoft.com) **en** bekijk vervolgens de sectie **Bestanden en inhoud.**</span><span class="sxs-lookup"><span data-stu-id="0e02e-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="0e02e-114">Klik in **de sectie Bestanden** en inhoud op Personen verbinden met **kennis.**</span><span class="sxs-lookup"><span data-stu-id="0e02e-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Personen verbinden met kennis](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="0e02e-116">Klik op **de pagina Personen verbinden met kennis** op Aan **de** slag om u door het installatieproces te helpen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Aan de slag](../media/k-get-started.png) 

4. <span data-ttu-id="0e02e-118">Op de **pagina Kiezen hoe Viva-onderwerpen onderwerpen kunnen vinden,** configureert u onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0e02e-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="0e02e-119">Selecteer in **de sectie SharePoint-onderwerpbronnen** selecteren welke SharePoint-sites tijdens de detectie worden verkend als bronnen voor uw onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0e02e-120">Kies uit:</span><span class="sxs-lookup"><span data-stu-id="0e02e-120">Choose from:</span></span>
    - <span data-ttu-id="0e02e-121">**Alle sites:** Alle SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0e02e-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="0e02e-122">Dit geldt ook voor huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="0e02e-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="0e02e-123">**Alle, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0e02e-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0e02e-124">U kunt ook een lijst uploaden met sites die u niet wilt ontdekken.</span><span class="sxs-lookup"><span data-stu-id="0e02e-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="0e02e-125">Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0e02e-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="0e02e-126">**Alleen geselecteerde sites:** Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0e02e-127">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="0e02e-127">You can also upload a list of sites.</span></span> <span data-ttu-id="0e02e-128">Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0e02e-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="0e02e-129">**Geen sites:** Neem geen SharePoint-sites op.</span><span class="sxs-lookup"><span data-stu-id="0e02e-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/ksetup1.png) 
   
5. <span data-ttu-id="0e02e-131">In de **sectie Onderwerpen uitsluiten op naam** kunt u namen toevoegen van onderwerpen die u wilt uitsluiten van onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="0e02e-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="0e02e-132">Gebruik deze instelling om te voorkomen dat gevoelige informatie als onderwerpen wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="0e02e-133">De opties zijn:</span><span class="sxs-lookup"><span data-stu-id="0e02e-133">The options are:</span></span>
    - <span data-ttu-id="0e02e-134">**Sluit geen onderwerpen uit**</span><span class="sxs-lookup"><span data-stu-id="0e02e-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="0e02e-135">**Onderwerpen uitsluiten op naam**</span><span class="sxs-lookup"><span data-stu-id="0e02e-135">**Exclude topics by name**</span></span>

    ![Onderwerpen uitsluiten](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="0e02e-137">(Kennisbeheerders kunnen ook onderwerpen in het onderwerpcentrum uitsluiten na ontdekking.)</span><span class="sxs-lookup"><span data-stu-id="0e02e-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="0e02e-138">Onderwerpen uitsluiten op naam</span><span class="sxs-lookup"><span data-stu-id="0e02e-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="0e02e-139">Als u onderwerpen wilt uitsluiten nadat u Onderwerpen op naam uitsluiten hebt **geselecteerd,** downloadt u de CSV-sjabloon en updatet u deze met de lijst met onderwerpen die u wilt uitsluiten van de detectieresultaten.</span><span class="sxs-lookup"><span data-stu-id="0e02e-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

    <span data-ttu-id="0e02e-141">Voer in de CSV-sjabloon de volgende informatie in over de onderwerpen die u wilt uitsluiten:</span><span class="sxs-lookup"><span data-stu-id="0e02e-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="0e02e-142">**Naam:** Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0e02e-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0e02e-143">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="0e02e-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="0e02e-144">Exacte overeenkomst: U kunt de exacte naam of het acroniem (bijvoorbeeld *Contoso* of *ATL) opnemen.*</span><span class="sxs-lookup"><span data-stu-id="0e02e-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="0e02e-145">Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="0e02e-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0e02e-146">Met een *boog worden bijvoorbeeld* alle onderwerpen uitgesloten met de woordboog in de boog, zoals boogcirkel, lassen van de boog van Het *plasma* of *Trainingsboog.*   Houd er rekening mee dat onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, niet worden *uitgesloten.*</span><span class="sxs-lookup"><span data-stu-id="0e02e-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="0e02e-147">**Staat voor (optioneel)**: Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.</span><span class="sxs-lookup"><span data-stu-id="0e02e-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="0e02e-148">**MatchType-Exact/Gedeeltelijk:** Typ of de opgegeven naam *een exact* of *gedeeltelijk overeenkomend* type was.</span><span class="sxs-lookup"><span data-stu-id="0e02e-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="0e02e-149">Nadat u het CSV-bestand hebt voltooid en opgeslagen, **selecteert** u Bladeren om het te zoeken en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0e02e-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="0e02e-150">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0e02e-150">Select **Next**.</span></span>

6. <span data-ttu-id="0e02e-151">Op de **pagina Wie kan onderwerpen zien en waar kunnen** ze deze zien, configureert u de zichtbaarheid van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="0e02e-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="0e02e-152">In de **instelling Wie kan onderwerpen** zien, kiest u wie toegang heeft tot onderwerpdetails, zoals gemarkeerde onderwerpen, onderwerpkaarten, onderwerp antwoorden in zoekopdrachten en onderwerppagina's.</span><span class="sxs-lookup"><span data-stu-id="0e02e-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="0e02e-153">U kunt het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="0e02e-153">You can select:</span></span>
    - <span data-ttu-id="0e02e-154">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="0e02e-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="0e02e-155">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="0e02e-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="0e02e-156">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="0e02e-156">**No one**</span></span>

    ![Wie kan onderwerpen zien](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="0e02e-158">Hoewel u met deze instelling elke gebruiker in uw organisatie kunt selecteren, kunnen alleen gebruikers met licenties voor onderwerpervaringen onderwerpen bekijken.</span><span class="sxs-lookup"><span data-stu-id="0e02e-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="0e02e-159">Op de **pagina Machtigingen voor onderwerpbeheer** kiest u wie onderwerpen kan maken, bewerken of beheren.</span><span class="sxs-lookup"><span data-stu-id="0e02e-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="0e02e-160">In de **sectie Wie kan onderwerpen maken en bewerken,** kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="0e02e-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="0e02e-161">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="0e02e-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="0e02e-162">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="0e02e-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="0e02e-163">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="0e02e-163">**No one**</span></span>

    ![Machtigingen voor onderwerpbeheer, die onderwerpen kunnen maken en bewerken](../media/ksetup3.png) 

8. <span data-ttu-id="0e02e-165">In de **sectie Wie kan onderwerpen beheren,** kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="0e02e-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="0e02e-166">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="0e02e-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="0e02e-167">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="0e02e-167">**Only selected people or security groups**</span></span>

    ![Machtigingen voor onderwerpbeheer](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="0e02e-169">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0e02e-169">Select **Next**.</span></span>

9. <span data-ttu-id="0e02e-170">Op de **pagina Onderwerpcentrum** maken kunt u uw onderwerpcentrumsite maken waarin onderwerppagina's kunnen worden bekeken en onderwerpen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="0e02e-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="0e02e-171">Typ in **het vak** Sitenaam een naam voor het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="0e02e-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="0e02e-172">U kunt desgewenst een korte beschrijving typen in **het vak** Beschrijving.</span><span class="sxs-lookup"><span data-stu-id="0e02e-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="0e02e-173">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0e02e-173">Select **Next**.</span></span>

   ![Kenniscentrum maken](../media/ksetup4.png)  

10. <span data-ttu-id="0e02e-175">Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="0e02e-176">Selecteer **Activeren** wanneer u tevreden bent met uw selecties.</span><span class="sxs-lookup"><span data-stu-id="0e02e-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="0e02e-177">De **geactiveerde pagina Viva-onderwerpen** wordt weergegeven, om te bevestigen dat het systeem nu begint met het analyseren van de geselecteerde sites voor onderwerpen en het maken van de site van het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="0e02e-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="0e02e-178">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0e02e-178">Select **Done**.</span></span>

12. <span data-ttu-id="0e02e-179">U wordt teruggegeven aan de pagina **Personen verbinden met kennis.**</span><span class="sxs-lookup"><span data-stu-id="0e02e-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="0e02e-180">Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="0e02e-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Toegepaste instellingen](../media/ksetup7.png)    

<span data-ttu-id="0e02e-182">De eerste keer dat onderwerpdetectie is ingeschakeld, kan het maximaal twee weken duren voordat alle voorgestelde onderwerpen worden weergegeven in de weergave Onderwerpen beheren.</span><span class="sxs-lookup"><span data-stu-id="0e02e-182">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="0e02e-183">Onderwerpdetectie wordt voortgezet wanneer er nieuwe inhoud of updates voor inhoud worden aangebracht.</span><span class="sxs-lookup"><span data-stu-id="0e02e-183">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="0e02e-184">Het is normaal dat er fluctuaties zijn in het aantal voorgestelde onderwerpen in uw organisatie, aangezien Viva Topics nieuwe informatie evalueert.</span><span class="sxs-lookup"><span data-stu-id="0e02e-184">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="0e02e-185">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="0e02e-185">Assign licenses</span></span>

<span data-ttu-id="0e02e-186">Nadat u de onderwerpervaringen hebt geconfigureerd, moet u licenties toewijzen aan de gebruikers die Onderwerpen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0e02e-186">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="0e02e-187">Alleen gebruikers met een licentie kunnen informatie zien over onderwerpen zoals highlights, onderwerpkaarten, onderwerppagina's en het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="0e02e-187">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="0e02e-188">Licenties toewijzen:</span><span class="sxs-lookup"><span data-stu-id="0e02e-188">To assign licenses:</span></span>

1. <span data-ttu-id="0e02e-189">Klik in het Microsoft 365-beheercentrum onder **Gebruikers** op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="0e02e-189">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="0e02e-190">Selecteer de gebruikers die u een licentie wilt geven en klik op **Licenties en apps.**</span><span class="sxs-lookup"><span data-stu-id="0e02e-190">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="0e02e-191">Selecteer **onder Licenties** de optie **Viva-onderwerpen.**</span><span class="sxs-lookup"><span data-stu-id="0e02e-191">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="0e02e-192">Zorg **er onder Apps** voor dat Graph **Connectors Search with Index (Viva Topics)** en **Viva Topics** beide zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="0e02e-192">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0e02e-193">![Microsoft Viva Topics-licenties in het Microsoft 365-beheercentrum](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="0e02e-193">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="0e02e-194">Klik op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0e02e-194">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="0e02e-195">Onderwerpervaringen beheren</span><span class="sxs-lookup"><span data-stu-id="0e02e-195">Manage topic experiences</span></span>

<span data-ttu-id="0e02e-196">Nadat u Onderwerpen hebt ingesteld, kunt u de instellingen wijzigen die u hebt gekozen tijdens de installatie in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="0e02e-196">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="0e02e-197">Zie de volgende referenties:</span><span class="sxs-lookup"><span data-stu-id="0e02e-197">See the following references:</span></span>

- [<span data-ttu-id="0e02e-198">Onderwerpdetectie beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0e02e-198">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="0e02e-199">Zichtbaarheid van onderwerpen beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0e02e-199">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="0e02e-200">Onderwerpmachtigingen beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0e02e-200">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="0e02e-201">De naam van het onderwerpcentrum wijzigen in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0e02e-201">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="0e02e-202">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0e02e-202">See also</span></span>

[<span data-ttu-id="0e02e-203">Overzicht van onderwerpervaringen</span><span class="sxs-lookup"><span data-stu-id="0e02e-203">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
