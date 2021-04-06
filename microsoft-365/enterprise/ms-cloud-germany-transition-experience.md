---
title: Wat verandert er na de migratie naar Office 365-services in de nieuwe Duitse datacenterregio's
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Samenvatting: Meer informatie over wat er is veranderd voor de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365-services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 74ad9a662d3ea7a68ef1f82961864eb4468f6098
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591778"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Wat verandert er na de migratie naar Office 365-services in de nieuwe Duitse datacenterregio's

Tenantmigraties zijn zo ontworpen dat ze minimale gevolgen hebben voor beheerders en gebruikers. Er zijn echter overwegingen voor elke werkbelasting. Bekijk de volgende secties om meer inzicht te krijgen in de migratie-ervaring voor de werkbelastingen.

Hieronder volgen de belangrijkste verschillen tussen Microsoft Cloud Deutschland en Office 365-services in de nieuwe Duitse datacenterregio's.

| Categorie | Microsoft Cloud Germany (Microsoft Cloud Deutschland) | Office 365-services in de nieuwe Duitse datacenterregio's |
|:-------|:-----|:-------|
| Microsoft 365-services beschikbaar voor abonnement met slechts één Office 365-tenant | 15 services | 29 services <br><br> Zie Wat is de beschikbaarheid van de service tussen de [verschillende Office 365-cloudserviceaanbiedingen?](ms-cloud-germany-transition.md#serv-avail)voor meer informatie. |
| Nieuwe functies | Er zijn geen nieuwe functies beschikbaar. | Nieuwe functies zijn beschikbaar in overeenstemming met Office 365-services. |
| Gegevensbeheerder | Ja | Nee |
| Samenwerking tussen verschillende tenants met globale Office 365-tenants | Nee | Ja |
| Klantgegevens ingezetenschap | Klantgegevens worden uitsluitend opgeslagen in Duitse datacenters. | Microsoft zal de volgende klantgegevens uitsluitend in Duitsland opslaan: <ul><li> Inhoud van Exchange Online-postvak (e-mail, agenda-items en de inhoud van e-mailbijlagen) </li><li> SharePoint Online-site-inhoud en de bestanden die zijn opgeslagen op die site en bestanden die zijn geüpload naar OneDrive voor Bedrijven </li></ul> |
| Toepasselijke voorwaarden | [Voorwaarden voor onlineservices](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) met deze [aanvulling](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Voorwaarden voor onlineservices](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Microsoft Azure Active Directory

Wat verandert er niet:

- Het eerste domein van tenant (zoals ) met tenant-id (GUID) en aangepaste domeinen blijft `contoso.onmicrosoft.de` bestaan na de migratie. 

- Verificatieaanvragen voor resources die zijn gemigreerd naar Office 365-services worden verleend door de Azure Authentication-service voor Office 365-services ( `login.microsoftonline.com` ). Tijdens de migratie worden resources die nog steeds in Office 365 Duitsland staan, geverifieerd door de bestaande Azure-service van Duitsland ( `login.microsoftonline.de` ).

Aandachtspunten:

- Voor beheerde domeinaccounts is het kopiëren van de eerste Azure Active Directory-tenant (Azure AD) voltooid (de eerste stap van Azure AD-migratie naar de Azure 365-services Azure AD-service), wachtwoordwijzigingen, wijzigingen in selfservicewachtwoord opnieuw instellen (SSPR) en wachtwoordresets door beheerders moeten worden uitgevoerd vanuit de Office 365-serviceportals. Aanvragen om wachtwoorden van de Duitsland-service bij te werken, slagen op dit moment niet, omdat de Azure AD-tenant is gemigreerd naar Office 365-services. Resets van federatief domeinwachtwoorden worden niet beïnvloed, omdat deze worden voltooid in de on-premises adreslijst.

- Azure-aanmeldingen worden weergegeven in de portal waar de gebruiker toegang probeert te krijgen. Auditlogboeken zijn alleen beschikbaar in het Office 365-services-eindpunt na de overgang. Voordat u de migratie doormaakt naar de voltooiing van de migratie, moet u aanmeldings- en auditlogboeken opslaan vanuit de Microsoft Cloud Deutschland-portal.

- Wachtwoordinstellingen, wachtwoordwijzigingen, wachtwoordresets door een beheerder voor beheerde organisaties (die geen Active Directory Federation Services gebruiken) moeten worden uitgevoerd via de Office 365-servicesportal. Pogingen van gebruikers die toegang hebben tot Microsoft Cloud Deutschland-portals om wachtwoorden opnieuw in te stellen, mislukken.

- Algemene verordening gegevensbescherming (AVG) Verzoeken om gegevensonderwerpen (DSR's) worden uitgevoerd vanuit de Azure-beheerportal van Office 365-services voor toekomstige aanvragen. Oudere of niet-klant diagnostische gegevens die in Microsoft Cloud Deutschland zijn opgeslagen, worden na of vóór 30 dagen verwijderd.

## <a name="subscriptions--licenses"></a>Abonnementen & licenties

- Office 365- en Dynamics-abonnementen van Microsoft Cloud Deutschland worden overgeplaatst naar de Duitse regio met de Azure AD-verplaatsing. De organisatie wordt vervolgens bijgewerkt om nieuwe Office 365-servicesabonnementen weer te geven. Tijdens het korte abonnementsoverdrachtsproces worden wijzigingen in abonnementen geblokkeerd.

- Wanneer de tenant wordt overgeleverd aan Office 365-services, worden de Duitsland-specifieke abonnementen en licenties gestandaardiseerd met nieuwe Office 365-services. Corresponderende Office 365-servicesabonnementen worden gekocht voor de overgedragen Duitsland-abonnementen. Gebruikers met Duitsland-licenties krijgen office 365-serviceslicenties toegewezen. Na voltooiing worden oudere Duitsland-abonnementen geannuleerd en verwijderd uit de huidige Office 365-servicesten tenant.

- Na de migratie van de afzonderlijke werkbelastingen wordt extra functionaliteit beschikbaar gesteld via de Office 365-services (zoals Microsoft Planner en Microsoft Flow) vanwege de nieuwe Office 365-servicesabonnementen. Indien van toepassing voor uw organisatie, kan de tenant of licentiebeheerder nieuwe serviceplannen uitschakelen terwijl u van plan bent het wijzigingsbeheer in te voeren voor de nieuwe services. Zie Toegang tot [Microsoft 365-services](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)uitschakelen tijdens het toewijzen van gebruikerslicenties voor informatie over het uitschakelen van serviceplannen die zijn toegewezen aan gebruikerslicenties.

## <a name="exchange-online"></a>Exchange Online

- Exchange-resource-URL's gaan na de migratie over van het oude Eindpunt duitsland naar het `outlook.office.de` Office 365-services-eindpunt. `outlook.office365.com` Uw gebruikers kunnen hun gemigreerde postvak openen met behulp van de oudere URL totdat de migratie is voltooid. Klanten moeten gebruikers zo snel mogelijk overstappen op de nieuwe URL nadat exchange-migratie is gestart om te voorkomen dat de uittreding van de Duitse omgeving wordt beïnvloed. De URL's voor Office 365-services voor Outlook-services zijn alleen beschikbaar nadat de Exchange-migratie is gestart.

- Postvakken worden gemigreerd als back-mailproces. Gebruikers in uw organisatie kunnen tijdens de overgang in Microsoft Cloud Deutschland of de Duitse regio zijn en maken deel uit van dezelfde Exchange-organisatie (in dezelfde algemene adreslijst).

- Gebruikers van de Outlook Web App die toegang hebben tot de service met behulp van een URL waar hun postvak zich niet bevindt, krijgen een extra verificatieprompt te zien. Als het postvak van de gebruiker zich bijvoorbeeld in de Office 365-services en de Outlook Web App-verbinding van de gebruiker het oudere eindpunt gebruikt, wordt de gebruiker eerst geverifieerd bij en vervolgens bij `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` . Wanneer de migratie is voltooid, heeft de gebruiker toegang tot de nieuwe URL ( ) en ziet hij of zij alleen de enige, verwachte `https://outlook.office365.com` aanmeldingsaanvraag. 

## <a name="office-services"></a>Office Services

Office Online-services zijn toegankelijk via `office.de` voor en tijdens de overgang. Nadat de postvakken van gebruikers zijn overgestappen naar de Office 365-services, moeten gebruikers URL's voor Office 365-services gaan gebruiken. Wanneer de volgende werkbelastingen worden gemigreerd naar Office 365-services, werkt de interface van de office.com portal.

De meest recent gebruikte (MRU) service in Office is een cutover van de Microsoft Cloud Deutschland naar Office 365 Global Services, niet een migratie. Alleen MRU-koppelingen van de kant globale services van Office 365 zijn zichtbaar na de migratie vanuit de Office.com portal. MRU-koppelingen vanuit de Microsoft Cloud Deutschland zijn niet zichtbaar als MRU-koppelingen in Office 365 Global Services. In Globale Office 365-services zijn MRU-koppelingen alleen toegankelijk nadat de tenantmigratie fase 9 heeft bereikt.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Back-end EOP-functies (Exchange Online Protection) worden gekopieerd naar de nieuwe regio Duitsland.
- Gebruikers van het Office 365-beveiligings- en compliancecentrum moeten overstappen op het gebruik van algemene URL's, als onderdeel `https://protection.office.com` van de migratie.

## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

Bestaande klanten van Skype voor Bedrijven Online gaan overstappen op Microsoft Teams. Zie [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video wordt op 1 maart 2021 buiten gebruik genomen en Office 365 Video wordt niet ondersteund nadat de migratie van SharePoint Online naar de nieuwe Duitse datacenterregio's is voltooid. Inhoud van Office 365 Video wordt gemigreerd als onderdeel van de migratie van SharePoint Online. Video's in Office 365 Video worden echter niet meer afspelen in de Gebruikersinterface van Office 365 Video na de SharePoint-migratie. Meer informatie over de migratietijdlijn in [De overgang van Office 365 Video naar Microsoft Stream (klassiek) overzicht.](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Volgende stap

[Acties en effecten van migratiefasen begrijpen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Informatie over power bi-migratieprogramma's](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams-upgrade](/microsoftteams/upgrade-start-here)
