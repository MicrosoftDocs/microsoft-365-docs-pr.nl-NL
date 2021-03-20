---
title: Eigenschappen van microsoft 365-gebruikersaccounts configureren met PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Gebruik PowerShell voor Microsoft 365 om eigenschappen van afzonderlijke of meerdere gebruikersaccounts in uw Microsoft 365-tenant te configureren.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911082"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Eigenschappen van microsoft 365-gebruikersaccounts configureren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt het Microsoft 365-beheercentrum gebruiken om eigenschappen te configureren voor de gebruikersaccounts van uw Microsoft 365-tenant. In PowerShell kunt u dit ook doen, plus enkele andere dingen die u niet kunt doen in het beheercentrum.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De Azure Active Directory PowerShell voor Graph-module gebruiken

Als u eigenschappen wilt configureren voor gebruikersaccounts in de Azure Active Directory PowerShell voor Graph-module, gebruikt u de cmdlet [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) en geeft u de eigenschappen op die u wilt instellen of wijzigen.

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Eigenschappen wijzigen voor een specifiek gebruikersaccount

U identificeert het account met de *parameter -ObjectID* en stelt of wijzigt specifieke eigenschappen met behulp van extra parameters. Hier is een lijst met de meest voorkomende parameters:
  
- -Department " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -Achternaam \<user last name> " "
    
- -Mobile " \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress \<street address> " "
    
- -City " \<city name> "
    
- -State " \<state name> "
    
- -Postcode " \<postal code> "
    
- -Country " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Dit is de ISO 3166-1 alfa-2 (A2) land- of regiocode met twee letters.
    
Zie [Set-AzureADUser voor meer parameters.](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)

>[!Note]
>Voordat u licenties kunt toewijzen aan een gebruikersaccount, moet u een gebruikslocatie toewijzen.
>

Voer de volgende opdracht uit om de gebruikersnaam voor uw gebruikersaccounts weer te geven.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Sorteer de lijst met gebruikershoofdnamen alfabetisch **(Sorteer UserPrincipalName)** en verzend deze naar de volgende opdracht ( **|** ).
    
1. Geef alleen de eigenschap User Principal Name weer voor elk account **(Selecteer UserPrincipalName).**

1. Geef ze één scherm tegelijk weer **(Meer).**
    
Als u de gebruikersnaam voor een account wilt weergeven op basis van de weergavenaam (voor- en achternaam), voert u de volgende opdrachten uit. Vul de variabele *$userName* en verwijder de \< and > tekens:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de gebruikersnaam weergegeven voor het gebruikersaccount met de weergavenaam *Caleb Sills.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Met behulp van *$upn* variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam. Hier is een voorbeeld dat de gebruikslocatie van *Belinda Newman* in stelt op Frankrijk. Maar hiermee wordt de weergavenaam opgegeven in plaats van de naam van de hoofdgebruiker:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Eigenschappen wijzigen voor alle gebruikersaccounts

Als u eigenschappen voor alle gebruikers wilt wijzigen, kunt u een combinatie van **de get-AzureADUser-** en **Set-AzureADUser-cmdlets** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Stel de gebruikerslocatie in op Frankrijk (**Set-AzureADUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Eigenschappen wijzigen voor een specifieke set gebruikersaccounts

Als u eigenschappen voor een specifieke set gebruikersaccounts wilt wijzigen, kunt u een combinatie van de **cmdlets Get-AzureADUser**, **Where** en **Set-AzureADUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers van de afdeling Accounting gewijzigd in *Frankrijk:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1.  Zoek alle gebruikersaccounts waarop de *eigenschap Afdeling* is ingesteld op 'Accounting' (**Where {$_. Department -eq "Accounting"} ) en** stuur de resulterende informatie naar de volgende opdracht ( **|** ).
    
1. Stel de gebruikerslocatie in op Frankrijk (**Set-AzureADUser -UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Als u eigenschappen voor gebruikersaccounts wilt configureren met de Microsoft Azure Active Directory-module voor Windows PowerShell, gebruikt u de cmdlet **Set-MsolUser** en geeft u de eigenschappen op die u wilt instellen of wijzigen.

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Eigenschappen wijzigen voor een specifiek gebruikersaccount

Als u eigenschappen voor een specifiek gebruikersaccount wilt configureren, gebruikt u de cmdlet [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) en geeft u de eigenschappen op die u wilt instellen of wijzigen. 

U identificeert het account met *de parameter -UserPrincipalName* en stelt specifieke eigenschappen in of wijzigt deze met behulp van extra parameters. Hier is een lijst met de meest voorkomende parameters.
  
- -City " \<city name> "
    
- -Country " \<country name> "
    
- -Department " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -Fax " \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- -Postcode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State " \<state name> "
    
- -StreetAddress \<street address> " "
    
- -Titel " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Dit is de ISO 3166-1 alfa-2 (A2) land- of regiocode met twee letters.
    
Zie [Set-MsolUser voor meer parameters.](/previous-versions/azure/dn194136(v=azure.100))

Voer de volgende opdracht uit om de gebruikersnamen van al uw gebruikers te zien:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Haal alle informatie op voor de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Sorteer de lijst met gebruikershoofdnamen alfabetisch **(Sorteer UserPrincipalName)** en verzend deze naar de volgende opdracht ( **|** ).
    
1. Geef alleen de eigenschap User Principal Name weer voor elk account **(Selecteer UserPrincipalName).**
    
1. Geef ze één scherm tegelijk weer **(Meer).**
    
Als u de gebruikersnaam voor een account wilt weergeven op basis van de weergavenaam (voor- en achternaam), voert u de volgende opdrachten uit. Vul de variabele *$userName* en verwijder de \< and > tekens.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de gebruikersnaam weergegeven voor de gebruiker met de naam Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Met behulp van *$upn* variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam. Hier is een voorbeeld dat de gebruikslocatie van *Belinda Newman* in frankrijk in *stelt,* maar dat de weergavenaam wordt opgegeven in plaats van de naam van de hoofdgebruiker:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Eigenschappen wijzigen voor alle gebruikersaccounts

Als u eigenschappen voor alle gebruikers wilt wijzigen, gebruikt u een combinatie van **de cmdlets Get-MsolUser** en **Set-MsolUser.** In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Haal alle informatie op voor de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Stel de gebruikerslocatie in op Frankrijk (**Set-MsolUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Eigenschappen wijzigen voor een specifieke set gebruikersaccounts

Als u eigenschappen voor een specifieke set gebruikersaccounts wilt wijzigen, kunt u een combinatie van de **cmdlets Get-MsolUser,** **Where** en **Set-MsolUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers van de afdeling Accounting gewijzigd in *Frankrijk:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Haal alle informatie op voor de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts waarop de *eigenschap Afdeling* is ingesteld op 'Accounting' (**Where {$_. Department -eq "Accounting"}**) en stuur de resulterende informatie naar de volgende opdracht ( **|** ).
    
1. Stel de gebruikerslocatie in op Frankrijk (**Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)