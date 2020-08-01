---
title: Microsoft Managed Desktop-productlevenscyclus
description: In dit onderwerp worden de apparaatspecificaties weergegeven die worden gebruikt in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 0dee95743e0a504330ebbcc69749e41cdc96da39
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529945"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop-productlevenscyclus

Microsoft Managed Desktop heeft voordelen voor eindgebruikers om ervoor te zorgen dat ze altijd apparaten gebruiken die de beste prestaties, betrouwbaarheid, ontwerp en beveiligingsmogelijkheden bieden (zoals ondersteuning voor functies zoals Windows Hello). Om dit te bereiken, onderhoudt Microsoft Managed Desktop een korte catalogus van continu [bijgewerkte goedgekeurde apparaten.](device-list.md) 
 
In dit onderwerp wordt de levenscyclus van apparaten beschreven wanneer ze worden toegevoegd en verwijderd uit de goedgekeurde catalogus. 

> [!NOTE]
> In dit onderwerp maken we een onderscheid tussen een "apparaat" en een 'product'. Met "apparaat" bedoelen we één individuele, specifieke computer. Bijvoorbeeld, "Serienummer 1234", "Bill's laptop", "Shared VM XYZ" verwijzen naar specifieke apparaten. Een "product" verwijst echter naar een verzameling of een familie van apparaten. Bijvoorbeeld "Fabrikam Laptop", "Adatum ZX450 Laptop", enz. Dit is belangrijk omdat producten worden toegevoegd aan onze [goedgekeurde lijst](device-list.md)of catalogus, en apparaten worden ingeschreven bij Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Productlevenscyclus

 Over het algemeen doorlopen producten deze levenscyclusfasen:

- [Productrelease en -evaluatie](#product-release-and-evaluation)
- [Primaire beschikbaarheidsperiode voor producten](#product-primary-availability-period)
- [Product respijtperiode](#product-grace-period)
- [Productpensioen](#product-retirement)


Deze illustratie toont de gehele volgorde:

![levenscyclustijdlijn: vanaf de algemene beschikbaarheid van het product duurt 'primaire beschikbaarheid' twee jaar. Gedurende deze tijd eindigt het certificeringsvenster en op een gegeven moment is het apparaat aan boord. Aan het einde van de primaire beschikbaarheid wordt het product gearchiveerd en begint de "respijtperiode" van drie jaar. Vanaf het moment dat het apparaat is ingebouwde, heeft het een gebruiksperiode van 3 jaar totdat het uit het beheer wordt verwijderd. Aan het einde van de respijtperiode verwijderen we het product uit de catalogus.](../../media/non-dark1-edits.PNG)

Producten blijven maximaal 24 maanden in de catalogus staan, maar <em>apparaten</em> blijven 3 jaar onder beheer op basis van hun individuele inschrijvingsdatums. Effectief, elk product heeft drie belangrijke data, maar elk apparaat heeft slechts een. Voor producten worden alle drie deze data berekend op basis van de <em>goedkeuringsdatum,</em>en daarom publiceren we deze data na goedkeuring, zodat u altijd vooruit kijken en de gehele levenscyclus van het product op de juiste manier plannen.

In deze tabel worden voorbeelddata voor een theoretisch product weergegeven:


|Product  |Goedgekeurde datum  |Einde van de primaire beschikbaarheid  |Einde van de subsidiabiliteit  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum-laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

In deze tabel worden voorbeelddata voor theoretische *apparaten weergegeven:*


|Apparaat-id  |Inschrijvingsdatum  |Pensioendatum  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|#321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Productrelease en -evaluatie

De levenscyclus van het product begint wanneer een fabrikant het product openbaar uitbrengt:

![tijdlijntijdlijn met release- en evaluatieperiode](../../media/non-dark3-edits.PNG)

Tijdens deze fase doet het Microsoft Managed Desktop engineering team hun evaluatie en certificering van een product. Het team evalueert onder andere zaken als betrouwbaarheid en prestaties met Windows, naleving van een hardwarebasislijn, marktsentiment en voorraad- en kanaalbereidheid. Dit proces duurt meestal ongeveer 6 weken.
  
Microsoft Managed Desktop evalueert apparaten alleen voor certificering binnen de eerste zes maanden van beschikbaarheid. Dit zorgt ervoor dat we onze inspanningen altijd richten op de nieuwste generatie hardware.
 
Aan het einde van deze fase voegt Microsoft Managed Desktop het product toe aan de [goedgekeurde lijst,](device-list.md)waardoor het product effectief wordt vrijgegeven voor klantinschrijvingen. Ongeacht de datum waarop een apparaat is gecertificeerd, is de **goedgekeurde datum** gedateerd op de algemene beschikbaarheidsdatum van het product. 


## <a name="product-primary-availability-period"></a>Primaire beschikbaarheidsperiode voor producten

Deze periode is de kern van de beschikbaarheid van producten:

![tijdlijntijdlijn met primaire beschikbaarheid](../../media/non-dark4-edits.PNG)

Elk apparaat dat tijdens deze periode is ingeschreven, ontvangt de volledige drie jaar ondersteuning van Microsoft Managed Desktop (zoals blijkt uit de blauwe tijdlijn). Deze periode duurt tot een einddatum die is vastgesteld op 24 maanden vanaf de algemene beschikbaarheidsdatum.

U deze periode zien als effectief open inschrijving, dus om de waarde van Microsoft Managed Desktop te maximaliseren, moet u zich richten op uw inkoopmodellen en geselecteerde producten die binnen deze periode vallen. Als klein voorbeeld moet een klant voorkomen dat een klant zich vestigt op een roll-outperiode van twee jaar met behulp van een product dat zich in de laatste maand van de primaire beschikbaarheid bevindt - de meeste van deze apparaten ontvangen niet de volledige drie jaar Microsoft Managed Desktop-beheer (zie [respijtperiode](#product-grace-period) voor meer informatie).  

## <a name="product-grace-period"></a>Product respijtperiode

De productspijtperiode is een periode van drie jaar na de primaire beschikbaarheid. In deze fase u apparaten inschrijven die afkomstig zijn uit een ondersteunde productfamilie, maar nog steeds vasthouden aan de beloften van Microsoft Managed Desktop met betrekking tot moderne hardware- en apparaatprestaties. Deze fase is ideaal voor klanten die inkoopbeslissingen hebben genomen voordat ze weten van Microsoft Managed Desktop. 

Als u onlangs een aantal goedgekeurde apparaten hebt gekocht voordat u zich inschreef bij Microsoft Managed Desktop, u deze nog steeds inschrijven, maar u ontvangt geen volledige drie jaar beheer. In plaats daarvan zullen ze op de pensioendatum niet aan de eisen voldoen, ongeacht wanneer ze zijn ingeschreven. Achter de schermen behandelt Microsoft Managed Desktop deze apparaten alsof ze zijn ingeschreven op de laatste dag van de primaire beschikbaarheid. In deze illustratie u dit scenario zien door op te merken dat zowel het blauwe als het groene apparaat op dezelfde dag eindigen, ondanks hun verschil van één jaar in inschrijving:


![tijdlijntijdlijn met respijtperiode](../../media/non-dark2-edits.PNG)

Het Fabrikam Laptop voorbeeld van de vorige tabel illustreert deze situatie: 

|Product  |Goedgekeurde datum  |Einde van de primaire beschikbaarheid  |Einde van de subsidiabiliteit  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Als klant kun je Fabrikam Laptops helemaal inschrijven tot 6/1/2022 - maar ze worden allemaal behandeld alsof je ze hebt ingeschreven op 6/1/2019. Als je op 6/1/2021 een Fabrikam Laptop inschrijft, krijg je maar één jaar management. Met dit beleid u gedeeltelijke levenscyclusen extraheren uit producten die eerder werden ondersteund, in plaats van nieuwe apparaten voortijdig aan te schaffen. 

Ten slotte wordt het apparaat tijdens deze fase uit de [apparaatlijst](device-list.md) verwijderd en naar de [lijst met gearchiveerde apparaten](archived-device-list.md)verplaatst.


## <a name="product-retirement"></a>Productpensioen

Productpensioen is de laatste fase van de levenscyclus. In deze fase kunnen geen nieuwe apparaten van dat producttype worden ingeschreven in Microsoft Managed Desktop en per definitie zijn alle bestaande apparaten nu buiten de toegestane termijn van drie jaar. Gedurende deze periode verwijdert Microsoft Managed Desktop het apparaat volledig uit de openbare lijst. Het is ook tijdens deze fase waarin, als u nog geen vervangingen hebt aangeschaft, u verminderde services begint te zien terwijl Microsoft Managed Desktop begint te worden opgekort op de apparaten die niet aan de regels voldoen. 

## <a name="devices-that-are-out-of-compliance"></a>Apparaten die niet aan de regels voldoen

Een apparaat is niet in overeenstemming wanneer het toegestane venster voor Microsoft Managed Desktop-beheer is verstreken. Dit gebeurt wanneer het apparaat drie jaar beheer heeft bereikt of wanneer dat producttype uit de apparaatcatalogus wordt verwijderd, ongeacht wat het eerst gebeurt. U moet uw inkoopcycli altijd zodanig targeten dat nieuwe apparaten worden geïmplementeerd voordat de huidige apparaten niet meer voldoen.

Het Microsoft Managed Desktop-team weet dat inkoopcycli lang zijn en gepland rond langlopende budgetten. Om ervoor te zorgen dat u altijd op de hoogte bent van de status van uw apparaatpopulatie, bieden we een [website](https://aka.ms/mmdportal) die elk apparaat onder beheer, de leeftijd en een status vermeldt die de naleving ervan aangeeft. Dit betekent dat u altijd over de meest recente informatie beschikt over de leeftijd van het apparaat en het rapport gebruiken in elke inkoopplanningscyclus. 







