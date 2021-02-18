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
description: Beheerders kunnen meer informatie krijgen over de beschikbare en voorkeursopties voor het blokkeren van inkomende berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c95b49db811807a0cb46dce5363b8ae2dbe5602
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287279"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Lijsten met geblokkeerde afzenders maken in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken biedt EOP verschillende manieren om e-mail van ongewenste afzenders te blokkeren. Deze opties zijn onder andere Geblokkeerde afzenders in Outlook, lijsten met geblokkeerde afzenders of lijsten met geblokkeerde domeinen in antispambeleid, Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd) en de lijst met geblokkeerde IP-adressen (verbindingsfiltering). U kunt deze opties gezamenlijk zien als lijsten _met geblokkeerde afzenders._

De beste methode om afzenders te blokkeren, is afhankelijk van de omvang van de impact. Voor één gebruiker kan de juiste oplossing geblokkeerde afzenders van Outlook zijn. Voor veel gebruikers is een van de andere opties meer geschikt. De volgende opties worden gerangschikt op bereik van invloed en breadth. De lijst gaat van smal naar ruim, maar *lees de details voor* volledige aanbevelingen.

1. Geblokkeerde afzenders in Outlook (de lijst met geblokkeerde afzenders die in elk postvak is opgeslagen)

2. Lijsten met geblokkeerde afzenders of lijsten met geblokkeerde domeinen (antispambeleid)

3. Regels voor de e-mailstroom

4. De lijst met IP-blokkeringen (verbindingsfiltering)

> [!NOTE]
> Hoewel u instellingen voor blokkering voor de hele organisatie kunt gebruiken om fout-negatieven (gemiste spam) aan te pakken, moet u deze berichten ook naar Microsoft verzenden voor analyse. Als u onwaar-negatieven beheert met behulp van blokkeringslijsten, neemt de administratieve overhead aanzienlijk toe. Als u blokkeringslijsten gebruikt om gemiste spam tegen te gaan, moet u de berichten en bestanden over het onderwerp rapporteren [aan Microsoft](report-junk-email-messages-to-microsoft.md) bij de tijd houden.

U hebt daarentegen ook verschillende opties voor het altijd toestaan van e-mail van specifieke bronnen die lijsten _met veilige afzenders gebruiken._ Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) voor meer informatie.

## <a name="email-message-basics"></a>Basisprincipes van e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud. De envelop met berichten bevat informatie die is vereist voor het verzenden en bezorgen van het bericht tussen SMTP-servers. De inhoud van het bericht bevat berichtkopvelden (gezamenlijk de berichtkop *genoemd)* en de berichttekst. De berichtvelop wordt beschreven in RFC 5321 en de berichtkop wordt beschreven in RFC 5322. Geadresseerden zien de feitelijke berichtvelopop niet, omdat deze wordt gegenereerd door het verzendingsproces voor berichten en niet daadwerkelijk deel uitmaakt van het bericht.

- Het adres (ook wel bekend als het `5321.MailFrom` MAIL **FROM-adres,** de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-verzending van het bericht. Dit e-mailadres wordt  meestal opgenomen in het koptekstveld Retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor het retourpad kan aanwijzen). Als het bericht niet kan worden bezorgd, is het de geadresseerde van het rapport over niet-bezorging (ook wel een NDR- of niet-bezorgdbericht genoemd).

- De afzender (ook wel het Van-adres of P2 genoemd) is het e-mailadres in het veld Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail clients.  

De adressen en de adressen zijn vaak hetzelfde (communicatie tussen twee `5321.MailFrom` `5322.From` personen). Wanneer e-mail echter namens iemand anders wordt verzonden, kunnen de adressen verschillend zijn.

Lijsten met geblokkeerde afzenders en lijsten met geblokkeerde domeinen in antispambeleid in EOP inspecteren zowel de adressen als `5321.MailFrom` `5322.From` de adressen. Geblokkeerde afzenders in Outlook gebruiken alleen het `5322.From` adres.

## <a name="use-outlook-blocked-senders"></a>Geblokkeerde afzenders in Outlook gebruiken

Wanneer slechts een klein aantal gebruikers ongewenste e-mail heeft ontvangen, kunnen gebruikers of beheerders de e-mailadressen van de afzender toevoegen aan de lijst met geblokkeerde afzenders in het postvak. Zie Instellingen voor ongewenste [e-mail configureren in Postvakken van Exchange Online voor instructies.](configure-junk-email-settings-on-exo-mailboxes.md)

Wanneer berichten zijn geblokkeerd vanwege de lijst met geblokkeerde afzenders van een gebruiker, bevat het veld **X-Forefront-Antispam-Report** de `SFV:BLK` waarde.

> [!NOTE]
> Als de ongewenste berichten nieuwsbrieven zijn vanuit een betrouwbare en herkenbare bron, kunt u zich afmelden bij de e-mail om te voorkomen dat de gebruiker de berichten ontvangt.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten gebruiken

Wanneer meerdere gebruikers worden beïnvloed, is het bereik breder, dus de beste optie is lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten in antispambeleid. Berichten van afzenders op de lijsten worden gemarkeerd als **Spam** en de actie die u hebt geconfigureerd voor de **spamfilteractie** wordt op het bericht gebaseerd. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

## <a name="use-mail-flow-rules"></a>Regels voor de e-mailstroom gebruiken

Als u berichten wilt blokkeren die naar specifieke gebruikers of binnen de hele organisatie zijn verzonden, kunt u regels voor de e-mailstroom gebruiken. Regels voor de e-mailstroom zijn flexibeler dan lijsten met geblokkeerde afzenders of geblokkeerde domeinlijsten van afzenders, omdat ze ook kunnen zoeken naar trefwoorden of andere eigenschappen in ongewenste berichten.

Ongeacht de voorwaarden of uitzonderingen die u gebruikt voor het identificeren van de berichten, configureert u de actie om het betrouwbaarheidsniveau voor ongewenste e-mail van het bericht in te stellen op 9, waardoor het bericht in hoge mate spam **is.** Zie Regels voor de [e-mailstroom gebruiken om de SCL in](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)berichten in te stellen voor meer informatie.

> [!IMPORTANT]
> Het is eenvoudig om regels  te maken die te agressief zijn, dus het is belangrijk dat u alleen de berichten identificeert die u wilt blokkeren met behulp van zeer specifieke criteria. Zorg er ook voor dat u controle op de regel inschakelen en de resultaten van de regel test om ervoor te zorgen dat alles werkt zoals verwacht.

## <a name="use-the-ip-block-list"></a>De lijst met IP-blokkeringen gebruiken

Als het niet mogelijk is om een van de andere opties te gebruiken om een afzender te *blokkeren,* moet u de LIJST met IP-blokkeringen gebruiken in het verbindingsfilterbeleid. Zie Het verbindingsfilterbeleid [configureren voor meer informatie.](configure-the-connection-filter-policy.md) Het is belangrijk om het aantal geblokkeerde IP-adressen tot een minimum te beperken, dus het blokkeren van volledige IP-adresbereiken wordt *niet* aanbevolen.

Het  is beter om met name geen IP-adresbereiken toe te voegen die behoren tot consumentenservices (bijvoorbeeld outlook.com) of gedeelde infrastructuur en ervoor te zorgen dat u de lijst met geblokkeerde IP-adressen bekijkt als onderdeel van regulier onderhoud.
