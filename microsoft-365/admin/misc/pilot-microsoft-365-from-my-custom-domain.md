---
title: Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het testen van e-mailfunctionaliteit vanaf mijn aangepast domein in een Microsoft 365-postvak met slechts twee testaccounts.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186041"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein

U kunt Microsoft 365 testen met de volgende vereisten en beperkingen:

- Uw huidige e-mailprovider moet ondersteuning bieden voor het doorsturen van e-mail.

- U moet uw DNS-records voor Microsoft 365 beheren bij uw DNS-hostingprovider in plaats van dat Microsoft 365 dat voor u doet.

    Zie [DNS-records toevoegen om het domein te verbinden](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) voor meer informatie.

- Beschikbaarheidsinfo voor gebruikers op de andere e-mailserver is niet beschikbaar.

- Beheerders kunnen niet alle gebruikersaccounts vanaf één locatie beheren.

- Gebruikers kunnen mogelijk geen gebruik maken van Microsoft 365-spamfilters.

## <a name="set-up-a-microsoft-365-pilot"></a>Testfase van Microsoft 365 instellen

Volg deze stappen om een Microsoft 365-testfase in te stellen:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>Stap 1: aanmelden bij het Microsoft 365-beheercentrum

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw werk- of schoolaccount.

2. Selecteer **Instellingen** > **Domeinen** in het linker navigatiedeelvenster.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>Stap 2: controleren of u de eigenaar bent van het domein dat u wilt gebruiken

1. Op de pagina **Domeinen** selecteert u **Domein toevoegen**.

2. Typ de domeinnaam in het vak, selecteer **Dit domein gebruiken** en selecteer vervolgens **Doorgaan**.

3. Selecteer de services die u met uw domein wilt testen, zoals e-mail en chatberichten.

5. Volg de stapsgewijze instructies op de pagina **Domein verifiëren** en selecteer **Verifiëren**.

    Het doorvoeren van DNS-wijzigingen kan enkele minuten tot 72 uur duren.

    Als de verificatie is gelukt, wordt u gevraagd uw DNS-records te wijzigen. 

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>Stap 3: het domein in Exchange Online markeren als 'gedeeld'

1. In het Exchange-beheercentrum selecteert u in de sectie **E-mailstroom** de optie **Geaccepteerde domeinen** en selecteert u vervolgens het domein dat u wilt wijzigen.

2. Dubbelklik op het venster om het te openen en selecteer **Interne relay**. 

3. Selecteer **Opslaan**.

    Het kan enkele minuten duren voordat deze instelling is doorgevoerd. 

### <a name="step-4-unblock-the-existing-email-server-optional"></a>Stap 4: blokkering van de bestaande e-mailserver opheffen (optioneel)

Microsoft 365 maakt gebruik van Exchange Online Protection (EOP) voor bescherming tegen spam. Met EOP kunt u uw bestaande e-mailserver blokkeren als een grote hoeveelheid spam door de huidige e-mailserver wordt doorgestuurd. Als u de spambeveiliging voor uw andere e-mailprovider vertrouwt, kunt u de blokkering van de server in Microsoft 365 opheffen.

> [!NOTE]
> Als u de blokkering van uw bestaande e-mailserver opheft, kan spam die via de oorspronkelijke server binnenkomt, naar de Microsoft 365-postvakken worden gestuurd. U kunt dan niet evalueren hoe goed spam wordt tegengehouden in Microsoft 365.

1. In het navigatiedeelvenster van het Exchange-beheercentrum selecteert u **Beveiliging** en vervolgens **Verbindingsfilter**.

2. In de **IP-acceptatielijst** selecteert u **+** en voegt u het IP-adres van de e-mailserver van uw huidige e-mailprovider toe. 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>Stap 5: gebruikersaccounts maken en het primaire antwoordadres instellen

1. Selecteer in het linker navigatiedeelvenster van het Microsoft 365-beheercentrum de opties **Gebruikers** > **Actieve gebruikers**.

2. Maak twee testaccounts door twee bestaande gebruikers toe te voegen.

    Voor elk account selecteert u **+ Een gebruiker toevoegen** en vult u de vereiste gegevens in, inclusief de wachtwoordmethode die u wilt testen.

    Als u wilt dat het e-mailadres van een gebruiker ongewijzigd blijft, moet het veld **Gebruikersnaam** overeenkomen met het huidige e-mailadres van de gebruiker.

3. Kies de juiste licentie, klik op **Volgende** en klik vervolgens op **Toevoegen voltooien**. 

4. Selecteer naast **Gebruikersnaam** de naam van het aangepaste domein in de vervolgkeuzelijst. 

5. Selecteer **Maken** > **Sluiten**.

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>Stap 6: DNS-records bijwerken bij uw DNS-hostingprovider

Meld u aan bij de website van uw DNS-hostingprovider en volg de instructies op [DNS-records toevoegen om het domein te verbinden](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

**Maak de volgende twee uitzonderingen:**

- Maak geen nieuwe MX-record of wijzig uw bestaande MX-record niet.

- Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u 'include:spf.protection.outlook.com' toe aan de huidige TXT-record in plaats van een nieuwe SPF (TXT)-record te maken voor Exchange Online.

    Bijvoorbeeld 'v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all'.

    Als u geen SPF-record hebt, wijzigt u de door Microsoft 365 aanbevolen record om het domein voor uw huidige e-mailprovider op te nemen en voegt u spf.protection.outlook.com toe. Hiermee autoriseert u uitgaande berichten van beide e-mailsystemen.

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>Stap 7: doorsturen van e-mail instellen bij uw huidige provider

Stel bij uw huidige e-mailprovider het doorsturen van e-mail in voor de e-mailaccounts van uw gebruikers voor het onmicrosoft.com-domein:

- Postvak van gebruiker A doorsturen naar gebruikera@uwbedrijf.onmicrosoft.com

- Postvak van gebruiker B doorsturen naar gebruikerb@uwbedrijf.onmicrosoft.com

Wanneer u deze stap hebt voltooid, zijn alle e-mailberichten die naar gebruikera@uwbedrijf.onmicrosoft.com en gebruikerb@uwbedrijf.onmicrosoft.com zijn verzonden, beschikbaar in Microsoft 365.

> [!NOTE]
> Neem contact op met uw huidige e-mailprovider voor de juiste stappen voor het instellen van het doorsturen van e-mail.<br/>
> U hoeft geen kopie van berichten te bewaren bij de huidige e-mailprovider. <br/>
> Bij de meeste providers blijft het antwoordadres van de afzender behouden bij het doorsturen van e-mail. Antwoorden worden dus verzonden naar de oorspronkelijke afzender. 

### <a name="step-8-test-mail-flow"></a>Stap 8: e-mailstroom testen

1. Meld u aan bij Outlook Web App met de referenties van gebruiker A.

2. Voer de volgende tests uit:

    - Test lokale Microsoft-e-mail door een e-mailbericht te verzenden naar bijvoorbeeld gebruiker B. Het e-mailbericht wordt onmiddellijk bezorgd. In dit scenario wordt het bericht niet gerouteerd naar het postvak van gebruiker B op de oorspronkelijke server, omdat het Microsoft 365-postvak lokaal is.

    - Test het verzenden van e-mail naar een gebruiker in het bestaande e-mailsysteem door een e-mailbericht te verzenden naar bijvoorbeeld gebruiker C. Het e-mailbericht wordt in het postvak van gebruiker C op de oorspronkelijke e-mailserver bezorgd.

    - Controleer of het doorsturen correct is ingesteld vanaf een extern account of vanaf een e-mailaccount van een werknemer in het bestaande e-mailsysteem. Bijvoorbeeld: verzend vanaf het oorspronkelijke serveraccount voor gebruiker C of vanaf een Hotmail-account een e-mailbericht naar gebruiker A en controleer of het wordt bezorgd in het Microsoft 365-postvak voor gebruiker A.

### <a name="step-9-move-mailbox-contents"></a>Stap 9: inhoud van postvak verplaatsen

Aangezien er slechts twee testgebruikers worden verplaatst en gebruiker A en gebruiker B beide Outlook gebruiken, kunt u de e-mail verplaatsen door het oude PST-bestand te openen in het nieuwe Outlook-profiel en de berichten, agenda-items, contactpersonen, enzovoort te kopiëren. Zie [E-mail, contactpersonen en agenda importeren vanuit een PST-bestand in Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac) voor meer informatie.

Nadat de items naar de juiste locaties in het Microsoft 365-postvak zijn geïmporteerd, kunnen ze overal op elk apparaat worden geopend.

Als er meer postvakken betrokken zijn of als Outlook niet wordt gebruikt, kunt u de migratiehulpprogramma's in het Exchange-beheercentrum gebruiken. Ga aan de slag door naar het Exchange-beheercentrum te gaan en de aanwijzingen te volgen in [E-mail migreren vanaf een IMAP-server naar Exchange Online-postvakken].