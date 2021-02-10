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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het doorrouten van spam naar mappen voor ongewenste e-mail van gebruikers in een hybride omgeving van Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167117"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Zelfstandige EOP configureren voor het bezorgen van spam naar de map Ongewenste e-mail in hybride omgevingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> Dit onderwerp is alleen voor zelfstandige EOP-klanten in hybride omgevingen. Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.

Als u een zelfstandige klant van Exchange Online Protection (EOP) bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie zo configureren dat de spamfilters van EOP worden herkend en vertaald, zodat berichten naar de map Ongewenste e-mail kunnen worden verplaatst met de regel voor ongewenste e-mail in het on-premises postvak.

U moet met name regels voor de e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden voor het vinden van berichten met een van de volgende EOP-antispamkoppen en -waarden, en acties die het betrouwbaarheidsniveau voor spam van deze berichten instellen op 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (bericht gemarkeerd als spam door spamfilters)

- `X-Forefront-Antispam-Report: SFV:SKS` (bericht gemarkeerd als spam door regels voor de e-mailstroom in EOP vóór spamfilters)

- `X-Forefront-Antispam-Report: SFV:SKB` (Bericht gemarkeerd als spam door spamfilters omdat het e-mailadres of e-maildomein van de afzender in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in EOP staat)

Zie de kopteksten tegen [ongewenste e-mailberichten voor meer informatie over deze kopteksten.](anti-spam-message-headers.md)

In dit onderwerp wordt beschreven hoe u deze e-mailstroomregels maakt in het Exchange-beheercentrum (EAC) en in de Exchange-beheershell (Exchange PowerShell) in de on-premises Exchange-organisatie.

> [!TIP]
> In plaats van de berichten in de map Ongewenste e-mail van de on-premises gebruiker te plaatsen, kunt u antispambeleid in EOP configureren voor het in quarantaine plaatsen van spamberichten in EOP. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen krijgen in de on-premises Exchange-omgeving voordat u deze procedures kunt uitvoeren. De rol Transportregels, die  standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer** en **Recordbeheer,** moet aan u zijn toegewezen. Zie Leden toevoegen [aan een rollengroep voor meer informatie.](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)

- Als en wanneer een bericht wordt bezorgd in de map Ongewenste e-mail in een on-premises Exchange-organisatie, wordt dit bepaald door een combinatie van de volgende instellingen:

  - De _parameterwaarde SCLJunkThreshold_ op de cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in de Exchange-beheershell. De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet bezorgen in de map Ongewenste e-mail van de gebruiker.

  - De _parameterwaarde SCLJunkThreshold_ op de cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in de Exchange-beheershell. De standaardwaarde is leeg ($null), wat betekent dat de organisatie-instelling wordt gebruikt.

  Zie voor meer informatie de drempelwaarden voor [het betrouwbaarheidsniveau voor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)spam in Exchange.

  - Of de regel voor ongewenste e-mail is ingeschakeld in het postvak (de waarde voor de ingeschakelde _parameter_ is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Exchange-beheershell). Het is de regel voor ongewenste e-mail die het bericht na bezorging daadwerkelijk verplaatst naar de map Ongewenste e-mail. De regel voor ongewenste e-mail is standaard ingeschakeld voor postvakken. Zie [Antispaminstellingen voor Exchange configureren voor postvakken voor meer informatie.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)

- Als u het Exchange-beheercentrum wilt openen op een Exchange-server, gaat u naar [het Exchange-beheercentrum in Exchange Server.](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center) Zie De Exchange-beheershell openen als u [de Exchange-beheershell wilt openen.](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)

- Zie de volgende onderwerpen voor meer informatie over regels voor de e-mailstroom in on-premises Exchange:

  - [Regels voor e-mailstroom in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mailstroomregel in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Het EAC gebruiken om regels voor de e-mailstroom te maken die de SCL van EOP-spamberichten instellen

1. Ga in het EAC naar **Regels voor e-mailstroom.** \> 

2. Klik **op** ![ het pictogram Toevoegen en selecteer Een nieuwe regel ](../../media/ITPro-EAC-AddIcon.png) **maken** in de vervolgkeuzebalk die wordt weergegeven.

3. Configureer **de volgende** instellingen op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** voer een unieke, beschrijvende naam voor de regel in. Bijvoorbeeld:

     - EOP SFV:SPM naar SCL 6

     - EOP SFV:SKS naar SCL 6

     - EOP SFV:SKB naar SCL 6

   - Klik **op Meer opties.**

   - **Pas deze regel toe als:** Selecteer **een berichtkop** \> **een van deze woorden bevat.**

     Voer in **de kopTekst invoeren de volgende** stappen uit om woorden in te voeren die worden weergegeven:

     - Klik **op Tekst invoeren.** Voer in het dialoogvenster Naam van **koptekst** opgeven dat wordt weergegeven **X-Forefront-Antispam-Report** in en klik op **OK.**

     - Klik **op Woorden invoeren.** Voer  in het dialoogvenster Woorden of woordgroepen opgeven dat wordt weergegeven een van de waarden voor EOP-spamkoptekst in **(SFV:SPM,** **SFV:SKS** of **SFV:SKB),** klik op pictogram Toevoegen en klik op  ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**

   - **Ga als volgt te** werk: **selecteer De berichteigenschappen wijzigen** Stel het \> **betrouwbaarheidsniveau voor ongewenste e-mail in.**

     Selecteer **6** (de standaardwaarde is **5)** in het dialoogvenster **SCL** opgeven dat wordt weergegeven.

   Wanneer u klaar bent, klikt u op **Opslaan**

Herhaal deze stappen voor de resterende waarden voor spam in EOP **(SFV:SPM,** **SFV:SKS** of **SFV:SKB).**

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Gebruik de Exchange-beheershell om regels voor de e-mailstroom te maken die de SCL van EOP-spamberichten instellen

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

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de zelfstandige EOP zodanig hebt geconfigureerd dat spam moet worden verzonden naar de map Ongewenste e-mail in een hybride omgeving, gaat u als volgt te werk:

- Ga in het EAC naar Regels voor **e-mailstroom,** selecteer de regel en klik vervolgens op het pictogram Bewerken \> bewerken om de instellingen  ![ te ](../../media/ITPro-EAC-EditIcon.png) controleren.

- Vervang in de Exchange-beheershell door de naam van de regel voor de e-mailstroom en regel de volgende opdracht om \<RuleName\> de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- In een extern e-mailsysteem waarin uitgaande berichten niet op **spam** worden gescand, verzendt u een algemene test voor ongevraagde bulk-e-mail (GTUBE) naar een getroffen geadresseerde en controleert u of het bericht is bezorgd in de map Ongewenste e-mail. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

  Als u een GTUBE-bericht wilt verzenden, moet u de volgende tekst in de berichttekst van een e-mailbericht opnemen op één regel, zonder spaties of regel-eindes:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
