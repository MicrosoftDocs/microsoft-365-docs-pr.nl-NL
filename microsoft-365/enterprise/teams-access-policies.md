---
title: 'Aanbevolen beleidsregels voor teams: Microsoft 365 for Enterprise | Microsoft docs'
description: Een beschrijving van de beleidsregels voor Microsoft-aanbevelingen over het beveiligen van de communicatie van teams en toegang tot bestanden.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: b9a9044a063c01724710679682e1edbe458dec0f
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327131"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Beleids aanbevelingen voor het beveiligen van teams-chats,-groepen en-bestanden

In dit artikel wordt uitgelegd hoe u de aanbevolen identiteit en het beleid voor het openen van een apparaat kunt implementeren om Microsoft teams-chats, groepen en inhoud, zoals bestanden en agenda's, te beschermen. Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en Apparaattoegang](identity-access-policies.md), met aanvullende informatie die specifiek is voor teams. Aangezien teams met onze andere producten integreren, zie ook [beleids aanbevelingen voor het beveiligen van SharePoint-sites en-bestanden](sharepoint-file-access-policies.md) en- [aanbevelingen voor het beveiligen van e-mail](secure-email-recommended-policies.md).

Deze aanbevelingen maken deel uit van drie verschillende niveaus voor beveiliging en bescherming voor teams die op de granulatie van uw behoeften kunnen worden toegepast: basislijn, gevoelige en nadrukkelijk gereglementeerde. U vindt meer informatie over deze beveiligingslagen en de aanbevolen beleidsregels waarnaar wordt verwezen door deze aanbevelingen in de [configuraties voor identiteit en Apparaattoegang](microsoft-365-policies-configurations.md).

In dit artikel vindt u aanvullende aanbevelingen die specifiek zijn voor de implementatie van teams, waaronder specifieke verificatie omstandigheden, waaronder gebruikers van buiten uw organisatie. U dient deze richtlijnen te volgen voor een volledige beveiligings ervaring.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Aan de slag met teams vóór andere afhankelijke services

U hoeft geen afhankelijke services in te schakelen om aan de slag te gaan met Microsoft teams. Dit is allemaal alles wat u allemaal hoeft te gebruiken. U moet echter wel voorbereid zijn om het volgende te beheren:

- Microsoft 365-groepen
- SharePoint-teamsites
- OneDrive voor Bedrijven
- Exchange-postvakken
- Video's en planner-abonnementen streamen (als deze services zijn ingeschakeld)

## <a name="updating-common-policies-to-include-teams"></a>Veelgebruikte beleidsregels bijwerken voor het opnemen van teams

In het volgende diagram ziet u welke beleidsregels u moet bijwerken vanuit de veelgebruikte beleidsregels voor identiteits-en toegangsbeleid om chatten, groepen en inhoud in teams te beschermen. Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de toewijzing van Cloud-apps voor elk beleid dat u wilt bijwerken.

[![Overzicht van beleidsupdates voor de bescherming van de toegang tot teams en de afhankelijke services](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Dit zijn de afhankelijke services die moeten worden opgenomen in de toewijzing van Cloud-apps voor teams:

- Microsoft Teams
- SharePoint en OneDrive voor Bedrijven
- Exchange Online
- Skype voor Bedrijven Online
- Microsoft stream (opnamen van vergaderingen)
- Microsoft planner (taken plannen en gegevens plannen)

In deze tabel vindt u een overzicht van de beleidsregels die moeten worden Revisited en koppelingen naar de verschillende beleidsregels moeten worden opgenomen in het [beleid voor veelgebruikte identiteits-en Apparaattoegang](identity-access-policies.md), waarvan de bredere beleidsregels voor alle Office-toepassingen zijn ingesteld.

|Beveiligingsniveau|Lijnen|Meer informatie voor de implementatie van teams|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de lijst met apps. Voor teams zijn gasttoegang en regels voor externe toegang ter overweging, u vindt hier meer informatie over deze verderop in dit artikel.|
|        |[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Teams en afhankelijke services opnemen in de toewijzing van Cloud-apps.|
|        |[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](identity-access-policies.md#high-risk-users-must-change-password)|Zorgt ervoor dat teams gebruikers hun wachtwoord kunnen wijzigen bij het aanmelden als er een High Risk-activiteit voor hun account wordt gedetecteerd. Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de lijst met apps.|
|        |[Beleid voor APP-gegevensbeveiliging toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de lijst met apps. Werk het beleid voor elk platform (iOS, Android, Windows) bij.|
|        |[Beleidsregels voor naleving van apparaten definiëren](identity-access-policies.md#define-device-compliance-policies)|Teams en afhankelijke services opnemen in dit beleid.|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Teams en afhankelijke services opnemen in dit beleid.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeld risico *slecht*, *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Voor teams zijn gasttoegang en regels voor externe toegang ter overweging, u vindt hier meer informatie over deze verderop in dit artikel. Teams en afhankelijke services opnemen in dit beleid.|
|         |[Compatibele Pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Teams en afhankelijke services opnemen in dit beleid.|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ongeacht de gebruikersidentiteit wordt MFA gebruikt door uw organisatie. Teams en afhankelijke services opnemen in dit beleid. |
| | |

## <a name="teams-dependent-services-architecture"></a>Architectuur van gebonden Services voor teams

In het volgende diagram ziet u een overzicht van de services teams. Zie [Microsoft teams en bijbehorende productiviteitsservices in Microsoft 365 voor IT-architecten](../solutions/productivity-illustrations.md)voor meer informatie en andere illustraties.

[![Diagram met de afhankelijkheden van teams in SharePoint, OneDrive voor bedrijven en Exchange](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gast en externe toegang voor teams

In Microsoft teams wordt het volgende gedefinieerd:

- **Gasttoegang** maakt gebruik van een Azure AD B2B-account voor een gast of externe gebruiker die kan worden toegevoegd als lid van een team en gemachtigd zijn om toegang te krijgen tot de communicatie en de bronnen van het team.

- **Externe toegang** is bedoeld voor externe gebruikers die geen Azure AD B2B-account hebben. Externe toegang omvat uitnodigingen en deelnemen aan gesprekken, chats en vergaderingen, maar omvat geen team lidmaatschap en toegang tot de bronnen van het team.

Beleidsregels voor voorwaardelijke toegang gelden alleen voor gasttoegang in teams omdat er een Azure AD B2B-account is.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

Zie beleidsregels voor het toestaan van toegang tot [gastaccounts en externe B2B-accounts](identity-access-policies-guest-access.md)voor aanbevolen beleidsregels voor toegang voor gasten en externe gebruikers met een Azure AD B2B-account.

### <a name="guest-access-in-teams"></a>Gasttoegang in teams

Naast de beleidsregels voor gebruikers die intern zijn voor uw bedrijf of organisatie, kunnen beheerders de toegang voor gasten toestaan, gebruikers die buiten uw bedrijf of organisatie deelnemen aan teams-bronnen en interactie met interne personen voor zaken zoals groepsgesprekken, chatten en vergaderingen. 

Zie voor meer informatie over gasttoegang en hoe u deze implementeert,  [gasttoegang voor teams](https://docs.microsoft.com/microsoftteams/guest-access).

### <a name="external-access-in-teams"></a>Externe toegang in teams

Externe toegang wordt soms niet verward met gasttoegang, dus het is belangrijk dat deze twee niet-interne toegangs mechanismen werkelijk afwijken. 

Externe toegang is een manier om teams-gebruikers van een volledig extern domein in te stellen, te bellen, te chatten en vergaderingen met uw gebruikers te vinden in teams. Beheerders van teams configureren externe toegang op organisatieniveau. Zie [externe toegang beheren in Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-external-access)voor meer informatie.

Externe gebruikers hebben geen toegang en functionaliteit dan een persoon die is toegevoegd via gasttoegang. Gebruikers van externe toegang kunnen bijvoorbeeld chatten met uw interne gebruikers met teams, maar hebben geen toegang tot team kanalen, bestanden of andere informatiebronnen.

Externe toegang maakt geen gebruik van Azure AD B2B-gebruikersaccounts en maakt daarom geen gebruik van regels voor voorwaardelijke toegang. 

## <a name="teams-policies"></a>Beleidsregels voor teams

Buiten de hierboven vermelde veelgebruikte beleidsregels zijn er specifieke beleidsregels die kunnen worden geconfigureerd voor het beheren van diverse team functies.

### <a name="teams-and-channels-policies"></a>Beleidsregels voor teams en kanalen

Teams en kanalen zijn twee veelgebruikte elementen in Microsoft teams, en er zijn beleidsregels die u kunt gebruiken om te bepalen wat gebruikers met teams en kanalen kunnen doen. Hoewel u een algemeen team kunt maken en uw organisatie 5000-gebruikers of minder weet, kunt u waarschijnlijk het beste kleinere teams en kanalen voor specifieke doeleinden voor specifieke doeleinden, in overeenstemming met de behoeften van uw organisatie.

U wordt aangeraden het standaardbeleid te wijzigen of aangepaste beleidsregels te maken en u vindt hier meer informatie over het beheren van uw beleidsregels op deze koppeling: [beleidsregels voor teams in Microsoft teams beheren](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Berichten beleid

U kunt berichten en chatberichten ook beheren via het standaard globale beleid, of via een aangepast beleid, zodat uw gebruikers kunnen communiceren op een andere manier die geschikt is voor uw organisatie. U kunt deze informatie nakijken via [berichten beleid beheren in teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Beleidsregels voor vergaderingen

Geen enkele discussie van teams kon worden voltooid zonder een beleid te plannen en te implementeren rond teams-vergaderingen. Vergaderingen zijn een essentieel onderdeel van teams, zodat personen formeel kunnen vergaderen en presenteren aan veel gebruikers tegelijk, en de inhoud van de vergadering delen. Het juiste beleid instellen voor uw organisatie is van essentieel belang.

Lees hoe u [vergaderings beleidsregels beheert in teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) voor meer informatie.

### <a name="app-permission-policies"></a>App-machtigingsbeleid

In teams kunt u ook apps gebruiken op verschillende plaatsen, zoals kanalen of persoonlijke chats. Met beleidsregels rond welke apps kunnen worden toegevoegd en gebruikt, en waar is het essentieel dat u een omgeving met uitgebreide inhoud die ook veilig is.

Zie [machtigingsbeleid voor apps in Microsoft teams beheren](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)voor meer informatie over machtigingsbeleid voor apps.

## <a name="next-steps"></a>Volgende stappen

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

