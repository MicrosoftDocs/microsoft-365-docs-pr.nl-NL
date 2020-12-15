---
title: Onderwerp ervaring plannen in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het plannen van onderwerpen in Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668154"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a>Onderwerp ervaring plannen in Microsoft 365

U bepaalt zelf hoe de onderwerpen in uw organisatie worden ervaren. Met uw plannings beslissingen voor de ervaringen van een onderwerp zorgt u ervoor dat de producten van hoge kwaliteit voor uw gebruikers worden weergegeven en dat ze de juiste machtigingen hebben om kennis te maken en Contribute te gebruiken.

In dit artikel worden deze plannings beslissingen onderzocht:

- De SharePoint-sites die u wilt verkennen voor onderwerpen.
- Welke onderwerpen, indien van toepassing, wilt u uitsluiten van onderwerp-ervaringen
- De gebruikers van wie u de onderwerpen zichtbaar wilt maken.
- Welke gebruikers u machtigingen wilt geven om onderwerpen te beheren in het onderwerp centrum.
- Welke gebruikers u machtigingen wilt geven om onderwerpen te maken of te bewerken in het onderwerp centrum.
- De naam van het onderwerp dat u wilt geven.

Beveiliging en privacy van uw gegevens worden geëerbiedigd en de onderwerp-ervaringen geven gebruikers geen toegang meer tot de bestanden waartoe ze geen rechten hebben. U wordt aangeraden ook een onderwerp te lezen dat op het gebied van uw planningsproces [beveiliging en privacy te](topic-experiences-security-privacy.md) maken heeft.

## <a name="requirements"></a>Vereisten

U moet een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-Beheercentrum en de functies voor het onderwerp in te stellen.

Voor alle gebruikers die de functies voor het gebruik van een onderwerp gaan gebruiken, is een licentie voor de **onderwerp-ervaring** vereist. Het toewijzen van licenties valt onder de functies voor het instellen van het [onderwerp](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Onderwerp detecteren

De instellingen voor de detectie van het onderwerp opgeven welke SharePoint-sites worden gebruikt als bronnen voor onderwerpen. U kunt ervoor kiezen om alle SharePoint-sites, een specifieke lijst met sites of geen sites op te nemen. We raden u aan om alle sites te kiezen, zodat de functies van het onderwerp een groot aantal goede onderwerpen kunnen ontdekken voor uw gebruikers.

Wanneer u onderwerpeert, kunt u kiezen uit de volgende opties:

- **Alle sites**: alle SharePoint-sites in uw organisatie. Dit geldt ook voor huidige en toekomstige sites.
- **Alles, met uitzondering van geselecteerde sites**: alle sites, behalve voor de accounts die u opgeeft. Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp. 
- **Alleen geselecteerde sites**: alleen de sites die u opgeeft. Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.
- **Geen sites**: geen SharePoint-sites opnemen.

Als u alle selecteert **, met uitzondering van geselecteerde sites** of **alleen geselecteerde sites**, kunt u een CSV-bestand uploaden met een lijst met sites. Deze opties zijn handig als u een pilot uitvoert en u een beperkt aantal sites wilt toevoegen om te starten.

U kunt de. CSV-sjabloon hieronder kopiëren:

``` csv
Site name,URL
```

We raden u niet aan **geen sites** te kiezen omdat het voorkomt dat onderwerpen automatisch worden gemaakt of bijgewerkt. U kunt echter deze optie selecteren als u topic Experience wilt instellen en later sites wilt toevoegen.

We raden u aan om een proces te maken voor gebruikers of kennis beheerders die de aanvraaging van de onderwerps detectie indien nodig in uw organisatie.

## <a name="user-permissions"></a>Gebruikersmachtigingen

De gebruikersmachtigingen die u opgeeft, bepalen welke personen in uw organisatie werken met onderwerpen en wat ze kunnen doen.

*Onderwerpen beheren*

Kennis beheerders houden de kwaliteit van de informatie over, hoe de gestructureerd en andere aanbevolen procedures in uw organisatie. Ze kunnen onderwerpen bevestigen en negeren.

U kunt ook afzonderlijke onderwerpen van een onderwerp opgeven, maar u kunt wel een beveiligingsgroep maken (of een bestaande maken) met de personen die u willen weten. U kunt deze beveiligingsgroep tijdens het installatieproces opgeven.

*Onderwerpen maken en bewerken*

Medewerkers in het leiders zijn de experts van de onderhevige experts van uw organisatie. Ze kunnen onderwerpen maken en bewerken. 

We raden u aan om iedereen in uw organisatie in staat te stellen onderwerpen te maken en bewerken omdat de functies voor het gebruik van onderwerpen het beste werken wanneer alle gebruikers informatie kunnen delen.

Als u het maken en bewerken van onderwerpen wilt beperken tot specifieke personen of groepen, maakt u hiervoor een beveiligingsgroep en geeft u deze op tijdens het installatieproces.

U kunt ervoor kiezen dat iedereen geen bijdrage biedt aan onderwerpen, maar dit wordt niet aanbevolen. Kennis beheerders kunnen nog steeds onderwerpen bewerken en maken.

*Onderwerp viewers*

De bezoekers van een onderwerp kunnen op de pagina met zoekresultaten en wanneer onderwerpen zijn gemarkeerd in de inhoud van de SharePoint-pagina's. Gebruikers kunnen alleen ontdekte onderwerpen zien wanneer ze toegang hebben tot de bestanden en pagina's waarvan het onderwerp is gevonden.

Wanneer u topic viewers instelt, kunt u kiezen uit:

- **Iedereen binnen mijn organisatie**
- **Alleen geselecteerde personen of beveiligingsgroepen**
- **Niemand**

We raden **iedereen binnen mijn organisatie** aan, maar als u een pilot uitvoert, kunt u alleen geselecteerde personen of beveiligingsgroepen kiezen. U kunt **er** ook voor kiezen om het onderwerp in te stellen, maar u kunt geen onderwerpen weergeven. (Kennis managers hebben nog steeds toegang tot de onderwerpen) en Help met de beslissing om de functies van het onderwerp algemeen beschikbaar te maken.)

## <a name="knowledge-rules"></a>Kennis regels

Als beheerder kunt u bepaalde onderwerpen uitsluiten van topic experiences. Dit is handig als u wilt voorkomen dat gevoelige gegevens in onderwerpen worden weergegeven. Hoewel kennis beheerders onderwerpen in het onderwerp centrum kunnen uitsluiten, zijn de onderwerpen die door de beheerder worden uitgesloten niet zichtbaar voor de kennis managers. (Kennis managers kunnen ook onderwerpen in het onderwerp centrum verwijderen na ontdekking.)

Als u onderwerpen wilt uitsluiten van het niveau van de beheerder, moet u deze toevoegen aan een CSV-bestand en het bestand uploaden. U kunt dit doen tijdens de installatie of later.

Het. CSV-bestand moet de volgende parameters bevatten:

- **Naam**: Typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
- **MatchType-exact/gedeeltelijk**: Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.
    - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.
    - Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.  Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel*, *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur*, niet worden uitgesloten.
- **Staat voor (optioneel)**: (ook wel bekend als *expansie*) als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/exclude-topics-csv.png) 

U kunt de onderstaande CSV-sjabloon kopiëren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Beheer

Wanneer u onderwerpings functies instelt, wordt er automatisch een onderwerpvenster gemaakt als onderdeel van het installatieproces. Denk na over de naam van het onderwerp en wat u wilt dat de URL wordt. U kunt zowel de naam als de URL instellen als onderdeel van het installatieproces, en u kunt de naam (maar niet de URL) wijzigen in het Microsoft 365-Beheercentrum. U kunt maar één onderwerp centreren.

## <a name="setup-checklist"></a>Installatie Controlelijst

Wanneer u onderwerpeert, hebt u de volgende items nodig wanneer u door de installatiewizard gaat:

> [!div class="checklist"]
> * Lijst met sites die u wilt opnemen in of uitsluiten van alle websites voor de detectie van het onderwerp
> * Beveiligingsgroep voor bezoekers van het onderwerp als u niet alle gebruikers de mogelijkheid wilt bieden om onderwerpen weer te geven
> * Beveiligingsgroep voor inzenders van een onderwerp, indien niet alle gebruikers de mogelijkheid bieden om onderwerpen te maken en bewerken
> * Beveiligingsgroep voorkennis managers van het onderwerp als u niet alle gebruikers de mogelijkheid wilt bieden om onderwerpen te beheren
> * Lijst met gevoelige onderwerpen die de detectie van het onderwerp uitsluiten
> * Een naam voor de onderwerpen centrum site

## <a name="see-also"></a>Zie ook

[Ervaring met het onderwerp instellen](set-up-topic-experiences.md)

[Detectie van onderwerp beheren in Microsoft 365](topic-experiences-discovery.md)

[De zichtbaarheid van een onderwerp beheren in Microsoft 365](topic-experiences-knowledge-rules.md)

[Machtigingen voor onderwerp beheren in Microsoft 365](topic-experiences-user-permissions.md)

[De naam van het onderwerp centreren in Microsoft 365](topic-experiences-administration.md)
