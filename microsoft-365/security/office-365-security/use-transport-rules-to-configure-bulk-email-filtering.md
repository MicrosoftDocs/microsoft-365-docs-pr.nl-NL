---
title: Regels voor e-mailstroom gebruiken om bulke-mailfiltering in Exchange Online Protection te configureren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze regels voor e-mailstromen kunnen gebruiken in Exchange Online Protection voor bulke-mailfiltering.
ms.openlocfilehash: 81b0f4cc58d712c3a1c1e09dab02d1c6f56cb69d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809173"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Regels voor e-mailstroom gebruiken om bulke-mailfiltering in Exchange Online Protection te configureren

U bedrijfsbrede inhoudsfilters instellen voor spam en bulke-mail met behulp van het standaardbeleid voor spaminhoud. Bekijk [Het beleid voor spamfilters](configure-your-spam-filter-policies.md) configureren en het beleid voor [inhoudsfilter instellen](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) over het instellen van het beleid voor inhoudsfilter.

Als u meer opties wilt om bulkberichten te filteren, u regels voor e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of -zinnen die vaak in bulke-mails worden gevonden. Elk bericht met deze kenmerken wordt gemarkeerd als spam. Het gebruik van deze regels kan helpen de hoeveelheid ongewenste bulke-mail die uw organisatie ontvangt te verminderen.

> [!IMPORTANT]
> Voordat u de regels voor de e-mailstroom maakt die dit onderwerp hebben gedocumenteerd, [Bulk Complaint Level values](bulk-complaint-level-values.md)raden we u aan eerst te lezen [Wat is het verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)<br>
> De volgende procedures markeren een bericht als spam voor uw hele organisatie. U echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke ontvangers in uw organisatie. Op deze manier kunnen de agressieve instellingen voor bulke-mailfiltering van toepassing zijn op een paar gebruikers die zeer gericht zijn, terwijl de rest van uw gebruikers (die meestal de bulke-mail krijgen waarvoor ze zich hebben aangemeld) niet worden beïnvloed.

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Een e-mailstroomregel maken om bulke-mailberichten te filteren op basis van tekstpatronen

1. Ga in het Exchange-beheercentrum (EAC) naar **Regels voor de mailstroom** \> **.**

2. Klik **Add** ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram Toevoegen toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.

3. Geef een naam voor de regel op.

4. Klik op **Meer** ![](../../media/ITPro-EAC-MoreOptionsIcon.png)opties Pictogram Meer opties . Selecteer onder **Toepassen van deze regel als**u Het onderwerp of de **hoofdtekst** \> selecteert **die overeenkomt met deze tekstpatronen**.

5. Voeg in het dialoogvenster **Woorden of zinnen** opgeven de volgende reguliere expressies toe die vaak worden gevonden in bulke-mails, één voor één, en klik op **OK** wanneer u klaar bent:

   - `If you are unable to view the content of this email\, please`

   - `\>(safe )?unsubscribe( here)?\</a\>`

   - `If you do not wish to receive further communications like this\, please`

   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

   - `To stop receiving these+emails\:http\://`

   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

   - `no longer (wish )?(to )?(be sent|receive) w+ email`

   - `If you are unable to view the content of this email\, please click here`

   - `To ensure you receive (your daily deals|our e-?mails)\, add`

   - `If you no longer wish to receive these emails`

   - `to change your (subscription preferences|preferences or unsubscribe)`

   - `click (here to|the) unsubscribe`

   De bovenstaande lijst is niet een uitputtende set van regelmatige uitdrukkingen gevonden in bulk e-mails; meer kan worden toegevoegd of verwijderd als dat nodig is. Het is echter een goed uitgangspunt.

   De zoekopdracht naar woorden of tekstpatronen in het onderwerp of andere kopvelden in het bericht vindt plaats *nadat* het bericht is gedecodeerd uit de mime-methode voor het coderen van inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden. U geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de onbewerkte (doorgaans Base64) gecodeerde waarden van het onderwerp of andere kopvelden in berichten.

6. Selecteer onder **Ga als volgt**de optie De \> eigenschappen van het bericht **wijzigen** **en stel het betrouwbaarheidsniveau voor spam (SCL)** in .

7. Stel in het dialoogvenster **SCL** op **5,** **6**of **9**op op opgeven en klik op **ok**.

   Als u de SCL instelt op 5 of 6, neemt de **actie Spam in** beslag, terwijl het instellen van de SCL op 9 de **spamactie met veel vertrouwen** neemt, zoals geconfigureerd in het beleid voor inhoudsfilter. De service voert de actieset uit in het beleid voor inhoudsfilter. De standaardactie is om het bericht te leveren aan de map Ongewenste e-mail van de geadresseerden, maar verschillende acties kunnen worden geconfigureerd zoals beschreven in [Het beleid voor spamfilters](configure-your-spam-filter-policies.md)configureren .

   Als uw geconfigureerde actie is om het bericht in quarantaine te plaatsen in plaats van het te verzenden naar de map Ongewenste e-mail van de geadresseerden, wordt het bericht verzonden naar de beheerder quarantaine als een e-mailstroomregel overeenkomen, en het zal niet beschikbaar zijn in de quarantaine van de eindgebruiker of via de eindgebruiker spammeldingen.

   Zie [Vertrouwensniveaus](spam-confidence-levels.md)voor spam voor meer informatie over SCL-waarden in de service.

8. Sla de regel op.

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Een e-mailstroomregel maken om bulke-mailberichten te filteren op basis van zinnen

1. Ga in de EAC naar **Mail flow** \> **Rules**.

2. Klik **Add** ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram Toevoegen toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.

3. Geef een naam voor de regel op.

4. Klik **op Meer opties**. Selecteer onder **Toepassen van deze regel als**u Het onderwerp of de **instantie** \> **of het lichaam een van deze woorden bevat**.

5. Voeg in het dialoogvenster **Woorden of zinnen** op te geven de volgende zinnen die vaak worden gevonden in bulke-mails, één voor één, toe en klik op **ok** wanneer u klaar bent:

   - `to change your preferences or unsubscribe`

   - `Modify email preferences or unsubscribe`

   - `This is a promotional email`

   - `You are receiving this email because you requested a subscription`

   - `click here to unsubscribe`

   - `You have received this email because you are subscribed`

   - `If you no longer wish to receive our email newsletter`

   - `to unsubscribe from this newsletter`

   - `If you have trouble viewing this email`

   - `This is an advertisement`

   - `you would like to unsubscribe or change your`

   - `view this email as a webpage`

   - `You are receiving this email because you are subscribed`

   Deze lijst is niet een uitputtende set van zinnen gevonden in bulk e-mails; meer kan worden toegevoegd of verwijderd als dat nodig is. Het is echter een goed uitgangspunt.

6. Selecteer onder **Ga als volgt**de optie De \> eigenschappen van het bericht **wijzigen** **en stel het betrouwbaarheidsniveau voor spam (SCL)** in .

7. Stel in het dialoogvenster **SCL** op **5,** **6**of **9**op op opgeven en klik op **ok**.

   Als u de SCL instelt op 5 of 6, neemt de **actie Spam in** beslag, terwijl het instellen van de SCL op 9 de **spamactie met veel vertrouwen** neemt, zoals geconfigureerd in het beleid voor inhoudsfilter. De service voert de actieset uit in het beleid voor inhoudsfilter. De standaardactie is om het bericht te leveren aan de map Ongewenste e-mail van de geadresseerden, maar verschillende acties kunnen worden geconfigureerd zoals beschreven in [Het beleid voor spamfilters](configure-your-spam-filter-policies.md)configureren .

   Als uw geconfigureerde actie is om het bericht in quarantaine te plaatsen in plaats van het te verzenden naar de map Ongewenste e-mail van de geadresseerden, wordt het bericht verzonden naar de beheerder quarantaine als een e-mailstroomregel overeenkomen, en het zal niet beschikbaar zijn in de quarantaine van de eindgebruiker of via de eindgebruiker spammeldingen.

   Zie [Vertrouwensniveaus](spam-confidence-levels.md)voor spam voor meer informatie over SCL-waarden in de service.

8. Sla de regel op.

## <a name="for-more-information"></a>Voor meer informatie

[Wat is het verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Waarden op bulkklachtenniveau](bulk-complaint-level-values.md)

[Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)

[Geavanceerde opties voor spamfilter](advanced-spam-filtering-asf-options.md)
