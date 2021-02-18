---
title: Gebruikers toegang geven tot het beveiligings- & compliancecentrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gebruikers moeten machtigingen toegewezen krijgen in het Microsoft 365-beveiligings- & compliancecentrum voordat ze de beveiligings- of nalevingsfuncties kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289875"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Gebruikers toegang geven tot het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Gebruikers moeten machtigingen toegewezen krijgen in het beveiligings- & voordat ze de beveiligings- of nalevingsfuncties kunnen beheren. Als globale beheerder of lid van de rollengroep OrganizationManagement in het beveiligings- & compliancecentrum kunt u deze machtigingen aan gebruikers verlenen. Gebruikers kunnen alleen de beveiligings- of nalevingsfuncties beheren die u hen toegang geeft.

Raadpleeg machtigingen in het beveiligings- & compliancecentrum voor meer informatie over de verschillende machtigingen die u gebruikers kunt geven in het beveiligings- & [compliancecentrum.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet een globale beheerder of lid zijn van de rollengroep OrganizationManagement in het beveiligings- & compliancecentrum om de stappen in dit artikel te kunnen voltooien.

- Rollengroepen voor het & compliancecentrum hebben mogelijk vergelijkbare namen als de rollengroepen in Exchange Online, maar deze zijn niet hetzelfde.

- Lidmaatschappen van rollengroep worden niet gedeeld tussen Exchange Online en het & Compliancecentrum.

- DAP-partners (Gedelegeerde toegangsmachtiging) met AOBO-machtigingen (Administer On Behalf Of) hebben geen toegang tot het beveiligings- & Compliancecentrum.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Het beveiligings- & compliancecentrum gebruiken om een andere gebruiker toegang te geven tot het & compliancecentrum

1. Open het & compliancecentrum en <https://protection.office.com> ga naar **Machtigingen.** Als u rechtstreeks naar het **tabblad Machtigingen wilt** gaan, opent u <https://protection.office.com/permissions> .

2. Kies de rollengroep in de lijst met rollengroepen en klik op **het pictogram** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Bewerken.

3. Klik op de eigenschappenpagina van de rollengroep onder **Leden** op Pictogram toevoegen en selecteer de naam van de gebruiker ![ ](../../media/ITPro-EAC-AddIcon.gif) (of gebruikers) die u wilt toevoegen.

4. Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollengroep, klikt u op **Toevoegen en \>** vervolgens op **OK.**

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>PowerShell voor & beveiligingscentrum gebruiken om een andere gebruiker toegang te geven tot het & compliancecentrum

1. [Maak verbinding met beveiligings & Compliancecentrum PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Gebruik de volgende syntaxis:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Zie [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) voor gedetailleerde problemen met de syntaxis en parameter

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u toegang hebt verleend tot het beveiligings- & compliancecentrum, gaat u op een van de volgende stappen te werk:

- Ga in het & Compliancecentrum naar **Machtigingen** en selecteer de rollengroep. Controleer in de flyout met details die wordt geopend de leden van de rollengroep.

- Vervang in & Compliancecentrum PowerShell door de naam van de rollengroep en voer \<RoleGroupName\> de volgende opdracht uit:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Zie [Get-RoleGroupMember voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)
