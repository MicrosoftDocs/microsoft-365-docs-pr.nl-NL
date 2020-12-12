---
title: Veilige documenten in Microsoft Defender voor Office 365
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
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659871"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Veilige documenten in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Veilige documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5-beveiliging waarbij [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) wordt gebruikt om documenten en bestanden te scannen die worden geopend in de [beveiligde weergave](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Veilige documenten zijn alleen beschikbaar voor gebruikers met de beveiligings licenties voor *Microsoft 365 E5* of *Microsoft 365 E5* . Deze licenties zijn niet opgenomen in Microsoft Defender for Office 365-abonnementen.

- Veilige documenten worden ondersteund in Microsoft 365-apps voor Enterprise (voorheen bekend als Office 365 ProPlus) versie 2004 of hoger.

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de pagina met **veilige bijlage van ATP** wilt gaan, opent u deze <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als u instellingen voor veilige documenten wilt configureren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .
  - Voor alleen-lezen toegang tot instellingen voor veilige documenten moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

### <a name="how-does-microsoft-handle-your-data"></a>Hoe bewerkt Microsoft uw gegevens?

Om te beschermen, worden met veilige documenten bestanden naar de [Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) van de Cloud verzonden voor analyse. In dit onderwerp vindt u informatie over de manier waarop u uw gegevens kunt vinden in Microsoft Defender for endpoints: [Microsoft Defender for Endpoint data storage en privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Bestanden die door veilige documenten zijn verzonden, worden niet langer bewaard dan de tijd die nodig is voor de analyse (meestal minder dan 24 uur).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Beveiligings & voor naleving van Beveiligingscentrum gebruiken om veilige documenten te configureren

1. Ga in het beveiligings & compliance naar veilige bijlagen voor het beleid voor **bedreigings beheer** \>  \> en klik vervolgens op **algemene instellingen**.

2. Configureer de volgende instellingen in de **algemene instellingen** die worden weergegeven:

   - **Veilige documenten inschakelen voor Office-clients**: zet de wisselknop naar rechts om de functie in te schakelen: ![ wisselknop ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Toestaan dat personen kunnen klikken via de beveiligde weergave, zelfs als de veilige documenten het bestand als schadelijk identificeren**: u wordt aangeraden deze optie uit te schakelen (laat de schakeloptie links: ![ uit ](../../media/scc-toggle-off.png) ) staan.

   Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor veilige documenten nadat u wereldwijde instellingen hebt geselecteerd op de pagina voor veilige bijlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Veilige documenten configureren met Exchange Online PowerShell

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

- Ga in het beveiligings & compliance **naar het** beleid voor het oplossen van beveiligingsfuncties, ga naar \>  \> **veilige bijlagen** **voor Office** , klik op **algemene instellingen** en zorg ervoor **dat personen kunnen klikken op de beveiligde weergave, ongeacht of het bestand wordt geïdentificeerd als kwaadwillende documenten** .

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapwaarden.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- De volgende bestanden kunnen worden gebruikt om de beveiliging van veilige documenten te testen. Deze documenten lijken op het EICAR.TXT-bestand voor het testen van anti-malware en anti-virus oplossingen. De bestanden zijn niet schadelijk, maar de bescherming van veilige documenten wordt geactiveerd.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
