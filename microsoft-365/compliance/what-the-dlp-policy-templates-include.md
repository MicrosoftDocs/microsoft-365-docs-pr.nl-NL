---
title: Wat zijn de DLP-beleidssjablonen?
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: Meer informatie over de DLP-beleidsjablonen (Data Loss Prevention) in het Office 365 beveiligingscentrum & compliancecentrum.
ms.openlocfilehash: afcc641e6e868c1988f6b30a286c082e960d056c
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162853"
---
# <a name="what-the-dlp-policy-templates-include"></a>Wat zijn de DLP-beleidssjablonen?

Preventie van gegevensverlies (DLP) in het Beveiligings compliancecentrum bevat kant-en-klare beleidssjablonen die voldoen aan algemene nalevingsvereisten, zoals het helpen beschermen van gevoelige informatie die onderhevig is aan de Amerikaanse Health Insurance Act (HIPAA), de Amerikaanse &amp; Gramm-Leach-Bliley Act (GLBA) of de Amerikaanse Patriot Act. In dit onderwerp worden alle beleidssjablonen weergegeven, welke typen gevoelige informatie ze zoeken en wat de standaardvoorwaarden en acties zijn. Dit onderwerp bevat niet elk detail van de configuratie van elke beleidssjabloon. In plaats daarvan bevat het onderwerp voldoende informatie om te bepalen welke sjabloon het beste uitgangspunt is voor uw scenario. Vergeet niet dat u deze beleidssjablonen kunt aanpassen aan uw specifieke vereisten.
  
## <a name="australia-financial-data"></a>Financiële gegevens in Australië

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Australia Financial: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  Australië Tax File Number — Min count 1, Max count 9  <br/>  Australië Bankrekeningnummer : Min count 1, Max count 9  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Australia Financial: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  Australië Tax File Number — Min count 10, Max count any  <br/>  Australië Bankrekeningnummer: Min aantal 10, Max aantal  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Australia Health Records Act (HRIP Act)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Australië HRIP: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Australië Tax File Number — Min count 1, Max count 9  <br/>  Australië Medical Account Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Australië HRIP: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Australië Tax File Number — Min count 10, Max count any  <br/>  Australië Medical Account Number — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Pii-gegevens (Persoonlijk identificeerbare gegevens in Australië)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Australië PII: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Australië Tax File Number — Min count 1, Max count 9  <br/>  Australië Rijbewijsnummer : Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Australië PII: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Australië Tax File Number — Min count 10, Max count any  <br/>  Australia Driver's License Number — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="australia-privacy-act"></a>Australische privacywet

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Privacy in Australië: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Australië Rijbewijsnummer : Min count 1, Max count 9  <br/>  Australië Paspoortnummer : Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Privacy in Australië: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Australia Driver's License Number — Min count 10, Max count any  <br/>  Australië Paspoortnummer: Min aantal 10, Max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-financial-data"></a>Financiële gegevens van Canada

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Financiële gegevens van Canada: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Canada Bank Account Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Financiële gegevens van Canada: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Canada Bank Account Number — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Canada Health Information Act (HIA)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Canada HIA: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Passport Number — Min count 1, Max count 9  <br/>  Canada Social Insurance Number — Min count 1, Max count 9  <br/>  Canada Health Service Getal : Min count 1, Max count 9  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Canada HIA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Passport Number : Min count 10, Max count any  <br/>  Canada Social Insurance Number — Min count 10, Max count any  <br/>  Canada Health Service getal : Min aantal 10, Max aantal  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Canada Personal Health Act (PHIPA) - Ontario

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Canada PHIPA: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Passport Number — Min count 1, Max count 9  <br/>  Canada Social Insurance Number — Min count 1, Max count 9  <br/>  Canada Health Service Getal : Min count 1, Max count 9  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Canada PHIPA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Passport Number : Min count 10, Max count any  <br/>  Canada Social Insurance Number — Min count 10, Max count any  <br/>  Canada Health Service getal : Min aantal 10, Max aantal  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Canada Personal Health Information Act (PHIA) - Manitoba

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Canada PHIA: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Social Insurance Number — Min count 1, Max count 9  <br/>  Canada Health Service Getal : Min count 1, Max count 9  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Canada PHIA: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Social Insurance Number — Min count 10, Max count any  <br/>  Canada Health Service getal : Min aantal 10, Max aantal  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Canada Personal Information Protection Act (PIPA)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Canada PIPA: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Passport Number — Min count 1, Max count 9  <br/>  Canada Social Insurance Number — Min count 1, Max count 9  <br/>  Canada Health Service Getal : Min count 1, Max count 9  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Canada PIPA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Passport Number : Min count 10, Max count any  <br/>  Canada Social Insurance Number — Min count 10, Max count any  <br/>  Canada Health Service getal : Min aantal 10, Max aantal  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Canada Personal Information Protection Act (PIPEDA)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Canada PIPEDA: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Driver's License Number — Min count 1, Max count 9  <br/>  Canada Bank Account Number — Min count 1, Max count 9  <br/>  Canada Passport Number — Min count 1, Max count 9  <br/>  Canada Social Insurance Number — Min count 1, Max count 9  <br/>  Canada Health Service Getal : Min count 1, Max count 9  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Canada PIPEDA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Driver's License Number — Min count 10, Max count any  <br/>  Canada Bank Account Number — Min count 10, Max count any  <br/>  Canada Passport Number : Min count 10, Max count any  <br/>  Canada Social Insurance Number — Min count 10, Max count any  <br/>  Canada Health Service getal : Min aantal 10, Max aantal  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Persoonlijke identificeerbare gegevens (PII)-gegevens in Canada

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Canada PII: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Driver's License Number — Min count 1, Max count 9  <br/>  Canada Bank Account Number — Min count 1, Max count 9  <br/>  Canada Passport Number — Min count 1, Max count 9  <br/>  Canada Social Insurance Number — Min count 1, Max count 9  <br/>  Canada Health Service Getal : Min count 1, Max count 9  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Canada PII: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Canada Driver's License Number — Min count 10, Max count any  <br/>  Canada Bank Account Number — Min count 10, Max count any  <br/>  Canada Passport Number : Min count 10, Max count any  <br/>  Canada Social Insurance Number — Min count 10, Max count any  <br/>  Canada Health Service getal : Min aantal 10, Max aantal  <br/>  Canada Personal Health Identification Number (PHIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="france-data-protection-act"></a>France Data Protection Act

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|France DPA: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  France National ID Card (CNI) — Min count 1, Max count 9  <br/>  France Social Security Number (INSEE) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|France DPA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  France National ID Card (CNI) — Min count 10, Max count any  <br/>  France Social Security Number (INSEE) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="france-financial-data"></a>Financiële gegevens van Frankrijk

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|France Financial: Inhoud scannen die buiten de map wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Eu Debit Card Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|France Financial: Inhoud scannen die buiten de deur wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  EU-betaalkaartnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>Pii-gegevens (Persoonlijk identificeerbare gegevens in Frankrijk)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|France PII: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  France Social Security Number (INSEE) — Min count 1, Max count 9  <br/>  France Driver's License Number — Min count 1, Max count 9  <br/>  France Passport Number : Min count 1, Max count 9  <br/>  France National ID Card (CNI) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|France PII: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  France Social Security Number (INSEE) — Min count 10, Max count any  <br/>  France Driver's License Number — Min count 10, Max count any  <br/>  France Passport Number : Min count 10, Max count any  <br/>  France National ID Card (CNI) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>Algemene verordening gegevensbescherming (AVG)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Laag volume EU-gevoelige inhoud gevonden  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Eu Debit Card Number — Min count 1, Max count 9  <br/>  Eu Driver's License Number — Min count 1, Max count 9  <br/>  NATIONAAL EU-identificatienummer : Min count 1, Max count 9  <br/>  EU-paspoortnummer: Min count 1, Max count 9  <br/>  EU-SSN (Social Security Number) of Equivalent ID : Min count 1, Max count 9  <br/>  EU Tax Identification Number (TIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Incidentrapporten verzenden naar beheerder  <br/> |
|Grote hoeveelheid EU-gevoelige inhoud gevonden  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Eu Debit Card Number — Min count 1, Max count 9  <br/>  Eu Driver's License Number — Min count 1, Max count 9  <br/>  NATIONAAL EU-identificatienummer : Min count 1, Max count 9  <br/>  EU-paspoortnummer: Min count 1, Max count 9  <br/>  EU-SSN (Social Security Number) of Equivalent ID : Min count 1, Max count 9  <br/>  EU Tax Identification Number (TIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot de inhoud voor externe gebruikers beperken  <br/>  Gebruikers op de hoogte stellen met e-mail- en beleidstips  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Incidentrapporten verzenden naar beheerder  <br/> |
   
## <a name="germany-financial-data"></a>Financiële gegevens van Duitsland

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Financiële gegevens van Duitsland: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Eu Debit Card Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Financiële gegevens van Duitsland: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  EU-betaalkaartnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Pii-gegevens (Persoonlijk identificeerbare gegevens in Duitsland)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Duitsland PII: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Duits rijbewijsnummer : Min count 1, Max count 9  <br/>  Duits paspoortnummer : Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Duitsland PII: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Duits rijbewijsnummer: Min aantal 10, Max telt elke  <br/>  Duits paspoortnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="israel-financial-data"></a>Financiële gegevens van Israël

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Financiële gegevens van Israël: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Israel Bank Account Number — Min count 1, Max count 9  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Financiële gegevens van Israël: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Israel Bank Account Number — Min count 10, Max count any  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Persoonsgegevens van Israël (PII)-gegevens

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Israel PII: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Israel National ID — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Israel PII: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Israel National ID : Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Bescherming van privacy in Israël

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Privacy van Israël: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Israel National ID — Min count 1, Max count 9  <br/>  Israel Bank Account Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Privacy van Israël: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Israel National ID : Min count 10, Max count any  <br/>  Israel Bank Account Number — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="japan-financial-data"></a>Financiële gegevens van Japan

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Japan Financial: Inhoud scannen die buiten het land wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Japan Bank Account Number — Min count 1, Max count 9  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Japan Financial: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Japan Bank Account Number — Min count 10, Max count any  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Persoonlijke gegevens (PII)-gegevens (Japan Persoonlijk identificeerbare gegevens)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Japan PII: Inhoud scannen die buiten wordt gedeeld - lage telling  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Japan Resident Registration Number — Min count 1, Max count 9  <br/>  Japan Social Insurance Number (SIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Japan PII: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Japan Resident Registration Number — Min count 10, Max count any  <br/>  Japan Social Insurance Number (SIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Japan Protection of Personal Information

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Japan PPI: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Japan Resident Registration Number — Min count 1, Max count 9  <br/>  Japan Social Insurance Number (SIN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Japan PPI: Inhoud scannen die buiten het land wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Japan Resident Registration Number — Min count 10, Max count any  <br/>  Japan Social Insurance Number (SIN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>PCI Data Security Standard (PCI DSS)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|PCI DSS: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|PCI DSS: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Saudi-Arabië - Anti-Cyber Crime Law

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Saudi-Arabië ACC: Inhoud scannen die buiten de stad wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  International Banking Account Number (IBAN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Saudi-Arabië ACC: Inhoud scannen die buiten de stad wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  International Banking Account Number (IBAN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Financiële gegevens van Saudi-Arabië

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Financiële gegevens in Saudi-Arabië: Inhoud scannen die buiten de stad wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  International Banking Account Number (IBAN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Financiële gegevens in Saudi-Arabië: Inhoud scannen die buiten de stad wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  International Banking Account Number (IBAN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Persoonlijke gegevens (PII)-gegevens (Persoonlijk identificeerbare gegevens) in Saudi-Arabië

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Saudi-Arabië PII: Inhoud scannen die buiten de stad wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Saudi Arabia National ID — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Saudi-Arabië PII: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Saudi Arabia National ID : Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>VK Access to Medical Reports Act

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|VK AMRA: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Health Service Number — Min count 1, Max count 9  <br/>  VK National Insurance Number (NINO) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|VK AMRA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Health Service Number — Min count 10, Max count any  <br/>  VK National Insurance Number (NINO) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="uk-data-protection-act"></a>VK Wet gegevensbescherming

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|VK DPA: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Insurance Number (NINO) — Min count 1, Max count 9  <br/>  V.S. / VK Paspoortnummer: Min count 1, Max count 9  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|VK DPA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Insurance Number (NINO) — Min count 10, Max count any  <br/>  V.S. / VK Paspoortnummer: min aantal 10, max aantal  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="uk-financial-data"></a>VK Financiële gegevens

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|VK Financiële gegevens: Inhoud scannen die buiten de deur wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Eu Debit Card Number — Min count 1, Max count 9  <br/>  SWIFT-code :Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|VK Financiële gegevens: Inhoud scannen die buiten de deur wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  EU-betaalkaartnummer: min aantal 10, max aantal  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>VK Personal Information Online Code of Practice (PIOCP)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|VK PIOCP: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Insurance Number (NINO) — Min count 1, Max count 9  <br/>  VK National Health Service Number — Min count 1, Max count 9  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|VK PIOCP: Inhoud scannen die buiten de map wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Insurance Number (NINO) — Min count 10, Max count any  <br/>  VK National Health Service Number — Min count 10, Max count any  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>VK Persoonlijke identificeerbare gegevens (PII)-gegevens

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|VK PII: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Insurance Number (NINO) — Min count 1, Max count 9  <br/>  V.S. / VK Paspoortnummer: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|VK PII: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  VK National Insurance Number (NINO) — Min count 10, Max count any  <br/>  V.S. / VK Paspoortnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>VK Privacy- en elektronische communicatieregels

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|VK PECR: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  SWIFT-code: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|VK PECR: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  SWIFT-code: Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>V.S. Federal Trade Commission (FTC) Consumentenregels

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|V.S. FTC-regels: inhoud scannen die buiten de vs wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Amerikaans bankrekeningnummer: Min count 1, Max count 9  <br/>  ABA Routing Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|V.S. FTC-regels: inhoud scannen die buiten de vs wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Amerikaans bankrekeningnummer: min aantal 10, max aantal  <br/>  ABA Routing Number : Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-financial-data"></a>Financiële gegevens van de V.S.

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Amerikaanse financiële gegevens: inhoud scannen die buiten de vs wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Amerikaans bankrekeningnummer: Min count 1, Max count 9  <br/>  ABA Routing Number — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Amerikaanse financiële gegevens: inhoud scannen die buiten de vs wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Amerikaans bankrekeningnummer: min aantal 10, max aantal  <br/>  ABA Routing Number : Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>U.S. Gramm-Leach-Bliley Act (GLBA)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Amerikaanse GLBA: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Amerikaans bankrekeningnummer: Min count 1, Max count 9  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) — Min count 1, Max count 9  <br/>  Us Social Security Number (SSN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Amerikaanse GLBA: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Amerikaans bankrekeningnummer: min aantal 10, max aantal  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) — Min count 10, Max count any  <br/>  Us Social Security Number (SSN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>U.S. Health Insurance Act (HIPAA)

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Inhoud komt overeen met de Amerikaanse HIPAA  <br/> | Bevat een van de volgende gevoelige informatie:  <br/>  Us Social Security Number (SSN) — Min count 1, Max count any  <br/>  Nummer van DeA (Drug Enforcement Agency) — Min count 1, Max count any  <br/> **EN** <br/>  Inhoud bevat een van deze voorwaarden:  <br/>  International Classification of Diseases (ICD-9-CM) — Min count 1, Max count any  <br/>  International Classification of Diseases (ICD-10-CM) — Min count 1, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
   
## <a name="us-patriot-act"></a>Amerikaanse Patriot Act

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|U.S. Patriot Act: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Amerikaans bankrekeningnummer: Min count 1, Max count 9  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) — Min count 1, Max count 9  <br/>  Us Social Security Number (SSN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|U.S. Patriot Act: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Amerikaans bankrekeningnummer: min aantal 10, max aantal  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) — Min count 10, Max count any  <br/>  Us Social Security Number (SSN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>Pii-gegevens (Persoonlijk identificeerbare gegevens in de V.S.

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|U.S. PII: Inhoud scannen die buiten wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) — Min count 1, Max count 9  <br/>  Us Social Security Number (SSN) — Min count 1, Max count 9  <br/>  V.S. / VK Paspoortnummer: Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|U.S. PII: Inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) — Min count 10, Max count any  <br/>  Us Social Security Number (SSN) — Min count 10, Max count any  <br/>  V.S. / VK Paspoortnummer: min aantal 10, max aantal  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>Amerikaanse wetgeving voor melding van inbreuk op staatsinbreuk

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Amerikaanse staatsinbreuk: inhoud scannen die buiten de vs wordt gedeeld - laag aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: Min count 1, Max count 9  <br/>  Amerikaans bankrekeningnummer: Min count 1, Max count 9  <br/>  Amerikaans rijbewijsnummer : Min aantal 1, Max aantal 9  <br/>  Us Social Security Number (SSN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Amerikaanse staatsinbreuk: inhoud scannen die buiten de vs wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Creditcardnummer: min aantal 10, max aantal  <br/>  Amerikaans bankrekeningnummer: min aantal 10, max aantal  <br/>  Amerikaans rijbewijsnummer: min aantal 10, max aantal  <br/>  Us Social Security Number (SSN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>U.S. State Social Security Number Confidentiality Laws

|**Regelnaam**|**Voorwaarden  <br/> (inclusief typen gevoelige informatie)**|**Acties**|
|:-----|:-----|:-----|
|Amerikaanse SSN-wetten: inhoud scannen die buiten wordt gedeeld - lage telling  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Us Social Security Number (SSN) — Min count 1, Max count 9  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> |Een melding verzenden  <br/> |
|Amerikaanse SSN-wetten: inhoud scannen die buiten wordt gedeeld - hoog aantal  <br/> | Inhoud bevat gevoelige informatie:  <br/>  Us Social Security Number (SSN) — Min count 10, Max count any  <br/>  Inhoud wordt gedeeld met:  <br/>  Personen buiten mijn organisatie  <br/> | Toegang tot inhoud blokkeren  <br/>  Een melding verzenden  <br/>  Overschrijven toestaan  <br/>  Zakelijke rechtvaardiging vereisen  <br/>  Rapport over incidenten verzenden  <br/> |
   

