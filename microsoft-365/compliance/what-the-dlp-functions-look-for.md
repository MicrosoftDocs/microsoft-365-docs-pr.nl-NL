---
title: Waar de functies voor preventie van gegevensverlies (DLP) naar zoeken
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: Meer informatie over de functies voor preventie van gegevensverlies (DLP).
ms.openlocfilehash: 787abc1e7fb4c95392a76f7514ceffd3f7f4dda0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288093"
---
# <a name="what-the-dlp-functions-look-for"></a>Doel van de DLP-functies

DLP-beleid (Data Loss Prevention) kan gevoelige informatietypen gebruiken om gevoelige items te identificeren. Creditcardnummer en EU-betaalkaartnummer zijn voorbeelden van gevoelige informatietypen. Gevoelige informatietypen zoeken naar specifieke patronen. Gevoelige informatietypen valideren de gegevens door te kijken naar de indeling, de checksums en het zoeken naar relevante trefwoorden of andere informatie. Sommige van deze functies worden uitgevoerd door interne functies. Het type gevoelige gegevens creditcardnummer gebruikt bijvoorbeeld een functie om te zoeken naar datums die zijn opgemaakt als een vervaldatum. Dit helpt om te bevestigen dat een nummer een creditcardnummer is.

In dit artikel wordt uitgelegd waar deze functies naar zoeken, om u te helpen begrijpen hoe de vooraf gedefinieerde typen gevoelige informatie werken. Zie Entiteitsdefinities [van het type Gevoelige informatie voor meer informatie](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>Tabel met functies

<br>

****

|functienaam|functieactie|is een validator|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|detecteert en valideert Argentina Unique tax key|nee|
|Func_aba_routing|detecteert ABA-routeringsnummer|ja|
|Func_alabama_drivers_license_number|detecteert het nummer van het rijbewijs van Alabama|nee|
|Func_alaska_delaware_oregon_drivers_license_number|detecteert het nummer van het rijbewijs van Alaska, Delaware, Oregon|nee|
|Func_alaska_drivers_license_number|detecteert het nummer van het rijbewijs van Alaska|nee|
|Func_alberta_drivers_license_number|detecteert het licentienummer van Alberta|nee|
|Func_Argentina_Unique_Tax_Key|detecteert Argentina Unique tax key|nee|
|Func_arizona_drivers_license_number|detecteert het nummer van het rijbewijs van Arizona|nee|
|Func_arkansas_drivers_license_number|detecteert het rijbewijsnummer van Arkansas|nee|
|Func_australian_business_number|detecteert het australische bedrijfsnummer|nee|
|Func_Australian_Company_Number|detecteert het bedrijfsnummer van Australië|nee|
|Func_australian_medical_account_number|detecteert het nummer van het medische account van Australië|nee|
|Func_australian_tax_file_number|detecteert belastingbestandsnummer van Australië|ja|
|Func_austria_eu_ssn_or_equivalent|detecteert Oostenrijks sociaal-zekerheidsnummer|nee|
|Func_austria_eu_tax_file_number|detecteert oostenrijks belastingbestandsnummer|nee|
|Func_Austria_Value_Added_Tax|detecteert Oostenrijks belasting over toegevoegde waarde|nee|
|Func_belgium_national_number|detecteert het nationale nummer van België|nee|
|Func_belgium_value_added_tax_number|detecteert belgië btw-nummer|nee|
|Func_brazil_cnpj|detecteert brazil legal entity number (CNPJ)|ja|
|Func_brazil_cpf|detecteert Brazilië CPF|ja|
|Func_brazil_rg|detecteert Brazilië RG|nee|
|Func_british_columbia_drivers_license_number|detecteert het nummer van het rijbewijs van British Columbia|nee|
|Func_bulgaria_eu_national_id_card|detecteert een uniform burgerlijk nummer van Bulgarije|nee|
|Func_california_drivers_license_number|detecteert het nummer van het rijbewijs van Californië|nee|
|Func_canadian_sin|detecteert Canada sin|ja|
|Func_chile_id_card|detecteert Chili-id-kaart|nee|
|Func_china_resident_id|detecteert in China woonachtige id|nee|
|Func_colorado_drivers_license_number|detecteert het rijbewijsnummer van Colorado|nee|
|Func_connecticut_drivers_license_number|detecteert het nummer van het rijbewijs van Connecticut|nee|
|Func_credit_card|detecteert creditcard|ja|
|Func_croatia_id_card|detecteert Kroatië-id-kaart|nee|
|Func_croatia_oib_number|detecteert Het OIB-nummer van Kroatië|nee|
|Func_cyprus_eu_tax_file_number|detecteert cyprus belastingbestandsnummer|nee|
|Func_czech_id_card|detecteert Tsjechische id-kaart|nee|
|Func_czech_id_card_new_format|detecteert Tsjechische id-kaart in nieuwe indeling|nee|
|Func_dea_number|detecteert DEA-getal|ja|
|Func_denmark_eu_tax_file_number|detecteert het persoonlijke identificatienummer van Denemarken|nee|
|Func_district_of_columbia_drivers_license_number|detecteert het rijbewijsnummer van District of Columbia|nee|
|Func_estonia_eu_national_id_card|detecteert estlandse persoonlijke identificatiecode|nee|
|Func_eu_debit_card|detecteert eu-betaalkaart|nee|
|Func_finnish_national_id|detecteert finse nationale id|nee|
|Func_florida_drivers_license_number|detecteert het nummer van het rijbewijs van Florida|nee|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detecteert Het rijbewijsnummer van Florida, Maryland, Michigan en Minnesota|nee|
|Func_formatted_itin|detecteert opgemaakte US ITIN|ja|
|Func_fr_insee|detecteert France INSEE|nee|
|Func_fr_passport|detecteert Frankrijk-paspoort|nee|
|Func_france_eu_tax_file_number|detecteert frankrijks belastingbestandsnummer|nee|
|Func_france_value_added_tax_number|detecteert frankrijks btw-nummer|nee|
|Func_french_drivers_license|detecteert Frans rijbewijs|nee|
|Func_french_insee|detecteert Franse INSEE|nee|
|Func_georgia_drivers_license_number|detecteert het nummer van het rijbewijs van Georgia|nee|
|Func_german_drivers_license|detecteert het rijbewijs van Duitsland|nee|
|Func_german_passport|detecteert Duitsland-paspoort|nee|
|Func_german_passport_data|detecteert Duitsland-paspoort|nee|
|Func_germany_eu_tax_file_number|detecteert belastingbestandsnummer van Duitsland|nee|
|Func_germany_value_added_tax_number|detecteert duitsland btw-nummer|nee|
|Func_greece_eu_ssn|detecteert Griekenland sin (AMKA)|nee|
|Func_hawaii_drivers_license_number|detecteert het rijbewijsnummer van Hawaii|nee|
|Func_hong_kong_id_card|detecteert Hong Kong-id-kaart|nee|
|Func_hungarian_value_added_tax_number|detecteert het btw-nummer van Hongarije|nee|
|Func_hungary_eu_national_id_card|detecteert het persoonlijke identificatienummer van Hongarije|nee|
|Func_hungary_eu_ssn_or_equivalent|detecteert hongarijese sociale zekerheidsnummer|nee|
|Func_hungary_eu_tax_file_number|detecteert het belastingbestandsnummer van Hongarije|nee|
|Func_iban|detecteert IBAN|ja|
|Func_idaho_drivers_license_number|detecteert het nummer van het Idaho-rijbewijs|nee|
|Func_illinois_drivers_license_number|detecteert het rijbewijsnummer van Illinois|nee|
|Func_india_aadhaar|detecteert India aadhaar|ja|
|Func_indiana_drivers_license_number|detecteert het nummer van het Rijbewijs van Indiana|nee|
|Func_iowa_drivers_license_number|detecteert het nummer van het rijbewijs van Iowa|nee|
|Func_ireland_pps|detecteert Ireland PPS|nee|
|Func_israeli_national_id_number|detecteert het nationale id-nummer van Israël|nee|
|Func_italy_eu_national_id_card|detecteert fiscale code van Italië|nee|
|Func_italy_value_added_tax_number|detecteert italië btw-nummer|nee|
|Func_japanese_my_number_corporate|detecteert Japan mijn nummer bedrijf|ja|
|Func_japanese_my_number_personal|detecteert Japan mijn nummer persoonlijk|ja|
|Func_jp_bank_account|detecteert japanse bankrekening|nee|
|Func_jp_bank_account_branch_code|detecteert de Japanse bankaccount branch code|nee|
|Func_jp_drivers_license_number|detecteert japans rijbewijsnummer|nee|
|Func_jp_passport|detecteert Japans paspoort|nee|
|Func_jp_resident_registration_number|detecteert registratienummer in Japan|nee|
|Func_jp_sin|detecteert Japan SIN|nee|
|Func_jp_sin_pre_1997|detecteert Japan sin pre 1997|nee|
|Func_kansas_drivers_license_number|detecteert het nummer van het Kansas-rijbewijs|nee|
|Func_kentucky_drivers_license_number|detecteert het rijbewijsnummer van Kentucky|nee|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detecteert Het rijbewijsnummer van Kentucky, Massachusetts, Virginia|nee|
|Func_latvia_eu_national_id_card|detecteert persoonlijke code letland|nee|
|Func_lithuania_eu_tax_file_number|detecteert persoonlijke code van Litouwen|nee|
|Func_louisiana_drivers_license_number|detecteert het nummer van het rijbewijs van Louisiana|nee|
|Func_luxemburg_eu_tax_file_number|detecteert luxemburgs nationaal identificatienummer (natuurlijke personen)|nee|
|Func_luxemburg_eu_tax_file_number_non_natural|detecteert luxemburgs nationaal identificatienummer (niet-natuurlijke personen)|nee|
|Func_maine_drivers_license_number|detecteert het rijbewijsnummer van Maine|nee|
|Func_manitoba_drivers_license_number|detecteert manitoba-rijbewijsnummer|nee|
|Func_maryland_drivers_license_number|detecteert het nummer van het rijbewijs van Maryland|nee|
|Func_massachusetts_drivers_license_number|detecteert het nummer van het rijbewijs van Massachusetts|nee|
|Func_mexico_population_registry_code|detecteert De bevolkingsregistercode van Mexico|nee|
|Func_michigan_minnesota_drivers_license_number|detecteert het rijbewijsnummer van Michigan, Minnesota|nee|
|Func_minnesota_drivers_license_number|detecteert het nummer van het rijbewijs van Minnesota|nee|
|Func_mississippi_oklahoma_drivers_license_number|detecteert Mississippi, rijbewijsnummer van Oklahoma|nee|
|Func_missouri_drivers_license_number|detecteert het rijbewijsnummer van Missouri|nee|
|Func_montana_drivers_license_number|detecteert het nummer van het rijbewijs van Montana|nee|
|Func_nebraska_drivers_license_number|detecteert het licentienummer van Nebraska|nee|
|Func_netherlands_bsn|detecteert Nederlandse BSN|nee|
|Func_netherlands_eu_tax_file_number|detecteert nederlandse belastingbestandsnummer|nee|
|Func_netherlands_value_added_tax_number|detecteert het nederlandse btw-nummer|nee|
|Func_nevada_drivers_license_number|detecteert het nummer van het rijbewijs van Nevada|nee|
|Func_new_brunswick_drivers_license_number|detecteert het rijbewijsnummer van New Brunswick|nee|
|Func_new_hampshire_drivers_license_number|detecteert het nummer van het rijbewijs van New Hampshire|nee|
|Func_new_jersey_drivers_license_number|detecteert het nummer van het rijbewijs van New Jersey|nee|
|Func_new_mexico_drivers_license_number|detecteert het rijbewijsnummer van New Mexico|nee|
|Func_new_york_drivers_license_number|detecteert het rijbewijsnummer van New York|nee|
|Func_new_zealand_bank_account_number|detecteert nieuw-Zeelands bankrekeningnummer|nee|
|Func_new_zealand_inland_revenue_number|detecteert nieuw-Zeelandse binnenlandomzetnummer|nee|
|Func_new_zealand_ministry_of_health_number|detecteert het nummer van het Ministerie van Gezondheid van Nieuw-Zeeland|nee|
|Func_newfoundland_labrador_drivers_license_number|detecteert het rijbewijsnummer van Newfoundland Labrador|nee|
|Func_newzealand_driver_license_number|detecteert nieuw-Zeelands rijbewijsnummer|nee|
|Func_newzealand_social_welfare_number|detecteert nieuw-Zeelandse sociaal-sociale zekerheidsnummer|nee|
|Func_north_carolina_drivers_license_number|detecteert het nummer van het rijbewijs van North Carolina|nee|
|Func_north_dakota_drivers_license_number|detecteert het nummer van het rijbewijs van North Dakota|nee|
|Func_norway_id_number|detecteert noorwegen-id-nummer|nee|
|Func_nova_scotia_drivers_license_number|detecteert het nummer van het rijbewijs van Nova Scotia|nee|
|Func_ohio_drivers_license_number|detecteert het rijbewijsnummer van Ohio|nee|
|Func_ontario_drivers_license_number|detecteert het rijbewijsnummer van Ontario|nee|
|Func_pennsylvania_drivers_license_number|detecteert het rijbewijsnummer van Pennsylvania|nee|
|Func_pesel_identification_number|detecteert nationale polen-id (PESEL)|nee|
|Func_poland_eu_tax_file_number|detecteert polen belastingbestandsnummer|nee|
|Func_polish_national_id|detecteert Polen-identiteitskaart|nee|
|Func_polish_passport_number|detecteert Pools paspoortnummer|nee|
|Func_polish_regon_number|detecteert Pools REGON-getal|nee|
|Func_portugal_eu_tax_file_number|detecteert Portugal Tax Identification Number|nee|
|Func_prince_edward_island_drivers_license_number|detecteert het rijbewijsnummer van Prince Edward Island|nee|
|Func_quebec_drivers_license_number|detecteert het rijbewijsnummer van Quebec|nee|
|Func_randomized_formatted_ssn|detecteert gerandomiseerde opgemaakte US SSN|ja|
|Func_randomized_unformatted_ssn|detecteert gerandomiseerde, niet-opgemaakte US SSN|ja|
|Func_rhode_island_drivers_license_number|detecteert het nummer van het rijbewijs van Rhode Island|nee|
|Func_romania_eu_national_id_card|detecteert roemenië persoonlijke numerieke code (CNP)|nee|
|Func_saskatchewan_drivers_license_number|detecteert saskatchewan-rijbewijsnummer|nee|
|Func_slovakia_eu_national_id_card|detecteert het persoonlijke nummer van Slowakije|nee|
|Func_slovenia_eu_national_id_card|detecteert Slovenië Unique Master Citizen Number|nee|
|Func_slovenia_eu_tax_file_number|detecteert het belastingbestandsnummer van Slovenië|nee|
|Func_south_africa_identification_number|detecteert het identificatienummer van Zuid-Afrika|ja|
|Func_south_carolina_drivers_license_number|detecteert het nummer van het rijbewijs van South Carolina|nee|
|Func_south_dakota_drivers_license_number|detecteert het nummer van het rijbewijs van South Dakota|nee|
|Func_south_korea_resident_number|detecteert het ingezetenenummer van Zuid-Korea|nee|
|Func_spain_eu_DL_and_NI_number_citizen|detecteert spanje DL en NI-nummer burger|nee|
|Func_spain_eu_DL_and_NI_number_foreigner|detecteert Spanje DL en NI-nummer buitenlander|nee|
|Func_spain_eu_driver is s_license_number|detecteert het spaanse nummer van het rijbewijs|nee|
|Func_spain_eu_tax_file_number|detecteert het belastingbestandsnummer van Spanje|nee|
|Func_spanish_social_security_number|detecteert Spaans sociaal-zekerheidsnummer|nee|
|Func_ssn|Functie om niet-gerandomiseerde opgemaakte US SSN te detecteren|ja|
|Func_sweden_eu_tax_file_number|detecteert belastingbestandsnummer zweden|nee|
|Func_swedish_national_identifier|detecteert Zweedse nationale id|ja|
|Func_swiss_social_security_number_ahv|detecteert Het Zwitserse sociale zekerheidsnummer AHV|nee|
|Func_taiwanese_national_id|detecteert een Taiwanese nationale id|nee|
|Func_tennessee_drivers_license_number|detecteert het nummer van het rijbewijs van Tennessee|nee|
|Func_texas_drivers_license_number|detecteert het nummer van het rijbewijs van Texas|nee|
|Func_Thai_Citizen_Id|detecteert Thaise burger-id|nee|
|Func_Turkish_National_Id|detecteert Turkse nationale id|ja|
|Func_uk_drivers_license|detecteert vk-rijbewijs|nee|
|Func_uk_eu_tax_file_number|detecteert het unieke nummer van de Britse belastingbetaler|nee|
|Func_uk_nhs_number|detecteert UK NHS-nummer|ja|
|Func_uk_nino|detecteert UK NINO|nee|
|Func_unformatted_canadian_sin|detecteert niet-opgemaakte Canadese SIN|nee|
|Func_unformatted_itin|detecteert unformatted US ITIN|ja|
|Func_unformatted_ssn|detecteert niet-gerandomiseerde, niet-opgemaakte US SSN|ja|
|Func_usa_uk_passport|detecteert vs- en Vk-paspoort|ja|
|Func_utah_drivers_license_number|detecteert het nummer van het rijbewijs van Utah|nee|
|Func_vermont_drivers_license_number|detecteert het nummer van het rijbewijs van Vermont|nee|
|Func_virginia_drivers_license_number|detecteert het nummer van het rijbewijs van Virginia|nee|
|Func_washington_drivers_license_number|detecteert het rijbewijsnummer van Washington|nee|
|Func_west_virginia_drivers_license_number|detecteert het nummer van het rijbewijs van West Virginia|nee|
|Func_wisconsin_drivers_license_number|detecteert het rijbewijsnummer van Wisconsin|nee|
|Func_wyoming_drivers_license_number|detecteert het licentienummer van Wyoming|nee|
|

## <a name="func_us_date"></a>Func_us_date

Func_us_date zoekt naar datums in veelgebruikte Amerikaanse indelingen. De algemene notaties zijn 'maand/dag/jaar', 'maanddag-jaar' en 'maanddagjaar'. De namen of afkortingen van maanden zijn niet case-sensitive.

Voorbeelden:

- 2 december 2016
- 2 december 2016
- dec 02 2016
- 12/2/2016
- 12/02/16
- Dec-2-2016
- 12-2-16

Geaccepteerde maandnamen:

- Engels
  - Januari, februari, maart, april, mei, juni, juli, augustus, september, oktober, november, december
  - Jan. Feb. Mar. Apr. Mei juni juli aug. Sept. Okt. nov. dec.

## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates zoekt naar datums in veelvoorkomende E.U. notaties (en de meeste plaatsen buiten de Verenigde Staten), zoals 'dag/maand/jaar', 'dagmaand-jaar' en 'dagmaandjaar'. De namen of afkortingen van maanden zijn niet case-sensitive.

Voorbeelden:

- 2 december 2016
- 02 dec 2016
- 2 dec 16
- 2/12/2016
- 02/12/16
- 2-dec-2016
- 2-12-16

Geaccepteerde maandnamen:

- Engels
  - Januari, februari, maart, april, mei, juni, juli, augustus, september, oktober, november, december
  - Jan. Feb. Mar. Apr. Mei juni juli aug. Sept. Okt. nov. dec.
- Dutch
  - januari, februari, maart, april, mei, juni, juli, augustus, september, ocktober, oktober, november, december
  - jan feb maart apr mei jun jul aug sep sept okt nov dec
- French
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
  - janv. févr. mars avril mai juin juil. août sept. okt. nov. déc.
- German
  - jänuar, februari, märz, april, mei, juni juli, augustus, september, oktober, november, dezember
  - Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.
- Italian
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
  - genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.
- Portugees
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez
- Spanish
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. okt. nov. dic.

## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (afgeschaft)

> [!NOTE]
> Deze functie wordt afgeschaft omdat deze alleen Portugese maandnamen ondersteunt, die nu zijn opgenomen in de  `Func_eu_date` bovenstaande functie.

Deze functie zoekt naar een datum in de notatie die vaak in het Portugees wordt gebruikt. De notatie voor deze functie is hetzelfde als , die alleen verschilt  `Func_eu_date` in de gebruikte taal.

Voorbeelden:

- 2 Dez 2016
- 02 dez 2016
- 2 Dez 16
- 2/12/2016
- 02/12/16
- 2-Dez-2016
- 2-12-16

Geaccepteerde maandnamen:

- Portugees
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
  - jan fev mar abr mai jun jul ago set out nov dez

## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (afgeschaft)

> [!NOTE]
> Deze functie wordt afgeschaft omdat deze alleen Nederlandse maandnamen ondersteunt, die nu zijn opgenomen in de  `Func_eu_date` bovenstaande functie.

Deze functie zoekt naar een datum in de indeling die veel wordt gebruikt in het Nederlands. De notatie voor deze functie is hetzelfde als , die alleen verschilt  `Func_eu_date` in de gebruikte taal.

Voorbeelden:

- 2 mei 2016
- 02 mei 2016
- 2 mei 16
- 2/12/2016
- 02/12/16
- 2-mei-2016
- 2-12-16

Geaccepteerde maandnamen:

- Dutch
  - januari, februari, maart, april, mei, juni, juli, augustus, september, ocktober, oktober, november, december
  - jan feb maart apr mei jun jul aug sep sep out okt nov dec

## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date zoekt naar datums die worden gebruikt in de indelingen die vaak worden gebruikt door creditcards en betaalkaarten. Deze functie komt overeen met datums in de notatie 'maand/jaar', 'maandjaar', '[maandnaam] jaar' en '[maand afkorting] jaar". De namen of afkortingen van maanden zijn niet case-sensitive.

Voorbeelden:

- MM/YY, bijvoorbeeld 01-11 of 1-11
- MM/YYYY -- bijvoorbeeld 01-2011 of 1-2011
- MM-YY, bijvoorbeeld 01-22 of 1-11
- MM-YYYY, bijvoorbeeld 01-2000 of 1-2000

De volgende indelingen ondersteunen YY of YYYY:

- Month-YYY -- bijvoorbeeld jan-2010 of januari-2010 of 10 januari-10
- Maand YYY, bijvoorbeeld 'januari 2010' of '10 januari' of '10 januari' of '10 januari'
- MonthYYYY -- bijvoorbeeld 'januari2010' of 'Jan2010' of 'januari10' of 'Jan10'
- Month/YYYY -- bijvoorbeeld 'januari/2010' of 'Jan/2010' of 'januari/10' of '10 januari'

Geaccepteerde maandnamen:

- Engels
  - Januari, februari, maart, april, mei, juni, juli, augustus, september, oktober, november, december
  - Jan feb mar apr mei juni juli aug sept nov dec

## <a name="func_us_address"></a>Func_us_address

Func_us_address zoekt naar een Amerikaanse staatsnaam of postcode, gevolgd door een geldige postcode. De postcode moet een van de juiste postcodes zijn die zijn gekoppeld aan de Amerikaanse staatsnaam of afkorting. De Amerikaanse staatsnaam en postcode kunnen niet worden gescheiden door interpunctie of letters.

Voorbeelden:

- Washington 98052
- Washington 98052-9998
- WA 98052
- WA 98052-9998
