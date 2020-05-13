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
description: Beheerders kunnen meer te weten komen over de beschikbare en voorkeursopties om binnenkomende berichten te blokkeren in Exchange Online Protection (EOP).
ms.openlocfilehash: d9db3d4ac123998e6ab4f108199b3aee852f95d6
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209545"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Lijsten met geblokkeerde afzenders maken in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, biedt EOP meerdere manieren om e-mail van ongewenste afzenders te blokkeren. Deze opties omvatten Outlook Geblokkeerde afzenders, geblokkeerde afzenderlijsten of geblokkeerde domeinlijsten in antispambeleid, Exchange-e-mailstroomregels (ook wel transportregels genoemd) en de IP-bloklijst (verbindingsfiltering). Gezamenlijk u deze opties zien als _geblokkeerde afzenderlijsten._

De beste methode om afzenders te blokkeren, is afhankelijk van de impact. Voor één gebruiker kan de juiste oplossing Outlook Blocked Senders zijn. Voor veel gebruikers zou een van de andere opties meer geschikt zijn. De volgende opties worden gerangschikt op basis van zowel impactscope als breedte. De lijst gaat van smal naar breed, maar *lees de details* voor volledige aanbevelingen.

1. Geblokkeerde afzenders van Outlook (de lijst Met geblokkeerde afzenders die in elk postvak is opgeslagen)

2. Lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten (antispambeleid)

3. Regels voor e-mailstromen

4. De IP-bloklijst (verbindingsfiltering)

> [!NOTE]
> Hoewel u blokinstellingen voor de hele organisatie gebruiken om foutnegatieven (gemiste spam) aan te pakken, moet u deze berichten ook voor analyse bij Microsoft indienen. Het beheren van foute negatieven door bloklijsten te gebruiken, verhoogt uw administratieve overhead aanzienlijk. Als u bloklijsten gebruikt om gemiste spam af te leiden, moet u het onderwerp [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md) in de aanslag houden.

U hebt daarentegen ook verschillende opties om e-mail van specifieke bronnen altijd toe te staan met behulp van _lijsten met veilige afzenders._ Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) voor meer informatie.

## <a name="use-outlook-blocked-senders"></a>Outlook-geblokkeerde afzenders gebruiken

Wanneer slechts een klein aantal gebruikers ongewenste e-mail heeft ontvangen, kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst Geblokkeerde afzenders in het postvak. Zie Instellingen [voor ongewenste e-mail configureren in Exchange Online-postvakken voor](configure-junk-email-settings-on-exo-mailboxes.md)instructies.

Wanneer berichten met succes worden geblokkeerd vanwege de lijst Geblokkeerde afzenders van een gebruiker, bevat het koptekstveld **X-Forefront-Antispam-Report** de waarde `SFV:BLK` .

> [!NOTE]
> Als de ongewenste berichten nieuwsbrieven zijn van een gerenommeerde en herkenbare bron, is het afmelden van de e-mail een andere optie om te voorkomen dat de gebruiker de berichten ontvangt.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Geblokkeerde afzenderlijsten of geblokkeerde domeinlijsten gebruiken

Wanneer meerdere gebruikers worden beïnvloed, is het bereik breder, dus de volgende beste optie is geblokkeerde afzenderlijsten of geblokkeerde domeinlijsten in antispambeleid. Berichten van afzenders op de lijsten worden gemarkeerd als **Spam**en de actie die u hebt ingesteld voor **het** spamfiltervonnis wordt op het bericht uitgevoerd. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

## <a name="use-mail-flow-rules"></a>Regels voor e-mailstromen gebruiken

Als u berichten wilt blokkeren die naar specifieke gebruikers of in de hele organisatie worden verzonden, u regels voor e-mailstromen gebruiken. E-mailstroomregels zijn flexibeler dan lijsten met afzenders of geblokkeerde afzenderdomeinlijsten, omdat ze ook kunnen zoeken naar zoekwoorden of andere eigenschappen in de ongewenste berichten.

Ongeacht de voorwaarden of uitzonderingen die u gebruikt om de berichten te identificeren, configureert u de actie om het spamvertrouwensniveau (SCL) van het bericht in te stellen op 9, wat het bericht een **spam met een hoog vertrouwen**markeert. Zie [Regels voor e-mailstromen gebruiken om de SCL in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie.

> [!IMPORTANT]
> Het is eenvoudig om regels te maken die *overdreven* agressief zijn, dus het is belangrijk dat u alleen de berichten identificeert die u wilt blokkeren met behulp van zeer specifieke criteria. Zorg er ook voor dat u controle op de regel inschakelt en test de resultaten van de regel om ervoor te zorgen dat alles werkt zoals verwacht.

## <a name="use-the-ip-block-list"></a>De IP-bloklijst gebruiken

Als het niet mogelijk is om een van de andere opties te gebruiken om een afzender te blokkeren, moet u *alleen de* IP-bloklijst gebruiken in het beleid voor verbindingsfilter. Zie Het [verbindingsfilterbeleid configureren](configure-the-connection-filter-policy.md)voor meer informatie . Het is belangrijk om het aantal geblokkeerde IP-adressen tot een minimum te beperken, dus het blokkeren van volledige IP-adresbereiken wordt *niet* aanbevolen.

U moet *vooral* voorkomen dat IP-adresbereiken worden toegevoegd die behoren tot consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuren, en ervoor zorgen dat u de lijst met geblokkeerde IP-adressen bekijkt als onderdeel van regulier onderhoud.
