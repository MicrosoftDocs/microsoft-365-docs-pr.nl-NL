---
title: Toegang in Microsoft 365-groepen, Teams en SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Meer informatie over toegang in Microsoft 365-groepen, Teams en SharePoint.
ms.openlocfilehash: 24a8a43f05206c9f1c0cd07aef480b330d968935
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838707"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Toegang in Microsoft 365-groepen, Teams en SharePoint

Er zijn veel besturingselementen waarmee u kunt bepalen hoe personen toegang krijgen tot resources in groepen, teams en SharePoint. Bekijk deze opties en bedenk hoe deze worden toe te schrijven aan uw zakelijke behoeften, de gevoeligheid van uw gegevens en het bereik van personen met wie uw gebruikers moeten samenwerken.

De volgende tabel bevat een beknopt overzicht van de toegangsbesturingselementen die beschikbaar zijn in Microsoft 365. Meer informatie vindt u in de volgende secties.

|Categorie|Beschrijving|Verwijzing|
|:-------|:----------|:--------|
|Lidmaatschap|||
||Ontdekking van privéteams|[Het ontdekken van privéteams beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Dynamisch groepslidmaatschap op basis van regels|[Een dynamische groep maken of bijwerken in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Bepalen wie bestanden, mappen en sites kan delen.|[Toegangsaanvragen instellen en beheren](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Voorwaardelijke toegang|||
||Meervoudige verificatie|[Azure AD Meervoudige verificatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Apparaattoegang bepalen op basis van groeps-, team- of sitegevoeligheid.|[Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Toegang tot de site beperken voor niet-bemande apparaten.|[SharePoint-toegang beheren vanaf niet-beheerbare apparaten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Sitetoegang op basis van locatie bepalen|[Toegang tot SharePoint en OneDrive-gegevens regelen op basis van netwerklocatie](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Gasttoegang|||
||SharePoint-delen van opgegeven domeinen toestaan of blokkeren.|[Delen van SharePoint- en OneDrive-inhoud per domein beperken](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Team- of groepslidmaatschap van opgegeven domeinen toestaan of blokkeren.|[Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Voorkomen dat u anoniem kunt delen.|[Iedereen-koppelingen uitschakelen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Beheer de machtigingen voor koppelingen voor anonieme toegang.|[Koppelingsmachtigingen instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Beheer het verlopen van koppelingen voor anoniem delen.|[Een vervaldatum instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Beheer het type koppeling voor delen dat standaard aan gebruikers wordt weergegeven.|[Het standaardkoppelingstype voor een site wijzigen](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Beperk extern delen tot specifieke personen.|[Extern delen beperken tot opgegeven beveiligingsgroepen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Beheer gasttoegang tot een groep, team of site op basis van informatiegevoeligheid.|[Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Opties voor delen uitschakelen.|[Delen beperken in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Gebruikersbeheer|||
||Controleer regelmatig het team- en groepslidmaatschap.|[Wat zijn Azure AD Access-beoordelingen?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Beheer van toegang tot groepen en teams automatiseren.|[Wat is Azure AD-rechtbeheer?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Personen toestaan of blokkeren om privékanalen te maken in Teams.|[De levenscyclus van privékanalen beheren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Lidmaatschap

Het lidmaatschap van teams en groepen wordt bepaald door eigenaren. Leden kunnen anderen uitnodigen, maar de uitnodigingen worden ter goedkeuring naar eigenaren verzonden. Hoewel openbare teams en groepen door iedereen in de organisatie kunnen worden ontdekt, kunt u bepalen of privéteams en groepen kunnen worden ontdekt:

- [Het ontdekken van privéteams beheren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

U kunt het lidmaatschap van een groep of team dynamisch beheren op basis van bepaalde criteria, zoals afdeling. In dit geval kunnen leden en eigenaren geen personen uitnodigen voor het team. Dynamische groepen gebruiken metagegevens die u in Azure Active Directory definieert om te bepalen wie lid is van de groep. Zorg ervoor dat de metagegevens die u gebruikt, volledig en actueel zijn als onjuiste metagegevens, zodat gebruikers geen groepen meer hebben of onjuiste gebruikers worden toegevoegd.

- [Een dynamische groep maken of bijwerken in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint-sites bieden de mogelijkheid om eigenaren, leden en bezoekers toe te voegen, afgezien van groepslidmaatschap of teamlidmaatschap. Afhankelijk van uw vereisten, wilt u mogelijk beperken wie personen kan uitnodigen voor de site. Afhankelijk van de gevoeligheid van de informatie op een bepaalde site, kunt u ook beperken wie bestanden en mappen mag delen. Deze beperkingen worden geconfigureerd door de eigenaar van het team, de groep of de site:

- [Toegangsaanvragen instellen en beheren](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Voorwaardelijke toegang

Met Microsoft 365 kunt u meervoudige verificatie vereisen voor zowel personen binnen als buiten uw organisatie. Er zijn veel opties voor de omstandigheden waarin mensen worden gevraagd om een tweede verificatiefactor. U wordt ten zeerste aangeraden meervoudige verificatie voor uw organisatie te implementeren:

- [Azure AD Meervoudige verificatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Als u gevoelige informatie hebt in sommige groepen en teams, kunt u beleidsregels voor apparaatbeheer afdwingen op basis van het gevoeligheidslabel van een groep of team. U kunt de toegang volledig blokkeren vanaf niet-bemande apparaten of beperkte, alleen-webtoegang toestaan:

- [Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

In SharePoint kunt u de toegang tot sites beperken vanaf opgegeven netwerklocaties.

- [Toegang tot SharePoint en OneDrive-gegevens regelen op basis van netwerklocatie](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Aanvullende informatiebronnen:

- [Een implementatie van voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Overzicht van Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [SharePoint-toegang beheren vanaf niet-beheerbare apparaten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Gasttoegang

U kunt gasten beperken op basis van het domein van hun e-mailadres. SharePoint biedt instellingen voor organisatiespecifieke en sitespecifieke domeinbeperkingen. Groepen en Teams gebruiken het domein lijsten toestaan en weigeren in Azure AD. Zorg ervoor dat u beide instellingen configureert om ongewenste delen te voorkomen en een consistente gebruikerservaring te garanderen:

- [Delen van SharePoint- en OneDrive-inhoud per domein beperken](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 staat anoniem delen van bestanden en mappen toe met behulp *van Koppelingen voor iedereen* delen. *Iedereen* kan koppelingen doorsturen en iedereen met de koppeling heeft toegang tot het gedeelde item. Afhankelijk van de gevoeligheid van uw gegevens, kunt u bepalen hoe koppelingen voor iedereen worden gebruikt, zoals het volledig uitschakelen van koppelingen, het beperken van koppelingsmachtigingen tot alleen-lezen of het instellen van een verlooptijd voor deze koppelingen: 

- [Iedereen-koppelingen uitschakelen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Koppelingsmachtigingen instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Een vervaldatum instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Bij het delen van bestanden of mappen hebben gebruikers verschillende koppelingstypen om uit te kiezen. Als u het risico op onbedoeld ongepast delen wilt beperken, kunt u het standaardkoppelingstype wijzigen dat wordt weergegeven aan gebruikers wanneer ze delen. Als u bijvoorbeeld de  standaardkoppelingen van Koppelingen van Iedereen ( die anonieme toegang toestaan) naar Personen *in* uw organisatiekoppelingen wijzigen, kan het risico op ongewenst extern delen van gevoelige informatie worden verkleind:

- [Het standaardkoppelingstype voor een site wijzigen](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Als uw organisatie gevoelige gegevens heeft die u met gasten moet delen, maar u zich zorgen maakt over ongepast delen, kunt u het extern delen van bestanden en mappen beperken tot de leden van opgegeven beveiligingsgroepen. Op deze manier kunt u delen extern beperken tot een specifieke groep personen, of uw gebruikers verplichten om training te volgen voor passend extern delen voordat ze worden toegevoegd aan de beveiligingsgroep:

- [Extern delen beperken tot opgegeven beveiligingsgroepen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Groepen en Teams hebben instellingen op organisatieniveau die gasttoegang toestaan of weigeren. Hoewel u de toegang van gasten tot specifieke teams of groepen kunt beperken met [Microsoft PowerShell,](per-group-guest-access.md)raden we u aan dit te doen via een gevoeligheidslabel. Met gevoeligheidslabels kunt u gasttoegang automatisch toestaan of weigeren op basis van het toegepaste label:

- [Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

In een omgeving waarin u regelmatig gasten uitnodigt voor groepen en teams, kunt u overwegen regelmatig geplande gasttoegangsbeoordelingen in te stellen. Eigenaren kunnen worden gevraagd gasten in hun groepen en teams te controleren en de toegang goed te keuren of te weigeren.

- [Revisies voor gasttoegang instellen](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 biedt veel verschillende methoden voor het delen van informatie. Als u gevoelige informatie hebt en u wilt beperken hoe deze worden gedeeld, bekijkt u de opties voor het beperken van delen:

- [Delen beperken in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Aanvullende informatiebronnen:

- [Veilige samenwerking instellen met Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Een beveiligde omgeving voor het delen met gasten maken](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Externe B2B-samenwerking inschakelen en beheren wie gasten kan uitnodigen](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gebruikersbeheer

Naarmate groepen en teams zich ontwikkelen in uw organisatie, is het een goede gewoonte om het team- en groepslidmaatschap regelmatig te bekijken. Dit kan met name handig zijn voor teams en groepen met een veranderend lidmaatschap, personen met gevoelige informatie of personen met gasten. Overweeg om toegangsbeoordelingen in te stellen voor deze teams en groepen:

- [Wat zijn Azure AD Access-beoordelingen?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Veel organisaties hebben een zakelijke samenwerking met andere organisaties of belangrijke leveranciers met wie ze nauw samenwerken. Gebruikersbeheer en toegang tot resources kunnen in deze scenario's lastig zijn. U kunt een aantal gebruikersbeheertaken automatiseren en sommige zelfs overstappen naar uw partnerorganisatie:

- [Wat is Azure AD-rechtbeheer?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Met privékanalen in Teams kunnen gesprekken met een bereik en het delen van bestanden tussen een subset teamleden worden gedeeld. Afhankelijk van uw specifieke zakelijke behoeften, kunt u deze mogelijkheid toestaan of blokkeren.

- [Privékanalen in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [De levenscyclus van privékanalen beheren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Aanvullende informatiebronnen:

- [Azure Active Directory Identity Governance](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Beveiliging en compliance in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Instellingen voor delen beheren in SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Een extern netwerk maken en beheren in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Teams met drie beschermingsniveaus configureren](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
