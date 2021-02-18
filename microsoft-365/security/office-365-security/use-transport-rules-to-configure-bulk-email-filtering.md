---
title: Regels voor de e-mailstroom gebruiken om bulk-e-mail te filteren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Beheerders kunnen lezen hoe ze regels voor de e-mailstroom (transportregels) kunnen gebruiken om bulkmail (grijze e-mail) te identificeren en te filteren in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8030d21d414cb38769a6831391262fa3798a8838
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287291"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken gebruikt EOP antispambeleidsregels (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om inkomende berichten te scannen op spam en bulkmail (ook wel grijze e-mail genoemd). Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u meer opties wilt voor het filteren van bulkmail, kunt u regels voor de e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of woordgroepen die vaak worden gevonden in bulkmail, en deze berichten markeren als spam. Zie wat is het verschil tussen ongewenste e-mail en [bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) en het niveau van bulksgeadresseren [in EOP](bulk-complaint-level-values.md)voor meer informatie over bulkmail.

In dit onderwerp wordt uitgelegd hoe u deze regels voor de e-mailstroom maakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen krijgen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordbeheer.**

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [De lijst met leden in rollengroepen wijzigen met het EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Als u het Exchange-beheercentrum wilt openen in Exchange Online, gaat u naar [het Exchange-beheercentrum in Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Zie het Exchange-beheercentrum in de zelfstandige EOP om het Exchange-beheercentrum [te openen in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor de e-mailstroom in Exchange Online en de zelfstandige EOP:

  - [E-mailstroomregels (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- De lijst met woorden en tekstpatronen die worden gebruikt om bulkmail in de voorbeelden te identificeren, is niet volledig. u kunt zo nodig items toevoegen en verwijderen. Ze zijn echter wel een goed uitgangspunt.

- De zoekopdracht naar woorden of tekstpatronen in het onderwerp  of andere koptekstvelden in het bericht vindt plaats nadat het bericht is gedecodeerd via de coderingsmethode voor MIME-inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden. U kunt geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de onbewerkte (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.

- Met de volgende procedures wordt een bulkbericht gemarkeerd als spam voor de hele organisatie. U kunt echter nog een voorwaarde toevoegen om deze regels alleen toe te passen op specifieke geadresseerden, zodat u uw filtering op een paar, zeer gerichte gebruikers kunt toepassen, terwijl de rest van uw gebruikers (die voornamelijk de bulk-e-mail ontvangen waar ze zich voor hebben aangemeld) niet van invloed zijn.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Het EAC gebruiken om regels voor de e-mailstroom te maken waarin bulk-e-mail wordt gefilterd

1. Ga in het EAC naar **Regels voor e-mailstroom.** \> 

2. Klik **op het** pictogram Toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** voer een unieke, beschrijvende naam voor de regel in.

   - Klik **op Meer opties.**

   - **Pas deze regel toe als:** Configureer een van de volgende instellingen om te zoeken naar inhoud in berichten met behulp van reguliere expressies (RegEx) of woorden of woordgroepen:

     - **Het onderwerp of de lichaam** \> **onderwerp** of de teksttekst komt  overeen met deze tekstpatronen: Voer in het dialoogvenster  Woorden of woordgroepen opgeven dat wordt weergegeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Als u een item wilt bewerken, selecteert u dit en klikt u op **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken. Als u een vermelding wilt verwijderen, selecteert u deze en klikt u **op pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

       Klik op OK wanneer u **klaar bent.**

     - **Het onderwerp of de lichaam** \> **onderwerp** of de tekst bevat een  van deze woorden: Voer in het dialoogvenster Woorden  of woordgroepen opgeven die worden weergegeven een van de volgende waarden in, klik op Pictogram toevoegen en herhaal dit totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

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

      Als u een item wilt bewerken, selecteert u dit en klikt u op **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken. Als u een vermelding wilt verwijderen, selecteert u deze en klikt u **op pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

       Klik op OK wanneer u **klaar bent.**

   - **Ga als volgt te** werk: selecteer **Wijzigen van de berichteigenschappen** \> **om het betrouwbaarheidsniveau voor ongewenste e-mail in te stellen.** Configureer een van de volgende instellingen in het dialoogvenster **SCL** opgeven dat wordt weergegeven:

     - Als u berichten wilt markeren **als Spam,** **selecteert u 6.** De actie die u hebt  geconfigureerd voor spamfilters in uw antispambeleid wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

     - Selecteer **9** om berichten **te markeren als Zeer vertrouwelijk spam.** De actie die u hebt  geconfigureerd voor een spamfilter met hoge betrouwbaarheid in uw antispambeleid wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

    Zie Spam-betrouwbaarheidsniveau [(SCL) in EOP voor meer informatie over SCL-waarden.](spam-confidence-levels.md)

   Wanneer u klaar bent, klikt u op **Opslaan**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell gebruiken om regels voor de e-mailstroom te maken waarin bulk-e-mail wordt gefilterd

Gebruik de volgende syntaxis om een of beide regels voor de e-mailstroom te maken (reguliere expressies versus woorden):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam Bulk-e-mailfiltering - RegEx, waarin dezelfde lijst met reguliere expressies uit eerder in het onderwerp wordt gebruikt om berichten in te stellen als **Spam.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam Bulkmail filteren - Woorden. Hierbij wordt dezelfde lijst met woorden uit eerder in het onderwerp gebruikt om berichten in te stellen als Zeer **vertrouwelijkheidspam.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u regels voor de e-mailstroom hebt geconfigureerd voor het filteren van bulk-e-mail, gaat u op een van de volgende stappen te werk:

- Ga in het EAC naar Regels voor **e-mailstroom** selecteer de regel klik op het pictogram \>  \> Bewerken en \> controleer de  ![ ](../../media/ITPro-EAC-EditIcon.png) instellingen.

- Vervang in PowerShell door de naam van de regel en voer de volgende opdracht \<Rule Name\> uit om de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Verzend vanuit een extern account een testbericht naar een getroffen geadresseerde die een van de zinnen of tekstpatronen bevat en controleer de resultaten.
