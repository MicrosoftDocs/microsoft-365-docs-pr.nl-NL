---
title: Beleidstips voor preventie van gegevensverlies (DLP)
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Lees hoe u een beleidstip toevoegt aan een DLP-beleid (Data Loss Prevention) om een gebruiker te laten weten dat deze werkt met inhoud die strijd is met een DLP-beleid.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903800"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Beleidstips voor preventie van gegevensverlies (DLP)

DLP-beleidstips in Outlook Web Access worden ondersteund voor alle voorwaarden, uitzonderingen en acties die van toepassing zijn op Exchange-werkbelasting in een DLP-beleid, behalve de volgende:

**Voorwaarden:**

- Afzender is
- Sender Domain Is
- Geadresseerde is lid van
- Koptekst bevat woorden of woordgroepen
- Koptekst komt overeen met patronen
- De documentgrootte is gelijk aan of groter dan
- Berichttype is
- Het belang van berichten is
- Inhoudstekenset bevat woorden
- Onderwerp of lichaam bevat woorden of woordgroepen
- Patronen voor onderwerp of lichaam
- Inhoudstekenset bevat woorden
- Inhoud wordt ontvangen van
- Heeft afzender de beleidstip overgenomen
- Berichtgrootte is gelijk aan of groter dan
- Ad-kenmerk Afzender bevat woorden of woordgroepen
- Ad-kenmerk Afzender komt overeen met patronen
- Documentinhoud bevat woorden of woordgroepen
- Documentinhoud komt overeen met patronen

**Acties:**

- Het bericht ter goedkeuring doorsturen naar de afzendermanager
- Het bericht ter goedkeuring doorsturen naar specifieke goedkeurders
- Het bericht omleiden naar specifieke gebruikers
- Geadresseerden toevoegen aan het vak Aan
- Geadresseerden toevoegen aan het cc-vak
- Geadresseerden toevoegen aan het BCC-vak
- Manager van de afzender toevoegen als geadresseerde
- HTML-vrijwaring toevoegen
- Voorbereidend e-mailonderwerp
- O365-berichtversleuteling en rechtenbescherming verwijderen

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 en hoger ondersteunt het weergeven van beleidstips voor slechts enkele voorwaarden en uitzonderingen

Momenteel ondersteunt Outlook 2013 en hoger het weergeven van beleidstips voor beleidsregels die geen voorwaarde of uitzondering bevatten, afgezien van de onderstaande voorwaarden en bijbehorende uitzonderingen:

- Inhoud bevat (werkt alleen voor gevoelige informatietypen. Gevoeligheidslabels worden niet ondersteund)
- Inhoud wordt gedeeld

Houd er rekening mee dat alle voorwaarden werken voor e-mailberichten die zijn geschreven in de Outlook-client-app, waar ze overeenkomen met inhoud en beschermende acties voor inhoud afdwingen. Het weergeven van beleidstips voor gebruikers wordt echter niet ondersteund voor voorwaarden die behalve de hierboven genoemde voorwaarden worden gebruikt.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Ondersteuning voor Outlook 2013 en hoger en Office-apps op bureaublad met beleidstips voor slechts enkele typen gevoelige informatie

De lijst met out-of-the-box gevoelige informatietypen die worden gedetecteerd voor het weergeven van DLP-beleidstips in Outlook op bureaublad (2013 en hoger) en Office-apps (Word, Excel, PowerPoint) op bureaublad zijn de volgende:

- ABA-routeringsnummer
- Argentina National Identity (DNI) Number
- Australië Bankrekeningnummer
- Australië Medical Account Number
- Australië Paspoortnummer
- Australië Belastingbestandsnummer
- Azure DocumentDB Auth Key  
- Azure IAAS Database Connection String en Azure SQL Connection String  
- Azure IoT-verbindingsreeks  
- Azure Publish Setting Password  
- Verbindingsreeks Azure Redis Cache  
- Azure SAS  
- Azure Service Bus Connection String  
- Azure Storage Account Key  
- Azure Storage Account Key (Generic)  
- Nationaal nummer belgië
- Brazilië CPF-nummer
- Brazil Legal Entity Number (CNPJ)
- Nationale id-kaart brazilië (RG)
- Canada Bankrekeningnummer
- Canada Driver's License Number
- Canada Health Service Number
- Canada Passport Number
- Canada Personal Health Identification Number (PHIN)
- Canada Social Insurance Number
- Chili-identiteitskaartnummer
- China Resident Identity Card (PRC) Number
- Creditcardnummer
- Kroatië-identiteitskaartnummer  
- OIB-nummer (Croatia Personal Identification)  
- Tsjechische persoonlijke identiteitsnummer  
- Denemarken Personal Identification Number
- Nummer van Het Bureau voor drugshandhaving (DEA)
- EU-betaalkaartnummer
- Eu-rijbewijsnummer  
- NATIONAAL EU-identificatienummer  
- EU-paspoortnummer  
- EU-SSN -nummer (Social Security Number) of equivalente id  
- EU-belastingidentificatienummer (TIN)  
- Nationale finland-id
- Finland Passport Number
- France Driver's License Number
- France National ID Card (CNI)
- Frankrijk Paspoortnummer
- France Social Security Number (INSEE)
- Duits rijbewijsnummer
- Duits paspoortnummer
- Duitsland-identiteitskaartnummer
- Nationale griekenland-id-kaart  
- Hong Kong Identity Card (HKID) Number
- India Permanent Account Number (PAN)
- India Unique Identification (Aadhaar) Number
- KTP-nummer (Indonesia Identity Card)
- IBAN (International Banking Account Number)
- Internationale classificatie van ziektes (ICD-10-CM)  
- Internationale classificatie van ziektes (ICD-9-CM)  
- IP Address
- Ierland Personal Public Service (PPS)-nummer 
- Israel Bank Account Number
- Nationale israël-id
- Rijbewijsnummer van Italië
- Japan Bank Account Number
- Japan Driver's License Number
- Japan Passport Number
- Japan Resident Registration Number
- Japan Social Insurance Number (SIN)
- Japans nummer van een verblijfskaart
- Maleisische identiteitskaartnummer
- BSN-nummer (Netherlands Citizen's Service)  
- Nieuw-Zeelands ministerie van Gezondheid Nummer
- Noorwegen-identiteitsnummer  
- Philippines Unified Multi-Purpose ID Number
- Polen-identiteitskaart
- Nationale Polen-id (PESEL)
- Polen-paspoort
- Portugal Burgerkaartnummer
- Nationale id van Saudi-Arabië
- NRIC-nummer (National Registration Identity Card) van Singapore
- Zuid-Afrika-identificatienummer  
- Registratienummer voor inwoners van Zuid-Korea
- Spain Social Security Number (SSN)
- SQL Server-verbindingsreeks  
- Nationale id Zweden
- Zweden Paspoortnummer
- SWIFT-code
- Nationale taiwan-id
- Taiwan Passport Number
- Taiwan Resident Certificate (ARC/TARC)
- Thaise bevolkingsidentificatiecode
- Turks nationaal identificatienummer
- VK Rijbewijsnummer
- VK Kieslijstnummer
- VK National Health Service Number
- VK National Insurance Number (NINO)
- V.S. / VK Paspoortnummer
- Amerikaans bankrekeningnummer
- Amerikaans rijbewijsnummer
- U.S. Individual Taxpayer Identification Number (ITIN)
- U.S. Social Security Number (SSN)

Houd er rekening mee dat aangepaste gevoelige informatietypen ook worden ondersteund voor DLP-beleidstips, naast de bovenstaande kant-en-kijkgevoelige informatietypen.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>Preventie van gegevensverlies op eindpuntapparaten ondersteunt beleidstips voor alleen bepaalde typen gevoelige informatie

De lijst met kant-en-weer gevoelige informatietypen die worden gedetecteerd in documenten die zich op eindpuntapparaten bewonen, zijn de volgende:

- ABA-routeringsnummer 
- Argentina National Identity (DNI) Number 
- Australië Bankrekeningnummer 
- Australië Medical Account Number 
- Australië Paspoortnummer 
- Australië Belastingbestandsnummer 
- Australisch bedrijfsnummer 
- Australisch bedrijfsnummer 
- Oostenrijks rijbewijsnummer 
- Oostenrijk-identiteitskaart 
- Oostenrijks paspoortnummer 
- Oostenrijks sociaal-zekerheidsnummer 
- Oostenrijks btw-nummer 
- Oostenrijks btw-nummer 
- Azure DocumentDB Auth Key 
- Azure IAAS Database Connection String en Azure SQL Connection String 
- Azure IoT-verbindingsreeks 
- Azure Publish Setting Password 
- Verbindingsreeks Azure Redis Cache 
- Azure SAS 
- Azure Service Bus Connection String 
- Azure Storage Account Key 
- Azure Storage Account Key (Generic) 
- Nummer van het Rijbewijs van België 
- Nationaal nummer belgië 
- België Paspoortnummer 
- België Btw-nummer 
- Brazilië CPF-nummer 
- Brazil Legal Entity Number (CNPJ) 
- Nationale id-kaart brazilië (RG) 
- Bulgarije Rijbewijsnummer 
- Bulgarije Paspoortnummer 
- Bulgarije Uniform Burgernummer 
- Canada Bankrekeningnummer 
- Canada Driver's License Number 
- Canada Health Service Number 
- Canada Passport Number 
- Canada Personal Health Identification Number (PHIN) 
- Canada Social Insurance Number 
- Chili-identiteitskaartnummer 
- China Resident Identity Card (PRC) Number 
- Creditcardnummer 
- Kroatische nummer van het rijbewijs 
- Kroatië-identiteitskaartnummer 
- Kroatië National ID Card Number 
- Kroatië Paspoortnummer 
- OIB-nummer (Croatia Personal Identification) 
- CSCAN-AZURE0060 Azure Storage Account Shared Access Signature 
- CSCAN-GENERAL0140 General Symmetric Key 
- Cyprus Driver's License Number 
- Cyprus-identiteitskaart 
- Cyprus Passport Number 
- Cyprus Tax Identification Number 
- Tsjechisch rijbewijsnummer 
- Tsjechische persoonlijke identiteitsnummer 
- Tsjechische Republiek Paspoortnummer 
- Rijbewijsnummer van Denemarken 
- Denemarken Paspoortnummer 
- Denemarken Personal Identification Number 
- Nummer van Het Bureau voor drugshandhaving (DEA) 
- Estlands rijbewijsnummer 
- Estlands paspoortnummer 
- Estlandse persoonlijke identificatiecode 
- EU-betaalkaartnummer 
- Eu-rijbewijsnummer 
- NATIONAAL EU-identificatienummer 
- EU-paspoortnummer 
- EU-SSN -nummer (Social Security Number) of equivalente id 
- EU-belastingidentificatienummer (TIN) 
- Finland Driver's License Number 
- Finland European Health Insurance Number 
- Nationale finland-id 
- Finland Passport Number 
- France Driver's License Number 
- France Health Insurance Number 
- France National ID Card (CNI) 
- Frankrijk Paspoortnummer 
- France Social Security Number (INSEE) 
- France Tax Identification Number (numéro SPI.) 
- Frankrijk Btw-nummer 
- Duits rijbewijsnummer 
- Duits paspoortnummer 
- Duitsland-identiteitskaartnummer 
- Duitsland Tax Identification Number 
- Duitsland Btw-nummer 
- Griekenland Rijbewijsnummer 
- Nationale griekenland-id-kaart 
- Griekenland Paspoortnummer 
- Griekenland-nummer voor sociale zekerheid (AMKA) 
- Griekse btw-identificatienummer 
- Hong Kong Identity Card (HKID) Number 
- Hongaars sociaal-zekerheidsnummer (TAJ) 
- Hongaars btw-nummer 
- Licentienummer van Hongarije 
- Hongarije Paspoortnummer 
- Hongarije Personal Identification Number 
- Btw-nummer van Hongarije 
- India Permanent Account Number (PAN) 
- India Unique Identification (Aadhaar) Number 
- KTP-nummer (Indonesia Identity Card) 
- IBAN (International Banking Account Number) 
- Internationale classificatie van ziektes (ICD-10-CM) 
- Internationale classificatie van ziektes (ICD-9-CM) 
- IP Address 
- Ireland Driver's License Number 
- Ierland Paspoortnummer 
- Ierland Personal Public Service (PPS)-nummer 
- Israel Bank Account Number 
- Nationale israël-id 
- Rijbewijsnummer van Italië 
- Italiaanse fiscale code 
- Italië Paspoortnummer 
- #A0 #A0 #A0 #A0 #A0 #A 
- Japan Bank Account Number 
- Japan Driver's License Number 
- Japan Passport Number 
- Japan Resident Registration Number 
- Japan Social Insurance Number (SIN) 
- Japans My Number Corporate 
- Japans Mijn nummer Persoonlijk 
- Japans nummer van een verblijfskaart 
- Letlandse rijbewijsnummer 
- Letland Paspoortnummer 
- Persoonlijke code letland 
- Litouws rijbewijsnummer 
- Litouws paspoortnummer 
- Persoonlijke code litouwen 
- Luxemburgs rijbewijsnummer 
- Luxemburg National Identification Number (Natuurlijke personen) 
- Luxemburg National Identification Number (Niet-natuurlijke personen) 
- Luxemburg Paspoortnummer 
- Maleisische identiteitskaartnummer 
- Malta Driver's License Number 
- Malta-identiteitskaartnummer 
- Malta Passport Number 
- Malta Tax ID-nummer 
- BSN-nummer (Netherlands Citizen's Service) 
- Nederlands rijbewijsnummer 
- Nederlands paspoortnummer 
- Btw-nummer van Nederland 
- Btw-nummer voor Nederland 
- Nieuw-Zeelands bankrekeningnummer 
- Nieuw-Zeelandse rijbewijsnummer 
- Nieuw-Zeelandse belastingdienst 
- Nieuw-Zeelands ministerie van Gezondheid Nummer 
- Nieuw-Zeelandse sociale voorzieningennummer 
- Noorwegen-identiteitsnummer 
- Philippines Unified Multi-Purpose ID Number 
- Polen Rijbewijsnummer 
- Polen-identiteitskaart 
- Nationale Polen-id (PESEL) 
- Polen-paspoort 
- Polen Tax Identification Number 
- Pools REGON-nummer 
- Portugal Burgerkaartnummer 
- Portugal Rijbewijsnummer 
- Portugal Passport Number 
- Portugal Tax Identification Number 
- Roemenië Rijbewijsnummer 
- Roemenië Paspoortnummer 
- Roemeense persoonlijke numerieke code (CNP) 
- Russisch paspoortnummer (binnenlands) 
- Russisch paspoortnummer (internationaal) 
- Nationale id van Saudi-Arabië 
- NRIC-nummer (National Registration Identity Card) van Singapore 
- Slowakije Rijbewijsnummer 
- Slowakije Paspoortnummer 
- Slowakije Persoonlijk Nummer 
- Sloveens rijbewijsnummer 
- Slovenië Paspoortnummer 
- Slovenië Tax Identification Number 
- Slovenië Unique Master Citizen Number 
- Zuid-Afrika-identificatienummer 
- Registratienummer voor inwoners van Zuid-Korea 
- Spanje DNI 
- Rijbewijsnummer van Spanje 
- Spanje Paspoortnummer 
- Spain Social Security Number (SSN) 
- Spanje Tax Identification Number 
- SQL Server-verbindingsreeks 
- Zweden Rijbewijsnummer 
- Nationale id Zweden 
- Zweden Paspoortnummer 
- Zweden Tax Identification Number 
- SWIFT-code 
- Zwitserse socialezekerheidsnummer AHV 
- Nationale taiwan-id 
- Taiwan Passport Number 
- Taiwan Resident Certificate (ARC/TARC) 
- Thaise bevolkingsidentificatiecode 
- Turks nationaal identificatienummer 
- VK Rijbewijsnummer 
- VK Kieslijstnummer 
- VK National Health Service Number 
- VK National Insurance Number (NINO) 
- VK Uniek referentienummer voor belastingbetalers 
- V.S. / VK Paspoortnummer 
- Amerikaans bankrekeningnummer 
- Amerikaans rijbewijsnummer 
- U.S. Individual Taxpayer Identification Number (ITIN) 
- U.S. Social Security Number (SSN) 
- Oekraine Paspoortnummer (binnenlands) 
- Oekraine Paspoortnummer (internationaal) 
 
Houd er rekening mee dat aangepaste gevoelige informatietypen ook worden gedetecteerd naast de bovenstaande kant-en-zeker gevoelige informatietypen

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Ondersteuningsmatrix voor DLP-beleidstips in Microsoft-apps

|**App en platform**|**Ondersteuning voor DLP-beleidstips**|**Ondersteunde typen gevoelige informatie**|**Ondersteunde predicaten en acties**|**Opmerkingen**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alles|Subset|Zie [Tips voor beleidstips voor preventie van gegevensverlies](#data-loss-prevention-policy-tips-reference)|
|**Outlook Win32 (Outlook 2013 en hoger)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Subset|Zie Ondersteuning voor [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) en hoger met beleidstips voor slechts enkele voorwaarden en uitzonderingen en Ondersteuning voor [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) en hoger en Office-apps op bureaublad, met beleidstips voor slechts enkele typen gevoelige informatie voor meer informatie over ondersteuning voor gevoelige informatietypen en DLP-voorwaarden en -acties die worden ondersteund voor het weergeven van DLP-beleidstips in Outlook Win32.|
|**Outlook Mobile (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Geen|Geen|DLP-beleidstips worden niet ondersteund in Outlook Mobile|
|**Sharepoint Online/One Drive for Business Web Client**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alles|Alle SPO/ODB-predicaten en acties in DLP||
|**Win32/ One Drive for Business Win32-client van Sharepoint**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Geen|Geen|DLP-beleidstips worden niet ondersteund in sharepoint- of OneDrive-bureaubladclient-apps|
|**Word, Excel, PowerPoint Web Client**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alles|Alle SPO/ODB-predicaten en acties in DLP|DLP-beleidstip wordt ondersteund als het document wordt gehost in de SPO- of ODB-web-app en het DLP-beleid al is gestempeld.|
|**Word, Excel, PowerPoint Mobile Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Geen|Geen|DLP-beleidstips worden niet ondersteund in mobiele apps voor Office.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alles|Alle Teams-predicaten in DLP-beleid|Beleidstips worden weergegeven wanneer een bericht wordt gemarkeerd als 'Dit bericht is gemarkeerd. Wat kan ik doen? Wanneer u op de koppeling klikt, kan de gebruiker de gevoelige informatietypen controleren die zijn gedetecteerd en een probleem kunnen overschrijven of rapporteren indien toegestaan door de beheerder. Houd er rekening mee dat er geen beleidstips worden weergegeven voor bestanden. Wanneer de geadresseerde toegang probeert te krijgen tot het document, krijgen ze mogelijk toegang geweigerd als dit niet is toegestaan.|
|**Win32 Endpoint-apparaten**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Alle endpoint DLP-predicaten en acties in DLP-beleid|Zie [Preventie van gegevensverlies op Eindpunt ondersteunt beleidstips voor alleen bepaalde typen gevoelige informatie](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Mac-apparaten**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Geen|Geen|Beleid voor preventie van gegevensverlies kan momenteel niet worden afgedwongen op Mac-apparaten|
|**Cloud-apps van derden**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Geen|Geen|Tips voor preventie van gegevensverlies worden niet ondersteund in cloud-apps van derden|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Geen|Geen||
|**Word, Excel, PowerPoint Win32-client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subset|Subset|Zie [Ondersteuning voor Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) en hoger en Office-apps op bureaublad met beleidstips voor alleen bepaalde typen gevoelige informatie voor de lijst met ondersteunde typen gevoelige informatie</br></br>Beleidstips voor WXP-client-apps werken voor documenten die zijn opgeslagen op Sharepoint Online of One Drive for Business Sites voor alle DLP-beleidsregels die precies de onderstaande of een subset met voorwaarden of acties in het DLP-beleid bevatten:</br> <ul><li>Inhoud bevat gevoelige informatietypen</li><li>Access-bereik (Inhoud wordt intern/extern gedeeld)</li><li>Gebruiker op de hoogte stellen (beleidstips/gebruikersmeldingen)</li><li>Iedereen blokkeren</li><li>Incidentenrapporten</li></ul></br> Als er een andere voorwaarde of actie aanwezig is, wordt de DLP-beleidstip voor dat beleid niet weergegeven in de bureaublad-apps van Word, Excel of PowerPoint.</br>Zie [Beleidstips in Excel, PowerPoint en Word voor](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) meer informatie|
||||||
