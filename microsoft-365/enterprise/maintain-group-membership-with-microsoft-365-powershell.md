---
title: Groepslidmaatschap van Microsoft 365 in PowerShell onderhouden
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Meer informatie over het gebruik van PowerShell om lidmaatschap te onderhouden in Microsoft 365 groepen.
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235628"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a>Groepslidmaatschap van Microsoft 365 in PowerShell onderhouden

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt PowerShell voor Microsoft 365 als alternatief voor het Beheercentrum van Microsoft 365 gebruiken om groepslidmaatschappen in Microsoft 365 te onderhouden. 

> [!TIP]
> Als u de kant-en-klare PowerShell-opdrachten wilt genereren door gebruikersaccounts en groepen namen op te geven, gebruikt u deze [groeps onderhoud Microsoft Excel-werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx). 

>[!Note]
>[Meer informatie over het beheren van groepslidmaatschappen van Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) met het microsoft 365-Beheercentrum. Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken
Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Gebruikersaccounts toevoegen of verwijderen als lid van een groep

**Als u een gebruikersaccount wilt toevoegen aan de UPN**, vult u de User Principal Name (UPN) van het gebruikersaccount in en de naam van de groepsweergave, verwijdert u de tekens ' < ' en ' > ' en voert u deze opdrachten uit in het PowerShell-venster of in de ISE (Integrated script Environment) van PowerShell.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een gebruikersaccount wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een gebruikersaccount wilt verwijderen van de UPN**, vult u de UPN van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een gebruikersaccount wilt verwijderen met de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Groepen toevoegen aan of verwijderen uit de groepsleden

Beveiligingsgroepen kunnen andere groepen als leden bevatten. Microsoft 365 groepen is echter niet mogelijk. Dit gedeelte bevat PowerShell-opdrachten voor het toevoegen of verwijderen van groepen voor een beveiligingsgroep.

**Als u een groep wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam in van de groep die u wilt toevoegen, en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een groep op basis van de weergavenaam wilt verwijderen**, vult u de weergavenaam in van de groep die u wilt verwijderen en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Gebruikersaccounts toevoegen of verwijderen als lid van een groep

**Als u een gebruikersaccount wilt toevoegen aan de UPN**, vult u de User Principal Name (UPN) van het gebruikersaccount in en de naam van de groepsweergave, verwijdert u de tekens ' < ' en ' > ' en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een gebruikersaccount wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een gebruikersaccount wilt verwijderen van de UPN**, vult u de UPN van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Als u een gebruikersaccount wilt verwijderen met de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Groepen toevoegen aan of verwijderen uit de groepsleden

Beveiligingsgroepen kunnen andere groepen als leden bevatten. Microsoft 365 groepen is echter niet mogelijk. Dit gedeelte bevat PowerShell-opdrachten voor het toevoegen of verwijderen van groepen voor een beveiligingsgroep.

**Als u een groep wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam in van de groep die u wilt toevoegen, en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

**Als u een groep op basis van de weergavenaam wilt verwijderen**, vult u de weergavenaam in van de groep die u wilt verwijderen en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

