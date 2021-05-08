---
title: Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het gebruik Microsoft Teams om uw contractbeheerkanaal te maken met behulp van een Microsoft 365 oplossing.
ms.openlocfilehash: a97f6a77818fc53aa28a5924b97e3c7309d01e3a
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281120"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a><span data-ttu-id="03ac3-104">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="03ac3-104">Step 2.</span></span> <span data-ttu-id="03ac3-105">Gebruik Microsoft Teams om uw contractbeheerkanaal te maken</span><span class="sxs-lookup"><span data-stu-id="03ac3-105">Use Microsoft Teams to create your contract management channel</span></span>

<span data-ttu-id="03ac3-106">Wanneer uw organisatie een oplossing voor contractenbeheer in stelt, hebt u een centrale locatie nodig waar belanghebbenden contracten kunnen bekijken en beheren.</span><span class="sxs-lookup"><span data-stu-id="03ac3-106">When your organization sets up a contracts management solution, you need a central location in which stakeholders can review and manage contracts.</span></span> <span data-ttu-id="03ac3-107">Hiervoor kunt u een [](https://docs.microsoft.com/microsoftteams/) Microsoft Teams voor het instellen van een Teams kanaal en de functies in Teams gebruiken:</span><span class="sxs-lookup"><span data-stu-id="03ac3-107">For this purpose, you can use [Microsoft Teams](https://docs.microsoft.com/microsoftteams/) to set up a Teams channel and use the features in Teams to:</span></span>

- <span data-ttu-id="03ac3-108">**Maak een locatie voor belanghebbenden om eenvoudig alle contracten te zien waarvoor actie moet worden ondernomen.**</span><span class="sxs-lookup"><span data-stu-id="03ac3-108">**Create a location for stakeholders to easily see all contracts that require action.**</span></span> <span data-ttu-id="03ac3-109">In Teams kunt u bijvoorbeeld een  tabblad Contracten maken in het kanaal Contractbeheer waarin leden een handige tegelweergave kunnen zien van alle contracten die moeten worden goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="03ac3-109">For example, in Teams you can create a **Contracts** tab in the Contract Management channel in which members can see a useful tile view of all contracts that need approval.</span></span> <span data-ttu-id="03ac3-110">U kunt de weergave ook zo configureren dat elke 'kaart' de belangrijke gegevens bevat die u belangrijk vindt (zoals *Client,* *Contractant* en *Kostenbedrag).*</span><span class="sxs-lookup"><span data-stu-id="03ac3-110">You can also configure the view so that each "card" lists the important data you care about (such as *Client*, *Contractor*, and *Fee amount*).</span></span>

     ![Tabblad Contracten.](../media/content-understanding/tile-view.png)

- <span data-ttu-id="03ac3-112">**Hebben een locatie voor leden om met elkaar te communiceren en belangrijke gebeurtenissen te zien.**</span><span class="sxs-lookup"><span data-stu-id="03ac3-112">**Have a location for members to interact with each other and see important events.**</span></span> <span data-ttu-id="03ac3-113">In Teams kunt u bijvoorbeeld  het tabblad Berichten gebruiken om gesprekken te voeren, updates op te vragen en acties te bekijken (zoals een lid dat een contract weigert).</span><span class="sxs-lookup"><span data-stu-id="03ac3-113">For example, in Teams, the **Posts** tab can be used to have conversations, get updates, and see actions (such as a member rejecting a contract).</span></span> <span data-ttu-id="03ac3-114">Wanneer er iets is gebeurd (zoals een  nieuw contract dat ter goedkeuring is ingediend), kan het tabblad Berichten niet alleen worden gebruikt om het aan te kondigen, maar ook om een record van het contract bij te houden.</span><span class="sxs-lookup"><span data-stu-id="03ac3-114">When something has happened (such as a new contract submitted for approval), the **Posts** tab can be used not only to announce it, but also to keep a record of it.</span></span> <span data-ttu-id="03ac3-115">En als leden zich abonneren op meldingen, krijgen ze een melding wanneer er een update is.</span><span class="sxs-lookup"><span data-stu-id="03ac3-115">And if members subscribe to notifications, they'll get notified whenever there's an update.</span></span> 

     ![Tabblad Berichten.](../media/content-understanding/posts.png)</br> 

- <span data-ttu-id="03ac3-117">**Hebben een locatie waar leden goedgekeurde contracten kunnen zien om te weten wanneer ze tegen betaling kunnen worden ingediend.**</span><span class="sxs-lookup"><span data-stu-id="03ac3-117">**Have a location for members to see approved contracts to know when they can be submitted for payment.**</span></span> <span data-ttu-id="03ac3-118">In Teams kunt u een <b></b> voor betaling kanaal maken waarin alle contracten worden vermeld die moeten worden verzonden naar betaling.</span><span class="sxs-lookup"><span data-stu-id="03ac3-118">In Teams, you can create a <b>For Payment</b> channel that will list all contracts that will need to be submitted to payment.</span></span> <span data-ttu-id="03ac3-119">U kunt deze oplossing eenvoudig uitbreiden om deze informatie rechtstreeks te schrijven naar een financiële toepassing van derden (bijvoorbeeld Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="03ac3-119">You can easily extend this solution to instead write this information directly to a third-party financial application (for example, Dynamics CRM).</span></span>

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a><span data-ttu-id="03ac3-120">Uw documentbibliotheek SharePoint toevoegen aan het tabblad Contracten</span><span class="sxs-lookup"><span data-stu-id="03ac3-120">Attach your SharePoint document library to the Contracts tab</span></span> 

<span data-ttu-id="03ac3-121">Nadat u een tabblad **Contracten** hebt aangemaakt in uw kanaal Contractenbeheer, moet u uw SharePoint [documentbibliotheek eraan koppelen.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)</span><span class="sxs-lookup"><span data-stu-id="03ac3-121">After you create a **Contracts** tab in your Contracts Management channel, you need to [attach your SharePoint document library to it](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).</span></span> <span data-ttu-id="03ac3-122">De SharePoint documentbibliotheek die u wilt toevoegen, is de bibliotheek waarin u het syntex-documentkennismodel in de vorige sectie hebt SharePoint toegepast.</span><span class="sxs-lookup"><span data-stu-id="03ac3-122">The SharePoint document library you want to attach is the one in which you applied your SharePoint Syntex document understanding model to in the previous section.</span></span>

<span data-ttu-id="03ac3-123">Nadat u de SharePoint documentbibliotheek hebt toegevoegd, kunt u alle geclassificeerde contracten weergeven via een standaardlijstweergave.</span><span class="sxs-lookup"><span data-stu-id="03ac3-123">After you attach the SharePoint document library, you'll be able to view any classified contracts through a default list view.</span></span>

   ![Lijstweergave.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a><span data-ttu-id="03ac3-125">De tegelweergave op het tabblad Contracten aanpassen</span><span class="sxs-lookup"><span data-stu-id="03ac3-125">Customize your Contracts tab tile view</span></span>

<span data-ttu-id="03ac3-126">Hoewel Teams kunt u uw contracten weergeven in een tegelweergave, kunt u deze aanpassen om de contractgegevens weer te geven die u zichtbaar wilt maken op de contractkaart.</span><span class="sxs-lookup"><span data-stu-id="03ac3-126">While Teams lets you view your contracts in a tile view, you might want to customize it to view the contract data you want to make visible in the contract card.</span></span> <span data-ttu-id="03ac3-127">Voor het tabblad  Contracten is het bijvoorbeeld belangrijk dat leden het bedrag van de klant, de contractant en de kosten op de contractkaart zien.</span><span class="sxs-lookup"><span data-stu-id="03ac3-127">For example, for the **Contracts** tab, it is important for members to see the client, contractor, and fee amount on the contract card.</span></span> <span data-ttu-id="03ac3-128">Al deze velden zijn uit elk contract geëxtraheerd via SharePoint Syntex-model dat is toegepast op uw documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="03ac3-128">All of these fields were extracted from each contract through your SharePoint Syntex model that was applied to your document library.</span></span> <span data-ttu-id="03ac3-129">U wilt ook de tegelkoptekstbalk kunnen wijzigen in verschillende kleuren voor elke status, zodat leden eenvoudig kunnen zien waar het contract zich in het goedkeuringsproces vindt.</span><span class="sxs-lookup"><span data-stu-id="03ac3-129">You also want to be able to change the tile header bar to different colors for each status so that members can easily see where the contract is in the approval process.</span></span> <span data-ttu-id="03ac3-130">Alle goedgekeurde contracten hebben bijvoorbeeld een blauwe koptekstbalk.</span><span class="sxs-lookup"><span data-stu-id="03ac3-130">For example, all approved contracts will have a blue header bar.</span></span>

   ![Lijstweergave.](../media/content-understanding/tile.png)

<span data-ttu-id="03ac3-132">Voor de aangepaste tegelweergave die u gebruikt, moet u wijzigingen aanbrengen in het JSON-bestand dat wordt gebruikt om de huidige tegelweergave op te maken.</span><span class="sxs-lookup"><span data-stu-id="03ac3-132">The custom tile view you use requires you to make changes to the JSON file used to format the current tile view.</span></span> <span data-ttu-id="03ac3-133">U kunt verwijzen naar het JSON-bestand dat wordt gebruikt om de kaartweergave te maken door het bestand **ContractCard.jsdownloaden.**</span><span class="sxs-lookup"><span data-stu-id="03ac3-133">You can reference the JSON file used to create the card view by downloading the **ContractCard.json** file.</span></span> <span data-ttu-id="03ac3-134">In de volgende secties ziet u specifieke secties van de code voor functies in de contractkaarten.</span><span class="sxs-lookup"><span data-stu-id="03ac3-134">In the following sections, you'll see specific sections of the code for features that are in the contract cards.</span></span>

<span data-ttu-id="03ac3-135">Als u de JSON-code voor uw weergave wilt zien of wijzigen in uw Teams-kanaal, selecteert u in het kanaal Teams de vervolgkeuzelijst Weergave en selecteert u Huidige weergave opmaken.</span><span class="sxs-lookup"><span data-stu-id="03ac3-135">If you want to see or make changes to the JSON code for your view in your Teams channel, in the Teams channel, select the view drop-down menu, and then select **Format current view**.</span></span>

   ![json-indeling.](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a><span data-ttu-id="03ac3-137">Kaartgrootte en -vorm</span><span class="sxs-lookup"><span data-stu-id="03ac3-137">Card size and shape</span></span>

<span data-ttu-id="03ac3-138">In **hetContractCard.jsbestand** dat u hebt gedownload in het zip-bestand van de verwijzing, bekijkt u de volgende sectie om de code te zien voor de opmaak van de grootte en vorm van de kaart.</span><span class="sxs-lookup"><span data-stu-id="03ac3-138">In the **ContractCard.json** file that you downloaded in the reference zip file, look at the following section to see the code for how the size and shape of the card is formatted.</span></span>

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a><span data-ttu-id="03ac3-139">Contractstatus</span><span class="sxs-lookup"><span data-stu-id="03ac3-139">Contract status</span></span>

<span data-ttu-id="03ac3-140">Met de volgende code kunt u de status van elke titelkaart definiëren.</span><span class="sxs-lookup"><span data-stu-id="03ac3-140">The following code lets you define the status of each title card.</span></span> <span data-ttu-id="03ac3-141">Elke statuswaarde (*Nieuw*, *In revisie*, Goedgekeurd en Geweigerd ) geeft voor elke status een andere kleurcode weer.  </span><span class="sxs-lookup"><span data-stu-id="03ac3-141">Note that each status value (*New*, *In review*, *Approved*, and *Rejected*) will display a different color code for each.</span></span> <span data-ttu-id="03ac3-142">Bekijk in **ContractCard.jsbestand** dat u hebt gedownload de sectie die de status definieert.</span><span class="sxs-lookup"><span data-stu-id="03ac3-142">In the **ContractCard.json** file that you downloaded, look at the section that defines the status.</span></span>

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a><span data-ttu-id="03ac3-143">Geëxtraheerde velden</span><span class="sxs-lookup"><span data-stu-id="03ac3-143">Extracted fields</span></span>

<span data-ttu-id="03ac3-144">Op elke contractkaart worden drie velden weergegeven die zijn geëxtraheerd voor elk contract *(Client,* *Contractant* en *Kostenbedrag).*</span><span class="sxs-lookup"><span data-stu-id="03ac3-144">Each contract card will display three fields that were extracted for each contract (*Client*, *Contractor*, and *Fee Amount*).</span></span> <span data-ttu-id="03ac3-145">Daarnaast wilt u ook de tijd/datum weergeven waarop het bestand is geclassificeerd met het syntex-model SharePoint gebruikt om het te identificeren.</span><span class="sxs-lookup"><span data-stu-id="03ac3-145">Additionally, you also want to display the time/date that the file was classified by the SharePoint Syntex model used to identify it.</span></span> 

<span data-ttu-id="03ac3-146">In het **ContractCard.jsbestand** dat u hebt gedownload, definiëren de volgende secties elk van deze bestanden.</span><span class="sxs-lookup"><span data-stu-id="03ac3-146">In the **ContractCard.json** file that you downloaded, the following sections define each of these.</span></span>

### <a name="client"></a><span data-ttu-id="03ac3-147">Client</span><span class="sxs-lookup"><span data-stu-id="03ac3-147">Client</span></span>

<span data-ttu-id="03ac3-148">In deze sectie wordt beschrijft hoe 'Client' wordt weergegeven op de kaart en wordt de waarde voor het specifieke contract gebruikt.</span><span class="sxs-lookup"><span data-stu-id="03ac3-148">This section defines how "Client" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a><span data-ttu-id="03ac3-149">Aannemer</span><span class="sxs-lookup"><span data-stu-id="03ac3-149">Contractor</span></span>

<span data-ttu-id="03ac3-150">In deze sectie wordt de weergave van de contractant op de kaart beschrijft en wordt de waarde voor het specifieke contract gebruikt.</span><span class="sxs-lookup"><span data-stu-id="03ac3-150">This section defines how the "Contractor" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a><span data-ttu-id="03ac3-151">Kostenbedrag</span><span class="sxs-lookup"><span data-stu-id="03ac3-151">Fee Amount</span></span>

<span data-ttu-id="03ac3-152">In deze sectie wordt beschrijft hoe het bedrag van de kosten wordt weergegeven op de kaart en wordt de waarde voor het specifieke contract gebruikt.</span><span class="sxs-lookup"><span data-stu-id="03ac3-152">This section defines how the "Fee Amount" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a><span data-ttu-id="03ac3-153">Classificatiedatum</span><span class="sxs-lookup"><span data-stu-id="03ac3-153">Classification date</span></span>

<span data-ttu-id="03ac3-154">In deze sectie wordt beschrijft hoe 'Classificatie' wordt weergegeven op de kaart en wordt de waarde voor het specifieke contract gebruikt.</span><span class="sxs-lookup"><span data-stu-id="03ac3-154">This section defines how "Classification" will display on the card, and uses the value for the specific contract.</span></span>

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a><span data-ttu-id="03ac3-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="03ac3-155">Next step</span></span>

[<span data-ttu-id="03ac3-156">Stap 3. Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken</span><span class="sxs-lookup"><span data-stu-id="03ac3-156">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
