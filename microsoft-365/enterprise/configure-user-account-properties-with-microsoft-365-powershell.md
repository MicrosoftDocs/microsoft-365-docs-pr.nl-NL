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
description: 'Overzicht: gebruik PowerShell voor Microsoft 365 om eigenschappen van afzonderlijke of meerdere gebruikersaccounts in uw Microsoft 365-Tenant te configureren.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580926"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Eigenschappen van Microsoft 365-gebruikersaccounts configureren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken om de eigenschappen van de gebruikersaccounts van uw Microsoft 365-Tenant te configureren, kunt u ook PowerShell gebruiken en de volgende dingen doen, wat niet mogelijk is met het Microsoft 365-Beheercentrum.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Voor het configureren van eigenschappen voor gebruikersaccounts met de module Azure Active Directory PowerShell voor Graph, gebruikt u de cmdlet [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) en geeft u de eigenschappen op die u wilt instellen of wijzigen. 

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Eigenschappen van een specifiek gebruikersaccount wijzigen

U identificeert het account met de parameter **-ObjectID** en stelt of wijzigt specifieke eigenschappen met aanvullende parameters. Hier volgt een lijst met de meest voorkomende parameters.
  
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
    
Zie [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) voor aanvullende parameters.

>[!Note]
>Voordat u licenties kunt toewijzen aan een gebruikersaccount, moet u een gebruikslocatie toewijzen.
>

Voer de volgende opdracht uit om de User Principal-naam van uw gebruikersaccounts weer te geven.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).
    
- Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).

- Toon ze één scherm voor één keer (**meer**).
    
Met deze opdracht worden al uw accounts weergegeven. Als u de User Principal-naam van een account wilt weergeven op basis van de naam van de persoon (voor-en achternaam), vult u de **$username** variabele onder (verwijdert \< and > u de tekens) en voert u de volgende opdrachten uit:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de User Principal name voor het gebruikersaccount weergegeven met de weergavenaam van Caleb Sills.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Met behulp van een **$UPN** -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam. Hier ziet u een voorbeeld van het instellen van de gebruikslocatie van Belinda Newman op Frankrijk, maar het opgeven van een weergavenaam in plaats van de naam van de gebruiker:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Eigenschappen wijzigen voor alle gebruikersaccounts

Als u de eigenschappen van alle gebruikers wilt wijzigen, kunt u de combinatie van de cmdlet **Get-AzureADUser** en **set-AzureADUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in Frankrijk:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts

Als u de eigenschappen van een bepaalde groep gebruikersaccount wilt wijzigen, kunt u de combinatie van de cmdlet **Get-AzureADUser**, **where**en **set-AzureADUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in Frankrijk:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Zoek alle gebruikersaccounts waarvan de afdelings eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**) en stuurt de resultaten naar de volgende opdracht ( **|** ).
    
- Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Voor het configureren van eigenschappen voor gebruikersaccounts met de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt u de cmdlet **set-MsolUser** en geeft u de eigenschappen op die u wilt instellen of wijzigen. 

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Eigenschappen van een specifiek gebruikersaccount wijzigen

Als u de eigenschappen voor een specifiek gebruikersaccount wilt configureren, gebruikt u de cmdlet [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) en geeft u de eigenschappen op die u wilt instellen of wijzigen. 

U identificeert het account met de parameter **-userPrincipalName** en stelt of wijzigt specifieke eigenschappen met aanvullende parameters. Hier volgt een lijst met de meest voorkomende parameters.
  
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
    
Zie [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) voor aanvullende parameters.

Voer de volgende opdracht uit om de hoofdnamen van gebruikers weer te geven voor alle gebruikers.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).
    
- Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).
    
- Toon ze één scherm voor één keer (**meer**).
    
Met deze opdracht worden al uw accounts weergegeven. Als u de User Principal-naam van een account wilt weergeven op basis van de naam van de persoon (voor-en achternaam), vult u de **$username** variabele onder (verwijdert \< and > u de tekens) en voert u de volgende opdrachten uit:
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de User Principal name weergegeven voor de gebruiker met de naam Caleb Sills.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Met behulp van een **$UPN** -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam. Hier ziet u een voorbeeld van het instellen van de gebruikslocatie van Belinda Newman op Frankrijk, maar het opgeven van een weergavenaam in plaats van de naam van de gebruiker:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Eigenschappen wijzigen voor alle gebruikersaccounts

Als u de eigenschappen van alle gebruikers wilt wijzigen, kunt u de combinatie van de cmdlet **Get-MsolUser** en **set-MsolUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in Frankrijk:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts

Als u de eigenschappen van een bepaalde groep gebruikersaccount wilt wijzigen, kunt u de combinatie van de cmdlet **Get-MsolUser**, **where**en **set-MsolUser** gebruiken. In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in Frankrijk:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Zoek alle gebruikersaccounts waarvan de afdelings eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**) en stuurt de resultaten naar de volgende opdracht ( **|** ).
    
- Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).


## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
