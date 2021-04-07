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
description: Beheerders in zelfstandige EOP-organisaties (Exchange Online Protection) kunnen informatie krijgen over het maken, wijzigen en verwijderen van distributiegroepen en beveiligingsgroepen met e-mail in het Exchange-beheercentrum (EAC) en in zelfstandige Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b9d83f2fb59ee8f8d2d3035045ed438d5ba45851
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599567"
---
# <a name="manage-groups-in-eop"></a>Groepen beheren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken kunt u de volgende typen groepen maken, wijzigen en verwijderen:

- **Distributiegroepen:** een verzameling e-mailgebruikers of andere distributiegroepen. Bijvoorbeeld teams of andere ad-hocgroepen die e-mail moeten ontvangen of verzenden in een gemeenschappelijk interessegebied. Distributiegroepen zijn uitsluitend voor het distribueren van e-mailberichten en zijn geen beveiligingsprincipen (ze kunnen geen machtigingen aan hen hebben toegewezen).

- **Beveiligingsgroepen met e-mail:** een verzameling e-mailgebruikers en andere beveiligingsgroepen die toegangsmachtigingen nodig hebben voor beheerdersrollen. U kunt bijvoorbeeld een bepaalde groep gebruikers beheerdersmachtigingen geven, zodat ze antispam- en anti-malware-instellingen kunnen configureren.

    > [!NOTE]
    >
    > - Nieuwe beveiligingsgroepen met e-mail weigeren standaard berichten van externe (niet-nauthenticated) afzenders.
    >
    > - Voeg geen distributiegroepen toe aan beveiligingsgroepen met e-mail.

U kunt groepen beheren in het Exchange-beheercentrum (EAC) en in zelfstandige EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie Exchange-beheercentrum in zelfstandige EOP om het Exchange-beheercentrum [te openen.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Wanneer u groepen beheert in zelfstandige EOP PowerShell, kunt u beperkingen ondervinden. De PowerShell-procedures in dit artikel gebruiken een batchverwerkingsmethode die resulteert in een vertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Distributiegroepen** nodig,  die standaard is toegewezen aan de rollengroepen **Organisatiebeheer** en Geadresseerdenbeheer. Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Het Exchange-beheercentrum gebruiken om distributiegroepen te beheren

### <a name="use-the-eac-to-create-groups"></a>Het EAC gebruiken om groepen te maken

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Klik **op** ![ Nieuw pictogram Nieuw en selecteer een van de volgende ](../../media/ITPro-EAC-AddIcon.png) opties:

   - **Distributiegroep**

   - **Beveiligingsgroep met e-mail**

3. Configureer de volgende instellingen op de nieuwe groepspagina die wordt geopend. Instellingen die zijn gemarkeerd met <sup>\*</sup> een zijn vereist.

   - <sup>\*</sup>**Weergavenaam:** deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel  Aan: wanneer e-mail naar deze groep wordt verzonden en in de lijst Groepen in het EAC. De weergavenaam is vereist, moet uniek zijn en moet gebruiksvriendelijk zijn, zodat mensen herkennen wat het is.

   - <sup>\*</sup>**Alias:** Gebruik dit vak om de naam van de alias voor de groep te typen. De alias mag niet meer dan 64 tekens bevatten en moet uniek zijn. Wanneer een gebruiker de alias in de regel Aan van een e-mailbericht typen, wordt de naam van de groep opgelost.

   - <sup>\*</sup>**E-mailadres:** Het e-mailadres bestaat uit de alias aan de linkerkant van het symbool bij (@) en een domein aan de rechterkant. Standaard wordt de waarde **van Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen. Voor de domeinwaarde klikt u op de vervolgkeuze en selecteert en accepteert u domein in uw organisatie.

   - **Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het deelvenster Details in het EAC.

   - <sup>\*</sup>**Eigenaren:** een groepseigenaar kan het groepslidmaatschap beheren. De persoon die een groep maakt, is standaard de eigenaar. Alle groepen moeten ten minste één eigenaar hebben.

     Als u eigenaren wilt toevoegen, klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Toevoegen ->.** Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK.**

     Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.

   - **Leden:** Groepsleden toevoegen en verwijderen.

     Als u leden wilt toevoegen, klikt **u op Pictogram** Toevoegen ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen. Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Toevoegen ->.** Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK.**

     Als u een lid wilt verwijderen, selecteert u het lid en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.

4. Wanneer u klaar bent, klikt u op **Opslaan om** de distributiegroep te maken.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Het EAC gebruiken om distributiegroepen te wijzigen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep of beveiligingsgroep met e-mail die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/ITPro-EAC-AddIcon.png) bewerken.

3. Klik op de pagina eigenschappen van de distributiegroep die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik dit tabblad om basisgegevens over de groep weer te geven of te wijzigen.

- **Weergavenaam:** Deze naam wordt weergegeven in het adresboek, op de regel Aan wanneer e-mail naar deze groep wordt verzonden en in de **lijst Groepen.** De weergavenaam is vereist en moet gebruiksvriendelijk zijn, zodat mensen herkennen wat het is. Het moet ook uniek zijn in uw domein.

  Als u een groepsnaambeleid hebt geïmplementeerd, moet de weergavenaam voldoen aan de naamgevingsindeling die door het beleid is gedefinieerd.

- **Alias:** dit is het gedeelte van het e-mailadres dat links van het symbool bij (@) wordt weergegeven. Als u de alias wijzigt, wordt het primaire SMTP-adres voor de groep ook gewijzigd en bevat u de nieuwe alias. Het e-mailadres met de vorige alias wordt ook bewaard als proxyadres voor de groep.

- **E-mailadres:** Het e-mailadres bestaat uit de alias aan de linkerkant van het symbool bij (@) en een domein aan de rechterkant. Standaard wordt de waarde **van Alias** gebruikt voor de aliaswaarde, maar u kunt deze wijzigen. Voor de domeinwaarde klikt u op de vervolgkeuze en selecteert en accepteert u domein in uw organisatie.

- **Beschrijving:** Deze beschrijving wordt weergegeven in het adresboek en in het deelvenster Details in het EAC.

#### <a name="ownership"></a>Eigendom

Gebruik dit tabblad om groepseigenaars toe te wijzen. Een groepseigenaar kan het groepslidmaatschap beheren. De persoon die een groep maakt, is standaard de eigenaar. Alle groepen moeten ten minste één eigenaar hebben.

Als u eigenaren wilt toevoegen, klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Toevoegen. Zoek en selecteer een geadresseerde in het dialoogvenster dat wordt weergegeven en klik vervolgens **op Toevoegen ->.** Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK.**

Als u een eigenaar wilt verwijderen, selecteert u de eigenaar en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.

#### <a name="membership"></a>Lidmaatschap

Gebruik dit tabblad om groepsleden toe te voegen of te verwijderen. Groepseigenaren hoeven geen lid te zijn van de groep.

Als u leden wilt toevoegen, klikt **u op Pictogram** Toevoegen ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen. Zoek en selecteer een geadresseerde of groep in het dialoogvenster dat wordt weergegeven en klik vervolgens op **Toevoegen ->.** Herhaal deze stap zo vaak als nodig is. Wanneer u klaar bent, klikt u op **OK.**

Als u een lid wilt verwijderen, selecteert u het lid en klikt u vervolgens **op Pictogram** ![ Verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) verwijderen.

### <a name="use-the-eac-to-remove-groups"></a>Het EAC gebruiken om groepen te verwijderen

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Selecteer in de lijst met groepen de distributiegroep die u wilt verwijderen en klik vervolgens op **Pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

## <a name="use-powershell-to-manage-groups"></a>PowerShell gebruiken om groepen te beheren

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen weer te geven

Voer de volgende opdracht uit als u een overzichtslijst met alle distributiegroepen en beveiligingsgroepen met e-mail wilt retourneren in zelfstandige EOP PowerShell:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Als u de lijst met groepsleden wilt retourneren, vervangt u de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Zie Get-Recipient and Get-DistributionGroupMember [(Get-Recipient and](/powershell/module/exchange/get-recipient) [Get-DistributionGroupMember)](/powershell/module/exchange/get-distributiongroupmember)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen te maken

Als u distributiegroepen of beveiligingsgroepen met e-mail wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Opmerkingen**:

- De _parameter_ Naam is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Naam_ gebruikt voor de weergavenaam.

- Als u de parameter _Alias_ niet gebruikt, wordt de parameter _Naam_ gebruikt voor de aliaswaarde. Spaties worden verwijderd en niet-ondersteunde tekens worden geconverteerd naar vraagtekens (?).

- Als u de parameter _PrimarySmtpAddress_ niet gebruikt, wordt de aliaswaarde gebruikt in de parameter _PrimarySmtpAddress._

- Als u de parameter _Type_ niet gebruikt, is de standaardwaarde Verdeling.

In dit voorbeeld wordt een distributiegroep met de naam IT-beheerders gemaakt met de opgegeven eigenschappen.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Zie [New-EOPDistributionGroup voor](/powershell/module/exchange/New-EOPDistributionGroup)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Zelfstandige EOP PowerShell gebruiken om groepen te wijzigen

Als u groepen in zelfstandige EOP PowerShell wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) voor de groep Werknemers van Seattle gewijzigd in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

In dit voorbeeld worden de huidige leden van de groep Beveiligingsteam vervangen door Kitty Petersen en Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In dit voorbeeld wordt een nieuwe gebruiker met de naam Tyson Fawcett toegevoegd aan de groep Beveiligingsteam met behoud van de huidige leden van de groep.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Zie [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) en [Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="remove-a-group-using-remote-windows-powershell"></a>Een groep verwijderen met behulp van externe Windows PowerShell

In dit voorbeeld wordt de distributiegroep met de naam IT-beheerders verwijderd.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Zie [Remove-EOPDistributionGroup voor](/powershell/module/exchange/remove-eopdistributiongroup)gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga als volgt te werk om te controleren of u een distributiegroep of een beveiligingsgroep met e-mail hebt gemaakt, gewijzigd of verwijderd:

- Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**. Controleer of de groep wordt vermeld (of niet wordt weergegeven) en controleer de **waarde Groeptype.** Selecteer de groep en bekijk de informatie in het deelvenster Details of klik op **Pictogram** ![ Bewerken bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.

- Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de groep wordt vermeld (of niet wordt vermeld):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Vervang \<GroupIdentity\> deze door de naam, alias of het e-mailadres van de groep en voer de volgende opdracht uit om de instellingen te verifiëren:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Als u de groepsleden wilt weergeven, vervangt u de naam, alias of het e-mailadres van de groep en voer \<GroupIdentity\> u de volgende opdracht uit:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```