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
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161526"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="2f16d-103">Documenten taggen in een revisieset in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2f16d-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="2f16d-104">Het organiseren van inhoud in een revisieset is belangrijk om verschillende werkstromen in het eDiscovery-proces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="2f16d-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="2f16d-105">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="2f16d-105">This includes:</span></span>

- <span data-ttu-id="2f16d-106">Overbodige inhoud verwijderen</span><span class="sxs-lookup"><span data-stu-id="2f16d-106">Culling unnecessary content</span></span>

- <span data-ttu-id="2f16d-107">Relevante inhoud identificeren</span><span class="sxs-lookup"><span data-stu-id="2f16d-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="2f16d-108">Inhoud identificeren die moet worden gecontroleerd door een expert of een advocaat</span><span class="sxs-lookup"><span data-stu-id="2f16d-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="2f16d-109">Wanneer experts, advocaten of andere gebruikers inhoud in een revisieset bekijken, kunnen hun adviezen met betrekking tot de inhoud worden vastgelegd met behulp van tags.</span><span class="sxs-lookup"><span data-stu-id="2f16d-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="2f16d-110">Als het bijvoorbeeld de bedoeling is om overbodige inhoud te verwijderen, kan een gebruiker documenten taggen met een tag zoals 'niet-responsief'.</span><span class="sxs-lookup"><span data-stu-id="2f16d-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="2f16d-111">Nadat inhoud is beoordeeld en gelabeld, kan er een zoekactie voor revisiesets worden gemaakt om inhoud die is gemarkeerd als 'niet-responsief' uit te sluiten, waardoor deze inhoud niet meer in de volgende stappen in de eDiscovery-werkstroom wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2f16d-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="2f16d-112">Het tagvenster kan voor elk geval worden aangepast, zodat de tags de beoogde revisiewerkstroom kunnen ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="2f16d-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="2f16d-113">Tagtypen</span><span class="sxs-lookup"><span data-stu-id="2f16d-113">Tag types</span></span>

<span data-ttu-id="2f16d-114">Advanced eDiscovery bevat twee typen tags:</span><span class="sxs-lookup"><span data-stu-id="2f16d-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="2f16d-115">**Labels voor één keuze:** gebruikers worden beperkt tot het selecteren van één tag in een groep.</span><span class="sxs-lookup"><span data-stu-id="2f16d-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="2f16d-116">Dit kan handig zijn om ervoor te zorgen dat gebruikers geen conflicterende tags selecteren, zoals 'responsief' en 'niet-responsief'.</span><span class="sxs-lookup"><span data-stu-id="2f16d-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="2f16d-117">Deze worden weergegeven als radioknoppen.</span><span class="sxs-lookup"><span data-stu-id="2f16d-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="2f16d-118">**Meervoudige keuzelabels:** gebruikers toestaan meerdere tags in een groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2f16d-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="2f16d-119">Deze worden weergegeven als selectievakjes.</span><span class="sxs-lookup"><span data-stu-id="2f16d-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="2f16d-120">Tagstructuur</span><span class="sxs-lookup"><span data-stu-id="2f16d-120">Tag structure</span></span>

<span data-ttu-id="2f16d-121">Naast de tagtypen, kan de structuur van de manier waarop tags zijn ingedeeld in het tagvenster worden gebruikt om het labelen van documenten intuïtiever te maken.</span><span class="sxs-lookup"><span data-stu-id="2f16d-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="2f16d-122">Tags worden gegroepeerd op secties.</span><span class="sxs-lookup"><span data-stu-id="2f16d-122">Tags are grouped by sections.</span></span> <span data-ttu-id="2f16d-123">Zoeken in revisieset ondersteunt de mogelijkheid om te zoeken op tag en op tagsectie.</span><span class="sxs-lookup"><span data-stu-id="2f16d-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="2f16d-124">Dit betekent dat u een zoekopdracht voor revisiesets kunt maken om documenten op te halen die zijn gemarkeerd met een tag in een sectie.</span><span class="sxs-lookup"><span data-stu-id="2f16d-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Secties taggen in het tagvenster](../media/Tagtypes.png)

<span data-ttu-id="2f16d-126">Tags kunnen verder worden georganiseerd door ze in een sectie te nesten.</span><span class="sxs-lookup"><span data-stu-id="2f16d-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="2f16d-127">Als het bijvoorbeeld de bedoeling is om bevoorrechte inhoud te identificeren en te taggen, kan nesting worden gebruikt om duidelijk te maken dat een gebruiker een document kan taggen als 'Privileged' en het type privilege kan selecteren door de juiste geneste tag te controleren.</span><span class="sxs-lookup"><span data-stu-id="2f16d-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Geneste tags in een tagsectie](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="2f16d-129">Tags toepassen</span><span class="sxs-lookup"><span data-stu-id="2f16d-129">Applying tags</span></span>

<span data-ttu-id="2f16d-130">Er zijn verschillende manieren om een tag toe te passen op inhoud.</span><span class="sxs-lookup"><span data-stu-id="2f16d-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="2f16d-131">Eén document labelen</span><span class="sxs-lookup"><span data-stu-id="2f16d-131">Tagging a single document</span></span>

<span data-ttu-id="2f16d-132">Wanneer u een document bekijkt in een revisieset, kunt u de tags weergeven die door een revisie kunnen worden gebruikt door te klikken op **Het deelvenster Labelen.**</span><span class="sxs-lookup"><span data-stu-id="2f16d-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Klik op Deelvenster Tag om het deelvenster met tags weer te geven](../media/Singledoctag.png)

<span data-ttu-id="2f16d-134">Op deze manier kunt u tags toepassen op het document dat in de viewer wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f16d-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="2f16d-135">Bulklabels</span><span class="sxs-lookup"><span data-stu-id="2f16d-135">Bulk tagging</span></span>

<span data-ttu-id="2f16d-136">Bulklabels kunnen worden uitgevoerd door meerdere bestanden in het  resultatenraster te selecteren en vervolgens de tags in het deelvenster Labelen te gebruiken, vergelijkbaar met het labelen van afzonderlijke documenten.</span><span class="sxs-lookup"><span data-stu-id="2f16d-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="2f16d-137">Bulk-un-tagging kan worden uitgevoerd door tags tweemaal te selecteren. met de eerste klik wordt de tag toegepast en met de tweede selectie wordt ervoor gezorgd dat de tag voor alle geselecteerde bestanden is geweken.</span><span class="sxs-lookup"><span data-stu-id="2f16d-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Een schermafbeelding van een beschrijving van een mobiele telefoon die automatisch wordt gegenereerd](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="2f16d-139">Wanneer het label bulksgewijs wordt gemarkeerd, wordt in het labelvenster een aantal bestanden weergegeven dat voor elke tag in het deelvenster is gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="2f16d-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="2f16d-140">Labelen in andere revisiepanelen</span><span class="sxs-lookup"><span data-stu-id="2f16d-140">Tagging in other review panels</span></span>

<span data-ttu-id="2f16d-141">Wanneer u documenten controleert, kunt u de andere revisiepanelen gebruiken om andere kenmerken van documenten in het resultatenraster te bekijken.</span><span class="sxs-lookup"><span data-stu-id="2f16d-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="2f16d-142">Dit omvat het controleren van andere gerelateerde documenten, e-mailthreads, near duplicates en hash duplicaten.</span><span class="sxs-lookup"><span data-stu-id="2f16d-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="2f16d-143">Wanneer u bijvoorbeeld gerelateerde documenten bekijkt (met  behulp van het revisievenster documentfamilie), kunt u de controletijd aanzienlijk verminderen door gerelateerde documenten bulksgewijs te labelen.</span><span class="sxs-lookup"><span data-stu-id="2f16d-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="2f16d-144">Als een e-mailbericht bijvoorbeeld meerdere bijlagen heeft en u ervoor wilt zorgen dat het hele gezin consistent wordt gelabeld.</span><span class="sxs-lookup"><span data-stu-id="2f16d-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="2f16d-145">U kunt bijvoorbeeld als volgende het deelvenster Labelen weergeven **wanneer** u het **revisievenster Documentfamilie** gebruikt:</span><span class="sxs-lookup"><span data-stu-id="2f16d-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="2f16d-146">Als het revisievenster is geopend voor een geselecteerd document (bijvoorbeeld  door de lijst  met gerelateerde inhoud weer te geven in het revisievenster documentfamilie, klikt u op Documenten taggen onder het documentfamiliebeoordelingsvenster.</span><span class="sxs-lookup"><span data-stu-id="2f16d-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="2f16d-147">Het labelvenster wordt weergegeven als een pop-upvenster.</span><span class="sxs-lookup"><span data-stu-id="2f16d-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="2f16d-148">Kies een of meer tags om het geselecteerde document toe te passen.</span><span class="sxs-lookup"><span data-stu-id="2f16d-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="2f16d-149">Als u alle documenten wilt taggen, selecteert u alle documenten in het deelvenster **Documentfamilie,** klikt u op Documenten labelen **en** kiest u vervolgens de tags die u wilt toepassen op de hele familie documenten.</span><span class="sxs-lookup"><span data-stu-id="2f16d-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](../media/Relatedtag.png)
