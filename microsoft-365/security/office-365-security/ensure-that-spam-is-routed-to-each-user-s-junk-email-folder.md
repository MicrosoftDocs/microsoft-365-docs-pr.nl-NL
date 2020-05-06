---
title: EOP configureren voor ongewenste spam in hybride omgevingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen lezen hoe ze spam kunnen routeren naar map ongewenste e-mail van gebruikers in een hybride omgeving van Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14193fecf90a6f2ddde05fbfdaded0ff2bcb5875
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036570"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Standalone EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen

> [!IMPORTANT]
> Dit onderwerp is alleen voor standalone EOP-klanten in hybride omgevingen. Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.

Als u een zelfstandige Exchange Online Protection (EOP)-klant bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie configureren om de spamfilteringsvonnissen van EOP te herkennen en te vertalen, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten naar de map Ongewenste e-mail kan verplaatsen.

In het bijzonder moet u regels voor e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden die berichten vinden met een van de volgende EOP-antispamheaders en -waarden en acties die het spamvertrouwensniveau (SCL) van die berichten instellen op 6:

- `X-Forefront-Antispam-Report: SFV:SPM`(bericht gemarkeerd als spam door spamfiltering)

- `X-Forefront-Antispam-Report: SFV:SKS`(bericht gemarkeerd als spam door mail flow regels in EOP voor spam filtering)

- `X-Forefront-Antispam-Report: SFV:SKB`(bericht gemarkeerd als spam door spamfiltering omdat het e-mailadres of e-mailadres van de afzender in de lijst met geblokkeerde afzenders of de geblokkeerde domeinlijst in EOP staat)

Zie [Kopteksten voor spamberichten](anti-spam-message-headers.md)voor meer informatie over deze kopteksten.

In dit onderwerp wordt beschreven hoe u deze regels voor e-mailstroom maakt, het Exchange-beheercentrum (EAC) en in exchangemanagementshell (Exchange PowerShell) in de on-premises Exchange-organisatie.

> [!TIP]
> In plaats van de berichten af te leveren aan de map Ongewenste e-mail van de eindgebruiker, u antispambeleid in EOP configureren om spamberichten in EOP in quarantaine te plaatsen. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen in de on-premises Exchange-omgeving toegewezen krijgen voordat u deze procedures uitvoeren. U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.** Zie [Leden toevoegen aan een rolgroep voor](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)meer informatie .

- Als en wanneer een bericht wordt afgeleverd in de map Ongewenste e-mail in een on-premises Exchange-organisatie, wordt u gecontroleerd door een combinatie van de volgende instellingen:

  - De parameterwaarde _SCLJunkThreshold_ op de cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) in de Exchange Management Shell. De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet leveren aan de e-mailmap ongewenste e-mail van de gebruiker.

  - De _parameterwaarde SCLJunkThreshold_ op de cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) in de Exchange Management Shell. De standaardwaarde is leeg ($null), wat betekent dat de organisatieinstelling wordt gebruikt.

  Zie [SCL-drempels (Exchange spam confidence level) voor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)meer informatie.

  - Of de regel voor ongewenste e-mail is ingeschakeld in het postvak (de _parameterwaarde Ingeschakeld_ is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) in de Exchange Management Shell). Het is de ongewenste e-mailregel die het bericht na levering daadwerkelijk verplaatst naar de map Ongewenste e-mail. Standaard is de regel voor ongewenste e-mail ingeschakeld voor postvakken. Zie [Antispam-instellingen voor Exchange configureren op postvakken voor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)meer informatie.
  
- Zie [Exchange-beheercentrum in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)als u de EAC op een Exchange-server wilt openen. Zie [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in on-premises Exchange:

  - [Regels voor e-mailstromen in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstromenregels (predicaten) in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Regelacties voor e-mailstromen in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Gebruik de EAC om regels voor e-mailstromen te maken die de SCL van EOP-spamberichten instellen

1. Ga in de EAC naar **Mail flow** \> **Rules**.

2. Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **Een nieuwe regel maken** in de vervolgkeuzelijst die wordt weergegeven.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam:** Voer een unieke, beschrijvende naam voor de regel in. Bijvoorbeeld:

     - EOP SFV:SPM naar SCL 6

     - EOP SFV:SKS naar SCL 6

     - EOP SFV:SKB naar SCL 6

   - Klik **op Meer opties**.

   - **Pas deze regel toe als**: Een **berichtkop** \> **selecteren een van deze woorden bevat**.

     Voer in de **koptekst Enter woorden in** die wordt weergegeven de volgende stappen uit:

     - Klik **op Tekst invoeren**. Typ in het dialoogvenster **Koptekst opgeven** dat wordt **weergegeven, X-Forefront-Antispam-Report** en klik op **OK**.

     - Klik **op Woorden invoeren**. Klik in het dialoogvenster **Woorden of zinnen opgeven** dat wordt weergegeven, voer een van de waarden van de EOP-spamkop (**SFV:SPM,** **SFV:SKS**of **SFV:SKB**) **in,** ![klik op Pictogram](../../media/ITPro-EAC-AddIcon.png)Toevoegen en klik vervolgens op **OK**.

   - **Ga als volgt**te werk: Selecteer **De eigenschappen** \> van het bericht **wijzigen Stel het betrouwbaarheidsniveau voor spam (SCL) in.**

     **Selecteer** 6 in het dialoogvenster **SCL opgeven** dat wordt weergegeven (de standaardwaarde is **5**).

   Klik op **Opslaan** als u klaar bent

Herhaal deze stappen voor de resterende EOP spam verdict waarden **(SFV: SPM**, **SFV: SKS**, of **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Gebruik de Exchange Management Shell om regels voor e-mailstromen te maken die de SCL van EOP-spamberichten instellen

Gebruik de volgende syntaxis om de drie regels voor e-mailstromen te maken:

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

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga op de volgende stappen als u wilt controleren of u zelfstandige EOP hebt geconfigureerd om spam te leveren aan de map Ongewenste e-mail in een hybride omgeving:

- Ga in de EAC naar **E-mailstroomregels,** \> **Rules**selecteer de regel](../../media/ITPro-EAC-EditIcon.png) en klik op Pictogram Bewerken **bewerken** ![om de instellingen te verifiëren.

- Vervang RuleName \<\> in de Exchange Management Shell door de naam van de regel voor e-mailstroom en voer de volgende opdracht in om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Stuur in een extern e-mailsysteem dat uitgaande **berichten niet scant op spam,** een algemene test voor GTUBE-bericht (Unsolicited Bulk Email) naar een getroffen ontvanger en bevestigt u dat het wordt bezorgd in de map Ongewenste e-mail. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

  Als u een GTUBE-bericht wilt verzenden, neemt u de volgende tekst op in de hoofdtekst van een e-mailbericht op één regel, zonder spaties of regeleinden:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
