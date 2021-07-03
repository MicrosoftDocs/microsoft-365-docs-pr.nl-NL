---
title: Office 365 DoD-eindpunten van de Amerikaanse overheid
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
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
description: Voor Office 365 is een internetverbinding vereist. De onderstaande eindpunten moeten bereikbaar zijn voor klanten die alleen Office 365 U.S. Government DoD-abonnementen gebruiken.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 32a760843453a4d243ee65802325852323402140
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286427"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 DoD-eindpunten van de Amerikaanse overheid

*Van toepassing op: Office 365 Admin*

Voor Office 365 is een internetverbinding vereist. De onderstaande eindpunten moeten bereikbaar zijn voor klanten die alleen Office 365 U.S. Government DoD-abonnementen gebruiken.
  
**Office 365 eindpunten:** [Worldwide (including GCC)](urls-and-ip-address-ranges.md) Office 365 operated \| [by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) Office 365 \| [Germany](microsoft-365-germany-endpoints.md) \| *Office 365 U.S. Government DoD* Office 365 \| [U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)

<br>

****

|Opmerkingen|Downloaden|
|---|---|
|**Laatst bijgewerkt:** 28-05-2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement op wijzigingenlogboek](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Downloaden:** de volledige lijst in [JSON-indeling](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen. Eindpuntgegevens worden aan het begin van elke maand bijgewerkt zoals vereist met nieuwe IP-adressen en URL's die worden gepubliceerd 30 dagen voordat ze actief worden. Hierdoor kunnen klanten die nog geen geautomatiseerde updates hebben, hun processen voltooien voordat nieuwe connectiviteit vereist is. Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken. De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice. Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).

De onderstaande eindpuntgegevens geven een overzicht van de vereisten voor verbinding tussen de computer van een gebruiker en Office 365. Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd. Zie Aanvullende eindpunten die niet zijn [opgenomen in de webservice](additional-office365-ip-addresses-and-urls.md)voor meer informatie.

De eindpunten worden ingedeeld in vier servicegebieden. De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken. Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.

De getoonde gegevenskolommen zijn:

- **ID**: Het ID-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.

- **Category**: Toon of de eindpuntenset wordt gecategoriseerd als "Optimaliseren", "Toestaan" of "Standaard". U kunt meer lezen over deze categorieën en richtlijnen voor het beheer van deze categorieën op [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) . In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding. Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd. Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.

- **ER**: Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen. De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied. Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is. Als u azure AD-Verbinding maken wilt gebruiken, [](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) leest u de sectie Speciale aandachtspunten om ervoor te zorgen dat u de juiste Azure AD-Verbinding maken hebt.

- **Adressen**: Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven. Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.

- **Poorten**: Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen. Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.

[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Notities voor deze tabel:

- Het Beveiligings- en compliancecentrum (SCC) biedt ondersteuning voor Azure ExpressRoute voor Office 365. Hetzelfde geldt voor veel functies die via de SCC worden belicht, zoals Rapportage, Auditing, Advanced eDiscovery, Unified DLP en Data Governance. Twee specifieke functies, PST-import en eDiscovery-export, bieden momenteel geen ondersteuning voor Azure ExpressRoute met alleen Office 365-routefilters vanwege hun afhankelijkheid van Azure Blob Storage. Als u deze functies wilt gebruiken, hebt u afzonderlijke connectiviteit nodig met Azure Blob Storage met behulp van ondersteuningsopties voor Azure-connectiviteit, waaronder internetverbinding of Azure ExpressRoute met Azure Public Route-filters. U moet evalueren of u voor beide functies een dergelijke verbinding hebt. Het Office 365 Information Protection-team is op de hoogte van deze beperking en werkt actief aan ondersteuning voor Azure ExpressRoute voor Office 365, zoals beperkt tot Office 365 routefilters voor beide functies.

- Er zijn extra optionele eindpunten voor Microsoft 365-apps voor ondernemingen die niet worden vermeld en die niet vereist zijn voor gebruikers om Microsoft 365-apps voor ondernemingen te starten en documenten te bewerken. Optionele eindpunten worden gehost in Microsoft-datacenters en verwerken, verzenden of opslaan van klantgegevens niet. Het is raadzaam dat gebruikersverbindingen met deze eindpunten worden doorgestuurd naar de standaardrand van internet.
