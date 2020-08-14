---
title: Toegang in Microsoft 365 groepen, teams en SharePoint beheren
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Meer informatie over het beheren van toegang in Microsoft 365 groepen, teams en SharePoint.
ms.openlocfilehash: 8b58016ffa421328e3c1442d4ed2364f2eedc37b
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662579"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Toegang in Microsoft 365 groepen, teams en SharePoint beheren

Er zijn veel besturingselementen waarmee u kunt bepalen hoe mensen toegang krijgen tot bronnen in groepen, teams en SharePoint. Bekijk deze opties en kijk hoe ze zijn toegewezen aan uw bedrijfsbehoeften, de gevoeligheid van uw gegevens en het bereik van personen waarmee uw gebruikers kunnen samenwerken.

De volgende tabel bevat een beknopt overzicht van de beschikbare besturingselementen voor Access in Microsoft 365. Meer informatie vindt u in de volgende secties.

|Categorie|Beschrijving|Kruisverwijzingsnr|
|:-------|:----------|:--------|
|Waartoe|||
||Detectie van persoonlijke teams|[Het detecteren van persoonlijke teams in Microsoft teams beheren](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Dynamisch groepslidmaatschap op basis van regels|[Een dynamische groep maken of bijwerken in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Bepalen wie bestanden, mappen en sites kan delen.|[Toegangsaanvragen instellen en beheren](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Voorwaardelijke toegang|||
||Meervoudige verificatie|[Azure multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||De toegang tot uw apparaat beheren op basis van de gevoeligheid van een groep, team of site.|[De beschikbaarheid van labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Toegang tot de site beperken voor niet-beheerde apparaten.|[Toegang tot SharePoint beheren vanaf niet-beheerde apparaten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Toegang tot een site beheren op basis van locatie|[Toegang tot SharePoint-en OneDrive-gegevens regelen op basis van netwerklocatie](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Gasttoegang|||
||Delen van SharePoint in opgegeven domeinen toestaan of blokkeren.|[Delen van SharePoint-en OneDrive-inhoud beperken per domein](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Groepslidmaatschappen van bepaalde domeinen toestaan of blokkeren.|[Uitnodigingen voor B2B-gebruikers in bepaalde organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Anoniem delen voorkomen.|[Iedereen-koppelingen uitschakelen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||De machtigingen voor koppelingen voor anonieme toegang beheren.|[Koppelings machtigingen instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Beheer de vervaldatum van koppelingen voor anonieme delen.|[Een vervaldatum instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Bepalen welk type koppeling voordelen standaard wordt weergegeven aan gebruikers.|[Het standaardkoppelingstype voor een site wijzigen](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Extern delen beperken tot specifieke personen.|[Extern delen beperken tot opgegeven beveiligingsgroepen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Gasttoegang tot een groep, team of site beheren op basis van de vertrouwelijkheid van gegevens.|[De beschikbaarheid van labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Schakelopties voordelen uit.|[Delen beperken in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Gebruikersbeheer|||
||Herzie team en groepslidmaatschap regelmatig.|[Wat zijn Azure AD Access-beoordelingen?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Toegangsbeheer automatiseren met groepen en teams.|[Wat is Azure AD-rechtenbeheer?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Mensen toestaan of blokkeren om persoonlijke kanalen in teams te maken.|[De levenscyclus van persoonlijke kanalen in Microsoft teams beheren](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Waartoe

Het lidmaatschap van teams en groepen wordt bepaald door eigenaren. Leden kunnen anderen uitnodigen, maar de uitnodigingen worden naar eigenaren verzonden voorgoed keuring. Hoewel openbare teams en groepen kunnen worden gevonden door iedereen binnen de organisatie, kunt u bepalen of persoonlijke teams en groepen kunnen worden gevonden:

- [Het detecteren van persoonlijke teams in Microsoft teams beheren](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

U kunt het lidmaatschap van een groep of team dynamisch beheren op basis van bepaalde criteria, zoals afdeling. In dit geval kunnen leden en eigenaren geen personen uitnodigen voor het team.

- [Een dynamische groep maken of bijwerken in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint-sites bieden de mogelijkheid om eigenaren, leden en bezoekers van een groep of team lidmaatschap toe te voegen. Afhankelijk van wat u nodig hebt, is het handig om te beperken wie personen kan uitnodigen voor de site. Afhankelijk van de vertrouwelijkheid van de gegevens op een bepaalde site, kunt u het delen van bestanden en mappen beperken. Deze beperkingen worden geconfigureerd door de eigenaar van het team, de groep of site:

- [Toegangsaanvragen instellen en beheren](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Voorwaardelijke toegang

Met Microsoft 365 kunt u meervoudige verificatie vereisen voor personen binnen en buiten uw organisatie. Er zijn veel opties voor de omstandigheden waarin u wordt gevraagd om een tweede verificatie factor. U wordt ten zeerste aangeraden verificatie met meerdere factoren te implementeren voor uw organisatie:

- [Azure multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Als u vertrouwelijke informatie hebt in sommige van uw groepen en teams, kunt u beleidsregels voor Apparaatbeheer afdwingen op basis van het gevoeligheids label van een groep of een team. U kunt Access helemaal blokkeren vanaf niet-beheerde apparaten of alleen beperkte toegang tot Internet toestaan:

- [De beschikbaarheid van labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

In SharePoint kunt u de toegang tot sites beperken vanaf opgegeven netwerklocaties.

- [Toegang tot SharePoint-en OneDrive-gegevens regelen op basis van netwerklocatie](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Aanvullende informatiebronnen:

- [Een implementatie voor voorwaardelijke toegang plannen](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Overzicht van Microsoft intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Toegang tot SharePoint beheren vanaf niet-beheerde apparaten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Gasttoegang

U kunt gasten beperken op basis van het domein met hun e-mailadres. SharePoint biedt instellingen voor organisatie beperkingen voor de gehele organisatie en de site-specifieke domeinen. Groepen en teams gebruiken het domein lijsten toestaan en weigeren in azure AD. Zorg ervoor dat u beide instellingen configureert om ongewenste delen te voorkomen en ervoor te zorgen dat u een consistente gebruikerservaring hebt:

- [Delen van SharePoint-en OneDrive-inhoud beperken per domein](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Uitnodigingen voor B2B-gebruikers in bepaalde organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

In Microsoft 365 kunt u bestanden en mappen anoniem delen met behulp van *iedereen* die koppelingen deelt. *Iedereen* kan worden doorgestuurd en iedereen met de koppeling kan het gedeelde item openen. Afhankelijk van de gevoeligheid van uw gegevens, kunt u overwegen om te bepalen hoe de verbindingen van *iedereen* worden gebruikt, inclusief het uitschakelen van koppelingen naar de instelling alleen-lezen, of het instellen van een verlooptijd voor ze:

- [Iedereen-koppelingen uitschakelen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Koppelings machtigingen instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Een vervaldatum instellen voor koppelingen voor iedereen](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Bij het delen van bestanden of mappen kunnen gebruikers verschillende koppelingstypen selecteren uit. Als u het risico van onopzettelijk delen wilt beperken, kunt u het standaardkoppelingstype voor gebruikers wijzigen tijdens het delen. Als u bijvoorbeeld de standaardinstelling van een van de koppelingen voor *iedereen* wijzigt, wat het risico biedt voor anonieme toegang tot *personen in uw organisatie* , kunt u het risico verminderen van ongewenste extern delen van gevoelige informatie:

- [Het standaardkoppelingstype voor een site wijzigen](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Als uw organisatie gevoelige gegevens heeft die u met gasten moet delen, maar u het niet wilt delen met ongepast delen, kunt u het extern delen van bestanden en mappen beperken tot de leden van opgegeven beveiligingsgroepen. Op deze manier kunt u het delen van extern beperken voor een bepaalde groep personen of de gebruikers laten oefenen met de juiste extern delen voordat u ze toevoegt aan de beveiligingsgroep:

- [Extern delen beperken tot opgegeven beveiligingsgroepen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Groepen en teams hebben de instelling op organisatieniveau waarmee gasttoegang kan worden toegestaan of geweigerd. U kunt de [toegang van gasten tot bepaalde teams of groepen beperken met behulp van Microsoft PowerShell](per-group-guest-access.md)via een gevoeligheids label. Met behulp van een gevoeligheids label kunt u gasttoegang op basis van het toegepaste label automatisch toestaan of weigeren:

- [De beschikbaarheid van labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 biedt veel verschillende methoden voor het delen van informatie. Als u vertrouwelijke informatie hebt en de manier waarop deze wordt gedeeld wilt beperken, controleert u de opties voor het beperken van delen:

- [Delen beperken in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Aanvullende informatiebronnen:

- [Veilige samenwerking instellen met Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Aanbevolen procedures voor het delen van bestanden en mappen met niet-geverifieerde gebruikers](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Een beveiligde omgeving voor het delen met gasten maken](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [B2B externe samenwerking inschakelen en beheren wie gasten kan uitnodigen](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gebruikersbeheer

Aangezien groepen en teams ontwikkelen in uw organisatie, is het raadzaam om regelmatig een team en groepslidmaatschap te herzien. Dit kan vooral handig zijn voor teams en groepen met een wijzigings lidmaatschap, de personen die gevoelige informatie bevatten, of degenen die gasten bevatten. Overweeg om toegangs Beoordelingen voor deze teams en groepen in te stellen:

- [Wat zijn Azure AD Access-beoordelingen?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Veel organisaties hebben zakelijke relaties met andere organisaties of belangrijke leveranciers van wie ze een uitgebreide samenwerking hebben. Het beheren van gebruikers en toegang tot bronnen kan lastig zijn om in deze scenario's te beheren. Overweeg om enkele gebruikersbeheertaken te automatiseren en zelfs enkele van de taken van uw organisatie te laten overstappen:

- [Wat is Azure AD-rechtenbeheer?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Met persoonlijke kanalen in teams kunt u gesprekken met een bereik en bestanden delen tussen een subset van teamleden. Afhankelijk van uw specifieke behoeften van uw bedrijf, is het raadzaam deze mogelijkheid toe te staan of te blokkeren.

- [Persoonlijke kanalen in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [De levenscyclus van persoonlijke kanalen in Microsoft teams beheren](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Aanvullende informatiebronnen:

- [Azure Active Directory Identity governance](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Verwante onderwerpen

[Beveiliging en compliance in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Instellingen voordelen beheren in SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Een extern netwerk in Yammer maken en beheren](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Teams met drie beschermingsniveaus configureren](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
