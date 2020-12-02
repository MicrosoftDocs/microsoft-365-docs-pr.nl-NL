---
title: Gebruikerservaring tijdens de migratie naar Office 365-Services in de nieuwe Duitse datacenter gebieden
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Overzicht: informatie over het overstappen van overstappen van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551693"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Gebruikerservaring tijdens de migratie naar Office 365-Services in de nieuwe Duitse datacenter gebieden

Tenant migraties zijn ontworpen om beheerders en gebruikers het minimum te bieden. Er zijn echter wel enkele aandachtspunten voor elke werkbelasting. Lees de volgende secties voor een beter begrip van de migratie ervaring voor de werkbelasting.

Hieronder staan de belangrijkste verschillen tussen Microsoft Cloud Deutschland en Office 365-Services in de nieuwe Duitse datacenter-regio's.

| Categorie | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | Office 365-Services in de nieuwe Duitse datacenter regio's |
|:-------|:-----|:-------|
| Microsoft 365-services beschikbaar voor abonnementen met maar één Office 365-Tenant | 15 Services | 29 Services <br><br> Voor meer informatie raadpleegt u de [beschikbaarheid van de service voor de verschillende Office 365-cloudservice aanbiedingen?](ms-cloud-germany-transition.md#serv-avail). |
| Nieuwe functies | Er zijn geen nieuwe functies beschikbaar. | De nieuwe functies zijn consistent met Office 365-Services. |
| Gegevensbeheerder | Ja | Nee |
| Samenwerking tussen tenants en wereldwijde Office 365-tenants | Nee | Ja |
| Woonplaats voor klantgegevens | Klantgegevens worden uitsluitend opgeslagen in een Duitse datacenter. | Microsoft zal de volgende gegevens van de klant bewaren, exclusief de rest van Duitsland: <ul><li> Postvak inhoud van Exchange Online (e-mail tekst, agenda-items en de inhoud van e-mailbijlagen) </li><li> Site-inhoud van SharePoint Online en de bestanden die zijn opgeslagen op deze site, en bestanden die zijn geüpload naar OneDrive voor bedrijven </li></ul> |
| Toepasselijke voorwaarden | [Online Servicevoorwaarden](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) met deze [aanvulling](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Online Servicevoorwaarden](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Microsoft Azure Active Directory

Niets wijzigen:

- Het eerste domein van de Tenant (zoals `contoso.onmicrosoft.de` ) met Tenant-id (GUID) en aangepaste domeinen blijven na de migratie behouden. 

- Verificatieaanvragen voor bronnen die worden gemigreerd naar Office 365-Services, worden verleend door de service Office 365 service Azure Authentication Service ( `login.microsoftonline.com` ). De resources die nog steeds in Office 365 Duitsland blijven, worden tijdens de migratie geverifieerd door de bestaande Duitsland Azure-service ( `login.microsoftonline.de` ).

Aandachtspunten:

- Wanneer de eerste Azure Active Directory (Azure AD)-Tenant is gekopieerd, wordt de account gewijzigd in het dialoog programma Office 365 Services Azure AD service, wordt het wachtwoord gewijzigd en worden de instellingen voor het zelf opnieuw instellen van wachtwoorden (SSPR) van de Office 365-service portals uitgevoerd. Aanvragen voor het bijwerken van wachtwoorden van de Duitse service zijn op dit moment niet mogelijk, omdat de Azure AD-Tenant is gemigreerd naar Office 365-Services. Het opnieuw instellen van federatieve domeinwachtwoorden heeft geen gevolgen omdat deze zijn voltooid in de on-premises adreslijst.

- Azure-aanmeld invoegtoepassingen worden weergegeven in de portal waartoe de gebruiker toegang wil hebben. Controlelogboeken zijn beschikbaar vanaf het Office 365 service-eindpunt na overgang. Voordat u na migratie verdergaat, moet u zich aanmelden en auditlogboeken opslaan via de portal van Microsoft Cloud Deutschland.

- Wachtwoorden opnieuw instellen, wachtwoorden wijzigen, wachtwoorden opnieuw instellen door een beheerder voor beheerde organisaties (die geen gebruikmaakt van Active Directory Federation Services) moet worden uitgevoerd via de Office 365 Services-portal. Pogingen van gebruikers die toegang hebben tot de Microsoft Cloud Deutschland portals kunnen geen wachtwoorden opnieuw instellen.

- De algemene verordening gegevensbescherming (AVG) data subject requests (DSRs) worden uitgevoerd vanuit de Office 365 Services Azure-beheerportal voor toekomstige aanvragen. Verouderde of niet-klant diagnostische gegevens die ingezetene zijn van Microsoft Cloud Deutschland, worden op of vóór 30 dagen verwijderd.

## <a name="subscriptions--licenses"></a>Abonnementen & licenties

- Office 365 en Dynamics-abonnementen van Microsoft Cloud Deutschland worden overgezet naar de Duitse regio met de Azure AD-herplaatste. Vervolgens worden de nieuwe Office 365-service-abonnementen weergegeven. Bij een kort proces voor het verzenden van een abonnement worden wijzigingen in abonnementen geblokkeerd.

- Aangezien de Tenant wordt overgezet naar Office 365-Services, zijn de bijbehorende Duitsland-specifieke abonnementen en licenties standaard genormaliseerd met nieuwe aanbiedingen van Office 365-Services. Corresponderende Office 365-service-abonnementen worden aangeschaft voor de overgezete Duitsland-abonnementen. Gebruikers met een Duitsland-licentie worden de licenties voor Office 365-services toegewezen. Na voltooiing worden oudere Duitsland-abonnementen opgezegd en verwijderd van de huidige Office 365 Services-Tenant.

- Na de migratie van de afzonderlijke belastingen wordt er extra functionaliteit beschikbaar via de Office 365-Services (zoals Microsoft planner en Microsoft flow) vanwege de nieuwe Office 365-Services-abonnementen. Als dit van toepassing is op uw organisatie, kan de beheerder van de Tenant of de licentieverlening nieuwe serviceplannen uitschakelen wanneer u gaat wijzigen voor wijzigingsbeheer om de nieuwe services te introduceren. Voor informatie over het uitschakelen van service-abonnementen die aan gebruikerslicenties zijn toegewezen, raadpleegt [u de toegang tot Microsoft 365-Services uitschakelen terwijl u gebruikerslicenties toewijst](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- Exchange Resource-Url's overstappen van het oude Duitsland-eindpunt `outlook.office.de` naar het Office 365 service-eindpunt `outlook.office365.com` na de migratie. Uw gebruikers hebben toegang tot hun gemigreerde postvak via de oudere URL totdat de migratie is voltooid. Klanten moeten gebruikers zo snel mogelijk overzetten na een Exchange-migratie, zodat dit geen invloed heeft op de beëindiging van de Duitse omgeving. De Url's van Office 365-Services voor Outlook services worden pas beschikbaar nadat Exchange-migratie is gestart.

- Postvakken worden gemigreerd als een back-upproces. Gebruikers in uw organisatie kunnen zich mogelijk in Microsoft Cloud Deutschland of in het Duitse gebied tijdens de overgang bevinden en maken deel uit van dezelfde Exchange-organisatie (in dezelfde algemene adreslijst).

- Gebruikers van de Outlook Web app die toegang krijgen tot de service via een URL waar hun postvak niet wordt weergegeven, zien een extra verificatie prompt. Als het postvak van de gebruiker bijvoorbeeld in Office 365-Services is en de Outlook Web App-verbinding van de gebruiker gebruikmaakt van het oude eindpunt `outlook.office.de` , wordt de gebruiker eerst geverifieerd `login.microsoftonline.de` en vervolgens aan `login.microsoftonline.com` . Wanneer de migratie is voltooid, heeft de gebruiker toegang tot de nieuwe URL ( `https://outlook.office365.com` ) en worden alleen de aanmeldingsaanvraag voor één keer weergegeven. 

## <a name="office-services"></a>Office-services

Office Online-Services zijn beschikbaar via `office.de` voor en tijdens de overgang. Wanneer gebruikerspostvakken overstappen naar Office 365-Services, moeten gebruikers hun Url's van Office 365 Services gaan gebruiken. Wanneer volgende belastingen worden gemigreerd naar Office 365-Services, begint de interface van de portal van office.com naar werken.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- De back-end Exchange Online Protection (EOP)-functies worden gekopieerd naar de nieuwe Duitse regio.
- Gebruikers van Office 365 beveiliging en compliance Center moeten gebruikers overstappen op het gebruik van globale Url's, `https://protection.office.com` als onderdeel van de migratie.

## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

Bestaande Skype voor bedrijven online-klanten zullen overstappen op Microsoft teams. Zie voor meer informatie [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Video van Office 365 wordt buiten de kant 1, 2021 en de video van Office 365 buiten gebruik gesteld na de migratie van SharePoint Online naar de nieuwe Duitse datacenter regio's. Inhoud van Office 365 video wordt gemigreerd als onderdeel van het migreren van SharePoint Online. Video's in Office 365 video worden echter niet afgespeeld in de GEBRUIKERSINTERFACE van Office 365 voor Video's na de SharePoint-migratie. Meer informatie over de migratie tijdlijn van [Office 365 video overgang naar Microsoft stream (klassiek)-overzicht](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Volgende stap

[Meer informatie over de acties en effecten voor migratie fasen](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)

Door de overgang navigeren:

- [Acties en effecten bij migratie fasen](ms-cloud-germany-transition-phases.md)
- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Services](ms-cloud-germany-transition-add-general.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
