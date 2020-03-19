---
title: Microsoft Managed Desktop-productlevenscyclus
description: In dit onderwerp worden de apparaatspecificaties weergegeven die worden gebruikt in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: b65724a1eee35149d473fb69ff646b5ef5751b2c
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2020
ms.locfileid: "42807315"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop-productlevenscyclus

Microsoft Managed Desktop profiteert ervoor dat eindgebruikers altijd apparaten gebruiken die de beste prestaties, betrouwbaarheid, ontwerp en beveiligingsmogelijkheden bieden (zoals ondersteuning voor functies zoals Windows Hello). Om dit te bereiken, onderhoudt Microsoft Managed Desktop een korte catalogus met voortdurend bijgewerkte [goedgekeurde apparaten.](device-list.md) 
 
In dit onderwerp wordt de levenscyclus van apparaten beschreven wanneer ze worden toegevoegd en uit de goedgekeurde catalogus worden verwijderd. 

> [!NOTE]
> In dit onderwerp maken we een onderscheid tussen een 'apparaat' en een 'product'. Met 'apparaat' bedoelen we één individuele, specifieke computer. Bijvoorbeeld, "Serienummer 1234", "Bill's laptop", "Shared VM XYZ" verwijzen naar specifieke apparaten. Een "product", echter, verwijst naar een verzameling of familie van apparaten. Bijvoorbeeld "Fabrikam Laptop", "Adatum ZX450 Laptop", enz. Dit is belangrijk omdat producten worden toegevoegd aan onze [goedgekeurde lijst](device-list.md)of catalogus en apparaten zijn wat worden ingeschreven bij Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Levenscyclus van producten

 Over het algemeen gaan producten door deze levenscyclusfasen:

- [Productrelease en -evaluatie](#product-release-and-evaluation)
- [Primaire beschikbaarheidsperiode voor producten](#product-primary-availability-period)
- [Respijtperiode bij het product](#product-grace-period)
- [Productpensioen](#product-retirement)


Deze illustratie toont de volledige reeks:

![levenscyclustijdlijn: te beginnen met de algemene beschikbaarheid van het product, duurt de primaire beschikbaarheid twee jaar. Gedurende deze tijd eindigt het certificeringsvenster en op een gegeven moment is het apparaat aan boord. Aan het einde van de primaire beschikbaarheid wordt het product gearchiveerd en begint de "respijtperiode" van drie jaar. Vanaf het moment dat het apparaat aan boord is, heeft het een gebruiksduur van 3 jaar totdat het uit het beheer is verwijderd. Aan het einde van de respijtperiode verwijderen we het product uit de catalogus.](../../media/non-dark1-edits.PNG)

Producten blijven maximaal 24 maanden in de catalogus staan, maar <em>apparaten</em> blijven 3 jaar onder beheer op basis van hun individuele inschrijvingsdata. Effectief, elk product heeft drie belangrijke data, maar elk apparaat heeft slechts een. Voor producten worden alle drie deze data berekend op basis van de <em>goedkeuringsdatum,</em>en daarom publiceren we deze data na goedkeuring, zodat u altijd vooruit kijken en de juiste plannen plannen voor de volledige levenscyclus van het product.

In deze tabel worden voorbeelddatums voor een theoretisch product weergegeven:


|Product  |Goedgekeurde datum  |Einde van de primaire beschikbaarheid  |Einde van de subsidiabiliteit  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

In deze tabel worden voorbeelddatums voor theoretische *apparaten weergegeven:*


|Apparaat-ID  |Inschrijvingsdatum  |Pensioendatum  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Bureaublad#321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Productrelease en -evaluatie

De levenscyclus van het product begint wanneer een fabrikant het product openbaar uitbrengt:

![levenscyclustijdlijn met release- en evaluatieperiode](../../media/non-dark3-edits.PNG)

In deze fase doet het Microsoft Managed Desktop engineering-team hun evaluatie en certificering van een product. Het team evalueert onder andere betrouwbaarheid en prestaties met Windows, naleving van een hardwarebaseline, marktsentiment en voorraad- en kanaalgereedheid. Dit proces duurt meestal ongeveer 6 weken.
  
Microsoft Managed Desktop evalueert alleen apparaten voor certificering binnen de eerste 6 maanden na beschikbaarheid. Dit zorgt ervoor dat we onze inspanningen altijd richten op de nieuwste generatie hardware.
 
Aan het einde van deze fase voegt Microsoft Managed Desktop het product toe aan de [goedgekeurde lijst,](device-list.md)waardoor het product effectief wordt vrijgegeven voor klantinschrijvingen. Ongeacht de datum waarop een apparaat is gecertificeerd, de **goedgekeurde datum** is gedateerd op de eigen algemene beschikbaarheidsdatum van het product. 


## <a name="product-primary-availability-period"></a>Primaire beschikbaarheidsperiode voor producten

Deze periode is de kern van de beschikbaarheid van producten:

![levenscyclustijdlijn met primaire beschikbaarheid](../../media/non-dark4-edits.PNG)

Elk apparaat dat tijdens deze periode is ingeschreven, krijgt de volledige drie jaar ondersteuning van Microsoft Managed Desktop (zoals weergegeven in de blauwe tijdlijn). Deze periode duurt tot een einddatum die is vastgesteld op 24 maanden na de algemene beschikbaarheidsdatum.

U deze periode zien als effectief open inschrijving, dus om de waarde van Microsoft Managed Desktop te maximaliseren, moet u uw inkoopmodellen en geselecteerde producten targeten om binnen deze periode te vallen. Als klein voorbeeld moet een klant voorkomen dat hij zich op een uitrolperiode van twee jaar vestigt met een product dat zich in de laatste maand van primaire beschikbaarheid bevindt - de meeste van deze apparaten ontvangen niet de volledige drie jaar Microsoft Managed Desktop-beheer (zie [respijtperiode](#product-grace-period) voor meer informatie).  

## <a name="product-grace-period"></a>Respijtperiode bij het product

De respijtperiode van het product is een periode van drie jaar na de primaire beschikbaarheid. Met deze fase u apparaten inschrijven die afkomstig zijn uit een ondersteunde productfamilie, maar nog steeds vasthouden aan de beloften van Microsoft Managed Desktop met betrekking tot moderne hardware- en apparaatprestaties. Deze fase is ideaal voor klanten die inkoopbeslissingen hebben genomen voordat ze weten over Microsoft Managed Desktop. 

Als u onlangs een aantal goedgekeurde apparaten hebt gekocht voordat u zich inschrijft bij Microsoft Managed Desktop, u ze nog steeds inschrijven, maar ontvangt u geen volledige drie jaar beheer. In plaats daarvan zullen ze vallen uit de naleving op de pensioendatum, ongeacht wanneer ze werden ingeschreven. Achter de schermen behandelt Microsoft Managed Desktop deze apparaten alsof ze zijn ingeschreven op de laatste dag van primaire beschikbaarheid. In deze illustratie u dit scenario zien door op te merken dat zowel het blauwe als het groene apparaat op dezelfde dag eindigt, ondanks hun verschil in inschrijving van een jaar:


![levenscyclustijdlijn met respijtperiode](../../media/non-dark2-edits.PNG)

De Fabrikam Laptop voorbeeld van de vorige tabel illustreert deze situatie: 

|Product  |Goedgekeurde datum  |Einde van de primaire beschikbaarheid  |Einde van de subsidiabiliteit  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Als klant kun je Fabrikam Laptops helemaal inschrijven tot 6/1/2022 - maar ze zullen allemaal worden behandeld alsof je ze hebt ingeschreven op 6/1/2019. Als je op 6/1/2021 een Fabrikam Laptop inschrijft, krijg je maar één jaar management. Met dit beleid u gedeeltelijke levenscycluss extraheren uit producten die eerder zijn ondersteund, in plaats van dat u voortijdig nieuwe apparaten moet aanschaffen. 

Ten slotte wordt het apparaat tijdens deze fase uit de [lijst](device-list.md) van apparaten verwijderd en naar de [lijst met gearchiveerde apparaten](archived-device-list.md)verplaatst.


## <a name="product-retirement"></a>Productpensioen

Productpensioen is de laatste fase van de levenscyclus. In deze fase kunnen geen nieuwe apparaten van dat producttype worden ingeschreven in Microsoft Managed Desktop en zijn alle bestaande apparaten nu per definitie buiten hun toegestane termijn van drie jaar. Gedurende deze periode verwijdert Microsoft Managed Desktop het apparaat volledig uit de openbare lijst. Het is ook tijdens deze fase waar, als u nog niet hebt aangeschaft vervangingen, zult u beginnen te zien verminderde diensten als Microsoft Managed Desktop begint te ramp down op de apparaten die niet voldoen aan de naleving. 

## <a name="devices-that-are-out-of-compliance"></a>Apparaten die niet aan de regels voldoen

Een apparaat voldoet niet meer aan de regels wanneer het toegestane venster voor Microsoft Managed Desktop-beheer is verstreken. Dit gebeurt wanneer het apparaat drie jaar beheer heeft bereikt of wanneer dat producttype uit de apparaatcatalogus wordt verwijderd, wat het geval is. U moet uw inkoopcycli altijd zo targeten dat nieuwe apparaten worden geïmplementeerd voordat huidige apparaten niet voldoen.

Het Microsoft Managed Desktop-team weet dat inkoopcycli lang zijn en gepland rond langlopende budgetten. Om ervoor te zorgen dat u altijd op de hoogte bent van de status van uw apparaatpopulatie, bieden we een website met een [lijst](https://aka.ms/mmdportal) van elk apparaat dat onder beheer is, de leeftijd en de status die aangeeft dat het voldoet. Dit betekent dat u altijd over de laatste informatie beschikt over de leeftijd van het apparaat en het rapport gebruiken in elke aanbestedingsplanningscyclus. 







