---
title: Lidmaatschap van beveiligingsgroep behouden met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Meer informatie over het gebruik van PowerShell om het lidmaatschap van Microsoft 365 behouden.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909572"
---
# <a name="maintain-security-group-membership-with-powershell"></a>Lidmaatschap van beveiligingsgroep behouden met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt PowerShell voor Microsoft 365 gebruiken als alternatief voor het Microsoft 365-beheercentrum om het lidmaatschap van beveiligingsgroep in Microsoft 365. 

>[!Note]
>[Lees hoe u het lidmaatschap van Microsoft 365 groep kunt behouden](../admin/create-groups/add-or-remove-members-from-groups.md) met het Microsoft 365 beheercentrum. Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module
Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Gebruikersaccounts toevoegen of verwijderen als leden van een groep

Als u een gebruikersaccount wilt toevoegen op basis van **de UPN,** vult u de user account User Principal Name (UPN) in (bijvoorbeeld: belindan@contoso.com) en de weergavenaam van de beveiligingsgroep, verwijdert u de tekens '<' en '>' en voert u deze opdrachten uit in het PowerShell-venster of de Geïntegreerde Scriptomgeving van PowerShell (ISE).

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een gebruikersaccount wilt toevoegen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een gebruikersaccount wilt verwijderen met **de UPN,** vult u de UPN van het gebruikersaccount in (bijvoorbeeld: belindan@contoso.com) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een **gebruikersaccount** wilt verwijderen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Groepen toevoegen of verwijderen als leden van een groep

Beveiligingsgroepen kunnen andere groepen als leden bevatten. Microsoft 365 groepen kunnen echter niet. Deze sectie bevat PowerShell-opdrachten om groepen alleen voor een beveiligingsgroep toe te voegen of te verwijderen.

Als u een groep wilt toevoegen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat toevoegen en de weergavenaam van de groep die de ledengroep bevat en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een groep wilt verwijderen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat verwijderen en de weergavenaam van de groep met de ledengroep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Gebruikersaccounts toevoegen of verwijderen als leden van een groep

Als u een gebruikersaccount wilt toevoegen op basis van **de UPN,** vult u de upn (User Principal Name) (user account User Principal Name) (voorbeeld: belindan@contoso.com) en de weergavenaam van de groep in, verwijdert u de tekens '<' en '>' en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een gebruikersaccount wilt toevoegen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een gebruikersaccount wilt verwijderen met **de UPN,** vult u de UPN van het gebruikersaccount in (bijvoorbeeld: belindan@contoso.com) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Als u een **gebruikersaccount** wilt verwijderen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Groepen toevoegen of verwijderen als leden van een groep

Beveiligingsgroepen kunnen andere groepen als leden bevatten. Microsoft 365 groepen kunnen echter niet. Deze sectie bevat PowerShell-opdrachten om groepen alleen voor een beveiligingsgroep toe te voegen of te verwijderen.

Als u een groep wilt toevoegen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat toevoegen en de weergavenaam van de groep die de ledengroep bevat en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

Als u een groep wilt verwijderen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat verwijderen en de weergavenaam van de groep met de ledengroep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)