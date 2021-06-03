---
title: Documenten taggen in een controleset
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Als u documenten in een revisieset tagt, kunt u overbodige inhoud verwijderen en relevante inhoud in een Advanced eDiscovery identificeren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736249"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="557a5-103">Documenten taggen in een revisieset in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="557a5-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="557a5-104">Het organiseren van inhoud in een revisieset is belangrijk om verschillende werkstromen in het eDiscovery-proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="557a5-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="557a5-105">Dit zijn:</span><span class="sxs-lookup"><span data-stu-id="557a5-105">This includes:</span></span>

- <span data-ttu-id="557a5-106">Overbodige inhoud verwijderen</span><span class="sxs-lookup"><span data-stu-id="557a5-106">Culling unnecessary content</span></span>

- <span data-ttu-id="557a5-107">Relevante inhoud identificeren</span><span class="sxs-lookup"><span data-stu-id="557a5-107">Identifying relevant content</span></span>

- <span data-ttu-id="557a5-108">Inhoud identificeren die moet worden gecontroleerd door een expert of een advocaat</span><span class="sxs-lookup"><span data-stu-id="557a5-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="557a5-109">Wanneer experts, advocaten of andere gebruikers inhoud in een revisieset bekijken, kunnen hun adviezen met betrekking tot de inhoud worden vastgelegd met behulp van tags.</span><span class="sxs-lookup"><span data-stu-id="557a5-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="557a5-110">Als het bijvoorbeeld de bedoeling is om overbodige inhoud te verwijderen, kan een gebruiker documenten taggen met een tag zoals 'niet-responsief'.</span><span class="sxs-lookup"><span data-stu-id="557a5-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="557a5-111">Nadat inhoud is beoordeeld en gelabeld, kan er een zoekactie voor revisiesets worden gemaakt om inhoud die is gemarkeerd als 'niet-responsief' uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="557a5-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="557a5-112">Met dit proces wordt de niet-responsieve inhoud uit de volgende stappen in de eDiscovery-werkstroom weggewerkt.</span><span class="sxs-lookup"><span data-stu-id="557a5-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="557a5-113">Het labelvenster in een revisieset kan voor elk geval worden aangepast, zodat de tags de beoogde revisiewerkstroom voor de zaak ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="557a5-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="557a5-114">Het bereik van tags is een Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="557a5-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="557a5-115">Dat betekent dat een zaak slechts één set tags kan bevatten die revisoren kunnen gebruiken om documenten met revisiesets te taggen.</span><span class="sxs-lookup"><span data-stu-id="557a5-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="557a5-116">U kunt geen andere set tags instellen voor gebruik in verschillende revisiesets in hetzelfde geval.</span><span class="sxs-lookup"><span data-stu-id="557a5-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="557a5-117">Tagtypen</span><span class="sxs-lookup"><span data-stu-id="557a5-117">Tag types</span></span>

<span data-ttu-id="557a5-118">Advanced eDiscovery bevat twee typen tags:</span><span class="sxs-lookup"><span data-stu-id="557a5-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="557a5-119">**Labels met één keuze:** hiermee beperkt u revisoren tot het selecteren van één tag in een groep.</span><span class="sxs-lookup"><span data-stu-id="557a5-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="557a5-120">Deze typen tags kunnen handig zijn om ervoor te zorgen dat revisoren geen conflicterende tags selecteren, zoals 'responsief' en 'niet-responsief'.</span><span class="sxs-lookup"><span data-stu-id="557a5-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="557a5-121">Labels met één keuze worden weergegeven als keuzerondjes.</span><span class="sxs-lookup"><span data-stu-id="557a5-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="557a5-122">**Meervoudige keuzelabels:** Toestaan dat beoordelingen meerdere tags in een groep selecteren.</span><span class="sxs-lookup"><span data-stu-id="557a5-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="557a5-123">Deze typen tags worden weergegeven als selectievakjes.</span><span class="sxs-lookup"><span data-stu-id="557a5-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="557a5-124">Tagstructuur</span><span class="sxs-lookup"><span data-stu-id="557a5-124">Tag structure</span></span>

<span data-ttu-id="557a5-125">Naast de tagtypen, kan de structuur van de manier waarop tags zijn ingedeeld in het tagvenster worden gebruikt om het labelen van documenten intuïtiever te maken.</span><span class="sxs-lookup"><span data-stu-id="557a5-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="557a5-126">Tags worden gegroepeerd op secties.</span><span class="sxs-lookup"><span data-stu-id="557a5-126">Tags are grouped by sections.</span></span> <span data-ttu-id="557a5-127">Zoeken in revisieset ondersteunt de mogelijkheid om te zoeken op tag en op tagsectie.</span><span class="sxs-lookup"><span data-stu-id="557a5-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="557a5-128">Dit betekent dat u een zoekopdracht voor revisiesets kunt maken om documenten op te halen die zijn gemarkeerd met een tag in een sectie.</span><span class="sxs-lookup"><span data-stu-id="557a5-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Secties taggen in het tagvenster](../media/TagTypes.png)

<span data-ttu-id="557a5-130">U kunt tags verder organiseren door ze in een sectie te nesten.</span><span class="sxs-lookup"><span data-stu-id="557a5-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="557a5-131">Als het bijvoorbeeld de bedoeling is om bevoorrechte inhoud te identificeren en te taggen, kan nesting worden gebruikt om duidelijk te maken dat een revisor een document kan taggen als 'Bevoorrecht' en het type privilege kan selecteren door de juiste geneste tag te controleren.</span><span class="sxs-lookup"><span data-stu-id="557a5-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Geneste tags in een tagsectie](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="557a5-133">Tags maken</span><span class="sxs-lookup"><span data-stu-id="557a5-133">Create tags</span></span>

<span data-ttu-id="557a5-134">Voordat u tags op documenten in de revisieset kunt toepassen, moet u een tagstructuur maken.</span><span class="sxs-lookup"><span data-stu-id="557a5-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="557a5-135">Open een revisieset en navigeer naar de opdrachtbalk en selecteer **Label op query.**</span><span class="sxs-lookup"><span data-stu-id="557a5-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="557a5-136">Selecteer in het deelvenster Labelen **de optie Tagopties beheren**</span><span class="sxs-lookup"><span data-stu-id="557a5-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="557a5-137">Selecteer **Tagsectie toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="557a5-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="557a5-138">Typ een labelgroeptitel en een optionele beschrijving en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="557a5-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="557a5-139">Selecteer de vervolgkeuzelijst met drie puntjes naast de titel van de taggroep en klik op **Selectievakje** Toevoegen of **knop Optie toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="557a5-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="557a5-140">Typ een naam en beschrijving voor het selectievakje of de optieknop.</span><span class="sxs-lookup"><span data-stu-id="557a5-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="557a5-141">Herhaal dit proces om nieuwe tagsecties, tagopties en selectievakjes te maken.</span><span class="sxs-lookup"><span data-stu-id="557a5-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Tagstructuur configureren](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="557a5-143">Tags toepassen</span><span class="sxs-lookup"><span data-stu-id="557a5-143">Applying tags</span></span>

<span data-ttu-id="557a5-144">Met de tagstructuur kunnen revisoren tags toepassen op documenten in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="557a5-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="557a5-145">Er zijn twee verschillende manieren om tags toe te passen:</span><span class="sxs-lookup"><span data-stu-id="557a5-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="557a5-146">Bestanden taggen</span><span class="sxs-lookup"><span data-stu-id="557a5-146">Tag files</span></span>

- <span data-ttu-id="557a5-147">Labelen op query</span><span class="sxs-lookup"><span data-stu-id="557a5-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="557a5-148">Bestanden taggen</span><span class="sxs-lookup"><span data-stu-id="557a5-148">Tag files</span></span>

<span data-ttu-id="557a5-149">Of u nu één item of meerdere items in een revisieset selecteert, u kunt tags toepassen op de selectie door op **Bestanden** labelen op de opdrachtbalk te klikken.</span><span class="sxs-lookup"><span data-stu-id="557a5-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="557a5-150">In het labelvenster kunt u een tag selecteren en deze automatisch toepassen op de geselecteerde documenten.</span><span class="sxs-lookup"><span data-stu-id="557a5-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Geselecteerde bestanden taggen](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="557a5-152">Tags worden alleen toegepast op geselecteerde items in de lijst met items.</span><span class="sxs-lookup"><span data-stu-id="557a5-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="557a5-153">Labelen op query</span><span class="sxs-lookup"><span data-stu-id="557a5-153">Tag by query</span></span>

<span data-ttu-id="557a5-154">Met Labelen op query kunt u tags toepassen op alle items die worden weergegeven door een filterquery die momenteel wordt toegepast in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="557a5-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="557a5-155">Schakel alle items in de revisieset uit en ga naar de opdrachtbalk en selecteer **Label per query.**</span><span class="sxs-lookup"><span data-stu-id="557a5-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="557a5-156">Selecteer in het labelvenster de tag die u wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="557a5-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="557a5-157">Onder de **vervolgkeuzekeuze van** Tag zijn er drie opties waarmee wordt bepaald op welke items de tag moet worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="557a5-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="557a5-158">**Items die overeenkomen met toegepaste query:** Hiermee worden tags toegepast op specifieke items die overeenkomen met de voorwaarden voor filterquery's.</span><span class="sxs-lookup"><span data-stu-id="557a5-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="557a5-159">**Bijbehorende gezinsitems opnemen:** Hiermee past u tags toe op specifieke items die overeenkomen met de filterqueryvoorwaarden en de bijbehorende gezinsitems.</span><span class="sxs-lookup"><span data-stu-id="557a5-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="557a5-160">*Gezinsitems* zijn items met dezelfde metagegevenswaarde FamilyId.</span><span class="sxs-lookup"><span data-stu-id="557a5-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="557a5-161">**Bijbehorende gespreksitems opnemen:** Hiermee worden tags toegepast op items die overeenkomen met de filterqueryvoorwaarden en de bijbehorende gespreksitems.</span><span class="sxs-lookup"><span data-stu-id="557a5-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="557a5-162">*Gespreksitems* zijn items die dezelfde waarden voor ConversationId-metagegevens delen.</span><span class="sxs-lookup"><span data-stu-id="557a5-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Tagselectie](../media/TagByQuery2.png)

4. <span data-ttu-id="557a5-164">Klik **op Taak labelen starten** om de labelingsbaan te activeren.</span><span class="sxs-lookup"><span data-stu-id="557a5-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="557a5-165">Labelfilter</span><span class="sxs-lookup"><span data-stu-id="557a5-165">Tag filter</span></span>

<span data-ttu-id="557a5-166">Gebruik het labelfilter in de revisieset om snel items te zoeken of uit te sluiten uit de queryresultaten op basis van de manier waarop een item is gelabeld.</span><span class="sxs-lookup"><span data-stu-id="557a5-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="557a5-167">Selecteer **Filters om** het filtervenster uit te vouwen.</span><span class="sxs-lookup"><span data-stu-id="557a5-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="557a5-168">Selecteer en vouw **itemeigenschappen uit.**</span><span class="sxs-lookup"><span data-stu-id="557a5-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="557a5-169">Schuif omlaag om het filter met de naam **Tag te zoeken,** schakel het selectievakje in en klik vervolgens op **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="557a5-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="557a5-170">Als u items met een specifieke tag wilt opnemen of uitsluiten uit een query, gaat u op een van de volgende punten te werk:</span><span class="sxs-lookup"><span data-stu-id="557a5-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="557a5-171">**Items opnemen:** Selecteer de tagwaarde en selecteer **Gelijk aan een van** de items in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="557a5-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="557a5-172">Of</span><span class="sxs-lookup"><span data-stu-id="557a5-172">Or</span></span>

   - <span data-ttu-id="557a5-173">**Items uitsluiten:** Selecteer de tagwaarde en selecteer **Gelijk aan geen van** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="557a5-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Items uitsluiten door labelfilter](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="557a5-175">Zorg ervoor dat u de pagina vernieuwt om ervoor te zorgen dat in het labelfilter de meest recente wijzigingen in de tagstructuur worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="557a5-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
