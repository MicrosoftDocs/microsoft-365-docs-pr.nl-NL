---
title: Veelgestelde vragen over zelfserviceaankopen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Vind antwoorden op veelgestelde vragen over zelfbedieningsaankopen.
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: 4e4ec060a1d782b9c0ddd970906eabebe218ac4f
ms.sourcegitcommit: ab916c216053999c9c4ef4838217e82cd861f23f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2020
ms.locfileid: "42805489"
---
# <a name="self-service-purchase-faq"></a>Veelgestelde vragen over zelfserviceaankopen

> [!NOTE]
> De informatie in dit artikel is alleen van toepassing op Microsoft Power Platform -abonnementen (Power BI, Power Apps en Power Automate).

Selfservice-aankopen zijn nu beschikbaar voor Power Platform in meerdere landen en regio's.

## <a name="general"></a>Algemeen

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Welke wijzigingen heeft Microsoft aangekondigd rond selfservice-aankopen voor de Power Platform-producten?

Op 19 november hebben we IT-beheerders een manier geboden om de aankoop van selfservice per product uit te schakelen via PowerShell. Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie over het gebruik ervan.

Om meer tijd te bieden om zich voor te bereiden op deze wijziging, werken we de lancering voor self-service aankoopmogelijkheden voor Power Platform-producten bij om op 14 januari met Power BI te beginnen voor alle commerciële cloudklanten.  

Vanaf 14 januari 2020 zijn selfservice-inkoop-, abonnements- en licentiebeheermogelijkheden voor Power Platform-producten (Power BI, Power Apps en Power Automate) beschikbaar voor commerciële cloudklanten in de Verenigde Staten. Self-service aankoop geeft gebruikers een kans om nieuwe technologieën uit te proberen en laat hen oplossingen ontwikkelen die uiteindelijk hun grotere organisaties ten goede komen. Deze mogelijkheid is op dit moment niet beschikbaar voor huurders in de VS die overheids-, non-profitorganisaties of onderwijs zijn. Centrale inkoop- en IT-teams hebben zichtbaarheid voor alle gebruikers die zelfbedieningsoplossingen kopen en implementeren via het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum</a>en kunnen de aankoop van selfservice per product uitschakelen via PowerShell.

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Waarom voegt Microsoft een selfservice-aankoopoptie toe voor de Power Platform-producten?

In de wereld van vandaag zijn eindgebruikers en afdelingen steeds vaker op zoek naar technologieoplossingen op eigen houtje. We hebben talloze verzoeken ontvangen van deze klanten om selfservice-aankopen van Power Platform-producten mogelijk te maken. We spelen in op deze behoeften van klanten en balanceren tegelijkertijd de behoeften van IT-beheerders, die vaak zichtbaar en controle verliezen wanneer individuen binnen hun organisatie oplossingen van derden aannemen zonder hun medeweten. Met de komende selfservice-mogelijkheden voor Power Platform-producten hebben IT-beheerders volledige zichtbaarheid voor alle selfservice-aankopen die plaatsvinden binnen hun organisatie, en zal het beleid voor gegevensbeheer dat op organisatieniveau is ingesteld, abonnementen gekocht via selfservice. Beheerders kunnen ook bestaande licenties toewijzen of extra abonnementen van Power Platform-producten kopen via bestaande overeenkomsten en prijzen voor gebruikers die zijn toegewezen aan zelfserviceaankopen. Na het toewijzen van deze centraal aangeschafte licenties kunnen beheerders vervolgens vragen dat de kopers hun bestaande abonnementen opzeggen. Microsoft onderzoekt manieren om dit proces voor beheerders in de toekomst te vereenvoudigen en te stroomlijnen.

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>Welke Power Platform-producten zijn beschikbaar voor zelfservice-aankopen?

Microsoft heeft selfservice-aankoop voor Power Platform (Power BI, Power Apps en Power Automate) gelanceerd aan klanten in de Verenigde Staten, waarbij in de komende maanden extra markten beschikbaar komen. Deze mogelijkheid is op dit moment niet beschikbaar voor huurders in de VS die overheids-, non-profitorganisaties of onderwijs zijn.

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>Zal selfservice-aankopen worden ingeschakeld voor diensten buiten de Power Platform-producten?

Op dit moment worden alleen de Power Platform-familieproducten aangeboden via zelfbedieningsaankopen.

## <a name="making-a-self-service-purchase"></a>Een selfservice aankoop doen

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Hoe doet een klant een selfservice aankoop?

Klanten kunnen online een selfservice-aankoop doen via de websites Microsoft Power BI, Power Apps en Power Automate. Klanten wordt eerst gevraagd een e-mailadres in te voeren om ervoor te zorgen dat ze een gebruiker zijn in een bestaande AD-tenant (Azure Active Directory). Vervolgens worden ze opgedragen om in te loggen met hun Azure AD-referenties. Na het aanmelden wordt de klant gevraagd om te selecteren hoeveel abonnementen hij wil kopen en creditcardbetalingen te verstrekken. Wanneer de aankoop is voltooid, kunnen ze hun abonnement gaan gebruiken. De koper zal ook toegang hebben tot een beperkt overzicht van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum,</a> waar hij of zij andere mensen in hun organisatie in staat kan stellen het product te gebruiken.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Wat zijn de betalingsmogelijkheden voor zelfbedieningsaankopen?

Momenteel is creditcard de enige beschikbare betaalmethode. Betaling via facturatie wordt niet ondersteund.

### <a name="who-can-buy-through-self-service-purchase"></a>Wie kan kopen via self-service aankoop?

Elke gebruiker met een niet-gastgebruikersaccount in een beheerde Azure AD-tenant kan kopen. Deze mogelijkheid is op dit moment niet beschikbaar voor huurders die overheids-, non-profitorganisaties of onderwijs zijn. Als dit van toepassing is op uw organisatie, is er op dit moment geen extra actie vereist om de aankoop van selfservice te beheren.

Gebruikers in organisaties of markten die niet in aanmerking komen voor selfservice-aankopen, zien een bericht waarin ze worden gevraagd contact op te nemen met hun IT-beheerder zoals ze dat nu doen.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Kunnen gastgebruikers kopen via selfservice-aankoop?

Nee, gastgebruikers kunnen een selfservice-aankoop niet voltooien in een tenant waarin ze te gast zijn.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Kunnen gebruikers worden gesynchroniseerd met een on-premises Active Directory-aankoop via selfservice-aankopen?

Als een gebruiker een actief gebruikersaccount heeft in een in aanmerking komende Azure AD-tenant, kan hij een zelfservice-aankoop voltooien.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Aan wie kunnen zelfservicekopers licenties toewijzen?

Selfservice-kopers kunnen alleen licenties toewijzen aan gebruikers in dezelfde Azure AD-tenant. De koper heeft toegang tot een beperkt zicht op het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum</a> om licenties toe te wijzen. Ze hebben alleen zichtbaarheid en kunnen licenties toewijzen aan die producten die ze hebben gekocht via selfservice-aankopen en ze kunnen deze licenties alleen toewijzen aan gebruikers in dezelfde Azure AD-tenant.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Waar ziet en beheert de selfservice-koper zijn aankopen?

Selfservice-kopers kunnen hun aankopen beheren in de beperkte weergave van het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum.</a> Kopers kunnen altijd naar het beheercentrum gaan via de tegel **Beheerder** in de startprogramma voor Office 365-apps die zijn ingebouwd in alle online apps van Office 365 en Dynamics. Ze kunnen de aankopen bekijken die ze hebben gedaan, extra abonnementen op dezelfde service kopen en licenties voor die abonnementen toewijzen aan andere gebruikers in hun organisatie. Bovendien kunnen kopers hun factuur bekijken en betalen, hun betalingsmethode bijwerken en hun abonnement opzeggen.

**Bekijk het beperkte Microsoft 365-beheercentrum voor selfservicekopers:**

![Microsoft 365 admin center screenshot.](../../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>Prijzen

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Wat zijn de prijzen voor selfservice-aankopen?

Prijzen voor elk van de Power Platform-producten voor zelfbedieningsaankopen zijn beschikbaar op de Microsoft-website en worden ook weergegeven als onderdeel van de afrekenervaring terwijl u een selfservice-aankoop doet. Deze prijzen kunnen afwijken van de prijzen die een organisatie betaalt bij het doen van centrale aankopen of prijzen aangeboden via een partner.

### <a name="who-is-responsible-for-payment"></a>Wie is verantwoordelijk voor de betaling?

De persoon die het abonnement koopt via selfservice aankoop wordt gefactureerd en is verantwoordelijk voor de betaling op basis van de voorwaarden en prijzen van de aankoop.

## <a name="admin-capabilities"></a>Beheerdersmogelijkheden

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Welke mogelijkheden heeft een beheerder voor zelfserviceaankopen?

Beheerders kunnen alle zelfserviceaankopen in hun organisatie bekijken in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum.</a> Ze kunnen het product, de naam van de koper, gekochte abonnementen, vervaldatum, ordergeschiedenis, aankoopprijs en toegewezen gebruikers zien voor elke zelfserviceaankoop. In het Power Platform Admin Center kunnen beheerders ook de capaciteit voor zelfserviceaankopen bekijken. Indien nodig voor hun organisatie, kunnen beheerders de aankoop van selfservice per product uitschakelen via PowerShell. Beheerders hebben hetzelfde beleid voor gegevensbeheer en toegang ten opzichte van producten die zijn gekocht via zelfserviceaankopen of centraal.

Beheerders kunnen ook bepalen of gebruikers in hun organisatie zelfserviceaankopen kunnen doen. Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module voor](allowselfservicepurchase-powershell.md)meer informatie.

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Hoe respecteert Microsoft gegevensbeheer en compliance door selfservice-aankopen mogelijk te maken?

Beheerders houden controle over welke services en producten binnen hun tenant zijn ingeschakeld op basis van hun vereisten voor gegevensbeheer en naleving. Bovendien zijn alle beleid voor gegevensbeheer en toegang, die uw organisatie heeft ingeschakeld, van toepassing op selfservice-ingekochte services.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Wie is eigenaar van de productgegevens die zijn gemaakt van zelfbedieningsaankopen?

Gegevens die zijn gemaakt van producten die via selfservice-aankoop zijn gekocht, worden eigendom van en worden beheerd door de organisatie.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Hoe centraliseer ik de aankopen via selfservice-aankopen?

Beheerders kunnen bestaande licenties toewijzen of extra abonnementen van Power Platform-producten (Power BI, Power Apps en Power Automate) aanschaffen via bestaande overeenkomsten en prijzen voor gebruikers die zijn toegewezen aan zelfserviceaankopen. Na het toewijzen van deze centraal aangeschafte licenties kunnen beheerders vervolgens vragen dat de kopers hun bestaande abonnementen opzeggen. Microsoft onderzoekt manieren om dit proces voor beheerders in de toekomst te vereenvoudigen en te stroomlijnen.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Waar ziet de beheerder zelfbedieningsaankopen?

Globale en factureringsbeheerders kunnen abonnementen zien die zijn gekocht via selfserviceaankopen in **Billing** > **Products &-services** in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum,</a> samen met alle andere abonnementen die via centrale aanbestedingen zijn gekocht. Ze kunnen de lijst filteren op alleen de abonnementen die via centrale aanbestedingen zijn gekocht of abonnementen bevatten die via selfservice-aankoop zijn gekocht.

Beheerders kunnen het product, de naam van de koper, gekocht abonnement, vervaldatum, bestelgeschiedenis, de aankoopprijs en toegewezen gebruikers zien.

## <a name="support-and-training"></a>Ondersteuning en training

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Wordt van de IT-afdelingen of partners van klanten verwacht dat ze producten ondersteunen die via selfservice-aankopen zijn gekocht?

VAN IT-afdelingen en partners wordt niet verwacht dat ze ondersteuning bieden voor producten die via selfservice-aankopen zijn gekocht. Microsoft biedt standaardondersteuning voor selfservicekopers.

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>Als een selfservice-koper ondersteuning aanroept, zullen ze dan gebruik maken van de Premier support-incidenten van de klant?

Selfservice-kopers gebruiken de Premier Support-incidenten van een klant niet voor het ontvangen van ondersteuning voor hun zelfbedieningsaankopen.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Hoe worden gebruikers geacht training te krijgen over de producten die ze kopen via selfservice-aankoop?

Uitgebreide training voor gebruikers wordt aangeboden op de websites Microsoft Power BI, Power Apps en Power Automate. De producten hebben begeleid leren, documentatie, monsters en sterke gemeenschappen om antwoorden en tips rechtstreeks van andere gebruikers te krijgen.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Wat gebeurt er met een selfservice-aankoop als een gebruiker de organisatie verlaat?

Geldige gebruikers zullen de selfservice-aankoop volledig blijven gebruiken voor de duur van het abonnement. Het abonnement blijft actief totdat de koper het abonnement rechtstreeks opzegt of een beheerder vraagt om het abonnement op te zeggen via de klantenservice. Beheerders kunnen er ook voor kiezen om een centraal aangeschafte licentie toe te wijzen aan gebruikers van het geannuleerde abonnement.

## <a name="partners"></a>Partners

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Wat is de rol van Microsoft's partners in selfservice-aankopen?

Partners die beheerbevoegdheden hebben gedelegeerd, kunnen zelfserviceaankopen zien in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum,</a>net als een beheerder. Partners kunnen helpen bij het ondersteunen van een organisatie die producten wil centraliseren die zijn gekocht via zelfbedieningsaankopen. Daarnaast kunnen partners oplossingen bieden om de mogelijkheden van een selfservice-aankoop uit te breiden.

## <a name="country-and-region-availability"></a>Beschikbaarheid land en regio

### <a name="in-which-countries-and-regions-can-i-make-a-self-service-purchase"></a>In welke landen en regio's kan ik een selfservice aankoop doen?

Self-service aankopen zijn beschikbaar in de volgende landen en regio's: Afghanistan, Åland Eilanden, Albanië, Algerije, Amerikaans Samoa, Andorra, Angola, Anguilla, Antarctica, Antigua en Barbuda, Argentinië, Armenië, Aruba, Australië, Oostenrijk, Azerbeidzjan, Bahama's, Bahrein, Bangladesh, Barbados, Wit-Rusland, België, Bulgarije, Belize, Benin, Bermuda, Bhutan, Bolivia, Bonaire, Sint Eustatius en Saba, Bosnië en Herzegovina, Botswana, Bouvet Island, Brazilië, Brits indische Oceaan territorium, Brits Maagdeneilanden, Brunei, Burkina Faso, Burundi, Cabo Verde, Cambodja, Kameroen, Canada, Kaaimaneilanden, Centraal-Afrikaanse Republiek, Tsjaad, Chili, China, Christmas Island, Cocos (Keeling) Eilanden, Colombia, Comoren, Congo, Congo (DRC), Cookeilanden, Costa Rica, Ivoorkust, Kroatië, Cyprus, Curaçao, Tsjechië, Denemarken, Djibouti, Dominica, Dominicaanse Republiek, Ecuador, Egypte, El Salvador, Equatoriaal-Guinea, Eritrea, Estland, Ethiopië, Falklandeilanden, Faeröer, Fiji, Finland, Frankrijk, Frans-Guyana, Frans-Polynesië, Franse zuidelijke gebieden, Gabon, Gambia, Georgië, Duitsland, Ghana, Gibraltar, Groenland, Griekenland, Grenada, Guadeloupe, Guam, Guatemala, Guernsey, Guinee, Guinee-Bissau, Guyana, Haïti, Heard Island en McDonald Islands, Honduras, Hong Kong SAR, Hongarije, IJsland, Indonesië, Irak, Ierland, Isle of Man, Israël, Italië, Jamaica, Japan, Jersey, Jordanië, Kazachstan, Kenia, Kiribati, Korea, Kosovo, Koeweit, Kirgizië, Laos, Letland, Libanon, Lesotho, Liberia, Libië, Liechtenstein, Litouwen, Luxemburg, Macao SAR, Madagaskar, Malawi, Maleisië, Malediven, Mali, Malta, Marshalleilanden, Martinique, Mauritanië, Mauritius, Mayotte, Mexico, Micronesië, Moldavië, Monaco, Mongolië, Montenegro, Montserrat, Marokko, Mozambique, Myanmar, Namibië, Nauru, Nepal, Nederland, Nieuw-Caledonië, Nieuw-Zeeland, Nicaragua, Niger, Nigeria, Niue, Norfolk Island, Noord-Macedonië, Noord-Marianen, Noorwegen, Oman, Pakistan, Palau, Palestijnse Autoriteit, Panama, Papoea-Nieuw-Guinea, Paraguay, Peru, Filippijnen, Pitcairn eilanden, Polen, Portugal, Puerto Rico, Qatar, Réunion, Roemenië, Rusland, Rwanda, Saint Barthélemy, Saint Kitts en Nevis, Saint Lucia, Saint Martin, Saint Pierre en Miquelon, Saint Vincent en de Grenadines, Samoa, San marino, São Tomé en Príncipe, Saoedi-Arabië, Senegal, Servië, Seychellen, Sierra Leone, Singapore, Sint Maarten, Slowakije, Slovenië, Salomonseilanden, Somalië, Zuid-Afrika, Zuid-Georgië en Zuid-Sandwich eilanden, Zuid-Soedan, Spanje, Sri Lanka, St Helena, Ascension, Tristan da Cunha, Suriname, Svalbard en Jan Mayen, Swaziland, Zweden, Zwitserland, Taiwan, Tadzjikistan, Tanzania, Thailand, Timor-Leste, Togo, Tokelau, Tonga, Trinidad en Tobago, Tunesië, Turkije, Turkmenistan, Turken en Caicos eilanden, Tuvalu, Amerikaanse afgelegen eilanden, VS. Maagdeneilanden, Oeganda, Oekraïne, Verenigde Arabische Emiraten, Verenigd Koninkrijk, Verenigde Staten, Uruguay, Oezbekistan, Vanuatu, Vaticaanstad, Venezuela, Vietnam, Wallis en Futuna, Jemen, Zambia en Zimbabwe.