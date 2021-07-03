---
title: Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken
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
description: Meer informatie over het gebruik Microsoft Teams om uw contractbeheerkanaal te maken met behulp van een Microsoft 365 oplossing.
ms.openlocfilehash: 79298cc570f59bbd4fa48a6ba9e68e8562a519a2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287303"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken

Wanneer uw organisatie een oplossing voor contractenbeheer in stelt, hebt u een centrale locatie nodig waar belanghebbenden contracten kunnen bekijken en beheren. Hiervoor kunt u een [](/microsoftteams/) Microsoft Teams voor het instellen van een Teams kanaal en de functies in Teams gebruiken:

- **Maak een locatie voor belanghebbenden om eenvoudig alle contracten te zien waarvoor actie moet worden ondernomen.** In Teams kunt u bijvoorbeeld een  tabblad Contracten maken in het kanaal Contractbeheer waarin leden een handige tegelweergave kunnen zien van alle contracten die moeten worden goedgekeurd. U kunt de weergave ook zo configureren dat elke 'kaart' de belangrijke gegevens bevat die u belangrijk vindt (zoals *Client,* *Contractant* en *Kostenbedrag).*

     ![Tabblad Contracten.](../media/content-understanding/tile-view.png)

- **Hebben een locatie voor leden om met elkaar te communiceren en belangrijke gebeurtenissen te zien.** In Teams kunt u bijvoorbeeld  het tabblad Berichten gebruiken om gesprekken te voeren, updates op te vragen en acties te bekijken (zoals een lid dat een contract weigert). Wanneer er iets is gebeurd (zoals een  nieuw contract dat ter goedkeuring is ingediend), kan het tabblad Berichten niet alleen worden gebruikt om het aan te kondigen, maar ook om een record van het contract bij te houden. En als leden zich abonneren op meldingen, krijgen ze een melding wanneer er een update is.

     ![Tabblad Berichten.](../media/content-understanding/posts.png)

- **Hebben een locatie waar leden goedgekeurde contracten kunnen zien om te weten wanneer ze tegen betaling kunnen worden ingediend.** In SharePoint moet u een lijst Voor  uitbetaling maken en kolommen opnemen voor het bedrag  **client,** contractant en **kosten,** en één regel tekst selecteren als kolomtype. U moet de lijst  Voor uitbetaling toevoegen als een Teams in het kanaal Contractbeheer, vergelijkbaar met wat u voor het tabblad [ **Contracten gaat** doen.](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab) Op **het tabblad** Voor uitbetaling worden alle contracten weergegeven die tegen betaling moeten worden ingediend. U kunt deze oplossing eenvoudig uitbreiden om deze informatie rechtstreeks te schrijven naar een financiële toepassing van derden (bijvoorbeeld Dynamics CRM). 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Uw documentbibliotheek SharePoint toevoegen aan het tabblad Contracten

Nadat u een tabblad **Contracten** hebt aangemaakt in uw kanaal Contractenbeheer, moet u uw SharePoint [documentbibliotheek eraan koppelen.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) De SharePoint documentbibliotheek die u wilt toevoegen, is de documentbibliotheek waarop u uw document SharePoint Syntex hebt toegepast in de vorige sectie.

Nadat u de SharePoint documentbibliotheek hebt toegevoegd, kunt u alle geclassificeerde contracten weergeven via een standaardlijstweergave.

   ![Lijstweergave van SharePoint bibliotheek.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>De tegelweergave op het tabblad Contracten aanpassen

> [!NOTE]
> In deze sectie wordt verwezen naar codevoorbeelden die zijn opgenomen in deContractTileFormatting.js[ bestand](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) dat is opgenomen in de opslagplaats Voor oplossingsactiva voor [contractenbeheer](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).

Hoewel Teams kunt u uw contracten weergeven in een tegelweergave, kunt u deze aanpassen om de contractgegevens weer te geven die u zichtbaar wilt maken op de contractkaart. Voor het tabblad  Contracten is het bijvoorbeeld belangrijk dat leden het bedrag van de klant, de contractant en de kosten op de contractkaart zien. Al deze velden zijn uit elk contract geëxtraheerd via SharePoint Syntex model dat is toegepast op uw documentbibliotheek. U wilt ook de tegelkoptekstbalk kunnen wijzigen in verschillende kleuren voor elke status, zodat leden eenvoudig kunnen zien waar het contract zich in het goedkeuringsproces vindt. Alle goedgekeurde contracten hebben bijvoorbeeld een blauwe koptekstbalk.

   ![Tegelweergave van SharePoint bibliotheek.](../media/content-understanding/tile.png)

Voor de aangepaste tegelweergave die u gebruikt, moet u wijzigingen aanbrengen in het JSON-bestand dat wordt gebruikt om de huidige tegelweergave op te maken. U kunt verwijzen naar het JSON-bestand dat wordt gebruikt om de kaartweergave te maken door te kijken [naar deContractTileFormatting.jsbestand.](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) In de volgende secties ziet u specifieke secties van de code voor functies in de contractkaarten.

Als u de JSON-code voor uw weergave wilt zien of wijzigen in uw Teams-kanaal, selecteert u in het kanaal Teams de vervolgkeuzelijst Weergave en selecteert u Huidige weergave opmaken.

   ![Schermafbeelding van json-indeling in Teams kanaal.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>Kaartgrootte en -vorm

Bekijk in [ContractTileFormatting.jsde](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) volgende sectie de code voor de opmaak van de grootte en vorm van de kaart.

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

## <a name="contract-status"></a>Contractstatus

Met de volgende code kunt u de status van elke titelkaart definiëren. Elke statuswaarde (*Nieuw*, *In revisie*, Goedgekeurd en Geweigerd ) geeft voor elke status een andere kleurcode weer.   Bekijk in [ContractTileFormatting.jsbestand](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) de sectie die de status definieert.

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

## <a name="extracted-fields"></a>Geëxtraheerde velden

Op elke contractkaart worden drie velden weergegeven die zijn geëxtraheerd voor elk contract *(Client,* *Contractant* en *Kostenbedrag).* Daarnaast wilt u ook de tijd/datum weergeven waarop het bestand is geclassificeerd op basis van het SharePoint Syntex om het te identificeren.

In het [ContractTileFormatting.jsbestand](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) definiëren de volgende secties elk van deze secties.

### <a name="client"></a>Client

In deze sectie wordt beschrijft hoe 'Client' wordt weergegeven op de kaart en wordt de waarde voor het specifieke contract gebruikt.

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

### <a name="contractor"></a>Aannemer

In deze sectie wordt de weergave van de contractant op de kaart beschrijft en wordt de waarde voor het specifieke contract gebruikt.

```JSON
                        {
                          "elmType": "div",
                          "txtContent": "Contractor",
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
                          "txtContent": "[$Contractor]"
                        },
```

### <a name="fee-amount"></a>Kostenbedrag

In deze sectie wordt beschrijft hoe het bedrag van de kosten wordt weergegeven op de kaart en wordt de waarde voor het specifieke contract gebruikt.

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

### <a name="classification-date"></a>Classificatiedatum

In deze sectie wordt beschrijft hoe 'Classificatie' wordt weergegeven op de kaart en wordt de waarde voor het specifieke contract gebruikt.

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

## <a name="next-step"></a>Volgende stap

[Stap 3. Gebruik Power Automate om uw stroom te maken om uw contracten te verwerken](solution-manage-contracts-step3.md)
