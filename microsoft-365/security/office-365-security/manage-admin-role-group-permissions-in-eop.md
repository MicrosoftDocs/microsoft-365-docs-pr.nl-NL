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
ms.openlocfilehash: ba2d053e1e75bd8867ebb9eb7f426cde92abd3e8
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352333"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Rollengroepen beheren in standalone EOP

In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken u het Exchange-beheercentrum (EAC) gebruiken om gebruikers toe te voegen aan rolgroepen. Als u een gebruikers toevoegt aan een rolgroep, geeft de gebruiker machtigingen om specifieke beheertaken uit te voeren. U gebruikers ook verwijderen uit rolgroepen.

Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen en rolgroepen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum (EAC) wilt openen.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u zelfstandige EOP PowerShell wilt openen.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt in het bijzonder de rolbeheerrol nodig, die standaard is toegewezen aan de rolgroep OrganizationManagement (globale beheerders). Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de [EAC wijzigen de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)voor meer informatie.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-manage-role-groups"></a>De EAC gebruiken om rolgroepen te beheren

### <a name="use-the-eac-to-view-role-groups"></a>De EAC gebruiken om rolgroepen weer te geven

1. Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**. Alle rolgroepen in uw organisatie worden hier weergegeven.

2. Selecteer een rolgroep. In het deelvenster Details wordt de **naam**, **beschrijving**, **toegewezen rollen**en beheerd **door** van de rolgroep weergegeven. U deze informatie ook bekijken door op pictogram Bewerken **bewerken** te klikken ![ ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>De EAC gebruiken om rolgroepen te maken

Wanneer u een nieuwe rolgroep maakt, u alle instellingen zelf configureren (tijdens het maken van de groep of erna). U ook een bestaande rolgroep kopiëren en wijzigen.

1. Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**en voer een van de volgende stappen uit:

   - **Handmatig een nieuwe rolgroep maken:** **Klik** op ![ Pictogram Toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) .

   - **Een bestaande rolgroep kopiëren:** selecteer de rolgroep die u wilt kopiëren en **klik** op ![ Pictogram Kopiëren ](../../media/ITPro-EAC-CopyIcon.png) .

2. Configureer in het venster **Nieuwe rolgroep** dat wordt weergegeven de volgende instellingen:

    - **Naam:** Voer een unieke naam in voor de rolgroep.

    - **Beschrijving**: Voer een optionele beschrijving in voor de rolgroep.

    - **Rollen**: **Klik** op ![ Pictogram Toevoegen toevoegen of ](../../media/ITPro-EAC-AddIcon.png) **VERWIJDEREN** ![ VAN ITPro-EAC-RemoveIcon.gif ](../../media/ITPro-EAC-RemoveIcon.gif) om de rollen te selecteren of te wijzigen die aan de rolgroep zijn toegewezen.

    - **Leden**: Klik op **Pictogram** ![ Toevoegen toevoegen of ](../../media/ITPro-EAC-AddIcon.png) **VERWIJDEREN** ![ ITPro-EAC-RemoveIcon.gif om het lidmaatschap van de ](../../media/ITPro-EAC-RemoveIcon.gif) rolgroep te wijzigen.

3. Wanneer u klaar bent, klikt u op **Opslaan** om de rolgroep te maken.

### <a name="use-the-eac-to-modify-role-groups"></a>De EAC gebruiken om rolgroepen te wijzigen

Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder,** selecteer de rolgroep die u wilt wijzigen en klik vervolgens op Pictogram Bewerken **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) .

Dezelfde opties zijn beschikbaar wanneer u rolgroepen wijzigt als wanneer u rolgroepen maakt. U kunt:

- Wijzig de naam en beschrijving.

- Beheerrollen toevoegen en verwijderen (roltoewijzingen maken of verwijderen).

- Leden toevoegen en verwijderen.

**Opmerking:** Sommige rolgroepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep verwijderen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>De EAC wijzigen van de lijst met leden in rolgroepen

1. Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder,** selecteer de rolgroep die u wilt wijzigen en klik vervolgens op Pictogram Bewerken **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) .

2. Ga in de pagina eigenschappen van de rolgroep die wordt geopend in de sectie **Memebers** een van de volgende stappen uit:

   - Klik **op** Pictogram Toevoegen ![ toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Zoek op de pagina die wordt weergegeven de gebruiker die wou wil toevoegen en klik vervolgens op **toevoegen ->**. Selecteer gebruikers en klik op **toevoegen ->** vele malen als dat nodig is. Klik op **OK**als u klaar bent.

   - Selecteer de gebruikers die u wilt **Remove** verwijderen en klik op ![ Pictogram Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klik op **Opslaan** wanneer u gereed bent.

   > [!NOTE]
   > Gebruikers moeten zich mogelijk afmelden en opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toegevoegd of verwijderd uit de rolgroep.

### <a name="use-the-eac-to-remove-role-groups"></a>De EAC gebruiken om rolgroepen te verwijderen

U ingebouwde rolgroepen niet verwijderen, maar u wel aangepaste rolgroepen verwijderen die u hebt gemaakt.

1. Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**.

2. Selecteer de rolgroep die u wilt verwijderen en **klik** op Pictogram ![ Verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klik **op Ja** in het bevestigingsvenster dat wordt weergegeven.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell gebruiken om rolgroepen te beheren

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rolgroepen weer te geven

Als u een rolgroep wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In dit voorbeeld wordt een overzichtslijst met alle rolgroepen geretourneerd.

```PowerShell
Get-RoleGroup
```

In dit voorbeeld worden gedetailleerde informatie geretourneerd voor de rolgroep met de naam Geadresseerde beheerders.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In dit voorbeeld worden alle rolgroepen geretourneerd waarvan de gebruiker Julia lid is. U moet de DN-waarde (DistinguishedName) voor Julia gebruiken, die u vinden door de opdracht uit te voeren: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Zie Groep voor rollen [en](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)parameters voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rolgroepen te maken

Wanneer u een nieuwe rolgroep maakt, u alle instellingen handmatig configureren (tijdens het maken van de groep of erna). U ook een bestaande rolgroep kopiëren en wijzigen.

- Als u handmatig een nieuwe rolgroep wilt maken, gebruikt u de volgende syntaxis:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - De parameter _Rollen_ geeft de beheerrollen op die aan de rolgroep moeten worden toegewezen met behulp van de volgende syntaxis `"Role1","Role1",..."RoleN"` . U de beschikbare rollen bekijken met de cmdlet **Get-ManagementRole.**

  - De parameter _Leden_ geeft de leden van de rolgroep op met behulp van de volgende syntaxis: `"Member1","Member2",..."MemberN"` . U gebruikers, universele beveiligingsgroepen (USG's) met e-mail of andere rolgroepen (beveiligingsprincipals) opgeven.

  In dit voorbeeld wordt een nieuwe rolgroep gemaakt met de naam 'Beheer van beperkte geadresseerden' met de volgende instellingen:

  - De rol E-mailgeadresseerden is toegewezen aan de rolgroep.

  - De gebruikers Kim en Martin worden toegevoegd als leden.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Ga als volgt te werk om een bestaande rolgroep te kopiëren:

  1. Sla de rolgroep op die u wilt kopiëren in een variabele met de volgende syntaxis:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Maak de nieuwe rolgroep met de volgende syntaxis:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     De parameter _Leden_ geeft de leden van de rolgroep op met behulp van de volgende syntaxis: `"Member1","Member2",..."MemberN"` . U gebruikers, universele beveiligingsgroepen (USG's) met e-mail of andere rolgroepen (beveiligingsprincipals) opgeven.

     In dit voorbeeld wordt de rolgroep Organisatiebeheer overgemaakt naar de nieuwe rolgroep met de naam 'Limited Organization Management'. De leden van de rolgroep zijn Isabelle, Carter en Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Voor gedetailleerde syntaxis- en parameterinformatie, [Nieuw-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>De lijst met leden in rolgroepen wijzigen door zelfstandige EOP PowerShell te wijzigen

- De cmdlets **Add-RoleGroupMember** en **Remove-RoleGroupMember** voegen afzonderlijke leden één voor één toe of verwijderen deze af. De cmdlet **Update-RoleGroupMember** kan de bestaande lijst met leden vervangen of wijzigen.

- De leden van een rolgroep kunnen gebruikers, universele beveiligingsgroepen (USG's) of andere rolgroepen (beveiligingsprincipals) zijn.

Als u de leden van een rolgroep wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Als u de bestaande lijst met leden wilt _vervangen_ door de waarden die u opgeeft, gebruikt u de volgende syntaxis: `"Member1","Member2",..."MemberN"` .

- Als u de bestaande lijst met leden selectief wilt _wijzigen,_ gebruikt u de volgende syntaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In dit voorbeeld worden alle huidige leden van de rolgroep Helpdesk vervangen door de opgegeven gebruikers.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Valeria Barrio verwijderd van de ledenlijst van de rolgroep Helpdesk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Zie [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rolgroepen te verwijderen

U ingebouwde rolgroepen niet verwijderen, maar u wel aangepaste rolgroepen verwijderen die u hebt gemaakt.

Als u een aangepaste rolgroep wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In dit voorbeeld wordt de rolgroep Trainingsbeheerders verwijderd.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Zie Groep verwijderen en [parameteren](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende stappen te werk om te controleren of u een rolgroep hebt gekopieerd:

- Ga in de EAC naar **Permissions** \> **rollen Machtigingenbeheerder**en controleer of de rolgroep wordt weergegeven (of niet wordt vermeld). Selecteer de rolgroep en controleer de instellingen **Edit** in het deelvenster Details of klik op ![ Pictogram Bewerken bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.

- Vervang in Exchange Online PowerShell \< de naam van de rolgroep door de naam van de \> rolgroep en voer de volgende opdracht uit om te controleren of de rolgroep bestaat (of bestaat niet) en controleer de instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
