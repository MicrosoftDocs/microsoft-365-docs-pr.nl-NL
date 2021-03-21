---
title: Microsoft 365-gebruikersaccounts weergeven met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Meer informatie over het weergeven, weergeven of weergeven van uw Microsoft 365-gebruikersaccounts op verschillende manieren met PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924646"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt het Microsoft 365-beheercentrum gebruiken om de accounts voor uw Microsoft 365-tenant te bekijken. PowerShell voor Microsoft 365 maakt dit mogelijk, maar biedt ook extra functionaliteit.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De Azure Active Directory PowerShell voor Graph-module gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>Alle accounts weergeven

Voer deze opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:
  
```powershell
Get-AzureADUser
```

U krijgt ongeveer dezelfde informatie:
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>Een specifiek account weergeven

Voer de volgende opdracht uit om een specifiek gebruikersaccount weer te geven. Vul de naam van het aanmeldingsaccount in van het gebruikersaccount, dat ook wel de gebruikersnaam (UPN) wordt genoemd. Verwijder de tekens '<' en '>'.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Hier is een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Aanvullende eigenschapswaarden voor een specifiek account weergeven

Standaard worden in **de get-AzureADUser-cmdlet** alleen de *eigenschappen ObjectID,* *DisplayName* en *UserPrincipalName van* accounts weergegeven.

Als u selectiever wilt zijn over  de eigenschappen die moeten worden weergegeven, gebruikt u de cmdlet Selecteren in combinatie met de **cmdlet Get-AzureADUser.** Als u de twee cmdlets wilt combineren, gebruikt u het teken 'pipe' ('|'), waarmee Azure Active Directory PowerShell voor Graph de resultaten van één opdracht krijgt en deze naar de volgende opdracht verzendt. Hier ziet u een voorbeeldopdracht met de *weergavenaam,* *afdeling* en *Gebruikslocatie* voor elk gebruikersaccount:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1.  Alleen de gebruikersnaam, de afdeling en de gebruikslocatie weergeven **(Selecteer DisplayName, Afdeling, UsageLocation).**
  
Als u alle eigenschappen voor een specifiek gebruikersaccount wilt zien, gebruikt u **de** cmdlet Selecteren en het jokerteken (*). Hier is een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Voer als een ander voorbeeld de volgende opdracht uit om de ingeschakelde status van een specifiek gebruikersaccount te controleren:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Accountsynchronisatiestatus weergeven

Gebruikersaccounts hebben twee bronnen: 

- Windows Server Active Directory (AD), accounts die worden gesynchroniseerd van on-premises AD naar de cloud.

- Azure Active Directory(Azure AD) AD-accounts, die rechtstreeks in de cloud worden gemaakt.


De volgende opdracht geeft PowerShell opdracht om alle gebruikers te krijgen die het kenmerk *DirSyncEnabled* hebben ingesteld op *Waar.* U kunt het gebruiken om accounts te zoeken die worden gesynchroniseerd vanuit on-premises AD.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

De volgende opdracht geeft PowerShell opdracht om alle gebruikers te krijgen die het kenmerk *DirSyncEnabled* hebben ingesteld op *Onwaar.* U kunt het gebruiken om alleen-cloudaccounts te zoeken.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Accounts weergeven op basis van een gemeenschappelijke eigenschap

Als u selectiever wilt zijn over de lijst met accounts die u wilt weergeven, kunt u de cmdlet **Where** gebruiken in combinatie met de **get-AzureADUser-cmdlet.** Als u de twee cmdlets wilt combineren, gebruikt u het teken 'pipe' ('|'), waarmee Azure Active Directory PowerShell voor Graph de resultaten van één opdracht krijgt en deze naar de volgende opdracht verzendt. Hier ziet u een voorbeeldopdracht die alleen de gebruikersaccounts wekt die een niet-gespecificeerde gebruikslocatie hebben:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Met deze opdracht geeft Azure Active Directory PowerShell voor Graph instructies voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts met een niet-gespecificeerde gebruikslocatie (**Where {$ \_ . UsageLocation -eq $Null}**). In de accolades geeft de opdracht PowerShell de opdracht alleen de set accounts te vinden waarvoor de eigenschap Gebruikersaccount UsageLocation **$ \_ (. UsageLocation**) is niet opgegeven (**-eq $Null).**
    
De **eigenschap UsageLocation** is slechts een van de vele eigenschappen die zijn gekoppeld aan een gebruikersaccount. Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u **de** cmdlet Selecteren en het jokerteken (*). Hier is een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Plaats is **bijvoorbeeld de** naam van een eigenschap van een gebruikersaccount. U kunt de volgende opdracht gebruiken om alle accounts weer te geven van gebruikers die in Londen wonen:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  De syntaxis voor de **cmdlet** Where in deze voorbeelden is **Where {$ \_ .** [naam van de eigenschap gebruikersaccount] [vergelijkingsoperator] [waarde] **}**.> [vergelijkingsoperator] is **-eq** voor gelijken, **-ne** voor niet gelijk aan, **-lt** voor minder dan, **-gt** voor groter dan en andere.  [waarde] is meestal een tekenreeks (een reeks letters, getallen en andere  tekens), een numerieke waarde of $Null voor niet-gespecificeerde tekens. Zie Where [.](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>Alle accounts weergeven

Voer deze opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.
>

U krijgt ongeveer dezelfde informatie:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

De **get-MsolUser-cmdlet** bevat ook een set parameters om de weergegeven set gebruikersaccounts te filteren. Voer bijvoorbeeld de volgende opdracht uit voor de lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365, maar nog geen licentie hebben gekregen om een van de services te gebruiken:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

U krijgt ongeveer dezelfde informatie:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Zie [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100))voor informatie over aanvullende parameters voor het filteren van de set gebruikersaccounts die worden weergegeven.
  
### <a name="view-a-specific-account"></a>Een specifiek account weergeven

Voer de volgende opdracht uit om een specifiek gebruikersaccount weer te geven. Vul de aanmeldingsnaam in van het gebruikersaccount, dat ook wel de gebruikersnaam (UPN) wordt genoemd. Verwijder de tekens '<' en '>'.
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Accounts weergeven op basis van een gemeenschappelijke eigenschap

Als u selectiever wilt zijn over de lijst met accounts die u wilt weergeven, kunt u de cmdlet **Where** gebruiken in combinatie met de **get-MsolUser-cmdlet.** Als u de twee cmdlets wilt combineren, gebruikt u het teken 'pipe' ("|"), waarmee PowerShell wordt verteld dat de resultaten van één opdracht moeten worden genomen en naar de volgende opdracht moeten worden doorsturen. Hier ziet u een voorbeeld van alleen gebruikersaccounts met een niet-gespecificeerde gebruikslocatie:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts met een niet-gespecificeerde gebruikslocatie (**Where {$ \_ . UsageLocation -eq $Null}**). In de accolades geeft de opdracht PowerShell opdracht om alleen de set accounts te zoeken waarvoor de eigenschap Gebruikersaccount UsageLocation **$ \_ (. UsageLocation**) is niet opgegeven (**-eq $Null).**
    
U krijgt ongeveer dezelfde informatie:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

De *eigenschap UsageLocation* is slechts een van de vele eigenschappen die zijn gekoppeld aan een gebruikersaccount. Als u alle eigenschappen voor gebruikersaccounts wilt zien, gebruikt u de **cmdlet** Selecteren en het jokerteken (*) om ze allemaal weer te geven voor een specifiek gebruikersaccount. Hier is een voorbeeld:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Plaats is *bijvoorbeeld de* naam van een eigenschap van een gebruikersaccount. U kunt de volgende opdracht gebruiken om alle gebruikersaccounts weer te geven voor gebruikers die in Londen wonen:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  De syntaxis voor de **cmdlet** Where in deze voorbeelden is **Where {$ \_ .** [naam van de eigenschap gebruikersaccount] [vergelijkingsoperator] [waarde] **}**.  [vergelijkingsoperator] is **-eq** voor gelijken, **-ne** voor niet gelijk aan, **-lt** voor kleiner dan, **-gt** voor groter dan, en anderen.  [waarde] is meestal een tekenreeks (een reeks letters, getallen en andere  tekens), een numerieke waarde of $Null voor niet-gespecificeerde tekens. Zie Where [.](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  
Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Aanvullende eigenschapswaarden voor accounts weergeven

Standaard worden deze drie eigenschappen van gebruikersaccounts weergegeven op de **get-MsolUser-cmdlet:**
  
- UserPrincipalName
    
- Weergavenaam
    
- isLicensed
    
Als u extra eigenschappen nodig hebt, zoals de afdeling waar de gebruiker werkt en het land/de regio waar de gebruiker  Microsoft 365-services gebruikt, kunt u **Get-MsolUser** uitvoeren in combinatie met de cmdlet Selecteren om de lijst met gebruikersaccounteigenschappen op te geven. Hier is een voorbeeld:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Alleen de gebruikersnaam, de afdeling en de gebruikslocatie weergeven **(Selecteer DisplayName, Afdeling, UsageLocation).**
    
U krijgt ongeveer dezelfde informatie:
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

Met **de** cmdlet Selecteren kunt u kiezen welke eigenschappen u wilt weergeven. Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u het jokerteken (*). Hier is een voorbeeld:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Als u selectiever wilt zijn over de lijst met accounts die u wilt weergeven, kunt u ook de cmdlet **Where** gebruiken. Hier ziet u een voorbeeldopdracht die alleen de gebruikersaccounts wekt die een niet-gespecificeerde gebruikslocatie hebben:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Met deze opdracht wordt PowerShell instructies gegeven voor:
  
1. Ontvang alle informatie over de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts met een niet-gespecificeerde gebruikslocatie (**Where {$ \_ . UsageLocation -eq $Null} )** en stuur de resulterende informatie naar de volgende opdracht ( **|** ). In de accolades geeft de opdracht PowerShell de opdracht alleen de set accounts te vinden waarvoor de eigenschap Gebruikersaccount UsageLocation **$ \_ (. UsageLocation**) is niet opgegeven (**-eq $Null).**
    
1. Alleen de gebruikersnaam, de afdeling en de gebruikslocatie weergeven **(Selecteer DisplayName, Afdeling, UsageLocation).**
    
U krijgt ongeveer dezelfde informatie:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Als u adreslijstsynchronisatie gebruikt om uw Microsoft 365-gebruikers te maken en te beheren, kunt u het lokale account weergeven waaruit een Microsoft 365-gebruiker is geprojecteerd. In het volgende voorbeeld wordt ervan uitgenomen dat:

- Azure AD Connect is geconfigureerd om het standaardbronanker van ObjectGUID te gebruiken. (Zie [Azure AD Connect: Ontwerpconcepten](/azure/active-directory/hybrid/plan-connect-design-concepts)voor meer informatie over het configureren van een bronanker.
- De Active Directory Domain Services-module voor PowerShell is geïnstalleerd (zie [RSAT-hulpprogramma's).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)