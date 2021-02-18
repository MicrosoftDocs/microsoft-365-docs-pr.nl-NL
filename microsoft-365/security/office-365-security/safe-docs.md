---
title: Veilige documenten in Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over de beveiliging van Veilige documenten in Microsoft 365 E5 of Microsoft 365 E5.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288583"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Veilige documenten in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Veilige documenten is een functie in microsoft 365 E5- of Microsoft 365 E5-beveiliging waarmee [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor het eindpunt wordt gebruikt om documenten en bestanden te scannen die worden geopend in de [beveiligde weergave.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Veilige documenten is alleen beschikbaar voor gebruikers met een beveiligingslicentie voor *Microsoft 365 E5* of *Microsoft 365 E5.* Deze licenties zijn niet opgenomen in Microsoft Defender voor Office 365-abonnementen.

- Veilige documenten wordt ondersteund in Microsoft 365-apps voor ondernemingen (voorheen Bekend als Office 365 ProPlus) versie 2004 of hoger.

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de pagina Veilige **bijlagen met ATP wilt** gaan, opent u <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als u instellingen voor veilige documenten wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot instellingen voor veilige documenten  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

### <a name="how-does-microsoft-handle-your-data"></a>Hoe gaat Microsoft om met uw gegevens?

Om u te beschermen, verzendt Veilige documenten bestanden naar de [Cloud van Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse. Meer informatie over hoe Microsoft Defender voor eindpunt uw gegevens verwerkt, vindt u hier: Gegevensopslag en privacy van [Microsoft Defender voor eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Bestanden die door Veilige documenten worden verzonden, worden niet bewaard in Defender na de tijd die nodig is voor analyse (meestal minder dan 24 uur).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Het beveiligings- & gebruiken om veilige documenten te configureren

1. Ga in het & Compliancecentrum  voor beveiligingsinstellingen naar Veilige bijlagen met ATP-beleid voor \>  \> **bedreigingsbeheer** en klik op **Globale instellingen.**

2. Configureer **de volgende instellingen** in de fly-out met globale instellingen:

   - **Veilige documenten voor Office-clients** in schakelen: verplaats de schakelaar naar rechts om de functie in te schakelen: ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)

   - **Personen toestaan** door de beveiligde weergave te klikken, zelfs als veilige documenten het bestand als schadelijk identificeren: het is raadzaam deze optie uitgeschakeld te laten (laat de schakelaar aan de linkerkant staan: Schakel de schakelaar ![ ](../../media/scc-toggle-off.png) uit).

   Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor veilige documenten nadat u algemene instellingen op de pagina Veilige bijlagen heeft geselecteerd.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell gebruiken om veilige documenten te configureren

Gebruik de volgende syntaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Met de parameter _EnableSafeDocs_ schakelt u veilige documenten in of uit voor de hele organisatie.
- Met de parameter _AllowSafeDocsOpen_ kunnen gebruikers de beveiligde weergave (dat wil zeggen het document openen) verlaten als het document is geïdentificeerd als schadelijk.

In dit voorbeeld worden veilige documenten voor de hele organisatie gebruikt en kunnen gebruikers geen documenten openen die in de beveiligde weergave als schadelijk zijn aangemerkt.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Zie [Set-AtpPolicyForO365 voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)syntaxis- en parameterinformatie.

### <a name="how-do-i-know-this-worked"></a>Hoe weet ik of dit heeft gewerkt?

Ga op een van de volgende stappen te werk om te controleren of u Veilige documenten hebt ingeschakeld en geconfigureerd:

- Ga in het & Compliancecentrum  voor beveiligingsbeheer naar VEILIGE bijlagen van ATP-beleid voor \>  \> **bedreigingsbeheer,**   klik op Algemene instellingen en controleer of veilige documenten voor **Office-clients** worden in- of uitschakelen en personen toestaan om door de beveiligde weergave te klikken, zelfs als het bestand wordt geïdentificeerd als schadelijke instellingen.

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- De volgende bestanden zijn beschikbaar om de beveiliging van veilige documenten te testen. Deze documenten zijn vergelijkbaar met het EICAR.TXT voor het testen van antivirus- en antivirusoplossingen. De bestanden zijn niet schadelijk, maar activeren wel de beveiliging van veilige documenten.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
