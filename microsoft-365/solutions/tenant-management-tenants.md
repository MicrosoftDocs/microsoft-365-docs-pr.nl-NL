---
title: Stap 1. Uw Microsoft 365 voor enterprise-tenants
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Een of meer Microsoft 365-tenants implementeren en beheren, met opties voor multige geo-locaties en locaties waar u zich kunt verplaatsen.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406382"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Stap 1. Uw Microsoft 365 voor enterprise-tenants

Een van uw eerste tenantbeslissingen is hoeveel u er moet hebben. Elke Microsoft 365-tenant is uniek en gescheiden van alle andere Microsoft 365-tenants. De bijbehorende Azure AD-tenant is ook uniek en gescheiden van alle andere Microsoft 365-tenants.

## <a name="single-tenant"></a>Eén tenant
Eén tenant vereenvoudigt veel aspecten van het gebruik van Microsoft 365 in uw organisatie. Eén tenant betekent één Azure AD-tenant met één set accounts, groepen en beleidsregels. Machtigingen en het delen van resources binnen uw organisatie kunnen worden uitgevoerd via deze centrale identiteitsprovider.

Eén tenant biedt de meest uitgebreide en vereenvoudigde samenwerkings- en productiviteitservaring voor uw gebruikers.

Hier is een voorbeeld met de standaardlocatie en Azure AD-tenant van een Microsoft 365-tenant.

![Eén Microsoft 365-tenant met de Azure AD-tenant](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Meerdere tenants

Er zijn diverse redenen waarom uw organisatie meerdere tenants kan hebben:

- Administratieve isolatie
- Autoriserende IT
- Historische beslissingen
- Fusies, overnames of verkoop
- Scheiding van huisstijl voor conglomeratie-organisaties duidelijk maken
- Pre-productie-, test- of sandbox-tenants

Hier is een voorbeeld van een organisatie die twee tenants (Tenant A en Tenant B) heeft in hetzelfde standaard datacenter geo. Elke tenant als een afzonderlijke Azure AD-tenant.

![Meerdere Microsoft 365-tenants met hun eigen Azure AD-tenants](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Als u meerdere tenants hebt, zijn er beperkingen en extra overwegingen bij het beheren van deze tenants en het leveren van services aan uw gebruikers.

### <a name="inter-tenant-collaboration"></a>Samenwerking tussen verschillende tenants

Als u wilt dat uw gebruikers op een veilige manier efficiënter samenwerken tussen verschillende Microsoft 365-tenants, kunt u samenwerken tussen tenants door een centrale locatie te gebruiken voor bestanden en gesprekken, agenda's te delen, chatberichten te gebruiken, audio-/videogesprekken te gebruiken voor communicatie en de toegang tot resources en toepassingen te beveiligen.

Zie microsoft [365](../enterprise/microsoft-365-inter-tenant-collaboration.md)samenwerking tussen verschillende tenants voor meer informatie.

### <a name="cross-tenant-mailbox-migration-preview"></a>Migratie van postvakken tussen tenants (preview)

Vóór migratie van postvakken op verschillende tenants (in preview) moet u bij het verplaatsen van Exchange Online-postvakken tussen tenants het postvak van een gebruiker volledig offboarden van de huidige tenant (de bronten tenant) naar de on-premises tenant en ze vervolgens onboarden naar een nieuwe tenant (de doelten tenant). Met de nieuwe functie voor migratie van postvakken op verschillende tenants kunnen tenantbeheerders in zowel de bron- als doelten tenants postvakken verplaatsen tussen de tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen. Hiermee verwijdert u de noodzaak om postvakken aan de andere bord- en onboard-app toe te laten.

Hier volgen twee voorbeeldtententen en hun postvakken vóór de migratie van postvakken tussen tenants.

![Meerdere Microsoft 365-tenants en hun postvakken](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

In deze afbeelding hebben twee afzonderlijke tenants hun eigen domeinen en set Exchange-postvakken.

Hier is de doel tenant (Tenant A) na de migratie van postvakken tussen tenants.

![De doel tenant na migratie van postvakken tussen tenants](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

In deze afbeelding heeft één tenant zowel domeinen als beide sets Exchange-postvakken.

Zie Postvakmigratie tussen [tenants voor meer informatie.](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>Tenant-naar-tenant-migraties

Er zijn verschillende architectuurbenaderingen voor fusies, overnames, verkoop en andere scenario's die ertoe kunnen leiden dat u een bestaande Microsoft 365-tenant migreert naar een nieuwe tenant. 

Zie Microsoft [365-tenant-naar-tenantmigraties voor gedetailleerde instructies.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo voor een tenant

Met Microsoft 365 Multi-Geo kunt u gegevens inrichten en opslaan in de geolocaties van het andere datacenter die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag en tegelijkertijd uw globale implementatie van moderne productiviteitservaringen voor uw collega's ontgrendelen.

In een Multi Geo-omgeving bestaat uw Microsoft 365-tenant uit een standaard- of centrale locatie waar uw Microsoft 365-abonnement oorspronkelijk is gemaakt en een of meer satellietlocaties. In een multige geo-tenant wordt de informatie over geografische locaties, groepen en gebruikersgegevens gemodeld in een globale Azure AD-tenant. Omdat uw tenantgegevens centraal worden gemodelleerd en gesynchroniseerd in elke geografische locatie, worden samenwerkingservaringen met iedereen in uw bedrijf gedeeld over de locaties.

Hier is een voorbeeld van een organisatie met een standaardlocatie in Europa en een satellietlocatie in Noord-Amerika. Beide locaties delen dezelfde globale Azure AD-tenant voor één Microsoft 365-tenant.

![Voorbeeld van een Multi Geo Microsoft 365-tenant](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Zie [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)voor meer informatie.

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Belangrijke gegevens verplaatsen naar een nieuw geografisch datacenter

Microsoft blijft het nieuwe datacenter geos openen voor Microsoft 365-services. Deze nieuwe datacenters voegen capaciteits- en berekeningsbronnen toe om onze continue vraag en gebruiksgroei van klanten te ondersteunen. Bovendien bieden de nieuwe datacenter geo's in-geo-gegevens opgeslagen voor belangrijke klantgegevens.

Hoewel het openen van een nieuw datacenter geo geen invloed heeft op u en uw kerngegevens die zijn opgeslagen in een bestaande geografische datacenter, kunt u met Microsoft een vroege migratie aanvragen van de kernklantgegevens van uw organisatie in rust naar een nieuw geografisch datacenter.

Hier is een voorbeeld waarin een Microsoft 365-tenant is verplaatst van het geografische datacenter van de Europese Unie (EU) naar het datacenter in het Verenigd Koninkrijk (VK).

![Voorbeeld van het verplaatsen van een Microsoft 365-tenant tussen datacenters](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Zie Kerngegevens verplaatsen naar nieuwe geografische datacenters in [Microsoft 365 voor meer informatie.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Producten en licenties voor een tenant

Uw Microsoft 365-tenant wordt gemaakt wanneer u uw eerste product koopt, zoals Microsoft 365 E3. Naast het product zijn licenties, waarvoor een maandelijks of jaarlijks bedrag in rekening wordt gebracht. Een beheerder wijst vervolgens een beschikbare licentie van een van uw producten toe aan een gebruikersaccount, rechtstreeks of via groepslidmaatschap. Afhankelijk van de zakelijke behoeften van uw organisatie, hebt u mogelijk een set producten met elk een eigen groep licenties. 

Voor het bepalen van de set producten en het aantal licenties voor elke set moet u enkele planningen maken:

- Zorg ervoor dat u voldoende licenties hebt voor de gebruikersaccounts die geavanceerde functies nodig hebben.
- Voorkomen dat uw licenties op lopen of te veel niet-toegewezen licenties hebben, op basis van wijzigingen in de personeelsbeplaatsing in uw organisatie.


## <a name="results-of-step-1"></a>Resultaten van stap 1

Voor uw Microsoft 365 voor enterprise-tenants hebt u het volgende bepaald:

- Hoeveel tenants u hebt of nodig hebt.
- Voor elke tenant moeten de producten en licenties worden gekocht.
- Of een tenant multige geo moet zijn om te voldoen aan de vereisten voor gegevenslocatie.
- Of u samenwerking tussen tenants moet instellen.
- Of u de ene tenant naar de andere wilt migreren.
- Of u kerngegevens moet verplaatsen van een geo datacenter naar een nieuwe datacenter.

Hier is een voorbeeld van een nieuwe tenant.

![Voorbeeld van een nieuwe tenant](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

In deze afbeelding heeft de tenant:

- Een standaardlocatie die overeenkomt met een geografische locatie in het Microsoft 365-datacenter.
- Een set producten en licenties.
- De set cloudproductiviteitsapps, waarvan sommige specifiek zijn voor producten.
- Een Azure AD-tenant met globale beheerdersaccounts en een initiële DNS-domeinnaam.

Terwijl we verder gaan met de extra stappen van deze oplossing, bouwen we deze afbeelding uit.

## <a name="ongoing-maintenance-for-tenants"></a>Doorlopend onderhoud voor tenants

Oplopende basis moet u mogelijk het volgende doen:

- Voeg een nieuwe tenant toe.
- Nieuwe producten toevoegen aan een tenant met een eerste aantal licenties.
- Wijzig de set licenties voor een product in een tenant om de personeelsvereisten aan te passen.
- Verplaats de kerngegevens van een tenant naar een nieuwe geografische locatie in het datacenter.
- Voeg Multi-Geo toe voor vereisten voor het opslaan van gegevens.
- Samenwerking tussen tenants instellen.

## <a name="next-step"></a>Volgende stap

[![Stap 2. Uw tenant optimaliseren voor netwerk voor toegang](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Ga door [met netwerken](tenant-management-networking.md) om optimale netwerken van uw collega's en Microsoft 365-cloudservices te bieden.
