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
description: Meer informatie over het plannen van microsoft Viva-onderwerpen
ms.openlocfilehash: 19baf8bdcfdd1fe38d64e3c2f259ace1ceab5a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925974"
---
# <a name="plan-for-microsoft-viva-topics"></a>Microsoft Viva-onderwerpen plannen

U hebt de controle over de manier waarop onderwerpen worden ervaren in uw organisatie. Uw planningsbeslissingen voor Onderwerpen zorgen ervoor dat onderwerpen van hoge kwaliteit worden weergegeven aan uw gebruikers en dat ze de juiste machtigingen hebben om kennis te gebruiken en bij te dragen.

In dit artikel gaan we in op de volgende planningsbeslissingen:

- Welke SharePoint-sites u wilt crawlen naar onderwerpen
- Welke onderwerpen u wilt uitsluiten van onderwerpervaringen
- Voor welke gebruikers u onderwerpen zichtbaar wilt maken
- Welke gebruikers u machtigingen wilt geven voor het beheren van onderwerpen in het onderwerpcentrum
- Welke gebruikers u machtigingen wilt geven voor het maken of bewerken van onderwerpen in het onderwerpcentrum
- Welke naam u wilt geven aan uw onderwerpcentrum

De beveiliging en privacy van uw gegevens wordt gerespecteerd en door onderwerpervaringen krijgen gebruikers geen extra toegang tot bestanden waar ze geen rechten op hebben. We raden u aan microsoft Viva Topics beveiliging [en privacy](topic-experiences-security-privacy.md) ook te lezen als onderdeel van uw planningsproces.

## <a name="requirements"></a>Vereisten

U moet zijn [geabonneerd](https://www.microsoft.com/microsoft-viva/topics) op Viva Topics en een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-beheercentrum en Onderwerpen in te stellen.

Alle gebruikers die Onderwerpen gaan gebruiken, hebben een **licentie Onderwerpervaringen** nodig. Het toewijzen van licenties valt onder [Microsoft Viva-onderwerpen instellen.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Onderwerpdetectie

De instellingen voor onderwerpdetectie geven aan welke SharePoint-sites worden gebruikt als bronnen voor onderwerpen. U kunt ervoor kiezen om alle SharePoint-sites, een specifieke lijst met sites of geen sites op te nemen. U wordt aangeraden alle sites te kiezen, zodat u met onderwerpervaringen een groot aantal goede onderwerpen voor uw gebruikers kunt ontdekken.

Wanneer u Onderwerpen in stelt, kunt u kiezen uit de volgende opties:

- **Alle sites:** Alle SharePoint-sites in uw organisatie. Dit geldt ook voor huidige en toekomstige sites.
- **Alle, behalve geselecteerde sites:** Alle sites, behalve de sites die u opgeeft. Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie. 
- **Alleen geselecteerde sites:** Alleen de sites die u opgeeft. Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.
- **Geen sites:** Neem geen SharePoint-sites op.

Als u Alle **kiest, behalve geselecteerde sites** of Alleen geselecteerde **sites,** kunt u een CSV-bestand uploaden met een lijst met sites. Deze opties zijn handig als u een pilot doet en u een beperkt aantal sites wilt opnemen om te starten.

U kunt de CSV-sjabloon hieronder kopiëren:

``` csv
Site name,URL
```

We raden u niet aan geen **sites te kiezen,** omdat hiermee wordt voorkomen dat onderwerpen automatisch worden gemaakt of bijgewerkt. U kunt deze optie echter kiezen als u Onderwerpen wilt instellen en later sites wilt toevoegen.

Het is raadzaam om een proces te maken voor gebruikers of kennisbeheerders om afzonderlijke sites op te vragen, indien nodig in uw organisatie, uit onderwerpdetectie te verwijderen.

### <a name="multi-geo"></a>Multi-geo

Als uw organisatie [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)heeft geïmplementeerd, is het onderwerpcentrum ingericht op de centrale locatie en kunnen alleen SharePoint-sites op de centrale locatie worden gebruikt als bronnen voor onderwerpen. (Als u Alle **sites selecteert,** worden in Viva-onderwerpen alle sites op de centrale locatie gebruikt.)

Alle verwerking en opslag van inhoud gebeurt op de centrale locatie.

## <a name="user-permissions"></a>Gebruikersmachtigingen

De gebruikersmachtigingen die u opgeeft, bepalen welke personen in uw organisatie met onderwerpen werken en wat ze kunnen doen.

*Onderwerpen beheren*

Kennismanagers houden toezicht op de kwaliteit van informatie, de gestructureerde en andere best practices in uw organisatie. Ze kunnen onderwerpen bevestigen en afwijzen.

Hoewel u afzonderlijke onderwerpmanagers kunt opgeven, raden we u aan een beveiligingsgroep te maken (of een bestaande groep te gebruiken) met de personen die u kennisbeheerders wilt zijn. U kunt deze beveiligingsgroep opgeven tijdens het installatieproces.

*Onderwerpen maken en bewerken*

Onderwerpcontribuanten zijn de kampioenen en experts in uw organisatie. Ze kunnen onderwerpen maken en bewerken. 

U wordt aangeraden iedereen in uw organisatie toe te staan onderwerpen te maken en te bewerken, omdat onderwerpervaringen het beste werken wanneer alle gebruikers informatie kunnen delen.

Als u het maken en bewerken van onderwerpen wilt beperken tot specifieke personen of groepen, maakt u een beveiligingsgroep voor hen en geeft u deze op tijdens het installatieproces.

U kunt ervoor kiezen om niemand toe te staan bij te dragen aan onderwerpen, maar dit wordt niet aanbevolen. Kennisbeheerders kunnen nog steeds onderwerpen bewerken en maken als u deze optie kiest.

*Onderwerpkijkers*

Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages. Gebruikers kunnen alleen gevonden onderwerpen zien wanneer ze toegang hebben tot de bestanden en pagina's waarin het onderwerp is gevonden.

Wanneer u onderwerpkijkers instelt, kunt u kiezen uit:

- **Iedereen in mijn organisatie**
- **Alleen geselecteerde personen of beveiligingsgroepen**
- **Niemand**

We raden **Iedereen in mijn organisatie** aan, maar als u een pilot doet, wilt u mogelijk alleen geselecteerde personen of beveiligingsgroepen kiezen. U kunt ook **Niemand kiezen als** u Onderwerpen wilt instellen, maar personen nog geen onderwerpen mogen laten zien. (Kennismanagers hebben nog steeds toegang om ze de onderwerpen te laten bekijken en te helpen bij de beslissing om Onderwerpen breed beschikbaar te maken.)

## <a name="knowledge-rules"></a>Kennisregels

Als beheerder kunt u bepaalde onderwerpen uitsluiten van onderwerpervaringen. Dit is handig als u wilt voorkomen dat gevoelige gegevens in onderwerpen worden weergegeven. Hoewel kennismanagers onderwerpen in het onderwerpcentrum kunnen uitsluiten, zijn onderwerpen die door de beheerder zijn uitgesloten, zelfs niet zichtbaar voor kennisbeheerders. (Kennisbeheerders kunnen ook onderwerpen in het onderwerpcentrum verwijderen na de ontdekking.)

Als u onderwerpen op beheerdersniveau wilt uitsluiten, moet u deze toevoegen aan een CSV-bestand en het bestand uploaden. U kunt dit doen tijdens de installatie of later.

Het CSV-bestand moet de volgende parameters bevatten:

- **Naam:** Typ de naam van het onderwerp dat u wilt uitsluiten. U kunt dit op twee manieren doen:
- **MatchType-Exact/Gedeeltelijk:** Typ of de opgegeven naam *een exact* of *gedeeltelijk overeenkomend* type was.
    - Exacte overeenkomst: U kunt de exacte naam of het acroniem (bijvoorbeeld *Contoso* of *ATL) opnemen.*
    - Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.  Met een *boog worden bijvoorbeeld* alle onderwerpen uitgesloten met de woordboog in de boog, zoals boogcirkel, lassen van de boog van Het *plasma* of *Trainingsboog.*   Houd er rekening mee dat onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, niet worden *uitgesloten.*
- **Staat voor (optioneel)**: (ook wel uitbreiding *genoemd)* Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

U kunt de csv-sjabloon hieronder kopiëren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Beheer

Wanneer u Onderwerpen instelt, als onderdeel van het installatieproces, wordt automatisch een onderwerpcentrum gemaakt. Bedenk wat u het onderwerpcentrum wilt noemen en wat u wilt dat de URL is. U kunt zowel de naam als de URL instellen als onderdeel van het installatieproces en u kunt de naam (maar geen URL) later wijzigen in het Microsoft 365-beheercentrum. U kunt maar één onderwerpcentrum hebben.

## <a name="setup-checklist"></a>Controlelijst instellen

Wanneer u onderwerpervaringen instelt, hebt u de volgende items nodig terwijl u door de installatiewizard gaat:

> [!div class="checklist"]
> * Lijst met sites die u wilt opnemen of uitsluiten als niet alle sites worden opgenomen voor onderwerpdetectie
> * Beveiligingsgroep voor onderwerpkijkers als niet alle gebruikers onderwerpen mogen bekijken
> * Beveiligingsgroep voor onderwerpcontribuanten als niet alle gebruikers onderwerpen mogen maken en bewerken
> * Beveiligingsgroep voor onderwerpkennisbeheerders als niet alle gebruikers onderwerpen mogen beheren
> * Lijst met gevoelige onderwerpen die u wilt uitsluiten van onderwerpdetectie
> * Een naam voor uw onderwerpcentrumsite

## <a name="see-also"></a>Zie ook

[Onderwerpservaringen instellen](set-up-topic-experiences.md)

[Onderwerpdetectie beheren in Microsoft 365](topic-experiences-discovery.md)

[Zichtbaarheid van onderwerp beheren in Microsoft 365](topic-experiences-knowledge-rules.md)

[Onderwerpmachtigingen beheren in Microsoft 365](topic-experiences-user-permissions.md)

[De naam van het onderwerpcentrum wijzigen in Microsoft 365](topic-experiences-administration.md)
