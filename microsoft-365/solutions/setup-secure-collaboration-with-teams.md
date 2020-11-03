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
- m365solution-securecollab
- m365solution-overview
ms.custom: ''
f1.keywords: NOCSH
description: Meer informatie over het instellen van teams om uw gegevens te beschermen op basis van de gevoeligheid
ms.openlocfilehash: 5cf4937a79fdf33e160432c740504ec84d196585
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843538"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Veilige samenwerking met Microsoft 365 instellen

U kunt eenvoudig informatie delen met de juiste personen, maar u kunt de inhoud van het bestand op de succesvolle manier delen met het succes van een organisatie. Dit omvat ook veilig het delen van gevoelige gegevens met uitsluitend degenen die er toegang toe moeten hebben. Afhankelijk van het project, kan dit betrekking hebben op het delen van gevoelige gegevens met personen buiten uw organisatie.

De richtlijnen voor oplossingen bestaan uit twee onderdelen waarmee u het volgende kunt doen:
- Microsoft teams implementeren met het juiste niveau van bescherming voor elk project
- Extern delen configureren met de juiste beveiligingsinstellingen voor elk project

![Teams implementeren met de juiste bescherming en extern delen configureren met de juiste beveiligingsinstellingen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Gebruikers kunnen vaak samenwerken via e-mailberichten als de veelzijdige en eenvoudig te gebruiken samenwerkingsfuncties niet beschikbaar zijn. Dit is een saaie methode voor samenwerking met een fout en een groter risico, wat niet mogelijk is met ongepaste delen van informatie. Als mensen te moeilijk informatie vinden over het delen van gegevens, kunnen ze teruggaan naar het gebruik van consumentenproducten die niet door het programma worden bestuurd. Dit kan een nog groter risico vormen.

Met Microsoft 365 kunt u teams implementeren met diverse configuraties waarmee u het volgende kunt doen:

- Beveilig uw intellectuele eigendom
- Eenvoudige samenwerking mogelijk maken
- Maak een evenwicht tussen beveiliging en bruikbaarheid voor het verhogen van de gebruikers tevredenheid en het risico van schaduw verminderen

De meeste organisaties hebben allerlei informatie, met verschillende graad van gevoeligheid en uiteenlopende vrijheidsgraden van de bedrijfsvoering als de gegevens niet naar wens worden gedeeld. Afhankelijk van de gevoeligheid van een bepaald deel van de informatie, wilt u mogelijk delen met:

- Iedereen (niet-geverifieerd)
- Personen binnen de organisatie
- Specifieke personen binnen de organisatie
- Specifieke personen binnen en buiten de organisatie

Informatie, zoals marketing brochures, is bedoeld voor een groot deel buiten de organisatie. Gegevens zoals cafeteria menu's zijn niet bedoeld voor extern delen, maar hebben geen gevolgen voor bedrijven als ze extern zijn gedeeld. Dit soort informatie heeft min of geen bescherming nodig.

Dezelfde marketing brochures, onder ontwikkeling, kunnen alleen binnen de organisatie worden gedeeld. In dit geval zijn de standaardinstellingen voordelen in teams mogelijk voldoende.

Informatie over een nieuw product dat zich onder ontwikkeling bevindt, kan als vertrouwelijk worden beschouwd, zelfs binnen de organisatie. In dit geval is een grotere mate van bescherming mogelijk. U kunt bijvoorbeeld beperkingen instellen voor de toegang tot deze gegevens voor leden van een specifiek team. Afhankelijk van het project moet u mogelijk samenwerken met mensen buiten uw organisatie, zoals een leverancier of een organisatie organisatie.

Gegevens die van essentieel belang zijn voor de succes van uw organisatie of een strikte beveiliging en nalevingsvereisten hebben mogelijk zelfs een grotere mate van bescherming.

![Beperking van risico naar hoog (uitgebrachte brochure) en hoog (gevoelige bedrijfsgegevens)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

U kunt teams in Microsoft teams gebruiken om de gegevens op te slaan, te delen en samen te werken. 

Voor het configureren van de Secure collabration gebruikt u deze Microsoft 365-functies en-functies.

| Product of onderdeel | Functie | Licenties |
|:-------|:-----|:-------|
| Microsoft Defender voor Office 365 | Veilige bijlagen voor SPO, OneDrive en teams; Veilige documenten; Veilige koppelingen voor teams    | Microsoft 365 E1, E3 en E5 |
| SharePoint    | Beleidsregels voor het delen van sites, machtigingen voor het delen van sites, koppelingen voordelen, toegangsaanvragen, site gastinstellingen voordelen | Microsoft 365 E1, E3 en E5 |
| Microsoft Teams   | Gasttoegang, persoonlijke teams, persoonlijke kanalen | Microsoft 365 E1, E3 en E5 |
| Microsoft 365-compliance  | Vertrouwelijkheidslabels    | Microsoft 365 E3 en E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Teams gebruiken voor alle gegevenstypen

Voor het beheren van de toegang tot informatie met verschillende sensitivities, hebben we [drie verschillende niveaus van bescherming voor teams](configure-teams-three-tiers-protection.md)ontwikkeld. U kunt een van deze lagen aanpassen om de behoeften van uw bedrijf beter te kunnen beantwoorden. 

![Miniatuurafbeelding van de poster Logische architectuur van Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Met deze lagen, met een *basislijn* , *gevoelige* en *zeer gevoelige* beveiliging, verhoogt u de bescherming waarmee u overstappen en mogelijke informatie lekkage kunt voorkomen, zoals in de volgende tabel wordt weergegeven.

||**Basislijn**|**Gevoelige laag**|**Uiterst gevoelige laag**|
|:--|:-----------|:------------|:-------------------|
|Openbaar of privé team|Ontbreekt|Privé|Privé|
|Niet-geverifieerd delen|Blokkeert|Blokkeert|Blokkeert|
|Bestanden delen|Ingesteld|Ingesteld|Alleen team eigenaren kunnen delen.|
|Team lidmaatschap|Iedereen kan deelnemen aan openbare teams.<br>Goedkeuring van team eigenaren vereist om lid te worden van persoonlijke teams.|Goedkeuring van team eigenaren vereist om deel te nemen.|Goedkeuring van team eigenaren vereist om deel te nemen.|
|Document versleuteling|||Beschikbaar met vertrouwelijkheids label|
|Gasten delen|Ingesteld|Kan worden toegestaan of geblokkeerd|Kan worden toegestaan of geblokkeerd|
|Niet-beheerde apparaten|Geen beperking|Toegang tot alleen Internet|Blokkeert|

Voor het configureren van deze lagen moet u het volgende doen:

- Instellingen in teams configureren voor gasttoegang en private-kanalen
- Instellingen configureren op de gekoppelde SharePoint-site van het team voor intern delen en het delen van een gast, toegangsaanvragen en gedeelde koppelingen
- Voor de *gevoelige* en *uiterst gevoelige* lagen, de laag gevoelige Labels configureren voor het classificeren van teams, en het delen van gasten en toegang beheren vanaf niet-beheerde apparaten
- Voor de *uiterst gevoelige* laag wordt een gevoeligheids label geconfigureerd voor het versleutelen van de documenten waarop deze is toegepast.

Begin met de basislijn en voeg vervolgens teams toe waarbij de *gevoelige* en *zeer gevoelige* lagen naar wens worden gebruikt om de gegevens in uw organisatie te beschermen. Bekijk deze informatiebronnen om aan de slag te gaan:

- [Teams met basisbescherming configureren](configure-teams-baseline-protection.md)
- [Teams met bescherming voor vertrouwelijke gegevens configureren](configure-teams-sensitive-protection.md)
- [Teams met bescherming voor zeer vertrouwelijke gegevens configureren](configure-teams-highly-sensitive-protection.md)

Als u een zeer gevoelig project hebt waarvoor extra bescherming moet worden gebruikt, zelfs binnen uw organisatie, kunt u een team configureren waarbij een eigen risico label wordt gebruikt om bestanden te versleutelen, zodat alleen teamleden deze kunnen lezen. Zie [een team met beveiligings isolatie configureren](secure-teams-security-isolation.md) voor meer informatie.

### <a name="sharing-with-people-outside-your-organization"></a>Delen met personen buiten uw organisatie

Mogelijk moet u [informatie over de gevoeligheid delen met personen buiten uw organisatie](collaborate-with-people-outside-your-organization.md). Dit kan variëren van het delen van één document met één persoon om samen te werken aan een belangrijk project met een grote partnerorganisatie of freelancers overal ter wereld. In Microsoft 365 kunt u dit bereik van extern delen eenvoudig uitvoeren en met de juiste beschermingsfuncties voor het beschermen van gevoelige informatie.

Met deze informatiebronnen kunt u aan de slag gaan met het instellen van uw omgeving voor samenwerking met mensen buiten uw organisatie:

- [Samenwerken aan documenten](collaborate-on-documents.md) om afzonderlijke bestanden met mappen te delen.
- [Samenwerken aan een site](collaborate-in-site.md) om samen te werken met gasten via een SharePoint-site.
- [Samenwerken als een team](collaborate-as-team.md) voor de samenwerking met gasten in een team.

Afhankelijk van de gevoeligheid van de informatie die wordt gedeeld, kunt u beveiligingen toevoegen om te voorkomen dat u overgaat delen. Met deze informatiebronnen kunt u de benodigde bescherming voor uw organisatie instellen:

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](best-practices-anonymous-sharing.md)
- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](create-secure-guest-sharing-environment.md)

Als u een groot project hebt met een partnerorganisatie, kunt u het beheer van de eigen organisatie gebruiken voor het beheren van de gasten van die organisatie in een team dat u hebt ingesteld voor het project. Zie [een B2B-extranet met beheerde gasten maken](b2b-extranet.md) voor meer informatie.

## <a name="deploy-the-secure-collaboration-solution"></a>De Secure Collaboration Solution implementeren

Ga als volgt te werk als u klaar bent om deze oplossing te implementeren:
1. Configureer de [drie verschillende niveaus van bescherming voor teams](configure-teams-three-tiers-protection.md).
2. Instellingen configureren voor het [delen van informatie over de gevoeligheid met personen buiten uw organisatie](collaborate-with-people-outside-your-organization.md).

## <a name="see-also"></a>Zie ook

[Documentatie over Microsoft 365-beveiliging](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365-compliancedocumentatie](https://docs.microsoft.com/microsoft-365/compliance)

[Welkom bij Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
