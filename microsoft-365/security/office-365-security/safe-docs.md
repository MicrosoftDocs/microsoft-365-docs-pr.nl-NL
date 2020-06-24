---
title: Veilige documenten in Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over veilige documenten in Microsoft 365 E5 of Microsoft 365 E5 Security.
ms.openlocfilehash: c574e28a01dc961d898638184afe9ece90e31133
ms.sourcegitcommit: aa7f7350d1342ff9713bb840b2cc96d1a4234ef4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2020
ms.locfileid: "44835347"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Veilige documenten in Microsoft 365 E5

Safe Documents is een functie in Microsoft 365 E5 of Microsoft 365 E5 Security die [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikt om documenten en bestanden te scannen die zijn geopend in de beveiligde [weergave.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Veilige documenten zijn nu algemeen beschikbaar voor gebruikers met Office Version 2004 (12730.x) of hoger! Deze functie is standaard uitgeschakeld en moet worden ingeschakeld door de beveiligingsbeheerder.

- Deze functie is alleen beschikbaar voor gebruikers met de *Microsoft 365 E5-* of *Microsoft 365 E5-beveiligingslicentie* (niet opgenomen in Office 365 ATP-abonnementen).

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet machtigingen krijgen toegewezen voordat u de procedures in dit onderwerp uitvoeren. Als u veilige documenten wilt in- en configureren, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

## <a name="how-does-microsoft-handle-your-data"></a>Hoe gaat Microsoft om met uw gegevens?

Om u te beschermen, stuurt Safe Documents bestanden naar de [Microsoft Defender Advanced Threat Protection-cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse.

- Details over hoe Microsoft Defender Advanced Threat Protection omgaat met uw gegevens vindt u [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- Naast de bovenstaande richtlijnen worden bestanden die door veilige documenten worden verzonden, niet langer bewaard in Defender dan de tijd die nodig is voor analyse, wat meestal minder dan 24 uur is

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Gebruik het Security & Compliance Center om veilige documenten te configureren

1. Open het Security & Compliance Center op <https://protection.office.com> .

2. Ga **Threat management** naar \> ATP Safe Attachments voor **bedreigingsbeheer.** \> **ATP Safe Attachments**

3. Configureer in de sectie **Help-mensen veilig wanneer u vertrouwt dat een bestand buiten de sectie Beveiligde weergave in Office-toepassingen** wordt geopend, een van de volgende instellingen:

   - **Veilige documenten voor Office-clients inschakelen**

   - **Laat mensen door de beveiligde weergave klikken, zelfs als Veilige documenten het bestand als kwaadaardig identificeert:** We raden u aan deze optie niet in te schakelen.

4. Klik op **Opslaan** wanneer u gereed bent.

![ATP Safe-bijlagenpagina](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om veilige documenten te configureren

Gebruik de volgende syntaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- De parameter _EnableSafeDocs_ schakelt veilige documenten voor de hele organisatie in of uit.

- Met de parameter _AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen het document openen) als het document als kwaadaardig is aangemerkt.

In dit voorbeeld worden veilige documenten voor de hele organisatie mogelijk en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als kwaadaardig in de beveiligde weergave.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Zie [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="how-do-i-know-this-worked"></a>Hoe weet ik dat dit werkte?

Als u wilt controleren of u veilige documenten hebt ingeschakeld en geconfigureerd, voert u een van de volgende stappen uit:

- Ga in het Security & Compliance Center naar **ATP** Safe Attachments voor \> **Policy** \> **bedreigingsbeheerbeleid**en controleer of de selecties in de **sectie Help-mensen veilig blijven wanneer ze vertrouwen dat een bestand buiten de sectie Beveiligde weergave in Office-toepassingen** wordt geopend.

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
