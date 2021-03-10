---
title: URL's en IP-adresbereiken voor Office 365 beheerd door 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/28/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: In dit artikel worden de URL's en IP-adresbereiken voor Office 365 vermeld wanneer deze worden beheerd door 21Vianet in China.
hideEdit: true
ms.openlocfilehash: dae2b5feb4fbf7fc3e9bdd2419e2d114b5507ee8
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597068"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>URL's en IP-adresbereiken voor Office 365 beheerd door 21Vianet

 *Van toepassing op: Office 365 beheerd door 21Vianet - Beheerder voor Kleine Bedrijven, Office 365 beheerd door 21Vianet - Beheerder*

**Overzicht:** De volgende eindpunten (FQDN's, poorten, URL's, IPv4- en IPv6-voorvoegsels) zijn van toepassing op Office 365 beheerd door 21 Vianet en zijn ontworpen om productiviteitsservices te leveren aan organisaties die alleen deze abonnementen gebruiken.
  
 **Office 365-eindpunten:** [Worldwide (inclusief GCC)](urls-and-ip-address-ranges.md)Office 365 beheerd door   |  *21 Vianet*  |  [Office 365 Germany](microsoft-365-germany-endpoints.md)Office  |  [365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)Office  |  [365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Laatst bijgewerkt:** 28-08-2020 - ![ Abonnement op ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-wijzigingslogboek](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Downloaden:** alle vereiste en optionele bestemmingen in één lijst in [JSON-indeling](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen. Eindpuntgegevens worden aan het begin van elke maand zo nodig bijgewerkt, met nieuwe IP-adressen en URL's die 30 dagen voor de actieve oproep zijn gepubliceerd. Dit maakt het voor klanten die nog geen geautomatiseerde updates hebben mogelijk om hun processen te voltooien voordat er een nieuwe verbinding is vereist. Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken. De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice. Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).

De eindpuntgegevens hieronder bevatten vereisten voor connectiviteit tussen de computer van een gebruiker en Office 365. Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd.

De eindpunten worden ingedeeld in vier servicegebieden. De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken. Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.

De getoonde gegevenskolommen zijn:

- **ID**: Het ID-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.

- **Categorie:** geeft aan of de eindpuntenset is gecategoriseerd als Optimaliseren, Toestaan of Standaard. U kunt meer lezen over deze categorieën en richtlijnen voor het beheer ervan [https://aka.ms/pnc](https://aka.ms/pnc) op. In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding. Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd. Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.

- **ER**: Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen. De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied. Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is.

- **Adressen**: Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven. Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.
 
- **Poorten**: Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen. Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]


