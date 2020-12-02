---
title: DNS-records toevoegen om het domein te verbinden
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Lees hier hoe u uw domein kunt verifiëren en DNS-records kunt maken bij een DNS-hostingprovider voor Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: bc22dbd3a050516f518c9ddc9ccf5a3af9c76f12
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519291"
---
# <a name="add-dns-records-to-connect-your-domain"></a>DNS-records toevoegen om het domein te verbinden

Als u een domein hebt aangekocht bij een externe hostingprovider, kunt u dit verbinden met Microsoft 365 door de DNS-records bij te werken in het account van uw registrar.

Na het doorlopen van dit stappenproces blijft uw domein geregistreerd bij de host waar u het domein hebt gekocht, maar Microsoft 365 kan het gebruiken voor e-mailadressen (zoals gebruiker@uwdomein.com) en andere services.

Als u geen domein toevoegt, maken de mensen in uw organisatie gebruik van het domein onmicrosoft.com voor hun e-mailadressen totdat u dit wel doet. Het is belangrijk om een domein toe te voegen voordat u gebruikers toevoegt, zodat u die niet tweemaal hoeft in te stellen.

[Raadpleeg Veelgestelde vragen over domeinen](../setup/domains-faq.md) als u hieronder niet kunt vinden wat u zoekt.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Stap 1: Voeg een TXT- of MX-record toe om te verifiëren dat u eigenaar van het domein bent

### <a name="recommended-verify-with-a-txt-record"></a>Aanbevolen: verifiëren met een TXT-record

Eerst moet u bewijzen dat u de eigenaar bent van het domein dat u wilt toevoegen aan Microsoft 365.

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en selecteer **Alles weergeven** > **Instellingen** > **Domeinen**.
2. In een nieuw browsertabblad of -venster meldt u zich aan bij uw DNS-hostingprovider en vervolgens gaat u naar de locatie waar u de DNS-instellingen kunt beheren (bijv. Instellingen zonebestand, Beheer domeinen, Domeinbeheer, DNS-beheer).
3. Ga naar de pagina DNS-beheer van uw provider en voeg de TXT-record die in het Beheercentrum wordt weergegeven toe aan uw domein.

Het toevoegen van deze record is niet van invloed op uw bestaande e-mail- of andere services en u kunt deze veilig verwijderen als uw domein eenmaal is verbonden met Microsoft 365.

Voorbeeld:
- TXT-naam: `@`
- TXT-waarde: MS=ms######## (unieke ID uit het Beheercentrum)
- TTL: `3600‎` (of de standaardwaarde van uw provider)

4. Sla de record op, ga terug naar het Beheercentrum en selecteer vervolgens **Verifiëren**. Het duurt ongeveer 15 minuten voordat recordwijzigingen zijn doorgevoerd, maar soms kan het langer duren. Wacht even en probeer het een aantal keer totdat de wijziging is doorgevoerd.

Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.

### <a name="verify-with-an-mx-record"></a>Verifiëren met een MX-record

Als het toevoegen van TXT-records niet wordt toegestaan door uw registrar, kunt u verifiëren door een MX-record toe te voegen.

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en selecteer **Alles weergeven** > **Instellingen** > **Domeinen**.
2. In een nieuw browsertabblad of -venster meldt u zich aan bij uw DNS-hostingprovider en vervolgens gaat u naar de locatie waar u de DNS-instellingen kunt beheren (bijv. Instellingen zonebestand, Beheer domeinen, Domeinbeheer, DNS-beheer).
3. Ga naar de pagina DNS-beheer van uw provider en voeg de MX-record die in het Beheercentrum wordt weergegeven, toe aan uw domein.

Deze MX-record moet de hoogste **prioriteit** hebben van alle bestaande MX-records voor het domein. Anders kunnen er problemen optreden bij het verzenden en ontvangen van e-mail. U moet deze records verwijderen zodra de domeinverificatie is voltooid.

Zorg dat de velden zijn ingesteld op de volgende waarden:

- Recordtype: `MX`
- Prioriteit: instellen op de hoogst beschikbare waarde, meestal `0`.
- Hostnaam: `@`
- Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.
- TTL: `3600‎` (of de standaardwaarde van uw provider)

Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein geverifieerd.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Stap 2: DNS-records toevoegen om Microsoft-services te verbinden

In een nieuw browsertabblad of -venster meldt u zich aan bij uw DNS-hostingprovider en gaat u naar de locatie waar u de DNS-instellingen kunt beheren (bijv. Instellingen zonebestand, Beheer domeinen, Domeinbeheer, DNS-beheer).

Afhankelijk van de services die u wilt inschakelen, kunt u verschillende typen DNS-records toevoegen. 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Een MX-record toevoegen voor e-mail (Outlook, Exchange Online)
**Voordat u begint:** als gebruikers al een e-mailadres hebben met uw domein (zoals user@yourdomain.com), kunt u hun accounts aanmaken in het Beheercentrum voordat u de MX-records instelt. Op die manier blijven ze e-mail ontvangen. Wanneer u de MX-record van uw domein bijwerkt, wordt alle nieuwe e-mail voor iedereen die uw domein gebruikt, verzonden naar Microsoft 365. Elk e-mailbericht dat u al hebt, blijft bij uw huidige e-mailhost, tenzij u besluit [e-mail en contactpersonen te migreren naar Microsoft 365](../setup/migrate-email-and-contacts-admin.md).

U ontvangt de informatie voor de MX-record via de domeininstallatiewizard in Beheercentrum.

Voeg een nieuwe MX-record toe op de website van de hostingprovider.
Zorg dat de velden zijn ingesteld op de volgende waarden:

- Recordtype: `MX`
- Prioriteit: instellen op de hoogst beschikbare waarde, meestal `0`.
- Hostnaam: `@`
- Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.
- TTL: `3600‎` (of de standaardwaarde van uw provider)

Sla de record op en verwijder vervolgens alle andere MX-records.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Voeg CNAME-records toe om andere services te verbinden (Teams, Exchange Online, AAD, MDM)
U ontvangt de informatie voor de CNAME-records via de domeininstallatiewizard in Beheercentrum.

Voeg op de website van de hostingprovider CNAME-records toe voor elke service die u wilt verbinden.
Zorg dat de velden zijn ingesteld op de volgende waarden voor elk:

- Recordtype: `CNAME (Alias)`
- Host: plak hier de waarden die u kopieert vanuit Beheercentrum.
- Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.
- TTL: `3600‎` (of de standaardwaarde van uw provider)


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Een SPF TXT-record toevoegen of bewerken om spam te helpen voorkomen (Outlook, Exchange Online)
**Voordat u begint:** als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 aan te maken. In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record op de website van de hostingprovider, zodat u beschikt over *één* enkel SPF-record waarin beide waardensets zijn opgenomen.

Op de website van de hostingprovider bewerkt u de bestaande SPF-record of maakt u een nieuwe SPF-record aan.
Zorg dat de velden zijn ingesteld op de volgende waarden:

- Recordtype: `TXT (Text)`
- Host: `@`
- TXT-waarde: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (of de standaardwaarde van uw provider)

Sla de record op.

Voor het valideren van uw SPF-record, gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Microsoft 365 configureren. 

Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) en [DMARC gebruiken om e-mail te valideren in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>SRV-records toevoegen voor communicatieservices (Teams, Skype voor Bedrijven)

Voeg op de website van de hostingprovider SRV-records toe voor elke service die u wilt verbinden.
Zorg dat de velden zijn ingesteld op de volgende waarden voor elk:

- Recordtype: `SRV (Service)`
- Naam: `@`
- Doel: kopieer de waarde uit het Beheercentrum en plak deze hier.
- Protocol: kopieer de waarde uit het Beheercentrum en plak deze hier.
- Service: kopieer de waarde uit het Beheercentrum en plak deze hier.
- Prioriteit: `100`
- Gewicht: `1`
- Poort: kopieer de waarde uit het Beheercentrum en plak deze hier.
- TTL: `3600‎` (of de standaardwaarde van uw provider)

Sla de record op.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Veldbeperkingen en tijdelijke oplossingen voor SRV-records
Sommige hostingproviders stellen beperkingen in voor veldwaarden binnen SRV-records. Hier vindt u enkele veelvoorkomende tijdelijke oplossingen voor deze beperkingen.

##### <a name="name"></a>Naam
Als de hostingprovider niet toestaat om dit veld in te stellen op **@**, laat u het veld leeg. Gebruik deze methode *alleen* wanneer de hostingprovider afzonderlijke velden voor de waarden Service en Protocol heeft. Raadpleeg anders onderstaande opmerkingen bij Service en Protocol.

##### <a name="service-and-protocol"></a>Service en Protocol
Als uw hostingprovider niet in deze velden voor SRV-records voorziet, geeft u de waarden voor **Service** en **Protocol** op in het **Naam**-veld van de record. (Opmerking: Afhankelijk van de hostingprovider kan het **Naam**-veld anders heten, bijvoorbeeld **Host**, **Hostnaam** of **Subdomein**.) Om deze waarden toe te voegen, maakt u één enkele tekenreeks, waarin de waarden van elkaar zijn gescheiden door een punt. 

Voorbeeld: `_sip._tls`

##### <a name="priority-weight-and-port-br"></a>Prioriteit, Gewicht en Poort <br>
Als uw hostingprovider niet in deze velden voor SRV-records voorziet, geeft u ze op in het **Doel**-veld van de record. (Opmerking: afhankelijk van uw hostingprovider kan het **Doel**-veld anders heten, bijvoorbeeld: **Inhoud**, **IP-adres**, of **Doelhost**.) 

Als u deze waarden wilt toevoegen, moet u één enkele tekenreeks aanmaken, waarbij de waarden worden gescheiden door spaties en *soms eindigen met een punt* (neem contact op met uw provider als u niet zeker bent). De waarden moeten in de volgende volgorde worden opgenomen: Prioriteit, Gewicht, Poort, Doel. 

- Voorbeeld 1: `100 1 443 sipdir.online.lync.com.`
- Voorbeeld 2: `100 1 443 sipdir.online.lync.com`
