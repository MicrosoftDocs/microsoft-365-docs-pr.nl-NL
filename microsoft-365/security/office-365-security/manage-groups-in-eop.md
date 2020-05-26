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
description: Beheerders in zelfstandige Exchange Online Protection-organisaties (EOP) kunnen leren hoe ze distributiegroepen en beveiligingsgroepen met e-mail kunnen maken, wijzigen en verwijderen in het Exchange-beheercentrum (EAC) en in zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: 4f1dbdb503f8baf02b7dd763dbf7fc6acdf5771a
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352189"
---
# <a name="manage-groups-in-eop"></a>Groepen beheren in EOP

In zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken u de volgende typen groepen maken, wijzigen en verwijderen:

- **Distributiegroepen**: een verzameling e-mailgebruikers of andere distributiegroepen. Bijvoorbeeld teams of andere ad hoc groepen die e-mail moeten ontvangen of verzenden in een gemeenschappelijk interessegebied. Distributiegroepen zijn uitsluitend voor het distribueren van e-mailberichten en zijn geen beveiligingsprincipals (ze kunnen geen machtigingen aan hen hebben toegewezen).

- **Beveiligde groepen met e-mail:** een verzameling e-mailgebruikers en andere beveiligingsgroepen die toegangsmachtigingen nodig hebben voor beheerdersrollen. U bijvoorbeeld specifieke beheerdersmachtigingen voor gebruikers geven, zodat ze instellingen voor antispam en anti-malware kunnen configureren.

    > [!NOTE]
    > <ul><li>Nieuwe beveiligingsgroepen met e-mail weigeren standaard berichten van externe (niet-geverifieerde) afzenders.</li><li>Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.</li></ul>.

U groepen beheren in het Exchange-beheercentrum (EAC) en in zelfstandige EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum te openen.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Wanneer u groepen beheert in zelfstandige EOP PowerShell, u beperking tegenkomen. De PowerShell-procedures in dit onderwerp gebruiken een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt in het bijzonder de rol Distributiegroepen nodig, die standaard is toegewezen aan de rolgroepen OrganizationManagement (globale beheerders) en RecipientManagement. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de [EAC wijzigen de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)voor meer informatie.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Het Exchange-beheercentrum gebruiken om distributiegroepen te beheren

### <a name="use-the-eac-to-create-groups"></a>De EAC gebruiken om groepen te maken

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Klik **op nieuw** nieuw pictogram en selecteer een van de volgende ![ ](../../media/ITPro-EAC-AddIcon.png) opties:

   - **Distributiegroep**

   - **Beveiligingsgroep met e-mail**

3. Configureer op de nieuwe groepspagina die wordt geopend de volgende instellingen. Instellingen gemarkeerd met een <sup>\*</sup> zijn vereist.

   - <sup>\*</sup>**Weergavenaam:** deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel Aan wanneer e-mail naar deze groep wordt verzonden en in de lijst **Groepen** in de EAC. De weergavenaam is vereist, moet uniek zijn en moet gebruiksvriendelijk zijn, zodat mensen herkennen wat het is.

   - <sup>\*</sup>**Alias:** gebruik dit vak om de naam van de alias voor de groep te typen. De alias mag niet meer dan 64 tekens bevatten en moet uniek zijn. Wanneer een gebruiker de alias intypt in de regel Aan van een e-mailbericht, wordt deze opgelost in de weergavenaam van de groep.

   - <sup>\*</sup>**E-mailadres**: Het e-mailadres bestaat uit de alias aan de linkerkant van het at (@) symbool en een domein aan de rechterkant. Standaard wordt de waarde van **Alias** gebruikt voor de aliaswaarde, maar u deze wijzigen. Klik voor de domeinwaarde op de vervolgkeuzelijst en selecteer en geaccepteerd domein in uw organisatie.

   - **Beschrijving**: Deze beschrijving wordt weergegeven in het adresboek en in het deelvenster Details in de EAC.

   - <sup>\*</sup>**Eigenaren**: Een groepseigenaar kan groepslidmaatschap beheren. Standaard is de persoon die een groep maakt de eigenaar. Alle groepen moeten ten minste één eigenaar hebben.

     Als u eigenaren wilt toevoegen, **klikt** u op Pictogram ![ Toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Zoek en selecteer in het dialoogvenster dat wordt weergegeven een geadresseerde of groep en klik vervolgens op **toevoegen >**. Herhaal deze stap zo vaak als nodig is. Klik op **OK**als u klaar bent.

     Als u een eigenaar wilt verwijderen, **Remove** selecteert u de eigenaar en klikt u op ![ Pictogram Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Leden**: Groepsleden toevoegen en verwijderen.

     Als u leden wilt toevoegen, **klikt** u op Pictogram ![ Toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Zoek en selecteer in het dialoogvenster dat wordt weergegeven een geadresseerde of groep en klik vervolgens op **toevoegen >**. Herhaal deze stap zo vaak als nodig is. Klik op **OK**als u klaar bent.

     Als u een lid wilt verwijderen, selecteert u het lid en **klikt** u op Pictogram ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Wanneer u klaar bent, klikt u op **Opslaan** om de distributiegroep te maken.

### <a name="use-the-eac-to-modify-distribution-groups"></a>De EAC gebruiken om distributiegroepen te wijzigen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep of de beveiligingsgroep met e-mail die u wilt wijzigen en klik vervolgens op Pictogram Bewerken **bewerken** ![ ](../../media/ITPro-EAC-AddIcon.png) .

3. Klik op de pagina eigenschappen van de distributiegroep die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik dit tabblad om basisgegevens over de groep weer te geven of te wijzigen.

- **Weergavenaam:** deze naam wordt weergegeven in het adresboek, op de regel Aan wanneer e-mail naar deze groep wordt verzonden en in de **lijst Groepen**. De weergavenaam is vereist en moet gebruiksvriendelijk zijn, zodat mensen herkennen wat het is. Het moet ook uniek zijn in uw domein.

  Als u een groepsnaamgevingsbeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die door het beleid is gedefinieerd.

- **Alias:** dit is het gedeelte van het e-mailadres dat links van het at (@) symbool wordt weergegeven. Als u de alias wijzigt, wordt ook het primaire SMTP-adres voor de groep gewijzigd en de nieuwe alias. Ook wordt het e-mailadres met de vorige alias bewaard als proxyadres voor de groep.

- **E-mailadres**: Het e-mailadres bestaat uit de alias aan de linkerkant van het at (@) symbool en een domein aan de rechterkant. Standaard wordt de waarde van **Alias** gebruikt voor de aliaswaarde, maar u deze wijzigen. Klik voor de domeinwaarde op de vervolgkeuzelijst en selecteer en geaccepteerd domein in uw organisatie.

- **Beschrijving**: Deze beschrijving wordt weergegeven in het adresboek en in het deelvenster Details in de EAC.

#### <a name="ownership"></a>Eigendom

Gebruik dit tabblad om groepseigenaren toe te wijzen. Een groepseigenaar kan groepslidmaatschap beheren. Standaard is de persoon die een groep maakt de eigenaar. Alle groepen moeten ten minste één eigenaar hebben.

Als u eigenaren wilt toevoegen, **klikt** u op Pictogram ![ Toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Zoek en selecteer in het dialoogvenster een geadresseerde en klik vervolgens op **Toevoegen ->**. Herhaal deze stap zo vaak als nodig is. Klik op **OK**als u klaar bent.

Als u een eigenaar wilt verwijderen, **Remove** selecteert u de eigenaar en klikt u op ![ Pictogram Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Lidmaatschap

Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen. Groepseigenaren hoeven geen lid te zijn van de groep.

Als u leden wilt toevoegen, **klikt** u op Pictogram ![ Toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Zoek en selecteer in het dialoogvenster dat wordt weergegeven een geadresseerde of groep en klik vervolgens op **toevoegen >**. Herhaal deze stap zo vaak als nodig is. Klik op **OK**als u klaar bent.

Als u een lid wilt verwijderen, selecteert u het lid en **klikt** u op Pictogram ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>De EAC gebruiken om groepen te verwijderen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep die u wilt verwijderen en **klik** op Pictogram Verwijderen ![ verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>PowerShell gebruiken om groepen te beheren

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen weer te geven

Voer de volgende opdracht uit om een overzichtslijst met alle distributiegroepen en beveiligingsgroepen met e-mail in zelfstandige EOP PowerShell terug te geven:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Als u de lijst met groepsleden wilt retourneren, vervangt u \< GroupIdentity \> door de naam, alias of e-mailadres van de groep en voert u de volgende opdracht uit:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Zie Ontvanger en Groeplid [voor ontvang-distributie](https://docs.microsoft.com/powershell/module/exchange/get-recipient) voor gedetailleerde syntaxis- en parametergegevens. [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Gebruik standalone EOP PowerShell om groepen te maken

Als u distributiegroepen of beveiligingsgroepen met e-mail wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Opmerkingen**:

- De parameter _Naam_ is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Name_ gebruikt voor de weergavenaam.

- Als u de parameter _Alias_ niet gebruikt, wordt de parameter _Name_ gebruikt voor de aliaswaarde. Spaties worden verwijderd en niet-ondersteunde tekens worden omgezet in vraagtekens (?).

- Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de aliaswaarde gebruikt in de parameter _PrimarySmtpAddress._

- Als u de parameter _Type_ niet gebruikt, is de standaardwaarde Distributie.

In dit voorbeeld wordt een distributiegroep met de naam IT-beheerders met de opgegeven eigenschappen gesa.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Zie [Nieuw-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen

Als u groepen in zelfstandige EOP PowerShell wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) gewijzigd voor de groep Werknemers in Seattle in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

In dit voorbeeld worden de huidige leden van de groep Beveiligingsteam vervangen door Kitty Petersen en Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In dit voorbeeld wordt een nieuwe gebruiker met de naam Tyson Fawcett toegevoegd aan de groep met de naam Beveiligingsteam, terwijl de huidige leden van de groep behouden blijven.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="remove-a-group-using-remote-windows-powershell"></a>Een groep verwijderen met externe Windows PowerShell

In dit voorbeeld wordt de distributiegroep met de naam IT-beheerders verwijderd.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd, doet u een van de volgende stappen:

- Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**. Controleer of de groep wordt vermeld (of niet wordt vermeld) en controleer de waarde **van groepstype.** Selecteer de groep en bekijk de informatie in het deelvenster Details of klik op Pictogram Bewerken **bewerken** ![ om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.

- Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt weergegeven (of niet wordt weergegeven):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Vervang \< GroupIdentity \> door de naam, alias of e-mailadres van de groep en voer de volgende opdracht uit om de instellingen te verifiëren:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Als u de groepsleden wilt weergeven, vervangt u \< GroupIdentity \> door de naam, alias of e-mailadres van de groep en voert u de volgende opdracht uit:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
