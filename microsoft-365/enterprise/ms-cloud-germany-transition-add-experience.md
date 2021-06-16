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
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930413"
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

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Vertrouwen van afhankelijke partijen verwijderen uit Microsoft Cloud Deutschland AD FS. | Nadat de cut-over naar Azure AD is voltooid, gebruikt de organisatie volledig Office 365 services en is ze niet meer verbonden met Microsoft Cloud Deutschland. Op dit moment moet de klant het vertrouwen van de vertrouwensrelatie met de Microsoft Cloud Deutschland-eindpunten verwijderen. Dit kan alleen als geen van de toepassingen van de klant naar Microsoft Cloud Deutschland-eindpunten wijst wanneer Azure AD wordt gebruikt als idp (Identity Provider). | Federatief verificatie-organisaties | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Groepsgoedkeuringen
**Van toepassing op:** Eindgebruikers van wie de goedkeuringsaanvragen voor Azure AD-groep niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie 

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Aanvragen om deel te nemen aan een Azure AD-groep in de afgelopen 30 dagen vóór de migratie, moeten opnieuw worden aangevraagd als de oorspronkelijke aanvraag niet is goedgekeurd. | Eindgebruikers moeten het Access-deelvenster gebruiken om opnieuw een aanvraag in te dienen om deel te nemen aan een Azure AD-groep als deze aanvragen niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie. |  Als eindgebruiker: <ol><li>Ga naar [het Access-deelvenster](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Zoek een Azure AD-groep waarvoor lidmaatschapsgoedkeuring in behandeling was gedurende de 30 dagen vóór de migratie.</li><li>Vraag om opnieuw deel te nemen aan de Azure AD-groep.</li></ol> Aanvragen om deel te nemen aan een groep die minder dan 30 dagen vóór de migratie actief zijn, kunnen niet worden goedgekeurd, tenzij ze na de migratie opnieuw worden aangevraagd. |
||||

## <a name="custom-dns-updates"></a>Aangepaste DNS-updates
**Van toepassing op:**  Alle klanten die hun eigen DNS-zones beheren

| Stap(en) | Omschrijving | Gevolg |
|:------|:-------|:-------|
| On-premises DNS-services bijwerken voor Office 365 services-eindpunten. | Door klanten beheerde DNS-vermeldingen die naar Microsoft Cloud Deutschland wijzen, moeten worden bijgewerkt om te wijzen naar de Office 365 global services-eindpunten. Raadpleeg Domeinen [in het Microsoft 365 beheercentrum](https://admin.microsoft.com/Adminportal/Home#/Domains) en pas de wijzigingen in uw DNS-configuratie toe. | Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. |
||||

## <a name="third-party-services"></a>Services van derden
**Van toepassing op:** Klanten die services van derden gebruiken voor Office 365 services-eindpunten

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Werk partners en services van derden bij voor Office 365 services-eindpunten. | <ul><li>Services en partners van derden die naar Duitsland Office 365, moeten worden bijgewerkt om te wijzen Office 365 services-eindpunten. Voorbeeld: Registreer opnieuw, in overeenstemming met uw leveranciers en partners, de galerie-app-versie van toepassingen, indien beschikbaar. </li><li>Wijs alle aangepaste toepassingen aan die gebruikmaken Graph API van `graph.microsoft.de` naar `graph.microsoft.com` . Andere API's met gewijzigde eindpunten moeten ook worden bijgewerkt, als ze worden gebruikt. </li><li>Wijzig alle niet-first-party enterprise-toepassingen om om te leiden naar de wereldwijde eindpunten. </li></ul>| Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. |
||||