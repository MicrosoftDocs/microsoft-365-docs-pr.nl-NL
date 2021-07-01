---
title: Microsoft Viva-onderwerpen plannen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Meer informatie over het plannen van microsoft Viva-onderwerpen
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229537"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="f4603-103">Microsoft Viva-onderwerpen plannen</span><span class="sxs-lookup"><span data-stu-id="f4603-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="f4603-104">U hebt de controle over de manier waarop onderwerpen worden ervaren in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4603-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="f4603-105">Uw planningsbeslissingen voor Onderwerpen zorgen ervoor dat onderwerpen van hoge kwaliteit worden weergegeven aan uw gebruikers en dat ze de juiste machtigingen hebben om kennis te gebruiken en bij te dragen.</span><span class="sxs-lookup"><span data-stu-id="f4603-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="f4603-106">In dit artikel gaan we in op de volgende planningsbeslissingen:</span><span class="sxs-lookup"><span data-stu-id="f4603-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="f4603-107">Welke SharePoint sites die u wilt crawlen naar onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f4603-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="f4603-108">Welke onderwerpen u wilt uitsluiten van onderwerpervaringen</span><span class="sxs-lookup"><span data-stu-id="f4603-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="f4603-109">Voor welke gebruikers u onderwerpen zichtbaar wilt maken</span><span class="sxs-lookup"><span data-stu-id="f4603-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="f4603-110">Welke gebruikers u machtigingen wilt geven voor het beheren van onderwerpen in het onderwerpcentrum</span><span class="sxs-lookup"><span data-stu-id="f4603-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="f4603-111">Welke gebruikers u machtigingen wilt geven voor het maken of bewerken van onderwerpen in het onderwerpcentrum</span><span class="sxs-lookup"><span data-stu-id="f4603-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="f4603-112">Welke naam u wilt geven aan uw onderwerpcentrum</span><span class="sxs-lookup"><span data-stu-id="f4603-112">What name you want to give your topic center</span></span>

<span data-ttu-id="f4603-113">De beveiliging en privacy van uw gegevens wordt gerespecteerd en door onderwerpervaringen krijgen gebruikers geen extra toegang tot bestanden waar ze geen rechten op hebben.</span><span class="sxs-lookup"><span data-stu-id="f4603-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="f4603-114">We raden u aan microsoft Viva Topics beveiliging [en privacy](topic-experiences-security-privacy.md) ook te lezen als onderdeel van uw planningsproces.</span><span class="sxs-lookup"><span data-stu-id="f4603-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="f4603-115">Lees Alexandria in Microsoft Viva Topics voor meer informatie over de AI-technologie achter [Viva-onderwerpen: van big data tot grote kennis.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)</span><span class="sxs-lookup"><span data-stu-id="f4603-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="f4603-116">Vereisten</span><span class="sxs-lookup"><span data-stu-id="f4603-116">Requirements</span></span>

<span data-ttu-id="f4603-117">U moet zijn [geabonneerd op Viva-onderwerpen](https://www.microsoft.com/microsoft-viva/topics) en een globale beheerder of SharePoint beheerder zijn om toegang te krijgen tot de Microsoft 365-beheercentrum en Onderwerpen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f4603-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="f4603-118">Alle gebruikers die Onderwerpen gaan gebruiken, hebben een **licentie Onderwerpervaringen** nodig.</span><span class="sxs-lookup"><span data-stu-id="f4603-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="f4603-119">Het toewijzen van licenties valt onder [Microsoft Viva-onderwerpen instellen.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="f4603-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="f4603-120">Onderwerpdetectie</span><span class="sxs-lookup"><span data-stu-id="f4603-120">Topic discovery</span></span>

<span data-ttu-id="f4603-121">De instellingen voor onderwerpdetectie geven aan SharePoint sites worden gebruikt als bronnen voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f4603-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="f4603-122">Dit omvat zowel klassieke als moderne sites, evenals sites die zijn gekoppeld aan Microsoft Teams en Microsoft 365 Groepen.</span><span class="sxs-lookup"><span data-stu-id="f4603-122">This includes both classic and modern sites, as well as sites associated with Microsoft Teams and Microsoft 365 Groups.</span></span> <span data-ttu-id="f4603-123">OneDrive sites zijn niet inbegrepen.</span><span class="sxs-lookup"><span data-stu-id="f4603-123">OneDrive sites are not included.</span></span>

<span data-ttu-id="f4603-124">U kunt ervoor kiezen om alle SharePoint sites, een specifieke lijst met sites of geen sites op te nemen.</span><span class="sxs-lookup"><span data-stu-id="f4603-124">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="f4603-125">U wordt aangeraden alle sites te kiezen, zodat u met onderwerpervaringen een groot aantal goede onderwerpen voor uw gebruikers kunt ontdekken.</span><span class="sxs-lookup"><span data-stu-id="f4603-125">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="f4603-126">Wanneer u Onderwerpen in stelt, kunt u kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="f4603-126">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="f4603-127">**Alle sites:** Alle SharePoint sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4603-127">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="f4603-128">Dit geldt ook voor huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="f4603-128">This includes current and future sites.</span></span>
- <span data-ttu-id="f4603-129">**Alle, behalve geselecteerde sites:** Alle sites, behalve de sites die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="f4603-129">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="f4603-130">Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="f4603-130">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="f4603-131">**Alleen geselecteerde sites:** Alleen de sites die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="f4603-131">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="f4603-132">Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="f4603-132">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="f4603-133">**Geen sites:** neem geen sites SharePoint op.</span><span class="sxs-lookup"><span data-stu-id="f4603-133">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="f4603-134">Als u Alle **kiest, behalve geselecteerde sites** of Alleen geselecteerde **sites,** kunt u een .csv met een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="f4603-134">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="f4603-135">Deze opties zijn handig als u een pilot doet en u een beperkt aantal sites wilt opnemen om te starten.</span><span class="sxs-lookup"><span data-stu-id="f4603-135">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="f4603-136">U kunt de sjabloon .csv kopiëren:</span><span class="sxs-lookup"><span data-stu-id="f4603-136">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="f4603-137">We raden u niet aan geen **sites te kiezen,** omdat hiermee wordt voorkomen dat onderwerpen automatisch worden gemaakt of bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f4603-137">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="f4603-138">U kunt deze optie echter kiezen als u Onderwerpen wilt instellen en later sites wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="f4603-138">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="f4603-139">Het is raadzaam om een proces te maken voor gebruikers of kennisbeheerders om afzonderlijke sites op te vragen, indien nodig in uw organisatie, uit onderwerpdetectie te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f4603-139">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="f4603-140">Multi-geo</span><span class="sxs-lookup"><span data-stu-id="f4603-140">Multi-geo</span></span>

<span data-ttu-id="f4603-141">Als uw organisatie Microsoft 365 [Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)heeft geïmplementeerd, is het onderwerpcentrum ingericht op de centrale locatie en kunnen alleen SharePoint-sites op de centrale locatie worden gebruikt als bronnen voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="f4603-141">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="f4603-142">(Als u Alle **sites selecteert,** worden in Viva-onderwerpen alle sites op de centrale locatie gebruikt.)</span><span class="sxs-lookup"><span data-stu-id="f4603-142">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="f4603-143">Alle verwerking en opslag van inhoud gebeurt op de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="f4603-143">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="f4603-144">Gebruikersmachtigingen</span><span class="sxs-lookup"><span data-stu-id="f4603-144">User permissions</span></span>

<span data-ttu-id="f4603-145">De gebruikersmachtigingen die u opgeeft, bepalen welke personen in uw organisatie met onderwerpen werken en wat ze kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="f4603-145">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="f4603-146">Op dit moment biedt Viva Topics geen ondersteuning voor het verstrekken van licenties of gebruikersmachtigingen voor gastgebruikers (externe gebruikers).</span><span class="sxs-lookup"><span data-stu-id="f4603-146">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="f4603-147">*Onderwerpen beheren*</span><span class="sxs-lookup"><span data-stu-id="f4603-147">*Manage topics*</span></span>

<span data-ttu-id="f4603-148">Kennismanagers houden toezicht op de kwaliteit van informatie, de gestructureerde en andere best practices in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4603-148">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="f4603-149">Ze kunnen onderwerpen bevestigen en afwijzen.</span><span class="sxs-lookup"><span data-stu-id="f4603-149">They can confirm and reject topics.</span></span>

<span data-ttu-id="f4603-150">Hoewel u afzonderlijke onderwerpmanagers kunt opgeven, raden we u aan een beveiligingsgroep te maken (of een bestaande groep te gebruiken) met de personen die u kennisbeheerders wilt zijn.</span><span class="sxs-lookup"><span data-stu-id="f4603-150">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="f4603-151">U kunt deze beveiligingsgroep opgeven tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="f4603-151">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="f4603-152">*Onderwerpen maken en bewerken*</span><span class="sxs-lookup"><span data-stu-id="f4603-152">*Create and edit topics*</span></span>

<span data-ttu-id="f4603-153">Onderwerpcontribuanten zijn de kampioenen en experts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4603-153">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="f4603-154">Ze kunnen onderwerpen maken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="f4603-154">They can create and edit topics.</span></span> 

<span data-ttu-id="f4603-155">U wordt aangeraden iedereen in uw organisatie toe te staan onderwerpen te maken en te bewerken, omdat onderwerpervaringen het beste werken wanneer alle gebruikers informatie kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="f4603-155">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="f4603-156">Als u het maken en bewerken van onderwerpen wilt beperken tot specifieke personen of groepen, maakt u een beveiligingsgroep voor hen en geeft u deze op tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="f4603-156">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="f4603-157">U kunt ervoor kiezen om niemand toe te staan bij te dragen aan onderwerpen, maar dit wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="f4603-157">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="f4603-158">Kennisbeheerders kunnen nog steeds onderwerpen bewerken en maken als u deze optie kiest.</span><span class="sxs-lookup"><span data-stu-id="f4603-158">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="f4603-159">*Onderwerpkijkers*</span><span class="sxs-lookup"><span data-stu-id="f4603-159">*Topic viewers*</span></span>

<span data-ttu-id="f4603-160">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span><span class="sxs-lookup"><span data-stu-id="f4603-160">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="f4603-161">Gebruikers kunnen alleen gevonden onderwerpen zien wanneer ze toegang hebben tot de bestanden en pagina's waarin het onderwerp is gevonden.</span><span class="sxs-lookup"><span data-stu-id="f4603-161">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="f4603-162">Wanneer u onderwerpkijkers instelt, kunt u kiezen uit:</span><span class="sxs-lookup"><span data-stu-id="f4603-162">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="f4603-163">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="f4603-163">**Everyone in my organization**</span></span>
- <span data-ttu-id="f4603-164">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="f4603-164">**Only selected people or security groups**</span></span>
- <span data-ttu-id="f4603-165">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="f4603-165">**No one**</span></span>

<span data-ttu-id="f4603-166">We raden **Iedereen in mijn organisatie** aan, maar als u een pilot doet, wilt u mogelijk alleen geselecteerde personen of beveiligingsgroepen kiezen.</span><span class="sxs-lookup"><span data-stu-id="f4603-166">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="f4603-167">U kunt ook **Niemand kiezen als** u Onderwerpen wilt instellen, maar personen nog geen onderwerpen mogen laten zien.</span><span class="sxs-lookup"><span data-stu-id="f4603-167">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="f4603-168">(Kennismanagers hebben nog steeds toegang om ze de onderwerpen te laten bekijken en te helpen bij de beslissing om Onderwerpen breed beschikbaar te maken.)</span><span class="sxs-lookup"><span data-stu-id="f4603-168">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="f4603-169">Kennisregels</span><span class="sxs-lookup"><span data-stu-id="f4603-169">Knowledge rules</span></span>

<span data-ttu-id="f4603-170">Als beheerder kunt u bepaalde onderwerpen uitsluiten van onderwerpervaringen.</span><span class="sxs-lookup"><span data-stu-id="f4603-170">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="f4603-171">Dit is handig als u wilt voorkomen dat gevoelige gegevens in onderwerpen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f4603-171">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="f4603-172">Hoewel kennismanagers onderwerpen in het onderwerpcentrum kunnen uitsluiten, zijn onderwerpen die door de beheerder zijn uitgesloten, zelfs niet zichtbaar voor kennisbeheerders.</span><span class="sxs-lookup"><span data-stu-id="f4603-172">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="f4603-173">(Kennisbeheerders kunnen ook onderwerpen in het onderwerpcentrum verwijderen na de ontdekking.)</span><span class="sxs-lookup"><span data-stu-id="f4603-173">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="f4603-174">Als u onderwerpen op beheerdersniveau wilt uitsluiten, moet u deze toevoegen aan een .csv en het bestand uploaden.</span><span class="sxs-lookup"><span data-stu-id="f4603-174">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="f4603-175">U kunt dit doen tijdens de installatie of later.</span><span class="sxs-lookup"><span data-stu-id="f4603-175">You can do this during setup or later.</span></span>

<span data-ttu-id="f4603-176">Het .csv bestand moet de volgende parameters bevatten:</span><span class="sxs-lookup"><span data-stu-id="f4603-176">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="f4603-177">**Naam:** Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="f4603-177">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="f4603-178">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="f4603-178">There are two ways to do this:</span></span>
- <span data-ttu-id="f4603-179">**MatchType-Exact/Gedeeltelijk:** Typ of de opgegeven naam *een exact* of *gedeeltelijk overeenkomend* type was.</span><span class="sxs-lookup"><span data-stu-id="f4603-179">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="f4603-180">Exacte overeenkomst: U kunt de exacte naam of het acroniem (bijvoorbeeld *Contoso* of *ATL) opnemen.*</span><span class="sxs-lookup"><span data-stu-id="f4603-180">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="f4603-181">Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="f4603-181">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="f4603-182">Met een *boog worden bijvoorbeeld* alle onderwerpen uitgesloten met de woordboog in de boog, zoals boogcirkel, lassen van de boog van Het *plasma* of *Trainingsboog.*   Houd er rekening mee dat onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, niet worden *uitgesloten.*</span><span class="sxs-lookup"><span data-stu-id="f4603-182">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="f4603-183">**Staat voor (optioneel)**: (ook wel uitbreiding *genoemd)* Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.</span><span class="sxs-lookup"><span data-stu-id="f4603-183">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

<span data-ttu-id="f4603-185">U kunt de csv-sjabloon hieronder kopiëren:</span><span class="sxs-lookup"><span data-stu-id="f4603-185">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="f4603-186">Beheer</span><span class="sxs-lookup"><span data-stu-id="f4603-186">Administration</span></span>

<span data-ttu-id="f4603-187">Wanneer u Onderwerpen instelt, als onderdeel van het installatieproces, wordt automatisch een onderwerpcentrum gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f4603-187">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="f4603-188">Bedenk wat u het onderwerpcentrum wilt noemen en wat u wilt dat de URL is.</span><span class="sxs-lookup"><span data-stu-id="f4603-188">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="f4603-189">U kunt zowel de naam als de URL instellen als onderdeel van het installatieproces en u kunt de naam (maar niet de URL) later in de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f4603-189">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f4603-190">U kunt maar één onderwerpcentrum hebben.</span><span class="sxs-lookup"><span data-stu-id="f4603-190">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="f4603-191">Controlelijst instellen</span><span class="sxs-lookup"><span data-stu-id="f4603-191">Setup checklist</span></span>

<span data-ttu-id="f4603-192">Wanneer u onderwerpervaringen instelt, hebt u de volgende items nodig terwijl u door de installatiewizard gaat:</span><span class="sxs-lookup"><span data-stu-id="f4603-192">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f4603-193">Lijst met sites die u wilt opnemen of uitsluiten als niet alle sites worden opgenomen voor onderwerpdetectie</span><span class="sxs-lookup"><span data-stu-id="f4603-193">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="f4603-194">Beveiligingsgroep voor onderwerpkijkers als niet alle gebruikers onderwerpen mogen bekijken</span><span class="sxs-lookup"><span data-stu-id="f4603-194">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="f4603-195">Beveiligingsgroep voor onderwerpcontribuanten als niet alle gebruikers onderwerpen mogen maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="f4603-195">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="f4603-196">Beveiligingsgroep voor onderwerpkennisbeheerders als niet alle gebruikers onderwerpen mogen beheren</span><span class="sxs-lookup"><span data-stu-id="f4603-196">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="f4603-197">Lijst met gevoelige onderwerpen die u wilt uitsluiten van onderwerpdetectie</span><span class="sxs-lookup"><span data-stu-id="f4603-197">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="f4603-198">Een naam voor uw onderwerpcentrumsite</span><span class="sxs-lookup"><span data-stu-id="f4603-198">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="f4603-199">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f4603-199">See also</span></span>

[<span data-ttu-id="f4603-200">Onderwerpservaringen instellen</span><span class="sxs-lookup"><span data-stu-id="f4603-200">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="f4603-201">Onderwerpdetectie beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4603-201">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="f4603-202">Zichtbaarheid van onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4603-202">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="f4603-203">Onderwerpmachtigingen beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4603-203">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="f4603-204">De naam van het onderwerpcentrum wijzigen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4603-204">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
