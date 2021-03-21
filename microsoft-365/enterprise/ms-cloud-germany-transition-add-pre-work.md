---
title: Pre-work for the migration from Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: 'Overzicht: Pre-work when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.'
ms.openlocfilehash: 37fde0119dfc84cbe9120cf922cbac469a0a50f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923836"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Pre-work for the migration from Microsoft Cloud Deutschland

Gebruik deze koppelingen om naar de pre-work-stappen te gaan die relevant zijn voor uw organisatie:

- Voor alle klanten die Office 365 in Microsoft Cloud Deutschland gebruiken, doet u [deze stappen.](#applies-to-everyone)
- Als u Exchange Online of Exchange hybrid gebruikt, doet u [deze stap](#exchange-online).
- Als u SharePoint Online gebruikt, doet u [deze stap](#sharepoint-online).
- Als u een MDM-oplossing (Mobile Device Management) van derden gebruikt, doet u [deze stap](#mobile).
- Als u service- of lob-apps van derden gebruikt die zijn geïntegreerd met Office 365, doet u [deze stap](#line-of-business-apps).
- Als u ook Azure-services gebruikt die buiten uw Office 365-abonnement vallen, doet u [deze stap](#microsoft-azure).
- Als u ook Dynamics 365 gebruikt, doet u [deze stap](#dynamics365).
- Als u ook Power BI gebruikt, doet u [deze stap](#power-bi).
- Voor DNS-wijzigingen doet u [deze stap](#dns).
- Als u federatief identiteit gebruikt, gaat u als [volgende stappen te werk.](#federated-identity)

## <a name="applies-to-everyone"></a>Van toepassing op iedereen

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Bereid u voor om gebruikers op de hoogte te stellen van het opnieuw opstarten en aanmelden bij hun clients na de migratie. | Office-clientlicenties worden tijdens de migratie overgeslagen van Microsoft Cloud Deutschland naar Office 365-services. Klanten halen een nieuwe geldige licentie op nadat ze zich hebben aanmelden bij Office-clients. | Office-producten van gebruikers moeten licenties vernieuwen vanuit Office 365-services. Als licenties niet worden vernieuwd, kunnen er fouten optreden bij het valideren van licenties voor Office-producten. |
| Zorg voor netwerkconnectiviteit [met URL's en IP-adressen van Office 365-services.](./urls-and-ip-address-ranges.md) | Alle clients en services die worden gehost door de klant die worden gebruikt om toegang te krijgen tot office 365-service, moeten toegang hebben tot de eindpunten voor globale services van Office 365. <br>In het geval dat u of uw samenwerkingspartners firewallregels hebben die verhinderen dat de URL's en IP-adressen worden gebruikt die worden vermeld in URL's en IP-adressen van [Office 365-services,](./urls-and-ip-address-ranges.md) moeten de firewallregels worden gewijzigd om toegang te krijgen tot de globale service-eindpunten van Office 365| Fouten van de service- of clientsoftware kunnen optreden als dit niet vóór fase 4 gebeurt  |
| Eventuele proefabonnementen opzeggen. | Proefabonnementen worden niet gemigreerd en blokkeren de overdracht van betaalde abonnementen. | Proefservices zijn verlopen en werken niet als ze worden gebruikt door gebruikers na annulering. |
| Analyseer verschillen in licentiefuncties tussen Microsoft Cloud Deutschland en Office 365 Services. | Office 365-services bevatten extra functies en services die niet beschikbaar zijn in de huidige Microsoft Cloud Deutschland. Tijdens de abonnementsoverdracht zijn nieuwe functies beschikbaar voor gebruikers. | <ul><li> Analyseer de verschillende functies van de licenties voor Microsoft Cloud Deutschland en Office 365 Services. Begin met de Servicebeschrijving van [het Office 365-platform.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Bepaal of nieuwe functies van Office 365-services in eerste instantie moeten worden uitgeschakeld om de effecten op gebruikers of op het beheer van gebruikerswijziging te beperken en de toewijzingen voor gebruikerslicenties zo nodig te wijzigen. </li><li>Bereid gebruikers en helpdeskmedewerkers voor op nieuwe services en functies die worden geleverd door Office 365-services. |
| Maak bewaarbeleid voor de hele organisatie [om](../compliance/retention.md) te beschermen tegen onbedoeld verwijderen van inhoud tijdens de migratie.  |<ul><li>Om ervoor te zorgen dat inhoud niet per ongeluk wordt verwijderd door eindgebruikers tijdens de migratie, kunnen klanten ervoor kiezen om een bewaarbeleid voor de hele organisatie in te stellen. </li><li>Hoewel bewaren niet vereist is, omdat bewaringen die op elk gewenst moment tijdens de migratie worden geplaatst, moeten werken zoals verwacht, is het hebben van een bewaarbeleid een back-upveiligheidsmechanisme. Tegelijkertijd kan een bewaarbeleid niet door alle klanten worden gebruikt, met name niet door klanten die zich zorgen maken over bewaring.</li></ul>| Bewaarbeleid toepassen zoals beschreven in [Meer informatie over bewaarbeleid en bewaarlabels.](../compliance/retention.md) Fouten van de service- of clientsoftware kunnen optreden als dit niet vóór fase 4 van 9 gebeurt. </li></ul>|
| Licentie-overages corrigeren | In bepaalde omstandigheden kunnen klanten mogelijk meer services gebruiken dan worden gekocht. Deze voorwaarde staat bekend als een licentie overage. Microsoft kan geen klanten met een licentie overbewaardend migreren van Microsoft Cloud Deutschland naar de Duitse datacenterregio's. Om continue toegang tot de service en gegevens te garanderen, heeft elke toegewezen gebruiker een licentie nodig. | Alle klanten | Klanten moeten de voorwaarde voor het gebruik van licenties evalueren en oplossen door extra licenties aan te schaffen of door licenties van gebruikers op te geven. |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)

**Is van toepassing op**: Klanten die AD FS on-premises gebruiken om gebruikers te verifiëren die verbinding maken met Microsoft Office 365

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| [Back-up van Ad FS-farm (Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) voor scenario's voor herstel na nood. | Klanten moeten op de juiste manier een back-up maken van de AD FS-farm om ervoor te zorgen dat de vertrouwensrelatie van de afhankelijke partij met globale & Duitsland-eindpunten kan worden hersteld zonder de URI van de uitgevende partij van de domeinen aan te raken. Microsoft raadt aan AD FS Rapid Restore te gebruiken voor een back-up van de farm en de desbetreffende herstel indien nodig. | Vereiste actie. Als de AD FS-farm van de klant mislukt, heeft dit gevolgen voor de service tijdens de migratie. Zie [ADFS-migratiestappen](./ms-cloud-germany-transition-add-adfs.md) voor meer informatie |
||||

## <a name="exchange-online"></a>Exchange Online

**Is van toepassing** op : Exchange Online-klanten die agenda- en beschikbaarheidsadresruimte voor delen hebben ingeschakeld.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Informeer externe partners over de aanstaande overgang naar Office 365-services. | Met configuraties voor beschikbaarheidsadresruimte kunt u gratis/bezet informatie delen met Office 365. | Als u dit niet doet, kan dit leiden tot een service- of clientfout in een latere fase van de klantmigratie. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Hybride configuratie van Exchange Online

**Is van toepassing op**: Exchange Online-klanten met een actieve hybride Exchange-configuratie

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Werk op elk gewenst moment bij naar de nieuwste versie van de wizard Hybride configuratie (HCW) voordat uw tenant de migratiefase 5 in gaat. U kunt deze activiteit direct starten nadat u de melding van het berichtencentrum hebt ontvangen dat de migratie van uw Office 365-tenant is gestart.<br><br> Hybride Exchange Online-klanten van Microsoft Cloud Deutschland moeten eerdere versies van HCW verwijderen en vervolgens de nieuwste versie (17.0.5378.0 of hoger) installeren en [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) uitvoeren. |<ul><li>De nieuwste versie van de HCW bevat benodigde updates om klanten te ondersteunen die overstappen van Microsoft Cloud Deutschland naar Office 365 Services.</li><li> Updates zijn onder andere wijzigingen in de on-premises certificaatinstellingen voor de connector Verzenden en de Connector Ontvangen.</li><li> Exchange-beheerders moeten de HCW opnieuw installeren voordat fase 5 van 9 (Exchange-migratie) begint.<br>Wanneer u de HCW vóór fase 5 uitvoert, selecteert u 'Office 365 Germany' op de 2e pagina van de HCW onder _Office 365 Exchange Online_ in de keuzelijst onder Mijn Office _365-organisatie wordt_ gehost door</li><li>**OPMERKING:** Nadat de migratie van uw Office 365-tenant is voltooid, verwijdert en installeert u de HCW opnieuw, ditmaal met de instellingen 'Office 365 Worldwide' op de 2e pagina van de HCW om uw hybride installatie te voltooien met de globale Exchange Online-service.</li></ul>|Het niet uitvoeren van de HCW vóór fase 5 (Exchange-migratie) kan leiden tot service- of clientfout. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**Van toepassing op**: Klanten die SharePoint 2013 on-premises gebruiken


| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Beperk SharePoint 2013-werkstromen, die worden gebruikt tijdens de SharePoint Online-migratie. | Verminder SharePoint 2013-werkstromen en voltooi werkstromen tijdens de vlucht vóór overgangen. | Actie kan leiden tot verwarring bij gebruikers en helpdeskgesprekken. |
||||

## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

**Van toepassing op**: Klanten van Skype voor Bedrijven Online

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Teams-bureaubladclient implementeren voor gebruikers die Skype voor Bedrijven in Duitsland openen. | Migratie verplaatst Skype voor Bedrijven-gebruikers naar Microsoft Teams voor samenwerking, bellen en chatten. Implementeer de bureaubladclient van Microsoft Teams of zorg ervoor dat er een ondersteunde browser beschikbaar is. | Niets doen resulteert in het niet beschikbaar zijn van microsoft Teams-samenwerkingsservices. |
| Controleer en bereid u voor op migratiegerelateerde DNS-wijzigingen. | Wijzigingen in de DNS-zone van klanten voor Skype voor Bedrijven Online. |<ul><li>U wordt aangeraden de Time-to-Live (TTL) voor dns-records van een klant bij te werken tot 5 minuten om het vernieuwen van DNS-records te versnellen. De door Microsoft beheerde cutover die aan deze DNS-wijziging is gekoppeld, kan echter op elk gewenst moment plaatsvinden binnen het opgegeven wijzigingsvenster van 24 uur. </li><li>Serviceonderbreking is mogelijk in de toekomst. Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven en worden omgeleid naar de gemigreerde Teams-ervaring in de Office 365-services. </li></ul>|
| Trainings- en beheertraining voor eindgebruikers voorbereiden en klaar zijn voor de overgang naar Microsoft Teams. | Wees succesvol in de overgang van Skype naar Teams door communicatie en gereedheid van gebruikers te plannen. | <ul><li>Klanten moeten op de hoogte zijn van de nieuwe services en hoe ze deze kunnen gebruiken wanneer hun services zijn overgestappen naar de Office 365-services. </li><li>Nadat DNS-wijzigingen zijn aangebracht voor zowel de klant-vanitydomeinen als het oorspronkelijke domein, melden gebruikers zich aan bij Skype voor Bedrijven en zien ze dat ze nu worden gemigreerd naar Teams. Hiermee wordt ook de bureaubladclient voor Teams op de achtergrond gedownload. </li></ul>|
||||

## <a name="mobile"></a>Mobiel

Als u een MDM-oplossing (Mobile Device Management) van derden gebruikt:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bereid training voor eindgebruikers en beheer voor over gebruikers die hun account verwijderen en opnieuw toevoegen aan Microsoft Outlook voor iOS en Android. | Microsoft Outlook voor iOS- en Android-accounts die zijn geconfigureerd met postvakken in Microsoft Cloud Deutschland, moeten mogelijk opnieuw worden verwijderd en toegevoegd aan Outlook om de nieuwe Configuratie van Office 365-services correct te synchroniseren. | Microsoft Outlook voor iOS- en Android-klanten | Outlook-postvakken die eerder zijn geconfigureerd voor Microsoft Cloud Deutschland, kunnen de nieuwe Configuratie van Office 365 Services mogelijk niet gebruiken, wat leidt tot fouten en slechtere prestaties van andere gebruikerservaringen. IT-beheerders worden aangeraden documentatie te verstrekken die gebruikers proactief instrueert hun accounts te verwijderen en opnieuw toe te voegen aan Microsoft Outlook voor iOS en Android als er na de migratie problemen optreden met het aanmelden of synchroniseren van e-mail. |
| Bepaal of een herconfiguratie vereist is na de migratie. | MDM-oplossingen (Mobile Device Management) kunnen `outlook.de` eindpunten targeten. In deze overgang naar Office 365 Services moeten clientprofielen worden bijgewerkt naar de URL van de Office 365-services, `outlook.office365.com` . | Exchange Online- en MDM-klanten | Clients kunnen blijven functioneren terwijl het eindpunt toegankelijk is, maar ze mislukken als `outlook.de` Microsoft Cloud Deutschland-eindpunten niet meer beschikbaar zijn. |
|||||

## <a name="line-of-business-apps"></a>Line-of-business-apps

Als u een service van derden gebruikt of LOB-apps (Line Of Business) gebruikt die zijn geïntegreerd met Office 365: 

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Bepaal of een herconfiguratie vereist is na de migratie. | Services en toepassingen van derden die zijn geïntegreerd met Office 365, kunnen worden gecodeerd om IP-adressen en URL's van Microsoft Cloud Deutschland te verwachten. | Vereiste actie. Een actie kan leiden tot fouten in de service- of clientsoftware. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Van toepassing op**: Klanten die Microsoft Dynamics gebruiken

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Voor Dynamics 365 sandbox-abonnementen moet u de productieomgeving van het SQL-exemplaar Dynamics downloaden van uw Dynamics 365-abonnement in Microsoft Cloud Deutschland. De nieuwste productieback-up moet worden hersteld naar de sandbox voordat de sandbox wordt gemigratied. | Voor de migratie van Dynamics 365 moeten klanten ervoor zorgen dat de Sandbox-omgeving wordt vernieuwd met de nieuwste productiedatabase. | Het FastTrack-team helpt klanten bij het uitvoeren van dry runs om de versie-upgrade te valideren van 8.x naar 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Van toepassing op**: Power BI-klanten 

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Objecten verwijderen uit Power BI-abonnementen die niet worden gemigreerd van Power BI Microsoft Cloud Deutschland naar Office 365-services. | Migratie van Power BI-services vereist actie van de klant om bepaalde artefacten te verwijderen, zoals gegevenssets en dashboards. | <ul><li>Beheerders moeten mogelijk de volgende items uit hun abonnement verwijderen: </li><li>Real-Time gegevenssets (bijvoorbeeld streaming- of pushsets) </li><li>Configuratie en gegevensbron van Power BI on-premises Data Gateway </li></ul>|
||||

## <a name="dns"></a>DNS

**Is van** toepassing op : Klanten met office-bureaubladclient (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Verwijder MSOID, CName uit dns van klanten als deze op elk gewenst moment bestaat voordat Azure Active Directory (Azure AD) wordt overgekapt. U kunt een TTL van 5 minuten instellen, zodat de wijziging snel van kracht kan worden.

## <a name="federated-identity"></a>Federatief identiteit

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Voeg een id voor eenmalige aanmelding (SSO) toe aan een bestaande vertrouwensrelatie van een afhankelijke partij en schakel automatische ad-FS-metagegevensupdates uit. | Er moet een id worden toegevoegd aan het vertrouwen van de ad-FS-afhankelijke partij voordat u de migratie start. Als u wilt voorkomen dat de id van de afhankelijke partij per ongeluk wordt verwijderd, schakelt u automatisch bijwerken voor metagegevensupdates uit. <br><br> Voer deze opdracht uit als één opdrachtregel op de AD FS-server: <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| Federatief verificatie-organisaties | Vereiste actie. Inactiviteit vóór fase 4 van 9 (SharePoint) resulteert in service-impact tijdens de migratie.  |
| Vertrouwen van afhankelijke partijen genereren voor globale Azure AD-eindpunten. | Klanten moeten handmatig een vertrouwensrelatie (Relying Party Trust) maken met [globale](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) eindpunten. Dit wordt gedaan door een nieuwe RPT toe te voegen via GUI door gebruik te maken van de URL van de globale federatiemetagegevens en vervolgens [Azure AD RPT-claimregels](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (in AD FS Help) te gebruiken om de claimregels te genereren en deze te importeren in de RPT. | Federatief verificatie-organisaties | Vereiste actie. Inactiviteit resulteert in service-impact tijdens de migratie. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

Als u dezelfde Azure Active Directory-identiteitspartitie voor Office 365 en Microsoft Azure gebruikt in het exemplaar Microsoft Cloud Deutschland, moet u zich voorbereiden op de klantgestuurde migratie van Microsoft Azure-services.
De migratie van uw Microsoft Azure-services mag niet worden gestart voordat uw Office 365-tenant migratiefase 3 heeft bereikt en moet zijn voltooid voordat migratiefase 8 is voltooid.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Bepaal welke Azure-services worden gebruikt en bereid u voor op toekomstige migratie van Duitsland naar de Office 365-services tenant door samen met uw partners te werken. Volg de stappen die worden beschreven in de [Azure-migratie playbook](/azure/germany/germany-migration-main). |<ul><li>Migratie van Azure-resources is een verantwoordelijkheid van de klant en vereist handmatige inspanning volgens de voorgeschreven stappen. Inzicht in de services die in de organisatie worden gebruikt, is essentieel voor een succesvolle migratie van Azure-services. </li><li> Office 365 Germany-klanten met Azure-abonnementen onder dezelfde identiteitspartitie (organisatie) moeten de door Microsoft voorgeschreven volgorde volgen wanneer ze kunnen beginnen met de migratie van abonnementen en services.</li></ul>|<ul><li>Klanten hebben mogelijk meerdere Azure-abonnementen, elk abonnement met infrastructuur, services en platformonderdelen. </li><li> Beheerders moeten abonnementen en belanghebbenden identificeren om ervoor te zorgen dat snelle migratie en validatie mogelijk is als onderdeel van deze migratiegebeurtenis. </li><li>Als de migratie van deze abonnementen en Azure-onderdelen binnen de voorgeschreven tijdlijn niet is voltooid, is dit van invloed op de voltooiing van de Office- en Azure AD-overgang naar Office 365-services en kan dit leiden tot gegevensverlies. </li><li> Een berichtcentrummelding geeft aan op welk punt de migratie door de klant kan beginnen. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

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