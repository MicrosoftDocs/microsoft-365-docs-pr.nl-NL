---
title: Microsoft Viva-onderwerpen plannen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Meer informatie over het plannen van Microsoft Viva-onderwerpen
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107952"
---
# <a name="plan-for-microsoft-viva-topics"></a>Microsoft Viva-onderwerpen plannen

U kunt zelf bepalen hoe u onderwerpen ervaren in uw organisatie. Uw planningsbeslissingen voor Onderwerpen garanderen dat onderwerpen van hoge kwaliteit worden weergegeven aan uw gebruikers en dat ze over de juiste machtigingen voor het gebruik en bijdragen van kennis zijn.

In dit artikel worden de volgende planningsbeslissingen beschreven:

- Welke SharePoint-sites u wilt crawlen voor onderwerpen
- Welke onderwerpen u indien van onderwerpervaringen wilt uitsluiten
- Voor welke gebruikers u onderwerpen zichtbaar wilt maken
- Welke gebruikers u machtigingen wilt geven voor het beheren van onderwerpen in het onderwerpcentrum
- Welke gebruikers u machtigingen wilt geven om onderwerpen te maken of te bewerken in het onderwerpcentrum
- Welke naam u het onderwerpcentrum wilt geven

De beveiliging en privacy van uw gegevens wordt in acht genomen en door onderwerpervaringen hebben gebruikers geen extra toegang tot bestanden waar ze geen rechten voor hebben. U wordt aangeraden ook de beveiliging en [privacy van Microsoft Viva-onderwerpen](topic-experiences-security-privacy.md) te lezen als onderdeel van uw planningsproces.

## <a name="requirements"></a>Vereisten

U moet een globale beheerder of Een SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-beheercentrum en Onderwerpen in te stellen.

Alle gebruikers die Onderwerpen gaan gebruiken, hebben een **licentie voor Onderwerpervaringen** nodig. Het toewijzen van licenties is mogelijk in [Microsoft Viva-onderwerpen instellen.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Onderwerpdetectie

Met de instellingen voor onderwerpdetectie kunt u opgeven welke SharePoint-sites als bronnen voor onderwerpen worden gebruikt. U kunt ervoor kiezen om alle SharePoint-sites, een specifieke lijst met sites of geen sites op te nemen. U wordt aangeraden alle sites te kiezen, zodat u met onderwerpervaringen een groot aantal goede onderwerpen voor uw gebruikers kunt ontdekken.

Wanneer u Onderwerpen in stelt, kunt u kiezen uit de volgende opties:

- **Alle sites:** alle SharePoint-sites in uw organisatie. Dit geldt ook voor huidige en toekomstige sites.
- **Alle, behalve geselecteerde sites:** Alle sites behalve de sites die u opgeeft. Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. 
- **Alleen geselecteerde sites:** alleen de sites die u opgeeft. Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.
- **Geen sites:** Geen SharePoint-sites opnemen.

Als u Alle **kiest, met uitzondering** van geselecteerde sites of Alleen geselecteerde **sites,** kunt u een CSV-bestand met een lijst met sites uploaden. Deze opties zijn handig als u een testfase hebt en een beperkt aantal sites wilt opnemen om te starten.

U kunt de CSV-sjabloon hieronder kopiëren:

``` csv
Site name,URL
```

U wordt niet aangeraden Geen **sites te kiezen,** omdat hiermee wordt voorkomen dat onderwerpen automatisch worden gemaakt of bijgewerkt. U kunt deze optie echter kiezen als u Onderwerpen wilt instellen en later sites wilt toevoegen.

U wordt aangeraden een proces te maken voor gebruikers of kennisbeheerders om zo nodig in uw organisatie aan te vragen dat afzonderlijke sites worden verwijderd uit onderwerpdetectie.

## <a name="user-permissions"></a>Gebruikersmachtigingen

De gebruikersmachtigingen die u opgeeft, bepalen welke personen in uw organisatie interactie hebben met onderwerpen en wat ze kunnen doen.

*Onderwerpen beheren*

Kennisbeheerders zijn verantwoordelijk voor de kwaliteit van informatie, de gestructureerde en andere best practices in uw organisatie. Ze kunnen onderwerpen bevestigen en weigeren.

Hoewel u afzonderlijke onderwerpmanagers kunt opgeven, raden we u aan een beveiligingsgroep te maken (of een bestaande groep te gebruiken) die de personen bevat die kennisbeheerders moeten worden. U kunt deze beveiligingsgroep opgeven tijdens het installatieproces.

*Onderwerpen maken en bewerken*

Onderwerpbijdragers zijn de kampioenen en deskundigen op het gebied van onderwerpen in uw organisatie. Ze kunnen onderwerpen maken en bewerken. 

Het is raadzaam om iedereen in uw organisatie toe te staan onderwerpen te maken en te bewerken, omdat onderwerpervaringen het beste werken wanneer alle gebruikers informatie kunnen delen.

Als u het maken en bewerken van onderwerpen wilt beperken tot specifieke personen of groepen, maakt u een beveiligingsgroep voor hen en geeft u deze op tijdens het installatieproces.

U kunt ervoor kiezen om niemand toe te staan een bijdrage te leveren aan onderwerpen, maar dit wordt niet aanbevolen. Knowledge Managers kunnen nog steeds onderwerpen bewerken en maken als u deze optie kiest.

*Onderwerp kijkers*

Onderwerpkijkers kunnen informatie zien over onderwerppagina's, in zoekresultaten en wanneer onderwerpen zijn gemarkeerd in de inhoud, zoals SharePoint-pagina's. Gebruikers kunnen alleen gevonden onderwerpen zien wanneer ze toegang hebben tot de bestanden en pagina's waarin het onderwerp is aangetroffen.

Wanneer u onderwerpkijkers instelt, kunt u kiezen uit:

- **Iedereen in mijn organisatie**
- **Alleen geselecteerde personen of beveiligingsgroepen**
- **Niemand**

We raden **Iedereen in mijn organisatie** aan, maar als u een testfase doet, kunt u alleen geselecteerde personen of beveiligingsgroepen kiezen. U kunt ook **Nee kiezen als** u Onderwerpen wilt instellen, maar personen nog geen onderwerpen wilt laten zien. (Knowledge Managers hebben nog steeds toegang om hen toe te staan de onderwerpen te bekijken en hulp bij de beslissing om Onderwerpen algemeen beschikbaar te maken.)

## <a name="knowledge-rules"></a>Kennisregels

Als beheerder kunt u bepaalde onderwerpen uitsluiten van onderwerpervaringen. Dit is handig als u wilt voorkomen dat gevoelige gegevens in onderwerpen worden weergegeven. Hoewel kennisbeheerders onderwerpen in het onderwerpcentrum kunnen uitsluiten, zijn onderwerpen die door de beheerder worden uitgesloten zelfs niet zichtbaar voor kennismanagers. (Kennisbeheerders kunnen na detectie ook onderwerpen in het onderwerpcentrum verwijderen.)

Als u onderwerpen op beheerdersniveau wilt uitsluiten, moet u deze toevoegen aan een CSV-bestand en het bestand uploaden. U kunt dit doen tijdens de installatie of later.

Het CSV-bestand moet de volgende parameters bevatten:

- **Naam:** typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
- **MatchType-Exact/Gedeeltelijk:** typ of de naam die u hebt ingevoerd *een exact* of *gedeeltelijk* overeenkomsttype is.
    - Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen (bijvoorbeeld *Contoso* of *ATL).*
    - Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.  Zo worden met *de boog* bijvoorbeeld alle onderwerpen met de *woordcirkel* uitgesloten, zoals Boogcirkel,  *Arc-boog* of *Trainingsbogen.* Onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, worden niet *uitgesloten.*
- **Staat voor (optioneel)**: (ook wel uitbreiding *genoemd)* Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

U kunt de csv-sjabloon hieronder kopiëren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Beheer

Wanneer u Onderwerpen instelt, wordt als onderdeel van het installatieproces automatisch een onderwerpcentrum gemaakt. Bedenk wat u het onderwerpcentrum wilt noemen en wat u de URL wilt maken. U kunt zowel de naam als de URL instellen als onderdeel van het installatieproces en u kunt de naam (maar niet de URL) later wijzigen in het Microsoft 365-beheercentrum. U kunt slechts één onderwerpcentrum hebben.

## <a name="setup-checklist"></a>Controlelijst instellen

Wanneer u onderwerpervaringen instelt, hebt u de volgende items nodig tijdens het uitvoeren van de installatiewizard:

> [!div class="checklist"]
> * Lijst met sites die u wilt opnemen of uitsluiten als niet alle sites voor onderwerpdetectie worden opgenomen
> * Beveiligingsgroep voor onderwerpbekijkers als niet alle gebruikers onderwerpen kunnen bekijken
> * Beveiligingsgroep voor onderwerpbijdragers als niet alle gebruikers onderwerpen mogen maken en bewerken
> * Beveiligingsgroep voor onderwerpkennisbeheerders als niet alle gebruikers de mogelijkheid bieden om onderwerpen te beheren
> * Lijst met gevoelige onderwerpen die u wilt uitsluiten van onderwerpdetectie
> * Een naam voor uw onderwerpcentrumsite

## <a name="see-also"></a>Zie ook

[Onderwerpservaringen instellen](set-up-topic-experiences.md)

[Onderwerpdetectie beheren in Microsoft 365](topic-experiences-discovery.md)

[Zichtbaarheid van onderwerpen beheren in Microsoft 365](topic-experiences-knowledge-rules.md)

[Onderwerpmachtigingen beheren in Microsoft 365](topic-experiences-user-permissions.md)

[De naam van het onderwerpcentrum wijzigen in Microsoft 365](topic-experiences-administration.md)
