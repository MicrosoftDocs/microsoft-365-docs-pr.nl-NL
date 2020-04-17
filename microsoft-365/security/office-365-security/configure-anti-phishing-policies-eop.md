---
title: Het standaard beleid voor antiphishing configureren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie vinden over het wijzigen van de anti-spoofing-instellingen die beschikbaar zijn in het standaard beleid voor antiphishing in Office 365-organisaties met Exchange Online-postvakken.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537531"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>Het standaard beleid voor antiphishing configureren in EOP

Office 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken hebben een standaard beleid voor antiphishing. Dit beleid bevat een beperkt aantal anti-spoofing functies die standaard zijn ingeschakeld. Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

Office 365-organisaties met Exchange Online-postvakken kunnen het standaard beleid voor phishing-phishing wijzigen in het Office 365 Security & Compliance Center of in Exchange Online PowerShell. Zelfstandige EOP-organisaties zonder Exchange Online-postvakken kunnen hun standaardbeleid voor antiphishing niet wijzigen.

Zie [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md)voor informatie over het maken en wijzigen van de meer geavanceerde ATP-antiphishingbeleidsregels die beschikbaar zijn in Office 365 Advanced Threat Protection.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik . **Anti-phishing** <https://protection.office.com/antiphishing>

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot anti-phishingbeleid moet u lid zijn van de rolgroep **Security Reader.** Zie [Machtigingen in het Office 365-beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Zie [EOP standaard antiphishingbeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor het standaardbeleid tegen phishing.

- Sta maximaal 30 minuten toe voordat het bijgewerkte beleid wordt toegepast.

- Zie [Volgorde en voorrang van e-mailbeveiliging in Office 365](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Het Beveiligingscentrum & gebruiken om het standaardbeleid voor phishing te wijzigen

Het standaard beleid voor antiphishing heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels. Ga als volgt te werk om het standaard beleid voor antiphishing te wijzigen:

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Klik op de pagina **Anti-phishing** op **Standaardbeleid**.

3. De pagina **Standaardinstelling voor uw beleid Office365 AntiPhish** wordt weergegeven. Klik **in** de sectie Spoof op **Bewerken**.

   Houd er rekening mee dat deze instellingen identiek zijn aan de spoofinstellingen die beschikbaar zijn in het ATP-beleid voor phishing.

   - **Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten staan. Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.** Zie [Spoofinformatie configureren in Office 365](learn-about-spoof-intelligence.md)voor meer informatie.

     > [!NOTE]
     > U hoeft anti-spoofingbeveiliging niet uit te schakelen als uw MX-record niet naar Office 365 wijst. u schakelt in plaats daarvan Uitgebreide filtering voor connectors in. Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .

   - **Functie Niet-geverifieerde afzender inschakelen:** hiermee voegt u een vraagteken toe aan de foto van de afzender als het bericht de verificatiecontroles van e-mailmislukt. Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie. De standaardwaarde is **Aan**. Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**

   - **Acties:** Geef de actie op die moet worden uitgevoerd met berichten die niet in de spoofinformatie zijn geslaagd:

     **Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**

     - **Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden** (dit is de standaardwaarde.)
     - **Het bericht in quarantaine plaatsen**

   - **Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.
     - U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**

       - **Antispoofing-beveiliging inschakelen**
       - **Functie Niet-geverifieerde afzender inschakelen**

   Klik op **Opslaan** op een pagina als u klaar bent.

4. Terug op de standaardpagina **van uw beleid Office365 AntiPhish,** controleert u uw instellingen en klikt u op **Sluiten**.

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>Gebruik het Beveiligings& Compliance Center om het standaard antiphishingbeleid weer te geven

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Klik **op Standaardbeleid** om het standaard beleid voor antiphishing weer te geven.

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Exchange Online PowerShell gebruiken om het standaard beleid voor antiphishing te configureren

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>PowerShell gebruiken om het standaard anti-phish-beleid weer te geven

Voer de volgende opdracht uit om het standaard anti-phish-beleid weer te geven:

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>PowerShell gebruiken om het standaard anti-phish-beleid te wijzigen

Als u het standaard anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

In dit voorbeeld wordt de actie voor vervalste berichten die geen verificatiecontroles uitvoeren, gewijzigd in quarantaine.

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga een van de volgende stappen uit om te controleren of u het standaardbeleid voor antiphishing hebt geconfigureerd:

- Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.

- Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
