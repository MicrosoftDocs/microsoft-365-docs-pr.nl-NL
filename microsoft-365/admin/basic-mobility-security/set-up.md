---
title: Eenvoudige mobiliteit en beveiliging instellen
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
description: Configureer basis mobiliteit en beveiliging om de mobiele apparaten van uw gebruikers te beschermen en beheren.
ms.openlocfilehash: cb010668d95e51edfbc913caa308ddd830d674e2
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430130"
---
# <a name="set-up-basic-mobility-and-security"></a>Eenvoudige mobiliteit en beveiliging instellen

Met de ingebouwde basis mobiliteit en beveiliging voor Microsoft 365 kunt u mobiele apparaten zoals iPhones, iPads, Android-telefoons en Windows Phones beschermen en beheren. U kunt beveiligingsbeleid voor apparaten maken en beheren, een apparaat op afstand wissen en gedetailleerde apparaatprofielen weergeven.

Hebt u vragen? Zie [Veelgestelde vragen over mobiliteit en beveiliging](frequently-asked-questions.md)voor informatie over veelgestelde vragen over het oplossen van veelvoorkomende vragen. U kunt geen gedelegeerde beheerdersaccount gebruiken om eenvoudige mobiliteit en beveiliging te beheren. Zie voor meer informatie [partners: gedelegeerd beheer bieden](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

Apparaatbeheer maakt deel uit van de beveiligings & nalevings centrum, zodat u dit moet doen om MDM-configuratie te starten.

## <a name="activate-the-basic-mobility-and-security-service"></a>De basis-service voor mobiliteit en beveiliging activeren

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.
    

2. Ga naar [basis mobiliteit en beveiliging activeren](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).
    
    Het kan enige tijd duren voor het activeren van basis mobiliteit en beveiliging. Wanneer u klaar bent, ontvangt u een e-mailbericht waarin de volgende stappen worden beschreven.

## <a name="set-up-mobile-device-management"></a>Mobile Device Management instellen

Wanneer de service klaar is, voert u de volgende stappen uit om de installatie te voltooien.

### <a name="step-1-required-configure-domains-for-mdm"></a>Stap 1: (vereist) domeinen voor MDM configureren

Als u geen aangepast domein hebt dat is gekoppeld aan Microsoft 365 of als u geen Windows-apparaten beheert, kunt u dit gedeelte overslaan. Anders moet u DNS-records voor het domein toevoegen aan uw DNS-host. Als u de records al hebt toegevoegd en u uw domein hebt ingesteld met Microsoft 365, bent u er helemaal klaar voor. Wanneer u de records hebt toegevoegd, worden Microsoft 365-gebruikers in uw organisatie die zich aanmelden op hun Windows-apparaat, met een e-mailadres dat gebruikmaakt van uw aangepaste domein, omgeleid om de schrijffunctie te registreren voor eenvoudige mobiliteit en beveiliging.

Hulp nodig bij het instellen van de records? Zoek uw domeinregistratie functie en selecteer de naam van de bewaarder voor stapsgewijze instructies voor het maken van een DNS-record in de lijst die wordt weergegeven in [DNS-records toevoegen om uw domein te verbinden](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Gebruik deze instructies voor het maken van CNAME-records die worden beschreven in de [Windows-registratie vereenvoudigen zonder Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Nadat u de twee CNAME-records hebt toegevoegd, gaat u terug naar de beveiligings & nalevings **Data loss prevention**centrum en gaat u verder met  >  **Apparaatbeheer**   voorkomen dat u de volgende stap uitvoert.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Stap 2: (vereist) een APNs-certificaat voor iOS-apparaten configureren

Als u iOS-apparaten zoals iPad en iPhones wilt beheren, moet u een APNs-certificaat maken.

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.   

2. In uw browsertype:  [https://protection.office.com](https://protection.office.com/) .  

3. Selecteer **preventie van gegevensverlies**   > in **Apparaatbeheer**en kies **APNs-certificaat voor IOS-apparaten**.   

4. Kies **volgende**op de pagina Apple Push Notification Certificate Settings.  

5. Selecteer **Download Your CSR file**   en sla de aanvraag voor certificaatondertekening op uw computer op een locatie op die u kunt onthouden. Selecteer **volgende**.
    
6. Op de pagina Create a APNs Certificate:
    
    - Selecteer Apple APNS-Portal om de Apple Push Certificate-portal te openen.
    - Meld u aan met een Apple-ID.

    >[!IMPORTANT]
    >Gebruik een netwerkapple-ID die is gekoppeld aan een e-mailaccount dat bij uw organisatie hoort, zelfs als de gebruiker die het account beheert de account blad houdt. Sla deze ID op omdat u de ID van het certificaat moet verlengen wanneer u dit tijdstip moet gebruiken.

    - Selecteer een certificaat maken en accepteer de gebruiksvoorwaarden.
    
    - Browseto de aanvraag voor certificaatondertekening die u naar uw computer hebt gedownload vanuit Microsoft 365 en selectUpload.
    
    - Downloadthe APN-certificaat dat is gemaakt door de Apple Push Certificate-Portal naar uw computer.

    >[!TIP]
    >Als u problemen ondervindt bij het downloaden van het certificaat, vernieuwt u de browser.

7. Ga terug naar Microsoft 365 en selecteer **volgende**.   

8. Blader naar het APN-certificaat dat u hebt gedownload van de Apple Push Certificate-Portal.   

9. Selecteer  **Voltooien**.  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Stap 3: (aanbevolen) meervoudige verificatie instellen

MFA helpt de aanmelding bij Microsoft 365 te beschermen voor de registratie van mobiele apparaten door een tweede vorm van verificatie te vereisen. Gebruikers moeten een telefoongesprek, een SMS-bericht of een app-melding op hun mobiele apparaat erkennen na het juiste wachtwoord voor het werkaccount invoeren. Ze kunnen hun apparaat alleen registreren na voltooiing van dit tweede formulierverificatie. Nadat gebruikers apparaten zijn ingeschreven voor basis mobiliteit en beveiliging, hebben gebruikers alleen toegang tot Microsoft 365-bronnen met hun werkaccount.

Zie [Meervoudige verificatie instellen](https://go.microsoft.com/fwlink/p/?LinkId=519255)voor meer informatie over het inschakelen van MFA in de Azure AD-Portal.

Nadat u MFA hebt ingesteld, gaat u terug naar het compliance-& Beveiligingscentrum en **gaat u naar**het hulpmiddel voor   >  het beheer van**Apparaatbeheer**,   >  **Device policies**   zodat u de volgende stap kunt voltooien.

### <a name="step-4-recommended-manage-device-security-policies"></a>Stap 4: (aanbevolen) beveiligingsbeleid voor apparaten beheren

De volgende stap is het maken en implementeren van beveiligingsbeleidsregels voor apparaten om uw Microsoft 365-organisatiegegevens te helpen beschermen. U kunt bijvoorbeeld verlies van gegevens voorkomen wanneer een gebruiker zijn of haar apparaat kwijtraakt door een beleid te maken om apparaten na vijf minuten inactiviteit te vergrendelen en apparaten te wissen na drie aanmeldfouten.

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount. 

2. Selecteer [Mobile Device Management activeren](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Als de service wordt geactiveerd, wordt in plaats van de activerings stappen een koppeling weergegeven voor het [beheren van apparaten](https://admin.microsoft.com/adminportal/home#/MifoDevices)   .
    
3. Ga naar **apparaatbeleid**.

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basisinstellingen voor beveiliging en mobiliteits beleid":::

4. Maak en implementeer beveiligingsbeleid voor apparaten dat geschikt is voor uw organisatie aan de hand van de stappen in [beveiligingsbeleid voor apparaat maken in eenvoudige mobiliteit en beveiliging](create-device-security-policies.md).

>[!TIP]
    - Wanneer u een nieuw beleid maakt, is het raadzaam om het beleid in te stellen op schending van toegangs-en rapport beleid waarbij een gebruikersapparaat niet voldoet aan het beleid. Hiermee kunt u zien hoeveel mobiele apparaten door het beleid worden beïnvloed zonder dat u de toegang tot Microsoft 365 blokkeert.<br/>-Voordat u een nieuw beleid implementeert voor iedereen in uw organisatie, is het raadzaam om dit te testen op de apparaten die door een klein aantal gebruikers worden gebruikt.<br/>Voordat u beleidsregels implementeert, kunt u ook de potentiële gevolgen van het registreren van een apparaat in basis mobiliteit en beveiliging weten. Afhankelijk van de manier waarop u beleidsregels hebt ingesteld, kunnen apparaten die niet voldoen aan beleidsregels (niet-compatibele apparaten), worden geblokkeerd voor het openen van Microsoft 365. Niet-compatibele apparaten kunnen ook apps hebben geïnstalleerd, Foto's en andere persoonlijke gegevens die, op een geregistreerd apparaat, kunnen worden verwijderd als het apparaat wordt gewist. Zie [een mobiel apparaat wissen in basis mobiliteit en beveiliging](wipe-mobile-device.md)voor meer informatie.
    
## <a name="make-sure-users-enroll-their-devices"></a>Zorg ervoor dat gebruikers hun apparaten registreren

Nadat u een beleid voor mobiel Apparaatbeheer hebt gemaakt en geïmplementeerd, ontvangt u in de desbetreffende Microsoft 365-gebruiker in uw organisatie dat het apparaatbeleid van toepassing is, een inschrijvingsbericht wanneer u zich de volgende keer aanmeldt bij Microsoft 365 vanaf hun mobiele apparaat. De stappen voor het registreren en activeren moeten worden voltooid voordat ze toegang hebben tot Microsoft 365-e-mail en-documenten. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device.md).

>[!IMPORTANT]
>Als de voorkeurstaal van een gebruiker niet wordt ondersteund door het registratieproces, ontvangen gebruikers mogelijk een melding voor de inschrijving en de stappen op hun mobiele apparaat in een andere taal. Niet alle talen die worden ondersteund in Microsoft 365 worden momenteel ondersteund voor het registratieproces op mobiele apparaten.

Gebruikers met Android-of iOS-apparaten moeten als onderdeel van het registratieproces de bedrijfs portal-app installeren.

## <a name="related-topics"></a>Verwante onderwerpen

[Mogelijkheden van eenvoudige mobiliteit en beveiliging](capabilities.md)<br/>
[Beveiligingsbeleid voor apparaten maken in eenvoudige mobiliteit en beveiliging](create-device-security-policies.md)