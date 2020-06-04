---
title: Lijst met geblokkeerde afzenders maken
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Beheerders kunnen meer te weten komen over de beschikbare en gewenste opties om binnenkomende berichten te blokkeren in Exchange Online Protection (EOP).
ms.openlocfilehash: 2862fa4a33a31eac9c61f94aa929133d2dc69fc8
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545898"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Lijsten met geblokkeerde afzenders maken in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken biedt EOP meerdere manieren om e-mail van ongewenste afzenders te blokkeren. Deze opties omvatten Outlook Geblokkeerde afzenders, geblokkeerde afzenderlijsten of geblokkeerde domeinlijsten in antispambeleid, Exchange-e-mailstroomregels (ook wel transportregels genoemd) en de IP-blokkerlijst (verbindingsfiltering). Samen u deze opties zien als _geblokkeerde afzenderlijsten._

De beste methode om afzenders te blokkeren, is afhankelijk van de impact. Voor één gebruiker kan de juiste oplossing Outlook Geblokkeerde afzenders zijn. Voor veel gebruikers zou een van de andere opties meer geschikt zijn. De volgende opties worden gerangschikt op basis van zowel impact scope en breedte. De lijst gaat van smal naar breed, maar *lees de details* voor volledige aanbevelingen.

1. Outlook Geblokkeerde afzenders (de lijst Geblokkeerde afzenders die in elk postvak is opgeslagen)

2. Lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten (antispambeleid)

3. Regels voor e-mailstroom

4. De IP-bloklijst (verbindingsfilter)

> [!NOTE]
> Hoewel u blokinstellingen voor de hele organisatie gebruiken om valse negatieven (gemiste spam) aan te pakken, moet u deze berichten ook voor analyse bij Microsoft indienen. Het beheren van foute negatieven met behulp van bloklijsten verhoogt uw administratieve overhead aanzienlijk. Als u bloklijsten gebruikt om gemiste spam af te leiden, moet u het onderwerp [Rapporteren berichten en bestanden in](report-junk-email-messages-to-microsoft.md) de aanslag bij Microsoft in de aanslag houden.

In tegenstelling, hebt u ook verscheidene opties om e-mail van specifieke bronnen altijd toe te staan gebruikend _veilige afzenderlijsten._ Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) voor meer informatie.

## <a name="email-message-basics"></a>Basisprincipes van e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *berichtenvelop* en berichtinhoud. De berichtenenvelop bevat informatie die nodig is voor het verzenden en afleveren van het bericht tussen SMTP-servers. De berichtinhoud bevat berichtkopvelden (gezamenlijk de *berichtkop genoemd)* en de berichttekst. De berichtenenvelop wordt beschreven in RFC 5321 en de berichtkoptekst wordt beschreven in RFC 5322. Ontvangers zien nooit de werkelijke berichtenenvelop omdat deze wordt gegenereerd door het berichtoverdrachtsproces en het is eigenlijk geen onderdeel van het bericht.

- Het `5321.MailFrom` adres (ook bekend als het **E-mailadres,** P1 afzender of envelop afzender) is het e-mailadres dat wordt gebruikt in de SMTP-transmissie van het bericht. Dit e-mailadres wordt meestal opgenomen in het kopveld **Return-Path** in de berichtkop (hoewel het mogelijk is dat de afzender een ander **e-mailadres voor retourpad** aanwijst). Als het bericht niet kan worden bezorgd, is het de ontvanger voor het rapport niet-levering (ook wel een NDR- of bouncebericht genoemd).

- `5322.From`Het e-mailadres (ook wel bekend als het **van-adres** of de P2-afzender) is het e-mailadres in het veld **Van** koptekst en is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.

Vaak zijn de `5321.MailFrom` adressen en de adressen `5322.From` hetzelfde (persoonlijke communicatie). Wanneer e-mail echter namens iemand anders wordt verzonden, kunnen de adressen anders zijn.

Geblokkeerde afzenderlijsten en geblokkeerde domeinlijsten in antispambeleid in EOP inspecteren zowel de adressen als de `5321.MailFrom` `5322.From` adressen. Outlook Geblokkeerde afzenders gebruikt alleen het `5322.From` adres.

## <a name="use-outlook-blocked-senders"></a>Outlook-geblokkeerde afzenders gebruiken

Wanneer slechts een klein aantal gebruikers ongewenste e-mail heeft ontvangen, kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst Geblokkeerde afzenders in het postvak. Zie Instellingen [voor ongewenste e-mail configureren in Exchange Online-postvakken voor](configure-junk-email-settings-on-exo-mailboxes.md)instructies.

Wanneer berichten worden geblokkeerd vanwege de lijst Geblokkeerde afzenders van een gebruiker, bevat het kopveld **X-Forefront-Antispam-Report** de waarde `SFV:BLK` .

> [!NOTE]
> Als de ongewenste berichten nieuwsbrieven zijn van een betrouwbare en herkenbare bron, is het afmelden van de e-mail een andere optie om te voorkomen dat de gebruiker de berichten ontvangt.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten gebruiken

Wanneer meerdere gebruikers worden beïnvloed, is het bereik breder, dus de volgende beste optie is geblokkeerde afzenderlijsten of geblokkeerde domeinlijsten in antispambeleid. Berichten van afzenders op de lijsten worden gemarkeerd als **spam**en de actie die u hebt geconfigureerd voor het vonnis **over het spamfilter** wordt op het bericht uitgevoerd. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

## <a name="use-mail-flow-rules"></a>Regels voor e-mailstroom gebruiken

Als u berichten moet blokkeren die naar specifieke gebruikers of in de hele organisatie worden verzonden, u regels voor e-mailstroom gebruiken. Regels voor e-mailstroom zijn flexibeler dan lijsten met afzenders blokkeren of domeinlijsten voor geblokkeerde afzenders, omdat ze ook kunnen zoeken naar zoekwoorden of andere eigenschappen in de ongewenste berichten.

Ongeacht de voorwaarden of uitzonderingen die u gebruikt om de berichten te identificeren, configureert u de actie om het spamvertrouwensniveau (SCL) van het bericht in te stellen op 9, wat het bericht markeert als een **spam met een hoog vertrouwen.** Zie [Regels voor e-mailstroom gebruiken om de SCL in berichten in te stellen voor](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)meer informatie.

> [!IMPORTANT]
> Het is eenvoudig om regels te maken die *overdreven* agressief zijn, dus het is belangrijk dat u alleen de berichten identificeert die u wilt blokkeren met behulp van zeer specifieke criteria. Zorg er ook voor dat u controle op de regel mogelijk maakt en de resultaten van de regel test om ervoor te zorgen dat alles werkt zoals verwacht.

## <a name="use-the-ip-block-list"></a>De IP-bloklijst gebruiken

Als het niet mogelijk is om een van de andere opties te gebruiken om een afzender te blokkeren, moet u *alleen de* IP-bloklijst gebruiken in het verbindingsfilterbeleid. Zie [Het verbindingsfilterbeleid configureren](configure-the-connection-filter-policy.md)voor meer informatie. Het is belangrijk om het aantal geblokkeerde IP's tot een minimum te beperken, dus het blokkeren van volledige IP-adresbereiken wordt *niet* aanbevolen.

U moet *vooral* voorkomen dat u IP-adresbereiken toevoegt die behoren tot consumentendiensten (bijvoorbeeld outlook.com) of gedeelde infrastructuren, en er ook voor zorgen dat u de lijst met geblokkeerde IP-adressen bekijkt als onderdeel van regulier onderhoud.
