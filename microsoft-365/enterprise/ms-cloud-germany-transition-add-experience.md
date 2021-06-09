---
title: Activiteiten na de migratie voor de migratie vanuit Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: Activiteiten na de migratie na de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899362"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Activiteiten na de migratie voor de migratie vanuit Microsoft Cloud Deutschland

De volgende secties bieden activiteiten na de migratie voor meerdere services na de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD federatief verificatie met AD FS
**Van toepassing op:** Alle klanten die federatief verificatie gebruiken met AD FS

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Vertrouwen van afhankelijke partijen verwijderen uit Microsoft Cloud Deutschland AD FS. | Nadat de cut-over naar Azure AD is voltooid, gebruikt de organisatie volledig Office 365 services en is ze niet meer verbonden met Microsoft Cloud Deutschland. Op dit moment moet de klant het vertrouwen van de vertrouwensrelatie met de Microsoft Cloud Deutschland-eindpunten verwijderen. Dit kan alleen als geen van de toepassingen van de klant naar Microsoft Cloud Deutschland-eindpunten wijst wanneer Azure AD wordt gebruikt als idp (Identity Provider). | Federatief verificatie-organisaties | Geen. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Groepsgoedkeuringen
**Van toepassing op:** Eindgebruikers van wie de goedkeuringsaanvragen voor Azure AD-groep niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie 

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Aanvragen om deel te nemen aan een Azure AD-groep in de afgelopen 30 dagen vóór de migratie, moeten opnieuw worden aangevraagd als de oorspronkelijke aanvraag niet is goedgekeurd. | Eindgebruikers moeten het Access-deelvenster gebruiken om opnieuw een aanvraag in te dienen om deel te nemen aan een Azure AD-groep als deze aanvragen niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie. |  Als eindgebruiker: <ol><li>Ga naar [het Access-deelvenster](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Zoek een Azure AD-groep waarvoor lidmaatschapsgoedkeuring in behandeling was gedurende de 30 dagen vóór de migratie.</li><li>Vraag om opnieuw deel te nemen aan de Azure AD-groep.</li></ol> Aanvragen om deel te nemen aan een groep die minder dan 30 dagen vóór de migratie actief zijn, kunnen niet worden goedgekeurd, tenzij ze na de migratie opnieuw worden aangevraagd. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Aangepaste DNS-updates
**Van toepassing op:**  Alle klanten die hun eigen DNS-zones beheren

| Stap(en) | Beschrijving | Gevolg |
|:------|:-------|:-------|
| On-premises DNS-services bijwerken voor Office 365 services-eindpunten. | Door klanten beheerde DNS-vermeldingen die naar Microsoft Cloud Deutschland wijzen, moeten worden bijgewerkt om te wijzen naar de Office 365 global services-eindpunten. | Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. |
||||

## <a name="third-party-services"></a>Services van derden
**Van toepassing op:** Klanten die services van derden gebruiken voor Office 365 services-eindpunten

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Werk partners en services van derden bij voor Office 365 services-eindpunten. | <ul><li>Services en partners van derden die naar Duitsland Office 365, moeten worden bijgewerkt om te wijzen Office 365 services-eindpunten. Voorbeeld: Registreer opnieuw, in overeenstemming met uw leveranciers en partners, de galerie-app-versie van toepassingen, indien beschikbaar. </li><li>Wijs alle aangepaste toepassingen aan die gebruikmaken Graph API van `graph.microsoft.de` naar `graph.microsoft.com` . Andere API's met gewijzigde eindpunten moeten ook worden bijgewerkt, als ze worden gebruikt. </li><li>Wijzig alle niet-first-party enterprise-toepassingen om om te leiden naar de wereldwijde eindpunten. </li></ul>| Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Van toepassing op**: Klanten die SharePoint 2013-werkstromen

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Opnieuw publiceren SharePoint 2013-werkstromen. | In het werk van vóór de migratie hebben we het aantal werkstromen SharePoint 2013 verminderd. Nu de migratie is voltooid, kan de klant de werkstromen opnieuw publiceren. | Dit is een vereiste actie. Als u dit niet doet, kan dit leiden tot verwarring bij gebruikers en helpdeskgesprekken. |
| Items delen via Outlook | Items delen in SharePoint Online en OneDrive voor Bedrijven via Outlook werkt niet meer na tenant cutover. |<ul><li>In SharePoint Online en OneDrive voor Bedrijven kunt u items delen via Outlook. Nadat u op Outlook knop hebt gedrukt, wordt er een deelbare koppeling gemaakt en in een nieuw bericht in de Outlook Web App.</li><li>Na tenant cutover werkt deze methode voor delen niet meer. We herkennen dat dit een bekend probleem is. Aangezien deze functie Outlook het pad van afzetting is, is het oplossen van het probleem echter niet gepland totdat de intrekking is uitgerold. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Van toepassing op**: Klanten die een hybride Exchange gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| De wizard Hybride configuratie (HCW) opnieuw uitvoeren op Office 365 services. | De bestaande HCW-configuratie is bedoeld ter ondersteuning van Microsoft Cloud Deutschland. Met de migratie Exchange services voltooid, ontkoppelen we on-premises configuratie van Microsoft Cloud Deutschland. |<ul><li>Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. Voordat Exchange postvakmigratie begint (met 5 of meer dagen kennisgeving), informeert u klanten dat ze moeten stoppen en alle onboarding- of offboarding-bewegingen van hun postvakken moeten verwijderen.  Als ze dat niet doen, zien ze fouten in hun verhuisverzoeken. </li><li>Nadat Exchange de postvakmigratie is voltooid, meldt u clients dat ze de onboarding en offboarding-bewegingen kunnen hervatten. <br> **Test-MigrationServer UitvoerenAvailabiilty**, een PowerShell-cmdlet, tijdens de migratie van Exchange van Microsoft Cloud Deutschland naar Office 365-services werkt mogelijk niet. De migratie werkt echter correct nadat de migratie is voltooid. </li><li>Als clients problemen hebben met referenties of autorisatie nadat postvakken zijn gemigreerd, kunnen gebruikers hun on-premises beheerdersreferenties in het migratie-eindpunt opnieuw instellen door dit uit te voeren of door hetzelfde in te stellen met behulp van `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange Control Panel (ECP). </li></ul>|
