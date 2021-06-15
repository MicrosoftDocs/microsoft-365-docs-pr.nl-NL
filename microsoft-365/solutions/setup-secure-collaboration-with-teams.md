---
title: Veilige samenwerking met Microsoft 365 instellen
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
recommendations: false
description: Meer informatie over het instellen van veilige samenwerking met inhoud in Teams om uw gegevens te beveiligen op basis van de gevoeligheid.
ms.openlocfilehash: 7a5b8f58cc5e4a23d2d143419f99ecdd87b949c1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924357"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>Veilige samenwerking instellen met Microsoft 365 en Microsoft Teams

Het is belangrijk om eenvoudig informatie te kunnen delen met de juiste personen en overbeharing te voorkomen. Dit geldt ook voor het veilig delen van gevoelige gegevens met alleen personen die toegang tot deze gegevens moeten hebben. Afhankelijk van het project kan dit het delen van gevoelige gegevens omvatten met personen buiten uw organisatie.

Deze richtlijnen voor samenwerkingsoplossing bevatten twee onderdelen om u te helpen:
- Implementatie Microsoft Teams met het juiste beveiligingsniveau voor elk project
- Extern delen configureren met de juiste beveiligingsinstellingen voor elk project

![Implementeer Teams met de juiste beveiliging en configureer extern delen met de juiste beveiligingsinstellingen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Als veelzijdige en eenvoudig te gebruiken hulpprogramma's voor samenwerking van inhoud niet beschikbaar zijn, werken gebruikers vaak samen door documenten te e-mailen. Dit is een vervelende en foutgevoelige methode voor samenwerking en kan het risico op ongepast delen van informatie vergroten. Als mensen het delen van informatie te moeilijk vinden, kunnen ze terugkeren naar het gebruik van consumentenproducten die niet onder IT vallen. Dit kan een nog groter risico opleveren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Met Microsoft 365 kunt u Teams verschillende configuraties implementeren die u helpen:

- Uw intellectuele eigendom beschermen
- Eenvoudige samenwerking inschakelen
- Een evenwicht creëren tussen beveiliging en bruikbaarheid, waardoor de tevredenheid van gebruikers toeneemt en het risico op schaduw-IT wordt verkleind

De meeste organisaties hebben een verscheidenheid aan informatie, met verschillende mate van gevoeligheid en verschillende mate van bedrijfsimpact als de informatie ongepast wordt gedeeld. Afhankelijk van de gevoeligheid van een bepaald stukje informatie, kunt u delen toestaan met:

- Iedereen (niet-genauteerd)
- Personen binnen de organisatie
- Specifieke personen binnen de organisatie
- Specifieke personen binnen en buiten de organisatie

Informatie zoals marketingbrochures zijn bedoeld voor delen in grote lijnen buiten de organisatie. Informatie zoals menu's voor cafetaria's zijn niet bedoeld voor extern delen, maar hebben geen zakelijke invloed als ze extern worden gedeeld. Deze soorten informatie hebben weinig of geen beveiliging nodig.

Dezelfde marketingbrochures, die nog in ontwikkeling zijn, worden mogelijk alleen gedeeld binnen de organisatie. In dit geval kunnen de standaardinstellingen voor delen in Teams voldoende zijn.

Informatie over een nieuw product dat in ontwikkeling is, kan als gevoelig worden beschouwd, zelfs binnen de organisatie. In dit geval is een grotere mate van beveiliging mogelijk geschikt. U kunt bijvoorbeeld de toegang tot deze gegevens beperken tot leden van een specifiek team. Afhankelijk van het project moet u mogelijk samenwerken met personen buiten uw organisatie, zoals een leverancier of partnerorganisatie.

Informatie die essentieel is voor het succes van uw organisatie of die strenge beveiligings- of compliancevereisten heeft, vereist mogelijk nog meer beveiligingsniveaus.

![Risicoschaal van laag (uitgebrachte brochure) tot hoog (gevoelige zakelijke gegevens)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Voor alle bovenstaande scenario's kunt u teams in Microsoft Teams gebruiken om de gegevens op te slaan, te delen en samen te werken. 

Als u veilige samenwerking wilt configureren, gebruikt u deze Microsoft 365 mogelijkheden en functies.

| Product of onderdeel | Functie | Licentieverlening |
|:-------|:-----|:-------|
| Microsoft Defender voor Office 365 | Safe Bijlagen voor SPO, OneDrive en Teams; Safe Documenten; Safe Koppelingen voor Teams    | Microsoft 365 E1, E3 en E5 |
| SharePoint    | Beleid voor het delen van site en bestanden, machtigingen voor het delen van site, Koppelingen delen, Access-aanvragen, instellingen voor het delen van sitegasten | Microsoft 365 E1, E3 en E5 |
| Microsoft Teams   | Gasttoegang, privéteams, privékanalen | Microsoft 365 E1, E3 en E5 |
| Microsoft 365-compliance  | Vertrouwelijkheidslabels    | Microsoft 365 E3 en E5 |

### <a name="collaboration-governance"></a>Samenwerkingsbeheer

Microsoft 365 biedt veel opties voor het besturen van uw samenwerkingsoplossing. We raden u aan deze implementatie-inhoud naast de inhoud van samenwerkingsbeheer te [gebruiken](collaboration-governance-overview.md) om de beste samenwerkingsoplossing voor uw organisatie te maken.

### <a name="using-teams-for-all-kinds-of-data"></a>Gebruik Teams voor allerlei gegevens

Om toegang tot informatie met verschillende gevoeligheden te beheren, hebben we drie verschillende beveiligingslagen ontwikkeld voor [Teams.](configure-teams-three-tiers-protection.md) U kunt een van deze lagen aanpassen om beter aan de behoeften of uw bedrijf te voldoen. 

![Afbeelding van drie beveiligingsniveaus voor Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Deze lagen - *basislijn* *,* gevoelig en zeer gevoelig *-* verhogen geleidelijk de beveiligingen die oversharing en mogelijke informatielekken helpen voorkomen, zoals wordt weergegeven in de volgende tabel.

|-|**Basislijnlaag**|**Gevoelige laag**|**Hooggevoelige laag**|
|:--|:-----------|:------------|:-------------------|
|Openbaar of privéteam|Een van beide|Privé|Privé|
|Niet-geverifieerd delen|Geblokkeerd|Geblokkeerd|Geblokkeerd|
|Bestandsdeling|Toegestaan|Toegestaan|Alleen teameigenaren kunnen delen.|
|Teamlidmaatschap|Iedereen kan deelnemen aan openbare teams.<br>Goedkeuring van teameigenaar vereist om deel te nemen aan privéteams.|Goedkeuring van teameigenaar vereist om deel te nemen.|Goedkeuring van teameigenaar vereist om deel te nemen.|
|Documentversleuteling|||Beschikbaar met gevoeligheidslabel|
|Delen met gasten|Toegestaan|Kan worden toegestaan of geblokkeerd|Kan worden toegestaan of geblokkeerd|
|Niet-bemande apparaten|Geen beperking|Web-only access|Geblokkeerd|

Als u deze lagen configureert, moet u het volgende doen:

- Instellingen configureren in Teams voor gasttoegang en privékanalen
- Instellingen configureren op de gekoppelde site van een team SharePoint voor interne en gastdeling, toegangsaanvragen en koppelingen voor delen
- Voor de *gevoelige* en *zeer gevoelige* lagen, het configureren van gevoeligheidslabels om de teams te classificeren en gast delen en toegang te beheren vanaf niet-beheerbare apparaten
- Voor de *zeer gevoelige* laag configureert u een gevoeligheidslabel om de documenten waarop deze wordt toegepast te versleutelen

Begin met de basislijnlaag en voeg  teams  toe die zo nodig de gevoelige en zeer gevoelige lagen gebruiken om de informatie in uw organisatie te beschermen. Bekijk deze bronnen om aan de slag te gaan:

- [Teams met basisbescherming configureren](configure-teams-baseline-protection.md)
- [Teams met bescherming voor vertrouwelijke gegevens configureren](configure-teams-sensitive-protection.md)
- [Teams met bescherming voor zeer vertrouwelijke gegevens configureren](configure-teams-highly-sensitive-protection.md)

Als u een zeer gevoelig project hebt dat extra beveiliging vereist voor delen, zelfs binnen uw organisatie, kunt u een team configureren dat een eigen gevoeligheidslabel gebruikt om bestanden te versleutelen, zodat alleen teamleden ze kunnen lezen. Zie [Een team configureren met beveiligingsisolatie](secure-teams-security-isolation.md) voor meer informatie.

### <a name="sharing-with-people-outside-your-organization"></a>Delen met personen buiten uw organisatie

Mogelijk moet u [gegevens met een gevoeligheid delen met personen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md) Dit kan variëren van het delen van één document met één persoon tot het samenwerken aan een groot project met een grote partnerorganisatie of met freelancers van over de hele wereld. In Microsoft 365 kan dit bereik van extern delen eenvoudig en met de juiste beveiligingen worden uitgevoerd om uw gevoelige informatie te beschermen.

Met deze bronnen kunt u aan de slag met het instellen van uw omgeving voor samenwerking met personen buiten uw organisatie:

- [Samenwerken aan documenten voor](collaborate-on-documents.md) het delen van afzonderlijke bestanden van mappen.
- [Samenwerken aan een site](collaborate-in-site.md) om samen te werken met gasten op een SharePoint site.
- [Samenwerken als een team om](collaborate-as-team.md) samen te werken met gasten in een team.

Afhankelijk van de gevoeligheid van de gegevens die worden gedeeld, kunt u beveiligingen toevoegen om oversharing te voorkomen. Met deze bronnen kunt u de beveiliging instellen die u nodig hebt voor uw organisatie:

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)
- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

Als u een belangrijk project hebt met een partnerorganisatie, kunt u Azure Entitlement Management gebruiken om de gasten van die organisatie te beheren in een team dat u voor het project hebt ingesteld. Zie [Een B2B-extranet maken met beheerde gasten voor](b2b-extranet.md) meer informatie.



## <a name="training-for-administrators"></a>Training voor beheerders

Deze trainingsmodules van Microsoft Learn kunnen u helpen bij het leren van de samenwerkings-, beheer- en identiteitsfuncties in Teams en SharePoint.

#### <a name="teams"></a>Teams

|Training:|Teamsamenwerking beheren met Microsoft Teams|
|:---|:---|
|![Teams samenwerkingstrainingspictogram](../media/manage-team-collaboration-with-microsoft-teams.svg)|Beheer teamsamenwerking met Microsoft Teams maakt kennis met de functies en mogelijkheden van Microsoft Teams, de centrale hub voor teamsamenwerking in Microsoft 365. U leert hoe u Teams kunt gebruiken om teamwerk en communicatie binnen uw organisatie te vergemakkelijken, zowel on- als off-premises, op een breed scala aan apparaten, van desktops tot tablets tot telefoons, terwijl u profiteert van alle uitgebreide functionaliteit van Office 365-toepassingen. U krijgt inzicht in de manier waarop Teams een uitgebreide en flexibele omgeving biedt voor samenwerking op verschillende toepassingen en apparaten. Met dit leerpad kunt u zich voorbereiden op Microsoft 365 certified: Teams Administrator Associate-certificering.<br><br>2 uur 17 min - Leerpad - 5 modules|

> [!div class="nextstepaction"]
> [Start >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Training:|Samenwerken met SharePoint in Microsoft 365|
|:---|:---|
|![SharePoint trainingspictogram](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Als u gedeelde inhoud met Microsoft SharePoint, maakt u kennis met de functies en mogelijkheden van SharePoint en hoe deze werkt met Microsoft 365. U leert over de verschillende typen SharePoint sites, waaronder hubsites, evenals informatiebeveiliging, rapportage en monitoring. U leert ook hoe u SharePoint bestanden en mappen kunt gebruiken om de samenwerking te optimaliseren, hoe u bestanden extern kunt delen en hoe u SharePoint sites in het SharePoint beheercentrum beheert. Dit leerpad kan u helpen om u voor te bereiden op Microsoft 365 certificering gecertificeerd: Teamwork Administrator Associate.<br><br>1 uur 14 min - Leerpad - 4 modules|

> [!div class="nextstepaction"]
> [Start >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Gegevensbescherming

|Training:|Bedrijfsgegevens beveiligen met Microsoft 365|
|:---|:---|
|![Teams infobeveiligingstrainingspictogram](../media/protect-enterprise-information-microsoft-365.svg)|Het beveiligen en beveiligen van de gegevens van uw organisatie is lastiger dan ooit. In het leerpad Ondernemingsgegevens beveiligen met Microsoft 365 wordt besproken hoe u uw gevoelige informatie kunt beschermen tegen onbedoelde oversharing of misbruik, hoe u gegevens kunt ontdekken en classificeren, hoe u deze met gevoeligheidslabels kunt beschermen en hoe u uw gevoelige gegevens kunt bewaken en analyseren om te beschermen tegen verlies. Dit leerpad kan u helpen bij het voorbereiden van de Microsoft 365 Certified: Security Administrator Associate en Microsoft 365 Certified: Enterprise Administration Expert certifications..<br><br>1 uur - Leerpad - 5 modules|

> [!div class="nextstepaction"]
> [Start >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identiteit en toegang

|Training:|Identiteit en toegang beveiligen met Azure Active Directory|
|:---|:---|
|![Pictogram Voor training voor identiteit en toegang](../media/protect-identity-and-access-with-microsoft-365.svg)|Het leerpad Identiteit en Access omvat de nieuwste identiteits- en toegangstechnologieën, hulpmiddelen voor het versterken van verificatie en richtlijnen voor identiteitsbeveiliging binnen uw organisatie. Met microsoft-toegangs- en identiteitstechnologieën kunt u de identiteit van uw organisatie beveiligen, ongeacht of deze on-premises of in de cloud is, en uw gebruikers in staat stellen veilig te werken vanaf elke locatie. Met dit leerpad kunt u zich voorbereiden op de Microsoft 365 Certified: Beveiligingsbeheerder associate en Microsoft 365 Certified: Enterprise Administration Expert-certificeringen.<br><br>2 uur 52 min - Leerpad - 6 modules|

> [!div class="nextstepaction"]
> [Start >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Training voor eindgebruikers

Met deze trainingsmodules kunnen uw gebruikers Teams, groepen en SharePoint gebruiken voor samenwerking in Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Uw teamtrainingspictogram instellen en aanpassen](../media/set-up-customize-team-training.png)<br>**[Uw team instellen en aanpassen](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint trainingspictogram delen en synchroniseren](../media/sharepoint-share-sync-training.png)<br>**[Delen en synchroniseren](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams pictogram voor het uploaden en zoeken van bestanden](../media/smc-teams-upload-find-files-training.png)<br>**[Upload en bestanden zoeken](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Pictogram Samenwerken in teams en kanalen](../media/teams-collaborate-channels-training.png)<br>**[Samenwerken in teams en kanalen](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>Illustraties

Deze illustraties helpen u inzicht te krijgen in de interactie tussen groepen en teams met andere services in Microsoft 365 en welke beheer- en compliancefuncties beschikbaar zijn om u te helpen bij het beheren van deze services in uw organisatie.

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

Wanneer u klaar bent om deze oplossing te implementeren, gaat u verder met de volgende stappen:
1. Configureer [de drie verschillende beveiligingslagen voor Teams.](configure-teams-three-tiers-protection.md)
2. Configureer instellingen voor [het delen van informatie die gevoelig is voor personen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Zie ook

[Documentatie over Microsoft 365-beveiliging](../security/index.yml)

[Microsoft 365-compliancedocumentatie](../compliance/index.yml)

[Welkom bij Microsoft Teams](/MicrosoftTeams/Teams-overview)
