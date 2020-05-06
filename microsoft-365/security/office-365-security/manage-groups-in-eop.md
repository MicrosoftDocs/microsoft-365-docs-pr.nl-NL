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
description: In dit artikel leert u hoe u groepen met e-mail voor een Exchange-organisatie maken en beheren in Exchange Online Protection (EOP).
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034400"
---
# <a name="manage-groups-in-eop"></a>Groepen beheren in EOP

 U Exchange Online Protection (EOP) gebruiken om groepen met e-mail voor een Exchange-organisatie te maken. U EOP ook gebruiken om groepseigenschappen te definiëren of bij te werken die lidmaatschap, e-mailadressen en andere aspecten van groepen opgeven. U distributiegroepen en beveiligingsgroepen maken, afhankelijk van uw behoeften. Deze groepen kunnen worden gemaakt met behulp van het Exchange-beheercentrum (EAC) of via externe Windows PowerShell.

## <a name="types-of-mail-enabled-groups"></a>Typen e-mailgroepen

U twee typen groepen maken voor uw Exchange-organisatie:

- Distributiegroepen zijn verzamelingen van e-mailgebruikers, zoals een team of een andere ad-hocgroep, die e-mail moeten ontvangen of verzenden met betrekking tot een gemeenschappelijk interessegebied. Distributiegroepen zijn uitsluitend voor het verspreiden van e-mailberichten. In EOP verwijst een distributiegroep naar een groep met e-mailingeschakelde groepen, ongeacht of deze al dan niet een beveiligingscontext heeft.

- Beveiligingsgroepen zijn verzamelingen van e-mailgebruikers die toegangsmachtigingen nodig hebben voor beheerdersrollen. U bijvoorbeeld specifieke machtigingen voor beheerdersvan gebruikers opgeven, zodat ze instellingen voor antispam en anti-malware kunnen configureren.

    > [!NOTE]
    > Standaard vereisen alle nieuwe beveiligingsgroepen met e-mail dat alle afzenders worden geverifieerd. Dit voorkomt dat externe afzenders berichten verzenden naar beveiligingsgroepen met e-mail.

## <a name="before-you-begin"></a>Voordat u begint

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het item 'Distributiegroepen en beveiligingsgroepen' in het onderwerp [Functiemachtigingen in het onderwerp EOP](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.

- Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.

- Houd er rekening mee dat bij het maken en beheren van groepen met Behulp van Exchange Online Protection PowerShell-cmdlets u mogelijk throttling tegenkomen.

- De PowerShell-procedures in dit onderwerp gebruiken een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online Protection.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="create-a-group-in-the-eac"></a>Een groep maken in de EAC

1. Ga in het Exchange-beheercentrum naar **Geadresseerden** \> **Groepen**.

2. Klik **New** ![op](../../media/ITPro-EAC-AddIcon.gif)Nieuw pictogram toevoegen en klik vervolgens op **Distributiegroep** of **Beveiligingsgroep,** afhankelijk van uw behoeften.

3. Configureer de volgende instellingen op de pagina **Nieuwe distributiegroep** of **Nieuwe beveiligingsgroep:**

   - **Weergavenaam:** typ een weergavenaam die uniek is voor uw organisatie en betekenisvol is voor EOP-gebruikers. De weergavenaam is vereist.

   - **Alias:** Typ een groepsalias van maximaal 64 tekens die uniek is voor uw organisatie. EOP-gebruikers typen de alias in de regel Aan: e-mailberichten en de alias wordt opgelost voor de weergavenaam van de groep. Als u de alias wijzigt, wordt ook het primaire SMTP-adres voor de groep gewijzigd en bevat het de nieuwe alias. De alias is vereist.

   - **Beschrijving**: Typ een beschrijving van de groep, zodat mensen het doel van de groep weten.

   - **Eigenaren**: Standaard is de persoon die de groep maakt de eigenaar. U een eigenaar **Add** ![toevoegen door](../../media/ITPro-EAC-AddIcon.gif)Pictogram Toevoegen te kiezen. Alle groepen moeten ten minste één eigenaar hebben.

     > [!NOTE]
     > Eigenaren hoeven geen lid te zijn van de groep.

   - **Leden**: Gebruik deze sectie om groepsleden toe te voegen en om aan te geven of er goedkeuring nodig is voor mensen om lid te worden of de groep te verlaten. Als u leden aan de groep](../../media/ITPro-EAC-AddIcon.gif)wilt toevoegen, **klikt** ![u op Pictogram toevoegen .

4. Klik op **OK** om terug te keren naar de oorspronkelijke pagina.

5. Wanneer u klaar bent, klikt u op **Opslaan** om de groep te maken. De nieuwe groep moet worden weergegeven in de lijst met groepen.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Een groep in de EAC bewerken of verwijderen

1. Navigeer in de EAC naar \> **ontvangersgroepen**. **Recipients**

2. Een van de volgende stappen uitvoeren:

   - Een groep bewerken: klik in de lijst met groepen op de groep die **Edit** ![u wilt](../../media/ITPro-EAC-EditIcon.gif)weergeven of wijzigen en klik vervolgens op Pictogram Bewerken bewerken . U algemene instellingen bijwerken, groepseigenaren toevoegen of verwijderen en groepsleden toevoegen of verwijderen als dat nodig is.

   - Een groep verwijderen: selecteer de **Remove** ![groep](../../media/ITPro-EAC-RemoveIcon.gif)en klik op Pictogram Verwijderen .

3. Klik op **Opslaan**als u klaar bent met het aanbrengen van wijzigingen.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Een groep maken, bewerken of verwijderen met behulp van externe Windows PowerShell

In deze sectie vindt u informatie over het maken van groepen en het wijzigen van hun eigenschappen in Exchange Online Protection PowerShell. Het laat ook zien hoe je een bestaande groep verwijdert.

### <a name="create-a-group-using-remote-windows-powershell"></a>Een groep maken met externe Windows PowerShell

In dit voorbeeld wordt de cmdlet [Nieuw-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) gebruikt om een distributiegroep te maken met een alias van itadmin en de naam IT-beheerders. Het voegt ook gebruikers toe als leden van de groep.

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Opmerking:** Als u een beveiligingsgroep wilt maken `Security` in plaats van een distributiegroep, gebruikt u de waarde voor de parameter *Type.*

Als u wilt controleren of u de groep IT-beheerders hebt gemaakt, voert u de volgende opdracht uit om informatie over de nieuwe groep weer te geven:

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

Zie [Ontvanger opdoen](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)voor gedetailleerde syntaxis- en parametergegevens.

Voer de volgende opdracht uit om een lijst met leden in de groep te krijgen:

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

Zie [Groeplid get-distributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.

Voer de volgende opdracht uit om een volledige lijst met al uw groepen te krijgen:

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>De eigenschappen van een groep wijzigen met behulp van externe Windows PowerShell

Een voordeel van het gebruik van PowerShell in plaats van de EAC is de mogelijkheid om eigenschappen voor meerdere groepen te wijzigen.

Hier volgen enkele voorbeelden van het gebruik van Exchange Online Protection PowerShell om groepseigenschappen te wijzigen.

In dit voorbeeld wordt het primaire SMTP-adres (ook wel het antwoordadres genoemd) gewijzigd voor de groep Werknemers in Seattle in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Zie [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.

Als u wilt controleren of u de eigenschappen voor de groep hebt gewijzigd, voert u de volgende opdracht uit om de nieuwe waarde te verifiëren:

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

In dit voorbeeld worden alle leden van de groep Werknemers in Seattle bijgewerkt. Gebruik een komma om alle leden te scheiden.

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Zie [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)voor gedetailleerde syntaxis- en parameterinformatie.

Voer de volgende opdracht uit om de lijst met alle leden in de groep Werknemers van Seattle te krijgen:

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Een groep verwijderen met externe Windows PowerShell

In dit voorbeeld wordt de distributiegroep met de naam IT-beheerders verwijderd.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Zie [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)voor gedetailleerde syntaxis- en parameterinformatie.

Als u wilt controleren of de groep is verwijderd, voert u de volgende opdracht uit en bevestigt u dat de groep (in dit geval 'It-beheerders') is verwijderd.

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
