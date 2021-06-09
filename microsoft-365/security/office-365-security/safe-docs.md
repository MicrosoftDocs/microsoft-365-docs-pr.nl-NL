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
description: Meer informatie over Safe documenten in Microsoft 365 E5 of Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644750"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Veilige documenten in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Safe Documenten is een functie in Microsoft 365 E5 of Microsoft 365 E5 Security die [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor Eindpunt gebruikt om documenten en bestanden te scannen die [worden](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) geopend in de beveiligde weergave of Application Guard voor [Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Safe Documenten zijn alleen beschikbaar voor gebruikers met *Microsoft 365 E5* of *Microsoft 365 E5 Security* licenties. Deze licenties zijn niet opgenomen in Microsoft Defender voor Office 365 abonnementen.

- Safe Documenten wordt ondersteund in Microsoft 365-apps voor ondernemingen (voorheen bekend als Office 365 ProPlus) versie 2004 of hoger.

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com>. Als u rechtstreeks naar de **pagina ATP-Safe bijlagen** wilt gaan, opent u <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u Safe documenteninstellingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot Safe documenteninstellingen, moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

### <a name="how-does-microsoft-handle-your-data"></a>Hoe gaat Microsoft om met uw gegevens?

Om u te beschermen, Safe documenten bestanden naar de [Microsoft Defender voor Eindpunt-cloud](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor analyse. Meer informatie over hoe Microsoft Defender voor Eindpunt met uw gegevens omgaat, vindt u hier: Microsoft Defender voor opslag en privacy van [eindpuntgegevens.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Bestanden die door Safe Documenten worden niet bewaard in Defender na de tijd die nodig is voor analyse (meestal minder dan 24 uur).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Gebruik het Beveiligings- & compliancecentrum om documenten Safe configureren

1. Ga in het & Beveiligingscentrum naar **ATP** voor bedreigingsbeleid Safe \>  \> **bijlagen** en klik vervolgens op **Algemene instellingen.**

2. Configureer **de volgende instellingen** in de algemene instellingen die worden weergegeven:

   - **Schakel Safe documenten in voor Office clients:** Verplaats de schakelknop naar rechts om de functie in te ![ schakelen: In- of ](../../media/scc-toggle-on.png) uitschakelen.

   - **Toestaan dat** personen door de beveiligde weergave kunnen klikken, zelfs als Safe Documenten het bestand als schadelijk identificeert: U wordt aangeraden deze optie uit te schakelen (laat de schakeloptie links staan: Schakel de schakeloptie ![ ](../../media/scc-toggle-off.png) uit).

   Klik op **Opslaan** wanneer u gereed bent.

   ![Safe Documenteninstellingen nadat u Globale instellingen op de pagina Safe bijlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>PowerShell Exchange Online gebruiken om documenten Safe configureren

Gebruik de volgende syntaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Met _de parameter EnableSafeDocs_ worden Safe documenten voor de hele organisatie in- of uitgeschakeld.
- Met _de parameter AllowSafeDocsOpen_ kunnen of voorkomen dat gebruikers de beveiligde weergave (dat wil zeggen het openen van het document) verlaten als het document is geïdentificeerd als schadelijk.

In dit voorbeeld kunt Safe documenten voor de hele organisatie gebruiken en voorkomen dat gebruikers documenten openen die zijn geïdentificeerd als schadelijk vanuit de beveiligde weergave.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities

Als u Microsoft Defender voor Eindpunt wilt implementeren, moet u de verschillende fasen van de implementatie doorlopen. Na onboarding kunt u auditfuncties configureren in het beveiligings- & compliancecentrum.

Zie Onboard to the Microsoft Defender for Endpoint service (Onboard [to the Microsoft Defender for Endpoint service)](/microsoft-365/security/defender-endpoint/onboarding)voor meer informatie. Als u extra hulp nodig hebt, raadpleegt u Microsoft Defender oplossen voor problemen met de [onboarding van eindpunten.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)

### <a name="how-do-i-know-this-worked"></a>Hoe weet ik of dit heeft gewerkt?

Als u wilt controleren of u documenten hebt ingeschakeld en geconfigureerd Safe documenten, gaat u als volgt te werk:

- Ga in het Beveiligings- & Compliancecentrum naar ATP Safe Bijlagen voor  \>  \> **bedreigingsbeleid,**   klik op Algemene instellingen en controleer de Safe-documenten in- en uitschakelen voor **Office-clients** en Laat personen door de beveiligde weergave klikken, zelfs als Safe Documenten het bestand identificeert als schadelijke instellingen.

- Voer de volgende opdracht uit in Exchange Online PowerShell en controleer de eigenschapswaarden:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- De volgende bestanden zijn beschikbaar om de Safe documenten te testen. Deze documenten zijn vergelijkbaar met het EICAR.TXT bestand voor het testen van anti-malware- en anti-virusoplossingen. De bestanden zijn niet schadelijk, maar ze worden wel Safe documentenbeveiliging.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
