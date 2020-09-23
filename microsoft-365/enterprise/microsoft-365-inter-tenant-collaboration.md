---
title: Samenwerking tussen Microsoft 365 tussen tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/21/2020
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
description: Meer informatie over de manier waarop Microsoft 365 samenwerken via tenants en organisaties werkt, zodat verschillende organisaties veilig kunnen samenwerken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8064543f771927f539d09e3136663bb0df56d5be
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214797"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Samenwerking tussen Microsoft 365 tussen tenants

Stel dat twee organisaties, Fabrikam en contoso, elk een Microsoft 365 for Business-Tenant hebben en ze samen aan meerdere projecten willen samenwerken. een deel van wat gedurende een beperkte periode en bepaalde worden uitgevoerd. Hoe kunnen Fabrikam en contoso hun personen en teams effectiever samenwerken in de verschillende Microsoft 365-tenants op een veilige manier? Microsoft 365, in combinatie met Azure Active Directory (Azure AD) B2B-samenwerking, biedt diverse opties. In dit artikel wordt beschreven hoe u met Fabrikam en contoso rekening kunt houden.
  
Samenwerkingsopties voor Microsoft 365 tussen tenants voor het gebruik van een centrale locatie voor bestanden en gesprekken, agenda's delen, met behulp van CHATBERICHTEN, audio-en videogesprekken voor communicatie en het beveiligen van toegang tot bronnen en toepassingen. Gebruik de volgende tabellen om oplossingen te selecteren en meer te weten te komen.
  
## <a name="exchange-online-collaboration-options"></a>Samenwerkingsopties voor Exchange Online

| Doel voordelen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Agenda's delen met een andere Microsoft 365-organisatie |Beheerders kunnen verschillende niveaus instellen voor het openen van een agenda in Exchange Online, zodat bedrijven samen met andere bedrijven kunnen samenwerken en de planningen (beschikbaarheidsinfo) met anderen kunnen delen. | <ul><li>[Delen](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) </li><li> [Organisatie relaties](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) </li><li> [Een organisatie relatie maken](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) </li><li> [Een organisatie relatie wijzigen ](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) </li><li> [Een organisatie relatie verwijderen](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) </li><li> [Agenda’s delen met externe gebruikers](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Bepalen hoe gebruikers hun agenda's delen met personen buiten uw organisatie | Beheerders passen beleidsregels voordelen toe op de postvakken van gebruikers om te bepalen met wie de postvakken kunnen worden gedeeld en welk toegangsniveau is toegestaan |  <ul><li> [Beleidsregels voordelen](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) </li><li> [Een beleid voordelen maken](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) </li><li> [Een beleid voordelen toepassen op postvakken](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) </li><li> [Een beleid voordelen wijzigen, uitschakelen of verwijderen](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) </li></ul> |
|Veilige e-mail kanalen configureren en e-mail stromen met partnerorganisaties beheren | Beheerders maken connectors om beveiliging toe te passen op e-mail uitwisseling met een partnerorganisatie of service provider. De verbindingslijnen dwingen versleuteling te beleggen via TLS (Transport Layer Security) en de beperkingen voor domeinnamen of IP-adresbereiken waarmee uw partners e-mail verzenden. |  <ul><li> [Hoe Exchange Online TLS gebruikt om verbinding te maken met e-mail verbindingen](https://technet.microsoft.com/library/mt163898.aspx) </li><li> [De e-mail stroom configureren met connectors](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) </li><li> [Externe domeinen](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) </li><li> [Connector instellen voor veilige e-mail stroom met een partnerorganisatie](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) </li><li> [Best practices voor e-mail stroom (overzicht)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Samenwerkingsopties voor SharePoint Online en OneDrive voor bedrijven

| Doelstellingen delen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Sites en documenten delen met externe gebruikers | Beheerders configureren delen op Tenant of niveau van siteverzameling voor geverifieerde Microsoft-account, werk-of schoolaccount geverifieerde of gastaccounts |  <ul><li> [Extern delen beheren voor uw SharePoint Online-omgeving](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Delen van SharePoint-en OneDrive-inhoud beperken per domein](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) </li><li> [SharePoint Online gebruiken als Business-to-Business (B2B) extranet-oplossing](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Extern delen voor eindgebruikers bijhouden en beheren | Bestands eigenaren van OneDrive voor bedrijven en eindgebruikers van SharePoint Online configureren het delen van sites en documenten en het maken van meldingen om delen bij te houden |  <ul><li> [Meldingen configureren voor extern delen voor OneDrive voor bedrijven](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [SharePoint-bestanden of-mappen delen](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Samenwerkingsopties voor Skype voor bedrijven

| Doel voordelen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Skype voor bedrijven online-CHATBERICHTEN, gesprekken en aanwezigheidsgegevens met andere gebruikers van Skype voor bedrijven | Beheerders kunnen instellen dat gebruikers van Skype voor bedrijven online kunnen chatten, audio-en videogesprekken kunnen voeren en aanwezigheid kunnen zien met gebruikers in een andere Microsoft 365-Tenant. | [Gebruikers contact laten opnemen met externe gebruikers van Skype voor Bedrijven](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype voor bedrijven online-CHATBERICHTEN, gesprekken en aanwezigheidsgegevens met Skype-gebruikers (consumenten) | Beheerders kunnen instellen dat gebruikers van Skype voor bedrijven online kunnen chatten en gesprekken kunnen voeren, en de aanwezigheidsgegevens kunnen zien met Skype-gebruikers (consumenten). | [Skype voor bedrijven-gebruikers Skype-contactpersonen laten toevoegen](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Samenwerkingsopties voor Azure AD B2B

| Doel voordelen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Azure AD B2B-samenwerking-inhoud delen door externe gebruikers toe te voegen aan een groep in de adreslijst van de organisatie | Een globale beheerder van een Microsoft 365-Tenant kan personen uit een andere Microsoft 365-Tenant uitnodigen om lid te worden van zijn of haar adreslijst, gebruikers toevoegen aan een groep en toegang verlenen tot inhoud, zoals SharePoint-sites en-Bibliotheken, voor de groep. |  <ul><li> [Voorbeeld van Azure AD B2B-samenwerking?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: nieuwe updates maken cross-Business samenwerkings eenvoudig](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Extern delen en Azure Active Directory B2B-samenwerking](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory B2B Collaboration API and customizationing](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) </li><li> [Azure ad and Identity show: Azure AD B2B-samenwerking (Business to Business)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Samenwerkingsopties voor Microsoft 365

| Doel voordelen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Microsoft 365-groepen-E-mail, agenda, OneNote en gedeelde bestanden op een centrale locatie | Groepen worden ondersteund in Business Essentials, Business Premium, Education en de Enterprise E1-, E3-en E5-abonnementen. Personen in een Microsoft 365-Tenant kunnen een groep maken en personen uit een andere Microsoft 365-Tenant uitnodigen als gastgebruikers. Dit geldt ook voor Dynamics CRM. |  <ul><li> [Meer informatie over Microsoft 365-groepen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Gasttoegang in Microsoft 365-groepen](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Microsoft 365-groepen implementeren](https://technet.microsoft.com/library/dn896591.aspx) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Samenwerkingsopties voor Yammer

| Doel voordelen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Yammer-samenwerking via het sociale medium van een onderneming | Tenzij de mogelijkheid om externe groepen te maken door een Yammer-beheerder is uitgeschakeld, kunnen gebruikers externe groepen maken om samen te werken via Yammer via gesprekken, de mogelijkheid om berichten te leuk vinden en te volgen, bestanden te delen en online te chatten. | [Externe groepen in Yammer maken en beheren](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Samenwerkingsopties voor teams

|Doel voordelen|Administratieve actie|Procedure gegevens|
|:-----|:-----|:-----|
|Samenwerken in teams met gebruikers buiten de organisatie | Een globale beheerder voor de uitnodiging van een Microsoft 365-Tenant moet externe samenwerking inschakelen in teams. Globale beheerders en team eigenaren kunnen nu iedereen met een e-mailadres uitnodigen om samen te werken in teams.  <br/> Beheerders kunnen ook gasten beheren en bewerken die al aanwezig zijn in hun Tenant. |  <ul><li> [Gasttoegang machtigen](https://docs.microsoft.com/microsoftteams/teams-dependencies) </li><li> [Gasttoegang in-of uitschakelen in teams](https://docs.microsoft.com/microsoftteams/set-up-guests) </li><li> [PowerShell gebruiken om gasttoegang te beheren](https://docs.microsoft.com/microsoftteams/guest-access-powershell) </li><li> [Controlelijst voor gasttoegang](https://docs.microsoft.com/microsoftteams/guest-access-checklist) </li><li> [Gastgebruikers weergeven](https://docs.microsoft.com/microsoftteams/view-guests) </li><li> [Gastgebruikers gegevens bewerken](https://docs.microsoft.com/microsoftteams/edit-guests-information) </li></ul> |
|Team eigenaren kunnen met hun team samenwerken aan en beheren hoe gasten binnen hun teams werken.  </li><li> |Team eigenaren hebben extra besturingselementen voor wat bezoekers binnen hun team kunnen doen. |  <ul><li> [Gasten toevoegen](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Een gast aan een team toevoegen](https://docs.microsoft.com/microsoftteams/add-guests) </li><li> [Gasttoegang beheren in teams](https://docs.microsoft.com/microsoftteams/manage-guests) </li><li> [Zien wie lid is van een team of een kanaal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Gasten van andere tenants kunnen inhoud in teams weergeven en samenwerken met andere leden | Zonder. | [De gast Access-ervaring](https://docs.microsoft.com/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Samenwerkingsopties voor Power BI

| Doel voordelen | Administratieve actie | Procedure gegevens |
|:-----|:-----|:-----|
|Met Power BI kunnen externe gastgebruikers inhoud die met hen wordt gedeeld, via koppelingen, gebruiken. Hiermee kunnen gebruikers in de organisatie de inhoud op een veilige manier verdelen binnen een organisatie.<br/> | Met de Power BI-beheerder kunt u bepalen of gebruikers externe gebruikers kunnen uitnodigen om inhoud in de organisatie te bekijken.| [Power BI-inhoud distribueren naar externe gastgebruikers met Azure AD B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Wat u moet weten over samenwerking tussen Microsoft 365 tussen tenants

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Het delen van gebruikersaccounts, licenties, abonnementen en opslag

Elke organisatie onderhoudt zijn eigen gebruikersaccounts, identiteiten, beveiligingsgroepen, abonnementen, licenties en opslag. Gebruikers gebruiken de samenwerkingsfuncties in Microsoft 365 samen met beleidsregels voordelen en beveiligingsinstellingen om toegang te bieden tot benodigde informatie, en om het beheer van bedrijfsactiva te behouden.
  
- **Gebruikersaccounts:** Accounts kunnen niet worden gedeeld en accounts kunnen niet worden gedupliceerd tussen de tenants of partities in de on-premises Active Directory Directory Services. 
    
- **Licentie &amp; abonnementen:** In Microsoft 365, licenties van licentie plannen (ook wel Sku's of Microsoft 365-abonnementen genoemd) verlenen gebruikers toegang tot de Microsoft 365-services die zijn gedefinieerd voor die plannen. 
    
- **Opslag:** In Microsoft 365-abonnementen worden software grenzen en-limieten voor SharePoint Online afzonderlijk beheerd via opslaglimieten voor uw postvak. Opslaglimieten voor e-mail worden ingesteld en beheerd met behulp van Exchange Online. In situaties waarin de opslag van beide scenario's geen gedeelde cross tenants zijn. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Kunnen we domeinnaamruimten delen in Microsoft 365-tenants?

Nee. Werden omgezet-domeinen, zoals fabrikam.com of tailspintoys.com, kunnen alleen worden gekoppeld en gebruikt met één Tenant op het moment. Elke Tenant moet een eigen naamruimte hebben. UPN-, SMTP-en SIP-naamruimten kunnen niet via een Tenant worden gedeeld.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Hoe zit het met hybride onderdelen en samenwerking tussen Microsoft 365 tussen tenants?

On-premises hybride onderdelen, zoals een Exchange-organisatie en Azure AD Connect, kunnen niet worden gesplitst in meerdere tenants.
  

