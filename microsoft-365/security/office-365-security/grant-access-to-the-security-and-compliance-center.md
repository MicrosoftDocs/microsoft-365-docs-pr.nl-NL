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
description: Gebruikers moeten machtigingen krijgen toegewezen in het Microsoft 365 Security & Compliance Center voordat ze een van de beveiligings- of compliancefuncties kunnen beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab02773a19e1b5881858104097b0b03e4385b40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907218"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Gebruikers toegang geven tot het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Gebruikers moeten worden toegewezen machtigingen in het Beveiligings- & compliancecentrum voordat ze een van de beveiligings- of compliancefuncties kunnen beheren. Als globale beheerder of lid van de rollengroep Organisatiebeheer in het beveiligings- & Compliancecentrum, kunt u deze machtigingen aan gebruikers geven. Gebruikers kunnen alleen de beveiligings- of compliancefuncties beheren die u hen toegang geeft.

Voor meer informatie over de verschillende machtigingen die u aan gebruikers kunt geven in het Beveiligings- & Compliancecentrum, raadpleegt u Machtigingen in het Beveiligings- [& Compliancecentrum.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet een globale beheerder zijn of lid zijn van de rollengroep Organisatiebeheer in het beveiligings- & compliancecentrum, om de stappen in dit artikel uit te voeren.

- Rollengroepen voor het beveiligings- & compliancecentrum hebben mogelijk vergelijkbare namen als de rollengroepen in Exchange Online, maar ze zijn niet hetzelfde.

- Lidmaatschappen van rollengroep worden niet gedeeld tussen Exchange Online en het Beveiligings- & Compliancecentrum.

- DAP-partners (Gedelegeerde Toegangsmachtiging) met machtigingen voor Beheer namens (AOBO) hebben geen toegang tot het Beveiligings- & Compliancecentrum.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Het beveiligings- & compliancecentrum gebruiken om een andere gebruiker toegang te geven tot het beveiligings- & compliancecentrum

1. Open het Beveiligingscentrum & compliancecentrum op <https://protection.office.com> en ga naar **Machtigingen.** Als u rechtstreeks naar het tabblad **Machtigingen** wilt gaan, opent u <https://protection.office.com/permissions> .

2. Kies in de lijst met rollengroepen de rollengroep en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) bewerken.

3. Klik op de pagina Eigenschappen van de rollengroep onder **Leden** op Pictogram toevoegen toevoegen en selecteer de naam van de gebruiker ![ (of gebruikers) die u wilt ](../../media/ITPro-EAC-AddIcon.gif) toevoegen.

4. Wanneer u alle gebruikers hebt geselecteerd die u wilt toevoegen aan de rollengroep, klikt u op **Toevoegen en \>** vervolgens OP **OK.**

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Gebruik Security & Compliance Center PowerShell om een andere gebruiker toegang te geven tot het & Compliance Center

1. [Maak verbinding met & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

2. Gebruik de volgende syntaxis:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Zie [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) voor gedetailleerde syntaxis- en parameterproblemen

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u toegang hebt verleend tot het beveiligings- & compliancecentrum, gaat u als volgt te werk:

- Ga in het & Compliancecentrum naar **Machtigingen** en selecteer de rollengroep. Controleer in de flyout details die wordt geopend de leden van de rollengroep.

- Vervang in & PowerShell van het Compliancecentrum door de naam van de rollengroep en \<RoleGroupName\> voer de volgende opdracht uit:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Zie [Get-RoleGroupMember (Get-RoleGroupMember)](/powershell/module/exchange/Get-RoleGroupMember)voor gedetailleerde syntaxis- en parametergegevens.