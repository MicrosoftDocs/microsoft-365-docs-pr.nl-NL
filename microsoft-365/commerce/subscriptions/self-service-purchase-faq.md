---
title: Veelgestelde vragen over self-service aankopen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: Hier vindt u antwoorden op veelgestelde vragen over self-service aankopen.
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653699"
---
# <a name="self-service-purchase-faq"></a>Veelgestelde vragen over self-service aankopen

Met selfservice aankopen kunnen gebruikers de mogelijkheid nieuwe technologieën uit te proberen en oplossingen te ontwikkelen die uiteindelijk een grotere organisatie voor u hebben. Centrale aanschaffing en IT-teams hebben inzicht in de aankoop van oplossingen voor Self-service aankopen en implementeren via het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>. Beheerders kunnen selfservice aankopen per product basis uitschakelen via PowerShell. Zie voor meer informatie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md).

Service voor selfservice aankoop is beschikbaar voor Power platform (Power BI, Power apps en Power Automatiseer), project en Visio.

> [!NOTE]
> Service voor selfservice aankopen is niet beschikbaar in India en is niet beschikbaar voor klanten van de overheid of onderwijsinstellingen.

## <a name="making-a-self-service-purchase"></a>Een self-service aankoop doen

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Hoe maakt een klant selfservice aankopen?

Klanten kunnen Self-service online kopen via de product websites of vanuit de aankoop vragen in de app. Klanten wordt eerst gevraagd een e-mailadres in te voeren om ervoor te zorgen dat ze een gebruiker zijn in een bestaande Azure Active Directory (AD)-Tenant. Vervolgens worden ze doorgestuurd om me aan te melden met hun Azure AD-referenties. Nadat u zich hebt aangemeld, wordt de klant gevraagd te selecteren hoeveel abonnementen ze willen kopen en om creditcardbetaling te bieden. Wanneer de aankoop is voltooid, kunnen ze hun abonnement gaan gebruiken. De verkoper heeft toegang tot een beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a> , waar zij licenties aan het product kunnen toewijzen voor andere personen in de organisatie.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Wat zijn de betalingsopties voor Self-service aankopen?

Op dit moment is creditcard de enige beschikbare betaalwijze. Betaling via de facturering wordt niet ondersteund.

### <a name="who-can-buy-through-self-service-purchase"></a>Wie kan uw eigen service aankopen kopen?

Gebruikers met een niet-gastgebruikersaccount in een beheerde Azure AD-Tenant kunnen selfservice aankopen doen. Service voor selfservice aankoop is niet beschikbaar voor tenants van Government-of onderwijs organisaties. Als dit van toepassing is op uw organisatie, hoeft u geen extra actie te ondernemen om de selfservice aankoop te bepalen.

Gebruikers in organisaties of markten die niet in aanmerking komen voor selfservice aankopen, zien een bericht waarin wordt gevraagd om contact op te nemen met hun IT-beheerder.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Kunnen gastgebruikers via selfservice aankopen kopen?

Nee, gastgebruikers kunnen geen selfservice aankopen voeren in een Tenant waarvan ze een gast zijn.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Kunnen gebruikers die worden gesynchroniseerd vanuit een on-premises Active Directory kopen via selfservice aankoop?

Als een gebruiker een actief gebruikersaccount heeft in de in aanmerking komende Azure AD-Tenant, kan hij of zij een selfservice aankoop voltooien.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Wie kan self-service-inkopen licenties toewijzen?

Selfservice aankopen kunnen alleen licenties toewijzen aan gebruikers in dezelfde Azure AD-Tenant. De verkoper heeft toegang tot een beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a> om licenties toe te wijzen. Verkoper kan licenties toewijzen aan de producten die ze hebben gekocht via selfservice aankoop, en kunnen deze licenties alleen toewijzen aan gebruikers in dezelfde Azure AD-Tenant.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Waar kan de selfservice verkoper hun aankopen zien en beheren?

Selfservice aankopen kunnen hun aankopen beheren in de beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>. U kunt op elk gewenst punt voor de beheerder van de tegel **beheerder** in het startprogramma voor apps in het startprogramma voor apps van microsoft 365 en Dynamics online-apps het Beheercentrum openen. Kopers kunnen de aankopen bekijken die ze hebben aangebracht, extra abonnementen op dezelfde service kopen en licenties toewijzen aan andere gebruikers in hun organisatie. Aankoopers kunnen ook hun factuur bekijken en betalen, hun betaalmethode bijwerken en hun abonnement opzeggen.

## <a name="pricing"></a>Koers

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Wat zijn de prijzen voor selfservice aankopen?

De prijzen voor elk product voor selfservice-aankopen zijn beschikbaar op de website van Microsoft. Prijzen worden ook weergegeven als onderdeel van de uitcheck ervaring wanneer gebruikers selfservice aankopen doen. Deze prijzen kunnen verschillen van de prijzen die een organisatie betaalt bij het aangaan van centrale aankopen of prijzen via een partner.

### <a name="who-is-responsible-for-payment"></a>Wie is verantwoordelijk voor de betaling?

De persoon die het abonnement via selfservice aankoop koopt, is de persoon die factureert en wie verantwoordelijk is voor de betaling op basis van de voorwaarden en prijzen van de aankoop.

## <a name="admin-capabilities"></a>Beheerders mogelijkheden

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Welke mogelijkheden biedt een beheerder voor Self-service-aankopen?

Beheerders kunnen alle selfservice aankopen weergeven die zijn gemaakt in hun organisatie in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>. Ze kunnen het product, de naam van de verkoper, aangeschafte abonnementen, vervaldatum, ordergeschiedenis, aankoopprijs en toegewezen gebruikers voor elke selfservice aankoop zien. In het Beheercentrum voor Power platform kunnen beheerders ook de capaciteit voor de eigen service aankopen bekijken. Indien nodig voor hun organisatie kunnen beheerders selfservice aankopen per product basis uitschakelen via PowerShell. Beheerders hebben dezelfde beleidsregels voor gegevensbeheer en toegang via producten die zijn gekocht via selfservice aankoop of centraal.

Beheerders kunnen ook bepalen of gebruikers in hun organisatie selfservice aankopen kunnen verrichten. Zie voor meer informatie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Hoe eerbiedigt Microsoft Data Governance en compliance door selfservice aankopen in te schakelen?

Beheerders beheren de controle over welke services en producten beschikbaar zijn in hun Tenant, op basis van hun data governance en de nalevingsvereisten. Alle beleidsregels voor gegevensbeheer en toegang tot het beleid dat uw organisatie heeft ingeschakeld, zijn van toepassing op de beschikbare services die voor selfservice zijn gekocht.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Wie is de eigenaar van de productgegevens die zijn gemaakt met selfservice aankopen?

Gegevens die zijn gemaakt op basis van producten die zijn gekocht via selfservice aankoop, zijn eigendom van en worden beheerd door de organisatie.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Hoe kan ik de aankopen op de eigen service aankopen centraliseren?

Beheerders kunnen bestaande licenties toewijzen of extra abonnementen van selfservice aankopen kopen via bestaande overeenkomsten en prijzen voor gebruikers die zijn toegewezen aan selfservice aankopen. Nadat u deze met een centrale licentie aangeschafte licenties hebt toegewezen, kunnen beheerders vragen of ze hun bestaande abonnementen annuleren.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Waar ziet de beheerder selfservice aankopen?

Globale beheerders en facturerings beheerders kunnen via selfservice aankoop de door u gekochte abonnementen zien in de **facturering**van  >  **de producten** van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>. Ze kunnen de lijst producten filteren om alleen de abonnementen weer te geven die zijn gekocht via de centrale aankoop, of voor het opnemen van abonnementen die zijn gekocht via selfservice purchase.

Beheerders kunnen het product, de naam van de verkoper, het aangeschafte abonnement, de vervaldatum, de ordergeschiedenis, de aankoopprijs en de toegewezen gebruikers zien.

## <a name="support-and-training"></a>Ondersteuning en training

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Zijn de IT-afdelingen van klanten of partners de ondersteuning van producten die zijn gekocht via selfservice Purchase?

IT-afdelingen en partners verwachten geen ondersteuning te bieden voor producten die zijn gekocht via selfservice aankopen. Microsoft biedt standaard ondersteuning voor selfservice-inkopen.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Gebruik de premier-ondersteunings incidenten van de klant als een selfservice medewerker ondersteuning biedt.

Selfservice aankopen gebruiken geen klanten van de premier-ondersteuning van een klant om ondersteuning te krijgen voor hun selfservice aankopen.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Hoe verwachten de gebruikers training te ontvangen op de producten die ze kopen via een selfservice aankoop?

Uitgebreide training voor gebruikers is beschikbaar op de product websites. De producten hebben geleide Learning, Documentatie, voorbeelden en krachtige community's om antwoorden en tips rechtstreeks van andere gebruikers te krijgen.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Wat gebeurt er met een selfservice aankoop als een gebruiker de organisatie verlaat?

Als degene die het selfservice Purchase product oorspronkelijk heeft gekocht, de organisatie verlaat, blijven geldige gebruikers hun gehele product gebruiken voor de duur van het abonnement. Het abonnement blijft actief totdat de koper de klant direct annuleert of een beheerder vraagt de annulering van het abonnement door de klantondersteuning. Beheerders kunnen er ook voor kiezen een centraal aangeschafte licentie toe te wijzen aan gebruikers van het geannuleerde abonnement.

## <a name="partners"></a>Relaties

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Wat is de rol van de partners van Microsoft in selfservice-aankopen?

Partners die gedelegeerde beheerdersrechten hebben, kunnen selfservice aankopen bekijken in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>, net als een beheerder. Partners kunnen ondersteuning bieden voor ondersteuning van een organisatie die producten wil centraliseren die via selfservice aankopen op de eigen service zijn gekocht. Daarnaast kunnen partners oplossingen bieden om de mogelijkheden van een selfservice aankoop uit te breiden.