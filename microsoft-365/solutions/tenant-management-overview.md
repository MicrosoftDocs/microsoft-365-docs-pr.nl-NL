---
title: Tenantbeheer voor Microsoft 365 voor ondernemingen
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
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Een overzicht van de planning, implementatie en doorlopende werking van uw Microsoft 365 tenants.
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405676"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Tenantbeheer voor Microsoft 365 voor ondernemingen

Voor het maken van een pad naar de digitale transformatie van uw organisatie met cloud computing is een stevige basis vereist waarop uw werknemers kunnen vertrouwen voor productiviteit, samenwerking, prestaties, privacy, compliance en beveiliging.

De juiste configuratie van uw Microsoft 365 tenants biedt deze basis, zodat uw werknemers zich kunnen concentreren op het doen van hun werk en op uw IT-afdeling om zich te concentreren op end-to-endoplossingen die extra bedrijfswaarde bieden. 

Deze oplossing neemt u mee door de configuratie van die basis in deze stappen:

1. Uw tenants bepalen
2. Uw netwerken optimaliseren
3. Uw identiteiten synchroniseren en veilige aanmeldingen afdwingen
4. Uw Windows, Office clients en on-premises Office servers en gegevens migreren
5. Apparaat- en app-beheer implementeren

Maar laten we eerst even kijken wat een tenant is en hoe een tenant met een stevige basis eruitziet.

## <a name="a-microsoft-365-tenant-defined"></a>Een Microsoft 365 tenant gedefinieerd

Een Microsoft 365 tenant is een toegewezen exemplaar van de services van Microsoft 365 en uw organisatiegegevens die zijn opgeslagen op een specifieke standaardlocatie, zoals Europa of Noord-Amerika. Deze locatie wordt opgegeven wanneer u de tenant voor uw organisatie maakt. Elke Microsoft 365 tenant is afzonderlijk, uniek en gescheiden van alle andere Microsoft 365 tenants. U maakt een Microsoft 365 tenant wanneer u een of meer producten bij Microsoft koopt, zoals Microsoft 365 E3 of E5, en een reeks licenties voor elk.

Uw Microsoft 365 tenant bevat ook een Azure Active Directory (Azure AD) tenant, een speciaal exemplaar van Azure AD voor gebruikersaccounts, groepen en andere objecten. Elke Azure AD-tenant is afzonderlijk, uniek en gescheiden van alle andere Azure AD-tenants. Hoewel uw organisatie meerdere Azure AD-tenants kan hebben die u kunt instellen met Azure-abonnementen, kunnen Microsoft 365-tenants slechts één Azure AD-tenant gebruiken, de tenant die is gemaakt toen u de tenant maakte. 

Hier is een voorbeeld:

![Een voorbeeld Microsoft 365 tenant met de Azure AD-tenant](../media/tenant-management-overview/tenant-management-example-tenant.png)

*Tenantbeheer* is de planning, implementatie en continue werking van uw Microsoft 365 tenants. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Kenmerken van een goed ontworpen en werkende tenant

Naast de juiste naam en locatie voor uw tenant zijn er extra elementen die u kunt plannen, implementeren en beheren om ervoor te zorgen dat uw gebruikerservaringen met cloudproductiviteitsapps zoals Microsoft Teams en Exchange Online effectief, veilig en &mdash; &mdash; performant zijn.

Hier zijn de elementen:

- U hebt de juiste set producten (abonnementen) en licenties.
  - De set producten komt overeen met uw bedrijfs-, IT- en beveiligingsbehoeften.
  - Er is een voldoende aantal licenties voor uw werknemers en verwachte wijzigingen in het personeel.
- Voor netwerken:
  - U hebt de juiste DNS-domeinnamen geconfigureerd.
  - Voor bedrijfsnetwerken hebt u netwerkverkeer naar het Microsoft-netwerk geoptimaliseerd voor on-site werknemers.
  - U hebt netwerkverkeer geoptimaliseerd voor externe werknemers die een VPN-client gebruiken.
- U hebt uw AD DS-accounts, groepen en andere objecten (Active Directory Domain Services) gesynchroniseerd.
  - Uw Azure AD-tenantaccounts worden Exchange Online postvakken met de juiste DNS-domeinen voor e-mailadressen.
  - Aan uw gebruikersaccounts zijn de juiste licenties toegewezen van de juiste gekochte producten (zoals Microsoft 365 E3 of E5).
- U hebt een sterke identiteits- en toegangsbeheer geconfigureerd.
  - U hebt veilige aanmelding van gebruikers nodig met wachtwoordloze of meervoudige verificatie (MFA).
  - U hebt beleidsregels voor voorwaardelijke toegang die aanmeldingsvereisten en -beperkingen afdwingen voor hogere beveiligingsniveaus.
- On-premises Office servers en hun gegevens zijn gemigreerd naar cloud-apps of worden gebruikt in een hybride configuratie.
- U doet apparaatbeheer met Intune of Basic Mobility and Security ingebouwd in Microsoft 365.
  - Uw apparaten die eigendom zijn van uw organisatie, worden geregistreerd en beheerd.
  - De apps voor persoonlijke apparaten worden beheerd.

Hier is een voorbeeld van een Microsoft 365 tenant met al deze elementen op zijn plaats.

![Een voorbeeld van Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-tenant-config.png)

In deze afbeelding bevat de Microsoft 365 tenant:

- Producten en licenties voor Microsoft 365 E3 en E5.
- Microsoft 365 productiviteits-apps.
- Intune met geregistreerde apparaten en apparaat- en toepassingsbeleid.
- Een Azure AD-tenant met gesynchroniseerd gebruikersaccount (groepen en andere adreslijstobjecten worden niet weergegeven), domeinen en beleid voor voorwaardelijke toegang.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Tenantmogelijkheden voor Microsoft 365 voor bedrijven

In de volgende secties en tabel worden de belangrijkste mogelijkheden en licenties vermeld voor de stappen in deze oplossing.

### <a name="tenant"></a>Tenant

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Meerdere tenants | Elke Microsoft 365 tenant is afzonderlijk, uniek en gescheiden van alle andere Microsoft 365 tenants. Bij meerdere tenants zijn er beperkingen en extra aandachtspunten bij het beheren van deze tenants en het leveren van services aan uw gebruikers. | Microsoft 365 E3 of E5 | 
| Migratie van postvakken tussen tenants | Tenantbeheerders kunnen postvakken verplaatsen tussen tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen. Hierdoor hoeft u geen postvakken aan boord of aan boord meer te gebruiken. | Microsoft 365 E3 of E5 | 
| Multi-Geo | Uw tenant kan gegevens in rust opslaan in de andere geografische datacenterlocaties die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag. | Microsoft 365 E3 of E5 | 
| Kerngegevens verplaatsen naar een nieuw datacenter | Wanneer Microsoft nieuwe datacentergeo's toevoegt voor extra capaciteits- en rekenbronnen, kunt u een geovernieuwing voor datacenters aanvragen voor in-geogegevens voor uw kerngegevens. | Microsoft 365 E3 of E5 | 
||||

### <a name="networking"></a>Netwerken

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Netwerkinzichten | Meetgegevens voor netwerkprestaties die zijn verzameld Microsoft 365 tenant om u te helpen bij het ontwerpen van netwerkperimeters voor uw kantoorlocaties. | Microsoft 365 E3 of E5 | 
| Endpoint-updates automatiseren | Automatiseer de configuratie en doorlopende updates voor Microsoft 365 eindpunten in uw CLIENT PAC-bestanden en netwerkapparaten en -services. | Microsoft 365 E3 of E5 | 
||||

### <a name="identity"></a>Identiteit

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| On-premises Active Directory Domain Services (AD DS) synchroniseren met uw Azure AD-tenant    | Maak gebruik van uw on-premises identiteitsprovider voor gebruikersaccounts, groepen en andere objecten. | Microsoft 365 E3 of E5 |
| Afgedwongen door MFA en met standaardbeveiligingsinstellingen   | Voorkom gecompromitteerde identiteiten en apparaten met een tweede vorm van verificatie voor aanmeldingen. Als standaardinstelling voor de beveiliging is MFA vereist voor alle gebruikersaccounts.   | Microsoft 365 E3 of E5 |
| Afgedwongen door MFA en met voorwaardelijke toegang| Vereist MFA op basis van de kenmerken van de aanmelding met beleid voor voorwaardelijke toegang.    | Microsoft 365 E3 of E5 | 
| Afgedwongen door MFA en met voorwaardelijke toegang op basis van risico   | Vereis MFA op basis van het risico van de gebruikersaanmelding met Microsoft Defender for Identity. | Microsoft 365 E5 of E3 met Azure AD Premium P2-licenties | 
| Selfservice voor wachtwoordherstel (SSPR)    | Sta toe dat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen.  | Microsoft 365 E3 of E5 |
||||

### <a name="migration"></a>Migratie

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Migreren naar Windows 10 | Migreert uw apparaten met Windows 7 of Windows 8.1 naar Windows 10 Enterprise. | Windows 10 Enterprise licenties die zijn inbegrepen bij Microsoft 365 E3 of E5 | 
| Migreren naar Microsoft 365-apps voor ondernemingen | Migreert Office client-apps zoals Word en PowerPoint naar de versies die zijn geïnstalleerd vanuit de cloud die worden bijgewerkt met nieuwe functies. | Microsoft 365 E3 of E5 | 
| On-premises servers en gegevens migreren naar Microsoft 365 | Migreert Exchange postvakken, SharePoint sites en Skype voor Bedrijven Online naar Microsoft 365 cloudservices. | Microsoft 365 E3 of E5 | 
||||

### <a name="device-and-app-management"></a>Apparaat- en app-beheer

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Microsoft Intune | Een cloudservice die MDM (Mobile Device Management) en MOBILE Application Management (MAM) biedt om te bepalen hoe de toepassing van uw organisatie en de apparaten worden gebruikt, inclusief mobiele telefoons, tablets en laptops. | Microsoft 365 E3 of E5 | 
| Basic Mobility en Security | Beveilig en beheer de mobiele apparaten van uw gebruikers, zoals iPhones, iPads, Androids en Windows met deze ingebouwde service.  | Microsoft 365 E3 of E5 | 
||||

## <a name="next-steps"></a>Volgende stappen

Gebruik deze stappen om uw tenants in te stellen en Microsoft 365 beheren.

1. [Uw tenants bepalen](tenant-management-tenants.md)
2. [Uw netwerken optimaliseren](tenant-management-networking.md)
3. [Uw identiteiten synchroniseren en veilige aanmeldingen afdwingen](tenant-management-identity.md)
4. [Uw on-premises Office servers en gegevens migreren](tenant-management-migration.md)
5. [Apparaat- en app-beheer implementeren](tenant-management-device-management.md)

[![De stappen voor het implementeren en beheren van een Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

In elke stap worden implementatieopties beschreven, worden de resultaten en de lopende onderhoudstaken samengevat.

Zie de [contoso-case study](../enterprise/contoso-case-study.md)om te begrijpen hoe een fictieve, maar representatieve multi-nationale organisatie de elementen van hun Microsoft 365 heeft geïmplementeerd.
