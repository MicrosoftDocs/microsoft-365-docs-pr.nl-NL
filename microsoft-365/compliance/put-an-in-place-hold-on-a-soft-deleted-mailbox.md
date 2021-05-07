---
title: Een postvak In-Place op een zacht verwijderd postvak in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Informatie over het maken van een In-Place Een postvak in de wacht zetten voor een postvak dat zacht is verwijderd, om het inactief te maken en de inhoud ervan te behouden.
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162104"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Een postvak In-Place op een zacht verwijderd postvak in Exchange Online

Informatie over het maken van een In-Place Een postvak in de wacht zetten voor een postvak dat zacht is verwijderd, om het inactief te maken en de inhoud ervan te behouden. Vervolgens kunt u microsoft eDiscovery-hulpprogramma's gebruiken om in het inactieve postvak te zoeken.

> [!IMPORTANT]
> Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange admin center (EAC). Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online. Maar u kunt nog steeds de In-Place in de EAC  beheren of met de cmdlet Postvak Zoeken instellen in Exchange Online PowerShell. Vanaf 1 oktober 2020 kunt u de In-Place beheren. U verwijdert ze alleen in het EAC of met de cmdlet **Remove-MailboxSearch.** Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)
  
U hebt mogelijk een situatie waarbij een persoon uw organisatie heeft verlaten en het bijbehorende gebruikersaccount en bijbehorende postvak zijn verwijderd. Daarna realiseert u zich dat er informatie in het postvak staat die moet worden bewaard. Wat kunt u doen? Als de bewaarperiode van het verwijderde postvak nog niet is verlopen, kunt u een In-Place Bewaring op het verwijderde postvak (een postvak met een soft-verwijderd postvak genoemd) zetten en er een inactief postvak van maken. Een  *inactief postvak*  wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat hij of zij uw organisatie heeft verlaat. De inhoud van een inactief postvak blijft behouden gedurende de duur van de In-Place Hold die is geplaatst in het postvak dat zacht is verwijderd toen het inactief werd gemaakt. Nadat het postvak inactief is gemaakt, kunt u in het postvak zoeken met behulp van In-Place eDiscovery in Exchange Online, Zoeken naar inhoud in het Compliancecentrum voor beveiliging & of het eDiscovery-centrum in SharePoint Online. 
  
> [!NOTE]
> In Exchange Online is een zacht verwijderd postvak een postvak dat is verwijderd, maar binnen een specifieke bewaarperiode kan worden hersteld. De bewaarperiode van het postvak in een Exchange Online is 30 dagen. Dit betekent dat het postvak binnen 30 dagen na het verwijderen kan worden hersteld (of een inactief postvak kan worden gemaakt). Na 30 dagen is een zacht verwijderd postvak gemarkeerd voor permanent verwijderen en kan niet worden hersteld of inactief worden gemaakt. 
  
## <a name="requirements-for-in-place-holds"></a>Vereisten voor In-Place-holds

- U moet de cmdlet **New-MailboxSearch** in Windows PowerShell gebruiken om een In-Place postvak in een zacht verwijderd postvak te zetten. U kunt het EAC (Exchange) of het eDiscovery-centrum niet gebruiken in SharePoint Online. 

- Voor meer informatie over het gebruik Windows PowerShell verbinding maken met Exchange Online, zie [Verbinding maken powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

- Voer de volgende opdracht uit om identiteitsgegevens op te halen over de zacht verwijderde postvakken in uw organisatie. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Zie Overzicht van inactieve postvakken in Office 365 voor [meer informatie over inactieve postvakken.](inactive-mailboxes-in-office-365.md)

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Een postvak In-Place op een zacht verwijderd postvak zetten om er een inactief postvak van te maken

Gebruik de **cmdlet New-MailboxSearch** om van een zacht verwijderd postvak een inactief postvak te maken. Zie [New-MailboxSearch voor](/powershell/module/exchange/new-mailboxsearch)meer informatie.
  
1. Maak een variabele die de eigenschappen van het postvak bevat.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > Gebruik in de vorige opdracht de waarde van de eigenschap **DistinguishedName** of **ExchangeGuid** om het zacht verwijderde postvak te identificeren. Deze eigenschappen zijn uniek voor elk postvak in uw organisatie, terwijl het mogelijk is dat een actief postvak en een zacht verwijderd postvak hetzelfde primaire SMTP-adres hebben. 
  
2. Maak een In-Place Houd vast en plaats het op het postvak met een zachte verwijderde postvak. In dit voorbeeld wordt geen duur van de wachttijd opgegeven. Dit betekent dat items voor onbepaalde tijd worden gehouden of totdat de wacht wordt verwijderd uit het inactieve postvak.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   U kunt ook een duur van de wacht houden opgeven wanneer u de In-Place maken. In dit voorbeeld worden items in het inactieve postvak ongeveer 7 jaar in het postvak op het postvak van de gebruiker op de plaats van de inactieve post.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Voer na een paar ogenblikken een van de volgende opdrachten uit om te controleren of het postvak met een zacht verwijderd postvak een inactief postvak is.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Of
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Meer informatie

Nadat u van een zacht verwijderd postvak een inactief postvak hebt maken, zijn er een aantal manieren waarop u het postvak kunt beheren. Zie voor meer informatie:
  
- [De duur van bewaring van een inactief postvak wijzigen](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Een inactief postvak herstellen](recover-an-inactive-mailbox.md)

- [Een inactief postvak terugzetten](restore-an-inactive-mailbox.md)

- [Een inactief postvak verwijderen](delete-an-inactive-mailbox.md) (door de wacht te verwijderen)