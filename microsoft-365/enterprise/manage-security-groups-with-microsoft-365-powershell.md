---
title: Beveiligingsgroepen beheren met PowerShell
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
description: Meer informatie over het gebruik van PowerShell voor het beheren van beveiligingsgroepen.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073205"
---
# <a name="manage-security-groups-with-powershell"></a>Beveiligingsgroepen beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt PowerShell voor Microsoft 365 als alternatief gebruiken voor het Beheercentrum van Microsoft 365 voor het beheren van beveiligingsgroepen. 

In dit artikel wordt beschreven hoe u de lijst, het maken, wijzigen van instellingen en beveiligingsgroepen verwijdert. 

Voer de volgende stappen uit als u in dit artikel de waarde van een variabele moet opgeven voor een opdracht blokkering in dit artikel.

1. Kopieer het opdracht blok naar het Klembord en plak dit in Kladblok of in de ISE (Integrated script Environment) van PowerShell.
2. Vul de waarden voor de variabele in en verwijder de tekens "<" en ">".
3. Voer de opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.

Zie [lidmaatschap van beveiligingsgroepen onderhouden](maintain-group-membership-with-microsoft-365-powershell.md) om groepslidmaatschap te beheren met PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Uw groepen weergeven

Gebruik deze opdracht om alle groepen weer te geven.

```powershell
Get-AzureADGroup
```
Met deze opdrachten kunt u de instellingen van een specifieke groep weergeven op basis van de weergavenaam.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Een nieuwe groep maken

Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>De instellingen van een groep wijzigen

De instellingen van de groep met deze opdrachten weergeven.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Gebruik vervolgens het artikel [set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) om te bepalen hoe u een instelling kunt wijzigen.

### <a name="remove-a-security-group"></a>Een beveiligingsgroep verwijderen

Met deze opdrachten kunt u een beveiligingsgroep verwijderen.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>De eigenaren van een beveiligingsgroep beheren

Met deze opdrachten kunt u de huidige eigenaren van een beveiligingsgroep weergeven.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Met deze opdrachten kunt u een gebruikersaccount toevoegen door middel van de **UPN (User Principal Name)** van de huidige eigenaren van een beveiligingsgroep.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Gebruik deze opdrachten om een gebruikersaccount toe te voegen aan de **weergegeven naam** van de huidige eigenaren van een beveiligingsgroep.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Met deze opdrachten kunt u een gebruikersaccount door de **UPN** van de huidige eigenaren van een beveiligingsgroep verwijderen.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Met deze opdrachten kunt u een gebruikersaccount verwijderen met de **weergavenaam** van de huidige eigenaren van een beveiligingsgroep.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Uw groepen weergeven

Gebruik deze opdracht om alle groepen weer te geven.

```powershell
Get-MsolGroup
```
Met deze opdrachten kunt u de instellingen van een specifieke groep weergeven op basis van de weergavenaam.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Een nieuwe groep maken

Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>De instellingen van een groep wijzigen

De instellingen van de groep met deze opdrachten weergeven.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Gebruik vervolgens het artikel [set-Remove msolgroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) om te bepalen hoe u een instelling kunt wijzigen.

### <a name="remove-a-security-group"></a>Een beveiligingsgroep verwijderen

Met deze opdrachten kunt u een beveiligingsgroep verwijderen.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

