---
title: Gebruikers toegang geven tot de beveiligings & nalevings centrum
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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gebruikers moeten zijn toegewezen machtigingen in het Microsoft 365-beveiligings & nalevings centrum voordat ze de functies voor beveiliging of compliance kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b51007221257b9adac46c31295e13b20b12342ab
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868919"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Gebruikers toegang geven tot de beveiligings & nalevings centrum

Gebruikers moeten zijn toegewezen aan de beveiligings & compliance Center voordat ze de functies voor beveiliging of compliance kunnen beheren. Als globale beheerder of als lid van de de organizationmanagement-rollen groep in het Beveiligingscentrum beveiligings &, kunt u deze machtigingen aan gebruikers verlenen. Gebruikers kunnen alleen de functies voor beveiliging en compliance beheren waartoe u ze toegang geeft.

Als u meer wilt weten over de verschillende machtigingen die u aan gebruikers kunt geven in het compliance-& Beveiligingscentrum, raadpleegt u [machtigingen in het beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet een globale beheerder of een lid van de rollen groep de organizationmanagement in het Beveiligingscentrum voor beveiliging & om de stappen in dit artikel uit te voeren.

- Rollen groepen voor de beveiligings & nalevings centrum kunnen soortgelijke namen hebben voor groepen met rollen in Exchange Online, maar ze zijn niet hetzelfde.

- Lidmaatschap van rollen groepen worden niet gedeeld tussen Exchange Online en de beveiligings & nalevings centrum.

- Machtigingen voor gedelegeerde toegangsmachtigingen (DAP) met de machtiging beheren namens (AOBO) hebben geen toegang tot de beveiligings & nalevings centrum.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Met behulp van het beveiligings & nalevings centrum kunt u een andere gebruiker toegang geven tot de beveiligings & nalevings centrum

1. Open het beveiligings & nalevings centrum aan <https://protection.office.com> en ga vervolgens naar **machtigingen**. Ga direct naar het tabblad **machtigingen** en open <https://protection.office.com/permissions> .

2. Kies in de lijst met rollen groepen de rollen groep en klik vervolgens op het **Edit** ![ pictogram bewerken bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. Klik op de pagina eigenschappen van rollen groep **Members**, onder leden **, op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.gif) en selecteer de naam van de gebruiker (s) die u wilt toevoegen.

4. Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollen groep, klikt u op **toevoegen \> ** en vervolgens op **OK**.

5. Wanneer u gereed bent, klikt u op **Opslaan**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Beveiligings & PowerShell gebruiken om een andere gebruiker toegang te geven tot de beveiligings & nalevings centrum

1. [Maak verbinding met beveiliging & nalevings centrum voor PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Gebruik de volgende syntaxis:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Zie [add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) voor gedetailleerde syntaxis-en Parameterproblemen.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Voer een van de volgende stappen uit om te controleren of u toegang hebt tot de beveiligings & nalevings centrum:

- Ga in het beveiligings & nalevings centrum naar **machtigingen** en selecteer de rolgroep. Controleer de leden van de groep rollen in het flyout Details dat wordt geopend. 

- In het beveiligings & nalevings centrum voor PowerShell, vervangt u \<RoleGroupName\> de naam van de rolgroep en voert u de volgende opdracht uit:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Zie [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)voor gedetailleerde syntaxis-en parameterinformatie.
