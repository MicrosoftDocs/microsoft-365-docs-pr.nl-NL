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
description: Beheerders kunnen leren hoe ze spam kunnen routeren naar ongewenste e-mailmappen van gebruikers in een hybride exchange-omgeving voor onlinebescherming.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d8ba6aae599ee4dd327bd1ec82b46e8f3ee3ca8
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679118"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Zelfstandige EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen

> [!IMPORTANT]
> Dit onderwerp is alleen voor standalone EOP-klanten in hybride omgevingen. Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.

Als u een zelfstandige EOP-klant (Exchange Online Protection) bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie configureren om de uitspraken van EOP voor spamfilters te herkennen en te vertalen, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten naar de map Ongewenste e-mail kan verplaatsen.

In het bijzonder moet u regels voor e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden die berichten vinden met een van de volgende EOP-antispamheaders en -waarden, en acties die het spamvertrouwensniveau (SCL) van die berichten instellen op 6:

- `X-Forefront-Antispam-Report: SFV:SPM`(bericht gemarkeerd als spam door spamfiltering)

- `X-Forefront-Antispam-Report: SFV:SKS`(bericht gemarkeerd als spam door e-mailstroomregels in EOP voordat spamfiltert)

- `X-Forefront-Antispam-Report: SFV:SKB`(bericht gemarkeerd als spam door spamfiltering omdat het e-mailadres of e-maildomein van de afzender zich in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in EOP bevindt)

Zie [Antispamberichtenkoppen](anti-spam-message-headers.md)voor meer informatie over deze kopteksten.

In dit onderwerp wordt beschreven hoe u deze regels voor e-mailstroom maakt in het Exchange-beheercentrum (EAC) en in de Exchange Management Shell (Exchange PowerShell) in de on-premises Exchange-organisatie.

> [!TIP]
> In plaats van de berichten te leveren aan de map Ongewenste e-mail van de on-premises gebruiker, u antispambeleid in EOP configureren om spamberichten in EOP in quarantaine te plaatsen. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen toegewezen in de on-premises Exchange-omgeving voordat u deze procedures uitvoeren. In het bijzonder moet u de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliance Management**en **Records Management.** Zie [Leden toevoegen aan een rolgroep voor](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)meer informatie.

- Als en wanneer een bericht wordt bezorgd in de map Ongewenste e-mail in een on-premises Exchange-organisatie, wordt het beheerd door een combinatie van de volgende instellingen:

  - De parameterwaarde _SCLJunkThreshold_ op de [cmdlet Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in de Exchange Management Shell. De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet leveren aan de map Ongewenste e-mail van de gebruiker.

  - De parameterwaarde _SCLJunkThreshold_ op de cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in de Exchange Management Shell. De standaardwaarde is leeg ($null), wat betekent dat de organisatie-instelling wordt gebruikt.

  Zie [SCL-drempels (Exchange spam confidence level) voor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)meer informatie.

  - Of de regel voor ongewenste e-mail is ingeschakeld in het postvak (de parameterwaarde _ingeschakeld_ is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Shell Exchange Management). Het is de regel voor ongewenste e-mail die het bericht na levering daadwerkelijk naar de map Ongewenste e-mail verplaatst. Standaard is de regel voor ongewenste e-mail ingeschakeld op postvakken. Zie [Exchange-antispaminstellingen configureren voor postvakken](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)voor meer informatie.
  
- Zie [Exchange-beheercentrum in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)als u de EAC op een Exchange Server wilt openen. Zie De Shell voor [Exchange Management openen](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)als u de Shell voor Exchange Management wilt openen.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstroom in on-premises Exchange:

  - [Regels voor e-mailstroom in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties van de e-mailstroomregel in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>De EAC gebruiken om regels voor e-mailstroom te maken die de SCL van EOP-spamberichten instellen

1. Ga in de EAC naar **Regels voor e-mailstromen** \> **Rules**.

2. Klik **op** ![ pictogram Toevoegen toevoegen en selecteer Een ](../../media/ITPro-EAC-AddIcon.png) nieuwe regel **maken** in de vervolgkeuzelijst die wordt weergegeven.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam**: Voer een unieke, beschrijvende naam voor de regel in. Bijvoorbeeld:

     - EOP SFV:SPM naar SCL 6

     - EOP SFV:SKS naar SCL 6

     - EOP SFV:SKB naar SCL 6

   - Klik op **Meer opties**.

   - **Pas deze regel toe als**: Selecteer Een **berichtkoptekst** \> **bevat een van deze woorden**.

     Voer in de **tekstkop enter de woordenzin** invoeren die wordt weergegeven, de volgende stappen uit:

     - Klik **op Tekst invoeren**. Voer in het dialoogvenster **Koptekstnaam opgeven** dat wordt **weergegeven, X-Forefront-Antispam-Rapport in** en klik op **OK**.

     - Klik **op Woorden invoeren**. Voer in het dialoogvenster **Woorden of zinnen opgeven** die wordt weergegeven, een van de EOP-spamkopwaarden in **(SFV:SPM**, **SFV:SKS**of **SFV:SKB),** **klik** op ![ pictogram Toevoegen en klik ](../../media/ITPro-EAC-AddIcon.png) vervolgens op **OK**.

   - **Ga als volgt te**werk: **Selecteer De berichteigenschappen wijzigen** Stel het \> **spamvertrouwensniveau (SCL)** in .

     Selecteer in het dialoogvenster **SCL opgeven** dat wordt weergegeven **6** (de standaardwaarde is **5).**

   Klik op **Opslaan** als u klaar bent

Herhaal deze stappen voor de resterende EOP-spamoordeelwaarden **(SFV:SPM**, **SFV:SKS**of **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>De Exchange Management Shell gebruiken om regels voor e-mailstroom te maken die de SCL van EOP-spamberichten instellen

Gebruik de volgende syntaxis om de drie regels voor e-mailstroom te maken:

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

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u zelfstandige EOP hebt geconfigureerd om spam te leveren aan de map Ongewenste e-mail in een hybride omgeving, voert u een van de volgende stappen uit:

- Ga in de EAC naar **e-mailstroomregels,** \> **Rules**selecteer de regel en klik vervolgens op pictogram Bewerken bewerken om de instellingen **Edit** ![ te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.

- Vervang in de Shell voor Exchange-beheer \<RuleName\> de naam van de e-mailstroomregel en regel de volgende opdracht om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- In een extern e-mailsysteem **dat geen uitgaande berichten scant voor spam, verzendt**u een GTUBE-bericht (Generic Test for Onsolitcited Bulk Email) naar een getroffen ontvanger en bevestigt u dat het wordt bezorgd in de map Ongewenste e-mail. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

  Als u een GTUBE-bericht wilt verzenden, neemt u de volgende tekst op in de hoofdtekst van een e-mailbericht op één regel, zonder spaties of regeleinden:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
