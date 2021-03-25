---
title: Technieken in de tijdlijn van het apparaat
description: Informatie over de apparaattijdlijn in Microsoft Defender voor Eindpunt
keywords: apparaattijdlijn, eindpunt, MITRE, MITRE ATT&CK, technieken, tactieken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185465"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="75b12-104">Technieken in de tijdlijn van het apparaat</span><span class="sxs-lookup"><span data-stu-id="75b12-104">Techniques in the device timeline</span></span>


<span data-ttu-id="75b12-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="75b12-105">**Applies to:**</span></span>
- [<span data-ttu-id="75b12-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="75b12-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="75b12-107">U kunt meer inzicht krijgen in een onderzoek door de gebeurtenissen op een bepaald apparaat te analyseren.</span><span class="sxs-lookup"><span data-stu-id="75b12-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="75b12-108">Selecteer eerst het apparaat van belang in de [lijst Apparaten.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="75b12-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="75b12-109">Op de apparaatpagina kunt u het tabblad **Tijdlijn** selecteren om alle gebeurtenissen op het apparaat weer te geven.</span><span class="sxs-lookup"><span data-stu-id="75b12-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="75b12-110">Technieken in de tijdlijn begrijpen</span><span class="sxs-lookup"><span data-stu-id="75b12-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="75b12-111">Sommige informatie heeft betrekking op een vooraf uitgebrachte productfunctie in een openbare preview die aanzienlijk kan worden gewijzigd voordat deze commercieel wordt uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="75b12-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="75b12-112">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="75b12-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="75b12-113">In Microsoft Defender voor Eindpunt zijn **technieken** een extra gegevenstype in de tijdlijn van de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="75b12-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="75b12-114">Technieken bieden meer inzicht in activiteiten die zijn gekoppeld aan [MITRE ATT-&CK-technieken](https://attack.mitre.org/) of subtechnieken.</span><span class="sxs-lookup"><span data-stu-id="75b12-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="75b12-115">Deze functie vereenvoudigt de onderzoekservaring door analisten te helpen inzicht te krijgen in de activiteiten die op een apparaat zijn waargenomen.</span><span class="sxs-lookup"><span data-stu-id="75b12-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="75b12-116">Analisten kunnen vervolgens besluiten om het verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="75b12-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="75b12-117">Voor een openbaar voorbeeld zijn technieken standaard beschikbaar en worden deze samen met gebeurtenissen weergegeven wanneer de tijdlijn van een apparaat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="75b12-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Schermafbeelding van technieken in de tijdlijn van het apparaat](images/device-timeline-2.png)

<span data-ttu-id="75b12-119">Technieken zijn gemarkeerd met vetgedrukte tekst en worden weergegeven met een blauw pictogram aan de linkerkant.</span><span class="sxs-lookup"><span data-stu-id="75b12-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="75b12-120">De bijbehorende MITRE ATT-&CK-id en -techniek worden ook weergegeven als tags onder Aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="75b12-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="75b12-121">Zoek- en exportopties zijn ook beschikbaar voor Technieken.</span><span class="sxs-lookup"><span data-stu-id="75b12-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="75b12-122">Onderzoeken met behulp van het zijdeelvenster</span><span class="sxs-lookup"><span data-stu-id="75b12-122">Investigate using the side pane</span></span>

<span data-ttu-id="75b12-123">Selecteer een techniek om het bijbehorende zijvenster te openen.</span><span class="sxs-lookup"><span data-stu-id="75b12-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="75b12-124">Hier ziet u aanvullende informatie en inzichten, zoals gerelateerde ATT-&CK-technieken, tactieken en beschrijvingen.</span><span class="sxs-lookup"><span data-stu-id="75b12-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="75b12-125">Selecteer de specifieke *aanvalstechniek om* de gerelateerde att-&CK-techniekpagina te openen, waar u meer informatie over kunt vinden.</span><span class="sxs-lookup"><span data-stu-id="75b12-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="75b12-126">U kunt de details van een entiteit kopiëren wanneer u een blauw pictogram aan de rechterkant ziet.</span><span class="sxs-lookup"><span data-stu-id="75b12-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="75b12-127">Als u bijvoorbeeld de SHA1 van een gerelateerd bestand wilt kopiëren, selecteert u het blauwe paginapictogram.</span><span class="sxs-lookup"><span data-stu-id="75b12-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Entiteitsgegevens kopiëren](images/techniques-side-pane-clickable.png)

<span data-ttu-id="75b12-129">U kunt hetzelfde doen voor opdrachtlijnen.</span><span class="sxs-lookup"><span data-stu-id="75b12-129">You can do the same for command lines.</span></span>

![Opdrachtregel kopiëren](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="75b12-131">Gerelateerde gebeurtenissen onderzoeken</span><span class="sxs-lookup"><span data-stu-id="75b12-131">Investigate related events</span></span>

<span data-ttu-id="75b12-132">Als u [geavanceerde jacht wilt gebruiken](advanced-hunting-overview.md) om gebeurtenissen te zoeken die betrekking hebben op de geselecteerde techniek, selecteert u **Opzoeken naar gerelateerde gebeurtenissen.**</span><span class="sxs-lookup"><span data-stu-id="75b12-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="75b12-133">Dit leidt naar de geavanceerde pagina met een query om gebeurtenissen te zoeken die betrekking hebben op de techniek.</span><span class="sxs-lookup"><span data-stu-id="75b12-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Op zoek gaan naar gerelateerde gebeurtenissen](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="75b12-135">Query's met **behulp** van de knop Zoeken naar gerelateerde gebeurtenissen in een zijvenster Techniek geven alle gebeurtenissen weer die betrekking hebben op de geïdentificeerde techniek, maar bevatten de techniek zelf niet in de queryresultaten.</span><span class="sxs-lookup"><span data-stu-id="75b12-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="75b12-136">De tijdlijn van uw apparaat aanpassen</span><span class="sxs-lookup"><span data-stu-id="75b12-136">Customize your device timeline</span></span>

<span data-ttu-id="75b12-137">Rechtsboven in de tijdlijn van het apparaat kunt u een datumbereik kiezen om het aantal gebeurtenissen en technieken in de tijdlijn te beperken.</span><span class="sxs-lookup"><span data-stu-id="75b12-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="75b12-138">U kunt aanpassen welke kolommen u wilt laten zien.</span><span class="sxs-lookup"><span data-stu-id="75b12-138">You can customize which columns to expose.</span></span> <span data-ttu-id="75b12-139">U kunt ook filteren op gemarkeerde gebeurtenissen op gegevenstype of op gebeurtenisgroep.</span><span class="sxs-lookup"><span data-stu-id="75b12-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="75b12-140">Kolommen kiezen om weer te geven</span><span class="sxs-lookup"><span data-stu-id="75b12-140">Choose columns to expose</span></span>
<span data-ttu-id="75b12-141">U kunt kiezen welke kolommen u wilt weergeven in de tijdlijn door de knop **Kolommen kiezen te** selecteren.</span><span class="sxs-lookup"><span data-stu-id="75b12-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Kolommen aanpassen](images/filter-customize-columns.png)

<span data-ttu-id="75b12-143">Hier kunt u selecteren welke gegevensset u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="75b12-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="75b12-144">Filteren om alleen technieken of gebeurtenissen weer te geven</span><span class="sxs-lookup"><span data-stu-id="75b12-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="75b12-145">Als u alleen gebeurtenissen of technieken wilt weergeven, **selecteert** u Filters in de apparaattijdlijn en kiest u het gewenste gegevenstype dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="75b12-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Schermafbeelding van filters](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="75b12-147">Zie ook</span><span class="sxs-lookup"><span data-stu-id="75b12-147">See also</span></span>
- [<span data-ttu-id="75b12-148">De lijst Apparaten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="75b12-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="75b12-149">Gebeurtenisvlaggen van Microsoft Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="75b12-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
