---
title: Veilige samenwerking instellen met Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Meer informatie over het instellen van veilige samenwerking aan inhoud in Teams om uw gegevens te beschermen op basis van de gevoeligheid.
ms.openlocfilehash: c7881328da2ef78d043b12db29f50b961d79b2cb
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423991"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Veilige samenwerking instellen met Microsoft 365

Het gemakkelijk kunnen delen van informatie met de juiste personen en het voorkomen van te veel delen is belangrijk voor het succes van een organisatie. Dit houdt onder andere in dat u gevoelige gegevens veilig kunt delen met alleen personen die er toegang toe moeten hebben. Afhankelijk van het project kan dit het delen van gevoelige gegevens omvatten met personen buiten uw organisatie.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Deze richtlijnen voor samenwerkingsoplossing bevatten twee onderdelen die u kunnen helpen:
- Microsoft Teams implementeren met het juiste beschermingsniveau voor elk project
- Extern delen configureren met de juiste beveiligingsinstellingen voor elk project

![Teams implementeren met de juiste beveiliging en extern delen configureren met de juiste beveiligingsinstellingen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Als er geen veelzijdige en eenvoudig te gebruiken hulpmiddelen voor samenwerking aan inhoud beschikbaar zijn, werken gebruikers vaak samen door documenten per e-mail te verzenden. Dit is een omslachtig en foutgevoelig methode voor samenwerking, die het risico op het delen van informatie kan vergroten. Als personen het delen van informatie te moeilijk vinden, kunnen ze weer consumentenproducten gebruiken die niet door IT worden beheerd. Dit kan een nog groter risico vormen.

Met Microsoft 365 kunt u Teams implementeren met diverse configuraties die helpen:

- Uw intellectuele eigendom beveiligen
- Eenvoudige samenwerking mogelijk maken
- Een balans creëren tussen beveiliging en bruikbaarheid waardoor de tevredenheid van gebruikers wordt verhoogd en het risico op schaduw van IT wordt verkleind

De meeste organisaties hebben een verscheidenheid aan informatie, met verschillende mate van gevoeligheid en verschillende mate van zakelijke impact als de informatie ongepast wordt gedeeld. Afhankelijk van de gevoeligheid van een bepaald stukje informatie, kunt u delen toestaan met:

- Iedereen (niet-geauteerd)
- Personen binnen de organisatie
- Specifieke personen binnen de organisatie
- Specifieke personen binnen en buiten de organisatie

Informatie zoals marketingbrochures is bedoeld voor een breed publiek buiten de organisatie. Informatie zoals menu's met menu's van het menu is niet bedoeld voor extern delen, maar heeft geen gevolgen voor het bedrijf als ze extern worden gedeeld. Dit soort informatie hoeft niet of niet te worden beschermd.

Deze marketingbrochures worden, zolang ze in ontwikkeling zijn, mogelijk alleen gedeeld binnen de organisatie. In dit geval zijn de standaardinstellingen voor delen in Teams mogelijk voldoende.

Informatie over een nieuw product dat in ontwikkeling is, wordt mogelijk beschouwd als gevoelig, zelfs binnen de organisatie. In dit geval is een betere bescherming mogelijk. U kunt bijvoorbeeld de toegang tot deze gegevens beperken tot leden van een specifiek team. Afhankelijk van het project moet u mogelijk samenwerken met personen buiten uw organisatie, zoals een leverancier of partnerorganisatie.

Informatie die essentieel is voor het succes van uw organisatie of die strikte beveiligings- of nalevingsvereisten heeft, vereist mogelijk nog meer beschermingsniveaus.

![Risicoschaal van laag (uitgebrachte brochure) tot hoog (gevoelige zakelijke gegevens)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Voor alle hierboven genoemde scenario's kunt u teams in Microsoft Teams gebruiken om de informatie op te slaan, te delen en er samen aan te werken. 

Voor het configureren van veilige samenwerking gebruikt u deze Mogelijkheden en functies van Microsoft 365.

| Product of onderdeel | Functie | Licentieverlening |
|:-------|:-----|:-------|
| Microsoft Defender voor Office 365 | Veilige bijlagen voor SPO, OneDrive en Teams; Veilige documenten; Veilige koppelingen voor Teams    | Microsoft 365 E1, E3 en E5 |
| SharePoint    | Beleidsregels voor het delen van site en bestanden, machtigingen voor het delen van een site, koppelingen voor delen, toegangsaanvragen, instellingen voor het delen van gasten van de site | Microsoft 365 E1, E3 en E5 |
| Microsoft Teams   | Gasttoegang, privéteams, privékanalen | Microsoft 365 E1, E3 en E5 |
| Microsoft 365-compliance  | Vertrouwelijkheidslabels    | Microsoft 365 E3 en E5 |

### <a name="collaboration-governance"></a>Samenwerkingsbeheer

Microsoft 365 biedt vele opties voor het besturen van uw samenwerkingsoplossing. U wordt aangeraden deze implementatie-inhoud samen met de inhoud van [het](collaboration-governance-overview.md) samenwerkingsbeheer te gebruiken om de beste samenwerkingsoplossing voor uw organisatie te maken.

### <a name="using-teams-for-all-kinds-of-data"></a>Teams gebruiken voor allerlei soorten gegevens

Om de toegang tot informatie met verschillende gevoeligheiden te beheren, hebben we drie verschillende [beschermingsniveaus](configure-teams-three-tiers-protection.md)ontwikkeld voor Teams. U kunt deze lagen aanpassen om beter aan de behoeften of uw bedrijf te voldoen. 

![Afbeelding van drie beschermingsniveaus voor Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Deze lagen , *basislijn,* *gevoelig* en zeer *gevoelig,* verhogen geleidelijk de beveiligingen die helpen voorkomen dat gegevens worden te veel verstrekt en mogelijke informatielekken, zoals wordt weergegeven in de volgende tabel.

|-|**Basislijnlaag**|**Gevoelige laag**|**Zeer gevoelige laag**|
|:--|:-----------|:------------|:-------------------|
|Openbaar of privéteam|Een van beide|Privé|Privé|
|Niet-geverifieerd delen|Geblokkeerd|Geblokkeerd|Geblokkeerd|
|Bestandsdeling|Toegestaan|Toegestaan|Alleen teameigenaren kunnen delen.|
|Teamlidmaatschap|Iedereen kan deelnemen aan openbare teams.<br>Goedkeuring van teameigenaar vereist om deel te nemen aan privéteams.|Goedkeuring van teameigenaar vereist om deel te nemen.|Goedkeuring van teameigenaar vereist om deel te nemen.|
|Documentversleuteling|||Beschikbaar met gevoeligheidslabel|
|Gasten delen|Toegestaan|Kan worden toegestaan of geblokkeerd|Kan worden toegestaan of geblokkeerd|
|Niet-beherende apparaten|Geen beperking|Toegang via alleen internet|Geblokkeerd|

Als u deze lagen configureert, moet u het volgende doen:

- Instellingen configureren in Teams voor gasttoegang en privékanalen
- Instellingen configureren op de gekoppelde SharePoint-site van een team voor interne en gastdeling, toegangsaanvragen en koppelingen voor delen
- Voor de *gevoelige* en *zeer gevoelige* lagen, het configureren van gevoeligheidslabels om de teams te classificeren en het delen van gasten en de toegang van gasten vanaf onbeheerde apparaten te beheren
- Voor de *zeer gevoelige* laag, configureert u een gevoeligheidslabel om de documenten te versleutelen waarop deze wordt toegepast

Begin met de basislijnlaag en voeg  vervolgens  teams toe die de gevoelige en zeer gevoelige lagen gebruiken om de informatie in uw organisatie te beschermen. Zie de volgende bronnen om aan de slag te gaan:

- [Teams met basisbescherming configureren](configure-teams-baseline-protection.md)
- [Teams met bescherming voor vertrouwelijke gegevens configureren](configure-teams-sensitive-protection.md)
- [Teams met bescherming voor zeer vertrouwelijke gegevens configureren](configure-teams-highly-sensitive-protection.md)

Als u een zeer gevoelig project hebt dat extra beveiliging vereist tegen delen, zelfs binnen uw organisatie, kunt u een team configureren dat zijn eigen gevoeligheidslabel gebruikt om bestanden te versleutelen, zodat alleen teamleden deze kunnen lezen. Zie [Een team configureren met beveiligingsisolatie](secure-teams-security-isolation.md) voor meer informatie.

### <a name="sharing-with-people-outside-your-organization"></a>Delen met personen buiten uw organisatie

Mogelijk moet u [informatie over een eventuele gevoeligheid delen met personen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md) Dit kan variëren van het delen van één document met één persoon tot het samenwerken aan een groot project met een grote partnerorganisatie of met iedereen over de hele wereld. In Microsoft 365 kunt u dit bereik van extern delen eenvoudig en met de juiste beveiliging gebruiken om uw gevoelige informatie te beschermen.

Deze bronnen helpen u om aan de slag te gaan met het instellen van uw omgeving voor samenwerking met personen buiten uw organisatie:

- [Werk samen aan documenten](collaborate-on-documents.md) voor het delen van afzonderlijke bestanden van mappen.
- [Werk samen op een site](collaborate-in-site.md) om samen te werken met gasten op een SharePoint-site.
- [Werk samen als een team](collaborate-as-team.md) om samen te werken met gasten in een team.

Afhankelijk van de gevoeligheid van de informatie die wordt gedeeld, kunt u beveiligingen toevoegen om te voorkomen dat er te veel informatie wordt gedeeld. Deze bronnen helpen u bij het instellen van de beveiliging die u nodig hebt voor uw organisatie:

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)
- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

Als u een belangrijk project hebt met een partnerorganisatie, kunt u Azure Rechtbeheer gebruiken om de gasten van die organisatie te beheren in een team dat u voor het project in stellen. Zie [Een B2B-extranet maken met beheerde gasten](b2b-extranet.md) voor meer informatie.



## <a name="training-for-administrators"></a>Training voor beheerders

Met deze trainingsmodules van Microsoft Learn leert u de functies voor samenwerking, beheer en identiteit in Teams en SharePoint.

#### <a name="teams"></a>Teams

|Training:|Teamsamenwerking beheren met Microsoft Teams|
|:---|:---|
|![Pictogram teamssamenwerkingstraining](../media/manage-team-collaboration-with-microsoft-teams.svg)|Manage team collaboration with Microsoft Teams introduces you to the features and capabilities of Microsoft Teams, the central hub for team collaboration in Microsoft 365. U leert hoe u Teams kunt gebruiken om teamwerk en communicatie binnen uw organisatie te vergemakkelijken, zowel on-premises als off-premises, op een groot aantal apparaten, van desktops tot tablets tot telefoons, terwijl u profiteert van alle uitgebreide functionaliteit van Office 365-toepassingen. U krijgt inzicht in de manier waarop Teams een uitgebreide en flexibele omgeving biedt voor samenwerking tussen toepassingen en apparaten. Dit leerpad kan u helpen bij de voorbereiding op de Microsoft 365 Certified: Teams Administrator Associate-certificering.<br><br>2 uur en 17 min . Leerpad - 5 modules|

> [!div class="nextstepaction"]
> [Start >](https://docs.microsoft.com/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Training:|Samenwerken met SharePoint in Microsoft 365|
|:---|:---|
|![Pictogram training voor SharePoint](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Als u gedeelde inhoud met Microsoft SharePoint beheert, maakt u kennis met de functies en mogelijkheden van SharePoint en de manier waarop het werkt met Microsoft 365. U krijgt informatie over de verschillende typen SharePoint-sites, waaronder hubsites, en informatiebescherming, rapportage en controle. U leert ook hoe u SharePoint-bestanden en -mappen kunt gebruiken om samenwerking te optimaliseren, hoe u bestanden extern kunt delen en hoe u SharePoint-sites beheert in het SharePoint-beheercentrum. Dit leerpad kan u helpen bij de voorbereiding op de Microsoft 365 Certified: Teamwork Administrator Associate-certificering.<br><br>1 uur en 14 min. - Leerpad - 4 modules|

> [!div class="nextstepaction"]
> [Start >](https://docs.microsoft.com/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Gegevensbescherming

|Training:|Bedrijfsgegevens beveiligen met Microsoft 365|
|:---|:---|
|![Pictogram training voor Teams-informatiebeveiliging](../media/protect-enterprise-information-microsoft-365.svg)|Het beschermen en beveiligen van de gegevens van uw organisatie is nu nog lastiger dan ooit. In het leerpad Microsoft 365 worden bedrijfsgegevens beschermd tegen onbedoelde overbelasting of misbruik, hoe u gegevens kunt vinden en classificeren, hoe u deze kunt beveiligen met gevoeligheidslabels en hoe u uw gevoelige informatie kunt bewaken en analyseren om te voorkomen dat deze verloren gaat. Dit leerpad kan u helpen bij de voorbereiding op de Microsoft 365 Certified: Security Administrator Associate en Microsoft 365 Certified: Enterprise Administration Expert-certificeringen.<br><br>1 uur - Leerpad - 5 modules|

> [!div class="nextstepaction"]
> [Start >](https://docs.microsoft.com/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identiteit en toegang

|Training:|Identiteit en toegang beveiligen met Azure Active Directory|
|:---|:---|
|![Pictogram Identiteit en toegangstraining](../media/protect-identity-and-access-with-microsoft-365.svg)|Het leerpad Identiteit en Access omvat de nieuwste identiteits- en toegangstechnologieën, hulpmiddelen voor verificatie via verificatie en richtlijnen voor identiteitsbeveiliging binnen uw organisatie. Met Microsoft-toegangs- en identiteitstechnologieën kunt u de identiteit van uw organisatie beveiligen, on-premises of in de cloud, en stelt u uw gebruikers in staat veilig te werken vanaf elke locatie. Dit leerpad kan u helpen bij de voorbereiding op de Microsoft 365 Certified: Security Administrator Associate en Microsoft 365 Certified: Enterprise Administration Expert-certificeringen.<br><br>2 uur en 52 min . Leerpad - 6 modules|

> [!div class="nextstepaction"]
> [Start >](https://docs.microsoft.com/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Training voor eindgebruikers

Met deze trainingsmodules kunnen uw gebruikers Teams, groepen en SharePoint gebruiken om samen te werken in Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Pictogram voor het instellen en aanpassen van uw teamtraining](../media/set-up-customize-team-training.png)<br>**[Uw team instellen en aanpassen](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![Pictogram training delen en synchroniseren in SharePoint](../media/sharepoint-share-sync-training.png)<br>**[Delen en synchroniseren](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Pictogram voor het uploaden en zoeken van teams voor het uploaden van bestanden](../media/smc-teams-upload-find-files-training.png)<br>**[Bestanden uploaden en zoeken](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Pictogram Samenwerken in teams en kanalen](../media/teams-collaborate-channels-training.png)<br>**[Samenwerken in teams en kanalen](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Illustraties

Deze afbeeldingen helpen u inzicht te krijgen in de interactie tussen groepen en teams met andere services in Microsoft 365 en welke beheer- en nalevingsfuncties beschikbaar zijn om u te helpen deze services in uw organisatie te beheren.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Groepen in Microsoft 365 voor IT-architecten
Wat IT-architecten moeten weten over Microsoft 365-groepen

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuurafbeelding van de infographic voor groepen](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Laatst bijgewerkt: juni 2019|Deze illustraties tonen verschillende soorten groepen, hoe ze worden gemaakt en beheerd, en enkele aanbevelingen voor beheer.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams en gerelateerde productiviteitsservices in Microsoft 365 voor IT-architecten
De logische architectuur van productiviteitsservices in Microsoft 365, geleid door Microsoft Teams.

|**Item**|**Beschrijving**|
|:-----|:-----|
|[![Miniatuurafbeelding van de poster Logische architectuur van Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Laatst bijgewerkt: april 2019   |Microsoft biedt een pakket met productiviteitsservices die samenwerken met behulp van functies voor gegevensbeheer, beveiliging en compliance. <br/> <br/>Deze reeks illustraties biedt een overzicht van de logische architectuur van productiviteitsservices voor ondernemingsarchitecten, geleid door Microsoft Teams.|

## <a name="deploy-the-secure-collaboration-solution"></a>De veilige samenwerkingsoplossing implementeren

Wanneer u klaar bent om deze oplossing te implementeren, gaat u verder met deze stappen:
1. Configureer [de drie verschillende beschermingsniveaus voor Teams.](configure-teams-three-tiers-protection.md)
2. Configureer instellingen [voor het delen van informatie over gevoeligheid met personen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Zie ook

[Documentatie over Microsoft 365-beveiliging](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365-compliancedocumentatie](https://docs.microsoft.com/microsoft-365/compliance)

[Welkom bij Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
