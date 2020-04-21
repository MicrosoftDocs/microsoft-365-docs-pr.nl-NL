---
title: Regels voor e-mailstromen gebruiken om bulke-mail te filteren in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Beheerders kunnen leren hoe u regels voor e-mailstroom gebruiken in Exchange Online Protection voor het filteren van bulke-mail.
ms.openlocfilehash: 229a66658e041be737efbc4cbb7c36ba667d3aed
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631071"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>Regels voor e-mailstromen gebruiken om bulke-mail te filteren in Office 365

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection(EOP)-klant zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook bekend als beleid voor spamfilters of inhoudsfilterbeleid) om binnenkomende berichten te scannen op spam en bulkmail (ook wel grijs mail genoemd). Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

Als u meer opties wilt filteren voor bulkmail, u regels voor e-mailstromen (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of zinnen die vaak in bulkmail worden gevonden en deze berichten markeren als spam. Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) en [Bulk klachtenniveau (BCL) in Office 365](bulk-complaint-level-values.md)voor meer informatie over bulkmail.

In dit onderwerp wordt uitgelegd hoe deze regels voor e-mailstroom worden gemaakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen in Exchange Online krijgen toegewezen voordat u deze procedures uitvoeren. U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.** Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .

- Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)als u de EAC in Exchange Online wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en zelfstandige EOP:

  - [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregels (predicaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- De lijst met woorden en tekstpatronen die worden gebruikt om bulkpost in de voorbeelden te identificeren, is niet volledig; u items indien nodig toevoegen en verwijderen. Ze zijn echter een goed uitgangspunt.

- Het zoeken naar woorden of tekstpatronen in de onderwerp- of andere koptekstvelden in het bericht vindt plaats *nadat* het bericht is gedecodeerd vanuit de MIME-inhoudsoverdrachtcoderingsmethode die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden. U geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de ruwe (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.

- De volgende procedures markeren een bulkbericht als spam voor uw hele organisatie. U echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke ontvangers, zodat u agressieve filtering gebruiken op een paar, zeer gerichte gebruikers, terwijl de rest van uw gebruikers (die meestal de bulke-mail krijgen waarvoor ze zich hebben aangemeld) geen invloed hebben.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>De EAC gebruiken om regels voor e-mailstromen te maken die bulke-mail filteren

1. Ga in de EAC naar **Mail flow** \> **Rules**.

2. Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **vervolgens Een nieuwe regel maken**.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam:** Voer een unieke, beschrijvende naam voor de regel in.

   - Klik **op Meer opties**.

   - **Pas deze regel toe als:** Een van de volgende instellingen configureren om inhoud in berichten te zoeken met behulp van reguliere expressies (RegEx) of woorden of zinnen:

     - **Het onderwerp of het onderwerp** \> **of de hoofdtekst komt overeen met deze tekstpatronen:** voer in](../../media/ITPro-EAC-AddIcon.png)het dialoogvenster Woorden of zinnen **opgeven** dat wordt weergegeven een van de volgende waarden in, **klik** ![op Pictogram toevoegen en herhaal totdat u alle waarden hebt ingevoerd.

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

      Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken . Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .

       Klik op **OK**als u klaar bent.

     - **Het onderwerp of het onderwerp** \> **of de hoofdtekst bevat een van deze woorden:** Voer in het dialoogvenster](../../media/ITPro-EAC-AddIcon.png)Woorden of zinnen **opgeven** dat wordt weergegeven een van de volgende waarden in, **klik** ![op Pictogram toevoegen en herhaal totdat u alle waarden hebt ingevoerd.

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

      Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken . Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .

       Klik op **OK**als u klaar bent.

   - **Ga als volgt**te werk: Selecteer **De eigenschappen** \> van het bericht **wijzigen stel het spamvertrouwensniveau (SCL) in.** Configureer in het dialoogvenster **SCL opgeven** dat wordt weergegeven een van de volgende instellingen:

     - Als u berichten als **spam**wilt markeren, selecteert u **6**. De actie die u hebt **Spam** ingesteld voor spamfiltervonnissen in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**

     - Om berichten te markeren als **Spam met een hoog vertrouwen** selecteert u **9**. De actie die u hebt geconfigureerd voor spamfilteringsvonnissen met **een hoog vertrouwen** in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

    Zie [SCL (Spam confidence level) in Office 365](spam-confidence-levels.md)voor meer informatie over SCL-waarden.

   Klik op **Opslaan** als u klaar bent

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell gebruiken om regels voor e-mailstromen te maken die bulke-mail filteren

Gebruik de volgende syntaxis om een of beide regels voor e-mailstromen (reguliere expressies versus woorden) te maken:

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulk e-mailfiltering - RegEx' die dezelfde lijst met reguliere expressies van eerder in het onderwerp gebruikt om berichten in te stellen als **Spam.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulk e-mailfiltering - Woorden' die dezelfde lijst met woorden van eerder in het onderwerp gebruikt om berichten in te stellen als **spam met een hoog vertrouwen.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga een van de volgende stappen uit om te controleren of u regels voor e-mail hebt geconfigureerd om bulke-mail te filteren:

- Ga in de EAC naar **EAC-regels** \> **Rules** \> en selecteer](../../media/ITPro-EAC-EditIcon.png)de regel \> klik op Pictogram Bewerken **bewerken** ![en controleer de instellingen.

- Vervang in \<PowerShell\> regelnaam door de naam van de regel en voer de volgende opdracht uit om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Stuur vanuit een extern account een testbericht naar een getroffen ontvanger die een van de zinnen of tekstpatronen bevat en verifieer de resultaten.
