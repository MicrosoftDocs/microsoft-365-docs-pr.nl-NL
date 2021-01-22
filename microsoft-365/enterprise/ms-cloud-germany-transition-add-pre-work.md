---
title: Pre-work voor de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921564"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Pre-work voor de migratie van Microsoft Cloud Deutschland


Gebruik deze koppelingen om naar de pre-workstappen te gaan die relevant zijn voor uw organisatie:

- Ga voor alle abonnementen als volgende [stappen te werk.](#applies-to-everyone)
- Als u een hybride versie van Exchange Online of Exchange gebruikt, moet u [deze stap volgen.](#exchange-online)
- Als u SharePoint Online gebruikt, doet u [deze stap.](#sharepoint-online)
- Als u een externe MDM-oplossing (Mobile Device Management) gebruikt, gaat u als [volgende stap te werk.](#mobile)
- Als u service of LOB-apps (Line-Of-Business) gebruikt die zijn geïntegreerd met Office 365, gaat u als volgende [stap te werk.](#line-of-business-apps)
- Als u ook Gebruik maakt van Azure-services die niet zijn inbegrepen bij uw Office 365-abonnement, gaat u als [volgende stap te werk.](#azure)
- Als u ook Dynamics 365 gebruikt, doet u [deze stap.](#dynamics365)
- Als u ook Power BI gebruikt, doet u [deze stap.](#power-bi)
- Voor DNS-wijzigingen gaat u [als volgende stap te werk.](#dns)
- Als u federatief identiteit gebruikt, gaat u als [volgen te werk.](#federated-identity)

## <a name="applies-to-everyone"></a>Van toepassing op iedereen

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Zorg voor netwerkconnectiviteit met [URL's en IP-adressen voor Office 365-services.](https://aka.ms/o365urls) | Alle klanten en services die worden gehost door de klant en die worden gebruikt om toegang te krijgen tot de Office 365-service, moeten toegang hebben tot de eindpunten van de Office 365-services. | Alle overstappende klanten en klanten met netwerktoegang beperkt tot Microsoft Cloud Deutschland. | Vereiste actie. Inactiviteit kan leiden tot fouten in de service of clientsoftware. |
| Controleer en bereid u voor op migratiegerelateerde DNS-wijzigingen. | Klant bereidt DNS-vermeldingen voor voor Exchange Online en Exchange Online Protection (MX-record, enzovoort). | Exchange Online-klanten | Dit is een aanbevolen actie. Geen actie betekent dat gemigreerde e-mail van klanten kan worden gerouteerd via Microsoft Cloud Deutschland totdat de Microsoft Cloud Deutschland-services zijn uitgeschakeld. |
| Controleer en bereid u voor op migratiegerelateerde DNS-wijzigingen. | DNS-zonewijzigingen van klanten voor Skype voor Bedrijven Online. | Klanten van Skype voor Bedrijven Online | - U wordt aangeraden de TTL (Time-to-Live) voor DNS-records in het domein van klanten bij te werken naar 5 minuten, zodat de DNS-records sneller worden vernieuwd. De door Microsoft beheerde cutover die aan deze DNS-wijziging is gekoppeld, kan echter altijd plaatsvinden binnen het opgegeven wijzigingsvenster van 24 uur. <br><br> - Onderbreking van de service is mogelijk in de toekomst. Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven en worden omgeleid naar de gemigreerde Teams-ervaring in de Office 365-services. |
| Bereid de training en gereedheid voor eindgebruikers en beheer voor op de overgang naar Microsoft Teams. | Be succesvol in de overgang van Skype naar Teams door de communicatie en gereedheid van gebruikers te plannen. | Klanten van Skype voor Bedrijven Online | - Klanten moeten op de hoogte zijn van de nieuwe services en moeten weten hoe ze deze kunnen gebruiken wanneer hun services zijn overstappen op de Office 365-services. <br><br> - Nadat DNS-wijzigingen zijn aangebracht voor zowel de klantdomeinen als het oorspronkelijke domein, zouden gebruikers zich aanmelden bij Skype voor Bedrijven en zien dat ze nu worden gemigreerd naar Teams. Hiermee wordt ook de bureaubladclient voor Teams op de achtergrond gedownload. |
| Bereid trainingen voor eindgebruikers en beheer voor over gebruikers die hun account verwijderen en opnieuw toevoegen aan Microsoft Outlook voor iOS en Android. | Microsoft Outlook voor iOS- en Android-accounts die zijn geconfigureerd met postvakken in Microsoft Cloud Deutschland, moeten mogelijk worden verwijderd en opnieuw worden toegevoegd aan Outlook om de nieuwe Office 365-servicesconfiguratie correct te synchroniseren. | Microsoft Outlook voor iOS- en Android-klanten | Outlook-postvakken die eerder zijn geconfigureerd voor Microsoft Cloud Deutschland, halen mogelijk niet de nieuwe configuratie voor Office 365-services op, wat leidt tot fouten en slechtere prestaties van andere gebruikerservaringen. IT-beheerders worden aangeraden documentatie te verstrekken waarin gebruikers proactief instructies krijgen om hun accounts te verwijderen en opnieuw toe te voegen aan Microsoft Outlook voor iOS en Android als er na de migratie problemen optreden met het aanmelden of synchroniseren van e-mail. |
| Bereid u voor om gebruikers te informeren over het opnieuw opstarten en aanmelden bij en bij hun klanten na de migratie. | Office-clientlicenties zullen overstappen van Microsoft Cloud Deutschland naar Office 365-services tijdens de migratie. Klanten halen een nieuwe geldige licentie op na het aanmelden bij en bij Office-clients. | Klanten van Microsoft 365-apps |  De Office-producten van gebruikers moeten licenties vernieuwen vanuit Office 365-services. Als licenties niet worden vernieuwd, kunnen er fouten in de licentievalidatie optreden voor Office-producten. |
| Annuleer proefabonnementen. | Proefabonnementen worden niet gemigreerd en blokkeren de overdracht van betaalde abonnementen. | Alle klanten | Proefservices zijn verlopen en werken niet als deze na annulering door gebruikers worden gebruikt. |
| Implementeer de Teams-bureaubladclient voor gebruikers die Skype voor Bedrijven in Duitsland gebruiken. | Migratie verplaatst gebruikers naar Teams voor samenwerking, bellen en chatten. Implementeer de Teams-bureaubladclient of zorg ervoor dat er een ondersteunde browser beschikbaar is. | Klanten van Skype voor Bedrijven | Inaction resulteert in niet-beschikbaarheid van teams-samenwerkingsservices. |
| Analyseer verschillen in licentiefuncties tussen Microsoft Cloud Deutschland en Office 365-services. | Office 365-services bevatten extra functies en services die niet beschikbaar zijn in de huidige Microsoft Cloud Deutschland. Tijdens de overdracht van het abonnement komen nieuwe functies beschikbaar voor gebruikers. | Alle klanten | - Analyseer de verschillende functies die beschikbaar zijn in de licenties voor Microsoft Cloud Deutschland en Office 365-services. Begin met de [Servicebeschrijving van het Office 365-platform.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) <br><br> - Bepaal of nieuwe functies van Office 365-services in eerste instantie moeten worden uitgeschakeld om het effect op gebruikers of op gebruikersbeheer te beperken en de licentietoewijzingen van gebruikers zo nodig te wijzigen. <br><br> - Bereid gebruikers en helpdeskmedewerkers voor op nieuwe services en functies die worden geleverd door Office 365-services. |
| Maak bewaarbeleid [voor](https://docs.microsoft.com/microsoft-365/compliance/retention) de hele organisatie om te beschermen tegen onbedoelde verwijdering van inhoud tijdens een migratie.  | - Om ervoor te zorgen dat inhoud niet per ongeluk door eindgebruikers wordt verwijderd tijdens de migratie, kunnen klanten ervoor kiezen om een bewaarbeleid voor de hele organisatie in te stellen. <br><br> - Hoewel bewaarbeleid niet vereist is, is het een back-up veiligheidsmechanisme omdat bewaringen op elk gewenst moment tijdens de migratie naar verwachting moeten werken. Tegelijkertijd kan een bewaarbeleid niet door alle klanten worden gebruikt, met name door klanten die zich zorgen maken over het behoud. | Office-klanten | Bewaarbeleid toepassen zoals wordt beschreven in [Meer informatie over bewaarbeleid en bewaarlabels.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) |
| [Back-up van AD FS-farm (Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) voor herstel na noodherstel. | Klanten moeten op de juiste manier een back-up maken van de AD FS-farm om ervoor te zorgen dat de vertrouwensrelatie tussen de afhankelijke partijen voor globale & Germany-eindpunten kan worden hersteld zonder de URI van de uitgiftegever van de domeinen aan te raken. Microsoft raadt u aan AD FS Rapid Restore te gebruiken voor een back-up van de farm en de desbetreffende herstelkopie, indien nodig. | Federatieverificatie-organisaties | Vereiste actie. Actie heeft gevolgen voor de service tijdens de migratie als de AD FS-farm van de klant mislukt. |


## <a name="exchange-online"></a>Exchange Online

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Informeer externe partners over de aanstaande overgang naar Office 365-services. | Met configuraties voor de beschikbaarheidsadresruimte kunt u beschikbaarheidsinformatie delen met Office 365. | Exchange Online-klanten die het delen van agenda- en beschikbaarheidsadresruimte hebben ingeschakeld. | Vereiste actie.  Als u dit niet doet, kan dit in een latere fase van de klantmigratie leiden tot een service- of clientfout. |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>Voor hybride Exchange

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijder eerdere versies van de wizard Hybride configuratie (HCW) en installeer en voer vervolgens de nieuwste versie, 17.0.5378.0, van [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | De nieuwste versie van de HCW bevat benodigde updates ter ondersteuning van klanten die overstappen van Microsoft Cloud Deutschland naar Office 365 Services. <br><br> Updates zijn onder andere wijzigingen in de instellingen voor on-premises certificaten voor connector voor verzenden en ontvangen van connectors. | Exchange Online-klanten die een hybride implementatie uitvoeren | Vereiste actie. Als u dit niet doet, kan dit leiden tot een service- of clientfout. |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

Als u SharePoint 2013 hebt:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Beperk SharePoint 2013-werkstromen, die worden gebruikt tijdens de SharePoint Online-migratie. | Verminder SharePoint 2013-werkstromen en voltooi flight-werkstromen vóór de overgangen. | SharePoint Online-klanten | Actie kan leiden tot verwarring onder gebruikers en tot telefoontjes van de helpdesk. |
|||||

## <a name="mobile"></a>Mobiel

Als u een MDM-oplossing (Mobile Device Management) van derden gebruikt:

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bepaal of opnieuw configureren is vereist na de migratie. | MDM-oplossingen zijn mogelijk `outlook.de` gericht op eindpunten. In deze overgang naar Office 365 Services moeten clientprofielen worden bijgewerkt naar de URL van de Office 365-services. `outlook.office365.com` | Klanten van Exchange Online en MDM | Clients blijven mogelijk werken terwijl het eindpunt toegankelijk is, maar mislukken als eindpunten van `outlook.de` Microsoft Cloud Deutschland niet meer beschikbaar zijn. |
|||||

## <a name="line-of-business-apps"></a>Line-Of-Business-apps

Als u een service van derden of LOB-apps (Line-Of-Business) gebruikt die zijn geïntegreerd met Office 365: 

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bepaal of opnieuw configureren is vereist na de migratie. | Externe services en toepassingen die kunnen worden geïntegreerd met Office 365, zijn mogelijk gecodeerd om IP-adressen en URL's van Microsoft Cloud Deutschland te verwachten. | Alle klanten | Vereiste actie. Inactiviteit kan leiden tot fouten in de service of clientsoftware. |
|||||

## <a name="azure"></a>Azure 

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bepaal welke Azure-services in gebruik zijn en bereid u voor op een toekomstige migratie van Duitsland naar de Office 365-services-tenant door samen met uw partners te werken. Volg de stappen die worden beschreven in de [Azure-migratie playbook.](https://docs.microsoft.com/azure/germany/germany-migration-main) | Migratie van Azure-resources is een klantverantwoordelijkheid en vereist handmatige inspanning volgens de voorgeschreven stappen. Het is belangrijk om te weten welke services in de organisatie worden gebruikt voor een succesvolle migratie van Azure-services. <br><br> Klanten van Office 365 Germany die een Azure-abonnement hebben met dezelfde identiteitspartitie (organisatie), moeten de door Microsoft voorgeschreven volgorde volgen wanneer ze de migratie van abonnementen en services kunnen starten. | Azure-klanten | - Klanten kunnen meerdere Azure-abonnementen hebben, elk abonnement met infrastructuur, services en platformonderdelen. <br><br> - Beheerders dienen abonnementen en belanghebbenden te identificeren om ervoor te zorgen dat snelle migratie en validatie mogelijk zijn als onderdeel van deze migratiegebeurtenis. <br><br> Als de migratie van deze abonnementen en Azure-onderdelen niet lukt binnen de voorgeschreven tijdlijn, is dit van invloed op de voltooiing van de overgang van Office en Azure AD naar Office 365-services en kan dit leiden tot gegevensverlies.  <br><br> - Een melding in het berichtencentrum geeft aan op welk punt de migratie door de klant kan beginnen. |
|||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="dynamics-365"></a>Dynamics 365

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Download voor Dynamics 365 sandbox-abonnementen de productieomgeving van het Dynamics SQL-exemplaar van uw Dynamics 365-abonnement in Microsoft Cloud Deutschland. De meest recente productieback-up moet worden teruggezet naar de sandbox vóór de migratie van de sandbox. | Bij de migratie van Dynamics 365 moeten klanten ervoor zorgen dat de Sandbox-omgeving wordt vernieuwd met de meest recente productiedatabase. | Klanten van Microsoft Dynamics | Het FastTrack-team helpt klanten bij het uitvoeren van droge runs om de versie-upgrade te valideren van 8.x naar 9.1.x. |
|||||

## <a name="power-bi"></a>Power BI

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijdering van objecten uit Power BI-abonnementen die niet worden gemigreerd van Power BI Microsoft Cloud Deutschland naar Office 365-services. | Voor de migratie van Power BI-services zijn acties van de klant nodig om bepaalde artefacten te verwijderen, zoals gegevenssets en dashboards. | Power BI-klanten | Beheerders moeten mogelijk de volgende items uit hun abonnement verwijderen: <br> - Real-Time (bijvoorbeeld gegevenssets voor streamen of pushen) <br> - On-premises Data Gateway-configuratie en -gegevensbron voor Power BI |
|||||

## <a name="dns"></a>DNS

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijder MSOID, CName uit DNS van de klant als deze op elk gewenst moment bestaat voordat Azure AD wordt overgesneden. U kunt een TTL van 5 minuten instellen, zodat de wijziging snel kan worden doorgevoerd. | DNS-zonewijzigingen van klant | Klanten van Office-clientservices | 
|||||

## <a name="federated-identity"></a>Federatief

| Stap(en) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Voeg een id voor eenmalige aanmelding (SSO) toe aan een bestaand vertrouwen van vertrouwde partijen en schakel automatische updates van AD FS-metagegevens uit. | Een id moet worden toegevoegd aan het AD FS-vertrouwensfeest voordat u de migratie start. Als u wilt voorkomen dat de id van een afhankelijke partij per ongeluk wordt verwijderd, schakelt u automatisch bijwerken uit voor updates van metagegevens. <br><br> Voer deze opdracht uit op de AD FS-server: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Federatieverificatie-organisaties | Vereiste actie. Inactiviteit resulteert in gevolgen voor de service tijdens de migratie.  |
| Genereer vertrouwen van vertrouwen van derden voor globale Azure AD-eindpunten. | Klanten moeten handmatig een vertrouwensrelatie tussen afhankelijke partijen (RPT) [voor](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) globale eindpunten maken. Hiervoor voegt u een nieuwe RPT via GUI toe door gebruik te maken van de URL voor globale federatiemetagegevens en vervolgens Azure AD RPT-claimregels (in AD FS Help) te gebruiken om de claimregels te genereren en deze in het [RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) te importeren. | Federatieverificatie-organisaties | Vereiste actie. Inactiviteit resulteert in gevolgen voor de service tijdens de migratie. |
|||||

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Migratieondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [In te 2010](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

De overgang door lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra voorlopig werk](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Informatie over Dynamics 365-migratieprogramma's](https://aka.ms/d365ceoptin)
- [Informatie over Power BI-migratieprogramma's](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
