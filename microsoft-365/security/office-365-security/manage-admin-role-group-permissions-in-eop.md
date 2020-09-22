---
title: Rollen groepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen informatie lezen over het toewijzen of verwijderen van machtigingen in het Exchange-Beheercentrum in Exchange Online Protection.
ms.openlocfilehash: fb1e0979b77c38d852f35817e01135af888eac68
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201899"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Rollengroepen beheren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, kunt u het Exchange-Beheercentrum (SBV) gebruiken om gebruikers toe te voegen aan rollen groepen. Door een gebruiker toe te voegen aan een rollen groep, krijgt u de gebruikersmachtigingen om specifieke beheertaken uit te voeren. U kunt gebruikers ook verwijderen uit rollen groepen.

Zie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen en rollen groepen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Exchange-Beheercentrum door het Exchange- [Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- U opent zelfstandige EOP PowerShell via [verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Specifiek hebt u de rol van rollenbeheer nodig die standaard is toegewezen aan de rollen groep de organizationmanagement (algemene beheerders). Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Problemen? Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-manage-role-groups"></a>Het Beheercentrum gebruiken om rollen groepen te beheren

### <a name="use-the-eac-to-view-role-groups"></a>Het Exchange-Beheercentrum gebruiken om rollen groepen weer te geven

1. Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerdersrollen**. Alle rollen groepen in uw organisatie worden hier vermeld.

2. Selecteer een rollen groep. In het deelvenster Details worden de **naam**, de **Beschrijving**, de **toegewezen rollen**en de **beheerde** rollen weergegeven. U kunt deze informatie ook zien door te **Edit** klikken op het ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Gebruik de functie SBV om rollen groepen te maken

Wanneer u een nieuwe rollen groep maakt, kunt u alle instellingen zelf configureren (tijdens het maken van de groep of na). U kunt ook een bestaande rollen groep kopiëren en deze wijzigen.

1. Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerders**en voer een van de volgende stappen uit:

   - **Handmatig een nieuwe rollen groep maken**: **Add** Klik op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) .

   - **Een bestaande rolgroep kopiëren**: Selecteer de rollen groep die u wilt kopiëren en klik op het pictogram kopiëren **kopiëren** ![ ](../../media/ITPro-EAC-CopyIcon.png) .

2. Configureer de volgende instellingen in het venster **nieuwe rollen groep** dat wordt weergegeven:

    - **Naam**: Voer een unieke naam in voor de rolgroep.

    - **Beschrijving**: Typ een optionele beschrijving voor de rollen groep.

    - **Rollen** **: Klik op** het ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) ofITPro-EAC-RemoveIcon.gif**verwijderen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) om de rollen te selecteren of te wijzigen die zijn toegewezen aan de rollen groep.

    - **Leden** **: Klik op** het ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) ofITPro-EAC-RemoveIcon.gif**verwijderen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) om het lidmaatschap van de rollen groep te wijzigen.

3. Wanneer u klaar bent, klikt u op **Opslaan** om de rollen groep te maken.

### <a name="use-the-eac-to-modify-role-groups"></a>Het Exchange-rollencentrum gebruiken om rollen groepen te wijzigen

Ga in het Exchange-Beheercentrum naar **machtigingen voor machtigingen** \> **beheerders**, selecteer de groep rollen die u wilt wijzigen en **Edit** klik vervolgens op ![ bewerken ](../../media/ITPro-EAC-EditIcon.png) .

De opties zijn alleen beschikbaar wanneer u Rolgroepen aanpast wanneer u rollen groepen maakt. U kunt:

- Wijzig de naam en beschrijving.

- Beheerrollen toevoegen en verwijderen (rollen toewijzingen maken of verwijderen).

- Leden toevoegen en verwijderen.

**Opmerking**: Sommige rollen groepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep kunt verwijderen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Werken met de lijst met wijzigingen in de lijst met leden van rollen groepen

1. Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerdersrollen**, selecteer de rolgroep die u wilt wijzigen en klik vervolgens op **Edit** ![ bewerken ](../../media/ITPro-EAC-EditIcon.png) .

2. Ga op een van de volgende manieren te werk in de sectie **leden** op de pagina eigenschappen van rollen groep:

   - Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Zoek op de pagina die wordt weergegeven de gebruiker die wou wilt toevoegen en klik vervolgens op **add->**. Selecteer gebruikers en klik zo nodig op **>** vaak. Wanneer u klaar bent, klikt u op **OK**.

   - Selecteer de gebruikers die u **wilt verwijderen en klik op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klik op **Opslaan** wanneer u gereed bent.

   > [!NOTE]
   > Gebruikers moeten zich mogelijk afmelden en opnieuw aanmelden om de wijziging in de beheerdersbevoegdheid te zien nadat u leden toevoegt of verwijdert uit de rolgroep.

### <a name="use-the-eac-to-remove-role-groups"></a>De rollen groepen verwijderen via het Exchange-Beheercentrum

U kunt ingebouwde rollen groepen niet verwijderen, maar u kunt wel aangepaste Rolgroepen verwijderen die u hebt gemaakt.

1. Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerdersrollen**.

2. Selecteer de rollen groep die u wilt verwijderen en **Klik op** ![ verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klik op **Ja** in het bevestigingsvenster dat wordt weergegeven.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell gebruiken om rollen groepen te beheren

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Standalone EOP PowerShell gebruiken om rollen groepen weer te geven

Gebruik de volgende syntaxis om een rollen groep weer te geven:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In dit voorbeeld wordt een overzichtslijst met alle rollen groepen geretourneerd.

```PowerShell
Get-RoleGroup
```

In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de rollen groep met de naam beheerders van de beheerder.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In het volgende voorbeeld worden alle rollen groepen opgevraagd waarvan de gebruiker Julia lid is. U moet de DN-waarde (Distinguished Name) gebruiken voor Julia, die u kunt vinden door de opdracht uit te voeren: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Zie [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Standalone EOP PowerShell gebruiken om rollen groepen te maken

Wanneer u een nieuwe rollen groep maakt, kunt u alle instellingen handmatig configureren (tijdens het maken van de groep of na). U kunt ook een bestaande rollen groep kopiëren en deze wijzigen.

- Als u handmatig een nieuwe rollen groep wilt maken, gebruikt u de volgende syntaxis:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Met de parameter _roles_ worden de management rollen opgegeven die aan de rollen groep moeten worden toegewezen met behulp van de volgende syntaxis `"Role1","Role1",..."RoleN"` . U kunt de beschikbare rollen zien met behulp van de cmdlet **Get-ManagementRole** .

  - Met de parameter parameters worden de leden van de rollen groep opgegeven met behulp _van de volgende_ syntaxis: `"Member1","Member2",..."MemberN"` . U kunt gebruikers opgeven, universele beveiligingsgroepen voor e-mail (USGs) of andere Rolgroepen (beveiligings-principals).

  In dit voorbeeld wordt een nieuwe rollen groep met de naam ' beperkte ontvanger beheer ' gemaakt met de volgende instellingen:

  - De rol van e-mail geadresseerden is toegewezen aan de groep rollen.

  - De gebruikers Kim en Martin worden toegevoegd als leden.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Voer de volgende stappen uit om een bestaande rollen groep te kopiëren:

  1. Sla de rollen groep op die u in een variabele wilt kopiëren met behulp van de volgende syntaxis:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Maak als volgt de nieuwe rollen groep met de volgende syntaxis:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Met de parameter parameters worden de leden van de rollen groep opgegeven met behulp _van de volgende_ syntaxis: `"Member1","Member2",..."MemberN"` . U kunt gebruikers opgeven, universele beveiligingsgroepen voor e-mail (USGs) of andere Rolgroepen (beveiligings-principals).

     In dit voorbeeld wordt de rollen groep Organisatiebeheer naar de nieuwe rollen groep met de naam ' beperkte Organisatiebeheer ' gekopieerd. De leden van de rollen groep zijn Isabelle, Carter en Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Voor gedetailleerde syntaxis-en parameterinformatie, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Standalone EOP PowerShell gebruiken de lijst met leden in rollen groepen wijzigen

- Met de cmdlet **add-RoleGroupMember** en **Remove-RoleGroupMember** worden afzonderlijke leden één voor één toegevoegd of verwijderd. Met de cmdlet **Update-RoleGroupMember** kunt u de bestaande lijst met leden vervangen of wijzigen.

- De leden van een rollen groep kunnen gebruikers zijn, universele beveiligingsgroepen voor e-mail (USGs) of andere rollen groepen (beveiligings-principals).

Gebruik de volgende syntaxis om de leden van een rollen groep te wijzigen:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Als u de bestaande lijst met leden wilt _vervangen_ door de waarden die u opgeeft, gebruikt u de volgende syntaxis: `"Member1","Member2",..."MemberN"` .

- Als u de bestaande lijst met leden _selectief wilt wijzigen_ , gebruikt u de volgende syntaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In dit voorbeeld worden alle huidige leden van de rollen groep Help Desk vervangen door de opgegeven gebruikers.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Valeria Barrio verwijderd uit de lijst met leden van de rollen groep van de Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Zie [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Standalone EOP PowerShell gebruiken om rollen groepen te verwijderen

U kunt ingebouwde rollen groepen niet verwijderen, maar u kunt wel aangepaste Rolgroepen verwijderen die u hebt gemaakt.

Als u een aangepaste rollen groep wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In dit voorbeeld wordt de rollen groep training beheerders verwijderd.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Zie [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een van de volgende stappen uit om te controleren of u een rollen groep hebt gekopieerd:

- Ga in het Exchange-Beheercentrum naar **machtigingen** \> **beheerders**en controleer of de rollen groep wel of niet wordt weergegeven. Selecteer de groep rollen, Controleer de instellingen in het detailvenster of klik op **Edit** ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-EditIcon.png) om de instellingen te controleren.

- In Exchange Online PowerShell vervangt u \<Role Group Name\> de naam van de rolgroep en voert u de volgende opdracht uit om te controleren of de rollen groep bestaat (of niet bestaat) en controleert u de instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
