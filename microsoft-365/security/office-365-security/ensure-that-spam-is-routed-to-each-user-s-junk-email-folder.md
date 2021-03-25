---
title: EOP configureren voor ongewenste e-mail in hybride omgevingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze spam kunnen doorverrouteeren naar mappen met ongewenste e-mail van gebruikers in een hybride omgeving van Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204260"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Zelfstandige EOP configureren om spam te verzenden naar de map Ongewenste e-mail in hybride omgevingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Dit onderwerp is alleen beschikbaar voor zelfstandige EOP-klanten in hybride omgevingen. Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.

Als u een zelfstandige EOP-klant (Exchange Online Protection) bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie zo configureren dat de spamfilters van EOP worden herkend en vertaald, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten naar de map Ongewenste e-mail kan verplaatsen.

In het bijzonder moet u regels voor e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden voor het vinden van berichten met een van de volgende EOP-antispamkoppen en -waarden, en acties die het betrouwbaarheidsniveau voor spam (SCL) van deze berichten instellen op 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (bericht gemarkeerd als spam door spamfilters)

- `X-Forefront-Antispam-Report: SFV:SKS` (bericht dat is gemarkeerd als spam door e-mailstroomregels in EOP voordat spam wordt gefilterd)

- `X-Forefront-Antispam-Report: SFV:SKB` (bericht dat is gemarkeerd als spam door spamfilters omdat het e-mailadres of e-maildomein van de afzender in de lijst met geblokkeerde afzenders of de geblokkeerde domeinlijst in EOP staat)

Zie Kopteksten voor spamberichten voor meer informatie over deze [koptekstwaarden.](anti-spam-message-headers.md)

In dit onderwerp wordt beschreven hoe u deze e-mailstroomregels maakt in het Exchange-beheercentrum (EAC) en in de Exchange Management Shell (Exchange PowerShell) in de on-premises Exchange-organisatie.

> [!TIP]
> In plaats van de berichten te verzenden naar de map Ongewenste e-mail van de on-premises gebruiker, kunt u antispambeleid configureren in EOP om spamberichten in EOP in quarantaine te plaatsen. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen toegewezen in de on-premises Exchange-omgeving voordat u deze procedures kunt uitvoeren. U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer** en **Recordsbeheer.** Zie Leden toevoegen aan [een rollengroep voor meer informatie.](/Exchange/permissions/role-group-members#add-members-to-a-role-group)

- Als en wanneer een bericht wordt bezorgd in de map Ongewenste e-mail in een on-premises Exchange-organisatie wordt bepaald door een combinatie van de volgende instellingen:

  - De _parameterwaarde SCLJunkThreshold_ op de [cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) in de Exchange Management Shell. De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet bezorgen in de map Ongewenste e-mail van de gebruiker.

  - De _parameterwaarde SCLJunkThreshold_ op de [cmdlet](/powershell/module/exchange/set-mailbox) Postvak instellen in de Exchange Management Shell. De standaardwaarde is leeg ($null), wat betekent dat de organisatieinstelling wordt gebruikt.

  Zie [SCL-drempels (Exchange spam confidence level) voor meer informatie.](/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Of de regel ongewenste e-mail is ingeschakeld in het postvak (de _parameterwaarde_ ingeschakeld is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Exchange Management Shell). Het is de regel voor ongewenste e-mail die het bericht na de bezorging naar de map Ongewenste e-mail verplaatst. Standaard is de regel ongewenste e-mail ingeschakeld in postvakken. Zie [Exchange-antispaminstellingen configureren voor postvakken](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)voor meer informatie.

- Zie [Exchange-beheercentrum in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center)om de EAC op een Exchange Server te openen. Zie De Exchange Management Shell openen om de Exchange Management Shell [te openen.](/powershell/exchange/open-the-exchange-management-shell)

- Zie de volgende onderwerpen voor meer informatie over e-mailstroomregels in on-premises Exchange:

  - [Regels voor e-mailstroom in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mailstroomregel in Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Gebruik de EAC om regels voor e-mailstroom te maken die de SCL van EOP-spamberichten instellen

1. Ga in het EAC naar **E-mailstroomregels.** \> 

2. Klik **op Pictogram** Toevoegen toevoegen en selecteer Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken** in de vervolgkeuzepagina die wordt weergegeven.

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** Voer een unieke, beschrijvende naam in voor de regel. Bijvoorbeeld:

     - EOP SFV:SPM naar SCL 6

     - EOP SFV:SKS naar SCL 6

     - EOP SFV:SKB naar SCL 6

   - Klik **op Meer opties.**

   - **Pas deze regel toe als**: Selecteer Een **berichtkop** \> **bevat een van deze woorden.**

     Voer de **volgende stappen uit** in de tekstkop Enter met de tekstzin Enter die wordt weergegeven:

     - Klik **op Tekst invoeren.** Typ in **het dialoogvenster Naam van koptekst** opgeven dat wordt weergegeven **X-Forefront-Antispam-Report** en klik vervolgens op **OK.**

     - Klik **op Woorden invoeren.** Typ **in** het dialoogvenster Woorden of woordgroepen opgeven dat wordt weergegeven een van de EOP-waarden voor spamkoppen **(SFV:SPM,** **SFV:SKS** of **SFV:SKB),** klik op Pictogram Toevoegen toevoegen en klik vervolgens op  ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**

   - **Ga als volgt** te werk: Selecteer **De eigenschappen van het bericht wijzigen** Het \> **betrouwbaarheidsniveau voor spam instellen (SCL).**

     Selecteer **6** (de standaardwaarde is **5)** in het dialoogvenster **SCL** opgeven dat wordt weergegeven.

   Wanneer u klaar bent, klikt u op **Opslaan**

Herhaal deze stappen voor de resterende EOP-waarden voor spam **(SFV:SPM,** **SFV:SKS** of **SFV:SKB).**

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Gebruik de Exchange Management Shell om e-mailstroomregels te maken die de SCL van EOP-spamberichten instellen

Gebruik de volgende syntaxis om de drie regels voor de e-mailstroom te maken:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Bijvoorbeeld:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u zelfstandige EOP hebt geconfigureerd om spam te verzenden naar de map Ongewenste e-mail in een hybride omgeving, gaat u als volgt te werk:

- Ga in het EAC naar **E-mailstroomregels,** selecteer de regel en klik vervolgens op Pictogram Bewerken bewerken om \> de instellingen  ![ te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.

- Vervang in de Exchange Management Shell de naam van de e-mailstroomregel en rul de volgende opdracht om \<RuleName\> de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- In een extern e-mailsysteem dat uitgaande berichten niet scant op **spam,** verzendt u een algemene test voor ongewenste bulk-e-mail (GTUBE) naar een getroffen geadresseerde en bevestigt u dat het bericht is bezorgd in de map Ongewenste e-mail. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

  Als u een GTUBE-bericht wilt verzenden, moet u de volgende tekst in de kop van een e-mailbericht opnemen op één regel, zonder spaties of regel-einden:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```