---
title: Veelgestelde vragen over selfservice-aankoop
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: Antwoorden vinden op veelgestelde vragen over selfserviceaankopen.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333192"
---
# <a name="self-service-purchase-faq"></a>Veelgestelde vragen over selfservice-aankoop

Selfserviceaankoop biedt gebruikers de mogelijkheid om nieuwe technologieën uit te proberen en oplossingen te ontwikkelen die uiteindelijk hun grotere organisaties ten goede komen. Centrale inkoop- en IT-teams hebben zichtbaarheid voor alle gebruikers die selfservice-aankoopoplossingen kopen en implementeren via het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum.</a> Beheerders kunnen selfservice-aankopen per product uitschakelen via PowerShell. Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie.

Selfservice-aankoop is beschikbaar voor Power Platform (Power BI, Power Apps en Power Automate), Project en Visio.

> [!NOTE]
> Selfserviceaankoop is niet beschikbaar in India of voor klanten van de overheid of onderwijs. Project en Visio zijn niet beschikbaar voor selfserviceaankoop in Brazilië en de Democratische Republiek Congo.

## <a name="making-a-self-service-purchase"></a>Een selfservice-aankoop doen

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Hoe doet een klant een selfserviceaankoop?

Klanten kunnen online een selfservice-aankoop doen via de productwebsites of via in-app aankoopprompts. Klanten wordt eerst gevraagd een e-mailadres in te voeren om ervoor te zorgen dat ze een gebruiker zijn in een bestaande Azure Active Directory-tenant (AD). Vervolgens worden ze doorgestuurd om zich aan te melden met hun Azure AD-referenties. Na het aanmelden wordt de klant gevraagd om te selecteren hoeveel abonnementen ze willen kopen en om creditcardbetaling te geven. Wanneer de aankoop is voltooid, kunnen ze hun abonnement gaan gebruiken. De inkoper heeft toegang tot een beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum,</a> waar hij of zij licenties aan het product kan toewijzen aan andere personen in de organisatie.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Wat zijn de betalingsopties voor selfserviceaankopen?

Momenteel is creditcard de enige beschikbare betalingswijze. Betaling via facturering wordt niet ondersteund.

### <a name="who-can-buy-through-self-service-purchase"></a>Wie kan kopen via selfservice-aankoop?

Elke gebruiker met een niet-gastgebruikersaccount in een beheerde Azure AD-tenant kan een selfserviceaankoop doen. Selfservice-inkoop is niet beschikbaar voor tenants die overheids- of onderwijsorganisaties zijn. Als dit van toepassing is op uw organisatie, is er geen extra actie vereist om de selfserviceaankoop te controleren.

Gebruikers in organisaties of markten die niet in aanmerking komen voor selfserviceaankoop, zien een bericht waarin ze worden gevraagd contact op te nemen met hun IT-beheerder.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Kunnen gastgebruikers kopen via selfservice-aankoop?

Nee, gastgebruikers kunnen een selfservice-aankoop niet voltooien in een tenant waarin ze een gast zijn.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Kunnen gebruikers die worden gesynchroniseerd via een on-premises Active Directory kopen via selfservice-aankoop?

Als een gebruiker een actief gebruikersaccount heeft in een in aanmerking komende Azure AD-tenant, kan deze een selfservice-aankoop uitvoeren.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Aan wie kunnen selfservice-inkopers licenties toewijzen?

Selfservice-inkopers kunnen alleen licenties toewijzen aan gebruikers in dezelfde Azure AD-tenant. De inkoper heeft toegang tot een beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum</a> om licenties toe te wijzen. Inkopers kunnen licenties toewijzen aan producten die ze hebben gekocht via selfservice-aankoop en kunnen deze licenties alleen toewijzen aan gebruikers in dezelfde Azure AD-tenant.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Waar ziet en beheert de selfservice-inkoper zijn aankopen?

Selfservice-inkopers kunnen hun aankopen beheren in de beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum.</a> Inkopers kunnen altijd naar het  beheercentrum gaan via de tegel Beheerder in het startpagina voor apps die zijn ingebouwd in alle online-apps van Microsoft 365 en Dynamics. Inkopers kunnen de aankopen bekijken die ze hebben gedaan, extra abonnementen op dezelfde service kopen en licenties voor deze abonnementen toewijzen aan andere gebruikers in hun organisatie. Bovendien kunnen inkopers hun factuur bekijken en betalen, hun betalingswijze bijwerken en hun abonnement opzeggen.

## <a name="pricing"></a>Prijzen

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Wat zijn de prijzen voor selfserviceaankopen?

Prijzen voor elk van de producten voor selfserviceaankoop zijn beschikbaar op de Microsoft-website. Prijzen worden ook weergegeven als onderdeel van de uitcheckervaring wanneer gebruikers een selfserviceaankoop doen. Deze prijzen kunnen afwijken van de prijzen die een organisatie betaalt bij het doen van centrale aankopen of prijzen die via een partner worden aangeboden.

### <a name="who-is-responsible-for-payment"></a>Wie is verantwoordelijk voor de betaling?

De persoon die het abonnement koopt via selfservice-aankoop, is de persoon die wordt gefactureerd en die verantwoordelijk is voor de betaling op basis van de voorwaarden en prijzen van de aankoop.

## <a name="admin-capabilities"></a>Beheermogelijkheden

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Welke mogelijkheden heeft een beheerder voor selfserviceaankopen?

Beheerders kunnen alle selfserviceaankopen in hun organisatie bekijken in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum.</a> Ze kunnen het product, de naam van de inkoper, de gekochte abonnementen, de vervaldatum, de ordergeschiedenis, de aankoopprijs en de toegewezen gebruikers zien voor elke selfserviceaankoop. In het Power Platform-beheercentrum kunnen beheerders ook de capaciteit voor selfserviceaankopen bekijken. Indien vereist voor hun organisatie, kunnen beheerders selfservice-aankopen per product uitschakelen via PowerShell. Beheerders hebben hetzelfde gegevensbeheer- en toegangsbeleid voor producten die zijn gekocht via selfserviceaankoop of centraal.

Beheerders kunnen ook bepalen of gebruikers in hun organisatie selfserviceaankopen kunnen doen. Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie.

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Hoe respecteert Microsoft gegevensbeheer en compliance door selfserviceaankoop in te stellen?

Beheerders houden de controle over welke services en producten beschikbaar zijn in hun tenant op basis van hun vereisten voor gegevensbeheer en compliance. Alle beleidsregels voor gegevensbeheer en toegang die uw organisatie heeft ingeschakeld, zijn van toepassing op beschikbare selfservice aangeschafte services.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Wie is de eigenaar van de productgegevens die zijn gemaakt van selfserviceaankopen?

Gegevens die zijn gemaakt van producten die via selfservice worden gekocht, zijn eigendom van en worden beheerd door de organisatie.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Hoe centraliseer ik de aankopen die worden gedaan via selfservice-aankopen?

Beheerders kunnen bestaande licenties toewijzen of extra abonnementen kopen voor selfservice-aankoopproducten via bestaande overeenkomsten en prijzen voor gebruikers die zijn toegewezen aan selfserviceaankopen. Na het toewijzen van deze centraal aangeschafte licenties kunnen beheerders vervolgens vragen dat de inkopers hun bestaande abonnementen opzeggen.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Waar ziet de beheerder selfserviceaankopen?

Globale en factureringsbeheerders kunnen abonnementen zien die zijn gekocht via selfservice-aankoop in **Facturering**  >  **uw producten** in het Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365-beheercentrum.</a> Ze kunnen de lijst met producten filteren om alleen de abonnementen weer te geven die zijn gekocht via centrale inkoop of om abonnementen op te nemen die zijn gekocht via selfserviceaankoop.

Beheerders kunnen het product, de naam van de koper, het gekochte abonnement, de vervaldatum, de ordergeschiedenis, de aankoopprijs en de toegewezen gebruikers zien.

## <a name="support-and-training"></a>Ondersteuning en training

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Worden it-afdelingen of partners van klanten verwacht dat ze producten ondersteunen die worden gekocht via selfserviceaankoop?

It-afdelingen en -partners bieden naar verwachting geen ondersteuning voor producten die via selfservice worden gekocht. Microsoft biedt standaardondersteuning voor selfservice-inkopers.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Als een selfservice-inkoper ondersteuning belt, worden dan de Premier Support-incidenten van de klant gebruikt?

Selfservice-inkopers gebruiken de Premier Support-incidenten van een klant niet voor het ontvangen van ondersteuning voor hun selfserviceaankopen.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Hoe wordt van gebruikers verwacht dat ze training krijgen over de producten die ze kopen via selfserviceaankoop?

Uitgebreide training voor gebruikers wordt gegeven op de productwebsites. De producten hebben geleide leer-, documentatie-, steekproeven en sterke community's om rechtstreeks antwoorden en tips van andere gebruikers te krijgen.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Wat gebeurt er met een selfserviceaankoop als een gebruiker de organisatie verlaat?

Als de persoon die het selfservice-aankoopproduct oorspronkelijk heeft gekocht, de organisatie verlaat, blijven geldige gebruikers het product volledig gebruiken gedurende de duur van het abonnement. Het abonnement blijft actief totdat de koper het rechtstreeks annuleert of een beheerder annulering van het abonnement aanvraagt via klantondersteuning. Beheerders kunnen er ook voor kiezen om een centraal aangeschafte licentie toe te wijzen aan gebruikers van het geannuleerde abonnement.

## <a name="partners"></a>Partners

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Wat is de rol van microsofts partners bij selfserviceaankopen?

Partners die gedelegeerde beheerbevoegdheden hebben, kunnen selfserviceaankopen zien in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum,</a>net als een beheerder. Partners kunnen helpen bij het ondersteunen van een organisatie die producten die via selfservice-aankopen worden gekocht, wil centraliseren. Daarnaast kunnen partners oplossingen bieden om de mogelijkheden van een selfserviceaankoop uit te breiden.