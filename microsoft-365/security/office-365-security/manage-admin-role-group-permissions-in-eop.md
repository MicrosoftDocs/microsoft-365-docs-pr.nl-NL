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
description: Beheerders kunnen leren hoe ze machtigingen kunnen toewijzen of verwijderen in het Exchange-beheercentrum (EAC) in Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926878"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Rollengroepen beheren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken kunt u het Exchange-beheercentrum (EAC) gebruiken om gebruikers toe te voegen aan rollengroepen. Als u een gebruiker toevoegt aan een rollengroep, krijgt de gebruiker machtigingen om specifieke beheertaken uit te voeren. U kunt gebruikers ook verwijderen uit rollengroepen.

Zie Machtigingen in zelfstandige EOP voor meer informatie over rollen en [rollengroepen.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie Exchange-beheercentrum in zelfstandige [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum (EAC) te openen.

- Zie Connect to Exchange Online Protection PowerShell (Verbinding maken [met Exchange Online Protection PowerShell)](/powershell/exchange/connect-to-exchange-online-protection-powershell)als u zelfstandige EOP PowerShell wilt openen.

- U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Rollenbeheer**  nodig, die standaard is toegewezen aan de rollengroep Organisatiebeheer. Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-manage-role-groups"></a>Het EAC gebruiken om rollengroepen te beheren

### <a name="use-the-eac-to-view-role-groups"></a>Het EAC gebruiken om rollengroepen weer te geven

1. Ga in het EAC naar **Machtigingenbeheerdersrollen.** \>  Alle rollengroepen in uw organisatie worden hier weergegeven.

2. Selecteer een rollengroep. In het deelvenster Details ziet u **de naam,** **beschrijving,** **toegewezen rollen** en Beheerd **door** van de rollengroep. U kunt deze informatie ook zien door op Pictogram **Bewerken** ![ bewerken te ](../../media/ITPro-EAC-EditIcon.png) klikken.

### <a name="use-the-eac-to-create-role-groups"></a>Het EAC gebruiken om rollengroepen te maken

Wanneer u een nieuwe rollengroep maakt, kunt u alle instellingen zelf configureren (tijdens het maken van de groep of na). U kunt ook een bestaande rollengroep kopiëren en wijzigen.

1. Ga in het EAC naar **Machtigingenbeheerdersrollen** \> en ga vervolgens een van de volgende stappen uit:

   - **Handmatig een nieuwe rollengroep maken:** klik **op Pictogram** ![ Toevoegen ](../../media/ITPro-EAC-AddIcon.png) toevoegen.

   - **Een bestaande rollengroep kopiëren:** Selecteer de rollengroep die u wilt kopiëren en klik vervolgens **op Pictogram** ![ Kopiëren ](../../media/ITPro-EAC-CopyIcon.png) kopiëren.

2. Configureer **de volgende** instellingen in het venster Nieuwe rollengroep dat wordt weergegeven:

    - **Naam:** Voer een unieke naam in voor de rollengroep.

    - **Beschrijving:** Voer een optionele beschrijving in voor de rollengroep.

    - **Rollen:** Klik op **Pictogram Toevoegen** toevoegen of pictogram Verwijderen om de rollen te selecteren of te wijzigen die ![ aan de ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rollengroep zijn toegewezen.

    - **Leden:** Klik op **Pictogram Toevoegen** toevoegen ![ of ](../../media/ITPro-EAC-AddIcon.png) **Pictogram** Verwijderen verwijderen om het lidmaatschap van ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) rollengroep te wijzigen.

3. Wanneer u klaar bent, klikt u op **Opslaan om** de rollengroep te maken.

### <a name="use-the-eac-to-modify-role-groups"></a>Het EAC gebruiken om rollengroepen te wijzigen

Ga in het EAC naar **Machtigingenbeheerdersrollen,** selecteer de rollengroep die u wilt wijzigen en \> klik vervolgens op **Pictogram** ![ Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken.

Dezelfde opties zijn beschikbaar wanneer u rollengroepen wijzigt als wanneer u rollengroepen maakt. U kunt:

- Wijzig de naam en beschrijving.

- Beheerrollen toevoegen en verwijderen (rollentoewijzingen maken of verwijderen).

- Leden toevoegen en verwijderen.

**Opmerking:** Sommige rollengroepen (bijvoorbeeld Organisatiebeheer) beperken de rollen die u uit de groep kunt verwijderen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>De lijst met leden in rollengroepen wijzigen met het EAC

1. Ga in het EAC naar **Machtigingenbeheerdersrollen,** selecteer de rollengroep die u wilt wijzigen \> en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken.

2. Ga als volgt te werk op de pagina eigenschappen van de rollengroep die wordt geopend in **de** sectie Leden:

   - Klik **op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek op de pagina die wordt weergegeven de gebruiker die u wilt toevoegen en klik vervolgens **op Toevoegen ->.** Selecteer gebruikers en klik **zo nodig >** add->. Wanneer u klaar bent, klikt u op **OK.**

   - Selecteer de gebruikers die u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.

3. Klik op **Opslaan** wanneer u gereed bent.

   > [!NOTE]
   > Gebruikers moeten zich mogelijk aanmelden en zich opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toevoegen of verwijderen uit de rollengroep.

### <a name="use-the-eac-to-remove-role-groups"></a>Het EAC gebruiken om rollengroepen te verwijderen

U kunt ingebouwde rollengroepen niet verwijderen, maar u kunt aangepaste rollengroepen verwijderen die u hebt gemaakt.

1. Ga in het EAC naar **Machtigingenbeheerdersrollen.** \> 

2. Selecteer de rollengroep die u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) verwijderen.

3. Klik **op Ja** in het bevestigingsvenster dat wordt weergegeven.

## <a name="use-powershell-to-manage-role-groups"></a>PowerShell gebruiken om rollengroepen te beheren

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rollengroepen weer te geven

Als u een rollengroep wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In dit voorbeeld wordt een overzichtslijst met alle rollengroepen weergegeven.

```PowerShell
Get-RoleGroup
```

Dit voorbeeld retourneert gedetailleerde informatie voor de rollengroep met de naam Geadresseerdebeheerders.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

Dit voorbeeld retourneert alle rollengroepen waar de gebruiker Julia lid van is. U moet de DN-waarde (DistinguishedName) voor Julia gebruiken, die u kunt vinden door de opdracht uit te voeren: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Zie [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rollengroepen te maken

Wanneer u een nieuwe rollengroep maakt, kunt u alle instellingen handmatig configureren (tijdens het maken van de groep of na). U kunt ook een bestaande rollengroep kopiëren en wijzigen.

- Als u handmatig een nieuwe rollengroep wilt maken, gebruikt u de volgende syntaxis:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Met _de_ parameter Rollen worden de beheerrollen opgegeven die u aan de rollengroep wilt toewijzen met de volgende `"Role1","Role1",..."RoleN"` syntaxis. U kunt de beschikbare rollen zien met de **cmdlet Get-ManagementRole.**

  - De _parameter Leden_ geeft de leden van de rollengroep aan met de volgende syntaxis: `"Member1","Member2",..."MemberN"` . U kunt gebruikers, universele beveiligingsgroepen met e-mail (USG's) of andere rollengroepen (beveiligingsprincipen) opgeven.

  In dit voorbeeld wordt een nieuwe rollengroep gemaakt met de naam 'Beperkt beheer van geadresseerden' met de volgende instellingen:

  - De rol E-mailontvangers wordt toegewezen aan de rollengroep.

  - De gebruikers Kim en Martin worden toegevoegd als leden.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Als u een bestaande rollengroep wilt kopiëren, gaat u als volgt te werk:

  1. Sla de rollengroep op die u wilt kopiëren in een variabele met de volgende syntaxis:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Maak de nieuwe rollengroep met de volgende syntaxis:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     De _parameter Leden_ geeft de leden van de rollengroep aan met de volgende syntaxis: `"Member1","Member2",..."MemberN"` . U kunt gebruikers, universele beveiligingsgroepen met e-mail (USG's) of andere rollengroepen (beveiligingsprincipen) opgeven.

     In dit voorbeeld kopieert u de rollengroep Organisatiebeheer naar de nieuwe rollengroep met de naam 'Beperkt organisatiebeheer'. De leden van de rollengroep zijn Raymond, Voerman en Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Voor gedetailleerde syntaxis- en parametergegevens, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om de lijst met leden in rollengroepen te wijzigen

- De **cmdlets Add-RoleGroupMember** en **Remove-RoleGroupMember** voegen afzonderlijke leden een voor een toe of verwijderen. De **cmdlet Update-RoleGroupMember** kan de bestaande lijst met leden vervangen of wijzigen.

- De leden van een rollengroep kunnen gebruikers, universele beveiligingsgroepen (USG's) met e-mail of andere rollengroepen (beveiligingsprincipen) zijn.

Als u de leden van een rollengroep wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Als _u de_ bestaande lijst met leden wilt vervangen door de waarden die u opgeeft, gebruikt u de volgende syntaxis: `"Member1","Member2",..."MemberN"` .

- Als _u de bestaande lijst_ met leden selectief wilt wijzigen, gebruikt u de volgende syntaxis: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In dit voorbeeld worden alle huidige leden van de rollengroep Helpdesk vervangen door de opgegeven gebruikers.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In dit voorbeeld wordt Daigoro Akai toegevoegd en wordt Valeria Barrio verwijderd uit de lijst met leden in de rollengroep Helpdesk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Zie [Update-RoleGroupMember voor](/powershell/module/exchange/Update-RoleGroupMember)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Zelfstandige EOP PowerShell gebruiken om rollengroepen te verwijderen

U kunt ingebouwde rollengroepen niet verwijderen, maar u kunt aangepaste rollengroepen verwijderen die u hebt gemaakt.

Als u een aangepaste rollengroep wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In dit voorbeeld wordt de rollengroep Trainingsbeheerders verwijderd.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Zie [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u een rollengroep hebt gekopieerd, gaat u als volgt te werk:

- Ga in het EAC naar **Machtigingenbeheerdersrollen** en controleer of de rollengroep \> wordt weergegeven (of niet wordt weergegeven). Selecteer de rollengroep en controleer de instellingen in het deelvenster Details of klik op **Pictogram** ![ Bewerken bewerken om de instellingen te ](../../media/ITPro-EAC-EditIcon.png) controleren.

- Vervang in Exchange Online PowerShell door de naam van de rollengroep en voer de volgende opdracht uit om te controleren of de rollengroep bestaat (of niet bestaat) en controleer de \<Role Group Name\> instellingen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```