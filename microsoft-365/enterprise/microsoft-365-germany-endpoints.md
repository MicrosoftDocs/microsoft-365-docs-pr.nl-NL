---
title: Office 365-eindpunten voor Duitsland
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/08/2020
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
ms.openlocfilehash: 07badf1febec964ffdf6d6ef39c88f0e8bbca3f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689514"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Duitsland-eindpunten

 *Van toepassing op: Office 365-beheerder*

Voor Office 365 is connectiviteit met Internet vereist. De onderstaande eindpunten zijn bereikbaar voor klanten met alleen **Office 365 Duitsland** -abonnementen.
  
 **Office 365-eindpunten:** [wereldwijd (waaronder gcc)](urls-and-ip-address-ranges.md)   |  [Office 365 beheerd door 21 ViaNet](urls-and-ip-address-ranges-21vianet.md)   |  *Office 365 Duitsland*  |  [Office 365 US Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  |  [Office 365 US Government gcc High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Laatst bijgewerkt:** 07/08/2020- ![ abonnement op RSS- ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [wijzigingslogboek](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**Download:** alle vereiste en optionele bestemmingen in één [JSON](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) -lijst.  <br/> |

Begin met het [beheren van Office 365-eindpunten](managing-office-365-endpoints.md) voor informatie over de aanbevelingen voor het beheren van netwerkverbindingen met behulp van deze gegevens. De gegevens van eindpunten worden aan het begin van elke maand bijgewerkt met nieuwe IP-adressen en Url's gepubliceerd 30 dagen voordat ze actief zijn. Hiermee kunnen klanten die nog geen geautomatiseerde updates hebben, de processen voltooien voordat nieuwe verbinding is vereist. Eindpunten kunnen ook binnen de maand worden bijgewerkt, indien nodig voor de ondersteuning van escalaties, beveiligingsincidenten of andere directe bedrijfsvereisten. U kunt altijd naar het abonnement op het [wijzigingslogboek](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)verwijzen.

De op deze pagina vermelde gegevens worden allemaal gegenereerd op basis van de REST-webservices. Als u een script of een netwerkapparaat gebruikt voor toegang tot deze gegevens, moet u de [webservice](microsoft-365-ip-web-service.md) rechtstreeks raadplegen.

Gegevens van een eindpunt dit zijn de vereisten voor connectiviteit van de computer van een gebruiker in Office 365. Dit geldt niet voor netwerkverbindingen van Microsoft in een klanten netwerk, ook wel hybride verbindingen genaamd en inkomende netwerkverbindingen.

De eindpunten zijn gegroepeerd in vier serviceregio's. De eerste drie servicegebieden kunnen afzonderlijk voor connectiviteit worden geselecteerd. Het vierde servicegebied is een veelvoorkomende afhankelijkheid (genaamd Microsoft 365 common and Office) en moet altijd netwerkverbinding hebben.

Weergegeven gegevenskolommen zijn:

- **Id**: het id-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als het resultaat van de webservice van de eindpuntenset.

- **Categorie**: toont of de eindpunten van de set zijn gecategoriseerd als ' optimaliseren ', ' toestaan ' of ' standaard '. U vindt meer informatie over deze categorieën en richtlijnen voor het beheer hiervan [https://aka.ms/pnc](https://aka.ms/pnc) . In deze kolom wordt ook vermeld welke eindpunten sets vereist zijn voor netwerkverbindingen. Voor eindpunten die niet vereist zijn voor een netwerkverbinding, geven we notities in dit veld om aan te geven welke functionaliteit niet is beschadigd als de eindpunttoewijzer is geblokkeerd. Als u een volledig servicegebied uitlaat, zijn voor de opgegeven eindpunten die in de lijst aangegeven vereisten geen verbinding nodig.

- Geen **: dit**is **Ja** als de eindpunttoewijzer is geconfigureerd via Azure ExpressRoute met Office 365 route prefixen. De BGP-community die de weergegeven route prefixen bevat, wordt uitgelijnd met het aangegeven servicegebied. Als dit **niet het enige**is, betekent dit dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. Het kan echter voorkomen dat **er geen routes**worden aangekondigd voor een eindpuntenset.

- **Adressen**: vermeldt de FQDN-namen of de domeinnamen en IP-adresbereiken van de jokertekens voor de eindpuntenset. Houd er rekening mee dat een IP-adresbereik een CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen in het opgegeven netwerk omvat.
 
- **Poorten**: Hier vindt u de TCP-of UDP-poorten die worden gecombineerd met de adressen, om het eindpunt van het netwerk te vormen. U merkt mogelijk dat er dubbele poorten worden vermeld in IP-adresbereiken.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

