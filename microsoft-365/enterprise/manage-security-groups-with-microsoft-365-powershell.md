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
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909500"
---
# <a name="manage-security-groups-with-powershell"></a>Beveiligingsgroepen beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt PowerShell voor Microsoft 365 gebruiken als alternatief voor het Microsoft 365 beheercentrum voor het beheren van beveiligingsgroepen. 

In dit artikel wordt beschreven hoe u beveiligingsgroepen kunt maken, maken, wijzigen en verwijderen. 

Als voor een opdrachtblok in dit artikel variabele waarden moeten worden opgegeven, gebruikt u deze stappen.

1. Kopieer het opdrachtblok naar het klembord en plak het in Kladblok of de Geïntegreerde Scriptomgeving (ISE) van PowerShell.
2. Vul de variabele waarden in en verwijder de tekens '<' en '>'.
3. Voer de opdrachten uit in het PowerShell-venster of de PowerShell-ise.

Zie [Lidmaatschap van beveiligingsgroep behouden om](maintain-group-membership-with-microsoft-365-powershell.md) het groepslidmaatschap met PowerShell te beheren.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="list-your-groups"></a>Uw groepen op een lijst zetten

Gebruik deze opdracht om al uw groepen op te geven.

```powershell
Get-AzureADGroup
```
Gebruik deze opdrachten om de instellingen van een bepaalde groep weer te geven op de weergavenaam.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Een nieuwe groep maken

Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>De instellingen voor een groep wijzigen

Geef de instellingen van de groep weer met deze opdrachten.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Gebruik vervolgens het artikel [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) om te bepalen hoe u een instelling wijzigt.

### <a name="remove-a-security-group"></a>Een beveiligingsgroep verwijderen

Gebruik deze opdrachten om een beveiligingsgroep te verwijderen.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>De eigenaren van een beveiligingsgroep beheren

Gebruik deze opdrachten om de huidige eigenaren van een beveiligingsgroep weer te geven.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Gebruik deze opdrachten om een gebruikersaccount op basis van de gebruikersnaam **(UPN)** toe te voegen aan de huidige eigenaren van een beveiligingsgroep.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Gebruik deze opdrachten om een gebruikersaccount op de weergavenaam **toe te** voegen aan de huidige eigenaren van een beveiligingsgroep.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Gebruik deze opdrachten om een gebruikersaccount van de **UPN** te verwijderen naar de huidige eigenaren van een beveiligingsgroep.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Gebruik deze opdrachten om een gebruikersaccount met de **weergavenaam te verwijderen** voor de huidige eigenaren van een beveiligingsgroep.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="list-your-groups"></a>Uw groepen op een lijst zetten

Gebruik deze opdracht om al uw groepen op te geven.

```powershell
Get-MsolGroup
```
Gebruik deze opdrachten om de instellingen van een bepaalde groep weer te geven op de weergavenaam.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Een nieuwe groep maken

Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>De instellingen voor een groep wijzigen

Geef de instellingen van de groep weer met deze opdrachten.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Gebruik vervolgens het artikel [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) om te bepalen hoe u een instelling wijzigt.

### <a name="remove-a-security-group"></a>Een beveiligingsgroep verwijderen

Gebruik deze opdrachten om een beveiligingsgroep te verwijderen.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)