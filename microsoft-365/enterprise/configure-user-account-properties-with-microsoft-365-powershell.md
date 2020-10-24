---
title: Eigenschappen van Microsoft 365-gebruikersaccounts configureren met PowerShell
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
description: Gebruik PowerShell voor Microsoft 365 om eigenschappen van afzonderlijke of meerdere gebruikersaccounts in uw Microsoft 365-Tenant te configureren.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754326"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Eigenschappen van Microsoft 365-gebruikersaccounts configureren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met het Microsoft 365-Beheercentrum kunt u de eigenschappen van de gebruikersaccounts van uw Microsoft 365-Tenant configureren. In PowerShell kunt u dit ook doen, en wel wat andere dingen die u niet kunt doen in het Beheercentrum.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Als u de eigenschappen van gebruikersaccounts in de module Azure Active Directory PowerShell voor Graph wilt configureren, gebruikt u de cmdlet [**set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) en geeft u de eigenschappen op die u wilt instellen of wijzigen.

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Eigenschappen van een specifiek gebruikersaccount wijzigen

U identificeert het account met de parameter *-ObjectID* en stelt of wijzigt specifieke eigenschappen met behulp van aanvullende parameters. Hier volgt een lijst met de meest voorkomende parameters:
  
- -Afdeling " \<department name> "
    
- Naam van een \<full user name> '
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -Benaming " \<user first name> "
    
- -Achternaam " \<user last name> "
    
- -Mobiel " \<mobile phone number> "
    
- -JobTitle \<job title>
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -Plaats " \<city name> "
    
- -Status " \<state name> "
    
- -Postcode " \<postal code> "
    
- -Land " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Dit is de ISO 3166-1 alfa-2 (a2) land-of regiocode van twee letters.
    
Zie [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) voor aanvullende parameters.

>[!Note]
>Voordat u licenties kunt toewijzen aan een gebruikersaccount, moet u een gebruikslocatie toewijzen.
>

Voer de volgende opdracht uit om de User Principal-naam van uw gebruikersaccounts weer te geven.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. U ontvangt alle informatie in de gebruikersaccounts (**Get-AzureADUser**) en stuurt u deze naar de volgende opdracht ( **|** ).
    
1. De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).
    
1. Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).

1. Toon ze één scherm voor één keer (**meer**).
    
Voer de volgende opdrachten uit om de User Principal-naam van een account weer te geven op basis van de weergavenaam (voornaam en achternaam). Voer de *$username* variabele in en verwijder de \< and > tekens:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de User Principal name weergegeven voor het gebruikersaccount met de weergavenaam *Caleb Sills*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Met behulp van een *$UPN* -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam. Hier ziet u een voorbeeld waarin de gebruikslocatie van *Belinda Newman*wordt ingesteld op Frankrijk. Maar geeft de naam van de gebruikersnaam in plaats van de UPN van de gebruikersnaam aan.
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Eigenschappen wijzigen voor alle gebruikersaccounts

Als u de eigenschappen van alle gebruikers wilt wijzigen, kunt u een combinatie van de cmdlet **Get-AzureADUser** en **set-AzureADUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk*:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
1. Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts

Als u de eigenschappen van een bepaalde groep gebruikersaccounts wilt wijzigen, kunt u een combinatie van de cmdlet **Get-AzureADUser**, **where**en **set-AzureADUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in *Frankrijk*:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
1.  Zoek alle gebruikersaccounts waarvan de *afdelings* eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**), en stuurt de daaruit verlichte informatie naar de volgende opdracht ( **|** ).
    
1. Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Als u de eigenschappen van gebruikersaccounts met de Microsoft Azure Active Directory-module voor Windows PowerShell wilt configureren, gebruikt u de cmdlet **set-MsolUser** en geeft u de eigenschappen op die u wilt instellen of wijzigen.

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam. Voer de volgende cmdlets uit vanuit Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Eigenschappen van een specifiek gebruikersaccount wijzigen

Als u de eigenschappen voor een specifiek gebruikersaccount wilt configureren, gebruikt u de cmdlet [**set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) en geeft u de eigenschappen op die u wilt instellen of wijzigen. 

U identificeert het account met de parameter *-userPrincipalName* en stelt of wijzigt specifieke eigenschappen met behulp van aanvullende parameters. Hier volgt een lijst met de meest voorkomende parameters.
  
- -Plaats " \<city name> "
    
- -Land " \<country name> "
    
- -Afdeling " \<department name> "
    
- Naam van een \<full user name> '
    
- -Fax " \<fax number> "
    
- -Voornaam " \<user first name> "
    
- -Achternaam " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- -Postcode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -Status " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Titel " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Dit is de ISO 3166-1 alfa-2 (a2) land-of regiocode van twee letters.
    
Zie [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))voor aanvullende parameters.

Voer de volgende opdracht uit om de hoofdnamen van gebruikers van alle gebruikers weer te geven:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie voor de gebruikersaccounts (**Get-MsolUser**) weergeven en verzenden naar de volgende opdracht ( **|** ).
    
1. De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).
    
1. Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).
    
1. Toon ze één scherm voor één keer (**meer**).
    
Voer de volgende opdrachten uit om de User Principal-naam van een account weer te geven op basis van de weergavenaam (voornaam en achternaam). Voer de *$username* variabele in en verwijder de \< and > tekens.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de User Principal name van de gebruiker met de naam Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Met behulp van een *$UPN* -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam. Hier ziet u een voorbeeld waarin de gebruikslocatie van *Belinda Newman*wordt ingesteld op *Frankrijk*, maar geeft de naam van de gebruikersnaam in plaats van de UPN van de gebruikersnaam aan:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Eigenschappen wijzigen voor alle gebruikersaccounts

Als u de eigenschappen van alle gebruikers wilt wijzigen, gebruikt u een combinatie van de cmdlet **Get-MsolUser** en **set-MsolUser** . In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk*:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie voor de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
1. Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts

Als u de eigenschappen van een bepaalde groep gebruikersaccounts wilt wijzigen, kunt u een combinatie van de cmdlet **Get-MsolUser**, **where**en **set-MsolUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in *Frankrijk*:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie voor de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts waarvan de *afdelings* eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**) en stuurt de resultaten naar de volgende opdracht ( **|** ).
    
1. Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
