---
title: Gesprekken bekijken in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over de functie gespreksreconstructie in Advanced eDiscovery (gespreksthreading genoemd) om chatgesprekken te reconstrueren, te bekijken en te exporteren in Microsoft Teams en Yammer groepen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161734"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="3ac4e-103">Gespreksthreading in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3ac4e-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="3ac4e-104">Chatten is een handige manier om vragen te stellen, ideeën te delen of snel te communiceren tussen grote doelgroepen.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="3ac4e-105">Aangezien chatplatforms, zoals Microsoft Teams en Yammer-groepen, de basis vormen voor samenwerking tussen ondernemingen, moeten organisaties evalueren hoe hun eDiscovery-werkstroom deze nieuwe vormen van communicatie en samenwerking adresseert.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="3ac4e-106">De functie Gespreksreconstructie in Advanced eDiscovery is ontworpen om contextuele inhoud te identificeren en verschillende gespreksweergaven te produceren.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="3ac4e-107">Met deze mogelijkheid kunt u snel en efficiënt volledige chatgesprekken (ook wel discussielijngesprekken *genoemd)* bekijken die worden gegenereerd op platforms zoals Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="3ac4e-108">Met Gespreksreconstructie kunt u ingebouwde mogelijkheden gebruiken om gesprekken met discussielijn te reconstrueren, te bekijken en te exporteren.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="3ac4e-109">Gebruik Advanced eDiscovery Gespreksreconstructie om:</span><span class="sxs-lookup"><span data-stu-id="3ac4e-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="3ac4e-110">Behoud unieke metagegevens op berichtniveau voor alle berichten in een gesprek.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="3ac4e-111">Verzamel contextuele berichten rond uw zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="3ac4e-112">Discussielijngesprekken controleren, aantekeningen maken en redacteren.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="3ac4e-113">Afzonderlijke berichten of discussielijngesprekken exporteren</span><span class="sxs-lookup"><span data-stu-id="3ac4e-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="3ac4e-114">Terminologie</span><span class="sxs-lookup"><span data-stu-id="3ac4e-114">Terminology</span></span>

<span data-ttu-id="3ac4e-115">Hier volgen enkele definities om u te helpen aan de slag te gaan met Gespreksreconstructie.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="3ac4e-116">**Berichten:** Vertegenwoordig de kleinste eenheid van een gesprek.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="3ac4e-117">Berichten kunnen variëren in grootte, structuur en metagegevens.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="3ac4e-118">**Gesprek:** Vertegenwoordigt een groepering van een of meer berichten.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="3ac4e-119">In verschillende toepassingen kunnen gesprekken op verschillende manieren worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="3ac4e-120">In sommige toepassingen is er een expliciete actie die het resultaat is van het beantwoorden van een bestaand bericht.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="3ac4e-121">Gesprekken worden expliciet gevormd als gevolg van deze gebruikersactie.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="3ac4e-122">Hier is bijvoorbeeld een schermafbeelding van een kanaalgesprek in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams Kanaalgesprek](../media/threadedchat.png)

   <span data-ttu-id="3ac4e-124">In andere apps (zoals 1xN-chatberichten in Teams) is er geen formele antwoordketen en worden berichten in plaats daarvan weergegeven als een 'platte rivier met berichten' in één thread.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="3ac4e-125">In deze typen apps worden gesprekken afgeleid van een groep berichten die binnen een bepaalde tijd plaatsvinden.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="3ac4e-126">Deze 'soft-grouping' van berichten (in tegenstelling tot een antwoordketen) vertegenwoordigt het 'heen en weer' gesprek over een specifiek onderwerp dat interessant is.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="3ac4e-127">Stap 1: Een conceptverzameling maken</span><span class="sxs-lookup"><span data-stu-id="3ac4e-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="3ac4e-128">Nadat u relevante beheerders en inhoudslocaties hebt geïdentificeerd, kunt u een zoekopdracht maken om mogelijk relevante inhoud te vinden.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="3ac4e-129">Op het **tabblad Verzamelingen** in het Advanced eDiscovery kunt u een verzameling maken door op **Nieuwe verzameling** te klikken en de wizard te volgen.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="3ac4e-130">Zie Een conceptverzameling maken voor informatie over hoe u een verzameling kunt maken, een zoekquery kunt maken en een voorbeeld van de zoekresultaten [kunt bekijken.](create-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="3ac4e-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="3ac4e-131">Stap 2: Een conceptverzameling verbinden met een revisieset</span><span class="sxs-lookup"><span data-stu-id="3ac4e-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="3ac4e-132">Nadat u de zoekquery in een verzameling hebt bekeken en afgerond, kunt u de zoekresultaten toevoegen aan een revisieset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="3ac4e-133">Wanneer u de zoekresultaten toevoegt aan een revisieset, worden de oorspronkelijke gegevens gekopieerd naar een Azure Storage gebied om het controle- en analyseproces te vergemakkelijken.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="3ac4e-134">Zie Een conceptverzameling aan een revisieset toevoegen voor meer informatie over het toevoegen van zoekresultaten aan [een revisieset.](commit-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="3ac4e-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="3ac4e-135">Wanneer u items uit gesprekken toevoegt aan een revisieset, kunt u de optie Gesprekken met discussielijn gebruiken om contextuele berichten te verzamelen uit gesprekken die items bevatten die voldoen aan de zoekcriteria van de verzameling.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="3ac4e-136">Nadat u de optie discussielijngesprekken hebt geselecteerd, kunnen de volgende dingen gebeuren:</span><span class="sxs-lookup"><span data-stu-id="3ac4e-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Gesprek ophalen](../media/messagesandconversations.png)
  
1. <span data-ttu-id="3ac4e-138">Met behulp van een trefwoord- en datumbereikquery heeft de zoekopdracht een treffer geretourneerd in *Bericht 3.*</span><span class="sxs-lookup"><span data-stu-id="3ac4e-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="3ac4e-139">Dit bericht maakte deel uit van een groter gesprek, geïllustreerd door *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="3ac4e-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>
  
2. <span data-ttu-id="3ac4e-140">Wanneer u de gegevens toevoegt aan een revisieset en de opties voor het ophalen van gesprekken inschakelen, Advanced eDiscovery u terug en verzamelt u andere items in *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="3ac4e-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>
  
3. <span data-ttu-id="3ac4e-141">Nadat de items zijn toegevoegd aan de revisieset, kunt u alle afzonderlijke berichten van *CRC1 bekijken.*</span><span class="sxs-lookup"><span data-stu-id="3ac4e-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="3ac4e-142">Zie Een conceptverzameling aan een revisieset verbinden als u de optie gesprekken met discussielijn [wilt inschakelen.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="3ac4e-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>
  
## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="3ac4e-143">Stap 3: Discussielijngesprekken bekijken en exporteren</span><span class="sxs-lookup"><span data-stu-id="3ac4e-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="3ac4e-144">Nadat de inhoud is verwerkt en toegevoegd aan de revisieset, kunt u beginnen met het controleren van de gegevens in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="3ac4e-145">De controlemogelijkheden zijn verschillend, afhankelijk van of de inhoud is toegevoegd aan een standaardbeoordelingsset of een gespreksbeoordelingsset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="3ac4e-146">Gesprekken bekijken in een standaardbeoordelingsset</span><span class="sxs-lookup"><span data-stu-id="3ac4e-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="3ac4e-147">In een standaardbeoordelingsset worden berichten verwerkt en weergegeven als afzonderlijke items, vergelijkbaar met hoe ze worden opgeslagen in een postvakmap.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="3ac4e-148">In deze werkstroom wordt elk bericht verwerkt als een afzonderlijk item.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="3ac4e-149">Hierdoor zijn de overzichts- en exportopties met discussielijn niet beschikbaar in een standaardbeoordelingsset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Standaardbeoordelingsset](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="3ac4e-151">Gesprekken bekijken in een gespreksbeoordelingsset</span><span class="sxs-lookup"><span data-stu-id="3ac4e-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="3ac4e-152">In een gespreksoverzichtsset worden afzonderlijke berichten met elkaar verbonden en gepresenteerd als gesprekken.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="3ac4e-153">Op deze manier kunt u contextuele gesprekken bekijken en exporteren.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-153">This lets you review and export contextual conversations.</span></span> 

  ![Gespreksbeoordelingsset](../media/ConversationRSOptions.PNG)

<span data-ttu-id="3ac4e-155">In de volgende secties wordt beschreven hoe u gesprekken kunt bekijken en exporteren in een gespreksbeoordelingsset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="3ac4e-156">Gesprekken bekijken</span><span class="sxs-lookup"><span data-stu-id="3ac4e-156">Reviewing conversations</span></span>

<span data-ttu-id="3ac4e-157">In een gespreksbeoordelingsset kunt u de volgende opties gebruiken om het revisieproces te vergemakkelijken.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="3ac4e-158">**Groep op gesprek:** Groepen berichten in hetzelfde gesprek samen om gebruikers te helpen hun controleproces te vereenvoudigen en te versnellen.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="3ac4e-159">**Overzichtsweergave:** Hiermee wordt het gesprek met discussielijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="3ac4e-160">In deze weergave ziet u het hele gesprek en hebt u ook toegang tot de metagegevens voor elk afzonderlijk bericht.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="3ac4e-161">Metagegevens voor afzonderlijke berichten weergeven</span><span class="sxs-lookup"><span data-stu-id="3ac4e-161">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="3ac4e-162">Afzonderlijke berichten downloaden</span><span class="sxs-lookup"><span data-stu-id="3ac4e-162">Download individual messages</span></span>

- <span data-ttu-id="3ac4e-163">**Tekstweergave:** Geeft de uitgepakte tekst voor het hele gesprek weer.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="3ac4e-164">**Aantekeningen maken:** Hiermee kunt u een discussielijnweergave van het gesprek markeren.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="3ac4e-165">Alle berichten in het gesprek delen hetzelfde document met aantekeningen.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="3ac4e-166">**Labelen:** Wanneer u gesprekken in een revisieset bekijkt, kunt u tags weergeven en toepassen door te klikken op **Het deelvenster Labelen** in het deelvenster Codering.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="3ac4e-167">**Gespreksconversie opnieuw starten:** Wanneer berichten worden toegevoegd aan een gespreksbeoordelingsset, wordt automatisch een conversieklus uitgevoerd om de samenvatting met discussielijn te maken en aantekeningen te maken.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="3ac4e-168">Als de taak Gespreksreconstructie mislukt, kunt u deze taak opnieuw doen door te klikken op **Actie > Gespreks-PDF's** maken in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="3ac4e-169">Gesprekken exporteren</span><span class="sxs-lookup"><span data-stu-id="3ac4e-169">Exporting conversations</span></span>

<span data-ttu-id="3ac4e-170">In een gespreksbeoordelingsset kunt u de volgende opties instellen voor het exporteren van gesprekken:</span><span class="sxs-lookup"><span data-stu-id="3ac4e-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Exportopties voor gesprekken](../media/export.png)

<span data-ttu-id="3ac4e-172">a.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-172">a.</span></span> <span data-ttu-id="3ac4e-173">Opties voor metagegevens</span><span class="sxs-lookup"><span data-stu-id="3ac4e-173">Metadata options</span></span>

   - <span data-ttu-id="3ac4e-174">**Bestand laden:** Metagegevens zijn opgenomen voor elk afzonderlijk bericht, e-mailbericht en document.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-174">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="3ac4e-175">Er is één rij voor elk bericht in een gesprek.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-175">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="3ac4e-176">**Tags:** Tags uit uw revisieproces worden opgenomen in het metagegevensbestand.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-176">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="3ac4e-177">Berichten in een gesprek delen dezelfde tags.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-177">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="3ac4e-178">b.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-178">b.</span></span> <span data-ttu-id="3ac4e-179">Gespreksopties</span><span class="sxs-lookup"><span data-stu-id="3ac4e-179">Conversation options</span></span>
  
   - <span data-ttu-id="3ac4e-180">**Gespreksbestanden:** Wanneer u gespreksbestanden exporteert, wordt de weergave met aantekeningen geconverteerd naar een PDF-bestand en gedownload naar de exportmap.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-180">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="3ac4e-181">Berichten in één gespreksbestand wijzen naar de PDF-versie van hetzelfde gespreksbestand.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-181">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="3ac4e-182">**Afzonderlijke chatberichten:** Wanneer u afzonderlijke berichten exporteert, wordt elk uniek bericht in het gesprek geëxporteerd als een zelfstandig item.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-182">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="3ac4e-183">Het bestand wordt geëxporteerd in dezelfde indeling als in het postvak.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-183">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="3ac4e-184">Voor een specifiek gesprek ontvangt u meerdere MSG-bestanden.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-184">For a specific conversation, you receive multiple .msg files.</span></span>

     >[!NOTE]
     > <span data-ttu-id="3ac4e-185">Als u aantekeningen hebt toegepast op het gespreksbestand, worden deze aantekeningen niet overgebracht naar de afzonderlijke berichten.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-185">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

<span data-ttu-id="3ac4e-186">c.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-186">c.</span></span> <span data-ttu-id="3ac4e-187">Andere opties</span><span class="sxs-lookup"><span data-stu-id="3ac4e-187">Other options</span></span>

   - <span data-ttu-id="3ac4e-188">**Tekstbestanden genereren voor alle geëxporteerde inhoud:** Genereert een tekstbestand voor elk gesprek dat wordt geëxporteerd uit de revisieset.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-188">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>

   - <span data-ttu-id="3ac4e-189">**Geëxporteerde inhoud vervangen door opnieuw uitgevoerde PDF-bestanden:** Als tijdens het revisieproces redacted conversation files worden gegenereerd, zijn deze bestanden beschikbaar tijdens het exporteren.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-189">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="3ac4e-190">U kunt bepalen of u alleen de oorspronkelijke bestanden wilt exporteren (door deze optie niet te selecteren) of om de oorspronkelijke bestanden te vervangen door de heruitvoerde versies van de oorspronkelijke bestanden (door deze optie te selecteren), die als PDF-bestanden worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="3ac4e-190">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="3ac4e-191">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="3ac4e-191">More information</span></span>

<span data-ttu-id="3ac4e-192">Zie de volgende artikelen voor meer informatie over hoe u casegegevens in Advanced eDiscovery bekijkt:</span><span class="sxs-lookup"><span data-stu-id="3ac4e-192">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="3ac4e-193">Casegegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="3ac4e-193">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="3ac4e-194">Casegegevens analyseren</span><span class="sxs-lookup"><span data-stu-id="3ac4e-194">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="3ac4e-195">Casegegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="3ac4e-195">Export case data</span></span>](exporting-data-ediscover20.md)
