---
title: Groepen beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Beheerders in zelfstandige Exchange Online Protection-organisaties (EOP) kunnen informatie krijgen over het maken, wijzigen en verwijderen van distributiegroepen en beveiligingsgroepen met e-mail in het Exchange-beheercentrum (EAC) en in zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166961"
---
# <a name="manage-groups-in-eop"></a>Groepen beheren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

In zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken kunt u de volgende typen groepen maken, wijzigen en verwijderen:

- **Distributiegroepen:** een verzameling e-mailgebruikers of andere distributiegroepen. Bijvoorbeeld teams of andere ad-hocgroepen die e-mail moeten ontvangen of verzenden in een gemeenschappelijk interessegebied. Distributiegroepen zijn uitsluitend voor het distribueren van e-mailberichten en zijn geen beveiligings-principals (aan deze groepen zijn geen machtigingen toegewezen).

- **Beveiligingsgroepen met e-mail:** een verzameling e-mailgebruikers en andere beveiligingsgroepen die toegangsrechten nodig hebben voor beheerdersrollen. U wilt bijvoorbeeld een specifieke groep gebruikers beheerdersmachtigingen geven zodat ze antispam- en antimalware-instellingen kunnen configureren.

    > [!NOTE]
    >
    > - Standaard weigeren nieuwe beveiligingsgroepen met e-mail berichten van externe (niet-geauteerde) afzenders.
    >
    > - Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.

U kunt groepen beheren in het Exchange-beheercentrum (EAC) en in zelfstandige EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Exchange-beheercentrum wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Wanneer u groepen beheert in zelfstandige EOP PowerShell, kan er beperkingen worden aangetroffen. In de PowerShell-procedures in dit artikel wordt een batchverwerkingsmethode gebruikt die resulteert in een doorloopvertraging van een paar minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Distributiegroepen**  nodig, die standaard is toegewezen aan de rollengroepen Organisatiebeheer en **Geadresseerdenbeheer.** Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Hebt u problemen? Vraag om hulp op het forum [van Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Het Exchange-beheercentrum gebruiken om distributiegroepen te beheren

### <a name="use-the-eac-to-create-groups"></a>Het EAC gebruiken om groepen te maken

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Klik **op** ![ het pictogram Nieuw en selecteer een van de volgende ](../../media/ITPro-EAC-AddIcon.png) opties:

   - **Distributiegroep**

   - **Beveiligingsgroep met e-mail**

3. Configureer de volgende instellingen op de nieuwe groepspagina die wordt geopend. Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.

   - <sup>\*</sup>**Weergavenaam:** deze naam wordt weergegeven in het adresboek van uw organisatie, op de Regel  Aan: wanneer e-mail naar deze groep wordt verzonden en in de lijst Groepen in het EAC. De weergavenaam is vereist, moet uniek zijn en moet herkenbaar zijn, zodat gebruikers weten wat de naam is.

   - <sup>\*</sup>**Alias:** gebruik dit vak om de naam van de alias voor de groep te typen. De alias mag niet meer dan 64 tekens bevatten en moet uniek zijn. Wanneer een gebruiker de alias in de regel Aan van een e-mailbericht typen, wordt de weergavenaam van de groep weergegeven.

   - <sup>\*</sup>**E-mailadres:** het e-mailadres bestaat uit de alias aan de linkerkant van het at-symbool (@) en een domein aan de rechterkant. Standaard wordt de waarde van **Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen. Voor de domeinwaarde klikt u op de vervolgkeuzekeuze en selecteert en geaccepteerd domein in uw organisatie.

   - **Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het EAC.

   - <sup>\*</sup>**Eigenaren:** een groepseigenaar kan groepslidmaatschap beheren. De persoon die een groep maakt, is standaard de eigenaar. Alle groepen moeten ten minste één eigenaar hebben.

     Als u eigenaars wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik op **-toevoegen >.** Herhaal deze stap zo vaak als nodig is. Klik op OK wanneer u **klaar bent.**

     Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

   - **Leden:** groepsleden toevoegen en verwijderen.

     Als u leden wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik op **-toevoegen >.** Herhaal deze stap zo vaak als nodig is. Klik op OK wanneer u **klaar bent.**

     Als u een lid wilt verwijderen, selecteert u het lid en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

4. Wanneer u klaar bent, klikt u op **Opslaan om** de distributiegroep te maken.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Het EAC gebruiken om distributiegroepen te wijzigen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep of beveiligingsgroep met e-mail die u wilt wijzigen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Bewerken.

3. Klik op de pagina met eigenschappen van de distributiegroep die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik dit tabblad om basisinformatie over de groep weer te geven of te wijzigen.

- **Weergavenaam:** deze naam wordt weergegeven in het adresboek, op de regel Aan wanneer e-mail naar deze groep wordt verzonden en in de **lijst Groepen.** De weergavenaam is verplicht en moet herkenbaar zijn, zodat gebruikers weten wat deze is. Het moet ook uniek zijn in uw domein.

  Als u een groepsnaambeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die is gedefinieerd in het beleid.

- **Alias:** dit is het gedeelte van het e-mailadres dat links van het @-symbool wordt weergegeven. Als u de alias wijzigt, wordt het primaire SMTP-adres voor de groep ook gewijzigd en bevat de nieuwe alias. Het e-mailadres met de vorige alias wordt ook bewaard als een proxyadres voor de groep.

- **E-mailadres:** het e-mailadres bestaat uit de alias aan de linkerkant van het at-symbool (@) en een domein aan de rechterkant. Standaard wordt de waarde van **Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen. Voor de domeinwaarde klikt u op de vervolgkeuzekeuze en selecteert en geaccepteerd domein in uw organisatie.

- **Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het detailvenster van het EAC.

#### <a name="ownership"></a>Eigendom

Gebruik dit tabblad om groepseigenaars toe te wijzen. Een groepseigenaar kan het groepslidmaatschap beheren. De persoon die een groep maakt, is standaard de eigenaar. Alle groepen moeten ten minste één eigenaar hebben.

Als u eigenaars wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek en selecteer een geadresseerde in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Invoeg**>. Herhaal deze stap zo vaak als nodig is. Klik op OK wanneer u **klaar bent.**

Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

#### <a name="membership"></a>Lidmaatschap

Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen. Groepseigenaren hoeven geen lid te zijn van de groep.

Als u leden wilt toevoegen, klikt **u op pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik op **-toevoegen >.** Herhaal deze stap zo vaak als nodig is. Klik op OK wanneer u **klaar bent.**

Als u een lid wilt verwijderen, selecteert u het lid en klikt u op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

### <a name="use-the-eac-to-remove-groups"></a>Het EAC gebruiken om groepen te verwijderen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep die u wilt verwijderen en klik op **pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

## <a name="use-powershell-to-manage-groups"></a>PowerShell gebruiken om groepen te beheren

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen weer te geven

Voer de volgende opdracht uit om een overzichtslijst met alle distributiegroepen en beveiligingsgroepen met e-mail in zelfstandige EOP PowerShell te retourneren:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Als u de lijst met groepsleden wilt retourneren, vervangt u door de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Zie Get-Recipient en [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie. [](https://docs.microsoft.com/powershell/module/exchange/get-recipient)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen te maken

Gebruik de volgende syntaxis om distributiegroepen of beveiligingsgroepen met e-mail te maken in zelfstandige EOP PowerShell:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Opmerkingen**:

- De  parameter Name is vereist, heeft een maximumlengte van 64 tekens en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Name_ gebruikt voor de weergavenaam.

- Als u de _aliasparameter_ niet gebruikt, wordt de parameter _Name_ gebruikt voor de aliaswaarde. Spaties worden verwijderd en niet-ondersteunde tekens worden geconverteerd naar vraagtekens (?).

- Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de aliaswaarde gebruikt in de _primarySmtpAddress-parameter._

- Als u de parameter Type niet _gebruikt,_ is de standaardwaarde Verdeling.

In dit voorbeeld wordt een distributiegroep gemaakt met de naam IT-beheerders met de opgegeven eigenschappen.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Zie [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen

Gebruik de volgende syntaxis om groepen in zelfstandige EOP PowerShell te wijzigen:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) gewijzigd, dat de groep Werknemers van Seattle moet sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

In dit voorbeeld worden de huidige leden van de groep Beveiligingsteam vervangen door Petersen En Wordt Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In dit voorbeeld wordt een nieuwe gebruiker met de naam Wordt Fawcett toegevoegd aan de groep genaamd Beveiligingsteam met behoud van de huidige leden van de groep.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="remove-a-group-using-remote-windows-powershell"></a>Een groep verwijderen met behulp van externe Windows PowerShell

In dit voorbeeld wordt de distributiegroep IT-beheerders verwijderd.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende stappen te werk om te controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd:

- Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**. Controleer of de groep wel of niet wordt weergegeven en controleer de **waarde van het groepstype.** Selecteer de groep en bekijk de informatie  in het detailvenster of klik op het pictogram ![ Bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.

- Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt weergegeven (of niet wordt weergegeven):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Vervang door de naam, alias of het e-mailadres van de groep en voer de volgende opdracht \<GroupIdentity\> uit om de instellingen te controleren:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Als u de groepsleden wilt weergeven, vervangt u door de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
