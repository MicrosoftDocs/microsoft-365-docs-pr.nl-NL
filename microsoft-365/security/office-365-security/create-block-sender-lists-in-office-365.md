---
title: Lijst met geblokkeerde afzenders maken
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
description: Beheerders kunnen meer informatie krijgen over de beschikbare en voorkeursopties voor het blokkeren van binnenkomende berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fa2a5e0c71f14838dc8446431f5ea02a535fb787
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331452"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Geblokkeerde afzenderlijsten maken in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, biedt EOP meerdere manieren om e-mail van ongewenste afzenders te blokkeren. Deze opties zijn: Geblokkeerde afzenders van Outlook, lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten in antispambeleid, Exchange-regels voor e-mailstroom (ook wel transportregels genoemd) en de IP-bloklijst (verbindingsfiltering). U kunt deze opties gezamenlijk zien als _geblokkeerde afzenderlijsten._

De beste methode om afzenders te blokkeren, is afhankelijk van het effectbereik. Voor één gebruiker kan outlook geblokkeerde afzenders de juiste oplossing zijn. Voor veel gebruikers is een van de andere opties geschikter. De volgende opties worden gerangschikt op impactbereik en breedte. De lijst gaat van smal naar breed, maar *leest de details voor* volledige aanbevelingen.

1. Geblokkeerde afzenders in Outlook (de lijst Geblokkeerde afzenders die in elk postvak is opgeslagen)

2. Lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten (antispambeleid)

3. Regels voor e-mailstroom

4. De LIJST MET IP-blokkering (verbindingsfilters)

> [!NOTE]
> Hoewel u instellingen voor blokkeringen voor de hele organisatie kunt gebruiken om onwaar negatieven (gemiste spam) aan te pakken, moet u deze berichten ook indienen bij Microsoft voor analyse. Als u onwaar negatieven beheert met behulp van bloklijsten, wordt uw administratieve overhead aanzienlijk verhoogd. Als u bloklijsten gebruikt om gemiste spam tegen te gaan, moet u het onderwerp Berichten en bestanden rapporteren aan [Microsoft](report-junk-email-messages-to-microsoft.md) gereed houden.

U hebt daarentegen ook verschillende opties om e-mail uit specifieke bronnen altijd toe te staan met _behulp van lijsten met veilige afzenders._ Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) voor meer informatie.

## <a name="email-message-basics"></a>Basisbeginselen van e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud. De envelop met berichten bevat informatie die nodig is voor het verzenden en verzenden van het bericht tussen SMTP-servers. De berichtinhoud bevat berichtkopvelden (gezamenlijk de *berichtkop* genoemd) en de hoofdtekst van het bericht. De bericht envelop wordt beschreven in RFC 5321 en de berichtkop wordt beschreven in RFC 5322. Geadresseerden zien nooit de werkelijke bericht envelop omdat deze wordt gegenereerd door het berichttransmissieproces en het bericht niet deel uitmaakt van het bericht.

- Het `5321.MailFrom` adres (ook wel mail **from-adres,** P1-afzender of afzender van de envelop genoemd) is het e-mailadres dat wordt gebruikt bij de SMTP-verzending van het bericht. Dit **e-mailadres** wordt meestal opgenomen in het veld Koptekst van het retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor retourpaden kan aanwijzen). Als het bericht niet kan worden bezorgd, is het de geadresseerde voor het rapport niet-bezorging (ook wel een NDR- of bouncebericht genoemd).

- De afzender (ook wel het Van-adres of de afzender van P2 genoemd) is het e-mailadres in het veld Koptekst van Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail  clients. 

Vaak zijn de `5321.MailFrom` adressen en adressen hetzelfde `5322.From` (communicatie tussen personen). Wanneer e-mail echter namens iemand anders wordt verzonden, kunnen de adressen anders zijn.

Lijsten met geblokkeerde afzenders en geblokkeerde domeinlijsten in antispambeleid in EOP controleren zowel de adressen `5321.MailFrom` als de `5322.From` adressen. In Outlook Blocked Senders wordt alleen het adres `5322.From` gebruikt.

## <a name="use-outlook-blocked-senders"></a>Geblokkeerde afzenders van Outlook gebruiken

Wanneer slechts een klein aantal gebruikers ongewenste e-mail heeft ontvangen, kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst Geblokkeerde afzenders in het postvak. Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md)voor instructies.

Wanneer berichten zijn geblokkeerd vanwege de lijst Geblokkeerde afzenders van een gebruiker, bevat het **veld X-Forefront-Antispam-Report** de waarde `SFV:BLK` .

> [!NOTE]
> Als de ongewenste berichten nieuwsbrieven zijn van een betrouwbare en herkenbare bron, is het afmelden van de e-mail een andere optie om te voorkomen dat de gebruiker de berichten ontvangt.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten gebruiken

Wanneer meerdere gebruikers worden beïnvloed, is het bereik breder, dus de volgende beste optie is geblokkeerde afzenderlijsten of geblokkeerde domeinlijsten in antispambeleid. Berichten van afzenders op de lijsten worden gemarkeerd als spam met hoog  vertrouwen **en** de actie die u hebt geconfigureerd voor de uitspraak over het hoge vertrouwensfilter wordt in het bericht opgenomen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

## <a name="use-mail-flow-rules"></a>Regels voor e-mailstroom gebruiken

Als u berichten wilt blokkeren die naar specifieke gebruikers of in de hele organisatie worden verzonden, kunt u e-mailstroomregels gebruiken. E-mailstroomregels zijn flexibeler dan lijsten met afzenders of geblokkeerde afzenderdomeinlijsten, omdat ze ook kunnen zoeken naar trefwoorden of andere eigenschappen in de ongewenste berichten.

Ongeacht de voorwaarden of uitzonderingen die u gebruikt om de berichten te identificeren, configureert u de actie om het betrouwbaarheidsniveau voor spam (SCL) van het bericht in te stellen op 9, waarmee het bericht wordt gemarkeerd als spam met hoog **vertrouwen.** Zie E-mailstroomregels gebruiken om de SCL in berichten [in te stellen voor meer informatie.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> Het is eenvoudig om regels  te maken die te agressief zijn, dus het is belangrijk dat u alleen de berichten identificeert die u wilt blokkeren met behulp van zeer specifieke criteria. Zorg er ook voor dat u controle op de regel inschakelen en de resultaten van de regel test om ervoor te zorgen dat alles werkt zoals verwacht.

## <a name="use-the-ip-block-list"></a>De LIJST MET IP-blokkeringen gebruiken

Als het niet mogelijk is om een van de andere opties te gebruiken om een afzender te *blokkeren,* moet u alleen de IP-bloklijst gebruiken in het verbindingsfilterbeleid. Zie Het verbindingsfilterbeleid configureren voor [meer informatie.](configure-the-connection-filter-policy.md) Het is belangrijk om het aantal geblokkeerde IP-adressen tot een minimum te beperken, dus het blokkeren van hele IP-adresbereiken wordt *afgeraden.*

U  moet vooral voorkomen dat IP-adresbereiken worden toegevoegd die behoren tot consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuren, en zorg er ook voor dat u de lijst met geblokkeerde IP-adressen controleert als onderdeel van regelmatig onderhoud.
