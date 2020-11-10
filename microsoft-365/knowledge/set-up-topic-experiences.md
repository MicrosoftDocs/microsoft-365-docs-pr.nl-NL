---
title: 'Kennisbeheer instellen (preview) '
description: Het instellen van kennisbeheer.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988943"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="a5aa6-103">Kennisbeheer instellen (preview)</span><span class="sxs-lookup"><span data-stu-id="a5aa6-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="a5aa6-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="a5aa6-105">[Meer informatie over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="a5aa6-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="a5aa6-106">Met het Microsoft 365-Beheercentrum kunt u [kennisbeheer](knowledge-management-overview.md)instellen en configureren.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="a5aa6-107">Het is belangrijk dat u de beste manier voor het instellen van kennisbeheer in uw omgeving de beste manier plant en configureert.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="a5aa6-108">U moet bijvoorbeeld overwegingen voor het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="a5aa6-109">De SharePoint-sites die u voor onderwerpen wilt analyseren.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="a5aa6-110">De gebruikers van wie u de onderwerpen zichtbaar wilt maken.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="a5aa6-111">Welke gebruikers u machtigingen wilt geven om onderwerpen te beheren in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="a5aa6-112">Welke gebruikers u machtigingen wilt geven om onderwerpen te maken of te bewerken in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="a5aa6-113">De naam van het onderwerp dat u wilt geven.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="a5aa6-114">Het kan handig zijn om beveiligingsgroepen te maken om uw gebruikers de benodigde machtigingen voor het weergeven van onderwerpen te zien, onderwerp te beheren en onderwerpen te maken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="a5aa6-115">Een beheerder kan ook [op elk gewenst moment na de installatie wijzigingen aanbrengen](topic-experiences-discovery.md) in de instellingen voorkennis beheer in het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="a5aa6-116">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a5aa6-116">Requirements</span></span> 
<span data-ttu-id="a5aa6-117">U moet een globale beheerder of SharePoint-beheerdersmachtigingen hebben om toegang te krijgen tot het Microsoft 365-Beheercentrum en om bedrijfsinformatie in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="a5aa6-118">Uw kennis netwerk instellen</span><span class="sxs-lookup"><span data-stu-id="a5aa6-118">Set up your knowledge network</span></span>

<span data-ttu-id="a5aa6-119">Het instellen van uw kennis netwerk begeleidt u door het volgende:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="a5aa6-120">Onderwerp detecteren: het selecteren van onderwerpen bronnen en onderwerpen voor het opzeggen van detectie.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="a5aa6-121">Onderwerp zichtbaar: wanneer u een gebruiker selecteert, kunt u deze onderwerpen als aandachtspunten weergeven op de tabbladen zoeken en onderwerp.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="a5aa6-122">Onderwerp machtigingen: selecteren wie onderwerpen kan maken, bewerken en beheren.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="a5aa6-123">Onderwerpen centrum: het onderwerpen centrum maken.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="a5aa6-124">Controleren: de instellingen controleren en toepassen.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="a5aa6-125">Uw kennis netwerk instellen:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="a5aa6-126">In het Microsoft 365-Beheercentrum (admin.microsoft.com), selecteert u **instellingen** en vervolgens de afdelings informatie van de **organisatie** weergeven.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="a5aa6-127">Klik in de sectie **kennis van organisatie** op **personen verbinden met kennis**.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Mensen verbinden met kennis](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="a5aa6-129">Klik op de pagina **personen verbinden met kennis** op aan de slag om u door te **gaan** met het instellen van het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Aan de slag](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="a5aa6-131">Ga naar de pagina **Kies hoe u de pagina wilt zoeken** in het onderwerp: detectie van een kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="a5aa6-132">Selecteer in de sectie **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="a5aa6-133">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-133">This includes:</span></span></br>
    <span data-ttu-id="a5aa6-134">a.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-134">a.</span></span> <span data-ttu-id="a5aa6-135">**Alle sites** : alle SharePoint-sites in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="a5aa6-136">Hiermee worden de huidige en toekomstige sites vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="a5aa6-137">b.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-137">b.</span></span> <span data-ttu-id="a5aa6-138">**Alles, met uitzondering van geselecteerde sites** : Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="a5aa6-139">U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="a5aa6-140">Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="a5aa6-141">c.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-141">c.</span></span> <span data-ttu-id="a5aa6-142">**Alleen geselecteerde sites** : Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="a5aa6-143">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-143">You can also upload a list of sites.</span></span> <span data-ttu-id="a5aa6-144">Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Kiezen hoe u onderwerpen kunt zoeken](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="a5aa6-146">In de sectie **onderwerpen uitsluiten van naam** kunt u kiezen of u namen wilt opnemen van onderwerpen die u niet wilt opnemen in de gedetecteerde resultaten.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="a5aa6-147">Gebruik deze instelling om te voorkomen dat vertrouwelijke onderwerpen worden opgenomen als onderdeel van het kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="a5aa6-148">De opties zijn:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-148">Your options include:</span></span></br>
    <span data-ttu-id="a5aa6-149">a.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-149">a.</span></span> <span data-ttu-id="a5aa6-150">**Geen onderwerpen uitsluiten**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="a5aa6-151">b.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-151">b.</span></span> <span data-ttu-id="a5aa6-152">**Onderwerpen uitsluiten op naam** : als u onderwerpen hebt die u niet wilt weergeven aan gebruikers als onderdeel van het kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Onderwerpen uitsluiten](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="a5aa6-154">Onderwerpen uitsluiten op naam</span><span class="sxs-lookup"><span data-stu-id="a5aa6-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="a5aa6-155">Als u onderwerpen wilt uitsluiten, selecteert u **de sjabloon. csv downloaden** als u **onderwerpen uitsluiten op naam** selecteert.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="a5aa6-156">Gebruik Excel. CSV-sjabloon voor een lijst met onderwerpen die u niet wilt opnemen in de resultaten van detectie.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="a5aa6-158">Voer de volgende informatie over de onderwerpen die u wilt uitsluiten in het CSV-sjabloon in:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="a5aa6-159">**Naam** : Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="a5aa6-160">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="a5aa6-161">Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="a5aa6-162">Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="a5aa6-163">Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel* , *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur* , niet worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="a5aa6-164">**Expansie (optioneel)** : als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="a5aa6-165">**MatchType-exact/gedeeltelijk** : Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="a5aa6-166">Wanneer u het CSV-sjabloonbestand hebt voltooid en opgeslagen, selecteert u **Bladeren** om naar het bestand te zoeken en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="a5aa6-167">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="a5aa6-168">In de pagina **wie kan de onderwerpen zien en waar ze deze kunnen zien** , wordt de zichtbaarheid van het onderwerp geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="a5aa6-169">In de instelling **wie kan de onderwerpen zien in de instelling van het kennis netwerk** , kiest u wie toegang heeft tot de details van het onderwerp, zoals gemarkeerde onderwerpen, topic cards, onderwerp Answers in Search en topic Pages.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="a5aa6-170">U kunt kiezen voor:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-170">You can select:</span></span></br>
    <span data-ttu-id="a5aa6-171">a.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-171">a.</span></span> <span data-ttu-id="a5aa6-172">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a5aa6-173">b.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-173">b.</span></span> <span data-ttu-id="a5aa6-174">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="a5aa6-175">c.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-175">c.</span></span> <span data-ttu-id="a5aa6-176">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-176">**No one**</span></span></br>

    ![Wie kan onderwerpen zien?](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="a5aa6-178">Met deze instelling kunt u een gebruiker in de organisatie selecteren, zodat alleen gebruikers met een licentie voorkennis beheer die aan hen zijn toegewezen, onderwerpen kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="a5aa6-179">Op de pagina **machtigingen voor onderwerp beheren** kiest u wie onderwerpen kan maken, bewerken en beheren.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="a5aa6-180">In de sectie **wie kan onderwerpen maken en bewerken** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="a5aa6-181">a.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-181">a.</span></span> <span data-ttu-id="a5aa6-182">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a5aa6-183">b.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-183">b.</span></span> <span data-ttu-id="a5aa6-184">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="a5aa6-185">In de sectie **wie kan secties beheren** , kunt u het volgende selecteren:</span><span class="sxs-lookup"><span data-stu-id="a5aa6-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="a5aa6-186">a.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-186">a.</span></span> <span data-ttu-id="a5aa6-187">**Iedereen in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="a5aa6-188">b.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-188">b.</span></span> <span data-ttu-id="a5aa6-189">**Geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="a5aa6-189">**Selected people or security groups**</span></span></br>

    ![Machtigingen voor onderwerp beheren](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="a5aa6-191">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="a5aa6-192">Op de pagina **topic maken** kunt u de site van het onderwerp maken waarin de onderwerpen kunnen worden weergegeven en de onderwerpen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="a5aa6-193">Typ in het vak **naam van onderwerp centrum** een naam voor het onderwerp Center.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="a5aa6-194">U kunt desgewenst een korte beschrijving typen in het vak **Beschrijving van site** .</span><span class="sxs-lookup"><span data-stu-id="a5aa6-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="a5aa6-195">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-195">Select **Next**.</span></span></br>

   ![Kennis centrum maken](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="a5aa6-197">Op de pagina **Controleren en voltooien** kunt u de geselecteerde instelling bekijken en wijzigingen aanbrengen.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="a5aa6-198">Selecteer **Activeren** wanneer u tevreden bent met uw selecties.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Voltooien en controleren](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="a5aa6-200">De pagina voor **geactiveerde kennis netwerk** wordt weergegeven en u wordt bevestigd dat het systeem nu begint met het analyseren van de geselecteerde sites voor onderwerpen en de site van de Knowledge Center-site maakt.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="a5aa6-201">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-201">Select **Done**.</span></span></br>

    ![Gestart](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="a5aa6-203">U gaat terug naar de pagina contact **personen verbinden met kennis** .</span><span class="sxs-lookup"><span data-stu-id="a5aa6-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="a5aa6-204">Op deze pagina kunt u **Beheren** selecteren om wijzigingen aan te brengen in de configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Instellingen toegepast](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="a5aa6-206">Na de installatie kan een beheerder op elk moment [wijzigingen aanbrengen in uw geselecteerde instellingen voorkennis beheer](topic-experiences-discovery.md) , door terug te gaan naar deze pagina.</span><span class="sxs-lookup"><span data-stu-id="a5aa6-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="a5aa6-207">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a5aa6-207">See also</span></span>



  






