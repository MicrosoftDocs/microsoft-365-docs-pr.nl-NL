---
title: Veilige documenten in Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over veilige documenten in Microsoft 365 E5 of Microsoft 365 E5 beveiliging.
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949452"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Veilige documenten in Microsoft 365 E5

Veilige documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5-beveiliging waarbij [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikmaakt voor het scannen van documenten en bestanden die worden geopend in de [beveiligde weergave](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Veilige documenten zijn nu algemeen beschikbaar voor gebruikers met Office versie 2004 (12730. x) of hoger. Deze functie is standaard uitgeschakeld en moet worden ingeschakeld door de beveiligingsbeheerder.

- Deze functie is alleen beschikbaar voor gebruikers met de beveiligings licentie voor *Microsoft 365 E5* of *Microsoft 365 E5* (deze functie is niet opgenomen in Office 365 ATP-abonnementen).

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Voor meer informatie over 

- U moet machtigingen zijn toegewezen voordat u de procedures in dit onderwerp kunt uitvoeren. Als u veilige documenten wilt inschakelen en configureren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** . Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

## <a name="how-does-microsoft-handle-your-data"></a>Hoe bewerkt Microsoft uw gegevens?

Om te beschermen, worden met veilige documenten bestanden naar de [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) -Cloud verzonden voor analyse.

- In [dit onderwerp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)vindt u meer informatie over de manier waarop u uw gegevens kunt vinden in Microsoft Defender Advanced Threat Protection.
- Naast de bovenstaande richtlijnen, worden bestanden die zijn verzonden via veilige documenten niet bewaard na de tijd die nodig is om te worden geanalyseerd, wat meestal minder dan 24 uur duurt.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Beveiligings & voor naleving van Beveiligingscentrum gebruiken om veilige documenten te configureren

1. Open het beveiligings & nalevings centrum op <https://protection.office.com> .

2. Ga naar **Threat management** \> **Policy** \> **veilige bijlagen**voor het beleid voor risicobeheer.

3. Configureer een van de volgende instellingen in de sectie **Help personen veilig houden wanneer u een bestand vertrouwt om buiten de beveiligde weergave te openen in** de sectie Office-toepassingen:

   - **Veilige documenten voor Office-clients inschakelen**

   - **Toestaan dat mensen kunnen klikken via de beveiligde weergave, zelfs als een veilig document het bestand als schadelijk identificeert**: u wordt aangeraden deze optie niet in te schakelen.

4. Klik op **Opslaan** wanneer u gereed bent.

![Pagina voor veilige bijlagen met ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Veilige documenten configureren met Exchange Online PowerShell of zelfstandige EOP PowerShell

Gebruik de volgende syntaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Met de parameter _EnableSafeDocs_ kunt u veilige documenten voor de hele organisatie in-of uitschakelen.

- Met de parameter _AllowSafeDocsOpen_ kunt u of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen, het document openen) als het document is geïdentificeerd als schadelijk.

In dit voorbeeld worden veilige documenten ingeschakeld voor de hele organisatie en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk voor de beveiligde weergave.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="how-do-i-know-this-worked"></a>Hoe weet ik of ik dit heb gewerkt?

Ga op een van de volgende manieren te werk om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:

- Ga in het beveiligings & compliance naar veilige bijlagen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Attachments**en controleer de selecties in de secties **Help-personen veilig blijven als u een bestand vertrouwt om buiten de beveiligde weergave te openen in** de sectie Office-toepassingen.

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapwaarden.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
