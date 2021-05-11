---
title: Stap 3. Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken
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
description: Informatie over het gebruik van Power Automate om uw stroom te maken om uw contracten te verwerken met behulp van een Microsoft 365 oplossing.
ms.openlocfilehash: d9892110d6aebd3eaae6fbc21d453b7eb14d7f7e
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281141"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a><span data-ttu-id="09d22-104">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="09d22-104">Step 3.</span></span> <span data-ttu-id="09d22-105">Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken</span><span class="sxs-lookup"><span data-stu-id="09d22-105">Use Power Automate to create your flow to process your contracts</span></span>

<span data-ttu-id="09d22-106">U hebt uw contractbeheerkanaal gemaakt en uw documentbibliotheek SharePoint toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="09d22-106">You've created your Contract Management channel and have attached your SharePoint document library.</span></span> <span data-ttu-id="09d22-107">De volgende stap is het maken van een Power Automate om uw contracten te verwerken die door SharePoint Syntex-model worden geïdentificeerd en classificeert.</span><span class="sxs-lookup"><span data-stu-id="09d22-107">The next step is to create a Power Automate flow to process your contracts that your SharePoint Syntex model identifies and classifies.</span></span> <span data-ttu-id="09d22-108">U kunt deze stap doen door [een Power Automate te maken in uw SharePoint documentbibliotheek.](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)</span><span class="sxs-lookup"><span data-stu-id="09d22-108">You can do this step by [creating a Power Automate flow in your SharePoint document library](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span></span>

<span data-ttu-id="09d22-109">Voor uw oplossing voor contractenbeheer wilt u een Power Automate maken om de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="09d22-109">For your contracts management solution, you want to create a Power Automate flow to do the following actions:</span></span>

-  <span data-ttu-id="09d22-110">Nadat een contract is geclassificeerd door uw SharePoint Syntex-model, wijzigt u de contractstatus **in In review.**</span><span class="sxs-lookup"><span data-stu-id="09d22-110">After a contract has been classified by your SharePoint Syntex model, change the contract status to **In review**.</span></span>
- <span data-ttu-id="09d22-111">Het contract wordt vervolgens beoordeeld en wordt goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="09d22-111">The contract is then reviewed and is either approved or rejected.</span></span>
- <span data-ttu-id="09d22-112">Voor goedgekeurde contracten worden de contractgegevens geplaatst op een tabblad voor betalingsverwerking.</span><span class="sxs-lookup"><span data-stu-id="09d22-112">For approved contracts, the contract information is posted to a tab for payment processing.</span></span>
- <span data-ttu-id="09d22-113">Voor geweigerde contracten wordt het team op de hoogte gesteld voor verdere analyse.</span><span class="sxs-lookup"><span data-stu-id="09d22-113">For rejected contracts, the team is notified for further analysis.</span></span> 

<span data-ttu-id="09d22-114">In het volgende diagram ziet u de Power Automate voor de oplossing voor contractbeheer.</span><span class="sxs-lookup"><span data-stu-id="09d22-114">The following diagram shows the Power Automate flow for the contract management solution.</span></span>

![Flow diagram met de hele oplossing.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a><span data-ttu-id="09d22-116">Uw contract voorbereiden voor controle</span><span class="sxs-lookup"><span data-stu-id="09d22-116">Prepare your contract for review</span></span>

<span data-ttu-id="09d22-117">Wanneer een contract wordt geïdentificeerd en geclassificeerd door uw SharePoint Syntex-documentkennismodel, verandert de Power Automate de status eerst in 'In review'.</span><span class="sxs-lookup"><span data-stu-id="09d22-117">When a contract is identified and classified by your SharePoint Syntex document understanding model, the Power Automate flow will first change the status to "In review."</span></span>

![Status bijwerken.](../media/content-understanding/flow-overview.png)

<span data-ttu-id="09d22-119">Nadat u het bestand hebt uitchecken, wijzigt u de statuswaarde in 'Ter controle'.</span><span class="sxs-lookup"><span data-stu-id="09d22-119">After checking out the file, change the status value to "In review."</span></span>

![In revisiestatus.](../media/content-understanding/in-review.png)

<span data-ttu-id="09d22-121">De volgende stap is het maken van een adaptieve kaart waarin wordt aangegeven dat het contract wacht op revisie en deze post naar het kanaal Contractbeheer.</span><span class="sxs-lookup"><span data-stu-id="09d22-121">The next step is to create an adaptive card stating that the contract is waiting for review and posting it to the Contract Management channel.</span></span>

![Contractbeoordelingsbericht.](../media/content-understanding/contract-approval-post.png)


![Maak adaptieve kaart voor controle.](../media/content-understanding/adaptive-card.png)

<span data-ttu-id="09d22-124">De volgende code is de JSON die voor deze stap in de Power Automate wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="09d22-124">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional"></a><span data-ttu-id="09d22-125">Voorwaardelijk</span><span class="sxs-lookup"><span data-stu-id="09d22-125">Conditional</span></span>

<span data-ttu-id="09d22-126">In uw stroom moet u vervolgens een voorwaarde maken waarin uw contract wordt goedgekeurd of geweigerd.</span><span class="sxs-lookup"><span data-stu-id="09d22-126">In your flow, next you need to create a condition in which your contract will be either  approved or rejected.</span></span>

![Voorwaardelijk.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a><span data-ttu-id="09d22-128">Als het contract is goedgekeurd</span><span class="sxs-lookup"><span data-stu-id="09d22-128">If the contract is approved</span></span>

<span data-ttu-id="09d22-129">Wanneer een contract is goedgekeurd, treden de volgende dingen op:</span><span class="sxs-lookup"><span data-stu-id="09d22-129">When a contract has been approved, the following things occur:</span></span>

- <span data-ttu-id="09d22-130">Op het **tabblad** Contracten wordt de status op de contractkaart gewijzigd in **Goedgekeurd.**</span><span class="sxs-lookup"><span data-stu-id="09d22-130">On the **Contracts** tab, the status in the contract card will change to **Approved**.</span></span>

   ![Kaartstatus goedgekeurd.](../media/content-understanding/approved-contracts-tab.png)

- <span data-ttu-id="09d22-132">In uw stroom wordt de status gewijzigd in 'Goedgekeurd'.</span><span class="sxs-lookup"><span data-stu-id="09d22-132">In your flow, the status is changed to "Approved."</span></span>

   ![Flow status goedgekeurd.](../media/content-understanding/status-approved.png)

- <span data-ttu-id="09d22-134">In deze oplossing worden de contractgegevens  toegevoegd aan het tabblad Voor uitbetaling, zodat de uitbetalingen kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="09d22-134">In this solution, the contract data will be added to the **For Payout** tab so that the payouts can be managed.</span></span> <span data-ttu-id="09d22-135">Dit proces kan worden uitgebreid zodat de stroom de contracten voor betaling kan indienen door een financiële toepassing van derden (bijvoorbeeld Dynamics CRM).</span><span class="sxs-lookup"><span data-stu-id="09d22-135">This process can be extended to allow the flow to submit the contracts for payment by a third-party financial application (for example, Dynamics CRM).</span></span>

   ![Het contract is verplaatst naar Uitbetalen.](../media/content-understanding/for-payout.png)

- <span data-ttu-id="09d22-137">In de stroom maakt u het volgende item om goedgekeurde contracten te verplaatsen naar **het tabblad Voor uitbetaling.**</span><span class="sxs-lookup"><span data-stu-id="09d22-137">In the flow, you create the following item to move approved contracts to the **For Payout** tab.</span></span>

   ![Flow item om naar Pay Out te gaan.](../media/content-understanding/ready-for-payout.png)

- <span data-ttu-id="09d22-139">Een adaptieve kaart waarin wordt aangegeven dat het contract is goedgekeurd, wordt gemaakt en gepost op het kanaal Contractbeheer.</span><span class="sxs-lookup"><span data-stu-id="09d22-139">An adaptive card stating that the contract has been approved is created and posted to the Contract Management channel.</span></span>

   ![Goedkeuring van het contract is gepost.](../media/content-understanding/adaptive-card-approval.png)

   ![Goedkeuring van adaptieve kaarten.](../media/content-understanding/adaptive-card.png)


   <span data-ttu-id="09d22-142">De volgende code is de JSON die voor deze stap in de Power Automate wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="09d22-142">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a><span data-ttu-id="09d22-143">Als het contract wordt geweigerd</span><span class="sxs-lookup"><span data-stu-id="09d22-143">If the contract is rejected</span></span>

<span data-ttu-id="09d22-144">Wanneer een contract is geweigerd, treden de volgende dingen op:</span><span class="sxs-lookup"><span data-stu-id="09d22-144">When a contract has been rejected, the following things occur:</span></span>

- <span data-ttu-id="09d22-145">Op het **tabblad** Contracten wordt de status op de contractkaart gewijzigd in **Geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="09d22-145">On the **Contracts** tab, the status in the contract card will change to **Rejected**.</span></span>

   ![Kaartstatus geweigerd.](../media/content-understanding/rejected-contracts-tab.png)

- <span data-ttu-id="09d22-147">In uw stroom bekijkt u het contractbestand, wijzigt u de status in **Geweigerd** en controleert u het bestand opnieuw.</span><span class="sxs-lookup"><span data-stu-id="09d22-147">In your flow, you check out the contract file, change the status to **Rejected**, and then check the file back in.</span></span>

   ![Flow status geweigerd.](../media/content-understanding/reject-flow.png)

- <span data-ttu-id="09d22-149">In uw stroom maakt u een adaptieve kaart waarin wordt aangegeven dat het contract is geweigerd.</span><span class="sxs-lookup"><span data-stu-id="09d22-149">In your flow, you create an adaptive card stating that the contract has been rejected.</span></span>

   ![Flow status geweigerd.](../media/content-understanding/reject-flow-item.png)

<span data-ttu-id="09d22-151">De volgende code is de JSON die voor deze stap in de Power Automate wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="09d22-151">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- <span data-ttu-id="09d22-152">De kaart wordt gepost in het kanaal Contractbeheer.</span><span class="sxs-lookup"><span data-stu-id="09d22-152">The card is posted in the Contract Management channel.</span></span>

   ![Flow adaptieve kaart om te weigeren.](../media/content-understanding/rejected.png)