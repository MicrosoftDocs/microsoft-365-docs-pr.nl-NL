---
title: Retentie starten als zich een gebeurtenis voordoet
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Meestal kunt u in een oplossing voor recordbeheer een retentielabel configureren om de retentieperiode te starten op basis van een gebeurtenis die u identificeert.
ms.openlocfilehash: 83f1be417b706fdb66b1df71ba351ce16d5ad485
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226621"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="76c32-103">Retentie starten als zich een gebeurtenis voordoet</span><span class="sxs-lookup"><span data-stu-id="76c32-103">Start retention when an event occurs</span></span>

><span data-ttu-id="76c32-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="76c32-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="76c32-105">Wanneer u inhoud behoudt, is de retentieperiode vaak gebaseerd op de leeftijd van de inhoud.</span><span class="sxs-lookup"><span data-stu-id="76c32-105">When you retain content, the retention period is often based on the age of the content.</span></span> <span data-ttu-id="76c32-106">U kunt bijvoorbeeld documenten nog zeven jaar bewaren nadat ze zijn gemaakt en ze vervolgens verwijderen.</span><span class="sxs-lookup"><span data-stu-id="76c32-106">For example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="76c32-107">Maar wanneer u [retentielabels](retention.md#retention-labels) configureert, kunt u een retentieperiode ook baseren op wanneer een specifiek type gebeurtenis plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="76c32-107">But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="76c32-108">De gebeurtenis activeert het begin van de retentieperiode. Voor alle inhoud met een retentielabel dat op dat type gebeurtenis is toegepast, worden de bewaaracties van het label afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="76c32-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="76c32-109">Voorbeelden voor het gebruik van retentiebeleid op basis van gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="76c32-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="76c32-110">**Werknemers die de organisatie verlaten** Stel dat werknemersrecords tien jaar moeten worden bewaard vanaf het moment dat een werknemer de organisatie verlaat.</span><span class="sxs-lookup"><span data-stu-id="76c32-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="76c32-111">Na 10 jaar moeten alle documenten die betrekking hebben op de benoeming, de prestaties en het beëindigen van het dienstverband voor die werknemer worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="76c32-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="76c32-112">De gebeurtenis die de bewaarperiode van tien jaar activeert, is het vertrek van de werknemer.</span><span class="sxs-lookup"><span data-stu-id="76c32-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="76c32-113">**Beëindiging van het contract** Stel dat alle records die betrekking hebben op contracten vijf jaar moeten worden bewaard vanaf het moment dat het contract afloopt.</span><span class="sxs-lookup"><span data-stu-id="76c32-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="76c32-114">De gebeurtenis die de retentieperiode van vijf jaar activeert, is het einde van het contract.</span><span class="sxs-lookup"><span data-stu-id="76c32-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="76c32-115">**Levensduur van product** Uw organisatie heeft mogelijk bewaarvereisten met betrekking tot de laatste productiedatum van producten voor bijvoorbeeld technische specificaties.</span><span class="sxs-lookup"><span data-stu-id="76c32-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="76c32-116">In dit geval is de laatste productiedatum de gebeurtenis die de bewaarperiode activeert.</span><span class="sxs-lookup"><span data-stu-id="76c32-116">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="76c32-p105">Retentie op basis van gebeurtenissen wordt doorgaans gebruikt als onderdeel van een recordbeheerproces. Dit betekent dat:</span><span class="sxs-lookup"><span data-stu-id="76c32-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="76c32-119">Retentielabels op basis van gebeurtenissen markeren items meestal ook als een record als onderdeel van een oplossing voor recordbeheer.</span><span class="sxs-lookup"><span data-stu-id="76c32-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="76c32-120">Zie [Meer informatie over recordbeheer](records-management.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="76c32-121">Een document dat als record is gedeclareerd, maar waarvan de gebeurtenis nog niet heeft plaatsgevonden, wordt voor onbepaalde tijd bewaard (records kunnen niet permanent worden verwijderd) totdat de retentieperiode van dat document wordt veroorzaakt door een gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="76c32-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="76c32-122">Retentielabels op basis van gebeurtenissen zorgen er meestal voor dat aan het einde van de bewaarperiode een beoordeling voor verwijdering wordt geactiveerd, zodat een recordbeheerder de inhoud handmatig kan controleren en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="76c32-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="76c32-123">Zie [Verwijdering van inhoud](disposition.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="76c32-124">Een retentielabel op basis van een gebeurtenis heeft dezelfde mogelijkheden als elk retentielabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76c32-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="76c32-125">Zie [Meer informatie over retentiebeleid en retentielabels](retention.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="76c32-126">De relatie tussen gebeurtenistypen, labels, gebeurtenissen en asset-id’s begrijpen</span><span class="sxs-lookup"><span data-stu-id="76c32-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="76c32-127">Om met succes retentie op basis van gebeurtenissen te gebruiken, is het belangrijk dat u de relatie begrijpt tussen gebeurtenistypen, retentielabels, gebeurtenissen en asset-id’s, zoals weergegeven in de diagrammen en de uitleg die volgt:</span><span class="sxs-lookup"><span data-stu-id="76c32-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagram 1 van 2: Gebeurtenistype, labels, gebeurtenissen en asset-id’s](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagram 2 van 2: Gebeurtenistype, labels, gebeurtenissen en asset-id’s](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="76c32-p109">U maakt retentielabels voor verschillende typen inhoud en koppelt deze vervolgens aan een type gebeurtenis. Retentielabels voor verschillende typen productbestanden en -records zijn bijvoorbeeld gekoppeld aan een gebeurtenistype met de naam Productlevensduur, omdat deze records tien jaar moeten worden bewaard vanaf het moment dat het product het einde van de levensduur bereikt.</span><span class="sxs-lookup"><span data-stu-id="76c32-p109">You create retention labels for different types of content and then associate them with a type of event. For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="76c32-132">Gebruikers (meestal recordbeheerders) passen deze labels toe op inhoud en (voor documenten in SharePoint en OneDrive) voeren een asset-id in voor elk item.</span><span class="sxs-lookup"><span data-stu-id="76c32-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="76c32-133">In dit voorbeeld is de asset-id een productnaam of code die door de organisatie wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="76c32-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="76c32-134">Vervolgens wordt aan de records van elk product een retentielabel toegewezen. Ook heeft elke record een eigenschap die een asset-id bevat.</span><span class="sxs-lookup"><span data-stu-id="76c32-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="76c32-135">Het diagram toont **alle inhoud** voor alle productrecords in een organisatie. Elk item bevat de asset-id van het product waarvan het record is.</span><span class="sxs-lookup"><span data-stu-id="76c32-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="76c32-136">Productlevensduur is het gebeurtenistype; een bepaald product dat het einde van de levensduur bereikt vormt een gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="76c32-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="76c32-137">Wanneer een gebeurtenis van dat type plaatsvindt (in dit geval het einde van de levensduur van een product) maakt u een gebeurtenis die het volgende opgeeft:</span><span class="sxs-lookup"><span data-stu-id="76c32-137">When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="76c32-138">Een asset-id (voor SharePoint- en OneDrive-documenten)</span><span class="sxs-lookup"><span data-stu-id="76c32-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="76c32-p112">Trefwoorden (voor Exchange-items). In dit voorbeeld gebruikt de organisatie een productcode in berichten met productrecords, zodat het trefwoord voor Exchange-items functioneel hetzelfde is als de asset-id voor SharePoint- en OneDrive-documenten.</span><span class="sxs-lookup"><span data-stu-id="76c32-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="76c32-141">De datum waarop de gebeurtenis heeft plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="76c32-141">The date when the event occurred.</span></span> <span data-ttu-id="76c32-142">Deze datum wordt gebruikt als het begin van de bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="76c32-142">This date is used as the start of the retention period.</span></span> <span data-ttu-id="76c32-143">Deze datum kan de huidige datum of een datum in het verleden of de toekomst zijn.</span><span class="sxs-lookup"><span data-stu-id="76c32-143">This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="76c32-144">Nadat u een gebeurtenis hebt gemaakt, wordt die datum van de gebeurtenis gesynchroniseerd met alle inhoud met een bewaarlabel van dat gebeurtenistype en die de opgegeven asset-id of het opgegeven trefwoord bevat.</span><span class="sxs-lookup"><span data-stu-id="76c32-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="76c32-145">Net als bij elk retentielabel kan deze synchronisatie maximaal zeven dagen duren.</span><span class="sxs-lookup"><span data-stu-id="76c32-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="76c32-146">Voor alle items die met rood zijn omcirkeld in het vorige diagram wordt de retentieperiode geactiveerd door deze gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="76c32-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="76c32-147">Met andere woorden: wanneer het einde van de levensduur van dit product wordt bereikt, activeert die gebeurtenis de retentieperiode voor de records van dat product.</span><span class="sxs-lookup"><span data-stu-id="76c32-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="76c32-148">Het is belangrijk om te weten dat **alle inhoud** met een retentielabel van dat gebeurtenistype de retentieperiode heeft die door de gebeurtenis wordt geactiveerd als u geen asset-id of trefwoorden opgeeft voor een gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="76c32-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="76c32-149">Dit betekent dat alle inhoud in het vorige diagram behouden zou blijven.</span><span class="sxs-lookup"><span data-stu-id="76c32-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="76c32-150">Dit is mogelijk niet wat u wilt.</span><span class="sxs-lookup"><span data-stu-id="76c32-150">This might not be what you intend.</span></span>

<span data-ttu-id="76c32-p116">Denk er ten slotte aan dat elk retentielabel eigen bewaarinstellingen heeft. In dit voorbeeld zijn ze allemaal ingesteld op tien jaar, maar het is mogelijk dat een gebeurtenis retentielabels activeert wanneer elk label een andere bewaarperiode heeft.</span><span class="sxs-lookup"><span data-stu-id="76c32-p116">Finally, remember that each retention label has its own retention settings. In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="76c32-153">Retentiebeleid op basis van een gebeurtenis instellen</span><span class="sxs-lookup"><span data-stu-id="76c32-153">How to set up event-driven retention</span></span>

<span data-ttu-id="76c32-154">Werkstroom op hoog niveau voor bewaren op basis van gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="76c32-154">High-level workflow for event-driven retention:</span></span>
  
![Diagram van werkstroom voor het instellen van retentiebeleid op basis van gebeurtenissen](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="76c32-156">Zie [Retentielabels gebruiken voor het beheren van de levenscyclus van documenten die zijn opgeslagen in SharePoint](auto-apply-retention-labels-scenario.md) voor een gedetailleerd scenario waarin beheerde eigenschappen in SharePoint worden gebruikt om automatisch retentielabels toe te passen en om retentie op basis van gebeurtenissen te implementeren.</span><span class="sxs-lookup"><span data-stu-id="76c32-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="76c32-157">Stap 1: maak een label waarvan de retentieperiode is gebaseerd op een gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="76c32-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="76c32-158">Bekijk de instructies voor [Retentielabels maken](./create-apply-retention-labels.md#step-1-create-retention-labels) om uw retentielabel te maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="76c32-158">To create and configure your retention label, see the instructions for [Create retention labels](./create-apply-retention-labels.md#step-1-create-retention-labels).</span></span> <span data-ttu-id="76c32-159">Maar specifiek voor retentie op basis van gebeurtenissen: selecteer op de pagina **Retentie-instellingen definiëren** in de wizard Retentielabel maken na **De retentieperiode starten op basis van** een van de standaardgebeurtenistypen in de vervolgkeuzelijst of maak zelf een gebeurtenistype door **Nieuw type gebeurtenis maken** te selecteren:</span><span class="sxs-lookup"><span data-stu-id="76c32-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![Een nieuw type gebeurtenis maken voor een retentielabel](../media/SPRetention6.png)

<span data-ttu-id="76c32-161">Een gebeurtenistype is gewoon een algemene beschrijving van een gebeurtenis die u wilt koppelen aan een retentielabel.</span><span class="sxs-lookup"><span data-stu-id="76c32-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="76c32-162">De standaardgebeurtenistypen hebben **(gebeurtenistype)** achter hun naam in de vervolgkeuzelijst, zodat u ze eenvoudiger kunt herkennen. U kunt ook gebeurtenistypen bekijken en maken op het tabblad **Recordbeheer** > **Gebeurtenissen** > **Gebeurtenistypen beheren**.</span><span class="sxs-lookup"><span data-stu-id="76c32-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="76c32-163">Voor het bewaren op basis van gebeurtenissen zijn bewaarinstellingen vereist die:</span><span class="sxs-lookup"><span data-stu-id="76c32-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="76c32-164">De inhoud bewaren.</span><span class="sxs-lookup"><span data-stu-id="76c32-164">Retain the content.</span></span>
    
- <span data-ttu-id="76c32-165">De inhoud automatisch verwijderen of een beoordeling van het verwijderen activeren aan het einde van de bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="76c32-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="76c32-166">Retentiebeleid op basis van gebeurtenissen wordt meestal gebruikt voor inhoud die als record wordt gedeclareerd. Dit is dus een goed moment om te controleren of u ook de optie moet selecteren die inhoud markeert als een [record](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="76c32-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="76c32-167">Ga verder met stap 3 als u een bestaand gebeurtenistype gebruikt en geen nieuw gebeurtenistype maakt.</span><span class="sxs-lookup"><span data-stu-id="76c32-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="76c32-168">Nadat u een gebeurtenistype hebt gekozen en het retentielabel opslaat, kan het type gebeurtenis niet worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="76c32-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="76c32-169">Stap 2: maak een nieuw type gebeurtenis voor uw label</span><span class="sxs-lookup"><span data-stu-id="76c32-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="76c32-170">Als u voor de retentie-instellingen de optie **Nieuw gebeurtenistype maken** hebt geselecteerd, voert u naam en beschrijving voor het gebeurtenistype in.</span><span class="sxs-lookup"><span data-stu-id="76c32-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="76c32-171">Selecteer vervolgens **Volgende**, **Verzenden** en **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="76c32-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="76c32-172">Terug op de pagina **Instellingen voor retentie definiëren** kunt u voor **De retentieperiode starten op basis van** in het vervolgkeuzemenu het gebeurtenistype selecteren dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="76c32-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="76c32-173">Stap 3: publiceer labels voor bewaarbeleid op basis van gebeurtenissen of pas deze automatisch toe</span><span class="sxs-lookup"><span data-stu-id="76c32-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="76c32-174">Net als elk retentielabel moet u een label op basis van gebeurtenissen publiceren of automatisch toepassen om dit handmatig of automatisch op inhoud toe te passen:</span><span class="sxs-lookup"><span data-stu-id="76c32-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="76c32-175">Retentielabels maken en deze toepassen in apps</span><span class="sxs-lookup"><span data-stu-id="76c32-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="76c32-176">Een retentielabel automatisch toepassen op inhoud</span><span class="sxs-lookup"><span data-stu-id="76c32-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="76c32-177">Stap 4: voer een asset-id in</span><span class="sxs-lookup"><span data-stu-id="76c32-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="76c32-p119">Nadat een label op basis van een gebeurtenis op inhoud is toegepast, kunt u een asset-id voor elk item invoeren. Uw organisatie kan bijvoorbeeld het volgende gebruiken:</span><span class="sxs-lookup"><span data-stu-id="76c32-p119">After an event-based label is applied to content, you can enter an asset ID for each item. For example, your organization might use:</span></span>
  
- <span data-ttu-id="76c32-180">Productcodes die u kunt gebruiken om alleen inhoud voor een specifiek product te bewaren.</span><span class="sxs-lookup"><span data-stu-id="76c32-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="76c32-181">Projectcodes die u kunt gebruiken om alleen inhoud voor een specifiek project te bewaren.</span><span class="sxs-lookup"><span data-stu-id="76c32-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="76c32-182">Werknemer-id’s die u kunt gebruiken om alleen inhoud voor een bepaalde persoon te bewaren.</span><span class="sxs-lookup"><span data-stu-id="76c32-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="76c32-183">Asset-id is gewoon een andere documenteigenschap die beschikbaar is in SharePoint en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="76c32-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="76c32-184">Uw organisatie gebruikt mogelijk al andere documenteigenschappen en -indelingen om inhoud te classificeren.</span><span class="sxs-lookup"><span data-stu-id="76c32-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="76c32-185">Als dit het geval is, kunt u deze eigenschappen en waarden ook gebruiken wanneer u een gebeurtenis maakt. Zie stap 6 hierna.</span><span class="sxs-lookup"><span data-stu-id="76c32-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="76c32-186">Het belangrijkste punt is dat u een of *eigenschap:waarde*-combinatie in de documenteigenschappen moet gebruiken om dat item te koppelen aan een gebeurtenistype.</span><span class="sxs-lookup"><span data-stu-id="76c32-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Tekstvak om een asset-id in te voeren](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="76c32-188">Stap 5: een gebeurtenis maken</span><span class="sxs-lookup"><span data-stu-id="76c32-188">Step 5: Create an event</span></span>

<span data-ttu-id="76c32-189">Wanneer een bepaald exemplaar van dat type gebeurtenis plaatsvindt, zoals het einde van de levensduur van een product, gaat u naar de pagina **Recordbeheer** > **Gebeurtenissen** in het Microsoft 365-compliancecentrum en selecteert u **+ Maken** om een gebeurtenis te maken.</span><span class="sxs-lookup"><span data-stu-id="76c32-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="76c32-190">U activeert de gebeurtenis door deze hier te maken.</span><span class="sxs-lookup"><span data-stu-id="76c32-190">You trigger the event by creating it, here.</span></span>

![Een gebeurtenis maken om het retentiebeleid te activeren voor labels op basis van gebeurtenissen](../media/create-event-records-management.png)

<span data-ttu-id="76c32-192">Er worden maximaal een miljoen gebeurtenissen per tenant ondersteund.</span><span class="sxs-lookup"><span data-stu-id="76c32-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="76c32-193">Stap 6: kies het type gebeurtenis dat door het label wordt gebruikt in stap 2</span><span class="sxs-lookup"><span data-stu-id="76c32-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="76c32-194">Wanneer u de gebeurtenis maakt, kiest u hetzelfde gebeurtenistype dat is opgegeven in de instellingen voor het retentielabel in stap 2.</span><span class="sxs-lookup"><span data-stu-id="76c32-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="76c32-195">Als u bijvoorbeeld **Productlevensduur** als uw gebeurtenistype voor de labelinstellingen hebt geselecteerd, selecteert u **Productlevensduur** wanneer u de gebeurtenis maakt.</span><span class="sxs-lookup"><span data-stu-id="76c32-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="76c32-196">De retentieperiode wordt alleen geactiveerd voor inhoud met retentielabels voor dit type gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="76c32-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![Optie in Gebeurtenisinstellingen om een gebeurtenistype te kiezen](../media/choose-event-type-records-management.png)

<span data-ttu-id="76c32-198">Selecteer de optie **Bestaande labels kiezen** als u een gebeurtenis wilt maken voor meerdere bewaarlabels met verschillende typen gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="76c32-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="76c32-199">Selecteer vervolgens de labels die zijn geconfigureerd voor de gebeurtenistypen die u aan deze gebeurtenis wilt koppelen.</span><span class="sxs-lookup"><span data-stu-id="76c32-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-query-for-exchange-asset-id-for-sharepoint-and-onedrive"></a><span data-ttu-id="76c32-200">Stap 7: voer trefwoorden of query's in voor Exchange, asset-id voor SharePoint en OneDrive</span><span class="sxs-lookup"><span data-stu-id="76c32-200">Step 7: Enter keywords or query for Exchange, asset ID for SharePoint and OneDrive</span></span>

<span data-ttu-id="76c32-201">Nu beperkt u het bereik van de inhoud.</span><span class="sxs-lookup"><span data-stu-id="76c32-201">Now you narrow the scope of the content.</span></span> <span data-ttu-id="76c32-202">Voor Exchange-inhoud doet u dit door trefwoorden of een query op te geven.</span><span class="sxs-lookup"><span data-stu-id="76c32-202">For Exchange content, you do this by specifying keywords or a query.</span></span> <span data-ttu-id="76c32-203">Voor SharePoint- en OneDrive-inhoud doet u dit door asset-id's op te geven.</span><span class="sxs-lookup"><span data-stu-id="76c32-203">For SharePoint and OneDrive content, you do this by specifying asset IDs.</span></span>

<span data-ttu-id="76c32-204">Gebruik voor Exchange-items trefwoorden of een query die gebruikmaakt van Keyword Query Language (KQL).</span><span class="sxs-lookup"><span data-stu-id="76c32-204">For Exchange items, use keywords or a query that uses Keyword Query Language (KQL).</span></span> <span data-ttu-id="76c32-205">Zie [Naslaginformatie over de syntaxis van KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) voor meer informatie over de syntaxis van de query.</span><span class="sxs-lookup"><span data-stu-id="76c32-205">For more information about the query syntax, see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span> <span data-ttu-id="76c32-206">Zie [Trefwoordquery's en zoekvoorwaarden voor Inhoud zoeken](keyword-queries-and-search-conditions.md)voor meer informatie over de doorzoekbare eigenschappen die u voor Exchange kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="76c32-206">For more information about the searchable properties that you can use for Exchange, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="76c32-207">Retentie van asset-id’s wordt alleen afgedwongen voor inhoud met de opgegeven *eigenschap:waarde*-combinatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-207">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="76c32-208">Als u bijvoorbeeld de eigenschap activa-id gebruikt, typt u `ComplianceAssetID:<value>` in het vak voor activa-id's die in de volgende afbeelding worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="76c32-208">For example, if you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown in the following picture.</span></span>

<span data-ttu-id="76c32-209">Als u geen asset-id hebt ingevoerd, wordt op alle inhoud met labels van dat gebeurtenistype dezelfde bewaardatum toegepast.</span><span class="sxs-lookup"><span data-stu-id="76c32-209">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="76c32-210">Uw organisatie heeft mogelijk andere eigenschappen en id’s toegepast op de documenten die zijn gerelateerd aan dit gebeurtenistype.</span><span class="sxs-lookup"><span data-stu-id="76c32-210">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="76c32-211">Als u bijvoorbeeld de records van een specifiek product moet detecteren, kan de id een combinatie zijn van uw aangepaste eigenschap ProductID en de waarde 'XYZ'.</span><span class="sxs-lookup"><span data-stu-id="76c32-211">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="76c32-212">In dit geval voert u `ProductID:XYZ` in het vak voor asset-id's (zie de volgende afbeelding).</span><span class="sxs-lookup"><span data-stu-id="76c32-212">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>

<span data-ttu-id="76c32-213">Kies ten slotte de datum waarop de gebeurtenis heeft plaatsgevonden; deze datum wordt gebruikt als het begin van de retentieperiode.</span><span class="sxs-lookup"><span data-stu-id="76c32-213">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="76c32-214">Nadat u een gebeurtenis hebt gemaakt, wordt die datum gesynchroniseerd met alle inhoud met een retentielabel van dat gebeurtenistype, die asset-id en die trefwoorden.</span><span class="sxs-lookup"><span data-stu-id="76c32-214">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords or queries.</span></span> <span data-ttu-id="76c32-215">Net als bij elk retentielabel kan deze synchronisatie maximaal zeven dagen duren.</span><span class="sxs-lookup"><span data-stu-id="76c32-215">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Pagina Gebeurtenisinstellingen](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="76c32-217">Nadat u een gebeurtenis hebt gemaakt, worden de bewaarinstellingen van kracht voor de inhoud die al is gelabeld en geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="76c32-217">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="76c32-218">Als het retentielabel aan nieuwe inhoud wordt toegevoegd nadat de gebeurtenis is gemaakt, moet u een nieuwe gebeurtenis met dezelfde details maken.</span><span class="sxs-lookup"><span data-stu-id="76c32-218">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="76c32-219">Als u een gebeurtenis verwijdert, betekent dit niet dat de bewaarinstellingen worden geannuleerd die nu van kracht zijn voor de inhoud die al een label heeft.</span><span class="sxs-lookup"><span data-stu-id="76c32-219">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="76c32-220">Maak een nieuwe gebeurtenis met dezelfde details, maar laat de datum leeg, als u dat wél wilt doen.</span><span class="sxs-lookup"><span data-stu-id="76c32-220">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="76c32-221">Inhoud zoeken gebruiken om alle inhoud met een specifiek label of specifieke activa-id te zoeken</span><span class="sxs-lookup"><span data-stu-id="76c32-221">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="76c32-222">Nadat retentielabels aan inhoud zijn toegewezen, kunt u Inhoud zoeken gebruiken om alle inhoud te zoeken die wordt geclassificeerd met een specifiek retentielabel of die een specifieke activa-id bevat:</span><span class="sxs-lookup"><span data-stu-id="76c32-222">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="76c32-223">Kies de voorwaarde **Retentielabel**, voer de volledige labelnaam of een deel van de labelnaam in en gebruik een jokerteken als u alle inhoud met een specifiek retentielabel wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="76c32-223">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="76c32-224">Voer de eigenschap **ComplianceAssetID** en een waarde in, met de indeling `ComplianceAssetID:<value>` als u alle inhoud met een specifieke activa-id wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="76c32-224">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="76c32-225">Zie [Trefwoordquery's en zoekvoorwaarden voor Inhoud zoeken](keyword-queries-and-search-conditions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-225">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="76c32-226">Gebeurtenissen automatiseren met behulp van PowerShell</span><span class="sxs-lookup"><span data-stu-id="76c32-226">Automate events by using PowerShell</span></span>

<span data-ttu-id="76c32-227">U kunt een PowerShell-script gebruiken om het bewaren op basis van gebeurtenissen vanuit uw zakelijke toepassingen te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="76c32-227">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="76c32-228">De volgende PowerShell-cmdlets zijn beschikbaar voor bewaren op basis van gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="76c32-228">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="76c32-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="76c32-229">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="76c32-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="76c32-230">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="76c32-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="76c32-231">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="76c32-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="76c32-232">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="76c32-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="76c32-233">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="76c32-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="76c32-234">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="76c32-235">Gebeurtenissen automatiseren met behulp van een REST-API</span><span class="sxs-lookup"><span data-stu-id="76c32-235">Automate events by using a REST API</span></span>

<span data-ttu-id="76c32-236">U kunt een REST-API gebruiken om automatisch de gebeurtenissen te maken die het begin van de retentietijd activeren.</span><span class="sxs-lookup"><span data-stu-id="76c32-236">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="76c32-237">Een REST-API is een service-eindpunt dat sets met HTTP-bewerkingen (methoden) ondersteunt die toegang bieden voor het maken/ophalen/bijwerken/verwijderen van de bronnen van de service.</span><span class="sxs-lookup"><span data-stu-id="76c32-237">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="76c32-238">Zie [Onderdelen van een REST-API-aanvraag/-reactie](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-238">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="76c32-239">Met de REST-API van Microsoft 365 kunnen gebeurtenissen worden gemaakt en opgehaald met behulp van de POST- en GET-methoden.</span><span class="sxs-lookup"><span data-stu-id="76c32-239">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="76c32-240">Er zijn twee opties voor het gebruik van de REST-API:</span><span class="sxs-lookup"><span data-stu-id="76c32-240">There are two options for using the REST API:</span></span>

- <span data-ttu-id="76c32-241">**Met Microsoft Power Automate of een soortgelijke toepassing** om een gebeurtenis automatisch te laten plaatsvinden.</span><span class="sxs-lookup"><span data-stu-id="76c32-241">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="76c32-242">Microsoft Power Automate is een orchestrator die verbinding maakt met andere systemen, zodat u geen aangepaste oplossing hoeft te schrijven.</span><span class="sxs-lookup"><span data-stu-id="76c32-242">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="76c32-243">Raadpleeg de [Power Automate-website](https://flow.microsoft.com/nl-NL/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76c32-243">For more information, see the [Power Automate website](https://flow.microsoft.com/nl-NL/).</span></span>

- <span data-ttu-id="76c32-244">**PowerShell of een HTTP-client om de REST-API aan te roepen** om gebeurtenissen te maken met behulp van PowerShell (versie 6 of hoger), die deel uitmaakt van een aangepaste oplossing.</span><span class="sxs-lookup"><span data-stu-id="76c32-244">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="76c32-245">Voordat u de REST-API gebruikt, moet u als globale beheerder de URL bevestigen die moet worden gebruikt voor de aanroep van de retentiegebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="76c32-245">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="76c32-246">Voer hiervoor een GET-aanroep voor een retentiegebeurtenis uit met behulp van de URL van de REST-API:</span><span class="sxs-lookup"><span data-stu-id="76c32-246">To do this, run a GET retention event call by using the REST API URL:</span></span>

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="76c32-247">Controleer de reactiecode.</span><span class="sxs-lookup"><span data-stu-id="76c32-247">Check the response code.</span></span> <span data-ttu-id="76c32-248">Als dit 302 is, moet u de omgeleide URL op uit de eigenschap Locatie van de koptekst van de reactie halen en die URL gebruiken in plaats van `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in de volgende instructies.</span><span class="sxs-lookup"><span data-stu-id="76c32-248">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="76c32-249">De gebeurtenissen die automatisch worden gemaakt, kunnen worden bevestigd door ze te bekijken in het Microsoft 365-compliancecentrum > **Recordbeheer** >  **Gebeurtenissen**.</span><span class="sxs-lookup"><span data-stu-id="76c32-249">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="76c32-250">Microsoft Power Automate gebruiken om de gebeurtenis te maken</span><span class="sxs-lookup"><span data-stu-id="76c32-250">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="76c32-251">Maak een stroom die een gebeurtenis maakt met behulp van de REST-API van Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="76c32-251">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Flow gebruiken om een gebeurtenis te maken](../media/automate-event-driven-retention-flow-1.png)

![Flow gebruiken om de REST-API aan te roepen](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="76c32-254">Een gebeurtenis maken</span><span class="sxs-lookup"><span data-stu-id="76c32-254">Create an event</span></span>

<span data-ttu-id="76c32-255">Voorbeeldcode voor het aanroepen van de REST-API:</span><span class="sxs-lookup"><span data-stu-id="76c32-255">Sample code to call the REST API:</span></span>

- <span data-ttu-id="76c32-256">**Methode**: POST</span><span class="sxs-lookup"><span data-stu-id="76c32-256">**Method**: POST</span></span>
- <span data-ttu-id="76c32-257">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="76c32-257">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="76c32-258">**Kopteksten**: Sleutel = Content-Type, Waarde = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="76c32-258">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="76c32-259">**Hoofdtekst**:</span><span class="sxs-lookup"><span data-stu-id="76c32-259">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="76c32-260">**Verificatie**: Basic</span><span class="sxs-lookup"><span data-stu-id="76c32-260">**Authentication**: Basic</span></span>
- <span data-ttu-id="76c32-261">**Gebruikersnaam**: 'Complianceuser'</span><span class="sxs-lookup"><span data-stu-id="76c32-261">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="76c32-262">**Wachtwoord**: 'Compliancepassword'</span><span class="sxs-lookup"><span data-stu-id="76c32-262">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="76c32-263">Beschikbare parameters</span><span class="sxs-lookup"><span data-stu-id="76c32-263">Available parameters</span></span>


|<span data-ttu-id="76c32-264">Parameters</span><span class="sxs-lookup"><span data-stu-id="76c32-264">Parameters</span></span>|<span data-ttu-id="76c32-265">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="76c32-265">Description</span></span>|<span data-ttu-id="76c32-266">Opmerkingen</span><span class="sxs-lookup"><span data-stu-id="76c32-266">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="76c32-267"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="76c32-267"><d:Name></d:Name></span></span>|<span data-ttu-id="76c32-268">Geef een unieke naam op voor de gebeurtenis,</span><span class="sxs-lookup"><span data-stu-id="76c32-268">Provide a unique name for the event,</span></span>|<span data-ttu-id="76c32-269">Kan geen volgspaties of de volgende tekens bevatten: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="76c32-269">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="76c32-270">, : ;</span><span class="sxs-lookup"><span data-stu-id="76c32-270">, : ;</span></span>|
|<span data-ttu-id="76c32-271"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="76c32-271"><d:EventType></d:EventType></span></span>|<span data-ttu-id="76c32-272">Voer de naam (of Guid) van het gebeurtenistype in,</span><span class="sxs-lookup"><span data-stu-id="76c32-272">Enter event type name (or Guid),</span></span>|<span data-ttu-id="76c32-p137">Voorbeeld: 'Ontslag van een werknemer'. Het type gebeurtenis moet zijn gekoppeld aan een retentielabel.</span><span class="sxs-lookup"><span data-stu-id="76c32-p137">Example: "Employee termination". Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="76c32-275"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="76c32-275"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="76c32-276">Voer 'ComplianceAssetId:' + werknemer-id in</span><span class="sxs-lookup"><span data-stu-id="76c32-276">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="76c32-277">Voorbeeld: 'ComplianceAssetId:12345'</span><span class="sxs-lookup"><span data-stu-id="76c32-277">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="76c32-278"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="76c32-278"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="76c32-279">Datum en tijd van gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="76c32-279">Event Date and Time</span></span>|<span data-ttu-id="76c32-280">Notatie: yyyy-MM-ddTHH:mm:ssZ, voorbeeld: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="76c32-280">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="76c32-281">Antwoordcodes</span><span class="sxs-lookup"><span data-stu-id="76c32-281">Response codes</span></span>

| <span data-ttu-id="76c32-282">Antwoordcode</span><span class="sxs-lookup"><span data-stu-id="76c32-282">Response Code</span></span> | <span data-ttu-id="76c32-283">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="76c32-283">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="76c32-284">302</span><span class="sxs-lookup"><span data-stu-id="76c32-284">302</span></span>               | <span data-ttu-id="76c32-285">Redirect</span><span class="sxs-lookup"><span data-stu-id="76c32-285">Redirect</span></span>              |
| <span data-ttu-id="76c32-286">201</span><span class="sxs-lookup"><span data-stu-id="76c32-286">201</span></span>               | <span data-ttu-id="76c32-287">Gemaakt</span><span class="sxs-lookup"><span data-stu-id="76c32-287">Created</span></span>               |
| <span data-ttu-id="76c32-288">403</span><span class="sxs-lookup"><span data-stu-id="76c32-288">403</span></span>               | <span data-ttu-id="76c32-289">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-289">Authorization Failed</span></span>  |
| <span data-ttu-id="76c32-290">401</span><span class="sxs-lookup"><span data-stu-id="76c32-290">401</span></span>               | <span data-ttu-id="76c32-291">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-291">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="76c32-292">Gebeurtenissen ophalen op basis van een tijdsbereik</span><span class="sxs-lookup"><span data-stu-id="76c32-292">Get events based on a time range</span></span>

- <span data-ttu-id="76c32-293">**Methode**: GET</span><span class="sxs-lookup"><span data-stu-id="76c32-293">**Method**: GET</span></span>

- <span data-ttu-id="76c32-294">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="76c32-294">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="76c32-295">**Kopteksten**: Sleutel = Content-Type, Waarde = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="76c32-295">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="76c32-296">**Verificatie**: Basic</span><span class="sxs-lookup"><span data-stu-id="76c32-296">**Authentication**: Basic</span></span>

- <span data-ttu-id="76c32-297">**Gebruikersnaam**: 'Complianceuser'</span><span class="sxs-lookup"><span data-stu-id="76c32-297">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="76c32-298">**Wachtwoord**: 'Compliancepassword'</span><span class="sxs-lookup"><span data-stu-id="76c32-298">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="76c32-299">Antwoordcodes</span><span class="sxs-lookup"><span data-stu-id="76c32-299">Response codes</span></span>

| <span data-ttu-id="76c32-300">Antwoordcode</span><span class="sxs-lookup"><span data-stu-id="76c32-300">Response Code</span></span> | <span data-ttu-id="76c32-301">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="76c32-301">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="76c32-302">200</span><span class="sxs-lookup"><span data-stu-id="76c32-302">200</span></span>               | <span data-ttu-id="76c32-303">OK, een lijst met gebeurtenissen in atom+ xml</span><span class="sxs-lookup"><span data-stu-id="76c32-303">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="76c32-304">404</span><span class="sxs-lookup"><span data-stu-id="76c32-304">404</span></span>               | <span data-ttu-id="76c32-305">Niet gevonden</span><span class="sxs-lookup"><span data-stu-id="76c32-305">Not found</span></span>                         |
| <span data-ttu-id="76c32-306">302</span><span class="sxs-lookup"><span data-stu-id="76c32-306">302</span></span>               | <span data-ttu-id="76c32-307">Redirect</span><span class="sxs-lookup"><span data-stu-id="76c32-307">Redirect</span></span>                          |
| <span data-ttu-id="76c32-308">401</span><span class="sxs-lookup"><span data-stu-id="76c32-308">401</span></span>               | <span data-ttu-id="76c32-309">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-309">Authorization Failed</span></span>              |
| <span data-ttu-id="76c32-310">403</span><span class="sxs-lookup"><span data-stu-id="76c32-310">403</span></span>               | <span data-ttu-id="76c32-311">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-311">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="76c32-312">Een gebeurtenis ophalen op basis van id</span><span class="sxs-lookup"><span data-stu-id="76c32-312">Get an event by ID</span></span>

- <span data-ttu-id="76c32-313">**Methode**: GET</span><span class="sxs-lookup"><span data-stu-id="76c32-313">**Method**: GET</span></span>

- <span data-ttu-id="76c32-314">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="76c32-314">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="76c32-315">**Kopteksten**: Sleutel = Content-Type, Waarde = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="76c32-315">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="76c32-316">**Verificatie**: Basic</span><span class="sxs-lookup"><span data-stu-id="76c32-316">**Authentication**: Basic</span></span>

- <span data-ttu-id="76c32-317">**Gebruikersnaam**: 'Complianceuser'</span><span class="sxs-lookup"><span data-stu-id="76c32-317">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="76c32-318">**Wachtwoord**: 'Compliancepassword'</span><span class="sxs-lookup"><span data-stu-id="76c32-318">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="76c32-319">Antwoordcodes</span><span class="sxs-lookup"><span data-stu-id="76c32-319">Response codes</span></span>

| <span data-ttu-id="76c32-320">Antwoordcode</span><span class="sxs-lookup"><span data-stu-id="76c32-320">Response Code</span></span> | <span data-ttu-id="76c32-321">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="76c32-321">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="76c32-322">200</span><span class="sxs-lookup"><span data-stu-id="76c32-322">200</span></span>               | <span data-ttu-id="76c32-323">OK, de hoofdtekst van de reactie bevat de gebeurtenis in atom+xml</span><span class="sxs-lookup"><span data-stu-id="76c32-323">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="76c32-324">404</span><span class="sxs-lookup"><span data-stu-id="76c32-324">404</span></span>               | <span data-ttu-id="76c32-325">Niet gevonden</span><span class="sxs-lookup"><span data-stu-id="76c32-325">Not found</span></span>                                            |
| <span data-ttu-id="76c32-326">302</span><span class="sxs-lookup"><span data-stu-id="76c32-326">302</span></span>               | <span data-ttu-id="76c32-327">Redirect</span><span class="sxs-lookup"><span data-stu-id="76c32-327">Redirect</span></span>                                             |
| <span data-ttu-id="76c32-328">401</span><span class="sxs-lookup"><span data-stu-id="76c32-328">401</span></span>               | <span data-ttu-id="76c32-329">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-329">Authorization Failed</span></span>                                 |
| <span data-ttu-id="76c32-330">403</span><span class="sxs-lookup"><span data-stu-id="76c32-330">403</span></span>               | <span data-ttu-id="76c32-331">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-331">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="76c32-332">Een gebeurtenis ophalen op basis van de naam</span><span class="sxs-lookup"><span data-stu-id="76c32-332">Get an event by name</span></span>

- <span data-ttu-id="76c32-333">**Methode**: GET</span><span class="sxs-lookup"><span data-stu-id="76c32-333">**Method**: GET</span></span>

- <span data-ttu-id="76c32-334">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="76c32-334">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="76c32-335">**Kopteksten**: Sleutel = Content-Type, Waarde = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="76c32-335">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="76c32-336">**Verificatie**: Basic</span><span class="sxs-lookup"><span data-stu-id="76c32-336">**Authentication**: Basic</span></span>

- <span data-ttu-id="76c32-337">**Gebruikersnaam**: 'Complianceuser'</span><span class="sxs-lookup"><span data-stu-id="76c32-337">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="76c32-338">**Wachtwoord**: 'Compliancepassword'</span><span class="sxs-lookup"><span data-stu-id="76c32-338">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="76c32-339">Antwoordcodes</span><span class="sxs-lookup"><span data-stu-id="76c32-339">Response codes</span></span>

| <span data-ttu-id="76c32-340">Antwoordcode</span><span class="sxs-lookup"><span data-stu-id="76c32-340">Response Code</span></span> | <span data-ttu-id="76c32-341">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="76c32-341">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="76c32-342">200</span><span class="sxs-lookup"><span data-stu-id="76c32-342">200</span></span>               | <span data-ttu-id="76c32-343">OK, de hoofdtekst van de reactie bevat de gebeurtenis in atom+xml</span><span class="sxs-lookup"><span data-stu-id="76c32-343">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="76c32-344">404</span><span class="sxs-lookup"><span data-stu-id="76c32-344">404</span></span>               | <span data-ttu-id="76c32-345">Niet gevonden</span><span class="sxs-lookup"><span data-stu-id="76c32-345">Not found</span></span>                                            |
| <span data-ttu-id="76c32-346">302</span><span class="sxs-lookup"><span data-stu-id="76c32-346">302</span></span>               | <span data-ttu-id="76c32-347">Redirect</span><span class="sxs-lookup"><span data-stu-id="76c32-347">Redirect</span></span>                                             |
| <span data-ttu-id="76c32-348">401</span><span class="sxs-lookup"><span data-stu-id="76c32-348">401</span></span>               | <span data-ttu-id="76c32-349">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-349">Authorization Failed</span></span>                                 |
| <span data-ttu-id="76c32-350">403</span><span class="sxs-lookup"><span data-stu-id="76c32-350">403</span></span>               | <span data-ttu-id="76c32-351">Autorisatie mislukt</span><span class="sxs-lookup"><span data-stu-id="76c32-351">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="76c32-352">PowerShell of een HTTP-client gebruiken om de gebeurtenis te maken</span><span class="sxs-lookup"><span data-stu-id="76c32-352">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="76c32-353">U moet minimaal PowerShell-versie 6 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="76c32-353">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="76c32-354">Voer in een PowerShell-sessie het volgende script uit :</span><span class="sxs-lookup"><span data-stu-id="76c32-354">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```
