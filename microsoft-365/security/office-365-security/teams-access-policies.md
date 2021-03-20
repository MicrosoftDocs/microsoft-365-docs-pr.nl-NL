---
title: Aanbevolen Teams-beleid - Microsoft 365 voor | Microsoft Docs
description: Beschrijft het beleid voor Microsoft-aanbevelingen over het beveiligen van Teams-communicatie en bestandstoegang.
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
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916416"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Beleidsaanbevelingen voor het beveiligen van Teams-chats, groepen en bestanden

In dit artikel wordt beschreven hoe u het aanbevolen identiteits- en apparaattoegangsbeleid implementeert ter bescherming van Microsoft Teams-chats, groepen en inhoud, zoals bestanden en agenda's. Deze richtlijnen zijn gebaseerd op het algemene beleid voor [identiteits-](identity-access-policies.md)en apparaattoegang, met aanvullende informatie die specifiek is voor Teams. Omdat Teams is geïntegreerd met onze andere producten, ziet u ook Beleidsaanbevelingen voor het beveiligen van [SharePoint-sites](sharepoint-file-access-policies.md) en -bestanden en beleidsaanbevelingen voor [het beveiligen van e-mail.](secure-email-recommended-policies.md)

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beveiligingslagen voor Teams die kunnen worden toegepast op basis van de granulariteit van uw behoeften: basislijn, gevoelig en sterk geregeld. U vindt meer informatie over deze beveiligingslagen en de aanbevolen beleidsregels waarnaar wordt verwezen in de configuraties Identiteits- en [apparaattoegang.](microsoft-365-policies-configurations.md)

Meer aanbevelingen die specifiek zijn voor De implementatie van Teams worden in dit artikel opgenomen om specifieke verificatie-omstandigheden te behandelen, ook voor gebruikers buiten uw organisatie. U moet deze richtlijnen volgen voor een volledige beveiligingservaring.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Aan de slag met Teams voor andere afhankelijke services

U hoeft niet afhankelijke services in te stellen om aan de slag te gaan met Microsoft Teams. Deze services werken allemaal 'gewoon'. U moet echter wel voorbereid zijn om de volgende service-gerelateerde elementen te beheren:

- Microsoft 365-groepen
- SharePoint-teamsites
- OneDrive voor Bedrijven
- Exchange-postvakken
- Video's en Planner-abonnementen streamen (als deze services zijn ingeschakeld)

## <a name="updating-common-policies-to-include-teams"></a>Gemeenschappelijke beleidsregels bijwerken om Teams op te nemen

Als u chat, groepen en inhoud in Teams wilt beveiligen, wordt in het volgende diagram weergegeven welk beleid moet worden bijgewerkt op basis van het algemene beleid voor identiteits- en apparaattoegang. Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de toewijzing van cloud-apps om elk beleid bij te werken.

[![Overzicht van beleidsupdates voor het beschermen van de toegang tot Teams en de afhankelijke services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Deze services zijn de afhankelijke services die u moet opnemen in de toewijzing van cloud-apps voor Teams:

- Microsoft Teams
- SharePoint en OneDrive voor Bedrijven
- Exchange Online
- Skype voor Bedrijven Online
- Microsoft Stream (vergaderingsopnamen)
- Microsoft Planner (Planner-taken en plangegevens)

Deze tabel bevat het beleid dat opnieuw moet worden [](identity-access-policies.md)bezocht en koppelingen naar elk beleid in het algemene beleid voor identiteits- en apparaattoegang, met het bredere beleid dat is ingesteld voor alle Office-toepassingen.

|Beveiligingsniveau|Beleid|Meer informatie over de implementatie van Teams|
|---|---|---|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico gemiddeld *of* *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps. Teams heeft ook regels voor Gasttoegang en Externe toegang, later in dit artikel vindt u meer informatie over deze regels.|
||[Clients blokkeren die moderne verificatie niet ondersteunen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Neem Teams en afhankelijke services op in de toewijzing van cloud-apps.|
||[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](identity-access-policies.md#high-risk-users-must-change-password)|Teams-gebruikers moeten hun wachtwoord wijzigen wanneer ze zich aanmelden als er activiteit met een hoog risico wordt gedetecteerd voor hun account. Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps.|
||[APP-beleid voor gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps. Werk het beleid voor elk platform bij (iOS, Android, Windows).|
||[Beleidsregels voor apparaat compliance definiëren](identity-access-policies.md#define-device-compliance-policies)|Neem Teams en afhankelijke services op in dit beleid.|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Neem Teams en afhankelijke services op in dit beleid.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog is*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams heeft ook regels voor Gasttoegang en Externe toegang, later in dit artikel vindt u meer informatie over deze regels. Neem Teams en afhankelijke services op in dit beleid.|
||[Compatibele pc's *en mobiele* apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Neem Teams en afhankelijke services op in dit beleid.|
|**Sterk gereglementeerd**|[*Altijd* MFA vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ongeacht de gebruikersidentiteit, wordt MFA gebruikt door uw organisatie. Neem Teams en afhankelijke services op in dit beleid. |
|

## <a name="teams-dependent-services-architecture"></a>Teams-afhankelijke servicesarchitectuur

In het volgende diagram ziet u de services waar Teams op vertrouwt. Zie Microsoft Teams en gerelateerde productiviteitsservices [in Microsoft 365 voor IT-architecten](../../solutions/productivity-illustrations.md)voor meer informatie en illustraties.

[![Diagram met Teams-afhankelijkheden op SharePoint, OneDrive voor Bedrijven en Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gast- en externe toegang voor Teams

Microsoft Teams definieert de volgende toegangstypen:

- **Gasttoegang** maakt gebruik van een Azure AD B2B-account voor een gast- of externe gebruiker die kan worden toegevoegd als lid van een team en alle machtigingen heeft voor toegang tot de communicatie en bronnen van het team.

- **Externe toegang** is voor een externe gebruiker die geen Azure AD B2B-account heeft. Externe toegang kan uitnodigingen en deelname aan gesprekken, chats en vergaderingen omvatten, maar omvat geen teamlidmaatschap en toegang tot de resources van het team.

Beleid voor voorwaardelijke toegang is alleen van toepassing op gasttoegang in Teams omdat er een bijbehorend Azure AD B2B-account is.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Zie Beleidsregels voor het toestaan van toegang tot gast- en externe gebruikers met een Azure AD [B2B-account](identity-access-policies-guest-access.md)voor aanbevolen beleidsregels.

### <a name="guest-access-in-teams"></a>Gasttoegang in Teams

Naast het beleid voor gebruikers die intern binnen uw bedrijf of organisatie zijn, kunnen beheerders gasttoegang toestaan om personen die buiten uw bedrijf of organisatie zijn, toegang te geven tot Teams-resources en interactie met interne personen toe te staan voor zaken als groepsgesprekken, chatgesprekken en vergaderingen.

Zie Gasttoegang voor Teams voor meer informatie over gasttoegang en hoe u deze [implementeert.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Externe toegang in Teams

Externe toegang wordt soms verward met gasttoegang, dus het is belangrijk om duidelijk te zijn dat deze twee niet-interne toegangsmechanismen verschillende typen toegang zijn.

Externe toegang is een manier voor Teams-gebruikers van een heel extern domein om vergaderingen met uw gebruikers in Teams te zoeken, te bellen, te chatten en in te stellen. Teams-beheerders configureren externe toegang op organisatieniveau. Zie Externe toegang beheren in Microsoft Teams voor [meer informatie.](/microsoftteams/manage-external-access)

Externe toegangsgebruikers hebben minder toegang en functionaliteit dan een persoon die is toegevoegd via gasttoegang. Gebruikers van externe toegang kunnen bijvoorbeeld chatten met interne gebruikers met Teams, maar hebben geen toegang tot teamkanalen, bestanden of andere bronnen.

Externe toegang gebruikt geen Azure AD B2B-gebruikersaccounts en gebruikt daarom geen beleid voor voorwaardelijke toegang.

## <a name="teams-policies"></a>Teams-beleid

Buiten de algemene beleidsregels die hierboven worden vermeld, zijn er teamsspecifieke beleidsregels die kunnen en moeten worden geconfigureerd voor het beheren van verschillende Teams-functionaliteiten.

### <a name="teams-and-channels-policies"></a>Teams- en kanalenbeleid

Teams en kanalen zijn twee veelgebruikte elementen in Microsoft Teams en er zijn beleidsregels die u kunt gebruiken om te bepalen wat gebruikers wel en niet kunnen doen bij het gebruik van teams en kanalen. Hoewel u een globaal team kunt maken, als uw organisatie 5000 gebruikers of minder heeft, is het waarschijnlijk handig om kleinere teams en kanalen te hebben voor specifieke doeleinden, in overeenstemming met uw organisatiebehoeften.

Het is raadzaam het standaardbeleid te wijzigen of aangepaste beleidsregels te maken en u kunt meer informatie over het beheren van uw beleid vinden via deze koppeling: Teams-beleid [beheren in Microsoft Teams.](/microsoftteams/teams-policies)

### <a name="messaging-policies"></a>Berichtenbeleid

Berichten of chats kunnen ook worden beheerd via het standaard globale beleid of via aangepast beleid, zodat uw gebruikers met elkaar kunnen communiceren op een manier die geschikt is voor uw organisatie. Deze informatie kan worden bekeken op [Berichtenbeleid beheren in Teams.](/microsoftteams/messaging-policies-in-teams)

### <a name="meeting-policies"></a>Vergaderbeleid

Geen enkele discussie over Teams is voltooid zonder het plannen en implementeren van beleid rond Teams-vergaderingen. Vergaderingen vormen een essentieel onderdeel van Teams, zodat personen elkaar formeel kunnen ontmoeten en presenteren aan veel gebruikers tegelijk en inhoud kunnen delen die relevant is voor de vergadering. Het instellen van het juiste beleid voor uw organisatie rond vergaderingen is essentieel.

Voor meer informatie kunt u [vergaderbeleid beheren in Teams bekijken.](/microsoftteams/meeting-policies-in-teams)

### <a name="app-permission-policies"></a>App-machtigingsbeleid

In Teams kunt u ook apps op verschillende plaatsen gebruiken, zoals kanalen of persoonlijke chats. Beleidsregels voor welke apps kunnen worden toegevoegd en gebruikt, en waar, is essentieel voor het behoud van een omgeving met inhoud die ook veilig is.

Zie Machtigingsbeleid voor apps beheren [in Microsoft Teams](/microsoftteams/teams-app-permission-policies)voor meer informatie over app-machtigingsbeleid.

## <a name="next-steps"></a>Volgende stappen

![Stap 4: Beleidsregels voor Cloud-apps van Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleid voor voorwaardelijke toegang configureren voor:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)