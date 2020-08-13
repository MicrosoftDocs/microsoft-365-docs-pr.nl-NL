---
title: Groepen beheren in EOP
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Beheerders in zelfstandige Exchange Online Protection-organisaties (EOP) kunnen leren hoe u distributiegroepen en beveiligingsgroepen met e-mail kunt maken, wijzigen en verwijderen in het Exchange Admin Center (PowerShell) en zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: 813735d4024c3b8424a6bbac51ebef7b4c53e590
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653651"
---
# <a name="manage-groups-in-eop"></a>Groepen beheren in EOP

U kunt de volgende typen groepen maken, wijzigen en verwijderen in zelfstandige Exchange Online Protection-organisaties (EOP) zonder postvakken van Exchange Online:

- **Distributiegroepen**: een verzameling e-mail gebruikers of andere distributiegroepen. Bijvoorbeeld teams of andere ad hoc groepen die in een gemeenschappelijk gebied een e-mailbericht moeten ontvangen of verzenden. Distributiegroepen zijn exclusief bedoeld voor het distribueren van e-mailberichten en geen beveiligings-principals (ze kunnen geen machtigingen aan hen toewijzen).

- **Beveiligingsgroepen met e-mail**: een verzameling e-mail gebruikers en andere beveiligingsgroepen die toegangsmachtigingen nodig hebben voor beheerdersrollen. U kunt bijvoorbeeld bepaalde groep gebruikers beheerdersmachtigingen geven, zodat ze antispam-en anti-malware-instellingen kunnen configureren.

    > [!NOTE]
    >
    > - Nieuwe beveiligingsgroepen met e-mail kunnen standaardberichten van externe (niet-geverifieerde) afzenders weigeren.
    >
    > - Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.

U kunt groepen beheren in het Exchange Admin Center (SBV) en zelfstandige EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Om het Exchange-Beheercentrum te openen, raadpleegt u het [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Wanneer u groepen beheert in zelfstandige EOP PowerShell, kan dit leiden tot vertraging. Voor de PowerShell-procedures in dit onderwerp wordt een batch verwerkingsmethode gebruikt waarmee de vertragings vertraging van een paar minuten wordt veroorzaakt voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Specifiek hebt u de rol van distributiegroepen nodig, dat is toegewezen aan de de organizationmanagement (algemene beheerders) en RecipientManagement rollen groepen. Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Problemen? Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Het Exchange-Beheercentrum gebruiken voor het beheren van distributiegroepen

### <a name="use-the-eac-to-create-groups"></a>Het gebruik van de toepassing SBV gebruiken om groepen te maken

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Klik op **Nieuw** ![ pictogram ](../../media/ITPro-EAC-AddIcon.png) en selecteer een van de volgende opties:

   - **Distributiegroep**

   - **Beveiligingsgroep met e-mail**

3. Configureer de volgende instellingen op de pagina nieuwe groep die wordt geopend. Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.

   - <sup>\*</sup>**Weergavenaam**: deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel aan: wanneer e-mail wordt verzonden naar deze groep en in de lijst **groepen** in de lijst. De weergavenaam is vereist en moet uniek zijn en moet gebruikersvriendelijk zijn, zodat de persoon de naam herkent.

   - <sup>\*</sup>**Alias**: gebruik dit vak om de naam van de alias voor de groep te typen. De alias mag niet langer zijn dan 64 tekens en moet uniek zijn. Wanneer een gebruiker de alias typt in de regel aan van een e-mailbericht, wordt deze herleid tot de weergavenaam van de groep.

   - <sup>\*</sup>**E-mailadres**: het e-mailadres bestaat uit de alias aan de linkerkant van het apenstaartje (@) en een domein aan de rechterkant. Standaard wordt de waarde van **alias** gebruikt voor de alias waarde, maar u kunt deze wijzigen. Klik voor de domeinwaarde op de vervolgkeuzelijst en selecteer het domein dat u in uw organisatie hebt geaccepteerd.

   - **Beschrijving**: deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het Exchange-Beheercentrum.

   - <sup>\*</sup>**Eigenaren**: een groepseigenaar kan groepslidmaatschap beheren. Standaard is de persoon die een groep maakt, de eigenaar. Alle groepen moeten minimaal één eigenaar hebben.

     Als u eigenaren wilt **Add** toevoegen, klikt u op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) . In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde of groep en klikt u vervolgens op **add->**. Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK**.

     Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt **u op** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Leden**: groepsleden toevoegen en verwijderen.

     Als u leden **wilt toevoegen, klikt u** op ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) . In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde of groep en klikt u vervolgens op **add->**. Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK**.

     Als u een lid wilt verwijderen, selecteert u het lid en klikt **u op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Wanneer u klaar bent, klikt u op **Opslaan** om de distributiegroep te maken.

### <a name="use-the-eac-to-modify-distribution-groups"></a>De Exchange-distributiegroepen wijzigen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep of beveiligingsgroep met e-mail die u wilt wijzigen en klik vervolgens op het pictogram bewerken **bewerken** ![ ](../../media/ITPro-EAC-AddIcon.png) .

3. Op de pagina met eigenschappen van distributiegroep die wordt geopend, klikt u op een van de volgende tabbladen om de eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Via dit tabblad kunt u algemene informatie over de groep weergeven of wijzigen.

- **Weergavenaam**: deze naam wordt weergegeven in het adresboek, op de regel aan wanneer e-mail wordt verzonden naar deze groep en in de **lijst met groepen**. De weergavenaam is vereist en moet gebruikersvriendelijk zijn, zodat de persoon de naam herkent. Het domein moet ook uniek zijn in uw domein.

  Als u een Groepsbeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die is gedefinieerd door het beleid.

- **Alias**: dit is het gedeelte van het e-mailadres dat links van het @-symbool wordt weergegeven. Als u de alias wijzigt, wordt het primaire SMTP-adres voor de groep eveneens gewijzigd en bevat de nieuwe alias. Ook wordt het e-mailadres met de vorige alias bewaard als een proxyadres voor de groep.

- **E-mailadres**: het e-mailadres bestaat uit de alias aan de linkerkant van het apenstaartje (@) en een domein aan de rechterkant. Standaard wordt de waarde van **alias** gebruikt voor de alias waarde, maar u kunt deze wijzigen. Klik voor de domeinwaarde op de vervolgkeuzelijst en selecteer het domein dat u in uw organisatie hebt geaccepteerd.

- **Beschrijving**: deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het Exchange-Beheercentrum.

#### <a name="ownership"></a>Eigendom

Gebruik dit tabblad om groepseigenaren toe te wijzen. Een groepseigenaar kan groepslidmaatschap beheren. Standaard is de persoon die een groep maakt, de eigenaar. Alle groepen moeten minimaal één eigenaar hebben.

Als u eigenaren wilt **Add** toevoegen, klikt u op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) . In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde en klikt u vervolgens op **add->**. Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK**.

Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt **u op** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Waartoe

Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen. Groepseigenaren hoeven niet lid te zijn van de groep.

Als u leden **wilt toevoegen, klikt u** op ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) . In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u een geadresseerde of groep en klikt u vervolgens op **add->**. Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK**.

Als u een lid wilt verwijderen, selecteert u het lid en klikt **u op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Het Exchange-Beheercentrum gebruiken om groepen te verwijderen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep die u **wilt verwijderen en klik op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>PowerShell gebruiken om groepen te beheren

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Standalone EOP PowerShell gebruiken om groepen weer te geven

Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle distributiegroepen en beveiligingsgroepen met e-mail in standalone EOP PowerShell.

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Als u de lijst met groepsleden wilt weergeven, vervangt u \<GroupIdentity\> de naam, alias of het e-mailadres van de groep en voert u de volgende opdracht uit:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Zie [Get-](https://docs.microsoft.com/powershell/module/exchange/get-recipient) [DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)voor meer informatie over de syntaxis en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Standalone EOP PowerShell gebruiken om groepen te maken

Als u distributiegroepen of beveiligingsgroepen met e-mail wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Opmerkingen**:

- De _naam_ parameter is vereist, mag maximaal 64 tekens lang zijn en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _name_ gebruikt voor de weergavenaam.

- Als u de parameter _alias_ niet gebruikt, wordt de parameter _name_ gebruikt voor de alias waarde. Spaties worden verwijderd en niet-ondersteunde tekens worden geconverteerd naar vraagtekens (?).

- Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de waarde van de alias gebruikt in de _PrimarySmtpAddress_ -parameter.

- Als u de parameter _type_ niet gebruikt, is de standaardwaarde distributie.

In dit voorbeeld wordt een distributiegroep met de naam beheerders gemaakt met de opgegeven eigenschappen.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Zie [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen

Gebruik de volgende syntaxis om groepen in een zelfstandige EOP PowerShell te wijzigen:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In dit voorbeeld wordt het primaire SMTP-adres (ook wel antwoordadres genoemd) voor de groep werknemers in de Seattle gebruikt in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

In dit voorbeeld worden de huidige leden van de groep beveiligings team vervangen door grappige Petersen en Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In dit voorbeeld wordt een nieuwe gebruiker met de naam Tyson Fawcett toegevoegd aan de groep met de naam Security team, en de huidige leden van de groep behouden.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Zie [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="remove-a-group-using-remote-windows-powershell"></a>Een groep verwijderen via externe Windows PowerShell

In dit voorbeeld wordt de distributiegroep met de naam beheerders verwijderd.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een van de volgende stappen uit om te controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd:

- Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**. Controleer of de groep wel of niet in de lijst staat, en controleer de waarde van het **groeps type** . Selecteer de groep en Bekijk de informatie in het detailvenster of klik op **Edit** ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-AddIcon.png) om de instellingen weer te geven.

- Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt weergegeven (of niet wordt weergegeven):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Vervang de \<GroupIdentity\> naam, alias of het e-mailadres van de groep en voer de volgende opdracht uit om de instellingen te controleren:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Als u de groepsleden wilt weergeven, vervangt u de \<GroupIdentity\> naam, alias of het e-mailadres van de groep en voert u de volgende opdracht uit:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
