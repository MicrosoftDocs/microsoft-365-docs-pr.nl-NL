---
title: Regels voor e-mail stroom gebruiken om bulk berichten te filteren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over het gebruik van regels voor e-mail stroom (transportregels) voor het identificeren en filteren van bulkmail (grijze e-mail) in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f88358973648846d650700bb5939c052851c789
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615634"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP-organisaties zonder Exchange Online-postvakken), EOP maakt gebruik van Antispambeleid (ook wel een spamfilter beleid of inhouds filter beleid) om binnenkomende berichten te scannen voor spam en bulkmail (ook wel grijze e-mail genoemd). Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u meer opties voor bulkmail wilt filteren, kunt u e-mail stroom regels (ook wel transport-regels genoemd) maken om te zoeken naar tekstpatronen of woordgroepen die vaak worden gevonden in bulkmail en om die berichten als spam te markeren. Zie voor meer informatie over bulkmail [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) en [bulk klachten niveau (BCL) in EOP](bulk-complaint-level-values.md).

In dit onderwerp wordt uitgelegd hoe u deze regels voor de e-mail stroom maakt in het Exchange Admin Center (SBV) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen hebben voordat u de volgende procedures kunt uitvoeren:

  - In Exchange Online raadpleegt u de invoer voor de e-mail stroom in [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).

  - In zelfstandige EOP hebt u de rol Transport regel nodig, die standaard is toegewezen aan de rollen de organizationmanagement, ComplianceManagement en RecordsManagement. Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om het SBV te openen in Exchange Online. Als u het Exchange-Beheercentrum in standalone EOP wilt openen, raadpleegt u [Exchange Admin Center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mail stroom in Exchange Online en zelfstandige EOP:

  - [Regels voor e-mail stroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- De lijst met woorden en tekstpatronen die worden gebruikt voor het identificeren van bulkmail in de voorbeelden zijn niet volledig; u kunt zo nodig gegevens toevoegen en verwijderen. Maar wel een goed beginpunt.

- De zoekfunctie voor woorden of tekstpatronen in het onderwerp of andere koptekstvelden in het bericht doet zich voor *Wanneer* het bericht is verwijderd uit de versleutelingsmethode MIME-inhoudsoverdracht die werd gebruikt om het binaire bericht te verzenden tussen SMTP-servers in ASCII-tekst. U kunt voorwaarden of uitzonderingen niet gebruiken om te zoeken naar de gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.

- In de volgende procedures wordt een bulk bericht als spam voor de hele organisatie gemarkeerd. U kunt echter nog een voorwaarde toevoegen om deze regels alleen op specifieke geadresseerden toe te passen, zodat u een zeer sterk bedoelende gebruiker kunt gebruiken, terwijl de rest van de gebruikers (die het grootste e-mailbericht waartoe de e-mail wordt verzonden) niet worden beïnvloed.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Het Exchange-Beheercentrum gebruiken om grote hoeveelheden e-mail te filteren

1. Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> .

2. Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.

3. Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:

   - **Naam**: Typ een unieke, beschrijvende naam voor de regel.

   - Klik op **meer opties**.

   - **Deze regel toepassen als**: een van de volgende instellingen configureren om inhoud in berichten te zoeken met behulp van reguliere expressies (regex) of woorden of woordgroepen:

     - **Het onderwerp of de hoofdtekst** \> **onderwerp of hoofdtekst komt overeen met deze tekstpatronen**: Typ een van de volgende waarden in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven **, klik op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en herhaal dit tot u alle waarden hebt ingevoerd.

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

      Als u een vermelding wilt bewerken, selecteert u  deze en klikt u op ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) . Als u een vermelding wilt verwijderen, selecteert u deze **en klikt u** op het ![ pictogram verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

       Wanneer u klaar bent, klikt u op **OK**.

     - **Het onderwerp of de hoofdtekst** \> het **onderwerp of de hoofdtekst bevat een of meer van deze woorden**: Typ een van de volgende waarden in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven **, klik op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en herhaal dit tot u alle waarden hebt ingevoerd.

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

      Als u een vermelding wilt bewerken, selecteert u  deze en klikt u op ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) . Als u een vermelding wilt verwijderen, selecteert u deze **en klikt u** op het ![ pictogram verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

       Wanneer u klaar bent, klikt u op **OK**.

   - **Ga als volgt** te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**. In het dialoogvenster **SCL opgeven** dat wordt weergegeven, configureert u een van de volgende instellingen:

     - Selecteer **6** om berichten als **spam** te markeren. De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** Verdicts in uw Antispambeleid op de berichten (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).

     - Als u berichten wilt markeren als **spam van hoge betrouwbaarheid** , selecteert u **9**. De actie die u hebt geconfigureerd voor het filteren van **spam** filteren Verdicts in uw Antispambeleid, wordt op de berichten toegepast (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).

    Zie voor meer informatie over SCL-waarden [spam niveau voor spam (SCL) in EOP](spam-confidence-levels.md).

   Wanneer u klaar bent, klikt u op **Opslaan** .

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell gebruiken om regels voor e-mail stroom te maken waarmee bulk berichten worden gefilterd

Gebruik de volgende syntaxis om een of beide regels voor de e-mail stroom te maken (reguliere expressies en. woorden):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam ' bulksgewijze e-mail filtering ', die dezelfde lijst met reguliere expressies gebruikt, van eerder in het onderwerp om berichten in te stellen als **spam**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In dit voorbeeld wordt een nieuwe regel gemaakt met de naam ' filteren van bulk-e-mail filteren-woorden ' waarbij de lijst met woorden van eerder in het onderwerp wordt gebruikt voor het instellen van berichten als **spam van hoge betrouwbaarheid**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Voer een van de volgende stappen uit om te controleren of u de e-mail stroom regels hebt geconfigureerd voor het filteren van bulk-e-mail:

- Ga in het Exchange-Beheercentrum naar **e-mail stroom** \> **regels** \> , selecteer de regel Klik op bewerkings \> pictogram **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) en controleer de instellingen.

- In PowerShell vervangt \<Rule Name\> u de naam van de regel en voert u de volgende opdracht uit om de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Verstuur via een extern account een testbericht naar een geadresseerde die een van de woordgroepen of tekstpatronen bevat, en controleer de resultaten.
