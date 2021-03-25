---
title: Acties en effecten van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (geavanceerd)
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
description: 'Overzicht: Aanvullende klantervaringsgegevens bij het overmaken van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: ecc549ca4d0bb8122de3bf092c004c919e958d5e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165643"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Acties en effecten van migratiefasen voor de migratie vanuit Microsoft Cloud Deutschland (geavanceerd)

Tenantmigraties van Microsoft Cloud Deutschland naar de Regio Duitsland van De Office 365-services van Microsoft worden uitgevoerd als een set fasen en hun geconfigureerde acties voor elke werkbelasting. In deze afbeelding ziet u de negen fasen van de migratie naar de nieuwe Duitse datacenters.

![De negen fasen van de migratie naar de nieuwe Datacenters van Duitsland](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

De volgende secties bevatten aanvullende informatie over klantervaringen bij het over stappen van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>Office 365 Portal Services tussen fase 2 en fase 3

Tussen fase 2 en fase 3 is partnerportal mogelijk niet toegankelijk. Gedurende deze periode heeft Partner mogelijk geen toegang tot de informatie van de tenant op de Partnerportal. Aangezien elke migratie anders is, kan de duur van de in-toegankelijkheid in uren zijn.

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>eDiscovery fase 4 tot het einde van fase 9

**Van toepassing op:** Alle klanten die eDiscovery gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Vanaf het begin van fase 4 tot fase 9 is voltooid, mislukken eDiscovery-zoekopdrachten of retourneren 0 resultaten voor SharePoint Online-, OneDrive voor Bedrijven- en Exchange Online-locaties die zijn gemigreerd. | Tijdens de migratie kunnen klanten zaken blijven maken, in- en uitbaten en exporteren in het [beveiligings- & compliancecentrum,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inclusief [Inhoud zoeken.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Zoekopdrachten op SharePoint Online, OneDrive voor Bedrijven en Exchange Online-locaties die zijn gemigreerd, leveren echter 0 resultaten op of leveren een fout op. Zie de kolom _Impact_ voor herstel. | Als een zoekopdracht nul resultaten of een fout oplevert tijdens de migratie, moet u de volgende actie ondernemen voor SharePoint Online: <ul><li>Download sites rechtstreeks van de SharePoint Online- of OneDrive voor Bedrijven-site door de instructies te volgen in Bestanden en mappen [downloaden vanuit OneDrive of SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Voor deze methode zijn beheerdersmachtigingen of alleen-lezen-machtigingen op de site vereist.</li><li>Als limieten worden overschreden, zoals wordt uitgelegd in Bestanden en mappen downloaden vanuit OneDrive of [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kunnen klanten de synchronisatieclient van OneDrive voor Bedrijven gebruiken door de richtlijnen in [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)en Teams-bestanden synchroniseren met uw computer te volgen.</li><li>Zie [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) voor meer informatie |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>Exchange Online Set-UserPhoto tijdens fase 5

**Van toepassing op:** Alle klanten die gebruikersfoto's opslaan in Exchange Online en **Set-UserPhoto gebruiken:**

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| De nieuwe regio 'Duitsland' wordt toegevoegd aan een bestaande organisatie-instelling van Exchange Online en postvakken worden verplaatst naar Office 365-services. | Exchange Online-configuratie voegt de nieuwe go-locale Duitse regio toe aan de overgangsorganisatie. Dit Office 365-servicesgebied is standaard ingesteld, waardoor de interne taakverdelingsservice postvakken kan distribueren naar de juiste standaardregio in Office 365-services. In deze overgang zijn gebruikers aan beide zijden (Duitsland of Office 365-services) in dezelfde organisatie en kunnen ze URL-eindpunten gebruiken. | Als een gebruikerspostvak is gemigreerd, maar een beheerderspostvak niet is gemigreerd, of omgekeerd, kunnen beheerders **set-UserPhoto,** een PowerShell-cmdlet, niet uitvoeren. In dit geval moet een beheerder een extra tekenreeks doorgeven tijdens het instellen van de verbinding met `ConnectionUri` de volgende syntaxis: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> waar is de tijdelijke aanduiding voor de e-mail-id van de gebruiker van wie de foto moet worden `<user_email>` gewijzigd met **Set-UserPhoto.** |
||||

## <a name="post-migration"></a>Na de migratie

### <a name="azure-ad-phase-9"></a>Azure AD fase 9

**Van toepassing op:** Alle klanten die identiteiten synchroniseren met Azure AD Connect

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Werk Azure AD Connect bij. | Nadat de cut over naar Azure AD is voltooid, maakt de organisatie volledig gebruik van Office 365-services en is ze niet meer verbonden met Microsoft Cloud Deutschland. Op dit moment moet de klant ervoor zorgen dat het deltasynchronisatieproces is afgerond en daarna de tekenreekswaarde van `AzureInstance` 3 (Microsoft Cloud Deutschland) wijzigen in 0 in het `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registerpad. | Wijzig de waarde van `AzureInstance` de registersleutel. Als u dit niet doet, worden objecten niet gesynchroniseerd nadat de Microsoft Cloud Deutschland-eindpunten niet meer beschikbaar zijn. |
|||||

**Van toepassing op:** Alle klanten die federatief verificatie gebruiken met ADFS

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Vertrouwen van afhankelijke partijen verwijderen uit Microsoft Cloud Deutschland AD FS. | Nadat de cut-over naar Azure AD is voltooid, maakt de organisatie volledig gebruik van Office 365-services en is ze niet meer verbonden met Microsoft Cloud Deutschland. Op dit moment moet de klant het vertrouwen van de vertrouwensrelatie met de Microsoft Cloud Deutschland-eindpunten verwijderen. Dit kan alleen als geen van de toepassingen van de klant naar Microsoft Cloud Deutschland-eindpunten wijst wanneer Azure AD wordt gebruikt als idp (Identity Provider). | Federatief verificatie-organisaties | Geen. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Van toepassing op:** Eindgebruikers van wie de goedkeuringsaanvragen voor Azure AD-groep niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie 

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Aanvragen om deel te nemen aan een Azure AD-groep in de afgelopen 30 dagen vóór de migratie, moeten opnieuw worden aangevraagd als de oorspronkelijke aanvraag niet is goedgekeurd. | Eindgebruikers moeten het Access-deelvenster gebruiken om opnieuw een aanvraag in te dienen om deel te nemen aan een Azure AD-groep als deze aanvragen niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie. |  Als eindgebruiker: <ol><li>Ga naar [het Access-deelvenster](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Zoek een Azure AD-groep waarvoor lidmaatschapsgoedkeuring in behandeling was gedurende de 30 dagen vóór de migratie.</li><li>Vraag om opnieuw deel te nemen aan de Azure AD-groep.</li></ol> Aanvragen om deel te nemen aan een groep die minder dan 30 dagen vóór de migratie actief zijn, kunnen niet worden goedgekeurd, tenzij ze na de migratie opnieuw worden aangevraagd. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Van toepassing op:**  Alle klanten die hun eigen DNS-zones beheren

| Stap(en) | Beschrijving | Gevolg |
|:------|:-------|:-------|
| Werk on-premises DNS-services voor Office 365-services-eindpunten bij. | Door klanten beheerde DNS-vermeldingen die naar Microsoft Cloud Deutschland wijzen, moeten worden bijgewerkt om te wijzen naar de eindpunten van globale services van Office 365. | Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. |
||||

**Van toepassing op:** Klanten die gebruikmaken van services van derden voor office 365-services

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Werk partners en services van derden bij voor office 365-services- eindpunten. | <ul><li>Services en partners van derden die naar Office 365 Duitsland wijzen, moeten worden bijgewerkt om te wijzen naar de office 365-services-eindpunten. Voorbeeld: Registreer opnieuw, in overeenstemming met uw leveranciers en partners, de galerie-app-versie van toepassingen, indien beschikbaar. </li><li>Wijs alle aangepaste toepassingen aan die gebruikmaken van Graph API `graph.microsoft.de` van naar `graph.microsoft.com` . Andere API's met gewijzigde eindpunten moeten ook worden bijgewerkt, als ze worden gebruikt. </li><li>Wijzig alle niet-first-party enterprise-toepassingen om om te leiden naar de wereldwijde eindpunten. </li></ul>| Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. |
||||

### <a name="sharepoint-online-post-migration"></a>SharePoint Online na migratie

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| SharePoint 2013-werkstromen opnieuw publiceren. | In het werk van vóór de migratie hebben we het aantal SharePoint 2013-werkstromen verminderd. Nu de migratie is voltooid, kan de klant de werkstromen opnieuw publiceren. | Dit is een vereiste actie. Als u dit niet doet, kan dit leiden tot verwarring bij gebruikers en helpdeskgesprekken. |
| Items delen via Outlook | Items delen in SharePoint Online en OneDrive voor Bedrijven via Outlook werkt niet meer na tenant cutover. |<ul><li>In SharePoint Online en OneDrive voor Bedrijven kunt u items delen via Outlook. Nadat u op de Outlook-knop hebt gedrukt, wordt er een deelbare koppeling gemaakt en in een nieuw bericht in de Outlook Web App gedrukt.</li><li>Na tenant cutover werkt deze methode voor delen niet meer. We herkennen dat dit een bekend probleem is. Aangezien deze Outlook-functie echter op het pad van afzetting staat, is het oplossen van het probleem niet gepland totdat de intrekking is uitgerold. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online na migratie

Als u een hybride Exchange-configuratie gebruikt:

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| De wizard Hybride configuratie (HCW) opnieuw uitvoeren voor Office 365-services. | De bestaande HCW-configuratie is bedoeld ter ondersteuning van Microsoft Cloud Deutschland. Als de migratie van Exchange-services is voltooid, ontkoppelen we on-premises configuratie van Microsoft Cloud Deutschland. |<ul><li>Vereiste actie. Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients. Voordat de migratie van Exchange-postvakken begint (met 5 of meer dagen van kennisgeving), informeert u klanten dat ze moeten stoppen met onboarding of offboarding van hun postvakken.  Als ze dat niet doen, zien ze fouten in hun verhuisverzoeken. </li><li>Nadat de migratie van Exchange-postvakken is voltooid, meldt u clients dat ze de onboarding en offboarding-bewegingen kunnen hervatten. <br> **Test-MigrationServer UitvoerenAvailabiilty**, een PowerShell-cmdlet, tijdens de migratie van Exchange van Microsoft Cloud Deutschland naar Office 365-services werkt mogelijk niet. De migratie werkt echter correct nadat de migratie is voltooid. </li><li>Als clients problemen hebben met referenties of autorisatie nadat postvakken zijn gemigreerd, kunnen gebruikers hun on-premises beheerdersreferenties in het migratie-eindpunt opnieuw openen door het migratie-eindpunt uit te voeren of door hetzelfde in te stellen met behulp van `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange Control Panel (ECP). </li></ul>|

### <a name="ediscovery-post-migration"></a>eDiscovery na migratie

**Van toepassing op:** Alle klanten die eDiscovery gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
|  Alle locaties van SharePoint Online, OneDrive voor Bedrijven en Exchange Online zijn samen met het Beveiligings- en compliancecentrum (SCC) gemigreerd. | Alle eDiscovery-activiteiten moeten worden uitgevoerd vanuit de wereldwijde tenant. Zoekopdrachten zijn nu 100% succesvol.  Eventuele fouten of fouten moeten de normale ondersteuningskanalen volgen. | Geen |
||||

**Van toepassing op:**  Alle klanten die een bewaarbeleid hebben toegepast als onderdeel van de stappen vóór de migratie

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens de stappen vóór de migratie | Klanten kunnen het bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens het werk van de klanten vóór de migratie. | Geen |
||||

## <a name="next-step"></a>Volgende stap

[Acties en effecten van migratiefasen begrijpen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Informatie over power bi-migratieprogramma's](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams-upgrade](/microsoftteams/upgrade-start-here)