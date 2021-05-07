---
title: Recordversies gebruiken om records bij te werken die zijn opgeslagen in SharePoint of OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Leer meer over records om u te helpen een oplossing voor recordbeheer te implementeren in Microsoft 365.
ms.openlocfilehash: 5c828f06f2ce9e2bd18869f897f1f372c1a62f21
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "52162507"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="8637b-103">Versiebeheer van records gebruiken om records bij te werken die zijn opgeslagen in SharePoint of OneDrive</span><span class="sxs-lookup"><span data-stu-id="8637b-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="8637b-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="8637b-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

>[!NOTE] 
> <span data-ttu-id="8637b-105">Aangezien wettelijke records niet kunnen worden bewerkt, is versiebeheer van records niet beschikbaar voor wettelijke records.</span><span class="sxs-lookup"><span data-stu-id="8637b-105">Because regulatory records block editing, record versioning is not available for regulatory records.</span></span>

<span data-ttu-id="8637b-106">De mogelijkheid om een document als een [record](records-management.md#records) te markeren en acties te beperken die op de record kunnen worden uitgevoerd, is een essentieel doel voor elke oplossing voor recordbeheer.</span><span class="sxs-lookup"><span data-stu-id="8637b-106">The ability to mark a document as a [record](records-management.md#records) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="8637b-107">Er kan echter ook samenwerking nodig zijn voor mensen om volgende versies te kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="8637b-107">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="8637b-108">U kunt bijvoorbeeld een verkoopcontract als een record markeren, maar moet het contract vervolgens bijwerken met nieuwe voorwaarden en de nieuwste versie markeren als een nieuwe record terwijl u nog steeds de vorige recordversie behoudt.</span><span class="sxs-lookup"><span data-stu-id="8637b-108">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="8637b-109">Voor dit soort scenario's bieden SharePoint en OneDrive ondersteuning voor *versiebeheer van records*.</span><span class="sxs-lookup"><span data-stu-id="8637b-109">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="8637b-110">OneNote-notitieblokmappen bieden geen ondersteuning voor versiebeheer van records.</span><span class="sxs-lookup"><span data-stu-id="8637b-110">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="8637b-111">Als u versiebeheer van records wilt gebruiken, moet u eerst [het document labelen en dit als een record markeren](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="8637b-111">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="8637b-112">Op dit punt wordt een documenteigenschap genaamd *Recordstatus* naast het retentielabel weergegeven en is de initiële recordstatus **Vergrendeld**.</span><span class="sxs-lookup"><span data-stu-id="8637b-112">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="8637b-113">U kunt nu het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="8637b-113">You can now do the following things:</span></span>

  - <span data-ttu-id="8637b-114">**Afzonderlijke versies van het document voortdurend bewerken en bewaren als records door de eigenschap Recordstatus te ontgrendelen en te vergrendelen.**</span><span class="sxs-lookup"><span data-stu-id="8637b-114">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="8637b-115">Alleen wanneer de eigenschap **Recordstatus** is ingesteld op **Vergrendeld**, wordt er een nieuwe versie van de record bewaard.</span><span class="sxs-lookup"><span data-stu-id="8637b-115">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="8637b-116">Deze schakeling tussen vergrendeld en ontgrendeld verkleint het risico dat onnodige versies en exemplaren van het document worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="8637b-116">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="8637b-117">**De records automatisch laten opslaan in een in-place recordopslagplaats in de siteverzameling.**</span><span class="sxs-lookup"><span data-stu-id="8637b-117">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="8637b-118">Elke siteverzameling in SharePoint en OneDrive bewaart de inhoud in de opslagbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="8637b-118">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="8637b-119">Recordversies worden opgeslagen in de map Records in deze bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="8637b-119">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="8637b-120">**Een actueel document onderhouden dat alle versies bevat.**</span><span class="sxs-lookup"><span data-stu-id="8637b-120">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="8637b-121">In elk SharePoint- en OneDrive-document is standaard een versiegeschiedenis beschikbaar in het itemmenu.</span><span class="sxs-lookup"><span data-stu-id="8637b-121">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="8637b-122">In deze versiegeschiedenis kunt u gemakkelijk zien welke versies records zijn en kunt u deze documenten bekijken.</span><span class="sxs-lookup"><span data-stu-id="8637b-122">In this version history, you can easily see which versions are records and view those documents.</span></span>

> [!TIP]
> <span data-ttu-id="8637b-123">Wanneer u versiebeheer van records gebruikt met een retentielabel dat een verwijderactie heeft, kunt u overwegen de retentie-instelling **Start de retentieperiode op basis van:** te configureren als **Wanneer items waren gelabeld**.</span><span class="sxs-lookup"><span data-stu-id="8637b-123">When you use record versioning with a retention label that has a delete action, consider configuring the retention setting **Start the retention period based on:** to be **When items were labeled**.</span></span> <span data-ttu-id="8637b-124">Met deze labelinstelling wordt het begin van de retentieperiode opnieuw ingesteld voor elke nieuwe recordversie, wat verzekert dat oudere versies worden verwijderd vóór nieuwere versies.</span><span class="sxs-lookup"><span data-stu-id="8637b-124">With this label setting, the start of the retention period is reset for each new record version, which ensures that older versions will be deleted before newer versions.</span></span>

<span data-ttu-id="8637b-125">Versiebeheer van records is automatisch beschikbaar voor elk document met een retentielabel dat het item als een record markeert.</span><span class="sxs-lookup"><span data-stu-id="8637b-125">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="8637b-126">Wanneer een gebruiker de documenteigenschappen bekijkt via het detailvenster, kan deze de **Recordstatus** wijzigen van **Vergrendeld** naar **Ontgrendeld**.</span><span class="sxs-lookup"><span data-stu-id="8637b-126">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="8637b-127">Met deze actie wordt een record gemaakt in de map Records in de opslagbibliotheek, waar deze voor de rest van de retentieperiode blijft staan.</span><span class="sxs-lookup"><span data-stu-id="8637b-127">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="8637b-128">Terwijl het document is ontgrendeld, kan elke gebruiker met standaard bewerkingsmachtigingen het bestand bewerken.</span><span class="sxs-lookup"><span data-stu-id="8637b-128">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="8637b-129">Gebruikers kunnen het bestand echter niet verwijderen, omdat het nog steeds een record is.</span><span class="sxs-lookup"><span data-stu-id="8637b-129">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="8637b-130">Wanneer het bewerken is voltooid, kan een gebruiker de **Recordstatus** vervolgens wijzigen van **Ontgrendeld** naar **Vergrendeld**, waardoor verdere bewerkingen worden voorkomen in deze status.</span><span class="sxs-lookup"><span data-stu-id="8637b-130">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Eigenschap Recordstatus op document gelabeld als record](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="8637b-132">Een record vergrendelen en ontgrendelen</span><span class="sxs-lookup"><span data-stu-id="8637b-132">Locking and unlocking a record</span></span>

<span data-ttu-id="8637b-133">Nadat een retentielabel dat inhoud als een record markeert op een document is toegepast, kan elke gebruiker met bijdragemachtigingen of een beperkter machtigingsniveau een record ontgrendelen of een ontgrendelde record vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="8637b-133">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Recordstatus toont dat recorddocument is ontgrendeld](../media/recordversioning9.png)

<span data-ttu-id="8637b-135">Wanneer een gebruiker een record ontgrendelt, vinden de volgende acties plaats:</span><span class="sxs-lookup"><span data-stu-id="8637b-135">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="8637b-136">Als de huidige siteverzameling geen opslagbibliotheek heeft, wordt er een gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8637b-136">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="8637b-137">Als de opslagbibliotheek geen map Records heeft, wordt er een gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8637b-137">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="8637b-138">Met de actie **Kopiëren naar** wordt de recentste versie van het document naar de map Records gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="8637b-138">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="8637b-139">Met de actie **Kopiëren naar** wordt alleen de recentste versie gekopieerd, en geen eerdere versies.</span><span class="sxs-lookup"><span data-stu-id="8637b-139">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="8637b-140">Dit gekopieerde document wordt nu beschouwd als een recordversie van het document, en de bestandsnaam heeft de indeling \[Titel GUID Versie\#\]</span><span class="sxs-lookup"><span data-stu-id="8637b-140">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="8637b-141">De kopie die in de map Records is gemaakt, wordt toegevoegd aan de versiegeschiedenis van het oorspronkelijke document, en deze versie toont het woord **Record** in het opmerkingenveld.</span><span class="sxs-lookup"><span data-stu-id="8637b-141">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="8637b-142">Het oorspronkelijke document is een nieuwe versie die wel kan worden bewerkt, maar niet kan worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8637b-142">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="8637b-143">De documentbibliotheekkolom **Item is een record** toont nog steeds de waarde **Ja** omdat het document nog steeds een record is, hoewel het nu kan worden bewerkt.</span><span class="sxs-lookup"><span data-stu-id="8637b-143">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="8637b-144">Wanneer een gebruiker een record vergrendelt, kan het oorspronkelijke document weer niet worden bewerkt.</span><span class="sxs-lookup"><span data-stu-id="8637b-144">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="8637b-145">Het is echter de actie van het ontgrendelen van een record die een versie kopieert naar de map Records in de opslagbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="8637b-145">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="8637b-146">Recordversies</span><span class="sxs-lookup"><span data-stu-id="8637b-146">Record versions</span></span>

<span data-ttu-id="8637b-147">Telkens wanneer een gebruiker een record ontgrendelt, wordt de recentste versie gekopieerd naar de opslagbibliotheek. Die versie bevat de waarde **Record** in het veld **Opmerkingen** van de versiegeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="8637b-147">Each time a user unlocks a record, the latest version is copied to the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Record weergegeven in de opslagbibliotheek](../media/recordversioning10.png)

<span data-ttu-id="8637b-149">Als u de versiegeschiedenis wilt bekijken, selecteert u een document in de documentbibliotheek en klikt u op **Versiegeschiedenis** in het itemmenu.</span><span class="sxs-lookup"><span data-stu-id="8637b-149">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="8637b-150">Waar records worden opgeslagen</span><span class="sxs-lookup"><span data-stu-id="8637b-150">Where records are stored</span></span>

<span data-ttu-id="8637b-151">Records worden opgeslagen in de map Records in de opslagbibliotheek op de site op het hoogste niveau in de siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="8637b-151">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="8637b-152">Kies **Site-inhoud** \> **Opslagbibliotheek** in het linkernavigatievenster op de site op het hoogste niveau.</span><span class="sxs-lookup"><span data-stu-id="8637b-152">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Opslagbibliotheek](../media/recordversioning11.png)

<br/><br/>

![De map Records in de opslagbibliotheek](../media/recordversioning12.png)

<span data-ttu-id="8637b-155">Zie [Hoe retentie werkt voor SharePoint en OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive) voor meer informatie over hoe de opslagbibliotheek werkt.</span><span class="sxs-lookup"><span data-stu-id="8637b-155">For more information about how the Preservation Hold library works, see [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="8637b-156">Het auditlogboek doorzoeken op gebeurtenissen voor versiebeheer van records</span><span class="sxs-lookup"><span data-stu-id="8637b-156">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="8637b-157">De acties van het vergrendelen en ontgrendelen van records worden geregistreerd in het auditlogboek.</span><span class="sxs-lookup"><span data-stu-id="8637b-157">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="8637b-158">Vanuit **Activiteiten van bestanden en pagina's** selecteert u **Recordstatus gewijzigd in vergrendeld** en **Recordstatus gewijzigd in ontgrendeld**.</span><span class="sxs-lookup"><span data-stu-id="8637b-158">From **File and page activities**, select **Changed record status to locked** and **Changed record status to unlocked**.</span></span>

<span data-ttu-id="8637b-159">Zie [Het auditlogboek doorzoeken in het beveiligings- en compliancecentrum](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities) voor meer informatie over het zoeken naar deze gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="8637b-159">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8637b-160">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8637b-160">Next steps</span></span>

<span data-ttu-id="8637b-161">Zie [Veelvoorkomende scenario's voor recordbeheer](get-started-with-records-management.md#common-scenarios-for-records-management) voor andere scenario's die worden ondersteund door recordbeheer.</span><span class="sxs-lookup"><span data-stu-id="8637b-161">For other scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>