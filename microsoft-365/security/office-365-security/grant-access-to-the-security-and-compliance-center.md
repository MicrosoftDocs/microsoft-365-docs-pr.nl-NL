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
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826599"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Gebruikers toegang geven tot de beveiligings & nalevings centrum

Gebruikers moeten zijn toegewezen aan de beveiligings & compliance Center voordat ze de functies voor beveiliging of compliance kunnen beheren. Als globale beheerder of als lid van de de organizationmanagement-rollen groep in het Beveiligingscentrum beveiligings &, kunt u deze machtigingen aan gebruikers verlenen. Gebruikers kunnen alleen de functies voor beveiliging en compliance beheren waartoe u ze toegang geeft.

Als u meer wilt weten over de verschillende machtigingen die u aan gebruikers kunt geven in het compliance-& Beveiligingscentrum, raadpleegt u [machtigingen in het beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet een globale beheerder of een lid van de rollen groep de organizationmanagement in het Beveiligingscentrum voor beveiliging & om de stappen in dit artikel uit te voeren.

- Rollen groepen voor de beveiligings & nalevings centrum kunnen soortgelijke namen hebben voor groepen met rollen in Exchange Online, maar ze zijn niet hetzelfde.

- Lidmaatschap van rollen groepen worden niet gedeeld tussen Exchange Online en de beveiligings & nalevings centrum.

- Machtigingen voor gedelegeerde toegangsmachtigingen (DAP) met de machtiging beheren namens (AOBO) hebben geen toegang tot de beveiligings & nalevings centrum.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Met het Beheercentrum kunt u een andere gebruiker toegang geven tot de beveiligings & nalevings centrum

1. [Meld u aan en ga naar het Beheercentrum](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Open in het Microsoft 365-Beheercentrum **beheer centra** en klik vervolgens op **beveiliging & naleving**.

3. Ga in het beveiligings & nalevings centrum naar **machtigingen**.

4. Kies in de lijst de rollen groep waaraan u de gebruiker wilt toevoegen en klik op het **Edit** ![ pictogram bewerken bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

5. Klik op de pagina eigenschappen van rollen groep **Members**, onder leden **, op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.gif) en selecteer de naam van de gebruiker (s) die u wilt toevoegen.

6. Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollen groep, klikt u op **toevoegen \> ** en vervolgens op **OK**.

7. Klik op **Opslaan** om de wijzigingen in de groep rollen op te slaan.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

1. Ga in het beveiligings & nalevings centrum naar **machtigingen**.

2. Selecteer in de lijst de rollen groep om de leden weer te geven.

3. Aan de rechterkant, in de groep Details van rollen, kunt u de leden van de groep rollen weergeven.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>PowerShell gebruiken om een andere gebruiker toegang te geven tot de beveiligings & nalevings centrum

1. [Maak verbinding met beveiliging & nalevings centrum voor PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Gebruik de opdracht **add-RoleGroupMember** om een gebruiker toe te voegen aan de rol van Organisatiebeheer, zoals in het volgende voorbeeld wordt weergegeven.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parameters**:

   - _Identiteit_ is de rollen groep waaraan u een lid wilt toevoegen.

   - _Lid_ is het postvak, de universele beveiligingsgroep (USG) of de computer die u wilt toevoegen aan de rollen groep. U kunt slechts één lid tegelijk opgeven.

Zie [add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)voor meer informatie over de syntaxis en parameters.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de gebruiker toegang wilt geven tot de beveiligings & nalevings centrum, gebruikt u de cmdlet **Get-RoleGroupMember** om de leden in de rollen groep Organisatiebeheer weer te geven, zoals in het volgende voorbeeld wordt weergegeven.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Zie [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)voor meer informatie over de syntaxis en parameters.
