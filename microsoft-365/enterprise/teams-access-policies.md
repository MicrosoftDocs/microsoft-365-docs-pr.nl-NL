---
title: Aanbevolen teams-beleid - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft het beleid voor Microsoft-aanbevelingen over het beveiligen van de communicatie en bestandstoegang van Teams.
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
ms.openlocfilehash: f1a4a4ea69efc3c68bdc8ed66aa18833a28feb94
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636721"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Beleidsaanbevelingen voor het beveiligen van Teams-chats, -groepen en -bestanden

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor identiteits- en apparaattoegangs implementeren om Teams-chats, -groepen en -inhoud zoals bestanden en agenda's te beschermen. Deze richtlijnen bouwen voort op het [beleid voor algemene identiteits- en apparaattoegangsbeleid,](identity-access-policies.md)met aanvullende informatie die teamsspecifiek is. Omdat Teams integreert met onze andere producten, zie ook [beleidsaanbevelingen voor het beveiligen van SharePoint-sites en bestanden](sharepoint-file-access-policies.md) en [beleidsaanbevelingen voor het beveiligen van e-mail.](secure-email-recommended-policies.md)

Deze aanbevelingen zijn gebaseerd op drie verschillende beveiligings- en beschermingsniveaus voor teams die kunnen worden toegepast op basis van de granulariteit van uw behoeften: basislijn, gevoelig en sterk gereguleerd. Meer informatie over deze beveiligingsniveaus en het aanbevolen beleid waarnaar wordt verwezen in deze aanbevelingen vindt u in de [configuraties voor identiteits- en apparaattoegang.](microsoft-365-policies-configurations.md)

Aanvullende aanbevelingen die specifiek zijn voor de implementatie van Teams zijn opgenomen in dit artikel voor specifieke verificatieomstandigheden, ook voor gebruikers buiten uw organisatie. U moet deze richtlijnen volgen voor een volledige beveiligingservaring.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Aan de slag met Teams voor andere afhankelijke services

U hoeft afhankelijke services niet in te schakelen om aan de slag te gaan met Microsoft Teams. Deze zullen allemaal "gewoon werken." U moet echter wel bereid zijn om het volgende te beheren:

- Microsoft 365-groepen
- SharePoint-teamsites
- OneDrive voor Bedrijven
- Postvakken
- Video's en Planner-abonnementen streamen (als deze services zijn ingeschakeld)

## <a name="updating-common-policies-to-include-teams"></a>Algemeen beleid bijwerken om Teams op te nemen

In het volgende diagram wordt de set aanbevolen beleidsregels voor het beschermen van chat, groepen en inhoud in Teams weergegeven. Het potloodpictogram geeft aan welk beleid opnieuw moet worden bekeken om er zeker van te zijn dat Teams en afhankelijke services zijn opgenomen in de toewijzing van cloud-apps.

![Een diagram met informatie over het gebruik van Microsoft Teams op verschillende apparaten.](../media/identity-access-ruleset-teams.png)

Dit zijn de afhankelijke services die moeten worden opgenomen in de toewijzing van cloud-apps voor Teams:

- Microsoft Teams
- SharePoint Online en OneDrive voor Bedrijven
- Exchange Online
- Skype voor Bedrijven Online
- Microsoft Stream (vergaderopnamen)
- Microsoft Planner (Planner-taken en plangegevens)

In deze tabel worden de beleidsregels weergegeven die opnieuw moeten worden bekeken en wordt koppelingen naar elk beleid weergegeven in [het beleid voor algemene identiteits- en apparaattoegangsbeleid](identity-access-policies.md), dat de bredere regelset heeft voor alle Office-toepassingen.

|Beschermingsniveau|Beleid|Meer informatie voor de implementatie van teams|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps. Teams hebben ook gasttoegangs- en externe toegangsregels om rekening mee te houden, u vindt hier later in dit artikel meer over.|
|        |[Cliënten blokkeren die geen moderne verificatie ondersteunen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Neem Teams en afhankelijke services op in de toewijzing van cloud-apps.|
|        |[Gebruikers met een hoog risico moeten het wachtwoord wijzigen](identity-access-policies.md#high-risk-users-must-change-password)|Dwingt Teams-gebruikers om hun wachtwoord te wijzigen wanneer ze zich aanmelden als activiteit met een hoog risico wordt gedetecteerd voor hun account. Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps.|
|        |[App-beleid voor gegevensbescherming toepassen](identity-access-policies.md#apply-app-data-protection-policies)|Zorg ervoor dat Teams en afhankelijke services zijn opgenomen in de lijst met apps. Werk het beleid voor elk platform (iOS, Android, Windows) bij.|
|        |[Goedgekeurde apps en APP-beveiliging vereisen](identity-access-policies.md#require-approved-apps-and-app-protection)|Neem teams en afhankelijke services op in dit beleid.|
|        |[Nalevingsbeleid voor apparaten definiëren](identity-access-policies.md#define-device-compliance-policies)|Neem teams en afhankelijke services op in dit beleid.|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Neem teams en afhankelijke services op in dit beleid.|
|**Gevoelig**|[MFA vereisen wanneer het aanmeldingsrisico *laag,* *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams hebben ook gasttoegangs- en externe toegangsregels om rekening mee te houden, u vindt hier later in dit artikel meer over. Neem teams en afhankelijke services op in dit beleid.|
|         |[Compatibele pc's *en* mobiele apparaten vereisen](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Neem teams en afhankelijke services op in dit beleid.|
|**Sterk gereglementeerd**|[*Altijd* mfa nodig](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ongeacht de gebruikersidentiteit wordt MFA gebruikt door uw organisatie. Neem teams en afhankelijke services op in dit beleid.
| | |

## <a name="teams-dependent-services-architecture"></a>Teams afhankelijke services architectuur

Ter referentie illustreert het volgende diagram de services waarop Teams vertrouwt. Zie Microsoft Teams en [gerelateerde productiviteitsservices in Microsoft 365 voor IT-architecten voor](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects)meer informatie en aanvullende illustraties.

![Diagram met afhankelijkheden van Teams van SharePoint Online, OneDrive voor Bedrijven en Exchange.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Gast- en externe toegang voor Teams inschakelen

In Azure AD zijn gast- en externe gebruikers hetzelfde. Het gebruikerstype voor beide is Gast. Gastgebruikers zijn B2B-gebruikers. Microsoft Teams maakt onderscheid tussen gastgebruikers en externe gebruikers in de app. Hoewel het belangrijk is om te begrijpen hoe elk van deze worden behandeld in Teams, zijn beide typen gebruikers B2B-gebruikers in Azure AD en zijn de aanbevolen beleidsregels voor B2B-gebruikers op beide van toepassing. Zie Beleid voor het toestaan [van gast- en externe B2B-toegang](identity-access-policies-guest-access.md)voor aanbevolen beleidsregels om gasttoegang toe te staan.

### <a name="guest-access-in-teams"></a>Gasttoegang in teams

Naast het beleid voor gebruikers die intern zijn in uw bedrijf of organisatie, kunnen beheerders gasttoegang toestaan om per gebruiker mensen die zich buiten uw bedrijf of organisatie bevinden, toegang te geven tot Teams-bronnen en interactie te hebben met interne mensen voor zaken als groepsgesprekken, chat en vergaderingen. Meer informatie over gasttoegang vindt u via de volgende link: [Teams gasttoegang](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Externe toegang in Teams

Externe toegang wordt soms verward met gasttoegang, dus het is belangrijk om duidelijk te zijn dat deze twee niet-interne toegangsmechanismen eigenlijk heel anders zijn. Terwijl gasttoegang plaatsvindt per gebruiker (u voegt één gebruiker tegelijk toe), u met een beheerder alle gebruikers van een extern domein tegelijkertijd aan Teams toevoegen. Deze externe gebruikers hebben echter minder toegang en functionaliteit dan een persoon die is toegevoegd via gasttoegang. Externe toeganggebruikers kunnen chatten met uw interne gebruikers via Teams.

Voor meer informatie over externe toegang en hoe u deze implementeren als dat nodig is, raadpleegt [u Externe toegang beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Teambeleid

Buiten de hierboven genoemde algemene beleidsregels zijn er teamsspecifieke beleidsregels die kunnen en moeten worden geconfigureerd om verschillende Teams-functionaliteiten te beheren.

### <a name="teams-and-channels-policies"></a>Beleid voor teams en kanalen

Teams en kanalen zijn twee veelgebruikte elementen in Microsoft Teams en er zijn beleidsregels die u invoeren om te bepalen wat gebruikers wel en niet kunnen doen bij het gebruik van teams en kanalen. Hoewel u een wereldwijd team maken, als uw organisatie 5000 gebruikers of minder heeft, zult u het waarschijnlijk nuttig vinden om kleinere teams en kanalen voor specifieke doeleinden te hebben, in overeenstemming met uw organisatorische behoeften.

Het standaardbeleid wijzigen of aangepaste beleidsregels maken wordt aanbevolen en u meer informatie vinden over het beheren van uw beleid op deze koppeling: [Teambeleid beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Berichtenbeleid

Berichten of chatberichten kunnen ook worden beheerd via het standaardalgemene beleid of via aangepaste beleidsregels, en dit kan uw gebruikers helpen met elkaar te communiceren op een manier die geschikt is voor uw organisatie. Deze informatie kan worden beoordeeld op [Het beheer van berichtenbeleid in Teams.](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)

### <a name="meeting-policies"></a>Vergaderbeleid

Geen discussie over Teams zou compleet zijn zonder het plannen en implementeren van beleid rond Teams-vergaderingen. Vergaderingen zijn een essentieel onderdeel van Teams, waardoor mensen elkaar formeel kunnen ontmoeten en aan veel gebruikers tegelijk kunnen presenteren, en inhoud kunnen delen die relevant is voor de vergadering. Het is essentieel om het juiste beleid voor uw organisatie rond vergaderingen vast te stellen.

Raadpleeg het [beleid voor vergaderen beheren in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) voor meer informatie.

### <a name="app-permission-policies"></a>Machtigingenbeleid voor apps

Met teams u ook apps gebruiken op verschillende plaatsen, zoals kanalen of persoonlijke chats. Het hebben van beleid rond welke apps kunnen worden toegevoegd en gebruikt, en waar, is essentieel voor het behoud van een inhoud-rijke omgeving die ook veilig is.

Voor meer informatie over het beleid voor machtigingen voor apps raadpleegt u [Het beleid voor app-machtigingen beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over het inschakelen van voorwaardelijke toegang voor Exchange Online](secure-email-recommended-policies.md)


