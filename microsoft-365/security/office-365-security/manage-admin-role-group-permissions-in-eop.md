---
title: Rollengroepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen informatie krijgen over het toewijzen of verwijderen van machtigingen in het Exchange-beheercentrum (EAC) in Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289923"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Rollengroepen beheren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunt u het Exchange-beheercentrum (EAC) gebruiken om gebruikers toe te voegen aan rollengroepen. Als u een gebruiker toevoegt aan een rollengroep, krijgt de gebruiker machtigingen om specifieke beheertaken uit te voeren. U kunt gebruikers ook verwijderen uit rollengroepen.

Zie Machtigingen in de zelfstandige EOP voor meer informatie over rollen en [rollengroepen.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Exchange-beheercentrum (EAC) wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie Connect to Exchange Online Protection PowerShell (Verbinding [maken met Exchange Online Protection PowerShell)](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)als u de zelfstandige EOP PowerShell wilt openen.

- U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de **rol Rollenbeheer**  nodig, die standaard is toegewezen aan de rollengroep Organisatiebeheer. Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Hebt u problemen? Vraag om hulp op het forum [van Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-manage-role-groups"></a>Het EAC gebruiken om rollengroepen te beheren

### <a name="use-the-eac-to-view-role-groups"></a>Het EAC gebruiken om rollengroepen weer te geven

1. Ga in het Exchange-beheercentrum naar **Beheerdersrollen** \> **voor machtigingen.** Alle rollengroepen in uw organisatie worden hier vermeld.

2. Selecteer een rollengroep. Het deelvenster Details bevat **de naam,** **beschrijving,** **toegewezen rollen** en beheerd **door** de rollengroep. U kunt deze informatie ook zien door op het **pictogram** Bewerken ![ te ](../../media/ITPro-EAC-EditIcon.png) klikken.

### <a name="use-the-eac-to-create-role-groups"></a>Het EAC gebruiken om rollengroepen te maken

Wanneer u een nieuwe rollengroep maakt, kunt u alle instellingen zelf configureren (tijdens het maken van de groep of er daarna). U kunt ook een bestaande rollengroep kopiëren en wijzigen.

1. Ga in het Exchange-beheercentrum naar de rollen **van Machtigingenbeheerder** \> en ga vervolgens op een van de volgende stappen te werk:

   - **Maak handmatig een nieuwe rollengroep:** klik op **het pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen.

   - **Een bestaande rollengroep kopiëren:** Selecteer de rollengroep die u wilt kopiëren en klik op **het pictogram** ![ ](../../media/ITPro-EAC-CopyIcon.png) Kopiëren.

2. Configureer **de volgende instellingen** in het venster Nieuwe rollengroep dat wordt weergegeven:

    - **Naam:** voer een unieke naam in voor de rollengroep.

    - **Beschrijving:** voer een optionele beschrijving in voor de rollengroep.

    - **Rollen:** klik op **het pictogram** Toevoegen of verwijderen om de rollen te selecteren of te wijzigen die aan de ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rollengroep zijn toegewezen.

    - **Leden:** klik op **het pictogram** Toevoegen of ![ het ](../../media/ITPro-EAC-AddIcon.png) **pictogram** Verwijderen om het lidmaatschap van ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) rollengroep te wijzigen.

3. Wanneer u klaar bent, klikt u op **Opslaan om** de rollengroep te maken.

### <a name="use-the-eac-to-modify-role-groups"></a>Het EAC gebruiken om rollengroepen te wijzigen

Ga in het Exchange-beheercentrum naar Rollen **van machtigingenbeheerder,** selecteer de rollengroep die u wilt wijzigen en klik vervolgens op \>  **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken.

Dezelfde opties zijn beschikbaar wanneer u rollengroepen wijzigt als wanneer u rollengroepen maakt. U kunt:

- Wijzig de naam en beschrijving.

- Beheerrollen toevoegen en verwijderen (roltoewijzingen maken of verwijderen).

- Leden toevoegen en verwijderen.

**Opmerking:** sommige rollengroepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep kunt verwijderen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>De lijst met leden in rollengroepen wijzigen met het EAC

1. Ga in het Exchange-beheercentrum naar Rollen **van machtigingenbeheerder,** selecteer de rollengroep die u wilt wijzigen en klik vervolgens op \>  **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken.

2. Ga op een van de volgende  stappen te werk op de pagina eigenschappen van rollengroep die wordt geopend in de sectie Leden:

   - Klik **op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek op de pagina die wordt weergegeven de gebruiker die u wilt toevoegen en klik op **->.** Selecteer gebruikers en klik **zo vaak** als nodig >toevoegen. Klik op OK wanneer u **klaar bent.**

   - Selecteer de gebruikers die u wilt verwijderen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

3. Klik op **Opslaan** wanneer u gereed bent.

   > [!NOTE]
   > Gebruikers moeten zich mogelijk afloggen en opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toevoegt aan of verwijderd uit de rollengroep.

### <a name="use-the-eac-to-remove-role-groups"></a>Het EAC gebruiken om rollengroepen te verwijderen

U kunt ingebouwde rollengroepen niet verwijderen, maar u kunt wel aangepaste rollengroepen verwijderen die u hebt gemaakt.

1. Ga in het Exchange-beheercentrum naar **Beheerdersrollen** \> **voor machtigingen.**

2. Selecteer de rollengroep die u wilt verwijderen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

3. Klik **op Ja** in het bevestigingsvenster dat wordt weergegeven.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell gebruiken om rollengroepen te beheren

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rollengroepen weer te geven

Gebruik de volgende syntaxis om een rollengroep weer te geven:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In dit voorbeeld wordt een overzichtslijst van alle rollengroepen weergegeven.

```PowerShell
Get-RoleGroup
```

In dit voorbeeld wordt gedetailleerde informatie gegeven over de rollengroep met de naam Ontvangersbeheerders.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In dit voorbeeld worden alle rollengroepen als retourneert waar de gebruiker Julia lid van is. U moet de DN-waarde (DistinguishedName) voor Julia gebruiken, die u kunt vinden door de opdracht uit te `Get-User -Identity Julia | Format-List DistinguishedName` voeren:

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Zie [Get-RoleGroup voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rollengroepen te maken

Wanneer u een nieuwe rollengroep maakt, kunt u alle instellingen handmatig configureren (tijdens het maken van de groep of er waarna). U kunt ook een bestaande rollengroep kopiëren en wijzigen.

- Gebruik de volgende syntaxis om handmatig een nieuwe rollengroep te maken:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Met de parameter _Rollen_ worden de beheerrollen opgegeven die moeten worden toegewezen aan de rollengroep met behulp van de volgende `"Role1","Role1",..."RoleN"` syntaxis. U kunt de beschikbare rollen zien met behulp van de cmdlet **Get-ManagementRole.**

  - De parameter _Leden_ geeft de leden van de rollengroep aan met behulp van de volgende `"Member1","Member2",..."MemberN"` syntaxis: U kunt gebruikers, usgs (mail-enabled universal security groups) of andere rollengroepen (security principals) opgeven.

  In dit voorbeeld wordt een nieuwe rollengroep met de naam Beperkt beheer van geadresseerden gemaakt met de volgende instellingen:

  - De rol E-mailontvangers wordt toegewezen aan de rollengroep.

  - De gebruikers Kim en Martin worden toegevoegd als leden.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Ga als volgt te werk om een bestaande rollengroep te kopiëren:

  1. Sla de rollengroep die u wilt kopiëren op in een variabele met behulp van de volgende syntaxis:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Maak de nieuwe rollengroep met behulp van de volgende syntaxis:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     De parameter _Leden_ geeft de leden van de rollengroep aan met behulp van de volgende `"Member1","Member2",..."MemberN"` syntaxis: U kunt gebruikers, usgs (mail-enabled universal security groups) of andere rollengroepen (security principals) opgeven.

     In dit voorbeeld wordt de rollengroep Organisatiebeheer gekopieerd naar de nieuwe rollengroep genaamd Beperkt organisatiebeheer. De leden van de rollengroep zijn Aek, Deze en Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Voor gedetailleerde syntaxis- en parameterinformatie, [New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>De lijst met leden in rollengroepen wijzigen met zelfstandige EOP PowerShell

- Met de cmdlets **Add-RoleGroupMember** en **Remove-RoleGroupMember** kunt u afzonderlijke leden een voor een toevoegen of verwijderen. De **cmdlet Update-RoleGroupMember** kan de bestaande lijst met leden vervangen of wijzigen.

- De leden van een rollengroep kunnen gebruikers, USG's (Universal Security Groups) met e-mail of andere rollengroepen (beveiligings-principals) zijn.

Gebruik de volgende syntaxis om de leden van een rollengroep te wijzigen:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Gebruik _de_ volgende syntaxis om de bestaande lijst met leden te vervangen door de waarden die u opgeeft: `"Member1","Member2",..."MemberN"`

- Gebruik _de volgende_ syntaxis om de bestaande lijst met leden selectief te wijzigen: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`

In dit voorbeeld worden alle huidige leden van de rollengroep Helpdesk vervangen door de opgegeven gebruikers.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Wordt Erdodo verwijderd uit de lijst met leden van de rollengroep Helpdesk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Zie [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rollengroepen te verwijderen

U kunt ingebouwde rollengroepen niet verwijderen, maar u kunt wel aangepaste rollengroepen verwijderen die u hebt gemaakt.

Gebruik de volgende syntaxis om een aangepaste rollengroep te verwijderen:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In dit voorbeeld wordt de rollengroep Trainingsbeheerders verwijderd.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Zie [Remove-RoleGroup voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende stappen te werk om te controleren of u een rollengroep hebt gekopieerd:

- Ga in het Exchange-beheercentrum naar Beheerdersrollen voor machtigingen en controleer of de rollengroep wordt vermeld  \> (of niet wordt weergegeven). Selecteer de rollengroep en controleer de instellingen  in het deelvenster Details of klik op het ![ pictogram Bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) controleren.

- Vervang in Exchange Online PowerShell door de naam van de rollengroep en voer de volgende opdracht uit om te controleren of de rollengroep bestaat (of bestaat niet) en controleer de \<Role Group Name\> instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
