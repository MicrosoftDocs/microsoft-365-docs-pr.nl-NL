---
title: Rolgroepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen leren hoe u machtigingen toewijzen of verwijderen in het Exchange-beheercentrum (EAC) in Exchange Online Protection.
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616512"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Rollengroepen beheren in standalone EOP

In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken u het Exchange-beheercentrum (EAC) gebruiken om gebruikers toe te voegen aan rolgroepen. Als u een gebruikers toevoegt aan een rolgroep, krijgt de gebruiker toestemming om specifieke beheerderstaken uit te voeren. U gebruikers ook uit rolgroepen verwijderen.

Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen en rolgroepen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum (EAC) wilt openen.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)als u zelfstandige EOP PowerShell wilt openen.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt in het bijzonder de rol Rolbeheer nodig, die standaard is toegewezen aan de rolgroep Organisatiebeheer (globale beheerders). Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-manage-role-groups"></a>De EAC gebruiken om rolgroepen te beheren

### <a name="use-the-eac-to-view-role-groups"></a>De EAC gebruiken om rolgroepen weer te geven

1. Ga in de EAC naar **machtigingen** \> **admin rollen**. Alle rolgroepen in uw organisatie worden hier vermeld.

2. Selecteer een rolgroep. In het deelvenster Details wordt de **naam**, **beschrijving**, **toegewezen rollen**en Beheerd **door** de rolgroep weergegeven. U deze informatie ook zien door op pictogram **Bewerken** bewerken te ![ ](../../media/ITPro-EAC-EditIcon.png) klikken.

### <a name="use-the-eac-to-create-role-groups"></a>De EAC gebruiken om rolgroepen te maken

Wanneer u een nieuwe rolgroep maakt, u alle instellingen zelf configureren (tijdens het maken van de groep of erna). U ook een bestaande rolgroep kopiëren en wijzigen.

1. Ga in de EAC naar rollen **machtigingenbeheer** \> **Admin roles**en voer een van de volgende stappen uit:

   - **Maak handmatig een nieuwe rolgroep:** Klik op pictogram Toevoegen **toevoegen** ![ ](../../media/ITPro-EAC-AddIcon.png) .

   - **Een bestaande rolgroep kopiëren:** selecteer de rolgroep die u wilt kopiëren en **klik** vervolgens op ![ pictogram Kopiëren kopiëren ](../../media/ITPro-EAC-CopyIcon.png) .

2. Configureer in het venster **Nieuwe rolgroep** dat wordt weergegeven de volgende instellingen:

    - **Naam**: Voer een unieke naam in voor de rolgroep.

    - **Beschrijving**: Voer een optionele beschrijving in voor de rolgroep.

    - **Rollen**: Klik op pictogram **Toevoegen toevoegen** ![ of ](../../media/ITPro-EAC-AddIcon.png) **ITPro-EAC-RemoveIcon.gif verwijderen** om de rollen te selecteren of te wijzigen die aan de ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rolgroep zijn toegewezen.

    - **Leden**: Klik op pictogram **Toevoegen toevoegen** ![ of ](../../media/ITPro-EAC-AddIcon.png) **ITPro-EAC-RemoveIcon.gif verwijderen** om het lidmaatschap van de ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rolgroep te wijzigen.

3. Wanneer u klaar bent, klikt u op **Opslaan** om de rolgroep te maken.

### <a name="use-the-eac-to-modify-role-groups"></a>De EAC gebruiken om rolgroepen te wijzigen

Ga in de EAC naar Rollen **Machtigingenbeheer,** \> **Admin roles**selecteer de rolgroep die u wilt wijzigen en klik vervolgens op **Edit** ![ pictogram Bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .

Dezelfde opties zijn beschikbaar wanneer u rolgroepen wijzigt als wanneer u rolgroepen maakt. U kunt:

- Wijzig de naam en beschrijving.

- Beheerrollen toevoegen en verwijderen (roltoewijzingen maken of verwijderen).

- Leden toevoegen en verwijderen.

**Opmerking:** Sommige rolgroepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep verwijderen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>De EAC wijzigen van de lijst met leden in rolgroepen

1. Ga in de EAC naar Rollen **Machtigingenbeheer,** \> **Admin roles**selecteer de rolgroep **Edit** die u wilt wijzigen en klik vervolgens op ![ pictogram Bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .

2. Doe in de pagina Eigenschappen van de rolgroep die wordt geopend in de sectie **Memebers** een van de volgende stappen:

   - Klik op Pictogram Toevoegen **toevoegen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Zoek op de pagina die wordt weergegeven de gebruiker die wou wil toevoegen en klik vervolgens op **toevoegen ->**. Selecteer gebruikers en klik op **toevoegen ->** vele malen als dat nodig is. Klik op **OK**als u klaar bent.

   - Selecteer de gebruikers die u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klik op **Opslaan** wanneer u gereed bent.

   > [!NOTE]
   > Gebruikers moeten zich mogelijk afmelden en zich opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toegevoegd of verwijderd uit de rolgroep.

### <a name="use-the-eac-to-remove-role-groups"></a>De EAC gebruiken om rolgroepen te verwijderen

U ingebouwde rolgroepen niet verwijderen, maar u aangepaste rolgroepen verwijderen die u hebt gemaakt.

1. Ga in de EAC naar **machtigingen** \> **admin rollen**.

2. Selecteer de rolgroep die u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klik op **Ja** in het bevestigingsvenster dat wordt weergegeven.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell gebruiken om rolgroepen te beheren

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rolgroepen weer te geven

Als u een rolgroep wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In dit voorbeeld wordt een overzichtslijst van alle rolgroepen geretourneerd.

```PowerShell
Get-RoleGroup
```

In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de rolgroep met de naam Ontvangersbeheerders.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In dit voorbeeld worden alle rolgroepen geretourneerd waarin de gebruiker Julia lid is. U moet de DN-waarde (DistinguishedName) voor Julia gebruiken, die u vinden door de opdracht uit te voeren: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Zie [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rolgroepen te maken

Wanneer u een nieuwe rolgroep maakt, u alle instellingen handmatig configureren (tijdens het maken van de groep of erna). U ook een bestaande rolgroep kopiëren en wijzigen.

- Als u handmatig een nieuwe rolgroep wilt maken, gebruikt u de volgende syntaxis:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - De parameter _Roles_ geeft de beheerrollen op die u aan de rolgroep moet toewijzen met behulp van de volgende syntaxis `"Role1","Role1",..."RoleN"` . U de beschikbare rollen bekijken met de cmdlet **Get-ManagementRole.**

  - De parameter _Members_ geeft de leden van de rolgroep aan met de volgende syntaxis: `"Member1","Member2",..."MemberN"` . U gebruikers, universele beveiligingsgroepen (USG's) of andere rolgroepen (beveiligings principals) opgeven.

  In dit voorbeeld wordt een nieuwe rolgroep met de naam 'Beperkt ontvangstbeheer' gemaakt met de volgende instellingen:

  - De rol E-mail geadresseerden wordt toegewezen aan de rolgroep.

  - De gebruikers Kim en Martin worden toegevoegd als leden.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Als u een bestaande rolgroep wilt kopiëren, voert u de volgende stappen uit:

  1. Sla de rolgroep op die u wilt kopiëren in een variabele met de volgende syntaxis:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Maak de nieuwe rolgroep met de volgende syntaxis:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     De parameter _Members_ geeft de leden van de rolgroep aan met de volgende syntaxis: `"Member1","Member2",..."MemberN"` . U gebruikers, universele beveiligingsgroepen (USG's) of andere rolgroepen (beveiligings principals) opgeven.

     In dit voorbeeld wordt de rolgroep Organisatiebeheer gekopieerd naar de nieuwe rolgroep met de naam 'Beperkt organisatiebeheer'. De leden van de rolgroep zijn Isabelle, Carter en Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Voor gedetailleerde syntaxis en parametergegevens, [Nieuwe-Rolgroep](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Zelfstandige EOP PowerShell gebruiken wijzigt de lijst met leden in rolgroepen

- De cmdlets **Van Add-RoleGroupMember** en **Remove-RoleGroupMember** voegen individuele leden één voor één toe of verwijderen deze. De **cmdlet Update-RoleGroupMember** kan de bestaande ledenlijst vervangen of wijzigen.

- De leden van een rolgroep kunnen gebruikers, universele beveiligingsgroepen (USG's) of andere rolgroepen (beveiligings principals) zijn.

Als u de leden van een rolgroep wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Als u de bestaande ledenlijst _wilt vervangen door_ de waarden die u opgeeft, gebruikt u de volgende syntaxis: `"Member1","Member2",..."MemberN"` .

- Als u de bestaande ledenlijst _selectief wilt wijzigen,_ gebruikt u de volgende syntaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In dit voorbeeld worden alle huidige leden van de rolgroep Helpdesk vervangen door de opgegeven gebruikers.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Valeria Barrio verwijderd uit de lijst met leden van de rolgroep Helpdesk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Zie Groep bijwerken en [een rolgroep](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)bijwerken voor gedetailleerde syntaxis en parametergegevens .

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rolgroepen te verwijderen

U ingebouwde rolgroepen niet verwijderen, maar u aangepaste rolgroepen verwijderen die u hebt gemaakt.

Als u een aangepaste rolgroep wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In dit voorbeeld wordt de rolgroep Trainingsbeheerders verwijderd.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Zie [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u een rolgroep hebt gekopieerd, voert u een van de volgende stappen uit:

- Ga in de EAC naar rollen **Permissions** \> **machtigingenbeheer**en controleer of de rolgroep wordt vermeld (of niet wordt vermeld). Selecteer de rolgroep en verifieer de instellingen in het deelvenster Details of **klik** op pictogram Bewerken bewerken ![ om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.

- Vervang in Exchange Online PowerShell \<Role Group Name\> de naam van de rolgroep en voer de volgende opdracht uit om te controleren of de rolgroep bestaat (of niet bestaat) en controleer de instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
