---
title: Regels voor e-mailstroom gebruiken om bulke-mail te filteren
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
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (transportregels) kunnen gebruiken om bulkmail (grijze e-mail) te identificeren en te filteren in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 860c9a1af2cb560c4fd966b303501686a1cbfea7
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613310"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam en bulkmail (ook wel grijze e-mail genoemd). Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u meer opties wilt om bulkmail te filteren, u regels voor e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of zinnen die vaak in bulkpost worden gevonden en deze berichten als spam markeren. Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail en](what-s-the-difference-between-junk-email-and-bulk-email.md) [bulkklachtniveau (BCL) in EOP](bulk-complaint-level-values.md)voor meer informatie over bulkmail.

In dit onderwerp wordt uitgelegd hoe u deze regels voor e-mailstroom maakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen voordat u deze procedures uitvoeren:

  - Zie in Exchange Online de vermelding 'E-mailstroom' in [Functiemachtigingen in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)
  
  - In standalone EOP hebt u standaard de rol Transportregels nodig, die standaard is toegewezen aan de rollen OrganizationManagement, ComplianceManagement en RecordsManagement. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.

- Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om de EAC in Exchange Online te openen. Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om de EAC in standalone EOP te openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en standalone EOP:

  - [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties van de mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- De lijst met woorden en tekstpatronen die worden gebruikt om bulkmail in de voorbeelden te identificeren, is niet volledig; u indien nodig vermeldingen toevoegen en verwijderen. Ze zijn echter een goed uitgangspunt.

- Het zoeken naar woorden of tekstpatronen in het onderwerp of andere koptekstvelden in het bericht vindt plaats *nadat* het bericht is gedecodeerd van de MIME-methode voor inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden. U geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de ruwe (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.

- De volgende procedures markeren een bulkbericht als spam voor uw hele organisatie. U echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke ontvangers, zodat u agressieve filtering gebruiken op een paar, zeer gerichte gebruikers, terwijl de rest van uw gebruikers (die meestal de bulke-mail krijgen waarvoor ze zich hebben aangemeld) geen invloed hebben gehad.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>De EAC gebruiken om regels voor e-mailstroom te maken die bulke-mail filteren

1. Ga in de EAC naar **Regels voor e-mailstromen** \> **Rules**.

2. Klik **op** ![ pictogram Toevoegen en selecteer ](../../media/ITPro-EAC-AddIcon.png) **vervolgens Een nieuwe regel maken**.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam**: Voer een unieke, beschrijvende naam voor de regel in.

   - Klik op **Meer opties**.

   - **Deze regel toepassen als:** Een van de volgende instellingen configureren om inhoud in berichten te zoeken met behulp van reguliere expressies (RegEx) of woorden of zinnen:

     - **Het onderwerp of het lichaam** \> **onderwerp of hoofdtekst komt overeen met deze tekstpatronen:** voer in het dialoogvenster **Woorden of zinnen opgeven** een van de volgende waarden in, klik op Pictogram **toevoegen** en herhaal totdat u alle waarden ![ hebt ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

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

      Als u een item wilt bewerken, selecteert u het item en **klikt** u op ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken . Als u een item wilt **Remove** verwijderen, selecteert u deze en klikt u op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

       Klik op **OK**als u klaar bent.

     - **Het onderwerp of het lichaam** \> **onderwerp of hoofdtekst bevat een van deze woorden:** Voer in het dialoogvenster **Woorden of zinnen opgeven** een van de volgende waarden in, klik op Pictogram **toevoegen** en herhaal totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

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

      Als u een item wilt bewerken, selecteert u het item en **klikt** u op ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken . Als u een item wilt **Remove** verwijderen, selecteert u deze en klikt u op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

       Klik op **OK**als u klaar bent.

   - **Ga als volgt te**werk : Selecteer **De berichteigenschappen** \> **wijzigen, het spamvertrouwensniveau (SCL) instellen.** Configureer in het dialoogvenster **SCL opgeven** dat wordt weergegeven een van de volgende instellingen:

     - Als u berichten als **spam wilt**markeren, selecteert u **6**. De actie die u hebt geconfigureerd voor **het** filteren van spam in uw antispambeleid wordt toegepast op de berichten (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**

     - Als u berichten markeert als **spam met een hoog vertrouwen,** selecteert u **9**. De actie die u hebt geconfigureerd voor uitspraken met **een hoog vertrouwensspamfiltering** in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**

    Zie [Spam confidence level (SCL) in EOP voor](spam-confidence-levels.md)meer informatie over SCL-waarden.

   Klik op **Opslaan** als u klaar bent

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell gebruiken om regels voor e-mailstroom te maken die bulke-mail filteren

Gebruik de volgende syntaxis om een of beide regels voor de e-mailstroom (reguliere expressies versus woorden) te maken:

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

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u regels voor e-mailstromen hebt geconfigureerd om bulke-mail te filteren, voert u een van de volgende stappen uit:

- Ga in de EAC naar **E-mailstroomregels** \> **Rules** \> selecteer de regel \> klik op **Edit** ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken en controleer de instellingen.

- Vervang in PowerShell \<Rule Name\> de naam van de regel en voer de volgende opdracht uit om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Verzend vanuit een extern account een testberichten naar een getroffen ontvanger die een van de zinnen of tekstpatronen bevat en verifieer de resultaten.
