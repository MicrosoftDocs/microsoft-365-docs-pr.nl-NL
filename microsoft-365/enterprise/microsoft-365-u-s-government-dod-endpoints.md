---
title: Office 365 US Government DOD-eindpunten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 vereist verbinding met internet. De onderstaande eindpunten zijn bereikbaar voor klanten met Office 365 US Government DoD-abonnementen.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ebf93708849a06348edd5433c56c486595da55a4
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791934"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 US Government DoD-eindpunten

*Van toepassing op: Office 365-beheerder*

 Office 365 vereist verbinding met internet. De onderstaande eindpunten zijn bereikbaar voor klanten met Office 365 US Government DoD-abonnementen.
  
 **Office 365-eindpunten:** [wereldwijd (waaronder gcc)](urls-and-ip-address-ranges.md)  |  [Office 365 beheerd door 21 ViaNet](urls-and-ip-address-ranges-21vianet.md)   |  [Office 365 Duitsland](microsoft-365-germany-endpoints.md)  |  *Office 365 US Government DoD*  |  [Office 365 US Government gcc High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Laatst bijgewerkt:** 10/28/2020- ![ abonnement op RSS- ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [wijzigingslogboek](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** de volledige lijst in [JSON-indeling](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen. Eindpuntgegevens worden aan het begin van elke maand bijgewerkt met nieuwe IP-adressen en URL's die worden gepubliceerd 30 dagen voordat ze actief worden. Hiermee kunnen klanten die nog geen geautomatiseerde updates hebben, de processen voltooien voordat nieuwe verbinding is vereist. Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken. De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice. Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).

De onderstaande eindpuntgegevens geven een overzicht van de vereisten voor verbinding tussen de computer van een gebruiker en Office 365. Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd. Zie [extra eindpunten die niet zijn opgenomen in de webservice](additional-office365-ip-addresses-and-urls.md)voor meer informatie. 

De eindpunten worden ingedeeld in vier servicegebieden. De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken. Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.

De getoonde gegevenskolommen zijn:

- **ID** : Het ID-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.

- **Category** : Toon of de eindpuntenset wordt gecategoriseerd als "Optimaliseren", "Toestaan" of "Standaard". U vindt meer informatie over deze categorieën en richtlijnen voor het beheer hiervan [https://aka.ms/pnc](https://aka.ms/pnc) . In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding. Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd. Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.

- **ER** : Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen. De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied. Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is. Als u van plan bent om Azure AD Connect te gebruiken, raadpleegt u de [sectie speciale aandachtspunten](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) om ervoor te zorgen dat u de juiste configuratie van Azure AD Connect hebt.

- **Adressen** : Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven. Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.
 
- **Poorten** : Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen. Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Opmerkingen voor deze tabel:

- Het beveiligings-en compliance Center (SCC) biedt ondersteuning voor Azure ExpressRoute voor Office 365. Dit geldt ook voor tal van functies die via het SCC worden weergegeven, zoals rapporteren, controleren, Advanced eDiscovery, Unified DLP en data governance. Bij twee specifieke functies, PST-import en eDiscovery-export, wordt momenteel geen Azure ExpressRoute ondersteund met alleen Office 365-routerings filters vanwege de afhankelijkheid van Azure Blob Storage. Als u deze functies wilt gebruiken, moet u verbinding maken met Azure-Blobopslag, met behulp van ondersteunde Azure-connectiviteitsopties, waaronder Internet verbinding of Azure ExpressRoute met openbare router filters van Azure. U moet de totstandkoming van een dergelijke verbinding voor beide functies evalueren. Het Office 365 Information Protection-Team is op de hoogte van dit probleem en werkt actief om ondersteuning te bieden voor Azure ExpressRoute voor Office 365, als beperkt tot Office 365-routefilters voor beide functies.

- Er zijn extra optionele eindpunten voor Microsoft 365-apps voor ondernemingen die niet worden vermeld en niet vereist zijn voor gebruikers om Microsoft 365-apps voor Enterprise-toepassingen te starten en documenten te bewerken. Optionele eindpunten worden gehost in Microsoft-datacenters en kunnen geen klantgegevens verwerken, verzenden of opslaan. U wordt aangeraden dat gebruikers verbindingen met deze eindpunten worden doorgestuurd naar de standaardverbinding voor Internet.
