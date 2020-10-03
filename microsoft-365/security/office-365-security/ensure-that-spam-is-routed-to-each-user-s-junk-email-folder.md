---
title: EOP configureren voor ongewenste spam in hybride omgevingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u spam stuurt naar mappen voor ongewenste E-mail in een Exchange Online Protection hybride omgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 76003f18009ebf9159f01d916cdaf38b50a213d1
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350337"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Zelfstandige EOP configureren voor het afleveren van spam op de map Ongewenste E-mail in hybride omgevingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Dit onderwerp is alleen voor zelfstandige EOP-klanten in hybride omgevingen. Dit onderwerp is niet van toepassing op Microsoft 365-klanten met postvakken van Exchange Online.

Als u een zelfstandige Exchange Online Protection-klant (EOP) hebt in een hybride omgeving, moet u uw on-premises Exchange-organisatie configureren voor het herkennen en vertalen van de spamfilters Verdicts van EOP, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten kan verplaatsen naar de map Ongewenste E-mail.

U moet specifiek voor het maken van een e-mail stroom regels (ook wel transport-regels genoemd) in uw on-premises Exchange-organisatie met voorwaarden waarmee u berichten vindt met een van de volgende EOP-antispam koppen en-waarden, en acties waarmee het spam niveau van deze berichten wordt ingesteld op 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (bericht gemarkeerd als spam door spam te filteren)

- `X-Forefront-Antispam-Report: SFV:SKS` (bericht gemarkeerd als spam door regels voor de e-mail stroom in EOP voordat spam wordt gefilterd)

- `X-Forefront-Antispam-Report: SFV:SKB` (bericht is gemarkeerd als spam door spam te filteren vanwege het e-mailadres of e-mail domein van de afzender in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in EOP)

Zie [anti spambericht koppen](anti-spam-message-headers.md)voor meer informatie over deze koptekst waarden.

In dit onderwerp wordt beschreven hoe u deze regels voor e-mail stroom kunt maken in het Exchange-Beheercentrum en in de Exchange-beheer shell (Exchange PowerShell) in de on-premises Exchange-organisatie.

> [!TIP]
> In plaats van de berichten naar de map Ongewenste E-mail van de gebruiker te bezorgen, kunt u Antispambeleid in EOP configureren voor het gebruiken van spamberichten in EOP. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen voor de on-premises Exchange-omgeving worden toegewezen voordat u deze procedures kunt uitvoeren. Specifiek moet u de rol van **transport regels** toewijzen, die aan de rollen voor **Organisatiebeheer**, **Compliance Management**, en het **beheer van recordbeheer** standaard is toegewezen. Zie [leden aan een rollen groep toevoegen](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)voor meer informatie.

- Als en wanneer een bericht wordt bezorgd in de map Ongewenste E-mail in een on-premises Exchange-organisatie, wordt bepaald door een combinatie van de volgende instellingen:

  - De waarde van _SCLJunkThreshold_ -parameter in de cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in de Exchange-beheer shell. De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht naar de map Ongewenste e-mail van de gebruiker verzorgt.

  - De waarde van de _SCLJunkThreshold_ -parameter in de cmdlet [set-mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in de Exchange-beheer shell. De standaardwaarde is leeg ($null), wat betekent dat de organisatie-instelling wordt gebruikt.

  Zie [drempelwaarden voor spam niveau van Exchange (SCL)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)voor meer informatie.

  - Of de regel voor ongewenste e-mail is ingeschakeld voor het postvak (de _ingeschakelde_ parameterwaarde is $True op de cmdlet [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Exchange-beheer shell). Het is de regel voor ongewenste e-mail waarmee het bericht na ontvangst naar de map Ongewenste E-mail wordt verplaatst. Standaard is de regel voor ongewenste e-mail ingeschakeld voor postvakken. Zie [Exchange spam instellingen in postvakken configureren](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)voor meer informatie.

- Zie [Exchange-Beheercentrum in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)om de versie van het Beheercentrum te openen op een Exchange-Server. Zie [de Exchange-beheer shell openen](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)voor informatie over het openen van de Exchange-beheer shell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mail stroom in on-premises Exchange:

  - [Regels voor e-mail stroom in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mail stroom regels in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Het Exchange-Beheercentrum gebruiken om regels voor de e-mail stroom in te stellen voor het maken van de SCL van EOP spamberichten

1. Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**.

2. Klik **op** ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer **een nieuwe regel maken** in de vervolgkeuzelijst die wordt weergegeven.

3. Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:

   - **Naam**: Typ een unieke, beschrijvende naam voor de regel. Bijvoorbeeld:

     - EOP SFV: SPM to SCL 6

     - EOP SFV: SKS naar SCL 6

     - EOP SFV: SKB naar SCL 6

   - Klik op **meer opties**.

   - **Deze regel toepassen als**: Selecteer **een kop van het bericht** \> **bevat een van deze woorden**.

     Voer de volgende stappen uit in de **kop tekst** invoeren die wordt weergegeven:

     - Klik op **tekst invoeren**. Voer in het dialoogvenster **opgegeven naam van de koptekst opgeven de tekst** **X-Forefront-spam-report** in en klik vervolgens op **OK**.

     - Klik op  **woorden invoeren**. Voer in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven een van de EOP spam waarden van de spam (**SFV: SPM**, **SFV: sks**of **SFV: SKB**) in **, klik op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en vervolgens op **OK**.

   - **Ga als volgt**te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**.

     Selecteer in het dialoogvenster **SCL opgeven** dat wordt weergegeven de optie **6** (de standaardwaarde is **5**).

   Wanneer u klaar bent, klikt u op **Opslaan** .

Herhaal deze stappen voor de resterende EOP spam verdict-waarden (**SFV: SPM**, **SFV: sks**of **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>De Exchange-beheer shell gebruiken om regels voor de e-mail stroom te maken die de SCL van EOP spamberichten instellen

Gebruik de volgende syntaxis om de drie e-mail stroom regels te maken:

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

Voer een van de volgende stappen uit om te controleren of u zelfstandige EOP hebt geconfigureerd voor het afleveren van spam in de map Ongewenste E-mail in hybride omgeving:

- Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**, selecteer de regel en klik vervolgens op **Edit** ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-EditIcon.png) om de instellingen te controleren.

- In de Exchange-beheer shell vervangt \<RuleName\> u de naam van de e-mail stroom regel door de naam van de e-mail stroom regel en rul u de volgende opdracht om de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- In een extern e-mailsysteem **dat uitgaande berichten voor spam niet scant**, stuurt u een algemene test voor ongevraagde E-mail (GTUBE) naar een geadresseerde en bevestigt u dat deze wordt bezorgd in de map Ongewenste e-mail. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

  Als u een GTUBE bericht wilt verzenden, moet u de volgende tekst opnemen in de hoofdtekst van een e-mailbericht op een enkele regel, zonder spaties of regeleinden:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
