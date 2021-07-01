---
title: Microsoft 365 samenwerking tussen tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Lees hoe Microsoft 365 samenwerking werkt tussen tenants en organisaties, zodat verschillende organisaties veilig kunnen samenwerken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0a9d15608e046e72ba579b77ba44092ed2ecb46
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229849"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 samenwerking tussen tenants

Stel dat twee organisaties, Fabrikam en Contoso, elk een Microsoft 365 voor zakelijke tenant hebben en ze willen samenwerken aan verschillende projecten; sommige worden uitgevoerd voor een beperkte periode en waarvan sommige nog lopen. Hoe kunnen Fabrikam en Contoso hun personen en teams in staat stellen effectiever samen te werken in hun verschillende Microsoft 365 tenants op een veilige manier? Microsoft 365, in combinatie met Azure Active Directory (Azure AD) B2B-samenwerking, biedt verschillende opties. In dit artikel worden verschillende belangrijke scenario's beschreven die Fabrikam en Contoso kunnen overwegen.

Microsoft 365 opties voor samenwerking tussen tenants zijn het gebruik van een centrale locatie voor bestanden en gesprekken, het delen van agenda's, het gebruik van chatberichten, audio-/videogesprekken voor communicatie en het beveiligen van toegang tot resources en toepassingen. Gebruik de volgende tabellen om oplossingen te selecteren en meer te weten te komen.

## <a name="exchange-online-collaboration-options"></a>Exchange Online samenwerkingsopties

| Doel voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Agenda's delen met een andere Microsoft 365 organisatie |Beheerders kunnen verschillende niveaus van agendatoegang instellen in Exchange Online zodat bedrijven kunnen samenwerken met andere bedrijven en gebruikers de planningen (gratis/drukke informatie) met anderen kunnen delen. | <ul><li>[Delen](/exchange/sharing/sharing) </li><li> [Organisatierelaties](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [Een organisatierelatie maken](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Een organisatierelatie wijzigen](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [Een organisatierelatie verwijderen](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [Agenda’s delen met externe gebruikers](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Bepalen hoe gebruikers hun agenda's delen met personen buiten uw organisatie | Beheerders passen beleid voor delen toe op postvakken van gebruikers om te bepalen met wie het kan worden gedeeld en het toegangsniveau dat wordt verleend |  <ul><li> [Beleid voor delen](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [Een beleid voor delen maken](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [Een beleid voor delen toepassen op postvakken](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [Een beleid voor delen wijzigen, uitschakelen of verwijderen](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|Beveiligde e-mailkanalen configureren en de e-mailstroom met partnerorganisaties bepalen | Beheerders maken verbindingslijnen om beveiliging toe te passen op e-mailuitwisselingen met een partnerorganisatie of serviceprovider. De connectors dwingen versleuteling af via TLS (Transport Layer Security) en het toestaan van beperkingen voor domeinnamen of IP-adresbereiken waar uw partners e-mail van verzenden. |  <ul><li> [Hoe Exchange Online TLS gebruikt om e-mailverbindingen te beveiligen](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [E-mailstroom configureren met behulp van verbindingslijnen](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [Externe domeinen](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [Verbindingslijn instellen voor een veilige e-mailstroom met een partnerorganisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [Best practices voor e-mailstroom (overzicht)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Online en OneDrive voor Bedrijven samenwerkingsopties

| Doelstellingen voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Sites en documenten delen met externe gebruikers | Beheerders configureren delen op tenant- of siteverzamelingsniveau voor geverifieerde, geverifieerde werk- of schoolaccounts van Microsoft-account of gastaccounts |  <ul><li> [Extern delen beheren voor uw SharePoint Online-omgeving](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Het delen van SharePoint en OneDrive per domein beperken](/sharepoint/restricted-domains-sharing) </li><li> [Gebruik SharePoint Online als een B2B-extranetoplossing (business-to-business)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Extern delen voor eindgebruikers bijhouden en beheren | OneDrive voor Bedrijven bestandseigenaren en SharePoint Online eindgebruikers configureren site en document delen en meldingen instellen voor het bijhouden van delen |  <ul><li> [Meldingen configureren voor extern delen voor OneDrive voor Bedrijven](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Bestanden SharePoint mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>Skype voor Bedrijven samenwerkingsopties

| Doel voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Skype voor Bedrijven Online : chatberichten, oproepen en aanwezigheid met andere Skype voor Bedrijven gebruikers | Beheerders kunnen hun Skype voor Bedrijven onlinegebruikers inschakelen voor chatberichten, audio-/videogesprekken voeren en aanwezigheid zien bij gebruikers in een andere Microsoft 365 tenant. | [Gebruikers contact laten opnemen met externe gebruikers van Skype voor Bedrijven](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|Skype voor Bedrijven Online : chatberichten, oproepen en aanwezigheid bij Skype (consumenten)gebruikers | Beheerders kunnen hun Skype voor Bedrijven onlinegebruikers inschakelen voor chatberichten, gesprekken voeren en aanwezigheid zien Skype (consumenten)gebruikers. | [Gebruikers Skype voor Bedrijven contactpersonen Skype toevoegen](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B-samenwerkingsopties

| Doel voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Azure AD B2B-samenwerking - Inhoud delen door externe gebruikers toe te voegen aan een groep in de adreslijst van een organisatie | Een globale beheerder voor een Microsoft 365-tenant kan personen in een andere Microsoft 365-tenant uitnodigen om deel te nemen aan hun adreslijst, deze externe gebruikers aan een groep toe te voegen en toegang te verlenen tot inhoud, zoals SharePoint sites en bibliotheken voor de groep. |  <ul><li> [Wat is azure AD B2B-samenwerkingsvoorbeeld?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: Met nieuwe updates kunt u eenvoudig samenwerken tussen bedrijven](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Extern delen en Azure Active Directory B2B-samenwerking](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory B2B-samenwerkings-API en aanpassing](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD and Identity Show: Azure AD B2B Collaboration (Business to Business)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 samenwerkingsopties

| Doel voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Microsoft 365 Groepen : E-mail, agenda, OneNote en gedeelde bestanden op een centrale plaats | Groepen worden ondersteund in Business Essentials, Business Premium, Education en de Enterprise E1-, E3- en E5-abonnementen. Personen in een Microsoft 365 kunnen een groep maken en personen in een andere tenant uitnodigen Microsoft 365 als gastgebruikers. Is ook van toepassing op Dynamics CRM. |  <ul><li> [Meer informatie over Microsoft 365-groepen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Gasttoegang in Microsoft 365 Groepen](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Groepen Microsoft 365 implementeren](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Yammer samenwerkingsopties

| Doel voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Yammer - Samenwerking via een sociaal medium voor ondernemingen | Tenzij de mogelijkheid om externe groepen te maken is uitgeschakeld door een Yammer-beheerder, kunnen gebruikers externe groepen maken om samen te werken in Yammer via gesprekken, de mogelijkheid om berichten leuk te vinden en te volgen, bestanden te delen en online te chatten. | [Externe groepen in Yammer maken en beheren](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Teams samenwerkingsopties

|Doel voor delen|Beheeractie|How-to-informatie|
|:-----|:-----|:-----|
|Samenwerken in Teams met gebruikers buiten de organisatie | Een globale beheerder voor de uitnodigende Microsoft 365 tenant moet externe samenwerking in Teams. Globale beheerders en teameigenaren kunnen nu iedereen met een e-mailadres uitnodigen om samen te werken in Teams.  <br/> Beheerders kunnen gasten die al aanwezig zijn in hun tenant beheren en bewerken. |  <ul><li> [Gasttoegang machtigen](/microsoftteams/teams-dependencies) </li><li> [Gasttoegang in- of uitschakelen in Teams](/microsoftteams/set-up-guests) </li><li> [PowerShell gebruiken om Gasttoegang te bepalen](/microsoftteams/guest-access-powershell) </li><li> [Controlelijst voor gasttoegang](/microsoftteams/guest-access-checklist) </li><li> [Gastgebruikers weergeven](/microsoftteams/view-guests) </li><li> [Gebruikersgegevens van gasten bewerken](/microsoftteams/edit-guests-information) </li></ul> |
|Teameigenaren kunnen uitnodigen en beheren hoe gasten samenwerken binnen hun teams.  |Teameigenaren hebben extra besturingselementen voor wat de gasten in hun teams kunnen doen. |  <ul><li> [Gasten toevoegen](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Een gast toevoegen aan een team](/microsoftteams/add-guests) </li><li> [Gasttoegang beheren in Teams](/microsoftteams/manage-guests) </li><li> [Zien wie er in een team of in een kanaal zit](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Gasten van andere tenants kunnen inhoud weergeven in Teams en samenwerken met andere leden | Geen. | [De gasttoegangservaring](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Power BI samenwerkingsopties

| Doel voor delen | Beheeractie | How-to-informatie |
|:-----|:-----|:-----|
|Power BI externe gastgebruikers kunnen inhoud gebruiken die aan hen wordt gedeeld via koppelingen. Hierdoor kunnen gebruikers in de organisatie inhoud op een veilige manier distribueren in verschillende organisaties.<br/> | De Power BI beheerder kan bepalen of gebruikers externe gebruikers kunnen uitnodigen om inhoud binnen de organisatie te bekijken.| [Inhoud Power BI externe gastgebruikers distribueren met Azure AD B2B](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Punten om op de hoogte te zijn van Microsoft 365 samenwerking tussen tenants

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Delen van gebruikersaccounts, licenties, abonnementen en opslag

Elke organisatie onderhoudt eigen gebruikersaccounts, identiteiten, beveiligingsgroepen, abonnementen, licenties en opslag. Personen gebruiken de samenwerkingsfuncties in Microsoft 365 samen met beleidsregels voor delen en beveiligingsinstellingen om toegang te bieden tot de benodigde informatie, met behoud van controle over bedrijfsmiddelen.

- **Gebruikersaccounts:** Accounts kunnen niet worden gedeeld of gedupliceerd tussen de tenants of partities in de on-premises Active Directory Domain Services.

- **&amp; Licentiesabonnementen:** In Microsoft 365 geven licenties van licentieplannen (ook wel SKU's of Microsoft 365-abonnementen genoemd) gebruikers toegang tot de Microsoft 365-services die voor deze abonnementen zijn gedefinieerd.

- **Storage:** In Microsoft 365 licentieplannen worden softwaregrenzen en -limieten voor SharePoint Online afzonderlijk beheerd van limieten voor postvakopslag. Limieten voor postvakopslag worden ingesteld en beheerd met Exchange Online. In beide scenario's kan opslag niet worden gedeeld tussen tenants.

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Kunnen we domeinnaamruimten delen in Microsoft 365 tenants?

Nee. Organisatiedomeinnamen, zoals fabrikam.com of tailspintoys.com, kunnen alleen worden gekoppeld en gebruikt met één Microsoft 365 tenant. Elke tenant moet een eigen naamruimte hebben. UPN-, SMTP- en SIP-naamruimten kunnen niet worden gedeeld tussen tenants.

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Hoe zit het met hybride onderdelen en Microsoft 365 samenwerking tussen tenants?

On-premises hybride onderdelen, zoals een Exchange en Azure AD-Verbinding maken, kunnen niet over meerdere tenants worden gesplitst.
