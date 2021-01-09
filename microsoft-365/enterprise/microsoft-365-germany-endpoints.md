---
title: Office 365-eindpunten voor Duitsland
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: In dit artikel vindt u eindpunten die bereikbaar zijn voor klanten met Office 365 in Duitsland.
hideEdit: true
ms.openlocfilehash: 7c4a65780892d6e257c1c03832cd640bdd4573f3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787913"
---
# <a name="office-365-germany-endpoints"></a>Office 365 eindpunten Germany-eindpunten

 *Van toepassing op: Office 365-beheerder*

Office 365 vereist verbinding met internet. De onderstaande eindpunten zijn bereikbaar voor klanten met alleen **Office 365 Duitsland** -abonnementen.
  
 **Office 365-eindpunten:** [wereldwijd (waaronder gcc)](urls-and-ip-address-ranges.md)   |  [Office 365 beheerd door 21 ViaNet](urls-and-ip-address-ranges-21vianet.md)   |  *Office 365 Duitsland*  |  [Office 365 US Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  |  [Office 365 US Government gcc High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Laatst bijgewerkt:** 01-04-2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement op wijzigingenlogboek](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**Downloaden:** alle vereiste en optionele bestemmingen in één lijst in [JSON-indeling](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen. Eindpuntgegevens worden aan het begin van elke maand bijgewerkt met nieuwe IP-adressen en URL's die worden gepubliceerd 30 dagen voordat ze actief worden. Hiermee kunnen klanten die nog geen geautomatiseerde updates hebben, de processen voltooien voordat nieuwe verbinding is vereist. Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken. U kunt altijd naar het abonnement op het [wijzigingslogboek](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)verwijzen.

De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice. Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).

De onderstaande eindpuntgegevens geven een overzicht van de vereisten voor verbinding tussen de computer van een gebruiker en Office 365. Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd.

De eindpunten worden ingedeeld in vier servicegebieden. De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken. Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.

De getoonde gegevenskolommen zijn:

- **ID**: Het ID-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.

- **Category**: Toon of de eindpuntenset wordt gecategoriseerd als "Optimaliseren", "Toestaan" of "Standaard". U vindt meer informatie over deze categorieën en richtlijnen voor het beheer hiervan [https://aka.ms/pnc](https://aka.ms/pnc) . In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding. Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd. Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.

- **ER**: Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen. De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied. Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is.

- **Adressen**: Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven. Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.
 
- **Poorten**: Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen. Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

