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
description: Meer informatie over het weergeven, weergeven en weergeven van uw Microsoft 365-gebruikersaccounts op verschillende manieren met PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754070"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met het Microsoft 365-Beheercentrum kunt u de accounts voor uw Microsoft 365-Tenant weergeven. Met PowerShell voor Microsoft 365 kunt u dit maar ook extra functionaliteit bieden.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Alle accounts weergeven

Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:
  
```powershell
Get-AzureADUser
```

U ziet nu informatie over het volgende:
  
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

Voer de volgende opdracht uit als u een specifiek gebruikersaccount wilt weergeven. Vul de naam in van het aanmeldingsaccount van het gebruikersaccount dat ook wel de UPN (User Principal Name) wordt genoemd. De tekens ' < ' en ' > ' verwijderen.
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Hier ziet u een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Extra eigenschapswaarden voor een specifiek account weergeven

Standaard worden met de cmdlet **Get-AzureADUser** alleen de eigenschappen *ObjectID*, *DisplayName*en *userPrincipalName* van accounts weergegeven.

Als u de eigenschappen die u wilt weergeven, verder wilt gebruiken, gebruikt u de cmdlet **Select** in combinatie met de cmdlet **Get-AzureADUser** . Als u de twee cmdlets wilt combineren, gebruikt u het teken ' sluis ' (' | '), waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van een opdracht oplevert en deze naar de volgende opdracht verzenden. Hier ziet u een voorbeeld van een opdracht waarmee u de *naam*, *afdeling*en *UsageLocation* voor elke gebruikersaccount kunt weergeven:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. U ontvangt alle informatie in de gebruikersaccounts (**Get-AzureADUser**) en stuurt u deze naar de volgende opdracht ( **|** ).
    
1.  Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven (**Selecteer DisplayName, Department, UsageLocation**).
  
Als u alle eigenschappen voor een specifiek gebruikersaccount wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (*). Hier ziet u een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Als u een ander voorbeeld, voert u de volgende opdracht uit om de ingeschakelde status van een specifiek gebruikersaccount in te schakelen:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Synchronisatiestatus van een account weergeven

Gebruikersaccounts hebben twee bronnen: 

- Windows Server Active Directory (AD), die accounts zijn die worden gesynchroniseerd vanuit on-premises advertenties met de Cloud.

- AD-accounts van Azure Active Directory (Azure AD) die rechtstreeks in de cloud worden gemaakt.


Met de volgende opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk *DirSyncEnabled* is ingesteld op *waar*. U kunt deze gebruiken om te zoeken naar accounts die worden gesynchroniseerd vanuit on-premises AD.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Met de volgende opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk *DirSyncEnabled* is ingesteld op *False*. U kunt deze gebruiken om alleen Cloud accounts te zoeken.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Accounts weergeven op basis van een gemeenschappelijke eigenschap

Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-AzureADUser** . Als u de twee cmdlets wilt combineren, gebruikt u het teken ' sluis ' (' | '), waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van een opdracht oplevert en deze naar de volgende opdracht verzenden. Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Met deze opdracht krijgt u Azure Active Directory PowerShell voor Graph om het volgende te doen:
  
1. U ontvangt alle informatie in de gebruikersaccounts (**Get-AzureADUser**) en stuurt u deze naar de volgende opdracht ( **|** ).
    
1. Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie (**waarbij {$ \_ . UsageLocation-EQ $Null}**). Met de opdracht wordt in de accolades aangegeven dat PowerShell de accounts waarvan de eigenschap UsageLocation user account (** $ \_ . UsageLocation**) is niet opgegeven (**-EQ $null**).
    
De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld. Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u de cmdlet **Select** en het jokerteken (*). Hier ziet u een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

**Plaats** is bijvoorbeeld de naam van een account eigenschap van een gebruiker. Met de volgende opdracht kunt u een lijst weergeven met alle accounts van gebruikers die in Londen wonen:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  De syntaxis voor de **where** -cmdlet in deze voorbeelden is **WHERE {$ \_ .** [naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**. > [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.  [Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde. Zie [waar](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7), voor meer informatie.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Alle accounts weergeven

Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam. Voer de volgende cmdlets uit vanuit Windows PowerShell.
>

U ziet nu informatie over het volgende:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

De cmdlet **Get-MsolUser** heeft ook een reeks parameters voor het filteren van de set gebruikersaccounts die wordt weergegeven. Als u bijvoorbeeld een lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365 maar nog geen licentie hebt voor het gebruik van de Services), voert u deze opdracht uit:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

U ziet nu informatie over het volgende:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Zie [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))voor meer informatie over aanvullende parameters voor het filteren van de set gebruikersaccounts die worden weergegeven.
  
### <a name="view-a-specific-account"></a>Een specifiek account weergeven

Voer de volgende opdracht uit als u een specifiek gebruikersaccount wilt weergeven. Voer de aanmeldingsnaam van het gebruikersaccount in, dat ook wel de UPN (User Principal Name) wordt genoemd. De tekens ' < ' en ' > ' verwijderen.
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Accounts weergeven op basis van een gemeenschappelijke eigenschap

Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-MsolUser** . Als u de twee cmdlets wilt combineren, gebruikt u het teken ' sluis ' (' | '), waarmee PowerShell de resultaten van één opdracht kan afronden en naar de volgende opdracht kunt verzenden. Hier ziet u een voorbeeld waarin alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. U ontvangt alle informatie in de gebruikersaccounts (**Get-MsolUser**) en stuurt u deze naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts met een niet-opgegeven gebruikslocatie (**waarbij {$ \_ . UsageLocation-EQ $Null}**). Met de opdracht wordt in PowerShell binnen de accolades gezocht naar de accounts waarvan de eigenschap UsageLocation (gebruikersaccount) is ingesteld** $ \_ . UsageLocation**) is niet opgegeven (**-EQ $null**).
    
U ziet nu informatie over het volgende:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

De eigenschap *UsageLocation* is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld. Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

*Plaats* is bijvoorbeeld de naam van een account eigenschap van een gebruiker. Met de volgende opdracht kunt u een lijst weergeven met alle gebruikersaccounts van gebruikers die in Londen wonen:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  De syntaxis voor de **where** -cmdlet in deze voorbeelden is **WHERE {$ \_ .** [naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**.  [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.  [Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde. Zie [waar](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7), voor meer informatie.
  
Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Meer eigenschapswaarden voor accounts weergeven

Standaard worden in de cmdlet **Get-MsolUser** de volgende drie eigenschappen van gebruikersaccounts weergegeven:
  
- UserPrincipalName
    
- Weergave
    
- isLicensed
    
Als u meer eigenschappen nodig hebt, zoals de afdeling met de gebruikers en het land of de regio waar ze Microsoft 365-Services gebruiken, kunt u de cmdlet **Get-MsolUser** gebruiken in combinatie met de **optie Select** om de lijst met eigenschappen van een gebruikersaccount op te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie over de gebruikersaccounts (**Get-MsolUser**) verzenden en verzenden naar de volgende opdracht ( **|** ).
    
1. Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven (**Selecteer DisplayName, Department, UsageLocation**).
    
U ziet nu informatie over het volgende:
  
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

Met de cmdlet **Select** kiest u welke eigenschappen moeten worden weergegeven. Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u het jokerteken (*). Hier ziet u een voorbeeld:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u ook de **where** -cmdlet gebruiken. Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
1. Alle informatie over de gebruikersaccounts (**Get-MsolUser**) verzenden en verzenden naar de volgende opdracht ( **|** ).
    
1. Zoek alle gebruikersaccounts met een niet-opgegeven gebruikslocatie (**waarbij {$ \_ . UsageLocation-EQ $Null}**) en verstuur de bijbehorende informatie naar de volgende opdracht ( **|** ). Met de opdracht wordt in de accolades aangegeven dat PowerShell de accounts waarvan de eigenschap UsageLocation user account (** $ \_ . UsageLocation**) is niet opgegeven (**-EQ $null**).
    
1. Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven (**Selecteer DisplayName, Department, UsageLocation**).
    
U ziet nu informatie over het volgende:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Als u adreslijstsynchronisatie gebruikt voor het maken en beheren van uw Microsoft 365-gebruikers, kunt u het lokale account weergeven waarmee een Microsoft 365-gebruiker is geprojecteerd. In het volgende voorbeeld wordt ervan uitgegaan:

- Azure AD Connect is geconfigureerd voor gebruik van het standaardbron ankerpunt van ObjectGUID. Ga voor meer informatie over het configureren van een bron ankerpunt naar [Azure AD Connect: ontwerp concepten](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts).
- De Active Directory Domain Services-module voor PowerShell is geïnstalleerd (Zie de [hulpmiddelen voor RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
