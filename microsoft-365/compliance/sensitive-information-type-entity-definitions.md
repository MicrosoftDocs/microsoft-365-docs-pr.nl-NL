---
title: Definities van entiteiten van het type Gevoelige informatie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Er zijn 200 typen gevoelige informatie die u kunt gebruiken in uw DLP-beleid. In dit artikel worden al deze typen gevoelige informatie beschreven en wordt beschreven waar een DLP-beleid naar zoekt wanneer elk type wordt gedetecteerd.
ms.openlocfilehash: 614649367e72766d8df210fccbb4e3cdc9cdb4b6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287465"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definities van entiteiten van het type Gevoelige informatie

In dit artikel vindt u een overzicht van alle entiteitsdefinities van het type gevoelige informatie. Elke definitie laat zien waar een DLP-beleid naar zoekt om elk type te detecteren. Zie Gevoelige informatietypen voor meer informatie over [gevoelige informatietypen.](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>ABA-routeringsnummer

### <a name="format"></a>Opmaak

negen cijfers met een opgemaakt of niet-opgemaakt patroon

### <a name="pattern"></a>Patroon

- twee cijfers in het bereik 00-12, 21-32, 61-72 of 80
- twee cijfers
- een optioneel afbreekstreester
- vier cijfers
- een optioneel afbreekstreester
- een cijfer


### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een beleid heeft het medium vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_aba_routing inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_ABA_Routing gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_aba_routing inhoud die overeenkomt met het patroon.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba-getal
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- routering #
- routering nee
- routeringsnummer
- routeringsnummer
- routering #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Argentinië national identity (DNI) number

### <a name="format"></a>Opmaak

Acht cijfers met of zonder perioden

### <a name="pattern"></a>Patroon

Acht cijfers:
- twee cijfers
- een optionele periode
- drie cijfers
- een optionele periode
- drie cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_argentina_national_id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_argentina_national_id gevonden.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Nationale identiteitsnummer argentinië
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Argentina Unique Tax Identification Key (CUIT/CUIL)

### <a name="format"></a>Opmaak

11 cijfers met streepje

### <a name="pattern"></a>Patroon

11 cijfers met een streepje:
- twee cijfers in 20, 23, 24, 27, 30, 33 of 34
- een afbreekstreester (-)
- acht cijfers
- een afbreekstreester (-)
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_Argentina_Unique_Tax_Key` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een `Keyword_Argentina_Unique_Tax_Key` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_Argentina_Unique_Tax_Key` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- unieke code voor arbeidsidentificatie 
- Clave Única de Identificación Tributaria
- unieke arbeidsidentificatiecode
- CUIL
- Unieke belastingidentificatiecode
- Unieke arbeidsidentificatiesleutel
- Unieke sleutel voor arbeidsidentificatie
- Unieke werkidentificatiecode
- Unieke code voor werkidentificatie
- Unieke werkidentificatiesleutel
- Unieke sleutel voor werkidentificatie
- Unieke code voor belastingidentificatie
- Unieke sleutel voor belastingidentificatie
- Unieke arbeidsidentificatiecode
- Unieke code voor arbeidsidentificatie
- Unieke Labor Identification Key
- Unieke sleutel voor arbeidsidentificatie
- belasting-id
- taxID #
- taxId
- getaxidnummer
- btw-nummer
- belasting nee
- belasting #
- belasting #
- belastingbetaler-id
- nummer van de belastingbetaler
- belastingbetaler nee
- belastingbetaler #
- belastingbetaler #
- belastingidentiteit
- belastingidentificatie
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>Australië bankrekeningnummer

### <a name="format"></a>Opmaak

zes tot tien cijfers met of zonder banknummer

### <a name="pattern"></a>Patroon

Accountnummer is 6 tot 10 cijfers.

Nummer van de australische bankstaat:
- drie cijfers
- een afbreekstreester
- drie cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_australia_bank_account_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_australia_bank_account_number gevonden.
- De normale expressie Regex_australia_bank_account_number_bsb inhoud die overeenkomt met het patroon.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_australia_bank_account_number inhoud die overeenkomt met het patroon.

- Er wordt een trefwoord Keyword_australia_bank_account_number gevonden.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bankcode
- correspondentbank
- basisvaluta
- vs-account
- adres van de houder
- bankadres
- informatieaccount
- overboekingen van fondsen
- bankkosten
- bankgegevens
- bankgegevens
- volledige namen
- ie

## <a name="australia-business-number"></a>Bedrijfsnummer van Australië
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps


### <a name="format"></a>Opmaak

11 cijfers met optionele scheidingstekens

### <a name="pattern"></a>Patroon

11 cijfers met optionele scheidingstekens:

- twee cijfers
- een optioneel afbreekstreester of spatie
- drie cijfers
- een optioneel afbreekstreester of spatie
- drie cijfers
- een optioneel afbreekstreester of spatie
- drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_australian_business_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_australian_business_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_australian_business_number wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- Australia Business no
- zakelijk nummer
- abn #
- businessid #
- zakelijke id
- abn
- businessno #

## <a name="australia-company-number"></a>Australië bedrijfsnummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

negen cijfers met scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers met scheidingstekens:

- drie cijfers
- een spatie
- drie cijfers
- een spatie
- drie cijfers


### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_Australian_Company_Number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Australian_Company_Number gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_Australian_Company_Number wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- kan
- australia company no
- australia company no #
- australië bedrijfsnummer
- Australisch bedrijf nee
- Australisch bedrijf nee #
- Australisch bedrijfsnummer

## <a name="australia-drivers-license-number"></a>Australië rijbewijsnummer

### <a name="format"></a>Opmaak

negen letters en cijfers

### <a name="pattern"></a>Patroon

negen letters en cijfers:

- twee cijfers of letters (niet hoofdlettergevoelig)
- twee cijfers
- vijf cijfers of letters (niet hoofdlettergevoelig)

OF

- een tot twee optionele letters (niet hoofdlettergevoelig)
- vier tot negen cijfers

OF

- negen cijfers of letters (niet hoofdlettergevoelig)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_australia_drivers_license_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_australia_drivers_license_number gevonden.
- Er wordt geen trefwoord Keyword_australia_drivers_license_number_exclusions gevonden.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- internationale rijbewijzen
- Australische auto-vereniging
- internationaal rijbewijs
- DriverLicence
- DriverLicences
- Driver Lic
- Rijbewijs
- Rijbewijzen
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Rijbewijs
- Rijbewijzen
- Driver'Lic
- Driver'Lics
- Rijbewijs
- Rijbewijzen
- Driver' Lic
- Driver' Lics
- Rijbewijs
- Rijbewijzen
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Rijbewijs
- Rijbewijzen
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic #
- Driver Lics #
- Rijbewijs #
- Rijbewijzen #
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic #
- Drivers Lics #
- Rijbewijs #
- Rijbewijzen #
- Driver'Lic #
- Driver'Lics #
- Rijbewijs #
- Rijbewijzen #
- Driver' Lic #
- Driver' Lics #
- Rijbewijs #
- Rijbewijzen #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic #
- Driver's Lics #
- Rijbewijs #
- Rijbewijzen #

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Rijbewijs
- Licenties voor stuurprogramma's
- DriversLicense
- DriversLicenses
- Rijbewijs
- Licenties voor stuurprogramma's
- Rijbewijs
- Licenties voor stuurprogramma's
- Rijbewijs
- Rijbewijzen
- Driver'sLicense
- Driver'sLicenses
- Rijbewijs
- Rijbewijzen
- DriverLicense #
- DriverLicenses #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- DriversLicense #
- DriversLicenses #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Rijbewijs #
- Rijbewijzen #
- Driver'sLicense #
- Driver'sLicenses #
- Rijbewijs #
- Rijbewijzen #

## <a name="australia-medical-account-number"></a>Nummer van medische rekening australië

### <a name="format"></a>Opmaak

10-11 cijfers

### <a name="pattern"></a>Patroon

10-11 cijfers:
- Het eerste cijfer is in het bereik 2-6
- Negende cijfer is een vinkje
- Tiende cijfer is het probleemcijfer
- Het elfde cijfer (optioneel) is het afzonderlijke getal

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_australian_medical_account_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Australia_Medical_Account_Number gevonden.
- De checksum passeert.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bankrekeninggegevens
- medicare payments
- hypotheekaccount
- bankbetalingen
- informatietak
- creditcardlening
- afdeling personeelsdiensten
- lokale service
- hospik


## <a name="australia-passport-number"></a>Australië paspoortnummer

### <a name="format"></a>Opmaak

acht of negen alfanumerieke tekens

### <a name="pattern"></a>Patroon

- één letter (N, E, D, F, A, C, U, X), gevolgd door zeven cijfers of
- Twee letters (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ), gevolgd door zeven cijfers.

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale `Regex_australia_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een `Keyword_australia_passport_number` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale `Regex_australia_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers
- paspoortdetails
- migratie en burgerschap
- gemenebest van Australië
- afdeling migratie
- nationale identiteitskaart
- reisdocument
- instantie voor uitgifte


## <a name="australia-tax-file-number"></a>Australië belastingbestandsnummer

### <a name="format"></a>Opmaak

acht tot negen cijfers

### <a name="pattern"></a>Patroon

acht tot negen cijfers die gewoonlijk spaties als volgt worden weergegeven:
- drie cijfers
- een optionele spatie
- drie cijfers
- een optionele spatie
- twee tot drie cijfers waarbij het laatste cijfer een controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_australian_tax_file_number inhoud die overeenkomt met het patroon.
- Er wordt geen trefwoord Keyword_Australia_Tax_File_Number of Keyword_number_exclusions gevonden.
- De checksum passeert.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- Australisch bedrijfsnummer
- marginaal belastingtarief
- hossinusheffing
- portfolionummer
- serviceveteranen
- bronbelasting
- individuele belastingaangifte
- btw-bestandsnummer
- tfn

## <a name="austria-drivers-license-number"></a>Oostenrijks rijbewijsnummer

### <a name="format"></a>Opmaak

acht cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de normale  `Regex_austria_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_austria_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver is s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Oostenrijk-identiteitskaart
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Een combinatie van 24 tekens van letters, cijfers en speciale tekens

### <a name="pattern"></a>Patroon

24 tekens:

-  22 letters (niet hoofdlettergevoelig), cijfers, backslashes, slashes of plustekens

- twee letters (niet hoofdlettergevoelig), cijfers, backslashes, slashes, plustekens of gelijktekens

### <a name="checksum"></a>Checksum

Niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de normale  `Regex_austria_eu_national_id_card` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_austria_eu_national_id_card` trefwoord uit gevonden.

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- identiteitsnummer
- nationale id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Oostenrijks paspoortnummer

### <a name="format"></a>Opmaak

Eén letter gevolgd door een optionele spatie en zeven cijfers

### <a name="pattern"></a>Patroon

Een combinatie van één letter, zeven cijfers en één spatie:

- één letter (niet case-sensitive)
- één spatie (optioneel)
- zeven cijfers

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_austria_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_austria_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_austria_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_austria_eu_passport_number` wordt gevonden.

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- heruitgave
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Wachtwoordnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum

## <a name="austria-social-security-number"></a>Oostenrijks sociaal-zekerheidsnummer

### <a name="format"></a>Opmaak

10 cijfers in de opgegeven notatie

### <a name="pattern"></a>Patroon

10 cijfers:

- drie cijfers die overeenkomen met een serieel getal
- een vinkje
- zes cijfers die overeenkomen met de geboortedatum (DDMMYY)

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_austria_eu_ssn_or_equivalent` functie wordt inhoud gevonden die overeenkomt met het patroon.
- een trefwoord  `Keywords_austria_eu_ssn_or_equivalent` uit wordt gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_austria_eu_ssn_or_equivalent` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- oostenrijks ssn
- ehic-getal
- ehic no
- verzekeringscode
- verzekeringscode #
- verzekeringsnummer
- verzekering nee
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- sociale zekerheid nee
- sociaal-zekerheidsnummer
- socialezekerheidscode
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Oostenrijks btw-nummer

### <a name="format"></a>Opmaak

negen cijfers met optioneel afbreekstreester en schuine streep

### <a name="pattern"></a>Patroon

negen cijfers met optioneel afbreekstreester en schuine streep vooruit:

- twee cijfers
- een afbreekstreester (optioneel)
- drie cijfers
- a forward slash (optioneel)
- vier cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_austria_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_austria_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_austria_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- btw-nummer

## <a name="austria-value-added-tax"></a>Oostenrijks belasting over toegevoegde waarde
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 11 tekens

### <a name="pattern"></a>Patroon

Alfanumeriek patroon van 11 tekens:

- A of een
- T of t
- Optionele spatie
- U of u
- optionele spatie
- twee of drie cijfers
- optionele spatie
- vier cijfers
- optionele spatie
- een of twee cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_Austria_Value_Added_Tax wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Austria_Value_Added_Tax gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_Austria_Value_Added_Tax wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- btw-nummer
- btw #
- oostenrijks btw-nummer
- btw nee.
- vatno #
- btw-nummer
- oostenrijks btw-tarief
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- btw-identificatienummer
- atu-getal
- uidnummer


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB auth-toets

### <a name="format"></a>Opmaak

De tekenreeks 'DocumentDb', gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven.

### <a name="pattern"></a>Patroon

- De tekenreeks 'DocumentDb'
- Een combinatie van 3-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- Een groter dan symbool (>), een gelijkteken (=), een aanhalingsteken ("), of een apostrof (')
- Elke combinatie van 86 kleine of hoofdletters, cijfers, slash (/) of plusteken (+)
- Twee gelijke tekens (=)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureDocumentDBAuthKey inhoud die overeenkomt met het patroon.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS-databaseverbindingsreeks en Azure SQL-verbindingsreeks

### <a name="format"></a>Opmaak

De tekenreeks 'Server', 'server' of 'gegevensbron', gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven, inclusief de tekenreeks 'cloudapp.azure..<!--no-hyperlink-->com' of 'cloudapp.azure.<!--no-hyperlink-->net" of "database.windows.<!--no-hyperlink-->en de tekenreeks 'Wachtwoord' of 'wachtwoord' of 'pwd'.

### <a name="pattern"></a>Patroon

- de tekenreeks 'Server', 'server' of 'gegevensbron'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- De tekenreeks 'cloudapp.azure.<!--no-hyperlink-->com', 'cloudapp.azure.<!--no-hyperlink-->net", of "database.windows.<!--no-hyperlink-->netto"
- een combinatie van 1-300 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'Wachtwoord', 'wachtwoord' of 'pwd'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een of meer tekens die geen puntkomma (;), aanhalingsteken (") of apostrof (')
- een puntkomma (;), aanhalingsteken (") of apostrof (')

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureConnectionString inhoud die overeenkomt met het patroon.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-iot-connection-string"></a>Azure IoT-verbindingsreeks

### <a name="format"></a>Opmaak

De tekenreeks 'HostName' gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven, inclusief de tekenreeksen 'azure-devices'.<!--no-hyperlink-->net" en "SharedAccessKey".

### <a name="pattern"></a>Patroon

- de tekenreeks 'HostName'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'azure-devices'.<!--no-hyperlink-->netto"
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'SharedAccessKey'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 43 kleine of hoofdletters, cijfers, slash (/) of plusteken (+)
- een gelijkteken (=)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureIoTConnectionString inhoud die overeenkomt met het patroon.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-publish-setting-password"></a>Wachtwoord voor publiceren in Azure

### <a name="format"></a>Opmaak

De tekenreeks 'userpwd=' gevolgd door een alfanumerieke tekenreeks.

### <a name="pattern"></a>Patroon

- de tekenreeks 'userpwd='
- een combinatie van 60 kleine letters of cijfers
- een aanhalingsteken (")

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzurePublishSettingPasswords inhoud die overeenkomt met het patroon.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-redis-cache-connection-string"></a>Verbindingsreeks Azure Redis-cache

### <a name="format"></a>Opmaak

De tekenreeks 'redis.cache.windows.<!--no-hyperlink-->net" gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven, inclusief de tekenreeks 'wachtwoord' of 'pwd'.

### <a name="pattern"></a>Patroon

- de tekenreeks 'redis.cache.windows.<!--no-hyperlink-->netto"
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'wachtwoord' of 'pwd'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 43 tekens die kleine of hoofdletters, cijfers, slash (/) of plusteken (+) zijn
- een gelijkteken (=)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureRedisCacheConnectionString inhoud die overeenkomt met het patroon.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Opmaak

De tekenreeks 'sig' gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven.

### <a name="pattern"></a>Patroon

- de tekenreeks 'sig'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 43-53 tekens die kleine of hoofdletters, cijfers of het procentteken (%)
- de tekenreeks '%3d'
- een teken dat geen kleine of hoofdletter, cijfer of procentteken (%) is

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureSAS inhoud die overeenkomt met het patroon.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Verbindingsreeks Azure-servicebus

### <a name="format"></a>Opmaak

De tekenreeks 'Eindpunt', gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven, inclusief de tekenreeksen 'servicebus.windows'.<!--no-hyperlink-->net" en "SharedAccesKey".

### <a name="pattern"></a>Patroon

- de tekenreeks 'EndPoint'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'servicebus.windows.<!--no-hyperlink-->netto"
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'SharedAccessKey'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 43 tekens die kleine of hoofdletters, cijfers, slash (/) of plusteken (+) zijn
- een gelijkteken (=)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureServiceBusConnectionString inhoud die overeenkomt met het patroon.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-storage-account-key"></a>Azure-opslagaccountcode

### <a name="format"></a>Opmaak

De tekenreeks 'DefaultEndpointsProtocol' gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven, inclusief de tekenreeks 'AccountKey'.

### <a name="pattern"></a>Patroon

- de tekenreeks 'DefaultEndpointsProtocol'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'AccountKey'
- nul tot twee witruimtetekens
- een gelijkteken (=)
- nul tot twee witruimtetekens
- een combinatie van 86 tekens die kleine of hoofdletters, cijfers, slash (/) of plusteken (+) zijn
- twee gelijke tekens (=)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureStorageAccountKey inhoud die overeenkomt met het patroon.
- De normale expressie CEP_AzureEmulatorStorageAccountFilter inhoud die overeenkomt met het patroon, wordt niet gevonden.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gezien identificeert dit type gevoelige informatie deze trefwoorden met behulp van een gewone expressie, niet met een trefwoordlijst.)

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-storage-account-key-generic"></a>Azure Storage accountcode (generic)

### <a name="format"></a>Opmaak

Elke combinatie van 86 kleine of hoofdletters, cijfers, de slash (/) of het plusteken (+), voorafgegaan of gevolgd door de tekens die in het onderstaande patroon worden beschreven.

### <a name="pattern"></a>Patroon

- nul tot een van de grootste symbolen (>), apostrof ('), gelijkteken (=), aanhalingsteken (") of getalteken (#)
- een combinatie van 86 tekens die kleine of hoofdletters, cijfers, de slash (/) of het plusteken (+) zijn
- twee gelijke tekens (=)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_AzureStorageAccountKeyGeneric inhoud die overeenkomt met het patroon.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Nummer van het Rijbewijs van België

### <a name="format"></a>Opmaak

10 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

10 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_belgium_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_driver's_license_number` van of `Keywords_belgium_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver is s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Nationaal nummer belgië

### <a name="format"></a>Opmaak

11 cijfers plus optionele scheidingstekens

### <a name="pattern"></a>Patroon

11 cijfers plus scheidingstekens:
- zes cijfers en twee optionele perioden in de notatie YY. MM.DD voor geboortedatum
- Een optioneel scheidingsteken van punt, streepje, spatie
- drie opeenvolgende cijfers (oneven voor mannen, zelfs voor vrouwen)
- Een optioneel scheidingsteken van punt, streepje, spatie
- twee controlecijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_belgium_national_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_belgium_national_number gevonden.
- De checksum passeert.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_belgium_national_number inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- identificatie
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identiteit
- opschrift
- nationaal nummer
- nationaal register
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- persoonlijk id-nummer
- personalausweis
- personalidnumber #
- registratie
- registratie
- registratiesnumme
- registrierung
- sociaal-zekerheidsnummer
- ssn #
- ssn
- steuernummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #

## <a name="belgium-passport-number"></a>België paspoortnummer

### <a name="format"></a>Opmaak

twee letters gevolgd door zes cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

twee letters en gevolgd door zes cijfers

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

 Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_belgium_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_belgium_eu_passport_number` wordt gevonden.
- Met de normale `Regex_eu_passport_date2` expressie wordt de datum gevonden in de indeling DD MM YY of een trefwoord van of wordt `Keywords_eu_passport_date` `Keywords_belgium_eu_passport_number` gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_belgium_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_belgium_eu_passport_number` wordt gevonden.

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport livre
- Pass-Nr
- Wachtwoordnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum

## <a name="belgium-value-added-tax-number"></a>België btw-nummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 12 tekens

### <a name="pattern"></a>Patroon

Alfanumeriek patroon van 12 tekens:

- een letter B of b
- een letter E of e
- een cijfer 0
- een cijfer van 1 tot en met 9
- een optionele punt of afbreekstreester of spatie
- vier cijfers
- een optionele punt of afbreekstreester of spatie
- vier cijfers


### <a name="checksum"></a>Checksum

Ja


### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_belgium_value_added_tax_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_belgium_value_added_tax_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_belgium_value_added_tax_number inhoud die overeenkomt met het patroon.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- btw-nummer
- btw-nee
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- btw #


## <a name="brazil-cpf-number"></a>Brazilië CPF-getal

### <a name="format"></a>Opmaak

11 cijfers die een controlecijfer bevatten en kunnen worden opgemaakt of niet-opgemaakt

### <a name="pattern"></a>Patroon

Opgemaakt:
- drie cijfers
- een punt
- drie cijfers
- een punt
- drie cijfers
- een afbreekstreester
- twee cijfers die cijfers controleren

Niet-opgemaakt:
- 11 cijfers waarbij de laatste twee cijfers controlecijfers zijn

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_brazil_cpf inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_brazil_cpf gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_brazil_cpf inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identificatie
- Registratie
- Omzet
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>Brazil legal entity number (CNPJ)

### <a name="format"></a>Opmaak

14 cijfers met een registratienummer, vertakkingsnummer en controlecijfers, plus scheidingstekens

### <a name="pattern"></a>Patroon

14 cijfers, plus scheidingstekens:

- twee cijfers
- een punt
- drie cijfers
- een punt
- drie cijfers (deze eerste acht cijfers zijn het registratienummer)
- een slash naar voren
- vertakkingsnummer met vier cijfers
- een afbreekstreester
- twee cijfers die cijfers controleren

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_brazil_cnpj wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_brazil_cnpj gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_brazil_cnpj wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- Nationaal register van juridische entiteiten
- Register voor belastingbetalers
- Rechtspersoon
- Juridische entiteiten
- Registratiestatus
- Business
- Company
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Cadastrale situação
- Inscrição
- Empresa


## <a name="brazil-national-identification-card-rg"></a>Brazilië National Identification Card (RG)

### <a name="format"></a>Opmaak

Registro Geral (oude notatie): Negen cijfers

Registro de Identidade (RIC) (nieuwe indeling): 11 cijfers

### <a name="pattern"></a>Patroon

Registro Geral (oude indeling):
- twee cijfers
- een punt
- drie cijfers
- een punt
- drie cijfers
- een afbreekstreester
- een cijfer dat een controlecijfer is

Registro de Identidade (RIC) (nieuwe indeling):
- 10 cijfers
- een afbreekstreester
- een cijfer dat een controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_brazil_rg wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_brazil_rg gevonden.
- De checksum passeert.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identiteitskaart
- nationale id
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (dit trefwoord is case-sensitive)
- RIC (dit trefwoord is case-sensitive)


## <a name="bulgaria-drivers-license-number"></a>Bulgarije rijbewijsnummer

### <a name="format"></a>Opmaak

negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_bulgaria_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_bulgaria_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver is s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Een uniform burgerlijk burgernummer van Bulgarije
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

10 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

10 cijfers zonder spaties en scheidingstekens

- zes cijfers die overeenkomen met de geboortedatum (YYMMDD)
- twee cijfers die overeenkomen met de geboortedatum
- één cijfer dat overeenkomt met geslacht: een even cijfer voor man en een oneven cijfer voor vrouw
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_bulgaria_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_bulgaria_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_bulgaria_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- edinen grazhdanski nomer
- egn #
- egn
- identificatienummer
- nationale id
- nationaal nummer
- nationalnumber #
- nationalnumber
- persoonlijke id
- persoonlijk nee
- persoonlijk nummer
- personalidnumber #
- sociaal-zekerheidsnummer
- ssn #
- ssn
- uniform burgerlijk identiteitsbewijs
- uniform burgerlijk nee
- uniform burgerlijk getal
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- uniek nummer voor het burgerschap
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униурм-id
- унигорм грагански id
- униформ граждански не
- униформ граждански номер
- унигормграганскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Bulgarije paspoortnummer

### <a name="format"></a>Opmaak

negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_bulgaria_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_bulgaria_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_bulgaria_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_bulgaria_eu_passport_number` wordt gevonden.

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum

## <a name="canada-bank-account-number"></a>Canada bankrekeningnummer

### <a name="format"></a>Opmaak

7 of 12 cijfers

### <a name="pattern"></a>Patroon

Een Canada-bankrekeningnummer is 7 of 12 cijfers.

Een transitnummer van een Canadese bankrekening is:
- vijf cijfers
- een afbreekstreester
- drie cijfers OF
- een nul "0"
- acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_canada_bank_account_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_canada_bank_account_number gevonden.
- De normale expressie Regex_canada_bank_account_transit_number inhoud die overeenkomt met het patroon.

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_canada_bank_account_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_canada_bank_account_number gevonden.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada spaarpapieren
- Canada Revenue Agency
- Canadese financiële instelling
- Direct stortingsformulier
- Canadese burger
- wettelijke vertegenwoordiger
- notaris
- commissariaat voor eeden
- kinderbijslag
- universele kinderzorg
- Canada Child Tax Benefit
- voordeel in de inkomstenbelasting
- btw
- sociaal verzekeringsnummer
- terugbetaling van inbelasting
- kinderbelastingvoordeel
- territoriaal betalen
- instellingsnummer
- stortingsaanvraag
- bankgegevens
- directe storting


## <a name="canada-drivers-license-number"></a>Canada-nummer van het rijbewijs

### <a name="format"></a>Opmaak

Verschilt per provincie

### <a name="pattern"></a>Patroon

Verschillende patronen die betrekking hebben op:
- Alberta
- Brits-Columbia
- Manitoba
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- Ontario
- Prins EdwardEiland
- Quebec
- Saskatchewan

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_[province_name]_drivers_license_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_[province_name]_drivers_license_name gevonden.
- Er wordt een trefwoord Keyword_canada_drivers_license gevonden.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- De afkorting van de provincie, bijvoorbeeld AB
- De provincienaam, bijvoorbeeld Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Rijbewijs
- Licenties voor stuurprogramma's
- Rijbewijs
- Rijbewijzen
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Rijbewijs
- Licenties voor stuurprogramma's
- Rijbewijs
- Rijbewijzen
- Driver'Lic
- Driver'Lics
- Rijbewijs
- Licenties voor stuurprogramma's
- Rijbewijs
- Rijbewijzen
- Driver' Lic
- Driver' Lics
- Rijbewijs
- Rijbewijzen
- Rijbewijs
- Rijbewijzen
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Rijbewijs
- Rijbewijzen
- Rijbewijs
- Rijbewijzen
- Permis de Conduire
- id
- id's
- idcardnummer
- idcardnummers
- idcard #
- idcard #s
- idcardkaart
- Idcard-kaarten
- idcard
- identificatienummer
- identificatienummers
- identificatie #
- identificatie #s
- identificatiekaart
- identificatiekaarten
- identificatie
- DL #
- DLS #
- CDL #
- CDLS #
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- DriverLicence #
- DriverLicences #
- Driver Lic #
- Driver Lics #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Rijbewijs #
- Rijbewijzen #
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- DriversLicence #
- DriversLicences #
- Drivers Lic #
- Drivers Lics #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Rijbewijs #
- Rijbewijzen #
- Driver'Lic #
- Driver'Lics #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Rijbewijs #
- Rijbewijzen #
- Driver' Lic #
- Driver' Lics #
- Rijbewijs #
- Rijbewijzen #
- Rijbewijs #
- Rijbewijzen #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Driver'sLicenses #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic #
- Driver's Lics #
- Rijbewijs #
- Rijbewijzen #
- Rijbewijs #
- Rijbewijzen #
- Permis de Conduire #
- id #
- id's #
- idcardkaart #
- Idcard-kaarten #
- idcard #
- identificatiekaart #
- identificatiekaarten #
- identificatie #


## <a name="canada-health-service-number"></a>Canada health service number

### <a name="format"></a>Opmaak

 10 cijfers

### <a name="pattern"></a>Patroon

10 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_canada_health_service_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_canada_health_service_number gevonden.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- persoonlijk gezondheidsnummer
- patiëntgegevens
- gezondheidsdiensten
- speciale services
- auto-ongeluk
- patiëntenziekenhuis
- psychiater
- werknemerscompensatie
- beperking


## <a name="canada-passport-number"></a>Canada-paspoortnummer

### <a name="format"></a>Opmaak

twee hoofdletters gevolgd door zes cijfers

### <a name="pattern"></a>Patroon

twee hoofdletters gevolgd door zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_canada_passport_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_canada_passport_number of Keyword_passport gevonden.

```xml
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- Canadese nationaliteit
- Canadees paspoort
- paspoorttoepassing
- pasfoto's
- gecertificeerde vertaler
- Canadese burgers
- verwerkingstijden
- verlengingstoepassing

#### <a name="keyword_passport"></a>Keyword_passport

- Paspoortnummer
- Paspoort nee
- Paspoort #
- Paspoort #
- PassportID
- Passportno
- paspoortnummer
- パスポート
- パスポート番号
- パのポーののNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>Canada Personal Health Identification Number (PHIN)

### <a name="format"></a>Opmaak

negen cijfers

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_canada_phin inhoud die overeenkomt met het patroon.
- Er worden ten minste twee trefwoorden Keyword_canada_phin of Keyword_canada_provinces gevonden.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- sociaal verzekeringsnummer
- health information act
- informatie over de inkomstenbelasting
- manitoba-gezondheid
- statusregistratie
- receptaankopen
- in aanmerking komen voor een uitkering
- persoonlijke gezondheid
- volmacht
- registratienummer
- persoonlijk gezondheidsnummer
- verwijzing naar de huisarts
- wellness professional
- verwijzing naar patiënten
- gezondheid en wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Quebec
- Northwest Territories
- Ontario
- Brits-Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland en Labrador
- New Brunswick
- Nova Scotia
- Prins EdwardEiland
- Canada


## <a name="canada-social-insurance-number"></a>Canada social insurance number

### <a name="format"></a>Opmaak

negen cijfers met optionele afbreekstree streepjes of spaties

### <a name="pattern"></a>Patroon

Opgemaakt:
- drie cijfers
- een afbreekstreester of spatie
- drie cijfers
- een afbreekstreester of spatie
- drie cijfers

Niet-opgemaakt: negen cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_canadian_sin inhoud die overeenkomt met het patroon.
- Ten minste twee van de volgende patronen:
    - Er wordt een trefwoord Keyword_sin gevonden.
    - Er wordt een trefwoord Keyword_sin_collaborative gevonden.
    - Met de Func_eu_date wordt een datum in de juiste datumnotatie gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_unformatted_canadian_sin inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_sin gevonden.
- De checksum passeert.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_sin"></a>Keyword_sin

- sin
- sociale verzekering
- numero d'assurance sociale
- zondes
- ssn
- ssns
- sociale zekerheid
- numero d'assurance social
- nationaal identificatienummer
- nationale id
- sin #
- soc-ins
- sociale ins

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- rijbewijs
- rijbewijs
- rijbewijs
- rijbewijs
- DOB
- Geboortedatum
- Verjaardag
- Geboortedatum


## <a name="chile-identity-card-number"></a>Chili-identiteitskaartnummer

### <a name="format"></a>Opmaak

zeven tot acht cijfers plus scheidingstekens van een vinkje of letter

### <a name="pattern"></a>Patroon

zeven tot acht cijfers plus scheidingstekens:
- één tot twee cijfers
- een optionele periode
- drie cijfers
- een optionele periode
- drie cijfers
- een streepje
- een cijfer of letter (niet case-sensitive) dat is een controlecijfer

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_chile_id_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_chile_id_card gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_chile_id_card inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- nationale identificatie
- nationaal identificatienummer
- nationale id
- número de identificación nacional
- rol único nacional
- rol único tributario
- UITVOEREN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- UITVOEREN #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad-getal
- Chileense identiteit nee.
- Chileense identiteitsnummer
- Chileense identiteit #
- Uniek belastingregister
- Unieke zijrivierrol
- Unieke belastingrol
- Uniek zijriviernummer
- Uniek nationaal nummer
- Unieke nationale rol
- Nationale unieke rol
- Chile identity no.
- Chili-identiteitsnummer
- Chili-identiteit #


## <a name="china-resident-identity-card-prc-number"></a>China Resident Identity Card (PRC) number

### <a name="format"></a>Opmaak

18 cijfers

### <a name="pattern"></a>Patroon

18 cijfers:
- zes cijfers die een adrescode zijn
- acht cijfers in het formulier YYYYMMDD, de geboortedatum
- drie cijfers die een ordercode zijn
- een cijfer dat een controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_china_resident_id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_china_resident_id gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_china_resident_id inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card
- Volksrepubliek China
- Nationale identificatiekaart
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定


## <a name="credit-card-number"></a>Creditcardnummer

### <a name="format"></a>Opmaak

14 tot 16 cijfers die kunnen worden opgemaakt of niet-opgemaakt (dddddd) en die de Luhn-toets moeten doorstaan.

### <a name="pattern"></a>Patroon

Detecteert kaarten van alle grote merken wereldwijd, waaronder Visa, MasterCard, Discover Card, JCB, American Express, cadeaukaarten en dinerkaarten.

### <a name="checksum"></a>Checksum

Ja, de Luhn-checksum

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_credit_card inhoud die overeenkomt met het patroon.
- Een van de volgende gegevens is waar:
    - Er wordt een trefwoord Keyword_cc_verification gevonden.
    - Er wordt een trefwoord Keyword_cc_name gevonden.
    - Met de Func_expiration_date wordt een datum in de juiste datumnotatie gevonden.
- De checksum passeert.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_credit_card inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- kaartverificatie
- kaartidentificatienummer
- cvn
- cid
- cvc2
- cvv2
- blok vastmaken
- beveiligingscode
- beveiligingsnummer
- beveiliging nee
- probleemnummer
- probleem nee
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca
- cod. segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- gegevensscad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transactie
- transactienummer
- verwijzingsnummer
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- American Express
- americanexpress
- americano espresso
- Visa
- mastercard
- basiskaart
- mc
- mastercards
- basiskaarten
- diner's Club
- diners club
- dinersclub
- ontdekken
- ontdekkaart
- discovercard
- ontdek kaarten
- JCB
- BrandSmart
- Japans kaartbureau
- carte blanche
- carteblanche
- creditcard
- cc #
- cc#:
- vervaldatum
- exp date
- vervaldatum
- datum d'expiratie
- date d'exp
- vervaldatum
- bankkaart
- bankcard
- kaartnummer
- kaartnummer
- kaartnummer
- kaartnummers
- kaartnummers
- creditcard
- creditcards
- creditcards
- ccn
- kaarthouder
- kaarthouder
- kaarthouders
- kaarthouders
- vinkje
- checkcard
- kaarten controleren
- checkcards
- betaalkaart
- debitcard
- betaalkaarten
- debitcards
- atm-kaart
- atmcard
- atm-kaarten
- atmcards
- enroute
- en route
- kaarttype
- Cardmember Acct
- cardmember-account
- Cardno
- Bedrijfskaart
- Visitekaartjes voor bedrijven
- Type kaart
- kaartaccountnummer
- kaartlidaccount
- Cardmember Acct.
- kaart nee.
- kaart nee
- kaartnummer
- carte banke
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta-atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- nee. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- nee. do cartão
- nee. cartao doen
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Nummer van het rijbewijs van Kroatië

### <a name="format"></a>Opmaak

acht cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de normale  `Regex_croatia_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_driver's_license_number` van of `Keywords_croatia_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver is s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Nummer van kroatische identiteitskaart
Deze entiteit is opgenomen in het gevoelige informatietype EU National Identification Number. Het is beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

negen cijfers

### <a name="pattern"></a>Patroon

negen opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_croatia_id_card wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_croatia_id_card gevonden.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- burgernummer voor master
- nacionalni identifikacijski broj
- nationaal identificatienummer
- oib #
- oib
- osobna iskaznica
- osobni-id
- osobni identifikacijski broj
- persoonlijk identificatienummer
- porezni broj
- porezni identifikacijski broj
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="croatia-passport-number"></a>Kroatië-paspoortnummer

### <a name="format"></a>Opmaak

negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_croatia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_croatia_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_croatia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_croatia_eu_passport_number` wordt gevonden.

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>OIB-nummer (Persoonlijke identificatie van Kroatië)

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

11 cijfers:
- 10 cijfers
- laatste cijfer is een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_croatia_oib_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_croatia_eu_tax_file_number gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_croatia_oib_number inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- burgernummer voor master
- nacionalni identifikacijski broj
- nationaal identificatienummer
- oib #
- oib
- osobna iskaznica
- osobni-id
- osobni identifikacijski broj
- persoonlijk identificatienummer
- porezni broj
- porezni identifikacijski broj
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #

## <a name="cyprus-drivers-license-number"></a>Cyprus drivers license number

### <a name="format"></a>Opmaak

12 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

12 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_cyprus_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_cyprus_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver is s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Cyprus-identiteitskaart
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

10 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

10 cijfers

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_cyprus_eu_national_id_card` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_cyprus_eu_national_id_card` trefwoord uit gevonden.

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id-kaartnummer
- nummer van een identiteitskaart
- kimlik-karti
- nationaal identificatienummer
- persoonlijk id-nummer
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Cyprus paspoortnummer

### <a name="format"></a>Opmaak

een letter gevolgd door 6-8 cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

een letter gevolgd door zes tot acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_cyprus_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_cyprus_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_cyprus_eu_passport_date` indeling DD/MM/YYYY of wordt een trefwoord `Keywords_cyprus_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_cyprus_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_cyprus_eu_passport_number` wordt gevonden.

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport nee.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- verloopt op
- uitgegeven op


## <a name="cyprus-tax-identification-number"></a>Btw-nummer cyprus
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

acht cijfers en één letter in het opgegeven patroon

### <a name="pattern"></a>Patroon

acht cijfers en één letter:

- een '0' of '9'
- zeven cijfers
- één letter (niet case-sensitive)

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_cyprus_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_cyprus_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_cyprus_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- belasting-id
- belastingidentificatiecode
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tic #
- tic
- tin-id
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Tsjechisch rijbewijsnummer

### <a name="format"></a>Opmaak

twee letters gevolgd door zes cijfers

### <a name="pattern"></a>Patroon

acht letters en cijfers:

- letter 'E' (niet case-sensitive)
- een brief
- een spatie (optioneel)
- zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_czech_republic_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_czech_republic_eu_driver's_license_number` wordt gevonden.

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver is s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských pr


## <a name="czech-passport-number"></a>Tsjechisch paspoortnummer

### <a name="format"></a>Opmaak

acht cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers zonder spaties of scheidingstekens

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_czech_republic_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_czech_republic_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_czech_republic_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_czech_republic_eu_passport_number` wordt gevonden.

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="czech-personal-identity-number"></a>Tsjechisch persoonlijk identiteitsnummer

### <a name="format"></a>Opmaak

negen cijfers met optionele slash (oude opmaak) 10 cijfers met optionele slash vooruit (nieuwe indeling)

### <a name="pattern"></a>Patroon

negen cijfers (oude notatie):
- zes cijfers die de geboortedatum vertegenwoordigen
- een optionele slash
- drie cijfers

10 cijfers (nieuwe indeling):
- zes cijfers die de geboortedatum vertegenwoordigen
- een optionele slash
- vier cijfers waarbij het laatste cijfer een controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- De functie Func_czech_id_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_czech_id_card gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- De functie Func_czech_id_card_new_format inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- geboortedatum
- Tsjechische republiek-id
- czechidno #
- daňové číslo
- identifikační číslo
- identiteit nee
- identiteitsnummer
- identityno #
- identityno
- verzekeringsnummer
- nationaal identificatienummer
- nationalnumber #
- nationaal nummer
- osobní číslo
- personalidnumber #
- persoonlijk id-nummer
- persoonlijk identificatienummer
- persoonlijk nummer
- pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- sociaal-zekerheidsnummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- uniek identificatienummer


## <a name="denmark-drivers-license-number"></a>Het rijbewijsnummer van Denemarken

### <a name="format"></a>Opmaak

acht cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_denmark_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_denmark_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver is s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Denemarken paspoortnummer

### <a name="format"></a>Opmaak

negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_denmark_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_denmark_eu_passport_number` wordt gevonden.
- Met de normale `Regex_eu_passport_date2` expressie wordt de datum gevonden in de indeling DD MM YY of wordt een trefwoord uit `Keywords_eu_passport_date` gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_denmark_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_denmark_eu_passport_number` wordt gevonden.

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="denmark-personal-identification-number"></a>Persoonlijk identificatienummer van Denemarken

### <a name="format"></a>Opmaak

10 cijfers met een afbreekstreester

### <a name="pattern"></a>Patroon

10 cijfers:
- zes cijfers in de indeling DDMMYY, de geboortedatum
- een afbreekstreester
- vier cijfers waarbij het uiteindelijke cijfer een controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Func_denmark_eu_tax_file_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_denmark_id gevonden.
- De checksum passeert.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Func_denmark_eu_tax_file_number inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personenregister
- civilt registreringssystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- gezondheidskaart
- nummer van ziektekostenverzekeringskaart
- nummer van ziektekostenverzekering
- identificatienummer
- identifikationsnummer
- identifikationsnummer #
- identiteitsnummer
- krankenkassennummer
- nationalid #
- nationalnumber #
- nationaal nummer
- personalidnumber #
- personalidentityno #
- persoonlijk id-nummer
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- skat-id
- skat kode
- skatnummer
- skattenummer
- sociaal-zekerheidsnummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- btw-code
- reisverzekeringskaart
- uniqueidentityno #
- btw-nummer
- btw-registratienummer
- belasting-id
- btw-nummer
- getaxid #
- belastingnummer #
- belasting nee
- taxno #
- belastingnummer
- geen belastingidentificatie
- tin #
- taxidno #
- getaxidnummer #
- belasting nee #
- tin-id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personenregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>Nummer van Het Bureau voor drugshandhaving (DEA)

### <a name="format"></a>Opmaak

twee letters gevolgd door zeven cijfers

### <a name="pattern"></a>Patroon

Patroon moet de volgende gegevens bevatten:
- één letter (niet hoofdlettergevoelig) van deze set mogelijke letters: abcdefghjklmnprstux, een registrantcode
- één letter (niet zaakgevoelig), de eerste letter van de achternaam of het cijfer '9' van de registrant
- zeven cijfers, waarvan het laatste het controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_dea_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een `Keyword_dea_number` trefwoord uit gevonden
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_dea_number wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- beheer van drugshandhaving
- instantie voor drugshandhaving


## <a name="estonia-drivers-license-number"></a>Estlands rijbewijsnummer

### <a name="format"></a>Opmaak

twee letters gevolgd door zes cijfers

### <a name="pattern"></a>Patroon

twee letters en zes cijfers:

- de letters 'ET' (niet hoofdlettergevoelig)
- zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_estonia_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_estonia_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver is s_license_number

-- permis de conduire
- juhilubade numbrid
- juhiloanummer
- juhiluba


## <a name="estonia-personal-identification-code"></a>Estlandse persoonlijke identificatiecode
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

11 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

11 cijfers:

- een cijfer dat overeenkomt met geslacht en eeuw van geboorte (oneven getal man, even getal vrouw; 1-2: 19e eeuw; 3-4: 20e eeuw; 5-6: 21e eeuw)
- zes cijfers die overeenkomen met de geboortedatum (YYMMDD)
- drie cijfers die overeenkomen met een serieel getal dat personen scheidt die op dezelfde datum zijn geboren
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_estonia_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_estonia_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_estonia_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood #
- isikukood
- maksu-id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- nationaal identificatienummer
- nationaal nummer
- persoonlijke code
- persoonlijk id-nummer
- persoonlijke identificatiecode
- persoonlijk identificatienummer
- personalidnumber #
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="estonia-passport-number"></a>Estlands paspoortnummer

### <a name="format"></a>Opmaak

één letter gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

één letter gevolgd door zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_estonia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_estonia_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_estonia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_estonia_eu_passport_number` wordt gevonden.

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="eu-debit-card-number"></a>EU-betaalkaartnummer

### <a name="format"></a>Opmaak

16 cijfers

### <a name="pattern"></a>Patroon

Complex en robuust patroon

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_eu_debit_card wordt inhoud gevonden die overeenkomt met het patroon.
- Ten minste een van de volgende gegevens is waar:
    - Er wordt een trefwoord Keyword_eu_debit_card gevonden.
    - Er wordt een trefwoord Keyword_card_terms_dict gevonden.
    - Er wordt een trefwoord Keyword_card_security_terms_dict gevonden.
    - Er wordt een trefwoord Keyword_card_expiration_terms_dict gevonden.
    - Met de Func_expiration_date wordt een datum in de juiste datumnotatie gevonden.
- De checksum passeert.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- accountnummer
- kaartnummer
- kaart nee.
- beveiligingsnummer
- cc #

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr
- acct-getal
- acct no
- American Express
- americanexpress
- americano espresso
- amex
- atm-kaart
- atm-kaarten
- atm-kaart
- atmcard
- atmcards
- atmkaart
- atmkaarten
- bancontact
- bankkaart
- bankkaart
- kaarthouder
- kaarthouders
- kaartnummer
- kaartnummer
- kaartnummers
- kaarttype
- cardano-numerieke waarde
- kaarthouder
- kaarthouders
- kaartnummer
- kaartnummers
- carta bianca
- carta credito
- carta di credito
- cartao de credito
- cartao de crédito
- cartao de debito
- cartao de débito
- carte banke
- carte blanche
- carte bleue
- carte de credit
- carte de crédit
- carte di credito
- carteblanche
- cartão de credito
- cartão de crédito
- cartão de debito
- cartão de débito
- cb
- ccn
- vinkje
- kaarten controleren
- checkcard
- checkcards
- chequekaart
- cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- creditcard
- creditcards
- creditcard
- creditcards
- debetkaart
- debetkaarten
- betaalkaart
- betaalkaarten
- debitcard
- debitcards
- debito automatico
- diners club
- dinersclub
- ontdekken
- ontdekkaart
- ontdek kaarten
- discovercard
- discovercards
- débito automático
- edc
- eigentümername
- Europese betaalkaart
- hoofdkaart
- hoofdkaarten
- in viaggio
- Japans kaartbureau
- japanse kaartdienst
- jcb
- kaart
- kaartnum
- kaartaantal
- kaartaantallen
- kaarthouder
- kaarthouders
- karte
- karteninhaber
- karteninhabers
- kartennr
- kartennummer
- kreditkarte
- kreditkarten-nummer
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartennummer
- kreditkartentyp
- maestro
- basiskaart
- basiskaarten
- mastercard
- mastercards
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- nee. de tarjeta
- nee. cartao doen
- nee. do cartão
- nr carta
- nr. carta
- numeri di scheda
- numero carta
- numero de cartao
- numero de carte
- numero de cartão
- numero de tarjeta
- numero della carta
- numero di carta
- numero di scheda
- numero do cartao
- numero do cartão
- numéro de carte
- nº carta
- nº de carte
- nº de la carte
- nº de tarjeta
- nº do cartao
- nº do cartão
- nº. do cartão
- número de cartao
- número de cartão
- número de tarjeta
- número do cartao
- scheda dell'assegno
- scheda dell'atmosfera
- scheda dell'atmosfera
- scheda della banca
- scheda di controllo
- scheda di debito
- scheda matrice
- schede dell'atmosfera
- schede di controllo
- schede di debito
- schede matrici
- scoprono la scheda
- scoprono le schede
- solo
- supporti di scheda
- supporto di scheda
- schakelen
- tarjeta-atm
- tarjeta credito
- tarjeta de atm
- tarjeta de credito
- tarjeta de debito
- tarjeta debito
- tarjeta no
- tarjetahabiente
- tipo della scheda
- ufficio giapponese della
- scheda
- v betalen
- v-pay
- visa
- visa plus
- visa-elektron
- visto
- visum
- vpay

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- kaartidentificatienummer
- kaartverificatie
- cardi la verifica
- cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- cod. seg
- cod. seguranca
- cod. segurança
- cod. sicurezza
- codice di sicurezza
- codice di verifica
- codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- cryptogram
- cryptogramme
- cv2
- cvc
- cvc2
- cvn
- cvv
- cvv2
- cód seguranca
- cód segurança
- cód. seguranca
- cód. segurança
- código
- código de seguranca
- código de segurança
- de kaart controle
- geeft nr uit
- probleem nee
- probleemnummer
- kaartidentificatienummer
- kreditkartenprufnummer
- kreditkartenprüfnummer
- kwestieaantal
- nee. dell'edizione
- nee. di sicurezza
- numero de securite
- numero de verificacao
- numero dell'edizione
- numero di identificazione della
- scheda
- numero di sicurezza
- numero van veiligheid
- numéro de sécurité
- nº autorizzazione
- número de verificação
- perno il blocco
- blok vastmaken
- prufziffer
- prüfziffer
- beveiligingscode
- beveiliging nee
- beveiligingsnummer
- sicherheits kode
- sicherheitscode
- sicherheitsnummer
- speldblok
- veiligheid nr
- veiligheidsaantal
- veiligheidscode
- veiligheidsnummer
- verfalldatum

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf
- data de expiracao
- data de expiração
- data del exp
- data di exp
- data di scadenza
- data em que expira
- gegevensscad
- data scadenza
- date de validé
- datum afloop
- datum van exp
- de afloop
- espira
- espira
- exp date
- exp datum
- verloop
- verlopen
- verloopt
- verlopen
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- valabel
- validade
- valido hasta
- valor
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>Eu-rijbewijsnummer

Deze entiteiten maken deel uit van het EU-rijbewijsnummer en zijn gevoelige informatietypen.

- [Oostenrijk](#austria-drivers-license-number)
- [België](#belgium-drivers-license-number)
- [Bulgarije](#bulgaria-drivers-license-number)
- [Kroatië](#croatia-drivers-license-number)
- [Cyprus](#cyprus-drivers-license-number)
- [Czech](#czech-drivers-license-number)
- [Denemarken](#denmark-drivers-license-number)
- [Estland](#estonia-drivers-license-number)
- [Finland](#finland-drivers-license-number)
- [Frankrijk](#france-drivers-license-number)
- [Duitsland](#germany-drivers-license-number)
- [Griekenland](#greece-drivers-license-number)
- [Hongarije](#hungary-drivers-license-number)
- [Ierland](#ireland-drivers-license-number)
- [Italië](#italy-drivers-license-number)
- [Letland](#latvia-drivers-license-number)
- [Litouwen](#lithuania-drivers-license-number)
- [Luxemburg](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Nederland](#netherlands-drivers-license-number)
- [Polen](#poland-drivers-license-number)
- [Portugal](#portugal-drivers-license-number)
- [Roemenië](#romania-drivers-license-number)
- [Slowakije](#slovakia-drivers-license-number)
- [Slovenië](#slovenia-drivers-license-number)
- [Spanje](#spain-drivers-license-number)
- [Zweden](#sweden-drivers-license-number)
- [VK](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>NATIONAAL EU-identificatienummer

Deze entiteiten maken deel uit van het nationale eu-identificatienummer en zijn gevoelige informatietypen.

- [Oostenrijk](#austria-identity-card)
- [België](#belgium-national-number)
- [Bulgarije](#bulgaria-uniform-civil-number)
- [Kroatië](#croatia-identity-card-number)
- [Cyprus](#cyprus-identity-card)
- [Czech](#czech-personal-identity-number)
- [Denemarken](#denmark-personal-identification-number)
- [Estland](#estonia-personal-identification-code)
- [Finland](#finland-national-id)
- [Frankrijk](#france-national-id-card-cni)
- [Duitsland](#germany-identity-card-number)
- [Griekenland](#greece-national-id-card)
- [Hongarije](#hungary-personal-identification-number)
- [Ierland](#ireland-personal-public-service-pps-number)
- [Italië](#italy-fiscal-code)
- [Letland](#latvia-personal-code)
- [Litouwen](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Nederland](#netherlands-citizens-service-bsn-number)
- [Polen](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Roemenië](#romania-personal-numeric-code-cnp)
- [Slowakije](#slovakia-personal-number)
- [Slovenië](#slovenia-unique-master-citizen-number)
- [Spanje](#spain-dni)
- [VK](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>EU-paspoortnummer

Deze entiteiten hebben het EU-paspoortnummer en zijn gevoelige informatietypen. Deze entiteiten maken deel uit van de EU-paspoortnummerbundel.

- [Oostenrijk](#austria-passport-number)
- [België](#belgium-passport-number)
- [Bulgarije](#bulgaria-passport-number)
- [Kroatië](#croatia-passport-number)
- [Cyprus](#cyprus-passport-number)
- [Czech](#czech-passport-number)
- [Denemarken](#denmark-passport-number)
- [Estland](#estonia-passport-number)
- [Finland](#finland-passport-number)
- [Frankrijk](#france-passport-number)
- [Duitsland](#germany-passport-number)
- [Griekenland](#greece-passport-number)
- [Hongarije](#hungary-passport-number)
- [Ierland](#ireland-passport-number)
- [Italië](#italy-passport-number)
- [Letland](#latvia-passport-number)
- [Litouwen](#lithuania-passport-number)
- [Luxemburg](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Nederland](#netherlands-passport-number)
- [Polen](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [Roemenië](#romania-passport-number)
- [Slowakije](#slovakia-passport-number)
- [Slovenië](#slovenia-passport-number)
- [Spanje](#spain-passport-number)
- [Zweden](#sweden-passport-number)
- [VK](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU-sociaal-zekerheidsnummer of equivalente identificatie

Deze entiteiten die deel uit maken van het EU-nummer voor sociale zekerheid of een equivalente identificatie en gevoelige informatietypen zijn.

- [Oostenrijk](#austria-social-security-number)
- [België](#belgium-national-number)
- [Kroatië](#croatia-personal-identification-oib-number)
- [Czech](#czech-personal-identity-number)
- [Denemarken](#denmark-personal-identification-number)
- [Finland](#finland-national-id)
- [Frankrijk](#france-social-security-number-insee)
- [Duitsland](#germany-identity-card-number)
- [Griekenland](#greece-national-id-card)
- [Hongarije](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [Spanje](#spain-social-security-number-ssn)
- [Zweden](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>EU-btw-identificatienummer

Deze entiteiten maken deel uit van het type gevoelige informatie over eu-belastingidentificatienummers.

- [Oostenrijk](#austria-tax-identification-number)
- [België](#belgium-national-number)
- [Bulgarije](#bulgaria-uniform-civil-number)
- [Kroatië](#croatia-identity-card-number)
- [Cyprus](#cyprus-tax-identification-number)
- [Czech](#czech-personal-identity-number)
- [Denemarken](#denmark-personal-identification-number)
- [Estland](#estonia-personal-identification-code)
- [Finland](#finland-national-id)
- [Frankrijk](#france-tax-identification-number)
- [Duitsland](#germany-tax-identification-number)
- [Griekenland](#greece-tax-identification-number)
- [Hongarije](#hungary-tax-identification-number)
- [Ierland](#ireland-personal-public-service-pps-number)
- [Italië](#italy-fiscal-code)
- [Letland](#latvia-personal-code)
- [Litouwen](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Nederland](#netherlands-tax-identification-number)
- [Polen](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Roemenië](#romania-personal-numeric-code-cnp)
- [Slowakije](#slovakia-personal-number)
- [Slovenië](#slovenia-tax-identification-number)
- [Spanje](#spain-tax-identification-number)
- [Zweden](#sweden-tax-identification-number)
- [VK](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Finland-nummer van het rijbewijs

### <a name="format"></a>Opmaak

10 cijfers met een afbreekstreester

### <a name="pattern"></a>Patroon

10 cijfers met een afbreekstreester:

- zes cijfers
- een afbreekstreester
- drie cijfers
- een cijfer of letter

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_finland_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_finland_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver is s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin-getal


## <a name="finland-european-health-insurance-number"></a>Finland European Health Insurance Number
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

20-cijferig getal

### <a name="pattern"></a>Patroon

20-cijferig getal:

- 10 cijfers - 8024680246
- een optionele spatie of afbreekstreester
- 10 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- In de regex Regex_Finland_European_Health_Insurance_Number inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Finland_European_Health_Insurance_Number gevonden.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsäkringskort
- gezondheidskaart
- zorgverzekeringskaart
- nummer van ziektekostenverzekering
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>Nationale finland-id

### <a name="format"></a>Opmaak

zes cijfers plus een teken dat een eeuw plus drie cijfers plus een vinkje aangeeft

### <a name="pattern"></a>Patroon

Patroon moet de volgende gegevens bevatten:
- zes cijfers in de indeling DDMMYY, een geboortedatum
- century marker ('-', '+' of 'a')
- persoonlijk identificatienummer met drie cijfers
- een cijfer of letter (case insensitive) dat een controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- de functie Func_finnish_national_id inhoud vindt die overeenkomt met het patroon
- een trefwoord uit Keyword_finnish_national_id wordt gevonden
- de checksum passeert

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- de functie Func_finnish_national_id inhoud vindt die overeenkomt met het patroon
- de checksum passeert

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- id-nummer
- identificatienummer
- identiteetti numero
- identiteitsnummer
- idnummer
- kansallinen henkilötunnus
- kansallisen henkilökortin
- nationale id-kaart
- national id no.
- persoonlijke id
- persoonlijke identiteitscode
- personalidnumber #
- personbeteckning
- personnummer
- sociaal-zekerheidsnummer
- sosiaaliturvatunnus
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- tunnistenumero
- tunnus-getal
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Finland paspoortnummer

Deze entiteit is beschikbaar in het gevoelige informatietype EU-paspoortnummer en is beschikbaar als een op zichzelf staand gevoelige informatietype entiteit.

### <a name="format"></a>Opmaak
combinatie van negen letters en cijfers

### <a name="pattern"></a>Patroon
combinatie van negen letters en cijfers:
- twee letters (niet hoofdlettergevoelig)
- zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale `Regex_finland_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_passport_number` van of `Keyword_finland_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale `Regex_finland_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_passport_number` van of `Keyword_finland_passport_number` wordt gevonden.

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- passinummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum

## <a name="france-drivers-license-number"></a>Rijbewijsnummer van Frankrijk

Deze entiteit is beschikbaar in het type gevoelige informatie over het EU-rijbewijsnummer en is beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

12 cijfers

### <a name="pattern"></a>Patroon

12 cijfers met validatie om vergelijkbare patronen, zoals Franse telefoonnummers, te korting te geven

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- de functie Func_french_drivers_license inhoud vindt die overeenkomt met het patroon.
- een trefwoord uit Keyword_french_drivers_license wordt gevonden.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal
- permis de conduire
- licentienummer
- licentienummer
- licentienummers
- licentienummers
- numéros de licence


## <a name="france-health-insurance-number"></a>Frankrijk gezondheidsverzekeringsnummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

21-cijferig getal

### <a name="pattern"></a>Patroon

21-cijferig getal:

- 10 cijfers
- een optionele spatie
- 10 cijfers
- een optionele spatie
- een cijfer


### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- de regex Regex_France_Health_Insurance_Number inhoud die overeenkomt met het patroon.
- een trefwoord uit Keyword_France_Health_Insurance_Number wordt gevonden.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- verzekeringskaart
- carte vitaal
- carte d'assuré sociaal


## <a name="france-national-id-card-cni"></a>Franse nationale id-kaart (CNI)

### <a name="format"></a>Opmaak

12 cijfers

### <a name="pattern"></a>Patroon

12 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_france_cni inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_france_eu_national_id_card gevonden.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- kaartnummer
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte banke
- nationaal identificatienummer
- nationale identiteit
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitaal


## <a name="france-passport-number"></a>Frankrijk paspoortnummer
Deze entiteit is beschikbaar in het gevoelige informatietype EU-paspoortnummer. Het is ook beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

negen cijfers en letters

### <a name="pattern"></a>Patroon

negen cijfers en letters:
- twee cijfers
- twee letters (niet hoofdlettergevoelig)
- vijf cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_fr_passport` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_passport_number` van of `Keywords_france_eu_passport_number` wordt gevonden.
- Met de normale `Regex_eu_passport_date3` expressie wordt de datum gevonden in de indeling DD MM YYYY of wordt een trefwoord van `Keywords_eu_passport_date` gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_fr_passport` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_passport_number` van of `Keywords_france_eu_passport_number` wordt gevonden.


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="france-social-security-number-insee"></a>Frankrijkse socialezekerheidsnummer (INSEE)

### <a name="format"></a>Opmaak

15 cijfers

### <a name="pattern"></a>Patroon

Moet overeenkomen met een van de twee patronen:
- 13 cijfers gevolgd door een spatie gevolgd door twee cijfers<br/>
of
- 15 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_french_insee` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_fr_insee gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de functie Func_french_insee of Func_fr_insee wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- nationale id
- nationale identificatie
- no d'identité
- nee. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- geen d'identite
- nee. d'identite
- ssn
- ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- sociaal-zekerheidsnummer
- socialezekerheidscode
- sociaal verzekeringsnummer


## <a name="france-tax-identification-number"></a>Frankrijk btw-nummer

### <a name="format"></a>Opmaak

13 cijfers

### <a name="pattern"></a>Patroon

13 cijfers

- Eén cijfer dat 0, 1, 2 of 3 moet zijn
- Eén cijfer
- Een spatie (optioneel)
- Twee cijfers
- Een spatie (optioneel)
- Drie cijfers
- Een spatie (optioneel)
- Drie cijfers
- Een spatie (optioneel)
- Drie controlecijfers


### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_france_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_france_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_france_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Frankrijk btw-nummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 13 tekens

### <a name="pattern"></a>Patroon

Alfanumeriek patroon van 13 tekens:

- twee letters - FR (hoofdletters ongevoelig)
- een optionele spatie of afbreekstreester
- twee letters of cijfers
- een optionele spatie, punt, afbreekstreester of komma
- drie cijfers
- een optionele spatie, punt, afbreekstreester of komma
- drie cijfers
- een optionele spatie, punt, afbreekstreester of komma
- drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_france_value_added_tax_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_france_value_added_tax_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_france_value_added_tax_number wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- btw-nummer
- btw-nee
- btw #
- btw
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification-sirene


## <a name="germany-drivers-license-number"></a>Het rijbewijsnummer van Duitsland

Deze entiteit van het type gevoelige informatie is opgenomen in het gevoelige informatietype EU-rijbewijsnummer. Het is ook beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

combinatie van 11 cijfers en letters

### <a name="pattern"></a>Patroon

11 cijfers en letters (niet hoofdlettergevoelig):
- een cijfer of letter
- twee cijfers
- zes cijfers of letters
- een cijfer
- een cijfer of letter

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_german_drivers_license inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_german_drivers_license_number gevonden.
- De checksum passeert.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-führerschein
- no-fuhrerschein
- no-fuehrerschein
- n-führerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dlno


## <a name="germany-identity-card-number"></a>Duitsland-identiteitskaartnummer

### <a name="format"></a>Opmaak

sinds 1 november 2010: Negen letters en cijfers

van 1 april 1987 tot en met 31 oktober 2010: 10 cijfers

### <a name="pattern"></a>Patroon

sinds 1 november 2010:
- één letter (niet case-sensitive)
- acht cijfers

van 1 april 1987 tot en met 31 oktober 2010:
- 10 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_germany_id_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_germany_id_card gevonden.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identificatie
- identifikation
- identifizierungsnummer
- identiteitskaart
- identiteitsnummer
- id-nummer
- persoonlijke id
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Duitsland paspoortnummer

Deze entiteit is opgenomen in het gevoelige informatietype EU-paspoortnummer en is beschikbaar als een op zichzelf staand gevoelige informatietype entiteit.

### <a name="format"></a>Opmaak

10 cijfers of letters

### <a name="pattern"></a>Patroon

Patroon moet de volgende gegevens bevatten:
- eerste teken is een cijfer of een letter uit deze set (C, F, G, H, J, K)
- drie cijfers
- vijf cijfers of letters uit deze set (C, -H, J-N, P, R, T, V-Z)
- een cijfer

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_german_passport inhoud die overeenkomt met het patroon.
- Een trefwoord `Keyword_german_passport` van of `Keywords_eu_passport_number_common` wordt gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_german_passport_data inhoud die overeenkomt met het patroon.
- Een trefwoord `Keyword_german_passport` van of `Keywords_eu_passport_number_common` wordt gevonden.
- De checksum passeert.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- heruitgave
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Wachtwoordnummer
- reisepässe
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers


## <a name="germany-tax-identification-number"></a>Btw-nummer duitsland

### <a name="format"></a>Opmaak

11 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

11 cijfers

- Twee cijfers
- Een optionele spatie
- Drie cijfers
- Een optionele spatie
- Drie cijfers
- Een optionele spatie
- Twee cijfers
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_germany_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_germany_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_germany_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer-id
- steueridentifikationsnummer
- steuernummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Duitsland btw-nummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 11 tekens

### <a name="pattern"></a>Patroon

Alfanumeriek patroon van 11 tekens:

- een letter D of d
- een letter E of e
- een optionele spatie
- drie cijfers
- een optionele spatie of komma
- drie cijfers
- een optionele spatie of komma
- drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_germany_value_added_tax_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_germany_value_added_tax_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_germany_value_added_tax_number inhoud die overeenkomt met het patroon.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- btw-nummer
- btw-nee
- btw #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Licentienummer van Griekenland

Deze entiteit is opgenomen in het gevoelige informatietype Eu Driver's License Number. Het is ook beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_greece_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_greece_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver is s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Nationale Griekenland-id-kaart

### <a name="format"></a>Opmaak

Combinatie van 7-8 letters en cijfers plus een streepje

### <a name="pattern"></a>Patroon

Zeven letters en cijfers (oude notatie):
- Eén letter (een letter van het Griekse alfabet)
- Een streepje
- Zes cijfers

Acht letters en cijfers (nieuwe notatie):
- Twee letters waarvan het hoofdletterteken voorkomt in zowel het Griekse als het Latijnse alfabet (ABEZHIKMNOPTYX)
- Een streepje
- Zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_greece_id_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_greece_id_card gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_greece_id_card inhoud die overeenkomt met het patroon.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- Griekse id
- Griekse nationale id
- Griekse persoonlijke id-kaart
- Griekse politie-id
- identiteitskaart
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Griekenland paspoortnummer

### <a name="format"></a>Opmaak

Twee letters gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

Twee letters gevolgd door zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_greece_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_greece_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de indeling `Regex_greece_eu_passport_date` DD MMM YY (voorbeeld - 28 aug 19) of wordt een trefwoord `Keywords_greece_eu_passport_date` gevonden van

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_greece_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_greece_eu_passport_number` wordt gevonden.

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Griekenland-nummer voor sociale zekerheid (AMKA)
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

11 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

- Zes cijfers als geboortedatum YYMMDD
- Vier cijfers
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_greece_eu_ssn` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_greece_eu_ssn_or_equivalent` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_greece_eu_ssn` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- sociale zekerheid nee
- socialsecurityno #
- sociaal-zekerheidsnummer
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Btw-nummer van Griekenland
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

Negen cijfers

### <a name="checksum"></a>Checksum

Niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de normale  `Regex_greece_eu_tax_file_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_greece_eu_tax_file_number` trefwoord uit gevonden.

```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- aφμ|aφμ αριμ
- aφμ
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- btw-register nee
- btw-registernummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- taxregistryno #
- tin-id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Hongkong-identiteitskaartnummer (HKID)

### <a name="format"></a>Opmaak

Combinatie van 8-9 letters en cijfers plus optionele haakjes rond het uiteindelijke teken

### <a name="pattern"></a>Patroon

Combinatie van 8-9 letters:
- 1-2 letters (niet hoofdlettergevoelig)
- Zes cijfers
- Het uiteindelijke teken (elk cijfer of de letter A), dat het controlecijfer is en optioneel tussen haakjes wordt omsloten.

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_hong_kong_id_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_hong_kong_id_card gevonden.
- De checksum passeert.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_hong_kong_id_card inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- Hongkong-identiteitskaart
- HKIDC
- id-kaart
- identiteitskaart
- hk-identiteitskaart
- hongkong-id
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証


## <a name="hungary-drivers-license-number"></a>Rijbewijsnummer van Hongarije

### <a name="format"></a>Opmaak

Twee letters gevolgd door zes cijfers

### <a name="pattern"></a>Patroon

Twee letters en zes cijfers:

- Twee letters (niet hoofdlettergevoelig)
- Zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de normale  `Regex_hungary_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_hungary_eu_driver's_license_number` wordt gevonden.

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver is s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Persoonlijk identificatienummer van Hongarije
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

11 cijfers:

- Eén cijfer dat overeenkomt met geslacht, 1 voor man, 2 voor vrouw. Andere getallen zijn ook mogelijk voor burgers die vóór 1900 zijn geboren of voor burgers met een dubbele nationaliteit.
- Zes cijfers die overeenkomen met de geboortedatum (YYMMDD)
- Drie cijfers die overeenkomen met een serieel getal
- Eén vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de  `Func_hungary_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_hungary_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de  `Func_hungary_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id-nummer
- identificatienummer
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Paspoortnummer van Hongarije

### <a name="format"></a>Opmaak

Twee letters gevolgd door zes of zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

Twee letters gevolgd door zes of zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_hungary_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_hungary_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt datum gevonden in de indeling `Regex_hungary_eu_passport_date` DD MMM/MMM YY (Voorbeeld - 01 MÁR/MAR 12) of een trefwoord uit `Keywords_eu_passport_date` wordt gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_hungary_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_hungary_eu_passport_number` wordt gevonden.

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="hungary-social-security-number-taj"></a>Hongarijese sociale zekerheidsnummer (TAJ)

### <a name="format"></a>Opmaak

Negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

Negen cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de  `Func_hungary_eu_ssn_or_equivalent` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_hungary_eu_ssn_or_equivalent` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de  `Func_hungary_eu_ssn_or_equivalent` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- Hongaars sociaal-zekerheidsnummer
- sociaal-zekerheidsnummer
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- sociale zekerheid nee
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Btw-nummer van Hongarije
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

10 cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

10 cijfers:

- Eén cijfer dat '8' moet zijn
- Acht cijfers
- Eén vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de  `Func_hungary_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_hungary_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de  `Func_hungary_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- Hongaars tin
- hungatiantin #
- belastinginstantie nee
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- btw-nummer


## <a name="hungary-value-added-tax-number"></a>Btw-nummer in Hongarije
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 10 tekens

### <a name="pattern"></a>Patroon

Alfanumeriek patroon van 10 tekens:

- twee letters - HU of hu
- optionele spatie
- acht cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de Func_hungarian_value_added_tax_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_hungarian_value_added_tax_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de Func_hungarian_value_added_tax_number wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- btw
- btw-nummer
- btw #
- vatno #
- hungarianvatno #
- belasting nee.
- btw áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>India permanent accountnummer (PAN)

### <a name="format"></a>Opmaak

10 letters of cijfers

### <a name="pattern"></a>Patroon

10 letters of cijfers:
- Drie letters (niet hoofdlettergevoelig)
- Een letter in C, P, H, F, A, T, B, L, J, G (niet case-sensitive)
- Een brief
- Vier cijfers
- Een letter die een alfabetisch controlecijfer is

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_india_permanent_account_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_india_permanent_account_number gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_india_permanent_account_number inhoud die overeenkomt met het patroon.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent accountnummer
- PAN

## <a name="india-unique-identification-aadhaar-number"></a>India unique identification (Aadhaar) number

### <a name="format"></a>Opmaak

12 cijfers met optionele spaties of streepjes

### <a name="pattern"></a>Patroon

12 cijfers:
- Een cijfer dat niet 0 of 1 is
- Drie cijfers
- Een optionele spatie of streepje
- Vier cijfers
- Een optionele spatie of streepje
- Het laatste cijfer, dat het controlecijfer is

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_india_aadhaar wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_india_aadhar gevonden.
- De checksum passeert.
-
Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de Func_india_aadhaar wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai

## <a name="indonesia-identity-card-ktp-number"></a>KTP-nummer (Indonesia Identity Card)

### <a name="format"></a>Opmaak

16 cijfers met optionele perioden

### <a name="pattern"></a>Patroon

16 cijfers:
- Provinciecode met twee cijfers
- Een punt (optioneel)
- Regency of stadscode met twee cijfers
- Subdistrictcode met twee cijfers
- Een punt (optioneel)
- Zes cijfers in de indeling DDMMYY, die de geboortedatum zijn
- Een punt (optioneel)
- Vier cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- De normale expressie Regex_indonesia_id_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_indonesia_id_card gevonden.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependukan

## <a name="international-banking-account-number-iban"></a>Internationaal bankrekeningnummer (IBAN)

### <a name="format"></a>Opmaak

Landcode (twee letters) plus controlecijfers (twee cijfers) plus bbannummer (maximaal 30 tekens)

### <a name="pattern"></a>Patroon

Patroon moet de volgende gegevens bevatten:

- Landcode met twee letters
- Twee controlecijfers (gevolgd door een optionele spatie)
- 1-7 groepen van vier letters of cijfers (kunnen worden gescheiden door spaties)
- 1-3 letters of cijfers

De notatie voor elk land is iets anders. Het type IBAN-gevoelige informatie bestrijkt deze 60 landen:

- ad
- ae
- al
- op
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- do
- ee
- es
- fi
- fo
- fr
- gb
- ge
- gi
- gl
- gr
- hr
- hu
- ie
- il
- is
- het
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- md
- mij
- mk
- mr.
- mt
- mu
- nl
- nee
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de Func_iban wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

Geen


## <a name="international-classification-of-diseases-icd-10-cm"></a>Internationale classificatie van ziektes (ICD-10-CM)

### <a name="format"></a>Opmaak

Woordenlijst

### <a name="pattern"></a>Patroon

Trefwoord

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Er wordt een trefwoord Dictionary_icd_10_updated gevonden.
- Er wordt een trefwoord Dictionary_icd_10_codes gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Er wordt een trefwoord Dictionary_icd_10_ bijgewerkt.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Trefwoorden

Elke term uit de Dictionary_icd_10_updated woordenlijst met trefwoorden, die is gebaseerd op de internationale classificatie van ziektes, tiende revisie, klinische wijziging [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Dit type zoekt alleen naar de term, niet naar de verzekeringscodes.

Elke term uit de Dictionary_icd_10_codes woordenlijst met trefwoorden, die is gebaseerd op de internationale classificatie van ziektes, tiende revisie, klinische wijziging [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Dit type zoekt alleen naar verzekeringscodes, niet naar de beschrijving.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Internationale classificatie van ziektes (ICD-9-CM)

### <a name="format"></a>Opmaak

Woordenlijst

### <a name="pattern"></a>Patroon

Trefwoord

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Er wordt een trefwoord Dictionary_icd_9_updated gevonden.
- Er wordt een trefwoord Dictionary_icd_9_codes gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Er wordt een trefwoord Dictionary_icd_9_updated gevonden.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

Elke term uit de Dictionary_icd_9_updated woordenlijst met trefwoorden, die is gebaseerd op de internationale classificatie van ziektes, negende revisie, klinische wijziging [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Dit type zoekt alleen naar de term, niet naar de verzekeringscodes.

Elke term uit de Dictionary_icd_9_codes woordenlijst met trefwoorden, die is gebaseerd op de internationale classificatie van ziektes, negende revisie, klinische wijziging [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Dit type zoekt alleen naar verzekeringscodes, niet naar de beschrijving.

## <a name="ip-address"></a>IP-adres

### <a name="format"></a>Opmaak

#### <a name="ipv4"></a>IPv4:
Complex patroon dat bestand is voor opgemaakte (perioden) en niet-opgemaakte versies (geen perioden) van de IPv4-adressen

#### <a name="ipv6"></a>IPv6:
Complex patroon dat bestand is voor opgemaakte IPv6-getallen (inclusief dubbele punt)

### <a name="pattern"></a>Patroon

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Voor IPv6 heeft een DLP-beleid er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_ipv6_address inhoud die overeenkomt met het patroon.
- Er wordt geen trefwoord Keyword_ipaddress gevonden.

Voor IPv4 heeft een DLP-beleid er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_ipv4_address inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_ipaddress gevonden.

Voor IPv6 heeft een DLP-beleid er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_ipv6_address inhoud die overeenkomt met het patroon.
- Er wordt geen trefwoord Keyword_ipaddress gevonden.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (dit trefwoord is case-sensitive)
- ip-adres
- ip-adressen
- internetprotocol
- IP-כתובת

## <a name="ireland-drivers-license-number"></a>Nummer van ierlands rijbewijs

### <a name="format"></a>Opmaak

Zes cijfers, gevolgd door vier letters

### <a name="pattern"></a>Patroon

Zes cijfers en vier letters:

- Zes cijfers
- Vier letters (niet hoofdlettergevoelig)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:

- Met de normale  `Regex_ireland_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_ireland_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver is s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Ierland paspoortnummer

### <a name="format"></a>Opmaak

Twee letters of cijfers gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

Twee letters of cijfers, gevolgd door zeven cijfers:

- Twee cijfers of letters (niet hoofdlettergevoelig)
- Zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_ireland_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_ireland_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt datum gevonden in de indeling `Regex_ireland_eu_passport_date` DD MMM/MMM YYYY (Voorbeeld - 01 BEA/MEI 1988) of een trefwoord uit `Keywords_eu_passport_date` wordt gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_ireland_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_ireland_eu_passport_number` wordt gevonden.

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport-numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="ireland-personal-public-service-pps-number"></a>Nummer van persoonlijke openbare service (PPS) van Ierland

### <a name="format"></a>Opmaak

Oude notatie (tot 31 december 2012):
- zeven cijfers gevolgd door 1-2 letters

Nieuwe notatie (1 januari 2013 en daarna):
- zeven cijfers gevolgd door twee letters

### <a name="pattern"></a>Patroon

Oude notatie (tot 31 december 2012):
- zeven cijfers
- één tot twee letters (niet hoofdlettergevoelig)

Nieuwe notatie (1 januari 2013 en daarna):
- zeven cijfers
- een letter (niet case-sensitive) die een alfabetisch vinkje is
- Een optionele letter in het bereik A-I of 'W'

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_ireland_pps wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_ireland_eu_national_id_card gevonden.
- De checksum passeert.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_ireland_pps wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- clientidentiteitsservice
- identificatienummer
- persoonlijk id-nummer
- persoonlijk nummer van openbare service
- persoonlijke service nee
- phearsanta seirbhíse poiblí
- pps no
- pps-getal
- pps-getal
- pps-service nee
- ppsn
- ppsno #
- ppsno
- psp
- openbare service nee
- publicserviceno #
- publicserviceno
- omzet- en sociale verzekeringsnummer
- rsi no
- rsi-getal
- rsin
- seirbhís aitheantais-client
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Israëls bankrekeningnummer

### <a name="format"></a>Opmaak

13 cijfers

### <a name="pattern"></a>Patroon

Opgemaakt:
- twee cijfers
- een streepje
- drie cijfers
- een streepje
- acht cijfers

Niet-opgemaakt:
- 13 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_israel_bank_account_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_israel_bank_account_number gevonden.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bankrekeningnummer
- Bankrekening
- Accountnummer
- מספר חשבון בנק

## <a name="israel-national-identification-number"></a>Nationaal identificatienummer van Israël

### <a name="format"></a>Opmaak

negen cijfers

### <a name="pattern"></a>Patroon

negen opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_israeli_national_id_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Israel_National_ID gevonden.
- De checksum passeert.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnummer #
-   id-nummer
-   identiteit nee        
-   identiteitsnummer #
-   identiteitsnummer
-   israeliidentitynumber       
-   persoonlijke id
-   unieke id  


## <a name="italy-drivers-license-number"></a>Nummer van het rijbewijs van Italië

Dit type entiteit is opgenomen in het gevoelige informatietype Eu Driver's License Number. Het is ook beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

een combinatie van 10 letters en cijfers

### <a name="pattern"></a>Patroon

een combinatie van 10 letters en cijfers:
- één letter (niet case-sensitive)
- de letter "A" of "V" (niet case-sensitive)
- zeven cijfers
- één letter (niet case-sensitive)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale `Regex_italy_drivers_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_driver's_license_number` van of `Keyword_italy_drivers_license_number` wordt gevonden.

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>Fiscale code van Italië
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

een combinatie van letters en cijfers met 16 tekens in het opgegeven patroon

### <a name="pattern"></a>Patroon

Een combinatie van 16 tekens van letters en cijfers:
- drie letters die overeenkomen met de eerste drie medeklinkers in de familienaam
- drie letters die overeenkomen met de eerste, derde en vierde medeklinker in de voornaam
- twee cijfers die overeenkomen met de laatste cijfers van het geboortejaar
- een letter die overeenkomt met de letter voor de maand van de geboorte: letters worden in alfabetische volgorde gebruikt, maar alleen de letters A tot en met E, H, L, M, P, R tot en met T worden gebruikt (januari is dus A en oktober is R)
- twee cijfers die overeenkomen met de dag van de geboortemaand om onderscheid te maken tussen geslachten, wordt 40 toegevoegd aan de geboortedatum voor vrouwen
- vier cijfers die overeenkomen met de gebiedscode die specifiek is voor de gemeente waar de persoon is geboren (landcodes worden gebruikt voor het buitenland)
- één pariteitscijfer

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_italy_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_italy_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_italy_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- fiscale code
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- persoonlijk certificaatnummer
- persoonlijke code
- persoonlijke id-code
- persoonlijk id-nummer
- personalcodeno #
- btw-code
- belasting-id
- geen belastingidentificatie
- btw-nummer
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="italy-passport-number"></a>Italië paspoortnummer

### <a name="format"></a>Opmaak

twee letters of cijfers gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

twee letters of cijfers, gevolgd door zeven cijfers:

- twee cijfers of letters (niet hoofdlettergevoelig)
- zeven cijfers

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_italy_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_italy_eu_passport_number` wordt gevonden.
- De normale expressie vindt datum in de indeling `Regex_italy_eu_passport_date` DD MMM/MMM YYYY (Voorbeeld - 01 GEN/JAN 1988) of een trefwoord uit `Keywords_eu_passport_date` wordt gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_italy_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_italy_eu_passport_number` wordt gevonden.

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="italy-value-added-tax-number"></a>#A0 #A0 #A0 #A0 #A0 #A
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 13 tekens met optionele scheidingstekens

### <a name="pattern"></a>Patroon

13 tekens alfanumeriek patroon met optionele scheidingstekens:

- Ik of ik
- T of t
- optionele spatie, punt, afbreekstreester of komma
- 11 cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_italy_value_added_tax_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_italy_value_added_tax_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_italy_value_added_tax_number wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- btw-nummer
- btw-nee
- btw #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Japans bankrekeningnummer

### <a name="format"></a>Opmaak

zeven of acht cijfers

### <a name="pattern"></a>Patroon

bankrekeningnummer:
- zeven of acht cijfers
- bankrekeningstakcode:
- vier cijfers
- een spatie of streepje (optioneel)
- drie cijfers

Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_jp_bank_account wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_bank_account gevonden.
- Een van de volgende gegevens is waar:
- De functie Func_jp_bank_account_branch_code inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_bank_branch_code gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_jp_bank_account wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_bank_account gevonden.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Rekeningnummer controleren
- Account controleren
- Account controleren #
- Acct-nummer controleren
- Acct controleren #
- Acct No controleren.
- Accountnummer controleren.
- Bankrekeningnummer
- Bankrekening
- Bankrekening #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bankrekening nee.
- Spaarrekeningnummer
- Spaarrekening
- Spaarrekening #
- Acct-nummer voor spaarrekening
- Spaarrekening #
- Savings Acct No.
- Spaarrekening Nee.
- Betaalrekeningnummer
- Betaalrekening
- Betaalrekening #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Betaalrekening nee.
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Japans rijbewijsnummer

### <a name="format"></a>Opmaak

12 cijfers

### <a name="pattern"></a>Patroon

12 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_jp_drivers_license_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_drivers_license_number gevonden.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- slicenses voor stuurprogramma's
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Japan My Number - Corporate
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

13-cijferig getal

### <a name="pattern"></a>Patroon

13-cijferig getal:

- één cijfer van één tot negen
- 12 cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_japanese_my_number_corporate inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_japanese_my_number_corporate gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_japanese_my_number_corporate inhoud die overeenkomt met het patroon.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- bedrijfsnummer
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Japan Mijn nummer - Persoonlijk
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

12-cijferig getal

### <a name="pattern"></a>Patroon

12-cijferig getal:

- vier cijfers
- een optionele spatie, punt of afbreekstreester
- vier cijfers
- een optionele spatie, punt of afbreekstreester
- vier cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_japanese_my_number_personal wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_japanese_my_number_personal gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_japanese_my_number_personal wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- mijn nummer
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード


## <a name="japan-passport-number"></a>Japan paspoortnummer

### <a name="format"></a>Opmaak

twee letters gevolgd door zeven cijfers

### <a name="pattern"></a>Patroon

twee letters (niet hoofdlettergevoelig) gevolgd door zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_jp_passport inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_passport gevonden.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Paspoort
- Paspoortnummer
- Paspoort nee.
- Paspoort #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パトポーーNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Japan residence card number

### <a name="format"></a>Opmaak

12 letters en cijfers

### <a name="pattern"></a>Patroon

12 letters en cijfers:
- twee letters (niet hoofdlettergevoelig)
- acht cijfers
- twee letters (niet hoofdlettergevoelig)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_jp_residence_card_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_residence_card_number gevonden.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Nummer van de woonplaatskaart
- Residence card no
- Woonplaatskaart #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Japans registratienummer

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

11 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_jp_resident_registration_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_resident_registration_number gevonden.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Registratienummer voor ingezetene
- Basisregisternummer voor bewoners
- Resident Registration No.
- Resident Register No.
- Bewoners Basic Registry No.
- Basic Resident Register No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証


## <a name="japan-social-insurance-number-sin"></a>Japans sociaal verzekeringsnummer (SIN)

### <a name="format"></a>Opmaak

7-12 cijfers

### <a name="pattern"></a>Patroon

7-12 cijfers:
- vier cijfers
- een afbreekstreester (optioneel)
- zes cijfers OF
- 7-12 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_jp_sin wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_sin gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_jp_sin_pre_1997 wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_jp_sin gevonden.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No.
- Aantal sociale verzekeringen
- Sociaal verzekeringsnummer
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Letlandse nummer van het rijbewijs

### <a name="format"></a>Opmaak

drie letters gevolgd door zes cijfers

### <a name="pattern"></a>Patroon

drie letters en zes cijfers:

- drie letters (niet hoofdlettergevoelig)
- zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_latvia_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_latvia_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver is s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Persoonlijke code letland

### <a name="format"></a>Opmaak

11 cijfers en een optioneel afbreekstreester

### <a name="pattern"></a>Patroon

Oude indeling

11 cijfers en een afbreekstreester:

- zes cijfers die overeenkomen met de geboortedatum (DDMMYY)
- een afbreekstreester
- een cijfer dat overeenkomt met de eeuw van geboorte ("0" voor de 19e eeuw, "1" voor de 20e eeuw en "2" voor de 21e eeuw)
- vier cijfers, willekeurig gegenereerd

Nieuwe indeling

11 cijfers

- Twee cijfers "32"
- Negen cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_latvia_eu_national_id_card` functie of regex `Regex_latvia_eu_national_id_card_new_format` wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_latvia_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_latvia_eu_national_id_card` functie of regex `Regex_latvia_eu_national_id_card_new_format` wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- beheernummer
- alvas nē
- geboortedatum
- burgernummer
- burgerlijk getal
- elektronisch tellingsnummer
- elektronisch nummer
- fiscale code
- gezondheidsgebruikersnummer
- id #
- id-code
- identificatienummer
- identifikācijas numurs
- id-nummer
- individueel getal
- latvija alva
- nacionālais-id
- nationale id
- nationaal identificatienummer
- nationaal identiteitsnummer
- nationaal verzekeringsnummer
- nummer van het nationale register
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- persoonlijk certificaatnummer
- persoonlijke code
- persoonlijke id-code
- persoonlijk id-nummer
- persoonlijke identificatiecode
- persoonlijke id
- persoonlijk identiteitsnummer
- persoonlijk nummer
- persoonlijke numerieke code
- personalcodeno #
- personas kods
- bevolkingsidentificatiecode
- openbare servicenummer
- registratienummer
- opbrengstnummer
- sociaal verzekeringsnummer
- sociaal-zekerheidsnummer
- belastingcode van de staat
- btw-bestandsnummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- nummer van de kiezer

## <a name="latvia-passport-number"></a>Letland paspoortnummer

### <a name="format"></a>Opmaak

twee letters of cijfers gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

twee letters of cijfers, gevolgd door zeven cijfers:

- twee cijfers of letters (niet hoofdlettergevoelig)
- zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_latvia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_latvia_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_latvia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_latvia_eu_passport_number` wordt gevonden.

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="lithuania-drivers-license-number"></a>Litouws rijbewijsnummer

### <a name="format"></a>Opmaak

acht cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_lithuania_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_lithuania_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver is s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Persoonlijke code litouwen
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

11 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

11 cijfers zonder spaties en scheidingstekens:

- één cijfer (1-6) dat overeenkomt met het geslacht en de eeuw van de geboorte van de persoon
- zes cijfers die overeenkomen met geboortedatum (YYMMDD)
- drie cijfers die overeenkomen met het seriële getal van de geboortedatum
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_lithuania_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_lithuania_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_lithuania_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- burgerservicenummer
- mokesčič id
- mokesčihou identifikavimas numeris
- mokesčič identifikavimo numeris
- mokesčič numeris
- nationaal identificatienummer
- persoonlijke code
- persoonlijke numerieke code
- piliečio paslaugos numeris
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- uniek identificatienummer
- uniek identiteitsnummer
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Litouws paspoortnummer

### <a name="format"></a>Opmaak

acht cijfers of letters zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers of letters (niet hoofdlettergevoelig)

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_lithuania_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_lithuania_eu_passport_number` wordt gevonden.
- Met de normale `Regex_eu_passport_date3` expressie wordt de datum gevonden in de indeling DD MM YYYY of wordt een trefwoord van `Keywords_eu_passport_date` gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_lithuania_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_lithuania_eu_passport_number` wordt gevonden.

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso-numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="luxemburg-drivers-license-number"></a>Luxemburgs rijbewijsnummer

### <a name="format"></a>Opmaak

zes cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_luxemburg_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_luxemburg_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver is s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Luxemburgs nationaal identificatienummer (natuurlijke personen)
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

13 cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

13 cijfers:

- 11 cijfers
- twee controlecijfers

### <a name="checksum"></a>Checksum

ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_luxemburg_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_luxemburg_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_luxemburg_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige-id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- afzonderlijke code
- individuele id
- individuele identificatie
- individuele identiteit
- numéro d'identification-personeel
- persoonlijke id
- persoonlijke identificatie
- persoonlijke identiteit
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- unieke id
- unieke identiteit
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Luxemburgs paspoortnummer

### <a name="format"></a>Opmaak

acht cijfers of letters zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

acht cijfers of letters (niet hoofdlettergevoelig)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_luxemburg_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_luxemburg_eu_passport_number` wordt gevonden.
- Met de normale `Regex_eu_passport_date3` expressie wordt de datum gevonden in de indeling DD MM YYYY of wordt een trefwoord van `Keywords_eu_passport_date` gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_luxemburg_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_luxemburg_eu_passport_number` wordt gevonden.

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- Luxemburgse pas
- Luxemburg passeport
- Luxemburgs paspoort
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Luxemburgs nationaal identificatienummer (niet-natuurlijke personen)

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

11 cijfers

- twee cijfers
- een optionele spatie
- drie cijfers
- een optionele spatie
- drie cijfers
- een optionele spatie
- twee cijfers
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_luxemburg_eu_tax_file_number_non_natural` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_luxemburg_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_luxemburg_eu_tax_file_number_non_natural` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxemburgse belasting identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- sociale zekerheid
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier-id
- steier identifikatiounsnummer
- steiernummer
- steuer-id
- steueridentifikationsnummer
- steuernummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Nummer van maleisische identificatiekaart

### <a name="format"></a>Opmaak

12 cijfers met optionele afbreekstree streepjes

### <a name="pattern"></a>Patroon

12 cijfers:
- zes cijfers in de notatie YYMMDD, de geboortedatum
- een streepje (optioneel)
- Plaats-van-geboortecode met twee letters
- een streepje (optioneel)
- drie willekeurige cijfers
- geslachtscode met één cijfer

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_malaysia_id_card_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_malaysia_id_card_number gevonden.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- digitale toepassingskaart
- i/c
- i/c no
- ic
- ic no
- id-kaart
- identificatiekaart
- identiteitskaart
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- Maleisische identiteitskaart
- Maleisische identiteitskaart
- nric
- persoonlijke identificatiekaart

## <a name="malta-drivers-license-number"></a>Malta-nummer van het rijbewijs

### <a name="format"></a>Opmaak

Combinatie van twee tekens en zes cijfers in het opgegeven patroon

### <a name="pattern"></a>Patroon

combinatie van twee tekens en zes cijfers:

- twee tekens (cijfers of letters, niet hoofdlettergevoelig)
- een spatie (optioneel)
- drie cijfers
- een spatie (optioneel)
- drie cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_malta_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_malta_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver is s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Malta-identiteitskaartnummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

zeven cijfers, gevolgd door één letter

### <a name="pattern"></a>Patroon

zeven cijfers, gevolgd door één letter:

- zeven cijfers
- één letter in 'M, G, A, P, L, H, B, Z' (case insensitive)

### <a name="checksum"></a>Checksum

Niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_malta_eu_national_id_card` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_malta_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_malta_eu_national_id_card` expressie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- burgerservicenummer
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- persoonlijke numerieke code
- uniek identificatienummer
- uniek identiteitsnummer
- uniqueidentityno #


## <a name="malta-passport-number"></a>Malta-paspoortnummer

### <a name="format"></a>Opmaak

zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_malta_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_malta_eu_passport_number` wordt gevonden.
- Er wordt een `Keywords_eu_passport_date` trefwoord uit gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_malta_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_malta_eu_passport_number` wordt gevonden.

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="malta-tax-identification-number"></a>Malta-nummer voor belastingidentificatie

### <a name="format"></a>Opmaak

Voor Maltese nationals:
- zeven cijfers en één letter in het opgegeven patroon

Niet-Maltese nationals en Maltese entiteiten:
- negen cijfers

### <a name="pattern"></a>Patroon

Maltese nationals: zeven cijfers en één letter

- zeven cijfers
- één letter (niet case-sensitive)

Niet-Maltese nationals en Maltese entiteiten: negen cijfers

- negen cijfers

### <a name="checksum"></a>Checksum

Niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De regex  `Regex_malta_eu_tax_file_number`  of zoekt inhoud die overeenkomt met het `Regex_malta_eu_tax_file_number_non_maltese_national` patroon.
- Er wordt een  `Keywords_malta_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De regex  `Regex_malta_eu_tax_file_number` of zoekt inhoud die overeenkomt met het `Regex_malta_eu_tax_file_number_non_maltese_national` patroon.

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- burgerservicenummer
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- persoonlijke numerieke code
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- uniek identificatienummer
- uniek identiteitsnummer
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Medicare Beneficiary Identifier (MBI)-kaart

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 11 tekens

### <a name="pattern"></a>Patroon

- één cijfer tussen 1 en 9
- één letter exclusief S, L, O, I, B, Z
- één cijfer of letter exclusief S, L, O, I, B, Z
- één cijfer
- een optioneel afbreekstreester
- één letter exclusief S, L, O, I, B, Z
- één cijfer of letter exclusief S, L, O, I, B, Z
- één cijfer
- een optioneel afbreekstreester
- twee letters exclusief S, L, O, I, B, Z
- twee cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_mbi_card` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keyword_mbi_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_mbi_card` expressie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- hospik zijn begunstigden #
- medicare beneficiary identifier
- hospik zijn geen begunstigden
- hospik zijn begunstigdennummer
- hospik zijn begunstigden #


## <a name="mexico-unique-population-registry-code-curp"></a>Mexico Unique Population Registry Code (CURP)

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 18 tekens

### <a name="pattern"></a>Patroon

- vier letters (hoofdletters ongevoelig)
- zes cijfers die een geldige datum aangeven
- een letter - H/h of M/m
- twee letters die een geldige Mexicaanse staatscode aangeven
- drie letters
- één letter of cijfer
- één cijfer

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_mexico_population_registry_code` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keyword_mexico_population_registry_code` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_mexico_population_registry_code` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Unieke registercode voor populaties 
- unieke populatiecode
- CURP
- Persoonlijke id
- Unieke id
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave persoonlijke Identidad
- persoonlijke Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>BSN-nummer (Nederlandse burgerservice)

### <a name="format"></a>Opmaak

acht of negen cijfers met optionele spaties

### <a name="pattern"></a>Patroon

acht-negen cijfers:
- drie cijfers
- een spatie (optioneel)
- drie cijfers
- een spatie (optioneel)
- twee-drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_netherlands_bsn inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_netherlands_bsn gevonden.
- De checksum passeert.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn #
- bsn
- burgerservicenummer
- burgerservicenummer
- persoonsnummer
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsgebonden nummer
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- sociaal-fiscaal getal
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- uniek identificatienummer
- uniek identiteitsnummer
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Nederlands rijbewijsnummer

### <a name="format"></a>Opmaak

10 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

10 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_netherlands_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_netherlands_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver is s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijsnummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Nederlands paspoortnummer

### <a name="format"></a>Opmaak

negen letters of cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

negen letters of cijfers

### <a name="checksum"></a>Checksum

niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_netherlands_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_netherlands_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de indeling `Regex_netherlands_eu_passport_date` DD MMM/MMM YYYY (Voorbeeld - 26 MAA/MAR 2012)

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_netherlands_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_netherlands_eu_passport_number` wordt gevonden.

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoortnummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Btw-nummer van Nederland
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

negen cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_netherlands_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_netherlands_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_netherlands_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw-nummer
- belastingidentificatie van hollânske
- hulandes impuesto id-nummer
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto-identificatienummer
- impuesto-getal
- nederlands belasting id nummer
- Nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- Nederlandse belasting identificatie
- nederlandse belastingidentificatie
- de belastingidentificatie van Nederland
- Nederlands tin
- tin van Nederland
- belasting-id
- geen belastingidentificatie
- btw-nummer
- tal van belastingidentificatie
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- belasting tal
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Btw-nummer voor Nederland
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

Alfanumeriek patroon van 14 tekens

### <a name="pattern"></a>Patroon

Alfanumeriek patroon van 14 tekens:

- N of n
- L of l
- optionele spatie, punt of afbreekstreester
- negen cijfers
- optionele spatie, punt of afbreekstreester
- B of b
- twee cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_netherlands_value_added_tax_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_netherlands_value_added_tax_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_netherlands_value_added_tax_number inhoud die overeenkomt met het patroon.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- btw-nummer
- btw-nee
- btw #
- wearde tafoege tax getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Nieuw-Zeelands bankrekeningnummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

14-cijferig tot 16-cijferig patroon met optioneel scheidingsteken

### <a name="pattern"></a>Patroon

14-cijferig tot 16-cijferig patroon met optioneel scheidingsteken:

- twee cijfers
- een optioneel afbreekstreester of spatie
- drie tot vier cijfers
- een optioneel afbreekstreester of spatie
- zeven cijfers
- een optioneel afbreekstreester of spatie
- twee tot drie cijfers
- een afbreekstreester of spatie met opties

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_new_zealand_bank_account_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_new_zealand_bank_account_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_new_zealand_bank_account_number wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- accountnummer
- bankrekening
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Nieuw-Zeelands rijbewijsnummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

alfanumeriek patroon van acht tekens

### <a name="pattern"></a>Patroon

alfanumeriek patroon van acht tekens

- twee letters
- zes cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_newzealand_driver_license_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_newzealand_driver_license_number gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_newzealand_driver_license_number inhoud die overeenkomt met het patroon.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- driver lic
- rijbewijs
- rijbewijzen
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- internationaal rijbewijs
- internationale rijbewijzen
- nz automobile association
- nieuw-Zeelandse auto-vereniging


## <a name="new-zealand-inland-revenue-number"></a>Nieuw-Zeelandse belastingdienst
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

acht of negen cijfers met optionele scheidingstekens

### <a name="pattern"></a>Patroon

acht of negen cijfers met optionele scheidingstekens

- twee of drie cijfers
- een optionele spatie of afbreekstreester
- drie cijfers
- een optionele spatie of afbreekstreester
- drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_new_zealand_inland_revenue_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_new_zealand_inland_revenue_number gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_new_zealand_inland_revenue_number inhoud die overeenkomt met het patroon.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird no.
- ird no #
- nz ird
- nieuw-Zeeland ird
- ird-getal
- binnenlands opbrengstnummer


## <a name="new-zealand-ministry-of-health-number"></a>Nieuw-Zeelands ministerie van gezondheid nummer

### <a name="format"></a>Opmaak

drie letters, een spatie (optioneel) en vier cijfers

### <a name="pattern"></a>Patroon

- drie letters (niet hoofdlettergevoelig), behalve 'I' en 'O'
- een spatie (optioneel)
- vier cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_new_zealand_ministry_of_health_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_nz_terms gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_new_zealand_ministry_of_health_number wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- Nieuw-Zeeland
- Gezondheid
- behandeling
- National Health Index Number
- nhi-nummer
- nhi nee.
- NHI #
- National Health Index No.
- National Health Index Id
- National Health Index #

## <a name="new-zealand-social-welfare-number"></a>Nieuw-Zeelandse sociale zekerheid

Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

negen cijfers

### <a name="pattern"></a>Patroon

negen cijfers

- drie cijfers
- een optioneel afbreekstreester
- drie cijfers
- een optioneel afbreekstreester
- drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_newzealand_social_welfare_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_newzealand_social_welfare_number gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_newzealand_social_welfare_number inhoud die overeenkomt met het patroon.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- sociaal welzijn #
- sociaal welzijn #
- sociaal welzijn Nee.
- sociaal welzijnsnummer
- swn #


## <a name="norway-identification-number"></a>Noorwegen-identificatienummer

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

11 cijfers:
- zes cijfers in de indeling DDMMYY, de geboortedatum
- individueel getal met drie cijfers
- twee controlecijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_norway_id_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_norway_id_number gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_norway_id_numbe inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Persoonlijk identificatienummer
- Noors id-nummer
- Id-nummer
- Identificatie
- Persoonnummer
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>Verenigd identificatienummer voor meerdere doeleinden in de Filipijnen

### <a name="format"></a>Opmaak

12 cijfers gescheiden door afbreekstree streepjes

### <a name="pattern"></a>Patroon

12 cijfers:
- vier cijfers
- een afbreekstreester
- zeven cijfers
- een afbreekstreester
- één cijfer

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_philippines_unified_id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_philippines_id gevonden.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID
- UMID
- Identiteitskaart
- Pinag-isang Multi-Layunin-id

## <a name="poland-drivers-license-number"></a>Licentienummer van Polen

### <a name="format"></a>Opmaak

14 cijfers met twee schuine schuine streep

### <a name="pattern"></a>Patroon

14 cijfers en twee slashes vooruit:

- vijf cijfers
- een slash naar voren
- twee cijfers
- een slash naar voren
- zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_poland_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_poland_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver is s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Polen-identiteitskaart

### <a name="format"></a>Opmaak

drie letters en zes cijfers

### <a name="pattern"></a>Patroon

drie letters (niet hoofdlettergevoelig) gevolgd door zes cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_polish_national_id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_polish_national_id_passport_number gevonden.
- De checksum passeert.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. besturingssysteem.


## <a name="poland-national-id-pesel"></a>Nationale Polen-id (PESEL)

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

- zes cijfers die de geboortedatum in de notatie YYMMDD vertegenwoordigen
- vier cijfers
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_pesel_identification_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_pesel_identification_number gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_pesel_identification_number wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny-numerieke waarde
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numerieke identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>Polen paspoortnummer
Deze entiteit van het type gevoelige informatie is opgenomen in het gevoelige informatietype EU-paspoortnummer. Het is ook beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

twee letters en zeven cijfers

### <a name="pattern"></a>Patroon

Twee letters (niet hoofdlettergevoelig) gevolgd door zeven cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_polish_passport_number_v2` functie wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.
- Een trefwoord `Keywords_eu_passport_number` van of `Keyword_polish_national_passport_number` wordt gevonden.
- Er wordt een `Keywords_eu_passport_date` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_polish_passport_number_v2` functie wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.
- Een trefwoord `Keywords_eu_passport_number` van of `Keyword_polish_national_passport_number` wordt gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_polish_passport_number_v2` functie wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numerieke paszportów
- numerieke paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="poland-regon-number"></a>Polen REGON-getal
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

9-cijferig of 14-cijferig getal

### <a name="pattern"></a>Patroon

negen cijfers of 14-cijferig getal:

- negen cijfers of
- negen cijfers
- afbreekstreester
- vijf cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_polish_regon_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_polish_regon_number gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_polish_regon_number inhoud die overeenkomt met het patroon.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon-id
- statistisch getal
- statistische id
- statistisch nee
- regonnummer
- regonid #
- regonno #
- bedrijfs-id
- companyid #
- companyidno #
- numerieke statystyczny
- getal regon
- numerstatystyczny #
- numerieke waarde #


## <a name="poland-tax-identification-number"></a>Btw-nummer polen
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

11 cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

11 cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_poland_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_poland_eu_tax_file_number` trefwoord uit gevonden.


```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
- nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- btw-id #
- btw-id
- btw-nee
- btw-nummer
- vatid #
- vatid
- vatno #


## <a name="portugal-citizen-card-number"></a>Portugal burgerkaartnummer

### <a name="format"></a>Opmaak

acht cijfers

### <a name="pattern"></a>Patroon

acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_portugal_citizen_card inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_portugal_citizen_card gevonden.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- burgerkaart
- documentnummer
- documento de identificação
- id-nummer
- identificatie nee
- identificatienummer
- identiteitskaart nee
- nummer van een identiteitskaart
- nationale id-kaart
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi-getal


## <a name="portugal-drivers-license-number"></a>Portugese nummer van het rijbewijs

### <a name="format"></a>Opmaak

twee patronen: twee letters gevolgd door 5-8 cijfers met speciale tekens

### <a name="pattern"></a>Patroon

Patroon 1: Twee letters gevolgd door 5/6 met speciale tekens:
- Twee letters (niet hoofdlettergevoelig)
- Een afbreekstreester
- Vijf of zes cijfers
- Een spatie
- Eén cijfer

Patroon 2: Een letter gevolgd door 6/8 cijfers met speciale tekens:
- Eén letter (niet zaakgevoelig)
- Een afbreekstreester
- Zes of acht cijfers
- Een spatie
- Eén cijfer


### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_portugal_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_portugal_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver is s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Portugal paspoortnummer

### <a name="format"></a>Opmaak

één letter gevolgd door zes cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

één letter gevolgd door zes cijfers:

- één letter (niet case-sensitive)
- zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_portugal_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_portugal_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_portugal_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_portugal_eu_passport_number` wordt gevonden.

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- Portugees paspoort
- Portugese passeport
- Portugese passaporte
- passaporte nº
- passeport nº
- números de passaporte
- Portugese paspoorten
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="portugal-tax-identification-number"></a>Portugese belastingidentificatienummer

### <a name="format"></a>Opmaak

negen cijfers met optionele spaties

### <a name="pattern"></a>Patroon

- drie cijfers
- een optionele spatie
- drie cijfers
- een optionele spatie
- drie cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_portugal_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_portugal_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_portugal_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- nif #
- nif
- número de identificação fisca
- getal fiscaal
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Roemenië rijbewijsnummer

### <a name="format"></a>Opmaak

één teken gevolgd door acht cijfers

### <a name="pattern"></a>Patroon

één teken gevolgd door acht cijfers:
- één letter (niet case-sensitive) of cijfer
- acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_romania_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_romania_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver is s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>Roemeense persoonlijke numerieke code (CNP)
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

13 cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

- één cijfer van 1-9
- zes cijfers die de geboortedatum (YYMMDD) vertegenwoordigen
- twee cijfers, die 01-52 of 99 kunnen zijn
- vier cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_romania_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_romania_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_romania_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- cod identificare personal
- cod numeriek persoonlijk
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- verzekeringsnummer
- verzekeringsnummer #
- nationale id #
- nationale id
- nationaal identificatienummer
- număr identificare personal
- număr-identiteit
- număr personal unic
- getalăridentitate #
- getalăridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- persoonlijke numerieke code
- vastmaken #
- vastmaken
- belastingbestand nee
- btw-bestandsnummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #
- uniek identificatienummer
- uniek identiteitsnummer
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Roemenië paspoortnummer

### <a name="format"></a>Opmaak

acht of negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

acht of negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_romania_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_romania_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de indeling `Regex_romania_eu_passport_date` DD MMM/MMM YY (voorbeeld- 01 FEB/FEB 10) of wordt een trefwoord `Keywords_eu_passport_date` uit gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_romania_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_romania_eu_passport_number` wordt gevonden.

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul paşaportului numarul pasaportului numerele paşaportului Paşaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="russia-passport-number-domestic"></a>Rusland paspoortnummer binnenlands
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

10-cijferig getal

### <a name="pattern"></a>Patroon

10-cijferig getal:

- twee cijfers
- een optionele spatie of afbreekstreester
- twee cijfers
- een optionele spatie
- zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- In de regex Regex_Russian_Passport_Number_Domestic inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Russian_Passport_Number gevonden.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- paspoortnummer
- paspoort nee
- paspoort #
- paspoort-id
- passportno #
- paspoortnummer #
- паспорт нет
- паспорт-id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Rusland paspoortnummer internationaal
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

negencijferig getal

### <a name="pattern"></a>Patroon

negencijferig getal:

- twee cijfers
- een optionele spatie of afbreekstreester
- zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- In de regex Regex_Russian_Passport_Number_International inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Russian_Passport_Number gevonden.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- paspoortnummer
- paspoort nee
- paspoort #
- paspoort-id
- passportno #
- paspoortnummer #
- паспорт нет
- паспорт-id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Nationale id van Saudi-Arabië

### <a name="format"></a>Opmaak

10 cijfers

### <a name="pattern"></a>Patroon

10 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_saudi_arabia_national_id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_saudi_arabia_national_id gevonden.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identificatiekaart
- I-kaartnummer
- ID-nummer
- الوطنية الهوية بطاقة رقم


## <a name="singapore-national-registration-identity-card-nric-number"></a>NRIC-nummer (National Registration Identity Card) van Singapore

### <a name="format"></a>Opmaak

negen letters en cijfers

### <a name="pattern"></a>Patroon

- negen letters en cijfers:
- de letter "F", "G", "S" of "T" (niet zaakgevoelig)
- zeven cijfers
- een alfabetisch vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_singapore_nric inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_singapore_nric gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_singapore_nric inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- Nationale registratie-identiteitskaart
- Nummer van een identiteitskaart
- NRIC
- IC
- Buitenlands identificatienummer
- FIN
- 身份证
- 身份證

## <a name="slovakia-drivers-license-number"></a>Slowakije-rijbewijsnummer

### <a name="format"></a>Opmaak

één teken gevolgd door zeven cijfers

### <a name="pattern"></a>Patroon

één teken gevolgd door zeven cijfers

- één letter (niet case-sensitive) of cijfer
- zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_slovakia_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_slovakia_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver is s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Persoonlijk nummer slowakije
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

negen of tien cijfers met optionele backslash

### <a name="pattern"></a>Patroon

- zes cijfers die de geboortedatum vertegenwoordigen
- optionele slash (/)
- drie cijfers
- een optioneel vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_slovakia_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_slovakia_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_slovakia_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- geboortedatum
- číslo národnej identifikačnej-karty
- číslo občianského preukazu
- daňové číslo
- id-nummer
- identificatie nee
- identificatienummer
- identifikačná karta č
- identifikačné číslo
- identiteitskaart nee
- nummer van een identiteitskaart
- národná identifikačná značka č
- nationaal nummer
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- sociaal-zekerheidsnummer
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- belastingbestand nee
- btw-bestandsnummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Slowakije paspoortnummer

### <a name="format"></a>Opmaak

één cijfer of letter gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

één cijfer of letter (niet case-sensitive) gevolgd door zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_slovakia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_slovakia_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_slovakia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_slovakia_eu_passport_number` wordt gevonden.

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="slovenia-drivers-license-number"></a>Nummer van sloveens rijbewijs

### <a name="format"></a>Opmaak

negen cijfers zonder spaties en scheidingstekens

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_slovenia_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_slovenia_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver is s_license_number

- vozniško dovoljenje
- vozniška številka licentie
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Slovenië Unique Master Citizen Number
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

13 cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

13 cijfers in het opgegeven patroon:

- zeven cijfers die overeenkomen met de geboortedatum (DDMMLLL) waarbij 'LLL' overeenkomt met de laatste drie cijfers van het geboortejaar
- twee cijfers die overeenkomen met het geboortegebied "50"
- drie cijfers die overeenkomen met een combinatie van geslacht en serienummer voor personen die op dezelfde dag zijn geboren. 000-499 voor man en 500-999 voor vrouw.
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_slovenia_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_slovenia_eu_national_id_card` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_slovenia_eu_national_id_card` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id-kaart
- identificatienummer
- identifikacijska številka
- identiteitskaart
- nacionalna-id
- nacionalni potni lijst
- nationale id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- persoonlijke code
- persoonlijk nummer
- persoonlijke numerieke code
- številka državljana
- uniek burgernummer
- uniek id-nummer
- uniek identiteitsnummer
- uniek burgernummer
- uniek registratienummer
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Slovenië paspoortnummer

### <a name="format"></a>Opmaak

twee letters gevolgd door zeven cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

twee letters gevolgd door zeven cijfers:

- de letter 'P'
- één hoofdletter
- zeven cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_slovenia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_slovenia_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_eu_passport_date1` indeling DD.MM.YYYY of wordt een trefwoord `Keywords_eu_passport_date` gevonden uit

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_slovenia_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_slovenia_eu_passport_number` wordt gevonden.

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni-lijst #
- datum rojstva
- potni-lijst
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="slovenia-tax-identification-number"></a>Nummer van belastingidentificatie van Slovenië
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

acht cijfers zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

- één cijfer van 1-9
- zes cijfers
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_slovenia_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_slovenia_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_slovenia_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- belastingbestand nee
- btw-bestandsnummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>Zuid-Afrika-identificatienummer

### <a name="format"></a>Opmaak

13 cijfers die spaties kunnen bevatten

### <a name="pattern"></a>Patroon

13 cijfers:
- zes cijfers in de notatie YYMMDD, de geboortedatum
- vier cijfers
- een indicator voor een eencijferig burgerschap
- het cijfer '8' of '9'
- één cijfer, een checksum-cijfer

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_south_africa_identification_number wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_south_africa_identification_number gevonden.
- De checksum passeert.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identiteitskaart
- ID
- Identificatie

## <a name="south-korea-resident-registration-number"></a>Registratienummer voor inwoners van Zuid-Korea

### <a name="format"></a>Opmaak

13 cijfers met een afbreekstreester

### <a name="pattern"></a>Patroon

13 cijfers:
- zes cijfers in de notatie YYMMDD, de geboortedatum
- een afbreekstreester
- één cijfer dat wordt bepaald door de eeuw en het geslacht
- viercijferige regio-van-geboortecode
- een cijfer dat wordt gebruikt om onderscheid te maken tussen personen voor wie de voorgaande getallen identiek zijn
- een vinkje.

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_south_korea_resident_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_south_korea_resident_number gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_south_korea_resident_number inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Nationale id-kaart
- Burgerregistratienummer
- Jumin deungnok beonho
- RRN
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Rijbewijsnummer van Spanje

### <a name="format"></a>Opmaak

acht cijfers gevolgd door één teken

### <a name="pattern"></a>Patroon

acht cijfers, gevolgd door één teken:

- acht cijfers
- één cijfer of letter (niet case-sensitive)

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie  `Func_spain_eu_DL_and_NI_number_citizen` of zoekt inhoud die overeenkomt met het `Func_spain_eu_DL_and_NI_number_foreigner` patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_spain_eu_driver's_license_number` wordt gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie  `Func_spain_eu_DL_and_NI_number_citizen` of zoekt inhoud die overeenkomt met het `Func_spain_eu_DL_and_NI_number_foreigner` patroon.

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver is s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carnetconducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>Spanje DNI
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

acht cijfers gevolgd door één teken

### <a name="pattern"></a>Patroon

zeven cijfers gevolgd door één teken

- acht cijfers
- Een optionele spatie of afbreekstreester
- one check letter (not case-sensitive)

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie  `Func_spain_eu_DL_and_NI_number_citizen` of zoekt inhoud die overeenkomt met het `Func_spain_eu_DL_and_NI_number_foreigner` patroon.
- Er wordt een  `Keywords_spain_eu_national_id_card"` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie  `Func_spain_eu_DL_and_NI_number_citizen` of zoekt inhoud die overeenkomt met het `Func_spain_eu_DL_and_NI_number_foreigner` patroon.


```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- verzekeringsnummer
- nationaal identificatienummer
- nationale identiteit
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- persoonlijk identificatienummer
- persoonlijke identiteit nee
- uniek identiteitsnummer
- uniqueid #

## <a name="spain-passport-number"></a>Spanje paspoortnummer

### <a name="format"></a>Opmaak

een combinatie van letters en getallen met acht of negen tekens zonder spaties of scheidingstekens

### <a name="pattern"></a>Patroon

een combinatie van letters en cijfers met acht of negen tekens:

- twee cijfers of letters
- één cijfer of letter (optioneel)
- zes cijfers

### <a name="checksum"></a>Checksum

Niet van toepassing

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_spain_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_spain_eu_passport_number` wordt gevonden.
- Met de normale expressie wordt de datum gevonden in de `Regex_spain_eu_passport_date` indeling DD-MM-YYYY of wordt een trefwoord `Keywords_eu_passport_date` uit gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_spain_eu_passport_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_passport_number` van of `Keywords_spain_eu_passport_number` wordt gevonden.

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- Spanje-paspoort

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="spain-social-security-number-ssn"></a>Spanje sociaal-zekerheidsnummer (SSN)


### <a name="format"></a>Opmaak

11-12 cijfers

### <a name="pattern"></a>Patroon

11-12 cijfers:
- twee cijfers
- a forward slash (optioneel)
- zeven tot acht cijfers
- a forward slash (optioneel)
- twee cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_spanish_social_security_number inhoud die overeenkomt met het patroon.
- De checksum passeert.
- - Er wordt een  `Keywords_spain_eu_ssn_or_equivalent` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_spanish_social_security_number inhoud die overeenkomt met het patroon.
- De checksum passeert.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- sociale zekerheid nee
- sociaal-zekerheidsnummer
- número de la seguridad sociaal

## <a name="spain-tax-identification-number"></a>Btw-nummer van Spanje
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

zeven of acht cijfers en een of twee letters in het opgegeven patroon

### <a name="pattern"></a>Patroon

Spaanse natuurlijke personen met een Nationale identiteitskaart van Spanje:

- acht cijfers
- één hoofdletter (hoofdlettergevoelig)

Niet-ingezetene Spanjaarden zonder spaanse nationale identiteitskaart

- één hoofdletter 'L' (hoofdlettergevoelig)
- zeven cijfers
- één hoofdletter (hoofdlettergevoelig)

Resident Spaniards under the age of 14 years without a Spain National Identity Card:

- één hoofdletter 'K' (hoofdlettergevoelig)
- zeven cijfers
- één hoofdletter (hoofdlettergevoelig)

Buitenlanders met het identificatienummer van een buitenlander

- een hoofdletter met de naam 'X', 'Y' of 'Z' (hoofdlettergevoelig)
- zeven cijfers
- één hoofdletter (hoofdlettergevoelig)

Buitenlanders zonder het identificatienummer van een buitenlander

- één hoofdletter met de letter 'M' (hoofdlettergevoelig)
- zeven cijfers
- één hoofdletter (hoofdlettergevoelig)

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie  `Func_spain_eu_tax_file_number` of zoekt inhoud die overeenkomt met het `Func_spain_eu_DL_and_NI_number_citizen` patroon.
- Er wordt een  `Keywords_spain_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie  `Func_spain_eu_tax_file_number` of zoekt inhoud die overeenkomt met het `Func_spain_eu_DL_and_NI_number_citizen` patroon.

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- belastingbestand nee
- btw-bestandsnummer
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server verbindingsreeks

### <a name="format"></a>Opmaak

De tekenreeks 'Gebruikers-id', 'Gebruikers-id', 'uid' of 'UserId' gevolgd door de tekens en tekenreeksen die in het onderstaande patroon worden beschreven.

### <a name="pattern"></a>Patroon

- de tekenreeks 'Gebruikers-id', 'Gebruikers-id', 'uid' of 'UserId'
- een combinatie van 1-200 kleine of hoofdletters, cijfers, symbolen, speciale tekens of spaties
- de tekenreeks 'Wachtwoord' of 'pwd' waarbij 'pwd' niet wordt voorafgegaan door een kleine letter
- een gelijkteken (=)
- een teken dat geen dollarteken ($), procentsymbool (%), groter dan symbool (>), bij symbool (@), aanhalingsteken ("), puntkomma (;), linkerbrace([) of linker vierkante haak ({)
- een combinatie van 7-128 tekens die geen puntkomma zijn (;), slash (/) of aanhalingsteken (")
- een puntkomma (;) of aanhalingsteken (")

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie CEP_Regex_SQLServerConnectionString inhoud die overeenkomt met het patroon.
- Een trefwoord CEP_GlobalFilter wordt niet gevonden.
- De normale expressie CEP_PasswordPlaceHolder inhoud die overeenkomt met het patroon, wordt niet gevonden.
- In de CEP_CommonExampleKeywords wordt geen inhoud gevonden die overeenkomt met het patroon.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- voorbeeld

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

Dit type gevoelige informatie identificeert deze trefwoorden met behulp van een gewone expressie, niet een lijst met trefwoorden.

- Wachtwoord of pwd gevolgd door 0-2 spaties, een gelijkteken (=), 0-2 spaties en een sterretje (*) -OF-
- Wachtwoord of pwd gevolgd door:
    - Gelijkteken (=)
    - Minder dan symbool (<)
    - Een combinatie van 1-200 tekens die hoofdletters of kleine letters, cijfers, een sterretje (*), afbreekstreeping (-), onderstreping (_) of witruimteteken zijn
    - Groter dan symbool (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Dit type gevoelige informatie identificeert deze trefwoorden met behulp van een gewone expressie, niet een lijst met trefwoorden.

- contoso
- fabrikam
- noordenwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->netto

## <a name="sweden-drivers-license-number"></a>Rijbewijsnummer van Zweden

### <a name="format"></a>Opmaak

10 cijfers met een afbreekstreester

### <a name="pattern"></a>Patroon

10 cijfers met een afbreekstreester:

- zes cijfers
- een afbreekstreester
- vier cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de normale  `Regex_sweden_eu_driver's_license_number` expressie wordt inhoud gevonden die overeenkomt met het patroon.
- Een trefwoord  `Keywords_eu_driver's_license_number` van of `Keywords_sweden_eu_driver's_license_number` wordt gevonden.

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver is s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Zweedse nationale id

### <a name="format"></a>Opmaak

10 of 12 cijfers en een optioneel scheidingsteken

### <a name="pattern"></a>Patroon

10 of 12 cijfers en een optioneel scheidingsteken:
- twee cijfers (optioneel)
- Zes cijfers in datumnotatie YYMMDD
- scheidingsteken van "-" of "+" (optioneel)
- vier cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_swedish_national_identifier` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een `Keywords_swedish_national_identifier` trefwoord uit gevonden
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_swedish_national_identifier` functie wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id-nummer
- id #
- identificatie nee
- identificatienummer
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- identiteitsdocument
- identiteit nee
- identiteitsnummer
- id-nummer
- persoonlijke id
- personnummer #
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>Zweden paspoortnummer

### <a name="format"></a>Opmaak

acht cijfers

### <a name="pattern"></a>Patroon

acht opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- met de normale expressie Regex_sweden_passport_number inhoud die overeenkomt met het patroon.
- een trefwoord `Keywords_eu_passport_number` van of `Keyword_sweden_passport` wordt gevonden.
- met de normale expressie wordt een datum gevonden in de indeling `Regex_sweden_eu_passport_date` DD MMM/MMM YY (01 JAN/JAN 12) of wordt een trefwoord `Keywords_eu_passport_date` uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- met de normale expressie Regex_sweden_passport_number inhoud die overeenkomt met het patroon.
- een trefwoord `Keywords_eu_passport_number` van of `Keyword_sweden_passport` wordt gevonden.


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- registratiekaart voor vreemden
- g3-verwerkingskosten
- meerdere invoer
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- pass nr
- visa voor Schengen
- visa voor Schengen
- enkele vermelding
- sverige pass
- visumvereisten
- visaverwerking
- visa type

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- datum van uitgifte
- vervaldatum


## <a name="sweden-tax-identification-number"></a>Btw-nummer zweden
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

10 cijfers en een symbool in het opgegeven patroon

### <a name="pattern"></a>Patroon

10 cijfers en een symbool:

- zes cijfers die overeenkomen met de geboortedatum (YYMMDD)
- een plusteken of minteken
- drie cijfers die het identificatienummer uniek maken op de volgende plaatsen:
  - voor getallen die vóór 1990 zijn uitgegeven, wordt met het zevende en achtste cijfer het geboorteland of de in het buitenland geboren personen
  - het cijfer in de negende positie geeft geslacht aan door oneven voor mannelijke of zelfs voor vrouwelijke
- een vinkje

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_sweden_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_sweden_eu_tax_file_number` trefwoord uit gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_sweden_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- persoonlijk id-nummer
- personnummer
- skatt-idnummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- belastingbestand
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-nummer
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #


## <a name="swift-code"></a>SWIFT-code

### <a name="format"></a>Opmaak

vier letters gevolgd door 5-31 letters of cijfers

### <a name="pattern"></a>Patroon

vier letters gevolgd door 5-31 letters of cijfers:
- bankcode met vier letters (niet case-sensitive)
- een optionele spatie
- 4-28 letters of cijfers (het basisrekeningnummer (BBAN))
- een optionele spatie
- één tot drie letters of cijfers (rest van de BBAN)

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_swift inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_swift gevonden.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_swift"></a>Keyword_swift

- internationale organisatie voor normalisatie 9362
- iso 9362
- iso9362
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swiftcode
- swift number #
- swift routing number
- bic-getal
- bic-code
- bic #
- bic #
- bank-idcode
- Organisatie internationale de normalisatie 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコード
- SWIFT番号
- BIC番号
- BICコード
- SWIFT コード
- SWIFT 番号
- BIC 番号
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Zwitserland SSN AHV-nummer
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

13-cijferig getal

### <a name="pattern"></a>Patroon

13-cijferig getal:

- drie cijfers - 756
- een optionele punt
- vier cijfers
- een optionele punt
- vier cijfers
- een optionele punt
- twee cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_swiss_social_security_number_ahv wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keywords_swiss_social_security_number_ahv gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_swiss_social_security_number_ahv wordt inhoud gevonden die overeenkomt met het patroon.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- verzekeringsnummer
- personalidno #
- sociaal-zekerheidsnummer
- persoonlijk id-nummer
- persoonlijke identificatie nee.
- insuranceno #
- uniqueidno #
- unieke identificatie nee.
- avs-nummer
- persoonlijke identiteit geen versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- id voor identificatiepersoneel
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>Taiwan national identification number

### <a name="format"></a>Opmaak

één letter (in het Engels) gevolgd door negen cijfers

### <a name="pattern"></a>Patroon

een letter (in het Engels) gevolgd door negen cijfers:
- één letter (in het Engels, niet case-sensitive)
- het cijfer '1' of '2'
- acht cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_taiwanese_national_id wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_taiwanese_national_id gevonden.
- De checksum passeert.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_taiwanese_national_id wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號
- 身份證
- 身份證號碼
- 身份證號
- 身分證字號
- 身分證
- 身分證號碼
- 身份證號
- 身分證統一編號
- 國民身分證統一編號
- 簽名
- 蓋章
- 簽名或蓋章
- 簽章

## <a name="taiwan-passport-number"></a>Taiwan paspoortnummer

### <a name="format"></a>Opmaak

- biometrisch paspoortnummer: negen cijfers
- niet-biometrisch paspoortnummer: negen cijfers

### <a name="pattern"></a>Patroon
biometrisch paspoortnummer:
- het teken '3'
- acht cijfers

niet-biometrisch paspoortnummer:
- negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_taiwan_passport inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_taiwan_passport gevonden.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC-paspoortnummer
- Paspoortnummer
- Paspoort nee
- Paspoortnum
- Paspoort #
- 护照
- 中華民國護照
- Zhōnghuá Mínguó hùzhào

## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan-ingezeten certificaatnummer (ARC/TARC)

### <a name="format"></a>Opmaak

10 letters en cijfers

### <a name="pattern"></a>Patroon

10 letters en cijfers:
- twee letters (niet hoofdlettergevoelig)
- acht cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_taiwan_resident_certificate inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_taiwan_resident_certificate gevonden.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Certificaat voor ingezetene
- Resident Cert
- Resident Cert.
- Identificatiekaart
- Certificaat voor buitenaardse ingezetene
- ARC
- Taiwan Area Resident Certificate
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證

## <a name="thai-population-identification-code"></a>Thaise bevolkingsidentificatiecode

### <a name="format"></a>Opmaak

13 cijfers

### <a name="pattern"></a>Patroon

13 cijfers:
- eerste cijfer is geen nul of negen
- 12 cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_Thai_Citizen_Id wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Thai_Citizen_Id gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_Thai_Citizen_Id wordt inhoud gevonden die overeenkomt met het patroon.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- Id-nummer
- Identificatienummer
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน

## <a name="turkish-national-identification-number"></a>Turks nationaal identificatienummer

### <a name="format"></a>Opmaak

11 cijfers

### <a name="pattern"></a>Patroon

11 cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_Turkish_National_Id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Turkish_National_Id gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_Turkish_National_Id inhoud die overeenkomt met het patroon.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>VK rijbewijsnummer

### <a name="format"></a>Opmaak

Combinatie van 18 letters en cijfers in de opgegeven notatie

### <a name="pattern"></a>Patroon

18 letters en cijfers:
- Vijf letters (niet hoofdlettergevoelig) of het cijfer '9' in plaats van een letter.
- Eén cijfer.
- Vijf cijfers in de datumnotatie MMDDY voor geboortedatum. Het zevende teken wordt verhoogd met 50 als het stuurprogramma een vrouw is. voor examen, 51 tot 62 in plaats van 01 tot 12.
- Twee letters (niet hoofdlettergevoelig) of het cijfer '9' in plaats van een letter.
- Vijf cijfers.

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_uk_drivers_license` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een `Keywords_eu_driver's_license_number` trefwoord uit gevonden.
- De checksum passeert.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de `Func_uk_drivers_license` functie wordt inhoud gevonden die overeenkomt met het patroon.
- De checksum passeert.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver is s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driverlics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver'lic
- driver'lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver' lic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- driver slic
- rij-slics
- driver'slicense
- slicenses voor stuurprogramma's
- driver'slicence
- driver'slicences
- driverlic
- rij-lics
- rijbewijs
- rijbewijzen
- rijbewijs
- rijbewijzen
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driverlics #
- rijbewijs #
- rijbewijzen #
- rijbewijzen #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver'lic #
- driver'lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver' lic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- driver slic #
- rij-slics #
- driver'slicense #
- slicenses voor stuurprogramma's #
- driver'slicence #
- driver'slicences #
- driverlic #
- rij-lics #
- rijbewijs #
- rijbewijzen #
- rijbewijs #
- rijbewijzen #
- rijbewijs 
- rijbewijs
- dlno #
- driv lic
- driv-licentie
- driv-licentie
- driv-licenties
- driv-licentie
- driv-licenties
- driver licen
- drivers licen
- licentie voor stuurprogramma's
- driving lic
- rij-licentie
- rijbewijzen
- rijbewijs
- rijbewijzen
- rijbewijs
- dl no
- dlno
- dl-getal


## <a name="uk-electoral-roll-number"></a>VK kieslijstnummer

### <a name="format"></a>Opmaak

twee letters gevolgd door 1-4 cijfers

### <a name="pattern"></a>Patroon

twee letters (niet hoofdlettergevoelig) gevolgd door 1-4 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_uk_electoral inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_uk_electoral gevonden.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- raadsnominatie
- formulier voor voordracht
- kiesregister
- kieslijst


## <a name="uk-national-health-service-number"></a>VK national health service number

### <a name="format"></a>Opmaak

10-17 cijfers gescheiden door spaties

### <a name="pattern"></a>Patroon

10-17 cijfers:
- 3 of 10 cijfers
- een spatie
- drie cijfers
- een spatie
- vier cijfers

### <a name="checksum"></a>Checksum

Ja

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_uk_nhs_number inhoud die overeenkomt met het patroon.
- Een van de volgende gegevens is waar:
    - Er wordt een trefwoord Keyword_uk_nhs_number gevonden.
    - Er wordt een trefwoord Keyword_uk_nhs_number1 gevonden.
    - Er wordt een trefwoord Keyword_uk_nhs_number_dob gevonden.
- De checksum passeert.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- nationale gezondheidsdienst
- nhs
- health services authority
- gezondheidsinstantie

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patiënt-id
- patiëntenidentificatie
- patiënt nee
- patiëntnummer

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- HUISARTS
- DOB
- D.O.B
- Geboortedatum
- Geboortedatum

## <a name="uk-national-insurance-number-nino"></a>VK national insurance number (NINO)
Deze entiteit van het type gevoelige informatie maakt deel uit van het eu-nationale identificatienummer voor gevoelige informatie. Het is ook beschikbaar als een op zichzelf staand entiteit met gevoelige informatie.

### <a name="format"></a>Opmaak

zeven tekens of negen tekens gescheiden door spaties of streepjes

### <a name="pattern"></a>Patroon

twee mogelijke patronen:

- twee letters (geldige NINOs gebruiken alleen bepaalde tekens in dit voorvoegsel, dat door dit patroon wordt gevalideerd; niet hoofdlettergevoelig)
- zes cijfers
- 'A', 'B', 'C' of 'D' (net als het voorvoegsel zijn alleen bepaalde tekens toegestaan in het achtervoegsel; niet hoofd- en hoofdschruf)

OF

- twee letters
- een spatie of streepje
- twee cijfers
- een spatie of streepje
- twee cijfers
- een spatie of streepje
- twee cijfers
- een spatie of streepje
- 'A', 'B', 'C' of 'D'

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_uk_nino inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_uk_nino gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_uk_nino inhoud die overeenkomt met het patroon.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- nationaal verzekeringsnummer
- nationale verzekeringsbijdragen
- protection act
- verzekering
- sociaal-zekerheidsnummer
- verzekeringstoepassing
- medische toepassing
- sociale verzekering
- medische hulp
- sociale zekerheid
- Groot-Brittannië
- NI-nummer
- NI Nee.
- NI #
- NI #
- verzekering #
- verzekeringsnummer
- nationalinsurance #
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>VK Uniek referentienummer voor belastingbetalers
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

10 cijfers zonder spaties en scheidingstekens


### <a name="pattern"></a>Patroon

10 cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de  `Func_uk_eu_tax_file_number` functie wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een  `Keywords_uk_eu_tax_file_number` trefwoord uit gevonden.

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- btw-nummer
- belastingbestand
- belasting-id
- geen belastingidentificatie
- btw-nummer
- belasting nee #
- belasting nee
- btw-registratienummer
- getaxid #
- taxidno #
- getaxidnummer #
- taxno #
- belastingnummer #
- belastingnummer
- tin-id
- tin no
- tin #

## <a name="us-bank-account-number"></a>Amerikaans bankrekeningnummer

### <a name="format"></a>Opmaak

6-17 cijfers

### <a name="pattern"></a>Patroon

6-17 opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_usa_bank_account_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_usa_Bank_Account gevonden.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Rekeningnummer controleren
- Account controleren
- Account controleren #
- Acct-nummer controleren
- Acct controleren #
- Acct No controleren.
- Accountnummer controleren.
- Bankrekeningnummer
- Bankrekening #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bankrekening nee.
- Spaarrekeningnummer
- Spaarrekening.
- Spaarrekening #
- Acct-nummer voor spaarrekening
- Spaarrekening #
- Savings Acct No.
- Spaarrekening Nee.
- Betaalrekeningnummer
- Betaalrekening
- Betaalrekening #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Betaalrekening nee.

## <a name="us-drivers-license-number"></a>Amerikaans nummer van het rijbewijs

### <a name="format"></a>Opmaak

Is afhankelijk van de status

### <a name="pattern"></a>Patroon

is afhankelijk van de staat, bijvoorbeeld New York:
- negen cijfers die zijn opgemaakt, zoals ddd ddd ddd, komen overeen.
- negen cijfers zoals ddddddddd komen niet overeen.

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_new_york_drivers_license_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_[state_name]_drivers_license_name gevonden.
- Er wordt een trefwoord Keyword_us_drivers_license gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_new_york_drivers_license_number inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_[state_name]_drivers_license_name gevonden.
- Er wordt een trefwoord Keyword_us_drivers_license_abbreviations gevonden.
- Er wordt geen trefwoord Keyword_us_drivers_license gevonden.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL
- DLS
- CDL
- CDLS
- ID
- IDs
- DL #
- DLS #
- CDL #
- CDLS #
- ID #
- IDs #
- ID-nummer
- ID-nummers
- LIC
- LIC #

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- Driver Lic
- Driver Lics
- Rijbewijs
- Licenties voor stuurprogramma's
- DriversLic
- DriversLics
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Rijbewijs
- Licenties voor stuurprogramma's
- Driver'Lic
- Driver'Lics
- Rijbewijs
- Licenties voor stuurprogramma's
- Driver' Lic
- Driver' Lics
- Rijbewijs
- Rijbewijzen
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver's Lic
- Driver's Lics
- Rijbewijs
- Rijbewijzen
- identificatienummer
- identificatienummers
- identificatie #
- id-kaart
- id-kaarten
- identificatiekaart
- identificatiekaarten
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- Driver Lic #
- Driver Lics #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- Drivers Lic #
- Drivers Lics #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Driver'Lic #
- Driver'Lics #
- Rijbewijs #
- Licenties voor stuurprogramma's #
- Driver' Lic #
- Driver' Lics #
- Rijbewijs #
- Rijbewijzen #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Driver'sLicenses #
- Driver's Lic #
- Driver's Lics #
- Rijbewijs #
- Rijbewijzen #
- id-kaart #
- id-kaarten #
- identificatiekaart #
- identificatiekaarten #


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- staatsafbreking (bijvoorbeeld 'NY')
- staatsnaam (bijvoorbeeld 'New York')

## <a name="us-individual-taxpayer-identification-number-itin"></a>Amerikaans individueel nummer voor het identificeren van belastingbetalers (ITIN)

### <a name="format"></a>Opmaak

negen cijfers die beginnen met een '9' en een '7' of '8' bevatten als het vierde cijfer, eventueel opgemaakt met spaties of streepjes

### <a name="pattern"></a>Patroon

opgemaakt:
- het cijfer '9'
- twee cijfers
- een spatie of streepje
- een '7' of '8'
- een cijfer
- een spatie of streepje
- vier cijfers

niet-opgemaakt:
- het cijfer '9'
- twee cijfers
- een '7' of '8'
- vijf cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_formatted_itin wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_itin gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_unformatted_itin wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_itin gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de functie Func_formatted_itin of Func_unformatted_itin wordt inhoud gevonden die overeenkomt met het patroon.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_itin"></a>Keyword_itin

- belastingbetaler
- belasting-id
- belastingidentificatie
- itin
- i.t.i.n.
- ssn
- tin
- sociale zekerheid
- belastingbetaler
- itins
- getaxid
- individuele belastingplichtige


## <a name="us-social-security-number-ssn"></a>Amerikaans sociaal-zekerheidsnummer (SSN)

### <a name="format"></a>Opmaak

negen cijfers, die zich mogelijk in een opgemaakt of niet-opgemaakt patroon

> [!NOTE]
> Als een SSN vóór medio 2011 is uitgegeven, heeft een SSN een sterke opmaak waarbij bepaalde delen van het getal binnen bepaalde bereik moeten vallen om geldig te zijn (maar er is geen checksum).

### <a name="pattern"></a>Patroon

Vier functies zoeken naar SSN's in vier verschillende patronen:
- Func_ssn vindt SSN's met een sterke opmaak van vóór 2011 die zijn opgemaakt met streepjes of spaties (ddd-ddddd OR ddd ddddd)
- Func_unformatted_ssn vindt SSN's met een sterke opmaak van vóór 2011 die niet is opgemaakt als negen opeenvolgende cijfers (ddddddddd)
- Func_randomized_formatted_ssn zoekt naar SSN's na 2011 die zijn opgemaakt met streepjes of spaties (ddd-dd-dddd OF ddd dd)
- Func_randomized_unformatted_ssn wordt na 2011 SSN's gevonden die niet zijn opgemaakt als negen opeenvolgende cijfers (ddddddddd)

### <a name="checksum"></a>Checksum

Nee


### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_ssn inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_ssn gevonden.

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_unformatted_ssn wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_ssn gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- Met de Func_randomized_formatted_ssn wordt inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_ssn gevonden.

Een DLP-beleid heeft weinig vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_randomized_unformatted_ssn inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_ssn gevonden.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA-nummer
- sociaal-zekerheidsnummer
- sociale zekerheid #
- sociale zekerheid #
- sociale zekerheid nee
- Sociale zekerheid #
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID

## <a name="us--uk-passport-number"></a>V.S. / VK paspoortnummer

### <a name="format"></a>Opmaak

negen cijfers

### <a name="pattern"></a>Patroon

negen opeenvolgende cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft er veel vertrouwen in dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_usa_uk_passport inhoud die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_passport_number` van of `Keywords_uk_eu_passport_number` wordt gevonden.
- Er wordt een `Keywords_eu_passport_date` trefwoord uit gevonden

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De functie Func_usa_uk_passport inhoud die overeenkomt met het patroon.
- Een trefwoord `Keywords_eu_passport_number` van of `Keywords_uk_eu_passport_number` wordt gevonden.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- paspoort #
- paspoort #
- passportid
- paspoorten
- passportno
- paspoort nee
- paspoortnummer
- paspoortnummer
- paspoortnummers
- paspoortnummers

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- Brits paspoort
- Vk-paspoort


## <a name="ukraine-passport-domestic"></a>Oekraïne paspoort binnenlands
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

negen cijfers

### <a name="pattern"></a>Patroon

negen cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- In de regex Regex_Ukraine_Passport_Domestic inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Ukraine_Passport_Domestic gevonden.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- Oekraïne-paspoort
- paspoortnummer
- paspoort nee
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Oekraine paspoort internationaal
Dit type gevoelige informatie is alleen beschikbaar voor gebruik in:
- preventiebeleid voor gegevensverlies
- beleid voor communicatie compliance
- informatiebeheer
- recordbeheer
- Beveiliging van microsoft-cloud-apps

### <a name="format"></a>Opmaak

alfanumeriek patroon met acht tekens

### <a name="pattern"></a>Patroon

alfanumeriek patroon met acht tekens:
- twee letters of cijfers
- zes cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- In de regex Regex_Ukraine_Passport_International inhoud gevonden die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_Ukraine_Passport_International gevonden.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- Oekraïne-paspoort
- paspoortnummer
- paspoort nee
- паспорт України
- номер паспорта
