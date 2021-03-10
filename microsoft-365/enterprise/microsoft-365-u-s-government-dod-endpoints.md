---
title: Office 365 US Government DOD-eindpunten
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/28/2021
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
description: Office 365 vereist verbinding met internet. De onderstaande eindpunten moeten alleen bereikbaar zijn voor klanten die gebruikmaken van Office 365 U.S. Government DoD-abonnementen.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7001ac258b0c866c6b41a580394c771d192beae
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596942"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 U.S. Government DoD-eindpunten

*Van toepassing op: Office 365-beheerder*

 Office 365 vereist verbinding met internet. De onderstaande eindpunten moeten alleen bereikbaar zijn voor klanten die gebruikmaken van Office 365 U.S. Government DoD-abonnementen.
  
 **Office 365-eindpunten:** [Worldwide (inclusief GCC)](urls-and-ip-address-ranges.md)Office 365 beheerd door  |  [21 Vianet](urls-and-ip-address-ranges-21vianet.md)   |  [Office 365 Germany](microsoft-365-germany-endpoints.md)Office  |  *365 U.S. Government DoD* Office  |  [365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Laatst bijgewerkt:** 28-01-2021 - ![ Abonnement op ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-wijzigingslogboek](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Downloaden:** de volledige lijst in [JSON-indeling](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen. Eindpuntgegevens worden aan het begin van elke maand zo nodig bijgewerkt, met nieuwe IP-adressen en URL's die 30 dagen voor de actieve oproep zijn gepubliceerd. Hierdoor kunnen klanten die nog geen geautomatiseerde updates hebben, hun processen voltooien voordat nieuwe connectiviteit vereist is. Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken. De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice. Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).

De onderstaande eindpuntgegevens geven een overzicht van de vereisten voor verbinding tussen de computer van een gebruiker en Office 365. Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd. Zie Aanvullende eindpunten die niet zijn [opgenomen in de webservice voor meer informatie.](additional-office365-ip-addresses-and-urls.md) 

De eindpunten worden ingedeeld in vier servicegebieden. De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken. Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.

De getoonde gegevenskolommen zijn:

- **ID**: Het ID-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.

- **Category**: Toon of de eindpuntenset wordt gecategoriseerd als "Optimaliseren", "Toestaan" of "Standaard". U kunt meer lezen over deze categorieën en richtlijnen voor het beheer ervan [https://aka.ms/pnc](https://aka.ms/pnc) op. In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding. Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd. Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.

- **ER**: Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen. De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied. Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is. Als u Azure AD Connect wilt [](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) gebruiken, leest u de sectie speciale aandachtspunten om ervoor te zorgen dat u over de juiste Azure AD Connect-configuratie kunt zorgen.

- **Adressen**: Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven. Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.
 
- **Poorten**: Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen. Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Opmerkingen voor deze tabel:

- Het beveiligings- en compliancecentrum (SCC) biedt ondersteuning voor Azure ExpressRoute voor Office 365. Hetzelfde geldt voor veel functies die via het SCC worden belicht, zoals Rapportage, Controle, Advanced eDiscovery, Unified DLP en Gegevensbeheer. Twee specifieke functies, PST-import en eDiscovery-export, ondersteunen Azure ExpressRoute momenteel niet met alleen Office 365-routefilters vanwege hun afhankelijkheid van Azure Blob Storage. Voor het gebruik van deze functies hebt u afzonderlijke connectiviteit met Azure Blob Storage nodig met behulp van ondersteuningsopties voor Azure-connectiviteit, zoals internetconnectiviteit of Azure ExpressRoute met openbare Azure-routefilters. Voor beide functies moet u een dergelijke verbinding evalueren. Het team van Office 365 Information Protection is op de hoogte van deze beperking en werkt actief aan ondersteuning voor Azure ExpressRoute voor Office 365, beperkt tot Office 365-routefilters voor beide functies.

- Er zijn extra optionele eindpunten voor Microsoft 365-apps voor ondernemingen die niet worden weergegeven en niet zijn vereist voor gebruikers om Microsoft 365-apps voor bedrijfstoepassingen te starten en documenten te bewerken. Optionele eindpunten worden gehost in Microsoft-datacenters en verwerken, verzenden of opslaan van klantgegevens niet. Het is raadzaam dat gebruikersverbindingen met deze eindpunten worden doorgestuurd naar de standaardperimeter voor internetingressie.
