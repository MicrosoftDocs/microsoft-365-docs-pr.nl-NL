---
title: Acties en effecten bij migratie fasen
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
description: 'Overzicht: algemene informatie over de migratie fasen en effecten van overstappen van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 9ffdb0bbe60bdb96d6e110ac08cba4030272c7e9
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551655"
---
# <a name="migration-phases-actions-and-impacts"></a>Acties en effecten bij migratie fasen

Tenant migraties van Microsoft Cloud Deutschland naar de Duitse regio van de Office 365-services van Microsoft worden als een reeks geconfigureerde acties uitgevoerd voor elke werkbelasting. Met deze acties zorgt u ervoor dat cruciale gegevens en ervaringen worden gemigreerd naar de Office 365-Services. Nadat u de Tenant hebt toegevoegd aan de migratie wachtrij, wordt elke werkbelasting voltooid als een reeks stappen die worden uitgevoerd op de backend-service. Voor sommige belastingen zijn mogelijk acties vereist door de beheerder (of gebruiker), of de migratie kan van invloed zijn op het gebruik voor de fasen die worden uitgevoerd en besproken in [de manier waarop de migratie wordt georganiseerd.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

De volgende secties bevatten acties en effecten voor werkbelastingen wanneer ze worden uitgevoerd in verschillende fasen van de migratie. Bekijk de tabellen en bepaal welke acties of effecten van toepassing zijn op uw organisatie. Zorg ervoor dat u ervoor hebt gezorgd dat u de stappen in de juiste fasen gaat uitvoeren. Als u de noodzakelijke stappen niet kunt voltooien, kunnen de service storing oplopen en kan de migratie naar Office 365-Services vertraging veroorzaken.

## <a name="exchange-online"></a>Exchange Online

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Nieuwe Duitse regio wordt toegevoegd aan de bestaande organisatie-instelling, en postvakken worden verplaatst naar Office 365-Services. | Exchange Online-configuratie voegt de nieuwe Go-Local Duitse regio toe aan de overgangs organisatie. Deze regio van Office 365-Services wordt ingesteld als standaard, zodat de interne taakverdelingsservice postvakken opnieuw kan distribueren naar het juiste standaardgebied in Office 365-Services. In deze overgang bevinden gebruikers aan de kant (Duitsland of Office 365-Services) zich in dezelfde organisatie en kunnen beide URL-eindpunten gebruiken. | Exchange Online | -Migreer gebruikers en services van Duitsland Url's naar Office 365-Services Url's ( `https://outlook.office365.com` ). <br><br> -Gebruikers blijven de service via oudere Duitsland-Url's tijdens de migratie verder raadplegen. U hoeft geen directe actie te ondernemen. <br><br> -Gebruikers moeten beginnen met de functies office.com Portal for Office Online (agenda, E-mail, personen). Navigatie naar services die nog niet zijn gemigreerd naar Office 365-Services, werkt pas na migratie. <br><br> -Outlook Web App biedt geen ondersteuning voor het maken van openbare mappen tijdens migraties. |
|||||

Als u meer wilt weten over de verschillen voor organisaties in migratie en nadat Exchange Online-bronnen zijn gemigreerd, bekijkt u de informatie in de gebruikers [ervaring tijdens de migratie naar Office 365-Services in de nieuwe Duitse datacenter regio's](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Exchange Online Protection

De back-end Exchange Online Protection (EOP)-functies worden gekopieerd naar de nieuwe Duitse regio. 

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Exchange Online Routering en historisch berichtdetail. | Met Exchange Online kunt u de routering van externe hosts naar Office 365. De externe MX-records worden overgezet naar routering naar de EOP-service. Tenant configuratie en historische gegevens worden gemigreerd. | Exchange Online-klanten | -Microsoft – beheerde DNS-vermeldingen worden bijgewerkt van Office 365 Duitsland EOP naar Office 365-Services. <br><br> -Klanten moeten dertig dagen na EOP Dual write voor EOP-migratie wachten. Anders zijn er mogelijk verlies van gegevens. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

<!--

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| SharePoint and OneDrive are transitioned. | SharePoint and OneDrive are migrated from Microsoft Cloud Deutschland to Office 365 services in this phase. Existing Microsoft Cloud Deutschland URLs are preserved (for example, `contoso.sharepoint.de`). Tokens that were issued by Microsoft Cloud Deutschland or Office 365 services are valid during the transition. | SharePoint customers | - Content will be read-only for two brief periods (less than x minutes) during migration. During this time, expect a "you can't edit content" banner in SharePoint. <br><br> - The search index won't be preserved, and may take up to 10 days to be rebuilt. <br><br> - SharePoint/OneDrive content will be read-only for two brief periods (less than x minutes) during migration. Users will see a "you can't edit content" banner briefly during this time. <br><br> - The search index may be unavailable while the index is rebuilt. During this period, search queries might not return complete results. <br><br> - Existing sites are preserved. |
|||||

--> 

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| SharePoint en OneDrive worden doorgeschakeld. | SharePoint en OneDrive worden gemigreerd van Microsoft Cloud Deutschland naar Office 365-Services in deze fase. Bestaande Url's voor Microsoft Cloud Deutschland blijven behouden (bijvoorbeeld `contoso.sharepoint.de` ). Tokens die zijn uitgegeven door Microsoft Cloud Deutschland of Office 365-Services, zijn geldig tijdens de overgang. | SharePoint-klanten | -De inhoud is gedurende twee korte perioden tijdens de migratie alleen-lezen. U krijgt een melding dat u tijdens deze periode de banner ' u kunt de inhoud niet bewerken ' kunt verwachten in SharePoint. <br><br> -De zoekindex wordt niet bewaard en kan tot 10 dagen duren. <br><br> -SharePoint/OneDrive-inhoud wordt voor twee korte perioden tijdens de migratie alleen-lezen. Gebruikers zien een vaandel met de tekst ' u kunt de banner niet kort bewerken ' tijdens deze periode. <br><br> -De zoekindex is mogelijk niet beschikbaar terwijl de index opnieuw wordt opgebouwd. Tijdens deze periode kunnen zoekquery's geen volledige resultaten opleveren. <br><br> -Bestaande sites blijven behouden. |
|||||


## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Migratie van Skype voor bedrijven naar teams. | Bestaande Skype voor bedrijven-klanten worden gemigreerd naar Office 365-Services in Europa en worden vervolgens overgezet naar Microsoft teams in de Duitse regio van Office 365-Services. | Skype voor bedrijven-klanten | -Gebruikers kunnen zich niet aanmelden bij Skype voor bedrijven op de migratiedatum. Tien dagen voor de migratie melden we eindgebruikers via de band van de Skype voor bedrijven-client waarop ze worden geüpgraded naar teams. In het Beheercentrum wordt ook deze wijzigingen weergegeven na de tien dagen. <br><br> -Beleidsconfiguratie wordt gemigreerd. <br><br> -Gebruikers worden gemigreerd naar teams en zullen na de migratie niet langer Skype voor bedrijven. <br><br> -Voor gebruikers moet de bureaubladtoepassing teams zijn geïnstalleerd. De installatie zal plaatsvinden gedurende de tien dagen via het beleid voor de Skype voor bedrijven-infrastructuur, maar als dit mislukt, moeten gebruikers de client downloaden of verbinding maken met een ondersteunde browser. <br><br> -Contactpersonen en vergaderingen worden gemigreerd naar teams. <br><br> -Gebruikers kunnen zich niet aanmelden bij Skype voor bedrijven tussen tijdsservice overgangen naar Office 365-Services en niet totdat de DNS-gegevens van de klant zijn voltooid. <br><br> -Contactpersonen en bestaande vergaderingen blijven werken als vergaderingen in Skype voor bedrijven. |
|||||
        
## <a name="subscription"></a>Leden

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| We kunnen geen klanten zonder toestemming migreren. | Microsoft verkrijgt het recht om te migreren op een van de volgende twee manieren, zodat Microsoft de overgang van gegevens en services kan overdragen aan het exemplaar van Office 365 Services. <br> De beheerder-inzoomen op de door Microsoft gerichte migratie. <br> Klanten vernieuwen een abonnement op hun Microsoft Cloud Deutschland-Tenant na 1 mei 2020. We sturen u elke maand een melding van deze klanten van de migratie, wacht 30 dagen om klanten een mogelijkheid te bieden een mogelijkheid te bieden om te annuleren en klik vervolgens rechtstreeks aanmelden, bijgehouden in ICM. | Alle Office-klanten | -De Tenant is gemarkeerd als afgestemd op de migratie, en de bevestiging wordt in het Beheercentrum weergegeven. <br><br> -Bevestiging wordt gepubliceerd naar Cloud Duitsland-berichtencentrum Tenant. Service configuratie gaat door van Microsoft Cloud Deutschland-eindpunten. <br><br> -Bewaak berichtencentrum voor updates over de status van de migratie fase. |
| Abonnementen worden overgebracht en licenties worden opnieuw toegewezen. | Nadat de Tenant is overgezet naar Office 365-Services, worden bijbehorende Office 365-Serviceabonnementen aangeschaft voor de overgezette Microsoft Cloud Deutschland-abonnementen. Gebruikers met toegewezen Microsoft Cloud Deutschland-licenties worden toegewezen Office 365-Services-licenties. Oudere Microsoft Cloud Deutschland-abonnementen worden na voltooiing van de Office 365 service-Tenant verwijderd. | Alle Office-klanten | Wijzigingen in bestaande abonnementen worden geblokkeerd (bijvoorbeeld: geen nieuwe abonnements aankopen of het wijzigen van het aantal seats) tijdens deze fase. <br><br> -Wijzigingen van licentietoewijzingen worden geblokkeerd. <br><br> -Het Microsoft Cloud Deutschland-abonnement wordt gemigreerd naar het bijbehorende Office 365 Services-abonnement. De aanbiedingen van dit abonnement voor Office 365 services worden gedefinieerd door Microsoft (ook wel bekend als de _aanbiedings toewijzingen_). <br><br> -Het aantal functies (Serviceabonnementen) dat wordt aangeboden door Office 365-Services kan groter zijn dan de aanbieding in de oorspronkelijke Microsoft Cloud Deutschland. Gebruikerslicenties in Office 365-Services zijn gelijk aan soortgelijke Microsoft Cloud Deutschland-functies (serviceplannen). Gebruikerslicenties voor alle gebruikers worden automatisch toegewezen aan de nieuwe functies. De beheerder moet, indien nodig, expliciete actie ondernemen om deze licenties uit te schakelen. <br><br> -Wanneer de abonnements migratie is voltooid, zijn zowel Office 365-Services als Duitsland-abonnementen zichtbaar in de Office 365-beheer Portal, met de status van Duitsland- _abonnementen._ <br><br> -Gebruikers krijgen opnieuw een licentie toegewezen die zijn gekoppeld aan de nieuwe Office 365-service-abonnementen. Klant processen met afhankelijkheden van Duitsland-abonnementen of SKU-GUID'S worden verbroken en moeten worden herzien met de aanbieding van Office 365 Services. <br><br> -Nieuwe abonnementen in de Office 365-services worden gekocht met de nieuwe periode (per maand/kwartaal) en de klant ontvangt een betaald bedrag voor het ongebruikte saldo van het Microsoft Cloud Deutschland-abonnement. <br><br> -Partners Microsoft Cloud Deutschland-tenants worden niet gemigreerd. CSP-klanten worden gemigreerd naar Office 365-Services onder de nieuwe Office 365 service-Tenant van dezelfde partner. Na de klant migratie kan de partner deze klant alleen beheren vanuit de Office 365 service-Tenant. <br><br> -Er is extra functionaliteit beschikbaar (bijvoorbeeld Microsoft planner en Microsoft flow), tenzij dit door de tenantbeheerder is uitgeschakeld. Voor informatie over het uitschakelen van service-abonnementen die aan gebruikerslicenties zijn toegewezen, raadpleegt [u de toegang tot Microsoft 365-Services uitschakelen terwijl u gebruikerslicenties toewijst](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Volgende stap

[Extra voor werk uitvoeren](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)
- [Gebruikerservaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang navigeren:

- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Services](ms-cloud-germany-transition-add-general.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
