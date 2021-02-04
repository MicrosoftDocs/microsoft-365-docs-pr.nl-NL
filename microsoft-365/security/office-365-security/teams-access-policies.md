---
title: Aanbevolen Teams-beleid - Microsoft 365 voor ondernemingen | Microsoft Docs
description: Hier worden de beleidsregels voor Microsoft-aanbevelingen beschreven voor het beveiligen van Teams-communicatie en bestandstoegang.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 12bdf0df1a5b2f616c5b2bed61d69e8226fa5844
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097184"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Beleidsaanbevelingen voor het beveiligen van Teams-chats, -groepen en -bestanden

In dit artikel wordt beschreven hoe u het aanbevolen identiteits- en apparaattoegangsbeleid implementeert om Microsoft Teams-chats, -groepen en -inhoud, zoals bestanden en agenda's, te beschermen. Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits-](identity-access-policies.md)en apparaattoegang, met extra informatie die Teams-specifiek is. Omdat Teams is geïntegreerd met onze andere producten, ziet u ook beleidsaanbevelingen voor het beveiligen van [SharePoint-sites](sharepoint-file-access-policies.md) en -bestanden en beleidsaanbevelingen voor [het beveiligen van e-mail.](secure-email-recommended-policies.md)

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beveiligingslagen voor Teams die kunnen worden toegepast op basis van de granulatie van uw behoeften: basislijn, gevoelig en sterk reguleerd. Meer informatie over deze beveiligingslagen en het aanbevolen beleid waarnaar wordt verwezen in deze aanbevelingen in de configuraties Identiteit en [Apparaattoegang.](microsoft-365-policies-configurations.md)

Meer aanbevelingen specifiek voor de implementatie van Teams worden in dit artikel opgenomen om specifieke verificatie-omstandigheden te behandelen, ook voor gebruikers buiten uw organisatie. U moet deze richtlijnen volgen voor een volledige beveiligingservaring.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Aan de slag met Teams vóór andere afhankelijke services

U hoeft afhankelijke services niet in te stellen om aan de slag te gaan met Microsoft Teams. Al deze services werken 'gewoon'. U moet echter wel voorbereid zijn om de volgende service-gerelateerde elementen te beheren:

- Microsoft 365-groepen
- SharePoint-teamsites
- OneDrive voor Bedrijven
- Exchange-postvakken
- Video's en Planner-plannen streamen (als deze services zijn ingeschakeld)

## <a name="updating-common-policies-to-include-teams"></a>Algemene beleidsregels bijwerken om Teams op te nemen

Om chat, groepen en inhoud in Teams te beschermen, ziet u in het volgende diagram welk beleid moet worden bijgewerkt op basis van het algemene identiteits- en apparaattoegangsbeleid. Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de toewijzing van cloud-apps voor elk beleid dat moet worden bijgewerkt.

[![Overzicht van beleidsupdates voor het beschermen van de toegang tot Teams en de afhankelijke services ervan](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Deze services zijn de afhankelijke services die moeten worden gebruikt bij de toewijzing van cloud-apps voor Teams:

- Microsoft Teams
- SharePoint en OneDrive voor Bedrijven
- Exchange Online
- Skype voor Bedrijven Online
- Microsoft Stream (opnamen van vergadering)
- Microsoft Planner (Planner-taken en planningsgegevens)

Deze tabel bevat het beleid dat opnieuw moet worden [](identity-access-policies.md)gebruikt en een koppeling naar elk beleid in het algemene identiteits- en apparaattoegangsbeleid, dat een breder beleid heeft ingesteld voor alle Office-toepassingen.

|Beveiligingsniveau|Beleidsregels|Meer informatie over de implementatie van Teams|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps. Teams heeft ook regels voor gasttoegang en externe toegang, later in dit artikel vindt u meer informatie over deze regels.|
||[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Neem Teams en afhankelijke services op in de toewijzing van cloud-apps.|
||[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](identity-access-policies.md#high-risk-users-must-change-password)|Dwingt Teams-gebruikers hun wachtwoord te wijzigen wanneer ze zich aanmelden als er activiteit met hoog risico voor hun account wordt gedetecteerd. Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps.|
||[Beleid voor app-gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps. Werk het beleid bij voor elk platform (iOS, Android, Windows).|
||[Beleidsregels voor apparaat compliance definiëren](identity-access-policies.md#define-device-compliance-policies)|Neem Teams en afhankelijke services op in dit beleid.|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Neem Teams en afhankelijke services op in dit beleid.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams heeft ook regels voor gasttoegang en externe toegang, later in dit artikel vindt u meer informatie over deze regels. Neem Teams en afhankelijke services op in dit beleid.|
||[Compatibele pc's *en mobiele* apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Neem Teams en afhankelijke services op in dit beleid.|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|MFA wordt gebruikt door uw organisatie, ongeacht de gebruikersidentiteit. Neem Teams en afhankelijke services op in dit beleid. |
|

## <a name="teams-dependent-services-architecture"></a>Architectuur voor afhankelijke services van Teams

Ter referentie toont het volgende diagram de services waar Teams gebruik van maakt. Zie Microsoft Teams en gerelateerde productiviteitsservices [in Microsoft 365 voor IT-architecten](../../solutions/productivity-illustrations.md)voor meer informatie en illustraties.

[![Diagram met Teams-afhankelijkheden in SharePoint, OneDrive voor Bedrijven en Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gast- en externe toegang voor Teams

Microsoft Teams definieert de volgende toegangstypen:

- **Voor gasttoegang** wordt een Azure AD B2B-account gebruikt voor een gast of externe gebruiker die kan worden toegevoegd als lid van een team en die alle machtigingen heeft tot de communicatie en bronnen van het team.

- **Externe toegang** is voor een externe gebruiker die geen Azure AD B2B-account heeft. Externe toegang kan uitnodigingen en deelname aan gesprekken, chats en vergaderingen omvatten, maar omvat geen teamlidmaatschap en toegang tot de resources van het team.

Beleidsregels voor voorwaardelijke toegang zijn alleen van toepassing op gasttoegang in Teams omdat er een bijbehorend Azure AD B2B-account is.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Zie Beleidsregels voor het toestaan van toegang voor gasten en externe gebruikers met een Azure AD B2B-account voor aanbevolen beleidsregels voor het toestaan van toegang voor gasten en externe gebruikers met een Azure AD [B2B-account.](identity-access-policies-guest-access.md)

### <a name="guest-access-in-teams"></a>Gasttoegang in Teams

Naast het beleid voor gebruikers die intern zijn binnen uw bedrijf of organisatie, kunnen beheerders gasttoegang toestaan, per gebruiker, personen van buiten uw bedrijf of organisatie toegang geven tot Teams-resources en communiceren met interne personen voor zaken zoals groepsgesprekken, chatgesprekken en vergaderingen.

Zie gasttoegang in Teams voor meer informatie over gasttoegang en hoe u deze [kunt implementeren.](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Externe toegang in Teams

Externe toegang wordt soms verward met gasttoegang, dus het is belangrijk om te weten dat deze twee niet-interne toegangsmechanismen verschillende toegangstypen zijn.

Externe toegang is een manier voor Teams-gebruikers vanuit een volledig extern domein om in Teams vergaderingen met uw gebruikers te zoeken, te bellen, te chatten en in te stellen. Beheerders van Teams configureren externe toegang op organisatieniveau. Zie Externe toegang beheren [in Microsoft Teams voor meer informatie.](https://docs.microsoft.com/microsoftteams/manage-external-access)

Externe toegangsgebruikers hebben minder toegang en functionaliteit dan een persoon die is toegevoegd via gasttoegang. Zo kunnen gebruikers met externe toegang met uw interne gebruikers chatten met Teams, maar hebben ze geen toegang tot teamkanalen, bestanden of andere bronnen.

Externe toegang maakt geen gebruik van B2B-gebruikersaccounts van Azure AD en maakt daarom geen gebruik van beleidsregels voor voorwaardelijke toegang.

## <a name="teams-policies"></a>Teams-beleid

Buiten het algemene beleid dat hierboven wordt vermeld, zijn er teams-specifiek beleid dat kan en moet worden geconfigureerd voor het beheren van verschillende Teams-functies.

### <a name="teams-and-channels-policies"></a>Beleid voor Teams en kanalen

Teams en kanalen zijn twee veelgebruikte elementen in Microsoft Teams en er is beleid dat u kunt stellen om te bepalen wat gebruikers wel en niet kunnen doen wanneer ze teams en kanalen gebruiken. U kunt een globaal team maken, maar als uw organisatie 5000 gebruikers of minder heeft, is het waarschijnlijk handig om kleinere teams en kanalen te hebben voor specifieke doeleinden, in overeenstemming met de behoeften van uw organisatie.

Het wordt aanbevolen het standaardbeleid te wijzigen of aangepaste beleidsregels te maken. Via deze koppeling vindt u meer informatie over het beheren van uw beleid: Teambeleid beheren [in Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-policies)

### <a name="messaging-policies"></a>Berichtenbeleid

Berichten of chatberichten kunnen ook worden beheerd via het standaard globale beleid of via aangepaste beleidsregels, en dit kan uw gebruikers helpen met elkaar te communiceren op een manier die geschikt is voor uw organisatie. U kunt deze informatie nagekeken krijgen [bij het beheren van berichtenbeleid in Teams.](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)

### <a name="meeting-policies"></a>Vergaderbeleid

Er zou geen discussie over Teams zijn zonder beleidsregels voor Teams-vergaderingen te plannen en te implementeren. Vergaderingen zijn een belangrijk onderdeel van Teams, waarmee personen formeel aan veel gebruikers tegelijk kunnen vergaderen en presenteren en inhoud kunnen delen die relevant is voor de vergadering. Het is essentieel dat u het juiste beleid voor uw organisatie voor vergaderingen instelt.

Bekijk vergaderbeleid beheren in Teams voor meer [informatie.](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

### <a name="app-permission-policies"></a>App-machtigingsbeleid

Met Teams kunt u ook apps gebruiken op verschillende plaatsen, zoals kanalen of persoonlijke chats. Het is essentieel om beleid te hebben voor welke apps kunnen worden toegevoegd en gebruikt, en waar, voor het onderhouden van een omgeving met inhouds rijk aan inhoud die ook veilig is.

Zie App-machtigingsbeleid beheren [in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)voor meer informatie over app-machtigingsbeleid.

## <a name="next-steps"></a>Volgende stappen

![Stap 4: Beleid voor Microsoft 365-cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
