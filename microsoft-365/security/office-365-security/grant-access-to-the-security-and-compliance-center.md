---
title: Geef gebruikers toegang tot het Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gebruikers moeten machtigingen krijgen toegewezen in het Microsoft 365 Security & Compliance Center voordat ze een van de beveiligings- of nalevingsfuncties kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfded9d3f75f57eca1097fec6f18dc55410b65fb
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616972"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Geef gebruikers toegang tot het Security & Compliance Center

Gebruikers moeten machtigingen krijgen toegewezen in het Security & Compliance Center voordat ze een van de beveiligings- of nalevingsfuncties kunnen beheren. Als globale beheerder of lid van de rolgroep OrganizationManagement in het Security & Compliance Center u deze machtigingen aan gebruikers geven. Gebruikers kunnen alleen de beveiligings- of nalevingsfuncties beheren waar u hen toegang toe geeft.

Raadpleeg [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over de verschillende machtigingen die u aan gebruikers geven in het Security & Compliance Center.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet een globale beheerder of lid zijn van de rolgroep OrganizationManagement in het Security & Compliance Center, om de stappen in dit artikel te voltooien.

- Rolgroepen voor het Security & Compliance Center hebben mogelijk vergelijkbare namen als de rolgroepen in Exchange Online, maar ze zijn niet hetzelfde.

- Lidmaatschappen van rolgroepen worden niet gedeeld tussen Exchange Online en het Security & Compliance Center.

- Gedelegeerde toegangsmachtiging (DAP) partners met Beheerde Naamgeving (AOBO) machtigingen hebben geen toegang tot het Security & Compliance Center.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Gebruik het beheercentrum om een andere gebruiker toegang te geven tot het Security & Compliance Center

1. [Meld u aan en ga naar het beheercentrum](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Open in het Microsoft 365-beheercentrum **Beheercentra** en klik vervolgens op **Beveiliging & Compliance**.

3. Ga in het Security & Compliance Center naar **Machtigingen**.

4. Kies in de lijst de rolgroep waaraan u de gebruiker wilt toevoegen en **klik** op ![ pictogram Bewerken bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

5. Klik op de eigenschappenpagina van de rolgroep onder **Leden**op **Add** ![ Pictogram toevoegen en selecteer ](../../media/ITPro-EAC-AddIcon.gif) de naam van de gebruiker (of gebruikers) die u wilt toevoegen.

6. Wanneer u alle gebruikers hebt geselecteerd die u aan de rolgroep wilt toevoegen, klikt u op ** \> Toevoegen** en vervolgens **op OK**.

7. Klik **op Opslaan** om de wijzigingen in de rolgroep op te slaan.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

1. Ga in het Security & Compliance Center naar **Machtigingen**.

2. Selecteer in de lijst de rolgroep om de leden weer te geven.

3. Rechts, in de details van de rolgroep, u de leden van de rolgroep bekijken.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>PowerShell gebruiken om een andere gebruiker toegang te geven tot het Security & Compliance Center

1. [Maak verbinding met PowerShell & Security-&.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Gebruik de opdracht **Add-RoleGroupMember** om een gebruiker toe te voegen aan de rol organisatiebeheer, zoals in het volgende voorbeeld wordt weergegeven.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parameters**:

   - _Identiteit_ is de rolgroep waaraan een lid moet worden toegevoegd.

   - _Lid_ is het postvak, universal security group (USG) of computer om toe te voegen aan de rolgroep. U slechts één lid tegelijk opgeven.

Zie [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)voor gedetailleerde informatie over syntaxis en parameters .

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u gebruikers toegang hebt gegeven tot het Security & Compliance Center, gebruikt u de **cmdlet Get-RoleGroupMember** om de leden in de rolgroep Organisatiebeheer weer te geven, zoals in het volgende voorbeeld wordt weergegeven.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Zie [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)voor gedetailleerde informatie over syntaxis en parameters .
