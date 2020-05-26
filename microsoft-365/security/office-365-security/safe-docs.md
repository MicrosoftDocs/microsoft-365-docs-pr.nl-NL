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
description: Meer informatie over veilige documenten in Office 365 ATP.
ms.openlocfilehash: f792b1acbdacfd29db5bbbf377f41396c35e3f17
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350949"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Veilige documenten in Office 365 Advanced Threat Protection

Veilige documenten is een functie in Office 365 Advanced Threat Protection (Office 365 ATP) die [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) gebruikt om documenten en bestanden te scannen die zijn geopend in de beveiligde [weergave.](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Deze functie is alleen beschikbaar voor gebruikers met de Microsoft 365 E5- of Microsoft 365 E5-beveiligingslicentie.

- Veilige documenten zijn momenteel beschikbaar voor een openbare preview, beschikbaar voor gebruikers die deel uitmaken van het [Office Insider-programma](https://insider.office.com/en-us/join) op het 'Monthly Channel (Targeted)' met Office Version 2002 (12527.20092) of hoger. Deze functie is standaard uitgeschakeld en moet worden ingeschakeld door de beveiligingsbeheerder.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet machtigingen toegewezen krijgen voordat u de procedures in dit onderwerp uitvoeren. Als u veilige documenten wilt in- en configureren, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

## <a name="how-does-microsoft-handle-your-data"></a>Hoe gaat Microsoft om met uw gegevens?

Om u te beschermen, stuurt Safe Documents bestanden naar de [Microsoft Defender Advanced Threat Protection-cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse.

- Details over hoe Microsoft Defender Advanced Thread Protection met uw gegevens omgaat, vindt u [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- Naast de bovenstaande richtlijnen worden bestanden die door veilige documenten worden verzonden, niet langer bewaard in Defender dan de tijd die nodig is voor analyse, wat meestal minder dan 24 uur is

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Het beveiligingscentrum & compliance center gebruiken om veilige documenten te configureren

1. Open het Security & Compliance Center op <https://protection.office.com> .

2. Ga naar ATP-veilige bijlagen **voor** \> **Policy** \> **bedreigingsbeheerbeleid**.

3. Configureer een van de volgende instellingen in de **sectie Help-personen die veilig zijn wanneer ze een bestand buiten de beveiligde weergave in office-toepassingen vertrouwen,** een van de volgende instellingen configureren:

   - **Veilige documenten inschakelen voor Office-clients (bestanden worden ook naar Microsoft Cloud verzonden voor diepgaande analyses)**

   - **Personen toestaan om door de beveiligde weergave te klikken, zelfs als safe documents het bestand als kwaadaardig identificeert:** we raden u aan deze optie niet in te schakelen.

4. Klik op **Opslaan** wanneer u gereed bent.

![Pagina ATP Safe-bijlagen](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell of standalone EOP PowerShell gebruiken om veilige documenten te configureren

Gebruik de volgende syntaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- Met de parameter _EnableSafeDocs_ worden veilige documenten voor de hele organisatie in- of uitgeschakeld.

- Met de parameter _AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave verlaten (dat wil zeggen het openen van het document) als het document als kwaadaardig is geïdentificeerd.

In dit voorbeeld worden veilige documenten voor de hele organisatie ingeschakeld en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als kwaadaardig vanuit de beveiligde weergave.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Zie [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="how-do-i-know-this-worked"></a>Hoe weet ik dat dit werkte?

Ga een van de volgende stappen uit om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:

- Ga in het Beveiligingscentrum **Threat management** & compliancecenter naar \> **Policy** \> **ATP-beveiligingsbijlagen**voor bedreigingsbeheerbeleid en controleer of de selecties in de **sectie Help-personen veilig blijven wanneer ze een bestand vertrouwen dat wordt geopend buiten de sectie Beveiligde weergave in Office-toepassingen.**

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
