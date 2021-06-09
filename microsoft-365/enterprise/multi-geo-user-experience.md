---
title: Gebruikerservaring in een multi-geo-omgeving
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Meer informatie over de SharePoint, OneDrive en Exchange gebruikerservaring in een multi-geo-omgeving voor Microsoft 365.
ms.openlocfilehash: 558e5a1f7ff2f6f5485a9f32d6e2b43b552b7f17
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749572"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Gebruikerservaring in een multi-geo-omgeving

Dit is wat uw gebruikers zien in een OneDrive Multi-Geo configuratie:

## <a name="exchange-mailbox"></a>Exchange postvak

Het postvak van Exchange gebruiker is ingericht op de gewenste gegevenslocatie en wordt automatisch verplaatst als de PDL-locatie wordt gewijzigd. Gebruikers kunnen Outlook en Outlook op internet gebruiken zonder dat de gebruikerservaring in een omgeving met meerdere geografische gegevens wordt gewijzigd.

## <a name="hub-sites"></a>Hubsites

SharePoint Hubsites verbeteren de detectie en betrokkenheid met inhoud voor werknemers, terwijl er een volledige en consistente weergave wordt van projecten, afdelingen of regio's. In een multi-geo-omgeving kunnen sites van satellietlocaties eenvoudig worden gekoppeld aan een hubsite, ongeacht de geografische locatie van de hubsite. Gebruikers kunnen zoeken en resultaten binnen de hub krijgen via één zoekervaring, ongeacht de geografische locatie van de sites.

## <a name="microsoft-365-app-launcher"></a>Microsoft 365 start-app

Het start start- en start start-start start-element voor apps is multi-geo aware en stuurt elke tegel naar de juiste geografische locatie van de werkbelasting. De SharePoint en OneDrive-tegels geven de gebruiker de locatie aan die overeenkomt met de geolocatie van de gebruiker. Dit betekent dat de gebruiker een OneDrive op de centrale locatie heeft, dat de tegel SharePoint deze naar SP Home op de centrale locatie zal wijzen, maar dat de groepssite wordt ingericht op de locatie die overeenkomt met hun PDL. 

## <a name="office-applications"></a>Office-toepassingen

Office toepassingen zoals Word, Excel en PowerPoint worden automatisch de juiste OneDrive voor Bedrijven geolocatie voor elke gebruiker gedetecteerd wanneer ze zich aanmelden. Gebruikers hoeven de geospecifieke URL niet in te voeren voor hun OneDrive of SharePoint sites.

## <a name="onedrive-for-business-sync-client"></a>OneDrive voor Bedrijven Synchronisatieclient

De OneDrive voor Bedrijven-synchronisatieclient (versie 17.3.6943.0625 en hoger) detecteert automatisch de juiste OneDrive voor Bedrijven geolocatie voor de gebruiker. Synchronisatieclientondersteuning omvat de mogelijkheid om sites op basis van groepen te synchroniseren, ongeacht hun geografische locatie. Houd er rekening mee Groove de synchronisatieclient niet wordt ondersteund voor multi-geo. 

## <a name="onedrive-for-business-location"></a>OneDrive voor Bedrijven locatie

Gebruikers hebben hun OneDrive voor Bedrijven ingericht op hun gewenste gegevenslocatie. Als een gebruiker naar een OneDrive-URL navigeert die een onjuiste geografische locatie bevat (zoals een bladwijzer van een vorige geografische locatie), worden deze automatisch omgeleid naar de OneDrive op de juiste geografische locatie.

## <a name="onedrive-ios-and-android"></a>OneDrive iOS en Android 

In OneDrive mobiele iOS- en Android-apps ziet u uw OneDrive bestanden en bestanden die met u worden gedeeld, ongeacht hun geografische locatie. Zoeken vanuit de OneDrive mobiele apps geeft relevante resultaten weer van alle geografische locaties. Download de nieuwste versie van deze apps.

Zie Gebruik [OneDrive voor iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) [en Gebruik OneDrive voor Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) voor meer informatie.

## <a name="onedrive-mobile-client"></a>OneDrive Mobiele client 

De OneDrive Mobile Client is multi-geo aware en geeft relevante inhoud en resultaten van alle geografische locaties weer.

## <a name="search"></a>Zoeken

Elke geografische locatie heeft een eigen zoekindex en zoekcentrum. Wanneer een gebruiker zoekt, wordt de query naar alle geografische locaties verzonden en worden de geretourneerde resultaten samengevoegd en vervolgens gerangschikt, zodat de gebruiker geïntegreerde resultaten krijgt. Gebruikers krijgen resultaten van alle geografische locaties, ongeacht hun eigen geografische locatie. Zie [Zoeken naar OneDrive voor Bedrijven multi-geo configureren](configure-search-for-multi-geo.md) voor specifieke informatie.

De volgende zoek clients worden ondersteund:

-   OneDrive voor Bedrijven

-   Delve

-   SharePoint Start

-   Het zoekcentrum

-   Aangepaste zoektoepassingen die gebruikmaken van de SharePoint Search API

## <a name="sharepoint-home"></a>SharePoint Start 

In SharePoint Multi-Geo uw SharePoint wordt gehost op de locatie waar de gebruiker zich bevindt, zoals bepaald door de locatie OneDrive voor bedrijven. Bijvoorbeeld: als de gebruiker zijn of haar OneDrive op een Europese satellietlocatie heeft gehost, wordt zijn of haar SharePoint vanuit Europa weergegeven. SharePoint home bevat alle inhoud die relevant is voor de gebruiker, ongeacht de geografische locatie. 

**Gevolgde sites, nieuws van sites, recente sites, veelgebruikte sites en voorgestelde sites**

Al deze onderdelen worden voor de gebruiker gebruikt, ongeacht de geografische locatie waar de inhoud wordt gehost, zolang de gebruiker machtigingen heeft voor deze inhoud. 

**Functieskoppelingen**

Beheerders kunnen aanbevolen koppelingen configureren in SharePoint home, naar eigen goed gebruik voor elke geografische locatie. Hierdoor kan de beheerder in de SP Home voor elke regio de koppelingen gebruiken die geschikt zijn voor gebruikers in de regio. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobiele client 

De SharePoint Mobile Client is multi-geo aware en geeft relevante inhoud en resultaten weer van alle geografische locaties.

## <a name="sharing"></a>Delen

De gebruikers picker-ervaring toont alle gebruikers, ongeacht hun geografische locatie. Op deze manier kan een gebruiker delen met een andere gebruiker in dezelfde geo of op een andere geografische locatie van uw tenant. Inhoud van verschillende geografische locaties  wordt in de weergave Gedeeld met mij in de OneDrive voor Bedrijven van de gebruiker weergeven en kan worden gebruikt met Een enkele Sign-On-ervaring, ongeacht de geografische locatie waarin deze wordt gehost.

## <a name="teams-experience"></a>Teams Ervaring

Teams is multi-geo aware. OneDrive bestanden en onlangs bekeken bestanden worden weergegeven, ongeacht de geografische locatie van de gebruiker. @ vermeldingen werken met gebruikers van alle geografische locaties.

## <a name="user-profiles"></a>Gebruikersprofielen

Gebruikersprofielgegevens worden beheerst op de geografische locatie van de gebruiker. Wanneer u een gebruiker selecteert, wordt u doorgestuurd naar de juiste geografische locatie voor de gebruiker, waar u de volledige profielgegevens ziet.

Als Delve is uitgeschakeld, ziet u de klassieke profielervaring in SharePoint, die niet multi-geo-aware is.


