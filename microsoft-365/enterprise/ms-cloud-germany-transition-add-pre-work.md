---
title: Activiteiten vóór de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
ms.openlocfilehash: f872a75ed11bfd53c2100f1370a4e22426437bff
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344696"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Activiteiten vóór de migratie van Microsoft Cloud Deutschland

Gebruik deze koppelingen om naar de stappen vóór de migratie te gaan die relevant zijn voor uw organisatie.

Als u

- **Office 365 in Microsoft Cloud Deutschland**, doe [deze stappen.](#general-tenant-migration-considerations)
- **Aangepaste domeinen**, doe [deze stap](#dns-entries-for-custom-domains).
- **Office Apps**, overweeg [deze stap.](#office-apps)
- **SharePoint Online**, doet [u deze stap](#sharepoint-online).
- **Exchange Online** of **Exchange hybride**, doet [u deze stap](#exchange-online).
- **Skype voor Bedrijven Online**, doet [u deze stap](#skype-for-business-online).
- **Dynamics 365**, doe [deze stap](#dynamics365).
- **Power BI**, doet [u deze stap](#power-bi).
- **Active Directory Federation Services** voor Azure AD Verbinding maken: ga [als volgende stappen te werk.](#active-directory-federation-services-ad-fs)
- **Doe deze stap door** services van derden **of LOB-apps (line-of-business)** die zijn geïntegreerd met Office 365. [](#line-of-business-apps)
- Een MDM-oplossing (Mobile Device Management) van derden, doet [u deze stap.](#mobile-device-management)
- Doe deze stap Office 365 **Azure-services** met [uw abonnement.](#microsoft-azure)

## <a name="general-tenant-migration-considerations"></a>Algemene tenantmigratieoverwegingen

**Van toepassing op:** Alle klanten die Office 365 in het Microsoft Deutschland Cloud-exemplaar

Office 365 tenant- en gebruikersaanduidingen blijven behouden tijdens de migratie. Azure AD-serviceoproepen worden omgeleid van Microsoft Cloud Deutschland naar Office 365 Globale services en zijn transparant voor Office 365 services.

- Algemene verordening gegevensbescherming (AVG) Verzoeken om gegevensonderwerpen (DSR's) worden uitgevoerd vanuit de Azure Admin-portal voor toekomstige aanvragen. Oudere of niet-klant diagnostische gegevens die in Microsoft Cloud Deutschland zijn opgeslagen, worden verwijderd na of vóór 30 dagen verstreken.
- Multi-factor authentication (MFA) requests that use Microsoft Authenticator display as the user ObjectID (a GUID) while the tenant is copied to Office 365 services. MFA-aanvragen worden volgens verwachting weergegeven, ondanks dit weergavegedrag.  Microsoft Authenticator accounts die zijn geactiveerd met Office 365 services-eindpunten, wordt de gebruikersnaam (UPN) weergegeven.  Accounts die zijn toegevoegd met Microsoft Cloud Deutschland-eindpunten, geven de gebruiker ObjectID weer, maar werken met zowel Microsoft Cloud Deutschland als Office 365 services-eindpunten.

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Bereid u voor om gebruikers op de hoogte te stellen van het opnieuw opstarten en aanmelden bij hun clients na de migratie. | Office clientlicenties overstappen van Microsoft Cloud Deutschland naar Office 365 services in de migratie. Klanten halen een nieuwe geldige licentie op na het aanmelden bij en Office klanten. | De producten Office gebruikers moeten licenties vernieuwen van Office 365 services. Als licenties niet worden vernieuwd, kunnen er Office fouten optreden bij het valideren van licenties. |
| Zorg voor netwerkconnectiviteit Office 365 [services-URL's en IP-adressen.](https://aka.ms/o365urls) | Alle clients en services die worden gehost door de klant die worden gebruikt voor toegang tot Office 365 service, moeten toegang hebben tot de Office 365 globale services-eindpunten. <br>Als u of uw samenwerkingspartners firewallregels hebben die verhinderen dat de URL's en IP-adressen worden gebruikt die worden vermeld in URL's en IP-adressen van [Office 365-services,](https://aka.ms/o365urls) moeten de firewallregels worden gewijzigd om toegang tot de endpoints van de globale service van Office 365 toe te staan| Fouten van de service- of clientsoftware kunnen optreden als dit niet vóór fase 4 gebeurt  |
| Eventuele proefabonnementen opzeggen. | Proefabonnementen worden niet gemigreerd en blokkeren de overdracht van betaalde abonnementen. | Proefservices zijn verlopen en werken niet als ze worden gebruikt door gebruikers na annulering. |
| Analyseer verschillen in licentiefuncties tussen Microsoft Cloud Deutschland en de Office 365 Global Services. | Office 365 services bevatten extra functies en services die niet beschikbaar zijn in de huidige Microsoft Cloud Deutschland. Tijdens de abonnementsoverdracht zijn nieuwe functies beschikbaar voor gebruikers. | <ul><li> Analyseer de verschillende functies van de licenties voor Microsoft Cloud Deutschland en Office 365 Global Services. Begin met de [servicebeschrijving Office 365 platform.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Bepaal of nieuwe functies van Office 365-services in eerste instantie moeten worden uitgeschakeld om de effecten op gebruikers of het beheer van gebruikerswijziging te beperken en indien nodig gebruikerslicentietoewijzingen te wijzigen. </li><li>Bereid gebruikers en helpdeskmedewerkers voor op nieuwe services en functies van Office 365 services. |
| Maak bewaarbeleid voor de hele organisatie [om](https://docs.microsoft.com/microsoft-365/compliance/retention) te beschermen tegen onbedoeld verwijderen van inhoud tijdens de migratie.  |<ul><li>Om ervoor te zorgen dat inhoud niet per ongeluk wordt verwijderd door eindgebruikers tijdens de migratie, kunnen klanten ervoor kiezen om een bewaarbeleid voor de hele organisatie in te stellen. </li><li>Hoewel bewaren niet vereist is, omdat bewaringen die op elk gewenst moment tijdens de migratie worden geplaatst, moeten werken zoals verwacht, is het hebben van een bewaarbeleid een back-upveiligheidsmechanisme. Tegelijkertijd kan een bewaarbeleid niet door alle klanten worden gebruikt, met name niet door klanten die zich zorgen maken over bewaring.</li></ul>| Bewaarbeleid toepassen zoals beschreven in [Meer informatie over bewaarbeleid en bewaarlabels.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Fouten van de service- of clientsoftware kunnen optreden als dit niet vóór fase 4 van 9 gebeurt. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>DNS-vermeldingen voor aangepaste domeinen

<!-- before phase 9 -->

**Is van toepassing** op : Klanten die een aangepaste _msoid_ CNAME hebben ingesteld in hun eigen DNS-domein of een domein voor Exchange Online

Indien geconfigureerd, is _de msoid_ CNAME alleen van invloed op klanten die Office Desktopclient (Microsoft 365-apps, Office 365 ProPlus, Office 2019, 2016, ...).

Als u een DNS CNAME met de naam _msoid_ hebt ingesteld in een of meer DNS-naamruimten die u bezit, moet u de CNAME uiterlijk tot het einde van fase 8 verwijderen. U kunt de _CNAME-msoid op elk_ moment vóór het einde van fase 8 verwijderen.

Als u wilt controleren of u een CNAME hebt ingesteld in uw DNS-naamruimte, volgt u de onderstaande _stappen_ en vervangt u contoso.com door uw eigen domeinnaam:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Als de opdrachtregel een DNS-record retourneert, verwijdert u _de msoid_ CNAME uit uw domein.

> [!NOTE]
> Als u een aangepast domein voor Exchange Online gebruikt, moet u toegang hebben tot uw DNS-hostingprovider. Zorg ervoor dat u uw DNS-instellingen kunt openen en bewerken. Tijdens de migratie wijzigt u DNS-records.

## <a name="office-apps"></a>Office Apps

**Is van toepassing** op : Klanten die Office apps gebruiken, met name op Windows clients <br>
**Wanneer toegepast:** Op elk moment voordat fase 9 begint

Office 365 tenants die overstappen op de regio 'Duitsland' moeten alle gebruikers sluiten, zich bij Office 365 en weer aanmelden voor alle Office-bureaubladtoepassingen (Word, Excel, PowerPoint, Outlook, enzovoort) en OneDrive voor Bedrijven-client nadat de tenantmigratie fase 9 heeft bereikt. Door u af te melden en aan te melden, kunnen Office nieuwe verificatietokens verkrijgen bij de globale Azure AD-service.

Dit is vereist voor alle clients. Om ervoor te zorgen dat de migratie soepel verloopt, wordt ten zeerste aangeraden alle betrokken gebruikers vooraf en in een vroeg stadium te informeren en in te delen over deze aanstaande activiteit.

Klanten met beheerde Windows klanten kunnen Windows voorbereiden met [Office Client Cutover Tool (OCCT).](https://github.com/microsoft/OCCT) De OCCT is ontworpen om regelmatig op Windows clients uit te voeren totdat de tenant fase 9 van de migratie heeft bereikt. Wanneer fase 9 is bereikt, voert het OCCT alle benodigde wijzigingen op de computer automatisch uit zonder tussenkomst van de gebruiker.

De OCCT kan op elk moment vóór fase 9 Windows clients worden geïmplementeerd. Als de OCCT de migratie-ervaring ondersteunt, raden we u aan de implementatie zo snel mogelijk te starten om een maximum aantal clients toe te rusten.

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)

<!-- before phase 4 -->

**Is van toepassing op**: Klanten die AD FS on-premises gebruiken om gebruikers te verifiëren die verbinding maken met Microsoft Office 365<br>
**Wanneer toegepast:** Op elk moment voordat fase 4 begint

De stappen voor [ADFS-migratie lezen en toepassen](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Van toepassing op**: Klanten die SharePoint on-premises 2013 gebruiken<br>
**Wanneer toegepast:** Op elk moment voordat fase 4 begint

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Beperk SharePoint 2013-werkstromen, die worden gebruikt tijdens de SharePoint Online-migratie. | Verminder SharePoint 2013-werkstromen en voltooi werkstromen tijdens de vlucht vóór overgangen. | Actie kan leiden tot verwarring bij gebruikers en helpdeskgesprekken. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Van toepassing op**: Exchange Online klanten<br>
**Wanneer toegepast**: Op elk moment vóór het einde van fase 9

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Informeer externe partners over de aanstaande overgang naar Office 365 services. |  Klanten moeten hun partners op de hoogte stellen met wie ze de configuratie van de gedeelde agenda en beschikbaarheidsadresruimte hebben ingeschakeld (het delen van gratis/drukke informatie met Office 365). Beschikbaarheidsconfiguratie moet overstappen om de Office 365 [eindpunten](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) te gebruiken wanneer Exchange Online migratie is voltooid. | Als u dit niet doet, kan dit leiden tot een service- of clientfout in een latere fase van de klantmigratie. |
| Gebruikers op de hoogte stellen van vereiste wijzigingen in de IMAP4/POP3/SMTP-client. | Gebruikers die apparaatverbindingen hebben met Microsoft Cloud Deutschland-eindpunten voor clientprotocollen IMAP4, POP3, SMTP, moeten hun clientapparaten handmatig bijwerken om over te schakelen naar de [Exchange Online servernamen.](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes) | Communiceer deze afhankelijkheid vooraf aan gebruikers van deze protocollen en zorg ervoor dat ze tijdens deze migratie overstappen op Outlook of Outlook op internet. Het niet bijwerken van client-eindpunten resulteert in fouten in de clientverbinding met Microsoft Cloud Deutschland wanneer gebruikerspostvakken worden gemigreerd. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online Hybride klanten

**Van toepassing op:** Alle klanten die een actieve Exchange hybride configuratie met Exchange servers on-premises<br>
**Wanneer toegepast:** Op elk moment voordat fase 5 wordt gestart

Enterprise-klanten met een hybride implementatie van Exchange Online en een on-premises Exchange Server voeren de wizard Hybride configuratie (HCW) en AAD Verbinding maken uit om de hybride configuratie te onderhouden en tot stand te brengen. Exchange Online Hybride beheerders moeten **de wizard Hybride configuratie (HCW)** meerdere keren uitvoeren als onderdeel van deze overgang. Wanneer de beheerder overstapt van Microsoft Cloud Deutschland naar de regio Office 365 Duitsland, moet de beheerder de nieuwste build van HCW opnieuw uitvoeren in de modus 'Office 365 Germany' voordat de Exchange-migratie (fase 5) begint. Voer vervolgens de HCW opnieuw uit in de modus 'Office 365 Worldwide' na voltooiing van fase 5 om de on-premises implementatie te voltooien met de regio-instellingen Office 365 Duitsland. De HCW-uitvoering mag niet worden uitgevoerd tijdens fase 5, het is belangrijk om de HCW pas uit te voeren als fase 5 is afgelopen.
Adreslijstkenmerken worden gesynchroniseerd tussen Office 365 en Azure AD met de on-premises implementatie via AAD-Verbinding maken. 

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| HCW opnieuw uitvoeren met Office 365 Duitsland-instellingen <br><br> <i>U kunt deze activiteit direct starten nadat u de melding van het berichtencentrum hebt ontvangen dat Office 365 tenantmigratie is gestart (fase 1).</i>| Het verwijderen en opnieuw uitvoeren van HCW (17.0.5378.0 of hoger) van vóór fase 5 zorgt ervoor dat uw on-premises configuratie is voorbereid om e-mail te verzenden en te ontvangen met zowel Microsoft Cloud Deutschland-gebruikers als gebruikers die zijn gemigreerd naar [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Duitsland. <p><li> Selecteer in de HCW voor de keuzelijst onder Mijn **Office 365** organisatie gehost door , Office 365 **Duitsland.** | Als u deze taak niet voltooit voordat fase 5 [Exchange migratie] begint, kan dit leiden tot NR's voor e-mail die wordt gerouteerd tussen uw on-premises Exchange implementatie en Office 365.  
| Instellingen voor gedeeld postvak behouden | Sommige hybride klanten hebben postvakken van cloudgebruikers geconverteerd naar gedeelde postvakken met Exchange Online opdrachten. Deze configuratie van het cloudpostvak wordt naar het postvak en de lokale Exchange Online-adreslijst geschreven, maar wordt niet terug gesynchroniseerd naar de Active Directory van de klant via AAD-Verbinding maken. Het resultaat is een verschil tussen de Active Directory-weergave van de waarden RemoteRecipientType en RemoteDisplayType van het postvak en die in Exchange Online het postvak definiëren als gedeeld. <br><br> De klant is verantwoordelijk om ervoor te zorgen dat alle gedeelde postvakken correct zijn ingericht met `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` , of `Set-RemoteMailbox -Shared` .  Zie deze verwijzing voor het converteren van het postvak van een gebruiker [in een hybride omgeving.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)| Als deze taak niet vóór fase 5 [Exchange Online migratie] wordt voltooid, kan dit leiden tot NR's voor gedeelde postvakken die worden ge converteren naar postvakken zonder vergunning en het verlies van gedeelde toegang voor de betreffende postvakken. [Gedeelde postvakken](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) worden onverwacht geconverteerd naar gebruikerspostvakken nadat adreslijstsynchronisatie is uitgevoerd in een hybride implementatie van Exchange, wordt de impact van het niet oplossen van dit probleem beschreven voordat de migratie Exchange Online voltooid.  
||||

## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

<!-- before phase 7 -->

**Van toepassing op**: Skype Voor Bedrijven Online-klanten<br>
**Wanneer toegepast:** Op elk moment voordat fase 7 begint

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Implementeer Teams desktopclient voor gebruikers die toegang hebben tot Skype voor Bedrijven in Duitsland. | Migratie verplaatst Skype voor Bedrijven gebruikers naar Microsoft Teams voor samenwerking, bellen en chatten. Implementeer de bureaubladclient Microsoft Teams of zorg ervoor dat er een ondersteunde browser beschikbaar is. | Inactiviteit resulteert in het niet beschikbaar zijn van Microsoft Teams samenwerkingsservices. |
| Controleer en bereid u voor op migratiegerelateerde DNS-wijzigingen. | Dns-zonewijzigingen van klanten voor Skype voor Bedrijven Online. |<ul><li>U wordt aangeraden de Time-to-Live (TTL) voor dns-records van een klant bij te werken tot 5 minuten om het vernieuwen van DNS-records te versnellen. De door Microsoft beheerde cutover die aan deze DNS-wijziging is gekoppeld, kan echter op elk gewenst moment plaatsvinden binnen het opgegeven wijzigingsvenster van 24 uur. </li><li>Serviceonderbreking is mogelijk in de toekomst. Gebruikers kunnen zich niet aanmelden bij Skype voor Bedrijven en worden omgeleid naar de gemigreerde Teams in de Office 365 services. </li></ul>|
| Bereid training en gereedheid voor eindgebruikers en beheer voor op de overgang naar Microsoft Teams. | Wees succesvol in de overgang van Skype naar Teams door communicatie en gereedheid van de gebruiker te plannen. | <ul><li>Klanten moeten op de hoogte zijn van de nieuwe services en hoe ze deze kunnen gebruiken wanneer hun services zijn overgestappen naar de Office 365 services. </li><li>Nadat DNS-wijzigingen zijn aangebracht voor zowel de klant vanity-domeinen als het oorspronkelijke domein, melden gebruikers zich aan bij Skype voor Bedrijven en zien ze dat ze nu worden gemigreerd naar Teams. Hiermee wordt ook de bureaubladclient gedownload voor Teams op de achtergrond. </li></ul>|
||||

## <a name="mobile-device-management"></a>Mobile Device Management

<!-- before phase 5 -->
**Van toepassing op:** Klanten die een MDM-oplossing (Mobile Device Management) van derden gebruiken<br>
**Wanneer toegepast:** Op elk moment voordat fase 5 begint

| Stap(en) | Omschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bereid training voor eindgebruikers en beheer voor over gebruikers die hun account verwijderen en opnieuw toevoegen aan Microsoft-Outlook voor iOS en Android. | Microsoft Outlook voor iOS- en Android-accounts die zijn geconfigureerd met postvakken in Microsoft Cloud Deutschland, moeten mogelijk worden verwijderd en opnieuw aan Outlook worden toegevoegd om de configuratie van de nieuwe Office 365-services correct te synchroniseren. | Microsoft Outlook voor iOS- en Android-klanten | Outlook postvakken die eerder zijn geconfigureerd voor Microsoft Cloud Deutschland, worden mogelijk niet de nieuwe Office 365 Services-configuratie opgehaald, wat leidt tot fouten en slechtere prestaties van andere gebruikerservaringen. IT-beheerders worden aangeraden documentatie te verstrekken die gebruikers proactief instrueert hun accounts te verwijderen en opnieuw toe te voegen aan Microsoft Outlook voor iOS en Android als er problemen optreden met het aanmelden of synchroniseren van e-mail na de migratie. |
| Bepaal of een herconfiguratie vereist is na de migratie. | MDM-oplossingen (Mobile Device Management) kunnen `outlook.de` eindpunten targeten. In deze overgang naar Office 365 Services moeten clientprofielen worden bijgewerkt naar de URL Office 365 services, `outlook.office365.com` . | Exchange Online en MDM-klanten | Clients kunnen blijven functioneren terwijl het eindpunt toegankelijk is, maar ze mislukken als `outlook.de` Microsoft Cloud Deutschland-eindpunten niet meer beschikbaar zijn. |
|||||

## <a name="line-of-business-apps"></a>Line-of-business-apps

**Van toepassing op:** Klanten die lob-apps (Line-of-Business) gebruiken met eindpunten die worden geleverd door Microsoft Cloud Deutschland<br>
**Wanneer toegepast**: Na voltooiing van fase 2 en vóór einde van fase 9

Als u een service van derden gebruikt of LOB-apps (line-of-business) die zijn geïntegreerd met Office 365, moet u eventuele afhankelijkheden van eindpunten oplossen die worden geleverd door het exemplaar microsoft Cloud Deutschland. Als uw LOB-apps bijvoorbeeld verbinding maken met , moet u `https://graph.microsoft.de/` het eindpunt wijzigen in `https://graph.microsoft.com/` . De eindpunten van de Microsoft Office 365 globale service zijn beschikbaar voor uw tenant na fase 2.

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Bepaal of een herconfiguratie vereist is na de migratie. | Services en toepassingen van derden die zijn geïntegreerd met Office 365 kunnen worden gecodeerd om IP-adressen en URL's van Microsoft Cloud Deutschland te verwachten. | Vereiste actie. Een actie kan leiden tot fouten in de service- of clientsoftware. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Van toepassing op**: Klanten die Microsoft Dynamics 365 gebruiken

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Voor Dynamics 365 sandbox-abonnementen moet u de productieomgeving van het dynamics SQL exemplaar downloaden van uw Dynamics 365-abonnement in Microsoft Cloud Deutschland. De nieuwste productieback-up moet worden hersteld naar de sandbox voordat de sandbox wordt gemigratied. | Voor de migratie van Dynamics 365 moeten klanten ervoor zorgen dat de Sandbox-omgeving wordt vernieuwd met de nieuwste productiedatabase. | Het FastTrack-team helpt klanten bij het uitvoeren van dry runs om de versie-upgrade te valideren van 8.x naar 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Is van toepassing op**: Klanten die Power BI

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Objecten verwijderen uit Power BI-abonnementen die niet worden gemigreerd van Power BI Microsoft Cloud Deutschland naar Office 365 services. | Migratie van Power BI services vereist actie van de klant om bepaalde artefacten te verwijderen, zoals gegevenssets en dashboards. | <ul><li>Beheerders moeten mogelijk de volgende items uit hun abonnement verwijderen: </li><li>Real-Time gegevenssets (bijvoorbeeld streaming- of pushsets) </li><li>Power BI on-premises Data Gateway-configuratie en -gegevensbron </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Als u dezelfde Azure Active Directory-identiteitspartitie gebruikt voor Office 365 en Microsoft Azure in het exemplaar Microsoft Cloud Deutschland, moet u zich voorbereiden op de klantgestuurde migratie van Microsoft Azure-services.

> [!NOTE]
> De migratie van uw Microsoft Azure-services mag niet worden gestart voordat uw Office 365 tenant migratiefase 3 heeft bereikt en moet zijn voltooid voordat migratiefase 8 is voltooid.

Klanten die Office 365 en Azure-resources (bijvoorbeeld netwerken, berekeningen en opslag) gebruiken, voeren de migratie van resources uit naar het Office 365 services-exemplaar. Deze migratie is de verantwoordelijkheid van de klant. Berichten in het Berichtencentrum geven het startsignaal. De migratie moet zijn voltooid voordat de Azure AD-organisatie in de Office 365 is voltooid. Voor Azure-migraties, zie de Azure-migratie playbook, [Overzicht van migratie-richtlijnen voor Azure Germany.](https://docs.microsoft.com/azure/germany/germany-migration-main)

| Stap(en) | Omschrijving | Gevolg |
|:-------|:-------|:-------|
| Bepaal welke Azure-services worden gebruikt en bereid u voor op toekomstige migratie van Duitsland naar de Office 365 services tenant door samen te werken met uw partners. Volg de stappen die worden beschreven in de [Azure-migratie playbook](/azure/germany/germany-migration-main). |<ul><li>Migratie van Azure-resources is een verantwoordelijkheid van de klant en vereist handmatige inspanning volgens de voorgeschreven stappen. Inzicht in de services die in de organisatie worden gebruikt, is essentieel voor een succesvolle migratie van Azure-services. </li><li> Office 365 Klanten in Duitsland die Azure-abonnementen hebben onder dezelfde identiteitspartitie (organisatie) moeten de door Microsoft voorgeschreven volgorde volgen wanneer ze kunnen beginnen met de migratie van abonnementen en services.</li></ul>|<ul><li>Klanten hebben mogelijk meerdere Azure-abonnementen, elk abonnement met infrastructuur, services en platformonderdelen. </li><li> Beheerders moeten abonnementen en belanghebbenden identificeren om ervoor te zorgen dat snelle migratie en validatie mogelijk is als onderdeel van deze migratiegebeurtenis. </li><li>Als de migratie van deze abonnementen en Azure-onderdelen binnen de voorgeschreven tijdlijn niet is voltooid, is dit van invloed op de voltooiing van de Office- en Azure AD-overgang naar Office 365-services en kan dit leiden tot gegevensverlies. </li><li> Een berichtcentrummelding geeft aan op welk punt de migratie door de klant kan beginnen. </li></ul>|
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

- [Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Power BI migratieprogrammagegevens](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams upgrade](/microsoftteams/upgrade-start-here)
