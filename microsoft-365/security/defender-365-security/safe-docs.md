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
description: Meer informatie over veilige documenten in Microsoft 365 E5 of Microsoft 365 E5-beveiliging.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1dc6c5dc54acd73b68fcd6241a270d2abdcc5c1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060310"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Veilige documenten in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Veilige documenten is een functie in Microsoft 365 E5- of Microsoft 365 E5-beveiliging waarmee [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor Eindpunt wordt gebruikt om documenten en bestanden te scannen die worden geopend in de [beveiligde weergave.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Veilige documenten is alleen beschikbaar voor gebruikers met *Microsoft 365 E5-* of *Microsoft 365 E5-beveiligingslicenties.* Deze licenties zijn niet opgenomen in Microsoft Defender voor Office 365-abonnementen.

- Veilige documenten wordt ondersteund in Microsoft 365 Apps voor ondernemingen (voorheen Bekend als Office 365 ProPlus) versie 2004 of hoger.

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de **pagina Veilige bijlagen van ATP** wilt gaan, opent u <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u instellingen voor veilige documenten wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot instellingen voor veilige documenten, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

### <a name="how-does-microsoft-handle-your-data"></a>Hoe gaat Microsoft om met uw gegevens?

Veilige documenten sturen bestanden naar de [Microsoft Defender for Endpoint-cloud](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse om u te beschermen. Meer informatie over hoe Microsoft Defender voor Eindpunt met uw gegevens omgaat, vindt u hier: Microsoft Defender voor opslag en privacy van [eindpuntgegevens.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Bestanden die door veilige documenten worden verzonden, worden niet bewaard in Defender na de tijd die nodig is voor analyse (meestal minder dan 24 uur).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Gebruik het Beveiligings- & compliancecentrum om veilige documenten te configureren

1. Ga in het & Compliancecentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments** en klik vervolgens op **Algemene instellingen.**

2. Configureer **de volgende instellingen** in de algemene instellingen die worden weergegeven:

   - **Veilige documenten voor Office-clients in-** of uitschakelen: Verplaats de schakelknop naar rechts om de functie in te ![ schakelen: Schakelen ](../../media/scc-toggle-on.png) in.

   - **Toestaan dat** personen door de beveiligde weergave kunnen klikken, zelfs als veilige documenten het bestand als schadelijk identificeren: U wordt aangeraden deze optie uitgeschakeld te laten (laat de schakeloptie links: Schakel de schakeloptie ![ ](../../media/scc-toggle-off.png) uit).

   Klik op **Opslaan** wanneer u gereed bent.

   ![Instellingen voor veilige documenten nadat u Globale instellingen op de pagina Veilige bijlagen heeft geselecteerd.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell gebruiken om veilige documenten te configureren

Gebruik de volgende syntaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Met _de parameter EnableSafeDocs_ worden veilige documenten voor de hele organisatie in- of uitgeschakeld.
- Met _de parameter AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave (dat wil zeggen het openen van het document) verlaten als het document is geïdentificeerd als schadelijk.

In dit voorbeeld worden veilige documenten voor de hele organisatie in gebruik en wordt voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk vanuit de beveiligde weergave.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="how-do-i-know-this-worked"></a>Hoe weet ik of dit heeft gewerkt?

Ga als volgt te werk om te controleren of u veilige documenten hebt ingeschakeld en geconfigureerd:

- Ga in het beveiligings- &  compliancecentrum naar Beveiligingsbeheerbeleid \>  \> **ATP-veilige** bijlagen , klik op Algemene  instellingen en controleer of veilige documenten voor **Office-clients** in- en toestaan dat personen door de beveiligde weergave kunnen klikken, zelfs als veilige documenten het bestand identificeren als schadelijke instellingen.

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- De volgende bestanden zijn beschikbaar om de beveiliging van veilige documenten te testen. Deze documenten zijn vergelijkbaar met het EICAR.TXT bestand voor het testen van anti-malware- en anti-virusoplossingen. De bestanden zijn niet schadelijk, maar ze activeren wel de beveiliging van veilige documenten.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)