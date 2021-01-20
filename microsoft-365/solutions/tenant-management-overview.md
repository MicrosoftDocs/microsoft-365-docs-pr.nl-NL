---
title: Pachtersbeheer voor Microsoft 365 for Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Een overzicht van de planning, implementatie en voortdurende werking van uw Microsoft 365-tenants.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908532"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Pachtersbeheer voor Microsoft 365 for Enterprise

Als u een pad naar de digitale transformatie van uw organisatie wilt maken met Cloud Computing, hebt u een firma Foundation nodig waarop uw werknemers kunnen vertrouwen voor productiviteit, samenwerking, prestaties, privacy, compliance en beveiliging.

De juiste configuratie van uw Microsoft 365-tenants biedt deze basis, zodat uw medewerkers zich richten op het verkrijgen van het werk en de IT-afdeling om zich te richten op de end-to-end-oplossingen die een extra zakelijke waarde bieden. 

Met deze oplossing gaat u door de configuratie van deze basisstappen:

1. Uw tenants bepalen
2. Optimaliseer uw netwerk
3. Uw identiteiten synchroniseren en beveiligde aanmeld modules afdwingen
4. Uw Windows-apparaten, Office-clients en on-premises Office-servers en-gegevens migreren
5. Apparaten en app-beheer implementeren

Laten we eerst eens kijken wat een Tenant is en welke een Tenant met een bedrijfs Stichting eruit ziet.

## <a name="a-microsoft-365-tenant-defined"></a>Een Microsoft 365-Tenant gedefinieerd

Een Microsoft 365-Tenant is een speciaal exemplaar van de services van Microsoft 365 en de gegevens in uw organisatie die zijn opgeslagen in een specifieke standaardlocatie, zoals Europe of Noord-Amerika. Dit is de locatie die u hebt opgegeven bij het maken van de Tenant voor uw organisatie. Elke Microsoft 365-Tenant is DISTINCT, Unique en los van alle andere Microsoft 365-tenants. U maakt een Microsoft 365-Tenant wanneer u een of meer producten koopt bij Microsoft, zoals Microsoft 365 E3 of E5, en een set licenties voor elk product.

Uw Microsoft 365-Tenant bevat ook een Azure Active Directory-Tenant (Azure AD), een toegewezen exemplaar van Azure AD voor gebruikersaccounts, groepen en andere objecten. Elke Azure AD-Tenant is DISTINCT, Unique en los van alle andere Azure AD-tenants. U kunt in uw organisatie meerdere Azure AD-tenants maken die u kunt instellen met Azure-abonnementen, maar Microsoft 365-tenants kunnen slechts één Azure AD-Tenant gebruiken, de naam die is gemaakt toen u de Tenant maakte. 

Hier ziet u een voorbeeld:

![Een voorbeeld van een Microsoft 365-Tenant met de Azure AD-Tenant](../media/tenant-management-overview/tenant-management-example-tenant.png)

*Pachtersbeheer* is de planning, implementatie en voortdurende werking van uw microsoft 365-tenants. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Kenmerken van een goed ontworpen en bewerkings Tenant

Naast de juiste naam en locatie voor uw Tenant zijn er nog meer elementen die u kunt gebruiken om te plannen, implementeren en beheren om ervoor te zorgen dat uw gebruikerservaring met apps voor Cloud productiviteit &mdash; zoals Microsoft teams en Exchange Online &mdash; efficiënt, veilig en oppassen.

Hier volgen de elementen:

- U beschikt over de juiste set producten (abonnementen) en licenties.
  - De set producten komt overeen met uw bedrijf, IT en beveiligingsbehoeften.
  - U hebt een voldoende aantal licenties voor uw werknemers en verwachte wijzigingen in personeel.
- Voor netwerken:
  - U hebt de juiste DNS-domeinnamen geconfigureerd.
  - Voor Enterprise-netwerken hebt u netwerkverkeer geoptimaliseerd voor het Microsoft-netwerk voor zelfstandigen.
  - U hebt een geoptimaliseerd netwerkverkeer voor externe werknemers die een VPN-client gebruiken.
- U hebt uw Active Directory Domain Services (AD DS)-accounts, groepen en andere objecten gesynchroniseerd.
  - Uw Azure AD-Tenant accounts worden gekoppeld aan postvakken van Exchange Online met de juiste DNS-domeinen voor e-mailadressen.
  - Aan uw gebruikersaccounts zijn de juiste licenties toegewezen van de juiste aangeschafte producten, zoals Microsoft 365 E3 of E5.
- U hebt een sterke identiteit en toegangsbeheer geconfigureerd.
  - U hebt een veilige gebruiker aangemeld met een wachtwoord of met multi-factor Authentication (MFA).
  - U hebt beleidsregels voor voorwaardelijke toegang die aanmeld vereisten en-beperkingen voor hogere beveiligingsniveaus afdwingen.
- On-premises Office-servers en de gegevens zijn gemigreerd naar Cloud-apps of worden gebruikt in een hybride configuratie.
- U doet Apparaatbeheer met intune of basis mobiliteit en beveiliging ingebouwd in Microsoft 365.
  - De apparaten van uw organisatie zijn geregistreerd en beheerd.
  - De apps voor persoonlijke apparaten worden beheerd.

Hier ziet u een voorbeeld van een Microsoft 365-Tenant met al deze elementen op hun plaats.

![Voorbeeld van Microsoft 365-Tenant](../media/tenant-management-overview/tenant-management-tenant-config.png)

In deze afbeelding bevat de Microsoft 365-Tenant de volgende opties:

- Producten en licenties voor Microsoft 365 E3 en E5.
- Microsoft 365-productiviteits-apps.
- InTune met geregistreerde apparaten en apparatuur en toepassingenbeleid.
- Een Azure AD-Tenant met gesynchroniseerde gebruikersaccount (groepen en andere directoryobjecten worden niet weergegeven), domeinen en regels voor voorwaardelijke toegang.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Tenant mogelijkheden voor Microsoft 365 for Enterprise

De volgende secties en tabel bevatten de belangrijkste mogelijkheden en licenties voor de stappen in deze oplossing.

### <a name="tenant"></a>Tenant

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Meerdere tenants | Elke Microsoft 365-Tenant is DISTINCT, Unique en los van alle andere Microsoft 365-tenants. Wanneer er meerdere tenants zijn, gelden er beperkingen en aanvullende aandachtspunten wanneer u ze beheert en services levert voor uw gebruikers. | Microsoft 365 E3 of E5 | 
| Migratie van postvakken tussen tenants | Tenant beheerders kunnen postvakken verplaatsen tussen tenants met minimale infrastructuur afhankelijkheden in hun on-premises systemen. Hiermee verwijdert u de postvakken die u niet nodig hebt. | Microsoft 365 E3 of E5 | 
| Meerdere geografische | Uw Tenant kan gegevens opslaan op de rest van de andere datacenter geo-locaties die u hebt gekozen om te voldoen aan de vereisten voor data woonplaats. | Microsoft 365 E3 of E5 | 
| Kerngegevens verplaatsen naar een nieuw datacenter-geo | Aangezien Microsoft nieuwe datacenter-GEOS toevoegt voor extra capaciteit en het berekenen van bronnen, kunt u voor de belangrijkste gegevens van uw primaire klant een datacenter aanvragen voor de geo-woonplaats. | Microsoft 365 E3 of E5 | 
||||

### <a name="networking"></a>Netwerken

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Netwerk inzichten | De gegevens van de netwerkprestaties die zijn verzameld van uw Microsoft 365-Tenant, zodat u Netwerkverbindingen voor uw Office-locaties kunt ontwerpen. | Microsoft 365 E3 of E5 | 
| Eindpunt updates automatiseren | De configuratie en voortdurende updates voor Microsoft 365-eindpunten automatiseren in de client PAC-bestanden en netwerkapparaten en-services. | Microsoft 365 E3 of E5 | 
||||

### <a name="identity"></a>Identiteit

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| On-premises Active Directory Domain Services (AD DS) synchroniseren met de Azure AD-Tenant    | Gebruik uw on-premises identiteitsprovider voor gebruikersaccounts, groepen en andere objecten. | Microsoft 365 E3 of E5 |
| Afgedwongen door MFA en met standaardbeveiligingsinstellingen   | Voorkom gecompromitteerde identiteiten en apparaten met een tweede vorm van verificatie voor aanmeldingen. Als standaardinstelling voor de beveiliging is MFA vereist voor alle gebruikersaccounts.   | Microsoft 365 E3 of E5 |
| Afgedwongen door MFA en met voorwaardelijke toegang| MFA vereisen op basis van de kenmerken van de aanmelding met regels voor voorwaardelijke toegang.    | Microsoft 365 E3 of E5 | 
| Afgedwongen door MFA en met voorwaardelijke toegang op basis van risico   | Vereis MFA op basis van het risico van de gebruikersaanmelding met Microsoft Defender for Identity. | Microsoft 365 E5 of E3 met Azure AD Premium P2-licenties | 
| Selfservice voor wachtwoordherstel (SSPR)    | Sta toe dat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen.  | Microsoft 365 E3 of E5 |
||||

### <a name="migration"></a>Migratie

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Migreren naar Windows 10 | Migreer uw apparaten waarop Windows 7 of Windows 8,1 wordt uitgevoerd naar Windows 10 Enterprise. | Licenties voor Windows 10 Enterprise die deel uitmaken van Microsoft 365 E3 of E5 | 
| Migreren naar Microsoft 365-apps voor Enterprise | Migreer uw Office-client-apps, zoals Word en PowerPoint, naar de versies die zijn geïnstalleerd vanuit de Cloud en die worden bijgewerkt met nieuwe functies. | Microsoft 365 E3 of E5 | 
| On-premises servers en gegevens migreren naar Microsoft 365 | Migreer uw Exchange-postvakken, SharePoint-sites en Skype voor bedrijven online naar Microsoft 365 cloudservices. | Microsoft 365 E3 of E5 | 
||||

### <a name="device-and-app-management"></a>Apparaten en apps beheren

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Microsoft Intune | Een op de cloud gebaseerde service die een MDM (Mobile Device Management) en Mobile Application Management (MAM) biedt om te bepalen hoe de toepassing van uw organisatie en de apparaten worden gebruikt, waaronder mobiele telefoons, Tablets en laptops. | Microsoft 365 E3 of E5 | 
| Basic Mobility en Security | Beveilig en beheer de mobiele apparaten van uw gebruikers, zoals iPhones, iPads, Android-telefoons en Windows Phones met deze ingebouwde service.  | Microsoft 365 E3 of E5 | 
||||

## <a name="next-steps"></a>Volgende stappen

Volg deze stappen voor het instellen en beheren van uw Microsoft 365-tenants.

1. [Uw tenants bepalen](tenant-management-tenants.md)
2. [Optimaliseer uw netwerk](tenant-management-networking.md)
3. [Uw identiteiten synchroniseren en beveiligde aanmeld modules afdwingen](tenant-management-identity.md)
4. [Uw on-premises Office-servers en-gegevens migreren](tenant-management-migration.md)
5. [Apparaten en app-beheer implementeren](tenant-management-device-management.md)

[![De stappen voor het implementeren en beheren van een Microsoft 365-Tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Elke stap beschrijft de implementatieopties, bevat een overzicht van de resultaten en permanente onderhoudstaken.

Voor inzicht in de manier waarop een fictieve maar representatieve mede-nationale organisatie de elementen van hun Microsoft 365-Tenant implementeert, raadpleegt u de casestudy van [Contoso](../enterprise/contoso-case-study.md).
