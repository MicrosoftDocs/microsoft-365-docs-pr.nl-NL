---
title: Regels voor e-mailstroom gebruiken om bulk-e-mail te filteren
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
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (transportregels) kunnen gebruiken om bulkmail (grijze e-mail) te identificeren en te filteren in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8632a0b583ec0457ea1146f0e197321890414ce3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926676"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam en bulkmail (ook wel grijze e-mail genoemd). Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u meer opties wilt om bulkmail te filteren, kunt u regels voor de e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of woordgroepen die vaak worden gevonden in bulkmail en deze berichten markeren als spam. Zie Wat is het [](what-s-the-difference-between-junk-email-and-bulk-email.md) verschil tussen ongewenste e-mail en bulk-e-mail? en Bulk [complaint level (BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over bulkmail.

In dit onderwerp wordt uitgelegd hoe u deze regels voor de e-mailstroom maakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen toegewezen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordsbeheer.**

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [De lijst met leden in rollengroepen wijzigen met het EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie [Exchange-beheercentrum in Exchange Online](/Exchange/exchange-admin-center)om het EAC in Exchange Online te openen. Zie [Exchange-beheercentrum in](exchange-admin-center-in-exchange-online-protection-eop.md)zelfstandige EOP om de EAC in zelfstandige EOP te openen.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over e-mailstroomregels in Exchange Online en zelfstandige EOP:

  - [Regels voor e-mailstroom (transportregels) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mailstroomregel in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- De lijst met woorden en tekstpatronen die worden gebruikt om bulkmail in de voorbeelden te identificeren, is niet volledig. u kunt indien nodig vermeldingen toevoegen en verwijderen. Ze zijn echter een goed beginpunt.

- Het zoeken naar woorden of tekstpatronen in het onderwerp  of andere koptekstvelden in het bericht vindt plaats nadat het bericht is gedecodeerd met de MIME-methode voor inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden. U kunt geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de onbewerkte (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.

- In de volgende procedures wordt een bulkbericht gemarkeerd als spam voor uw hele organisatie. U kunt echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke geadresseerden, zodat u agressieve filtering kunt gebruiken voor een paar zeer gerichte gebruikers, terwijl de rest van uw gebruikers (die meestal de bulk-e-mail ontvangen waar ze zich voor hebben aangemeld) geen invloed hebben.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC gebruiken om regels voor e-mailstroom te maken die bulk-e-mail filteren

1. Ga in het EAC naar **E-mailstroomregels.** \> 

2. Klik **op Pictogram** Toevoegen toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** Voer een unieke, beschrijvende naam in voor de regel.

   - Klik **op Meer opties.**

   - **Pas deze regel toe als**: Configureer een van de volgende instellingen om te zoeken naar inhoud in berichten met gewone expressies (RegEx) of woorden of woordgroepen:

     - **Het onderwerp of de body** \> **onderwerp** of de teksttekst komt  overeen met deze tekstpatronen: Voer in het dialoogvenster  Woorden of woordgroepen opgeven dat wordt weergegeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

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

      Als u een item wilt bewerken, selecteert u deze en klikt **u** op ![ Pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken. Als u een item wilt verwijderen, selecteert u deze en klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

       Wanneer u klaar bent, klikt u op **OK.**

     - **Het onderwerp of de body** \> **onderwerp** of de tekst bevat een  van deze woorden: Voer in het dialoogvenster Woorden  of woordgroepen opgeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

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

      Als u een item wilt bewerken, selecteert u deze en klikt **u** op ![ Pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken. Als u een item wilt verwijderen, selecteert u deze en klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

       Wanneer u klaar bent, klikt u op **OK.**

   - **Ga als volgt te** werk: Selecteer **De eigenschappen van het bericht wijzigen** om \> **het betrouwbaarheidsniveau voor spam (SCL) in te stellen.** Configureer een van de volgende instellingen in het dialoogvenster **SCL** opgeven dat wordt weergegeven:

     - Als u berichten wilt markeren **als Spam,** selecteert u **6**. De actie die u hebt  geconfigureerd voor spamfilters in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).**

     - Als u berichten wilt markeren als **spam met hoog vertrouwen,** **selecteert u 9**. De actie die u hebt  geconfigureerd voor het filteren van spam met hoge betrouwbaarheid in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

    Zie Betrouwbaarheidsniveau [spam (SCL) in EOP voor meer informatie over SCL-waarden.](spam-confidence-levels.md)

   Wanneer u klaar bent, klikt u op **Opslaan**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell gebruiken om regels voor e-mailstroom te maken die bulk-e-mail filteren

Gebruik de volgende syntaxis om een of beide regels voor de e-mailstroom (gewone expressies versus woorden) te maken:

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam Bulk-e-mailfiltering - RegEx, waarin dezelfde lijst met reguliere expressies uit eerder in het onderwerp wordt gebruikt om berichten in te stellen als **Spam.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulksgewijs filteren van e-mail - Woorden' waarin dezelfde lijst met woorden uit eerder in het onderwerp wordt gebruikt om berichten in te stellen als spam **met hoog vertrouwen.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u regels voor e-mailstroom hebt geconfigureerd om bulk-e-mail te filteren, gaat u als volgt te werk:

- Ga in het EAC naar **E-mailstroomregels** en selecteer de regel op Pictogram Bewerken \>  \> bewerken en \> controleer de  ![ ](../../media/ITPro-EAC-EditIcon.png) instellingen.

- Vervang in PowerShell door de naam van de regel en voer de volgende \<Rule Name\> opdracht uit om de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Verzend vanuit een extern account een testberichten naar een getroffen geadresseerde die een van de zinnen of tekstpatronen bevat en controleer de resultaten.