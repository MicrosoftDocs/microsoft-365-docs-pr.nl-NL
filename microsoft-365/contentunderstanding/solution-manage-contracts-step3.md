---
title: Stap 3. Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Informatie over het gebruik van Power Automate om uw stroom te maken om uw contracten te verwerken met behulp van een Microsoft 365 oplossing.
ms.openlocfilehash: e6c1d1e53363f996241efb2394189853d840c6c2
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054460"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a>Stap 3. Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken

U hebt uw contractbeheerkanaal gemaakt en uw documentbibliotheek SharePoint toegevoegd. De volgende stap is het maken van een Power Automate stroom voor het verwerken van uw contracten die door SharePoint Syntex model worden geïdentificeerd en classificeert. U kunt deze stap doen door [een Power Automate te maken in uw SharePoint documentbibliotheek.](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)

Voor uw oplossing voor contractenbeheer wilt u een Power Automate maken om de volgende acties uit te voeren:

-  Nadat een contract is geclassificeerd door uw SharePoint Syntex model, wijzigt u de contractstatus **in In review.**
- Het contract wordt vervolgens beoordeeld en wordt goedgekeurd of geweigerd.
- Voor goedgekeurde contracten worden de contractgegevens geplaatst op een tabblad voor betalingsverwerking.
- Voor geweigerde contracten wordt het team op de hoogte gesteld voor verdere analyse. 

In het volgende diagram ziet u de Power Automate voor de oplossing voor contractbeheer.

![Flow diagram met de hele oplossing.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>Uw contract voorbereiden voor controle

Wanneer een contract wordt geïdentificeerd en geclassificeerd door uw SharePoint Syntex document-inzichtsmodel, wordt de status Power Automate de status eerst gewijzigd **in In revisie.**

![Status bijwerken.](../media/content-understanding/flow-overview.png)

Nadat u het bestand hebt uitchecken, wijzigt u de statuswaarde **in In revisie.**

![In revisiestatus.](../media/content-understanding/in-review.png)

De volgende stap is het maken van een adaptieve kaart waarin wordt aangegeven dat het contract wacht op revisie en deze post naar het kanaal Contractbeheer.

![Contractbeoordelingsbericht.](../media/content-understanding/contract-approval-post.png)


![Maak adaptieve kaart voor controle.](../media/content-understanding/adaptive-card.png)

De volgende code is de JSON die voor deze stap in de Power Automate wordt gebruikt.

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


## <a name="conditional-context"></a>Voorwaardelijke context

In uw stroom moet u vervolgens een voorwaarde maken waarin uw contract wordt [goedgekeurd of](#if-the-contract-is-approved) [geweigerd.](#if-the-contract-is-rejected)

![Voorwaardelijk.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>Als het contract is goedgekeurd

Wanneer een contract is goedgekeurd, treden de volgende dingen op:

- Op het **tabblad** Contracten wordt de status op de contractkaart gewijzigd in **Goedgekeurd.**

   ![Kaartstatus goedgekeurd.](../media/content-understanding/approved-contracts-tab.png)

- In uw stroom wordt de status gewijzigd in **Goedgekeurd.**

   ![Flow status goedgekeurd.](../media/content-understanding/status-approved.png)

- In deze oplossing worden de contractgegevens  toegevoegd aan het tabblad Voor uitbetaling, zodat de uitbetalingen kunnen worden beheerd. Dit proces kan worden uitgebreid zodat de stroom de contracten voor betaling kan indienen door een financiële toepassing van derden (bijvoorbeeld Dynamics CRM).

   ![Het contract is verplaatst naar Uitbetalen.](../media/content-understanding/for-payout.png)

- In de stroom maakt u het volgende item om goedgekeurde contracten te verplaatsen naar **het tabblad Voor uitbetaling.**

   ![Flow item om naar Pay Out te gaan.](../media/content-understanding/ready-for-payout.png)

    Gebruik de waarden in de volgende tabel om de expressies te verkrijgen voor de Teams de benodigde gegevens.
 
    |Naam     |Expression |
    |---------|-----------|
    | Goedkeuringstoestand  | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['submitActionId']         |
    | Goedgekeurd door     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['responder'] ['displayName']        |
    | Goedkeuringsdatum     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['responseTime']         |
    | Opmerking     | body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')? ['gegevens'] ['acComments']         |
    
    In het volgende voorbeeld ziet u hoe u het formulevak gebruikt in Power Automate om een expressie te schrijven.

   ![Schermafbeelding in Power Automate met een expressieformule.](../media/content-understanding/expression-formula-power-automate.png)    

- Een adaptieve kaart waarin wordt aangegeven dat het contract is goedgekeurd, wordt gemaakt en gepost op het kanaal Contractbeheer.

   ![Goedkeuring van het contract is gepost.](../media/content-understanding/adaptive-card-approval.png)

   ![Goedkeuring van adaptieve kaarten.](../media/content-understanding/adaptive-card.png)


   De volgende code is de JSON die voor deze stap in de Power Automate wordt gebruikt.

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

## <a name="if-the-contract-is-rejected"></a>Als het contract wordt geweigerd

Wanneer een contract is geweigerd, treden de volgende dingen op:

- Op het **tabblad** Contracten wordt de status op de contractkaart gewijzigd in **Geweigerd.**

   ![Kaartstatus geweigerd.](../media/content-understanding/rejected-contracts-tab.png)

- In uw stroom bekijkt u het contractbestand, wijzigt u de status in **Geweigerd** en controleert u het bestand opnieuw.

   ![Flow status geweigerd in het contractbestand.](../media/content-understanding/reject-flow.png)

- In uw stroom maakt u een adaptieve kaart waarin wordt aangegeven dat het contract is geweigerd.

   ![Flow status wordt geweigerd op adaptieve kaart.](../media/content-understanding/reject-flow-item.png)

De volgende code is de JSON die voor deze stap in de Power Automate wordt gebruikt.

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

- De kaart wordt gepost in het kanaal Contractbeheer.

   ![Flow adaptieve kaart om te weigeren.](../media/content-understanding/rejected.png)