---
title: Basic Mobility en Security instellen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Stel Basismobiliteit en beveiliging in om de mobiele apparaten van uw gebruikers te beveiligen en te beheren door acties uit te voeren, zoals een apparaat op afstand wissen.
ms.openlocfilehash: 830baa79838818501101c0c4f2d3163f57d47611
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593415"
---
# <a name="set-up-basic-mobility-and-security"></a>Basic Mobility en Security instellen

Met de ingebouwde basismobiliteit en beveiliging voor Microsoft 365 kunt u mobiele apparaten van gebruikers beveiligen en beheren, zoals iPhones, iPads, Androids en Windows telefoons. U kunt beleidsregels voor apparaatbeveiliging maken en beheren, een apparaat op afstand wissen en gedetailleerde apparaatrapporten bekijken.

Hebt u vragen? Zie Veelgestelde vragen (Veelgestelde vragen over basismobiliteit en beveiliging) voor veelgestelde vragen om veelgestelde vragen [te beantwoorden.](frequently-asked-questions.md) U kunt geen gedelegeerd beheerdersaccount gebruiken om basismobiliteit en beveiliging te beheren. Zie Partners: Gedelegeerd beheer [aanbieden voor meer informatie.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

Apparaatbeheer maakt deel uit van het Beveiligings- & compliancecentrum, dus u moet daar naartoe gaan om basisinstellingen voor mobiliteit en beveiliging te starten.

## <a name="activate-the-basic-mobility-and-security-service"></a>De basisservice voor mobiliteit en beveiliging activeren

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.

2. Ga naar [Basismobiliteit en beveiliging activeren.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Het kan enige tijd duren om Basismobiliteit en Beveiliging te activeren. Wanneer het einde is bereikt, ontvangt u een e-mailbericht waarin de volgende stappen worden uitgelegd.

## <a name="set-up-mobile-device-management"></a>Mobile Device Management instellen

Wanneer de service gereed is, moet u de volgende stappen voltooien om de installatie te voltooien.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Stap 1: (Vereist) Domeinen configureren voor basismobiliteit en beveiliging

Als u geen aangepast domein hebt dat is gekoppeld aan Microsoft 365 of als u geen apparaten Windows beheren, kunt u deze sectie overslaan. Anders moet u DNS-records toevoegen voor het domein bij uw DNS-host. Als u de records al hebt toegevoegd, als onderdeel van het instellen van uw domein met Microsoft 365, bent u klaar. Nadat u de records hebt toevoegen, worden Microsoft 365 gebruikers in uw organisatie die zich aanmelden op hun Windows-apparaat met een e-mailadres dat uw aangepaste domein gebruikt, omgeleid om u aan te melden bij Basismobiliteit en Beveiliging.

Hulp nodig bij het instellen van de records? Zoek uw domeinregistrar en selecteer de naam van de registrar om naar stapsgewijs help te gaan voor het maken van DNS-record in de lijst in [DNS-records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)toevoegen om uw domein te verbinden. Gebruik deze instructies om CNAME-records te maken die worden beschreven in [Vereenvoudigen Windows registratie zonder Azure AD-Premium.](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

Nadat u de twee CNAME-records hebt toevoegen, gaat u terug naar het Beveiligings- & Compliancecentrum en gaat u naar **Preventie** van gegevensverlies Apparaatbeheer om de volgende stap  >     te voltooien.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Stap 2: (Vereist) Een APN-certificaat configureren voor iOS-apparaten

Als u iOS-apparaten zoals iPad en iPhones wilt beheren, moet u een APN-certificaat maken.

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.

2. In uw browsertype:  [https://protection.office.com](https://protection.office.com/) .

3. Selecteer  **Preventie van gegevensverlies**   >  **Apparaatbeheer** en kies **APN's-certificaat voor iOS-apparaten.**

4. Kies op de pagina Apple Push Notification Certificate Instellingen de optie **Volgende**.

5. Selecteer **Uw MVO-bestand downloaden** en sla de aanvraag voor het ondertekenen van certificaten op ergens op uw computer op die u zult   onthouden. Selecteer **Volgende**.

6. Op de pagina Een APN-certificaat maken:

   - Selecteer Apple APNS Portal om de Apple Push Certificates Portal te openen.
   - Meld u aan met een Apple ID.

     > [!IMPORTANT]
     > Gebruik een Apple-id van het bedrijf die is gekoppeld aan een e-mailaccount dat bij uw organisatie blijft, zelfs als de gebruiker die het account beheert, weggaat. Sla deze id op omdat u dezelfde id moet gebruiken wanneer het tijd is om het certificaat te verlengen.

   - Selecteer Een certificaat maken en accepteer de gebruiksvoorwaarden.
   - Blader naar het certificaat ondertekeningsverzoek dat u hebt gedownload naar uw computer Microsoft 365 selecteerUpload.
   - Download het APN-certificaat dat is gemaakt door de Apple Push Certificate Portal naar uw computer.

     > [!TIP]
     > Als u problemen hebt met het downloaden van het certificaat, vernieuwt u de browser.

7. Ga terug naar Microsoft 365 en selecteer **Volgende.**

8. Blader naar het APN-certificaat dat u hebt gedownload van de Apple Push Certificates Portal.

9. Selecteer  **Voltooien**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Stap 3: (Aanbevolen) Meervoudige verificatie instellen

Met MFA kunt u de aanmelding bij Microsoft 365 voor registratie van mobiele apparaten beveiligen door een tweede vorm van verificatie te vereisen. Gebruikers moeten een telefoongesprek, sms-bericht of app-melding op hun mobiele apparaat bevestigen nadat ze hun wachtwoord voor hun werkaccount correct hebben ingesteld. Ze kunnen hun apparaat pas registreren nadat deze tweede vorm van verificatie is voltooid. Nadat gebruikersapparaten zijn geregistreerd voor Basismobiliteit en Beveiliging, hebben gebruikers toegang tot Microsoft 365 resources met alleen hun werkaccount.

Zie Meervoudige verificatie instellen voor meer informatie over het inschakelen van MFA in de Azure [AD-portal.](../security-and-compliance/set-up-multi-factor-authentication.md)

Nadat u MFA hebt ingesteld, gaat u terug naar het Beveiligings- & Compliancecentrum en gaat u naar **Preventie** van gegevensverlies Apparaatbeheer Apparaatbeleid om de volgende stap   >     >  ****   te voltooien.

### <a name="step-4-recommended-manage-device-security-policies"></a>Stap 4: (Aanbevolen) Beveiligingsbeleid voor apparaten beheren

De volgende stap is het maken en implementeren van beveiligingsbeleid voor apparaten om uw organisatiegegevens Microsoft 365 beschermen. U kunt bijvoorbeeld gegevensverlies helpen voorkomen als een gebruiker zijn apparaat kwijt raakt door een beleid te maken om apparaten na vijf minuten inactiviteit te vergrendelen en apparaten te wissen na drie aanmeldingsfouten.

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.

2. Selecteer [Mobiel apparaatbeheer activeren.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Als de service is geactiveerd, ziet u in plaats daarvan de activeringsstappen een koppeling naar [Apparaten beheren.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Ga naar **Apparaatbeleid.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Beleidsinstellingen voor basisbeveiliging en mobiliteit":::

4. Maak en implementeer apparaatbeveiligingsbeleid dat geschikt is voor uw organisatie volgens de stappen in [Apparaatbeveiligingsbeleid maken in Basismobiliteit en Beveiliging.](create-device-security-policies.md)

> [!TIP]
>
> - Wanneer u een nieuw beleid maakt, kunt u het beleid zo instellen dat toegangs- en rapportbeleidsovertreding wordt toegestaan wanneer een gebruikersapparaat niet voldoet aan het beleid. Op deze manier kunt u zien hoeveel mobiele apparaten worden beïnvloed door het beleid zonder de toegang tot Microsoft 365.
>
> - Voordat u een nieuw beleid implementeert voor iedereen in uw organisatie, raden we u aan dit te testen op de apparaten die door een klein aantal gebruikers worden gebruikt.
>
> - Voordat u beleid implementeert, laat uw organisatie ook weten wat de mogelijke gevolgen zijn van het registreren van een apparaat in Basismobiliteit en Beveiliging. Afhankelijk van de manier waarop u het beleid in stelt, kunnen apparaten die niet voldoen aan beleidsregels (niet-compatibele apparaten) worden geblokkeerd voor toegang tot Microsoft 365. Niet-compatibele apparaten kunnen ook apps, foto's en andere persoonlijke gegevens bevatten die op een geregistreerd apparaat kunnen worden verwijderd als het apparaat wordt gewist. Zie Een mobiel apparaat [wissen in Basismobiliteit en Beveiliging voor meer informatie.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Zorg ervoor dat gebruikers hun apparaten registreren

Nadat u een beleid voor beheer van mobiele apparaten hebt gemaakt en geïmplementeerd, ontvangt elke gebruiker met een licentie Microsoft 365 uw organisatie die het apparaatbeleid van toepassing is, een inschrijvingsbericht wanneer deze zich de volgende keer bij Microsoft 365 aanmeldt vanaf hun mobiele apparaat. Ze moeten de registratie- en activeringsstappen voltooien voordat ze toegang hebben tot Microsoft 365 e-mail en documenten. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Als de voorkeurstaal van een gebruiker niet wordt ondersteund door het registratieproces, ontvangen gebruikers mogelijk een aanmeldingsmelding en stappen op hun mobiele apparaten in een andere taal. Niet alle talen die worden ondersteund in Microsoft 365 worden momenteel ondersteund voor het registratieproces op mobiele apparaten.

Gebruikers met Android- of iOS-apparaten moeten de app Bedrijfsportal installeren als onderdeel van het registratieproces.

## <a name="related-content"></a>Verwante inhoud

[Mogelijkheden van basismobiliteit en beveiliging](capabilities.md) (artikel)

[Apparaatbeveiligingsbeleid maken in Basismobiliteit en Beveiliging](create-device-security-policies.md) (artikel)