---
title: Aanbevolen teams-beleid - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen over het beveiligen van teamscommunicatie en bestandstoegang.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 4c72e340092bbd366277114a56aae7574d43dab5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808815"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Beleidsaanbevelingen voor het beveiligen van Teams-chats, groepen en bestanden

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegang implementeert om Teams-chats, groepen en inhoud zoals bestanden en agenda's te beschermen. Deze richtlijnen bouwt voort op het [beleid voor algemene identiteits- en apparaattoegang](identity-access-policies.md), met aanvullende informatie die teamspecifiek is. Omdat Teams integreert met onze andere producten, raadpleegt u ook [beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden](sharepoint-file-access-policies.md) en [beleidsaanbevelingen voor het beveiligen van e-mail.](secure-email-recommended-policies.md)

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligingsniveaus en -beveiliging voor teams die kunnen worden toegepast op basis van de granulariteit van uw behoeften: basislijn, gevoeligheid en sterk gereguleerd. Meer informatie over deze beveiligingslagen en het aanbevolen beleid waarnaar deze aanbevelingen verwijzen, vindt u in de [configuraties voor identiteits- en apparaattoegang.](microsoft-365-policies-configurations.md)

Aanvullende aanbevelingen die specifiek zijn voor de implementatie van Teams, zijn opgenomen in dit artikel voor specifieke verificatieomstandigheden, ook voor gebruikers buiten uw organisatie. U moet deze begeleiding volgen voor een volledige beveiligingservaring.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Aan de slag met Teams voor andere afhankelijke services

U hoeft niet afhankelijke services in te schakelen om aan de slag te gaan met Microsoft Teams. Deze zullen allemaal 'gewoon werken'. U moet echter wel bereid zijn om het volgende te beheren:

- Office 365-groepen
- SharePoint-teamsites
- OneDrive voor Bedrijven
- Postvakken
- Video's en Planner-abonnementen streamen (als deze services zijn ingeschakeld)

## <a name="updating-common-policies-to-include-teams"></a>Gemeenschappelijk beleid bijwerken met teams

Het volgende diagram illustreert de set aanbevolen beleidsregels voor het beschermen van chat, groepen en inhoud in Teams. Het potloodpictogram geeft aan welk beleid opnieuw moet worden uitgevoerd om er zeker van te zijn dat Teams en afhankelijke services zijn opgenomen in de toewijzing van cloud-apps.

![Een diagram dat laat zien hoe u Microsoft Teams op verschillende apparaten gebruiken.](../media/identity-access-ruleset-teams.png)

Dit zijn de afhankelijke services die moeten worden opgenomen in de toewijzing van cloud-apps voor Teams:

- Microsoft Teams
- SharePoint Online en OneDrive voor Bedrijven
- Exchange Online
- Skype voor Bedrijven Online
- Microsoft Stream (opnamen voor vergaderingen)
- Microsoft Planner (Planner-taken en plangegevens)

In deze tabel worden de beleidsregels weergegeven die opnieuw moeten worden bekeken en koppelingen naar elk beleid in [het beleid voor algemene identiteits- en apparaattoegang](identity-access-policies.md), dat de bredere regelset voor alle Office-toepassingen heeft.

|Beschermingsniveau|Beleid|Meer informatie voor de implementatie van teams|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de lijst met apps. Teams heeft ook regels voor gasttoegang en externe toegang om rekening mee te houden, je zult hier later in dit artikel meer over te weten komen.|
|        |[Clients blokkeren die geen ondersteuning bieden voor moderne verificatie](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Neem Teams en afhankelijke services op in de toewijzing van cloud-apps.|
|        |[Gebruikers met een hoog risico moeten wachtwoord wijzigen](identity-access-policies.md#high-risk-users-must-change-password)|Dwingt Teams-gebruikers om hun wachtwoord te wijzigen wanneer ze zich aanmelden als activiteit met een hoog risico wordt gedetecteerd voor hun account. Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de lijst met apps.|
|        |[App-beveiligingsbeleid definiëren](identity-access-policies.md#define-app-protection-policies)|Zorg ervoor dat teams en afhankelijke services zijn opgenomen in de lijst met apps. Werk het beleid voor elk platform bij (iOS, Android, Windows).|
|        |[Goedgekeurde apps vereisen](identity-access-policies.md#require-approved-apps)|Neem teams en afhankelijke services op in dit beleid.|
|        |[Apparaatnalevingsbeleid definiëren](identity-access-policies.md#define-device-compliance-policies)|Neem teams en afhankelijke services op in dit beleid.|
|        |[Compatibele pc's vereisen](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Neem teams en afhankelijke services op in dit beleid.|
|**Gevoelige**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams heeft ook regels voor gasttoegang en externe toegang om rekening mee te houden, je zult hier later in dit artikel meer over te weten komen. Neem teams en afhankelijke services op in dit beleid.|
|         |[Compatibele pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Neem teams en afhankelijke services op in dit beleid.|
|**Sterk gereguleerd**|[*Altijd* mfa vereisen](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ongeacht de identiteit van de gebruiker wordt MFA gebruikt door uw organisatie. Neem teams en afhankelijke services op in dit beleid.
| | |

## <a name="teams-dependent-services-architecture"></a>Teams afhankelijke services architectuur

Ter referentie, het volgende diagram illustreert de diensten teams vertrouwt op. Zie Microsoft Teams en [gerelateerde productiviteitsservices in Microsoft 365 voor IT-architecten voor](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects)meer informatie en aanvullende illustraties.

![Diagram met afhankelijkheden van Teams op SharePoint Online, OneDrive voor Bedrijven en Exchange.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Gast- en externe toegang voor teams inschakelen

In Azure AD zijn gast- en externe gebruikers hetzelfde. Het gebruikerstype voor beide is Gast. Gastgebruikers zijn B2B-gebruikers. Microsoft Teams maakt onderscheid tussen gastgebruikers en externe gebruikers in de app. Hoewel het belangrijk is om te begrijpen hoe elk van deze gebruikers in Teams wordt behandeld, zijn beide typen gebruikers B2B-gebruikers in Azure AD en het aanbevolen beleid voor B2B-gebruikers is op beide van toepassing. Zie [Beleid voor gast- en externe B2B-toegang](identity-access-policies-guest-access.md)voor aanbevolen beleidsregels om gasttoegang toe te staan.

### <a name="guest-access-in-teams"></a>Toegang tot gasten in teams

Naast het beleid voor gebruikers die intern zijn voor uw bedrijf of organisatie, kunnen beheerders gasttoegang toestaan om per gebruiker mensen die buiten uw bedrijf of organisatie staan, toegang te geven tot teamsbronnen en te communiceren met interne mensen voor zaken als groepsgesprekken, chat en vergaderingen. Meer informatie over Guest Access vindt u via de volgende link: [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Externe toegang in teams

Externe toegang wordt soms verward met gasttoegang, dus het is belangrijk om duidelijk te zijn dat deze twee niet-interne toegangsmechanismen eigenlijk heel verschillend zijn. Terwijl gasttoegang per gebruiker plaatsvindt (u voegt één gebruiker tegelijk toe), u, wanneer een beheerder externe toegang toestaat, alle gebruikers van een extern domein tegelijkertijd toevoegen aan Teams. Deze externe gebruikers hebben echter minder toegang en functionaliteit dan een persoon die via gasttoegang is toegevoegd. Externe toegang gebruikers kunnen chatten met uw interne gebruikers via Teams.

Als u meer wilt lezen over externe toegang en hoe u deze implementeren als dat nodig is, raadpleegt u [Externe toegang beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Beleid teams

Buiten het hierboven genoemde algemene beleid zijn er teamsspecifieke beleidsregels die kunnen en moeten worden geconfigureerd om verschillende Teams-functionaliteiten te beheren.

### <a name="teams-and-channels-policies"></a>Beleid voor teams en kanalen

Teams en kanalen zijn twee veelgebruikte elementen in Microsoft Teams en er zijn beleidsregels die u voeren om te bepalen wat gebruikers wel en niet kunnen doen bij het gebruik van teams en kanalen. Hoewel u een wereldwijd team maken, zult u het nuttig vinden om kleinere teams en kanalen te hebben voor specifieke doeleinden, in overeenstemming met uw organisatiebehoeften.

Het wijzigen van het standaardbeleid of het maken van aangepast beleid wordt aanbevolen en u meer informatie vinden over het beheren van uw beleid via deze koppeling: [Het beleid van teams beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Berichtenbeleid

Berichten of chat kunnen ook worden beheerd via het standaardglobale beleid of via aangepast beleid, en dit kan uw gebruikers helpen om met elkaar te communiceren op een manier die geschikt is voor uw organisatie. Deze informatie kan worden beoordeeld op Het beheer van [berichtenbeleid in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Beleid voor vergadering

Geen discussie over Teams zou compleet zijn zonder het plannen en implementeren van beleid rond Teams vergaderingen. Vergaderingen zijn een essentieel onderdeel van Teams, zodat mensen veel gebruikers formeel tegelijk kunnen ontmoeten en presenteren, en inhoud kunnen delen die relevant zijn voor de vergadering. Het is essentieel om het juiste beleid voor uw organisatie rond vergaderingen in te stellen.

Bekijk [het gespreksbeleid beheren in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) voor meer informatie.

### <a name="app-permission-policies"></a>Beleid voor app-machtigingen

Met Teams kun je apps ook op verschillende plaatsen gebruiken, zoals kanalen of persoonlijke chats. Het hebben van beleid rond welke apps kunnen worden toegevoegd en gebruikt, en waar, is essentieel voor het behoud van een inhoudsrijke omgeving die ook veilig is.

Voor meer informatie over app-machtigingsbeleid raadpleegt u [het beleid voor app-machtigingen beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over het inschakelen van voorwaardelijke toegang voor Exchange Online](secure-email-recommended-policies.md)


