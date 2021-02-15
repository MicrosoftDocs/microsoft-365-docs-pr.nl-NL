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
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233854"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Veilige samenwerking instellen met Microsoft 365

Het gemakkelijk kunnen delen van informatie met de juiste personen en het voorkomen van te veel delen is belangrijk voor het succes van een organisatie. Dit houdt onder andere in dat u gevoelige gegevens veilig kunt delen met alleen personen die er toegang toe moeten hebben. Afhankelijk van het project kan dit het delen van gevoelige gegevens omvatten met personen buiten uw organisatie.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Deze richtlijnen voor samenwerkingsoplossing bevatten twee onderdelen die u kunnen helpen:
- Microsoft Teams implementeren met het juiste beschermingsniveau voor elk project
- Extern delen configureren met de juiste beveiligingsinstellingen voor elk project

![Teams implementeren met de juiste beveiliging en extern delen configureren met de juiste beveiligingsinstellingen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Als er geen veelzijdige en eenvoudig te gebruiken hulpmiddelen voor samenwerking aan inhoud beschikbaar zijn, werken gebruikers vaak samen door documenten per e-mail te verzenden. Dit is een omslachtig en foutgevoelig methode voor samenwerking, die het risico op het delen van informatie kan vergroten. Als personen het delen van informatie te moeilijk vinden, kunnen ze terugkeren naar consumentenproducten die niet door DE IT worden beheerd. Dit kan een nog groter risico vormen.

Met Microsoft 365 kunt u Teams implementeren met diverse configuraties die helpen:

- Uw intellectuele eigendom beveiligen
- Eenvoudige samenwerking mogelijk maken
- Een balans creëren tussen beveiliging en bruikbaarheid waardoor de tevredenheid van gebruikers wordt verhoogd en het risico op schaduw van IT wordt verkleind

De meeste organisaties hebben een verscheidenheid aan informatie, met verschillende mate van gevoeligheid en verschillende mate van zakelijke impact als de informatie ongepast wordt gedeeld. Afhankelijk van de gevoeligheid van een bepaald stukje informatie, kunt u delen toestaan met:

- Iedereen (niet-geauteerd)
- Personen binnen de organisatie
- Specifieke personen binnen de organisatie
- Specifieke personen binnen en buiten de organisatie

Informatie zoals marketingbrochures is bedoeld voor een breed publiek buiten de organisatie. Informatie zoals menu's met menu's van het menu is niet bedoeld voor extern delen, maar heeft geen gevolgen voor het bedrijf als ze extern worden gedeeld. Voor dit soort informatie is weinig of geen beveiliging nodig.

Deze marketingbrochures worden, zolang ze in ontwikkeling zijn, mogelijk alleen gedeeld binnen de organisatie. In dit geval zijn de standaardinstellingen voor delen in Teams mogelijk voldoende.

Informatie over een nieuw product dat in ontwikkeling is, wordt mogelijk beschouwd als gevoelig, zelfs binnen de organisatie. In dit geval is een betere bescherming mogelijk geschikt. U kunt bijvoorbeeld de toegang tot deze gegevens beperken tot leden van een specifiek team. Afhankelijk van het project moet u mogelijk samenwerken met personen buiten uw organisatie, zoals een leverancier of partnerorganisatie.

Informatie die essentieel is voor het succes van uw organisatie of die strikte beveiligings- of nalevingsvereisten heeft, vereist mogelijk nog meer beschermingsniveaus.

![Risicoschaal van laag (uitgebrachte brochure) tot hoog (gevoelige bedrijfsgegevens)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Voor alle hierboven genoemde scenario's kunt u teams in Microsoft Teams gebruiken om de informatie op te slaan, te delen en er samen aan te werken. 

Gebruik deze Mogelijkheden en functies van Microsoft 365 om veilige samenwerking te configureren.

| Product of onderdeel | Functie | Licentieverlening |
|:-------|:-----|:-------|
| Microsoft Defender voor Office 365 | Veilige bijlagen voor SPO, OneDrive en Teams; Veilige documenten; Veilige koppelingen voor Teams    | Microsoft 365 E1, E3 en E5 |
| SharePoint    | Beleidsregels voor het delen van site en bestanden, machtigingen voor het delen van een site, koppelingen voor delen, toegangsaanvragen, instellingen voor het delen van gasten van de site | Microsoft 365 E1, E3 en E5 |
| Microsoft Teams   | Gasttoegang, privéteams, privékanalen | Microsoft 365 E1, E3 en E5 |
| Microsoft 365-compliance  | Vertrouwelijkheidslabels    | Microsoft 365 E3 en E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Teams gebruiken voor allerlei soorten gegevens

Om de toegang tot informatie met verschillende gevoeligheiden te beheren, hebben we drie verschillende [beschermingsniveaus](configure-teams-three-tiers-protection.md)ontwikkeld voor Teams. U kunt deze lagen aanpassen om beter aan de behoeften of uw bedrijf te voldoen. 

![Miniatuurafbeelding van de poster Logische architectuur van Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


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
- Voor de *zeer gevoelige* laag configureert u een gevoeligheidslabel om de documenten te versleutelen waarop deze wordt toegepast

Begin met de basislijnlaag en voeg  vervolgens  teams toe die de gevoelige en zeer gevoelige lagen gebruiken om de informatie in uw organisatie te beschermen. Zie de volgende bronnen om aan de slag te gaan:

- [Teams met basisbescherming configureren](configure-teams-baseline-protection.md)
- [Teams met bescherming voor vertrouwelijke gegevens configureren](configure-teams-sensitive-protection.md)
- [Teams met bescherming voor zeer vertrouwelijke gegevens configureren](configure-teams-highly-sensitive-protection.md)

Als u een zeer gevoelig project hebt dat extra beveiliging vereist tegen delen, zelfs binnen uw organisatie, kunt u een team configureren dat zijn eigen gevoeligheidslabel gebruikt om bestanden te versleutelen, zodat alleen teamleden deze kunnen lezen. Zie [Een team configureren met beveiligingsisolatie](secure-teams-security-isolation.md) voor meer informatie.

### <a name="sharing-with-people-outside-your-organization"></a>Delen met personen buiten uw organisatie

Mogelijk moet u [informatie over een eventuele gevoeligheid delen met personen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md) Dit kan variëren van het delen van één document met één persoon tot het samenwerken aan een groot project met een grote partnerorganisatie of met iedereen over de hele wereld. In Microsoft 365 kunt u dit bereik van extern delen eenvoudig en met de juiste beveiliging gebruiken om uw gevoelige informatie te beschermen.

Deze bronnen helpen u aan de slag te gaan met het instellen van uw omgeving voor samenwerking met personen buiten uw organisatie:

- [Werk samen aan documenten](collaborate-on-documents.md) voor het delen van afzonderlijke bestanden van mappen.
- [Werk samen op een site](collaborate-in-site.md) om samen te werken met gasten op een SharePoint-site.
- [Werk samen als een team](collaborate-as-team.md) om samen te werken met gasten in een team.

Afhankelijk van de gevoeligheid van de informatie die wordt gedeeld, kunt u beveiligingen toevoegen om te voorkomen dat er te veel informatie wordt gedeeld. Deze bronnen helpen u bij het instellen van de beveiliging die u nodig hebt voor uw organisatie:

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)
- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

Als u een belangrijk project hebt met een partnerorganisatie, kunt u Azure Rechtbeheer gebruiken om de gasten van die organisatie te beheren in een team dat u voor het project in stellen. Zie [Een B2B-extranet maken met beheerde gasten](b2b-extranet.md) voor meer informatie.

## <a name="deploy-the-secure-collaboration-solution"></a>De veilige samenwerkingsoplossing implementeren

Wanneer u klaar bent om deze oplossing te implementeren, gaat u verder met deze stappen:
1. Configureer [de drie verschillende beschermingsniveaus voor Teams.](configure-teams-three-tiers-protection.md)
2. Configureer instellingen [voor het delen van informatie over gevoeligheid met personen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Zie ook

[Documentatie over Microsoft 365-beveiliging](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365-compliancedocumentatie](https://docs.microsoft.com/microsoft-365/compliance)

[Welkom bij Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
