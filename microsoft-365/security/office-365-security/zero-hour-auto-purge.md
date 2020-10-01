---
title: Automatisch opschonen van 0 uur (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met de functie voor het automatisch wissen van rijen (ZAP) bezorgde berichten in een Exchange Online-postvak naar de map Ongewenste E-mail verplaatst, en de map Ongewenste E-mail naar een andere map.
ms.openlocfilehash: 31e546ddf6e93ed0a265aef3737182cf30ae5a95
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327973"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-Hour auto opgeschoond (ZAP) in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Basisfuncties van ZAP

In Microsoft 365-organisaties met postvakken in Exchange Online is de functie voor het automatisch wissen van Zero Hour (ZAP) een functie voor e-mail beveiliging waarmee u schadelijke malafide, spam-en malware-berichten die al zijn afgeleverd, kunt detecteren en neutraliseren die al zijn afgeleverd voor Exchange Online-postvakken.

ZAP werkt niet in zelfstandige Exchange Online Protection (EOP)-omgevingen die on-premises Exchange-postvakken beschermen.

## <a name="how-zap-works"></a>De werking van ZAP

Spam en malware-handtekeningen worden dagelijks bijgewerkt in de service voor eenmalige aanmelding. Gebruikers kunnen echter nog steeds kwaadaardige berichten ontvangen voor tal van redenen, ook als de inhoud is gewapend na levering aan gebruikers. ZAP-adressen dit probleem door continu de updates van de spam-en malware-ondertekening te controleren in de service. ZAP kan berichten zoeken en verwijderen die al aanwezig zijn in het postvak van een gebruiker.

De actie ZAP is naadloos voor de gebruiker; de persoon ontvangt geen meldingen als er een bericht wordt gevonden en verplaatst.

[Lijsten met veilige afzenders](create-safe-sender-lists-in-office-365.md), regels voor e-mail stroom (ook wel bekend als de transportregels), regels voor Postvak in of andere filters hebben voorrang boven zap. Vergelijkbaar met wat er gebeurt in de e-mail stroom, betekent dit dat zelfs als de service de bezorgings bericht voor ZAP controleert, het bericht niet is afgestemd op de lijst met veilige afzenders. Dit is een andere reden om te voorkomen dat u berichten configureert om het filteren te omzeilen.

### <a name="malware-zap"></a>Malware ZAP

Voor **gelezen of ongelezen berichten** die malware bevatten na levering, wordt ZAP gequarantined en wordt het bericht met de bijlage met schadelijke software gevonden. Alleen beheerders kunnen malware-berichten van Quarantine weergeven en beheren.

Malware ZAP is standaard ingeschakeld in beleid voor anti-malware. Zie voor meer informatie [anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phishing ZAP

Voor **gelezen of ongelezen berichten** die als aflezing na ontvangst worden geïdentificeerd, is de hoeveelheid ZAP afhankelijk van de actie die is geconfigureerd voor het filteren van **phishing-e-mail** verdict in het toepasselijke antispambeleid. In de volgende lijst vindt u een beschrijving van de beschikbare verdict-acties voor het filteren van een filter en de bijbehorende ZAP-resultaten.

- **Door onderwerpregel met tekst** **toevoegen**: zap hoeft geen actie te ondernemen voor het bericht.

- **Bericht verplaatsen naar ongewenste**E-mail: zap verplaatst het bericht naar de map Ongewenste e-mail, mits de regel voor ongewenste e-mail is ingeschakeld in het postvak (dit is standaard ingeschakeld). Zie voor meer informatie [instellingen voor ongewenste E-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Bericht omleiden naar e-mailadres**, **bericht verwijderen**, **quarantaine bericht**: zap quarantinet het bericht.

Standaard is Phish ZAP ingeschakeld in Antispambeleid en de standaardactie voor het filteren van **phishingberichten via e-mail** in de verdict is **quarantaine bericht**, wat betekent dat met phishing ZAP standaard het bericht wordt gequarantined.

Zie [Antispambeleid in Microsoft 365 configureren](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van spam filtering Verdicts.

### <a name="spam-zap"></a>Spam ZAP

Bij **ongelezen berichten** die als spam na ontvangst worden geïdentificeerd, is de Zap-uitslag afhankelijk van de actie die is geconfigureerd voor het **spam** filter verdict in het toepasselijke antispambeleid. In de volgende lijst vindt u de beschikbare verdict-acties voor het filteren van ongewenste e-mail en de mogelijke ZAP-resultaten.

- **Door onderwerpregel met tekst** **toevoegen**: zap hoeft geen actie te ondernemen voor het bericht.

- **Bericht verplaatsen naar ongewenste**E-mail: zap verplaatst het bericht naar de map Ongewenste e-mail, mits de regel voor ongewenste e-mail is ingeschakeld in het postvak (dit is standaard ingeschakeld). Zie voor meer informatie [instellingen voor ongewenste E-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Bericht omleiden naar e-mailadres**, **bericht verwijderen**, **quarantaine bericht**: zap quarantinet het bericht. Eindgebruikers kunnen hun eigen spamberichten in quarantaine weergeven en beheren.

Spam ZAP is standaard ingeschakeld in Antispambeleid en de standaardactie voor het filteren van **ongewenste** e-mail verstuurt **bericht naar de map**ongewenste e-mail, wat betekent dat ongewenste e-mail standaard **Ongelezen** berichten naar de map Ongewenste e-mail verplaatst.

Zie [Antispambeleid in Microsoft 365 configureren](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van spam filtering Verdicts.

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>ZAP-aandachtspunten voor Office 365 Advanced Threat Protection (Office 365 ATP)

ZAP vervangt geen berichten die zich in het proces bevindt waarin de [dynamische bezorging](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) van de bijlage wordt gecontroleerd, of waar het filteren van malware via malware de bijlage al heeft vervangen door de **malware-waarschuwing Text.txt** bestand. Als het signaal voor phishing of spam wordt ontvangen voor deze typen berichten en het filteren van de verdict in het antispambeleid is ingesteld op het uitvoeren van wat actie op het bericht (verplaatsen naar ongewenste E-mail, omleiden, verwijderen of Quarantine), wordt ZAP standaard ingesteld op de actie ' naar ongewenste E-mail '.

## <a name="how-to-see-if-zap-moved-your-message"></a>Kijken of ZAP uw bericht heeft verplaatst

Als u wilt weten of ZAP uw bericht heeft verplaatst, kunt u het [status rapport van de bedreigings bescherming](view-email-security-reports.md#threat-protection-status-report) of de bedreiging voor de [real-time detectie](threat-explorer.md)gebruiken. Houd er rekening mee dat bij een systeemactie ZAP niet in het auditlogboek voor het Exchange-postvak wordt geregistreerd.

## <a name="zap-faq"></a>VEELGESTELDE VRAGEN OVER ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Wat gebeurt er als een legitiem bericht is verplaatst naar de map Ongewenste E-mail?

U moet het normale rapportageproces voor [onjuiste positieven](report-junk-email-messages-to-microsoft.md)volgen. De enige reden waarom het bericht uit het postvak in naar de map Ongewenste E-mail werd verplaatst, is omdat de service heeft vastgesteld dat het bericht spam of kwaadief was.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Wat moet ik doen als ik de map Quarantine gebruik in plaats van de map Ongewenste e-mail?

ZAP zal actie ondernemen op een bericht op basis van de configuratie van uw Antispambeleid zoals beschreven in dit onderwerp.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Wat moet ik doen als ik veilige afzenders, e-mail stroom regels of lijsten met toegestane/geblokkeerde afzenders gebruik?

De lijst veilige afzenders, e-mail stroom en het blokkeren en toestaan van organisatie-instellingen hebben voorrang. Deze berichten worden uitgesloten van ZAP, aangezien de service wat u hebt geconfigureerd voor het uitvoeren van de service. Dit is een andere reden om te voorkomen dat u berichten configureert om het filteren te omzeilen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Wat gebeurt er als een bericht naar een andere map wordt verplaatst (bijvoorbeeld regels voor Postvak in)?

ZAP werkt nog steeds zo lang het bericht niet is verwijderd, niet is verwijderd, of zo lang dit niet is gebeurd, is de actie niet al toegepast. Als u bijvoorbeeld het beleid voor phishing hebt ingesteld op Quarantine en de gebruiker of beheerder de e-mail al heeft gemaild en de e-mail al heeft ongewenst.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hoe beïnvloedt ZAP-postvakken zich in de wacht?

ZAP zet geen berichten uit de postvakken in de wacht. ZAP kan berichten verplaatsen naar de map Ongewenste E-mail op basis van de actie die is geconfigureerd voor een spam-of phishing-verdict in antispambeleid.

Zie [in-place bewaring en ter plaatse bewaren in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)voor meer informatie over wachtruimten in Exchange Online.
