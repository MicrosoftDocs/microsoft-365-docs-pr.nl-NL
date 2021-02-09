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
description: Meer informatie over het plannen van Microsoft Viva-onderwerpen
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150476"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="aa786-103">Microsoft Viva-onderwerpen plannen</span><span class="sxs-lookup"><span data-stu-id="aa786-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="aa786-104">U kunt zelf bepalen hoe u onderwerpen ervaren in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa786-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="aa786-105">Uw planningsbeslissingen voor Onderwerpen garanderen dat onderwerpen van hoge kwaliteit worden weergegeven aan uw gebruikers en dat ze over de juiste machtigingen voor het gebruik en bijdragen van kennis zijn.</span><span class="sxs-lookup"><span data-stu-id="aa786-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="aa786-106">In dit artikel worden de volgende planningsbeslissingen beschreven:</span><span class="sxs-lookup"><span data-stu-id="aa786-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="aa786-107">Welke SharePoint-sites u wilt crawlen voor onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aa786-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="aa786-108">Welke onderwerpen u indien van onderwerpervaringen wilt uitsluiten</span><span class="sxs-lookup"><span data-stu-id="aa786-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="aa786-109">Voor welke gebruikers u onderwerpen zichtbaar wilt maken</span><span class="sxs-lookup"><span data-stu-id="aa786-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="aa786-110">Welke gebruikers u machtigingen wilt geven voor het beheren van onderwerpen in het onderwerpcentrum</span><span class="sxs-lookup"><span data-stu-id="aa786-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="aa786-111">Welke gebruikers u machtigingen wilt geven voor het maken of bewerken van onderwerpen in het onderwerpcentrum</span><span class="sxs-lookup"><span data-stu-id="aa786-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="aa786-112">Welke naam u het onderwerpcentrum wilt geven</span><span class="sxs-lookup"><span data-stu-id="aa786-112">What name you want to give your topic center</span></span>

<span data-ttu-id="aa786-113">De beveiliging en privacy van uw gegevens wordt in acht genomen en door onderwerpervaringen hebben gebruikers geen extra toegang tot bestanden waar ze geen rechten voor hebben.</span><span class="sxs-lookup"><span data-stu-id="aa786-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="aa786-114">U wordt aangeraden ook de beveiliging en [privacy van Microsoft Viva-onderwerpen](topic-experiences-security-privacy.md) te lezen als onderdeel van uw planningsproces.</span><span class="sxs-lookup"><span data-stu-id="aa786-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa786-115">Vereisten</span><span class="sxs-lookup"><span data-stu-id="aa786-115">Requirements</span></span>

<span data-ttu-id="aa786-116">U moet zijn [geabonneerd op Viva-onderwerpen](https://www.microsoft.com/microsoft-viva/topics) en een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-beheercentrum en Onderwerpen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="aa786-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="aa786-117">Alle gebruikers die Onderwerpen gaan gebruiken, hebben een **licentie voor Onderwerpervaringen** nodig.</span><span class="sxs-lookup"><span data-stu-id="aa786-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="aa786-118">Het toewijzen van licenties is mogelijk in [Microsoft Viva-onderwerpen instellen.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="aa786-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="aa786-119">Onderwerpdetectie</span><span class="sxs-lookup"><span data-stu-id="aa786-119">Topic discovery</span></span>

<span data-ttu-id="aa786-120">Met de instellingen voor onderwerpdetectie kunt u opgeven welke SharePoint-sites worden gebruikt als bronnen voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="aa786-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="aa786-121">U kunt ervoor kiezen om alle SharePoint-sites, een specifieke lijst met sites of geen sites op te nemen.</span><span class="sxs-lookup"><span data-stu-id="aa786-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="aa786-122">U wordt aangeraden alle sites te kiezen, zodat u met onderwerpervaringen een groot aantal goede onderwerpen voor uw gebruikers kunt ontdekken.</span><span class="sxs-lookup"><span data-stu-id="aa786-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="aa786-123">Wanneer u Onderwerpen in stelt, kunt u kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="aa786-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="aa786-124">**Alle sites:** alle SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa786-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="aa786-125">Dit geldt ook voor huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="aa786-125">This includes current and future sites.</span></span>
- <span data-ttu-id="aa786-126">**Alle, behalve geselecteerde sites:** Alle sites behalve de sites die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="aa786-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="aa786-127">Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="aa786-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="aa786-128">**Alleen geselecteerde sites:** alleen de sites die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="aa786-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="aa786-129">Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="aa786-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="aa786-130">**Geen sites:** Geen SharePoint-sites opnemen.</span><span class="sxs-lookup"><span data-stu-id="aa786-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="aa786-131">Als u Alle **kiest, met uitzondering** van geselecteerde sites of Alleen geselecteerde **sites,** kunt u een CSV-bestand met een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="aa786-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="aa786-132">Deze opties zijn handig als u een testfase hebt en een beperkt aantal sites wilt opnemen om te starten.</span><span class="sxs-lookup"><span data-stu-id="aa786-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="aa786-133">U kunt de CSV-sjabloon hieronder kopiëren:</span><span class="sxs-lookup"><span data-stu-id="aa786-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="aa786-134">U wordt niet aangeraden Geen **sites te kiezen,** omdat hiermee wordt voorkomen dat onderwerpen automatisch worden gemaakt of bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="aa786-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="aa786-135">U kunt deze optie echter kiezen als u Onderwerpen wilt instellen en later sites wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="aa786-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="aa786-136">U wordt aangeraden een proces te maken voor gebruikers of kennisbeheerders om zo nodig in uw organisatie aan te vragen dat afzonderlijke sites worden verwijderd uit onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="aa786-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="aa786-137">Gebruikersmachtigingen</span><span class="sxs-lookup"><span data-stu-id="aa786-137">User permissions</span></span>

<span data-ttu-id="aa786-138">De gebruikersmachtigingen die u opgeeft, bepalen welke personen in uw organisatie werken met onderwerpen en wat ze kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="aa786-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="aa786-139">*Onderwerpen beheren*</span><span class="sxs-lookup"><span data-stu-id="aa786-139">*Manage topics*</span></span>

<span data-ttu-id="aa786-140">Kennisbeheerders zijn verantwoordelijk voor de kwaliteit van informatie, de gestructureerde en andere best practices in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa786-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="aa786-141">Ze kunnen onderwerpen bevestigen en weigeren.</span><span class="sxs-lookup"><span data-stu-id="aa786-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="aa786-142">Hoewel u afzonderlijke onderwerpbeheerders kunt opgeven, raden we u aan een beveiligingsgroep te maken (of een bestaande groep te gebruiken) die de personen bevat die kennisbeheerders moeten worden.</span><span class="sxs-lookup"><span data-stu-id="aa786-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="aa786-143">U kunt deze beveiligingsgroep opgeven tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="aa786-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="aa786-144">*Onderwerpen maken en bewerken*</span><span class="sxs-lookup"><span data-stu-id="aa786-144">*Create and edit topics*</span></span>

<span data-ttu-id="aa786-145">Onderwerpbijdragers zijn de kampioenen en deskundigen op het gebied van onderwerpen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa786-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="aa786-146">Ze kunnen onderwerpen maken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="aa786-146">They can create and edit topics.</span></span> 

<span data-ttu-id="aa786-147">Het is raadzaam om iedereen in uw organisatie toe te staan onderwerpen te maken en te bewerken, omdat onderwerpervaringen het beste werken wanneer alle gebruikers informatie kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="aa786-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="aa786-148">Als u het maken en bewerken van onderwerpen wilt beperken tot specifieke personen of groepen, maakt u een beveiligingsgroep voor hen en geeft u deze op tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="aa786-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="aa786-149">U kunt ervoor kiezen om niemand toe te staan een bijdrage te leveren aan onderwerpen, maar dit wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="aa786-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="aa786-150">Knowledge Managers kunnen nog steeds onderwerpen bewerken en maken als u deze optie kiest.</span><span class="sxs-lookup"><span data-stu-id="aa786-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="aa786-151">*Onderwerpkijkers*</span><span class="sxs-lookup"><span data-stu-id="aa786-151">*Topic viewers*</span></span>

<span data-ttu-id="aa786-152">Onderwerpkijkers kunnen informatie zien over onderwerppagina's, in zoekresultaten en wanneer onderwerpen zijn gemarkeerd in de inhoud, zoals SharePoint-pagina's.</span><span class="sxs-lookup"><span data-stu-id="aa786-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="aa786-153">Gebruikers kunnen alleen gevonden onderwerpen zien wanneer ze toegang hebben tot de bestanden en pagina's waarin het onderwerp is aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="aa786-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="aa786-154">Wanneer u onderwerpkijkers instelt, kunt u kiezen uit:</span><span class="sxs-lookup"><span data-stu-id="aa786-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="aa786-155">**Iedereen in mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="aa786-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="aa786-156">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="aa786-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="aa786-157">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="aa786-157">**No one**</span></span>

<span data-ttu-id="aa786-158">We raden **Iedereen in mijn organisatie** aan, maar als u een testfase doet, kunt u alleen geselecteerde personen of beveiligingsgroepen kiezen.</span><span class="sxs-lookup"><span data-stu-id="aa786-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="aa786-159">U kunt ook **Nee kiezen** als u Onderwerpen wilt instellen, maar personen nog geen onderwerpen wilt laten zien.</span><span class="sxs-lookup"><span data-stu-id="aa786-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="aa786-160">(Knowledge Managers hebben nog steeds toegang om hen toe te staan de onderwerpen te bekijken en hulp bij de beslissing om Onderwerpen algemeen beschikbaar te maken.)</span><span class="sxs-lookup"><span data-stu-id="aa786-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="aa786-161">Kennisregels</span><span class="sxs-lookup"><span data-stu-id="aa786-161">Knowledge rules</span></span>

<span data-ttu-id="aa786-162">Als beheerder kunt u bepaalde onderwerpen uitsluiten van onderwerpervaringen.</span><span class="sxs-lookup"><span data-stu-id="aa786-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="aa786-163">Dit is handig als u wilt voorkomen dat gevoelige gegevens in onderwerpen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="aa786-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="aa786-164">Hoewel kennisbeheerders onderwerpen in het onderwerpcentrum kunnen uitsluiten, zijn onderwerpen die door de beheerder worden uitgesloten zelfs niet zichtbaar voor kennismanagers.</span><span class="sxs-lookup"><span data-stu-id="aa786-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="aa786-165">(Kennisbeheerders kunnen na detectie ook onderwerpen in het onderwerpcentrum verwijderen.)</span><span class="sxs-lookup"><span data-stu-id="aa786-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="aa786-166">Als u onderwerpen wilt uitsluiten op beheerdersniveau, moet u deze toevoegen aan een CSV-bestand en het bestand uploaden.</span><span class="sxs-lookup"><span data-stu-id="aa786-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="aa786-167">U kunt dit doen tijdens de installatie of later.</span><span class="sxs-lookup"><span data-stu-id="aa786-167">You can do this during setup or later.</span></span>

<span data-ttu-id="aa786-168">Het CSV-bestand moet de volgende parameters bevatten:</span><span class="sxs-lookup"><span data-stu-id="aa786-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="aa786-169">**Naam:** typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="aa786-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="aa786-170">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="aa786-170">There are two ways to do this:</span></span>
- <span data-ttu-id="aa786-171">**MatchType-Exact/Gedeeltelijk:** typ of de naam die u hebt ingevoerd *een exact* of *gedeeltelijk* overeenkomsttype is.</span><span class="sxs-lookup"><span data-stu-id="aa786-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="aa786-172">Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen (bijvoorbeeld *Contoso* of *ATL).*</span><span class="sxs-lookup"><span data-stu-id="aa786-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="aa786-173">Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een bepaald woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="aa786-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="aa786-174">Met een *boog worden bijvoorbeeld* alle onderwerpen met de woordbogen uitgesloten, zoals Boogcirkel, *Arc-boog* of *Trainingsbogen.*   Onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, worden niet *uitgesloten.*</span><span class="sxs-lookup"><span data-stu-id="aa786-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="aa786-175">**Staat voor (optioneel)**: (ook wel uitbreiding *genoemd)* Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.</span><span class="sxs-lookup"><span data-stu-id="aa786-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

<span data-ttu-id="aa786-177">U kunt de csv-sjabloon hieronder kopiëren:</span><span class="sxs-lookup"><span data-stu-id="aa786-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="aa786-178">Beheer</span><span class="sxs-lookup"><span data-stu-id="aa786-178">Administration</span></span>

<span data-ttu-id="aa786-179">Wanneer u Onderwerpen instelt, wordt als onderdeel van het installatieproces automatisch een onderwerpcentrum gemaakt.</span><span class="sxs-lookup"><span data-stu-id="aa786-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="aa786-180">Bedenk wat u het onderwerpcentrum wilt noemen en wat u de URL wilt maken.</span><span class="sxs-lookup"><span data-stu-id="aa786-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="aa786-181">U kunt zowel de naam als de URL instellen als onderdeel van het installatieproces en u kunt de naam (maar niet de URL) later wijzigen in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="aa786-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="aa786-182">U kunt slechts één onderwerpcentrum hebben.</span><span class="sxs-lookup"><span data-stu-id="aa786-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="aa786-183">Controlelijst instellen</span><span class="sxs-lookup"><span data-stu-id="aa786-183">Setup checklist</span></span>

<span data-ttu-id="aa786-184">Wanneer u onderwerpervaringen instelt, hebt u de volgende items nodig tijdens het uitvoeren van de installatiewizard:</span><span class="sxs-lookup"><span data-stu-id="aa786-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="aa786-185">Lijst met sites die u wilt opnemen of uitsluiten als niet alle sites voor onderwerpdetectie worden opgenomen</span><span class="sxs-lookup"><span data-stu-id="aa786-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="aa786-186">Beveiligingsgroep voor onderwerpbekijkers als niet alle gebruikers de onderwerpen kunnen bekijken</span><span class="sxs-lookup"><span data-stu-id="aa786-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="aa786-187">Beveiligingsgroep voor onderwerpbijdragers als niet alle gebruikers onderwerpen mogen maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="aa786-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="aa786-188">Beveiligingsgroep voor onderwerpkennisbeheerders als niet alle gebruikers de mogelijkheid bieden om onderwerpen te beheren</span><span class="sxs-lookup"><span data-stu-id="aa786-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="aa786-189">Lijst met gevoelige onderwerpen die u wilt uitsluiten van onderwerpdetectie</span><span class="sxs-lookup"><span data-stu-id="aa786-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="aa786-190">Een naam voor uw onderwerpcentrumsite</span><span class="sxs-lookup"><span data-stu-id="aa786-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="aa786-191">Zie ook</span><span class="sxs-lookup"><span data-stu-id="aa786-191">See also</span></span>

[<span data-ttu-id="aa786-192">Onderwerpservaringen instellen</span><span class="sxs-lookup"><span data-stu-id="aa786-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="aa786-193">Onderwerpdetectie beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa786-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="aa786-194">Zichtbaarheid van onderwerpen beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa786-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="aa786-195">Onderwerpmachtigingen beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa786-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="aa786-196">De naam van het onderwerpcentrum wijzigen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa786-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
