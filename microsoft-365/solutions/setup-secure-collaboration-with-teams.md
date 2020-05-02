---
title: Veilige samenwerking met Microsoft 365 instellen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Meer informatie over het instellen van Teams om uw gegevens te beschermen op basis van de gevoeligheid
ms.openlocfilehash: 77493398b11109a51c4e60599561fd8cd4f6c3ac
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002670"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Veilige samenwerking met Microsoft 365 instellen

Het eenvoudig delen van informatie met de juiste mensen en het voorkomen van overdelen is essentieel voor het succes van een organisatie. Dit houdt in dat u gevoelige gegevens veilig delen met alleen degenen die er toegang toe moeten hebben. Afhankelijk van het project kan dit onder meer het delen van gevoelige gegevens met mensen buiten uw organisatie.

Deze oplossingsrichtlijnen bevatten twee componenten om u te helpen:
- Microsoft Teams implementeren met het juiste beschermingsniveau voor elk project
- Extern delen configureren met de juiste beveiligingsinstellingen voor elk project

![Teams implementeren met de juiste beveiliging en extern delen configureren met de juiste beveiligingsinstellingen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Als er geen veelzijdige en gebruiksvriendelijke samenwerkingstools beschikbaar zijn, werken gebruikers vaak samen door documenten te e-mailen. Dit is een vervelende en foutgevoelige methode van samenwerking en kan het risico op het ongepast delen van informatie verhogen. Als mensen het delen van informatie te moeilijk vinden, kunnen ze terugkeren naar het gebruik van consumentenproducten die niet door IT worden geregeld. Dit kan een nog groter risico vormen.

Met Microsoft 365 u Teams implementeren met verschillende configuraties die u helpen:

- Bescherm uw intellectuele eigendom
- Eenvoudige samenwerking mogelijk maken
- Creëer een balans tussen beveiliging en bruikbaarheid die de tevredenheid van gebruikers verhoogt en het risico op schaduw-IT vermindert

De meeste organisaties hebben een verscheidenheid aan informatie, met verschillende mate van gevoeligheid en verschillende mate van zakelijke impact als de informatie op ongepaste wijze wordt gedeeld. Afhankelijk van de gevoeligheid van een bepaald stukje informatie, u delen toestaan met:

- Iedereen (niet geverifieerd)
- Mensen binnen de organisatie
- Specifieke mensen binnen de organisatie
- Specifieke mensen binnen en buiten de organisatie

Informatie zoals marketingbrochures is bedoeld om breed buiten de organisatie te delen. Informatie zoals cafetariamenu's zijn niet bedoeld voor extern delen, maar zou geen zakelijke impact hebben als ze extern worden gedeeld. Dit soort informatie heeft weinig of geen bescherming nodig.

Diezelfde marketingbrochures, terwijl ze in ontwikkeling zijn, kunnen alleen binnen de organisatie worden gedeeld. In dit geval kunnen de instellingen voor delen in Teams voldoende zijn.

Informatie over een nieuw product dat in ontwikkeling is, kan als gevoelig worden beschouwd, zelfs binnen de organisatie. Een grotere mate van bescherming zou in dit geval passend kunnen zijn. U de toegang tot deze informatie bijvoorbeeld beperken tot leden van een specifiek team. Afhankelijk van het project moet u mogelijk samenwerken met mensen buiten uw organisatie, zoals een leverancier of partnerorganisatie.

Informatie die essentieel is voor het succes van uw organisatie of strenge beveiligings- of nalevingsvereisten heeft, vereist mogelijk nog meer bescherming.

![Risicoschaal van laag (vrijgegeven brochure) tot hoog (gevoelige bedrijfsgegevens)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Voor alle bovenstaande scenario's u teams in Microsoft Teams gebruiken om de informatie op te slaan, te delen en samen te werken. 

## <a name="using-teams-for-all-kinds-of-data"></a>Teams gebruiken voor allerlei gegevens

Om de toegang tot informatie met verschillende gevoeligheden te beheren, hebben we [drie verschillende beschermingsniveaus voor Teams](configure-teams-three-tiers-protection.md)ontwikkeld. U elk van deze lagen aanpassen om beter aan de behoeften of uw bedrijf te voldoen. 

![Duimafbeelding voor logische architectuurposter teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Deze lagen - *basislijn*, *gevoelig*en *zeer gevoelig* - verhogen geleidelijk de beveiligingen die overdelen en mogelijke informatielekken helpen voorkomen, zoals in de volgende tabel wordt weergegeven.

||**Basislijnlaag**|**Gevoelige laag**|**Zeer gevoelige laag**|
|:--|:-----------|:------------|:-------------------|
|Openbaar of particulier team|Ofwel|Privé|Privé|
|Niet-geverifieerd delen|Geblokkeerd|Geblokkeerd|Geblokkeerd|
|Het delen van bestanden|Toegestaan|Toegestaan|Alleen teameigenaren kunnen delen.|
|Teamlidmaatschap|Iedereen kan zich aansluiten bij openbare teams.<br>Goedkeuring van de teameigenaar vereist om lid te worden van privéteams.|Teameigenaar goedkeuring vereist om toe te treden.|Teameigenaar goedkeuring vereist om toe te treden.|
|Documentversleuteling|||Beschikbaar met gevoeligheidslabel|
|Gasten delen|Toegestaan|Kan worden toegestaan of geblokkeerd|Kan worden toegestaan of geblokkeerd|
|Onbeheerde apparaten|Geen beperking|Alleen webtoegang|Geblokkeerd|

Het configureren van deze lagen omvat:

- Instellingen configureren in Teams voor gasttoegang en privékanalen
- Instellingen configureren in de bijbehorende SharePoint-site van een team voor het delen, openen van toegang en het delen van koppelingen van gasten
- Voor de *gevoelige* en *zeer gevoelige* lagen configureert u gevoeligheidslabels om de teams te classificeren en beheer gasten delen en openen vanaf onbeheerde apparaten
- Voor de *zeer gevoelige* laag configureert u een gevoeligheidslabel om de documenten waarop deze wordt toegepast te versleutelen

Begin met de basislijnlaag en voeg vervolgens teams toe die de *gevoelige* en *zeer gevoelige* lagen gebruiken als dat nodig is om de informatie in uw organisatie te beschermen. Bekijk deze bronnen om aan de slag te gaan:

- [Teams configureren met basislijnbeveiliging](configure-teams-baseline-protection.md)
- [Teams configureren met bescherming voor gevoelige gegevens](configure-teams-sensitive-protection.md)
- [Teams configureren met bescherming voor zeer gevoelige gegevens](configure-teams-highly-sensitive-protection.md)

Als u een zeer gevoelig project hebt dat extra bescherming tegen delen vereist, zelfs binnen uw organisatie, u een team configureren dat zijn eigen gevoeligheidslabel gebruikt om bestanden te versleutelen, zodat alleen teamleden ze kunnen lezen. Zie [Een team configureren met beveiligingsisolatie](secure-teams-security-isolation.md) voor meer informatie.

## <a name="sharing-with-people-outside-your-organization"></a>Delen met mensen buiten uw organisatie

Mogelijk moet u [informatie van elke gevoeligheid delen met mensen buiten uw organisatie.](collaborate-with-people-outside-your-organization.md) Dit kan variëren van het delen van één document met één persoon tot het samenwerken aan een groot project met een grote partnerorganisatie of freelancers van over de hele wereld. In Microsoft 365 kan dit bereik van extern delen eenvoudig en met de juiste waarborgen worden gedaan om uw gevoelige informatie te beschermen.

Met deze bronnen u aan de slag met het instellen van uw omgeving voor samenwerking met mensen buiten uw organisatie:

- [Werk samen aan documenten](collaborate-on-documents.md) voor het delen van afzonderlijke bestanden van mappen.
- [Werk samen in een site](collaborate-in-site.md) om samen te werken met gasten in een SharePoint-site.
- [Werk samen als een team](collaborate-as-team.md) om samen te werken met gasten in een team.

Afhankelijk van de gevoeligheid van de informatie die wordt gedeeld, u beveiligingen toevoegen om overdeling te voorkomen. Met deze bronnen u de beveiligingen instellen die u voor uw organisatie nodig hebt:

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)
- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen van buiten uw organisatie](share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

Als u een groot project hebt met een partnerorganisatie, u Azure Entitlement Management gebruiken om de gasten van die organisatie te beheren in een team dat u voor het project hebt ingesteld. Zie [Een B2B-extranet maken met beheerde gasten](b2b-extranet.md) voor meer informatie.

## <a name="see-also"></a>Zie ook

[Documentatie over Microsoft 365-beveiliging](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365-documentatie over naleving](https://docs.microsoft.com/microsoft-365/compliance)

[Welkom bij Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
