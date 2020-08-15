---
title: Locatie Services voor Microsoft 365-netwerkconnectiviteit
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/31/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Locatie Services voor Microsoft 365-netwerkconnectiviteit
ms.openlocfilehash: e614e719069a74ea087b07ca624ae0450790c763
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689371"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Locatie Services voor Microsoft 365-netwerkconnectiviteit

In het Microsoft 365-Beheercentrum ziet u nu de **aanbevelingen voor netwerk inzichten en prestaties**, die metrische gegevens van een dynamische prestaties van uw microsoft 365-Tenant verzamelen en alleen kunnen worden weergegeven door beheerders gebruikers in uw Tenant. De netwerkverbinding van de organisatie is ontwikkeld via een netwerklocatie op het internet. Microsoft 365-clientconnectiviteit maakt gebruik van die route en vervolgens op internet naar Microsoft-server voor Microsoft-deur. Het identificeren van Office-locaties is de sleutel om deze netwerk inzichten te kunnen weergeven.

## <a name="location-in-network-measurements"></a>Locatie in netwerk afmetingen

De beheerder van een organisatie kan zich afmelden voor de locatie die moet worden opgenomen in de netwerk metingen die door deze functie worden gebruikt. Hiermee kunt u automatisch opsporen van de plaats waar u Office bevindt. Locatiegegevens zijn niet nauwkeurig en zijn van 300m en gecategoriseerd op plaats. Op het moment dat de locatie wordt vastgelegd op een Windows-apparaat, wordt het pictogram voor de **locatie in het deel** venster weergegeven in het systeemvak en beheerders kunnen gebruikers hierover informeren. Met deze verwerking wordt de locatie behandeld als de kantoorlocatie van de organisatie en niet de locatie van een persoon of een apparaat. Netwerk inzichten kunnen worden weergegeven op deze gedetecteerde Office-locatie steden. Als u de aanbevelingen nauwkeuriger vindt, kunt u een beheerder bepaalde adressen van de Office-locaties invoeren en de netwerk inzichten worden geaggregeerd in plaats daarvan. Office-locaties kunnen niet dichter bij 300 meter worden geaggregeerd.

## <a name="location-in-the-microsoft-365-admin-center"></a>Locatie in het Microsoft 365-Beheercentrum

In het Microsoft 365-Beheercentrum worden Bing Maps-besturingselementen gebruikt om te laten zien waar de kantoorlocaties van de organisatie zijn en om de topologie voor netwerkverbindingen voor een geselecteerde kantoorlocatie weer te geven. Wanneer een beheerder specifiek adresgegevens voor Office-locaties toevoegt, worden met Bing Maps ook adressen voorgesteld voor het eenvoudiger maken van gegevensinvoer.

## <a name="terms-of-use"></a>Gebruiksvoorwaarden

Alle inhoud die u hebt verkregen via Bing Maps, waaronder geocodes, kan alleen worden gebruikt binnen het product waarop de inhoud wordt verstrekt. Het gebruik van de functie Services van het Microsoft 365-Beheercentrum, dat wordt beheerd door Bing Maps, is onderworpen aan de _Gebruiksvoorwaarden voor eindgebruikers van Bing Maps_ op de <https://go.microsoft.com/?linkid=9710837> privacyverklaring en de _privacyverklaring van Microsoft_ zijn beschikbaar op <https://go.microsoft.com/fwlink/?LinkID=248686.>

Deze functie, geleverd via Bing Maps, wordt ook door deze **technologieën**ondersteund. De werking van Bing Maps via Bing Maps wordt bepaald door de _Service voorwaarden van de volgende technologieën_ , verkrijgbaar op <https://legal.here.com/en-gb/terms> .
