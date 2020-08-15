---
title: Gebruikerservaring in een omgeving met meerdere geografische omgevingen
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
description: Meer informatie over de gebruikerservaring voor SharePoint, OneDrive en Exchange in een omgeving met meerdere geografische gebruikers voor Microsoft 365.
ms.openlocfilehash: c94fc5569a5444ca6361712f57460cf0c977b18e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689109"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Gebruikerservaring in een omgeving met meerdere geografische omgevingen

Hier ziet u wat uw gebruikers te zien krijgen in een configuratie van OneDrive voor meerdere gebruikers:

## <a name="exchange-mailbox"></a>Exchange-postvak

Het Exchange-postvak van een gebruiker wordt ingericht en de locatie van het Exchange-postvak wordt automatisch gewijzigd als de persoonlijke voorkeuren worden gewijzigd. Gebruikers kunnen standaard Outlook en de webversie van Outlook gebruiken zonder verandering in de gebruikerservaring in een omgeving met meerdere geografische omgevingen.

## <a name="hub-sites"></a>Hub-sites

SharePoint-sites verbeteren de detectie en afspraak met inhoud voor werknemers en maken een compleet en consistent uiterlijk van projecten, afdelingen en regio's. In een omgeving met meerdere geografische locaties kunnen sites van satelliet locaties eenvoudig worden gekoppeld aan een hubsite, ongeacht de geografische locatie van de hub. Gebruikers kunnen zoeken naar resultaten met een enkele zoekervaring, ongeacht de geografische locatie van de sites.

## <a name="microsoft-365-app-launcher"></a>Startprogramma voor Microsoft 365-app

Het startprogramma voor apps is een meervoudige geo-detectie en stuurt elke tegel door naar de juiste geografische locatie van de werkbelasting. De SharePoint-en OneDrive-tegels verwijzen naar de locatie van de geografische locatie voor de ingerichte gebruiker. Dit betekent dat de gebruiker een OneDrive heeft op de centrale locatie, de SharePoint-tegel van de SharePoint-site op de centrale locatie en de groepssite wordt ingericht op de locatie die hoort bij de persoonlijke voornaam. 

## <a name="office-applications"></a>Office-toepassingen

Office-toepassingen zoals Word, Excel en PowerPoint detecteren automatisch de juiste geografische locatie van OneDrive voor bedrijven voor elke gebruiker wanneer ze me aanmelden. Gebruikers hoeven geen geo-specifieke URL voor hun OneDrive-of SharePoint-site in te voeren.

## <a name="onedrive-for-business-sync-client"></a>Synchronisatie-synchronisatieclient van OneDrive voor bedrijven

Met de Synchronisatieclient van OneDrive voor bedrijven (versie 17.3.6943.0625 en hoger) wordt automatisch de juiste geografische OneDrive voor bedrijven-geografische locatie voor de gebruiker gedetecteerd. De ondersteuning voor synchronisatieclient bevat de mogelijkheid om op groepen gebaseerde sites te synchroniseren, ongeacht de geografische locatie. Houd er rekening mee dat de synchronisatieclient van Groove niet wordt ondersteund voor meervoudige geo. 

## <a name="onedrive-for-business-location"></a>Locatie van OneDrive voor bedrijven

Gebruikers hebben hun OneDrive voor bedrijven-gegevens op hun voorkeurs locatie. Als een gebruiker naar een OneDrive-URL gaat die een onjuiste geografische locatie bevat (zoals een bladwijzer van een vorige geografische locatie), wordt deze automatisch omgeleid naar de OneDrive op de juiste geografische locatie.

## <a name="onedrive-ios-and-android"></a>OneDrive iOS en Android 

De mobiele apps van OneDrive en Android tonen u uw OneDrive-bestanden en-bestanden die met u zijn gedeeld, ongeacht de geografische locatie. Wanneer u zoekt in de mobiele OneDrive-apps, worden relevante resultaten weergegeven van alle geo-locaties. Download de nieuwste versie van deze apps.

Zie [onedrive voor IOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) gebruiken en [Onedrive voor Android gebruiken](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) voor meer informatie.

## <a name="onedrive-mobile-client"></a>Mobiele OneDrive-client 

De mobiele OneDrive-client is multigeo-bekend en geeft relevante inhoud en resultaten weer van alle geo-locaties.

## <a name="search"></a>Vinden

Elke geografische locatie heeft een eigen zoekindex en een zoekcentrum. Wanneer een gebruiker zoekt, wordt de query naar alle geo-locaties verzonden en worden de geretourneerde resultaten samengevoegd en vervolgens weergegeven zodat de gebruiker een uniform resultaat krijgt. Gebruikers krijgen resultaten van alle geografische locaties, ongeacht hun eigen geografische locatie. Zie [Configure Search for OneDrive voor bedrijven-meerdere geografische](configure-search-for-multi-geo.md) versies voor specifieke gebruikers.

De volgende zoek clients worden ondersteund:

-   OneDrive voor Bedrijven

-   Delve

-   SharePoint-Startpagina

-   Het zoekcentrum

-   Aangepaste zoektoepassingen die gebruikmaken van de zoek-API van SharePoint

## <a name="sharepoint-home"></a>SharePoint-Startpagina 

In SharePoint wordt uw SharePoint-start gehost op de locatie waar de gebruiker zich bevindt, zoals wordt bepaald door de locatie van OneDrive voor bedrijven. Wanneer de gebruiker zijn of haar OneDrive host in een locatie van een Europese satelliet, wordt de startpagina van SharePoint van Europa weergegeven. SharePoint Home omvat alle inhoud die relevant is voor de gebruiker, ongeacht de geografische locatie. 

**Gevolgde sites, Nieuws van sites, recente sites, veelgebruikte sites en voorgestelde sites**

Alle onderdelen worden weergegeven voor de gebruiker, ongeacht de geografische locatie waarop de inhoud wordt gehost, zodat de gebruiker toegang heeft tot de inhoud. 

**Koppelingen van functies**

Beheerders kunnen aanbevolen koppelingen op de site van SharePoint naar de geografische locatie instellen. Hiermee kan de beheerder voor elke regio de juiste koppelingen gebruiken voor gebruikers in het gebied. 

## <a name="sharepoint-mobile-client"></a>Mobiele SharePoint-client 

De mobiele SharePoint-client is multigeo-bekend en geeft relevante inhoud en resultaten weer van alle geo-locaties.

## <a name="sharing"></a>Delen

Met de ervaring voor het kiezen van personen ziet u alle gebruikers, ongeacht hun geografische locatie. Hiermee kan een gebruiker de geografische locaties van de Tenant delen met een andere gebruiker of op een andere locatie. Inhoud van verschillende geografische locaties wordt weergegeven in de weergave **gedeeld met mij** in de OneDrive voor bedrijven van de gebruiker en kan worden geopend met de functie voor eenmalige aanmelding, ongeacht van de geografische locatie waarop de app wordt gehost.

## <a name="teams-experience"></a>Ervaring met teams

Teams is voor meerdere geografische detectie. OneDrive-bestanden en onlangs bekeken bestanden worden weergegeven, ongeacht de geografische locatie van de gebruiker. @ vermeldingen werken met gebruikers van alle geografische locaties.

## <a name="user-profiles"></a>Gebruikersprofielen

Gebruikersprofielgegevens zijn gemasters op de geografische locatie van de gebruiker. Wanneer u een gebruiker selecteert, wordt u omgeleid naar de gewenste geografische locatie voor de gebruiker, waar u de volledige profielgegevens kunt zien.

Als Delve is uitgeschakeld, ziet u de klassieke profiel ervaring in SharePoint, die geen ondersteuning bieden voor meerdere geo.


