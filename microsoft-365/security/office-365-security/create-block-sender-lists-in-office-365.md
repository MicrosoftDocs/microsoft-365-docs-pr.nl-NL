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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Beheerders kunnen meer te weten komen over de beschikbare en voorkeursopties voor het blokkeren van inkomende berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: 9b676f96ccdff8be1fa49841a9e0ce44bb59964c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827311"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Lijsten met geblokkeerde afzenders maken in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, biedt EOP meerdere manieren om e-mail van ongewenste afzenders te blokkeren. Deze opties zijn geblokkeerde afzenders van Outlook, lijsten met geblokkeerde afzenders of geblokkeerde domein lijsten in Antispambeleid, Exchange-e-mail stroom regels (ook wel de zogenaamde transportregels genoemd) en de lijst met IP-blok (verbindingen filteren). U kunt ook rekening houden met de volgende opties als _lijsten met geblokkeerde afzenders_.

De beste methode voor het blokkeren van afzenders is afhankelijk van het bereik van impact. De juiste oplossing is voor één gebruiker: geblokkeerde afzenders van Outlook. Voor veel gebruikers is een van de andere opties van toepassing. De volgende opties worden gerangschikt op basis van het bereik en de breedte van de invloed. De lijst gaat van beperkt tot algemeen, maar *Lees de specifieke informatie* voor alle aanbevelingen.

1. Geblokkeerde afzenders in Outlook (de lijst met geblokkeerde afzenders die in elk postvak is opgeslagen)

2. Geblokkeerde lijsten met geblokkeerde afzenders of geblokkeerde domein lijsten (Antispambeleid)

3. Regels voor e-mail stroom

4. De lijst met IP-blok (verbindingen filteren)

> [!NOTE]
> Hoewel u de instellingen voor de blokkering van de gehele organisatie kunt gebruiken om onwaar negatieve waarden (gemist spam) te adresseren, moet u ook die berichten bij Microsoft indienen voor analyse. Wanneer u onjuiste negatieven beheert met behulp van blok lijsten, wordt de beheerskosten aanzienlijk verhoogd. Als u lijsten met geblokkeerde uitgaand spam gebruikt, moet u het onderwerp [berichten en bestanden van het onderwerp naar Microsoft](report-junk-email-messages-to-microsoft.md) laten gaan.

In het contrast hebt u ook verschillende opties om e-mail van bepaalde bronnen altijd toe te staan via _lijsten met veilige afzenders_. Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) voor meer informatie.

## <a name="email-message-basics"></a>Basisbeginselen van e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en de inhoud van het bericht. De envelop bericht bevat informatie die nodig is voor het verzenden en het verzenden van het bericht tussen SMTP-servers. De inhoud van het bericht bevat berichtkop velden (gezamenlijk de kop van het *e-mailbericht*genoemd) en de berichttekst. De envelop van het bericht wordt beschreven in RFC 5321 en de kop van het e-mailbericht wordt beschreven in RFC 5322. Geadresseerden zien de envelop met het werkelijke bericht niet omdat deze wordt gegenereerd door het proces voor het verzenden van berichten en het maakt niet uit van het bericht.

- Het `5321.MailFrom` adres (ook wel **e-mail adres van** de afzender, de afzender van P1 of de afzender) is het e-mailadres dat wordt gebruikt in de SMTP-overdracht van het bericht. Dit e-mailadres wordt meestal opgenomen in het veld voor **de veldnamenrij in de kop van** het bericht (hoewel het mogelijk is dat de afzender een ander e-mailadres voor het **retour traject** aanwijst). Als het bericht niet kan worden bezorgd, is dit de geadresseerde voor het rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of een bericht met een stuiter bericht).

- De `5322.From` (ook bekend als de afzender **van** address of P2) is het e-mailadres in het veld **van** koptekst en het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.

Vaak zijn de `5321.MailFrom` en `5322.From` -adressen hetzelfde (communicatie van persoon naar persoon). Wanneer e-mail echter wordt verzonden namens iemand anders, kunnen de adressen afwijken.

Geblokkeerde lijsten met geblokkeerde afzenders en geblokkeerde domein lijsten in het antispambeleid van EOP dienen beide `5321.MailFrom` en adressen te controleren `5322.From` . Geblokkeerde afzenders in Outlook gebruiken het `5322.From` adres.

## <a name="use-outlook-blocked-senders"></a>Geblokkeerde afzenders in Outlook gebruiken

Wanneer slechts een klein aantal gebruikers ongewenste e-mail heeft ontvangen, kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst met geblokkeerde afzenders in het postvak. Zie [instellingen voor ongewenste e-mail in postvakken van Exchange Online configureren](configure-junk-email-settings-on-exo-mailboxes.md)voor instructies.

Wanneer berichten zijn geblokkeerd door de lijst met geblokkeerde afzenders van een gebruiker, bevat het veld **X-Forefront-spam-report** header de waarde `SFV:BLK` .

> [!NOTE]
> Als de ongewenste berichten een nieuwsbrief zijn van een betrouwbare en herkenbare bron, is het afmelden van de e-mail een andere optie om te voorkomen dat de gebruiker de berichten ontvangt.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Lijsten met geblokkeerde afzenders of geblokkeerde domeinen gebruiken

Wanneer meerdere gebruikers van invloed zijn, is de scope breder, zodat de volgende beste optie lijsten met geblokkeerde afzenders of geblokkeerde domein lijsten in Antispambeleid bevat. Berichten van afzenders in de lijsten worden als **ongewenste e-mail**gemarkeerd en de actie die u hebt geconfigureerd voor het **spam** filter verdict wordt in het bericht opgenomen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

## <a name="use-mail-flow-rules"></a>Regels voor e-mail stroom gebruiken

Als u berichten wilt blokkeren die zijn verzonden naar specifieke gebruikers of over de hele organisatie, kunt u de e-mail stroom regels gebruiken. De regels voor e-mail stroom zijn flexibeler dan lijsten van afzenders blokkeren of geblokkeerde domein lijsten, omdat ze ook naar trefwoorden of andere eigenschappen in de ongewenste berichten kunnen zoeken.

Ongeacht de voorwaarden of uitzonderingen waarmee u berichten identificeert, configureert u de actie voor het instellen van het spam betrouwbaarheidsniveau (SCL) van het bericht in 9, waarmee het bericht een **hoge betrouwbaarheid spam**ontvangt. Zie voor meer informatie [de regels voor de e-mail stroom gebruiken om de SCL in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Het is heel eenvoudig om regels te maken *die zich bevinden,* dus het is belangrijk dat u alleen de berichten identificeert die u wilt blokkeren met behulp van een zeer specifiek criterium. Zorg er ook voor dat u de controlefunctie op de regel inschakelt en de resultaten van de regel test om er zeker van te zijn dat alles naar verwachting werkt.

## <a name="use-the-ip-block-list"></a>De lijst met IP-blok lijsten gebruiken

Als u een afzender niet kunt blokkeren met een van de andere *Opties, gebruikt* u de lijst met geblokkeerde IP-adressen in het filter beleid voor verbindingen. Zie [het beleid voor verbindings filters configureren](configure-the-connection-filter-policy.md)voor meer informatie. Het is belangrijk dat u het aantal geblokkeerde IPs naar een minimum beperkt, zodat het blokkeren van hele IP-adresbereiken *niet* wordt aanbevolen.

U dient *met name* geen IP-adresbereiken toe te voegen die deel uitmaken van de consument service (bijvoorbeeld Outlook.com) of gedeelde infrastructuur, en er ook voor zorgen dat u de lijst met geblokkeerde IP-adressen als onderdeel van normaal onderhoud controleert.
