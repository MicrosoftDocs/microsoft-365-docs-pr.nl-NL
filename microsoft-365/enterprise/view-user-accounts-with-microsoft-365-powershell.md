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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357896"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken om de accounts voor uw Microsoft 365-Tenant weer te geven, kunt u ook PowerShell voor Microsoft 365 gebruiken en de volgende dingen doen voor het Beheercentrum.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Alle accounts weergeven

Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:
  
```powershell
Get-AzureADUser
```

U dient informatie te zien die er ongeveer als volgt uit ziet:
  
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

Als u een specifiek gebruikersaccount wilt weergeven, vult u de naam van het aanmeldingsaccount van het gebruikersaccount in, ook wel bekend als de UPN (User Principal Name), verwijdert u de tekens ' < ' en ' > ' en voert u deze opdracht uit:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Hier ziet u een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Extra eigenschapswaarden voor een specifiek account weergeven

Standaard worden met de cmdlet **Get-AzureADUser** alleen de eigenschappen ObjectID, DisplayName en userPrincipalName van accounts weergegeven.

Als u de lijst met eigenschappen wilt weergeven, kunt u de cmdlet **SELECT SELECT** gebruiken in combinatie met de cmdlet **Get-AzureADUser** . Als u de twee cmdlets wilt combineren, gebruikt u het teken ' pipe ' | ', waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van één opdracht oplevert en deze naar de volgende opdracht verzenden. Hier ziet u een voorbeeld van een opdracht waarmee u de naam, afdeling en UsageLocation voor elke gebruikersaccount kunt weergeven:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts ( **Get-AzureADUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).
  
Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Als ander voorbeeld kunt u de ingeschakelde status van een specifiek gebruikersaccount controleren met de volgende opdracht:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Synchronisatiestatus van een account weergeven

Gebruikersaccounts bestaan uit twee bronnen: Windows Server Active Directory (AD) voor accounts die worden gesynchroniseerd vanuit on-premises AD-advertenties met de Cloud en Azure AD die accounts rechtstreeks in de Cloud maken.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
Met deze opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk **DirSyncEnabled** is ingesteld op waar. U kunt deze gebruiken voor het opschonen van accounts die worden gesynchroniseerd vanuit on-premises AD.


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
Met deze opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk **DirSyncEnabled** is ingesteld op false. Dit kan worden gebruikt voor het opschonen van Cloud accounts.

### <a name="view-some-accounts-based-on-a-common-property"></a>Sommige accounts weergeven op basis van een gemeenschappelijke eigenschap

Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-AzureADUser** . Als u de twee cmdlets wilt combineren, gebruikt u het teken ' pipe ' | ', waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van één opdracht oplevert en deze naar de volgende opdracht verzenden. Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Met deze opdracht krijgt u Azure Active Directory PowerShell voor Graph om het volgende te doen:
  
- Alle informatie over de gebruikersaccounts ( **Get-AzureADUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ). Met de opdracht wordt in de accolades aangegeven dat PowerShell de set met accounts waarvan de eigenschap UsageLocation user account ( ** $ \_ . UsageLocation** ) is niet opgegeven ( **-EQ $null** ).
    
De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld. Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

In deze lijst is **plaats** bijvoorbeeld de naam van een account eigenschap van een gebruiker. Dit houdt in dat u de volgende opdracht kunt gebruiken om alle gebruikersaccounts van gebruikers in Londen weer te geven:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  De syntaxis voor de **where** -cmdlet wordt weergegeven in de volgende voorbeelden: **{$ \_ .** [naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**. > [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.  [Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven> Zie [waar](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) voor meer informatie.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Alle accounts weergeven

Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

U dient informatie te zien die er ongeveer als volgt uit ziet:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

De cmdlet **Get-MsolUser** heeft ook een reeks parameters voor het filteren van de set gebruikersaccounts die wordt weergegeven. Voer deze opdracht uit voor een lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365 maar nog geen licentie hebben voor het gebruik van een van de Services).
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

U dient informatie te zien die er ongeveer als volgt uit ziet:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Zie [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))voor meer informatie over aanvullende parameters voor het filteren van de weergave van de weergegeven gebruikersaccounts.
  
### <a name="view-a-specific-account"></a>Een specifiek account weergeven

Als u een specifiek gebruikersaccount wilt weergeven, vult u de aanmeldingsnaam van het gebruikersaccount van het gebruikersaccount in, ook wel bekend als de UPN (User Principal Name), verwijder de tekens ' < ' en ' > ' en voer deze opdracht uit:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Sommige accounts weergeven op basis van een gemeenschappelijke eigenschap

Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-MsolUser** . Om de twee cmdlets te combineren, gebruiken we het teken ' pipe ' | ', waarmee wordt aangegeven dat PowerShell de resultaten van één opdracht moet aannemen en deze naar de volgende opdracht kan verzenden. Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ). Met de opdracht wordt in de accolades aangegeven dat PowerShell de set met accounts waarvan de eigenschap UsageLocation user account ( ** $ \_ . UsageLocation** ) is niet opgegeven ( **-EQ $null** ).
    
U dient informatie te zien die er ongeveer als volgt uit ziet:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld. Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

In deze lijst is **plaats** bijvoorbeeld de naam van een account eigenschap van een gebruiker. Dit houdt in dat u de volgende opdracht kunt gebruiken om alle gebruikersaccounts van gebruikers in Londen weer te geven:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  De syntaxis voor de **where** -cmdlet wordt weergegeven in de volgende voorbeelden: **{$ \_ .** [naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**.  [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.  [Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde. Zie [waar](https://technet.microsoft.com/library/hh849715.aspx) vindt u meer informatie.
  
Met de volgende opdracht kunt u de geblokkeerde status van een gebruikersaccount controleren:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Meer eigenschapswaarden voor accounts weergeven

Met de cmdlet **Get-MsolUser** worden standaard drie eigenschappen van gebruikersaccounts weergegeven:
  
- UserPrincipalName
    
- Weergave
    
- isLicensed
    
Als u meer eigenschappen nodig hebt, zoals de afdeling waarin de gebruiker werkt, en het land of de regio waarin de gebruiker Microsoft 365-Services gebruikt, kunt u de cmdlet **Get-MsolUser** in combinatie met de **Select** -cmdlet gebruiken om de lijst met eigenschappen van een gebruikersaccount op te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).
    
U dient informatie te zien die er ongeveer als volgt uit ziet:
  
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

Met de cmdlet **Select selecteert** u de eigenschappen die u wilt weergeven en kiest u de gewenste opdracht. Als u alle eigenschappen voor gebruikersaccounts wilt zien, gebruikt u het jokerteken (*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven. Hier ziet u een voorbeeld:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u ook de **where** -cmdlet gebruiken. Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Met deze opdracht wordt PowerShell overgeïnstrueerd:
  
- Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).
    
- Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ) en verstuur de bijbehorende informatie naar de volgende opdracht ( **|** ). Binnen de accolades moet de opdracht PowerShell geïnstrueerd om alleen de groep met accounts te vinden waarin de eigenschap UsageLocation van het gebruikersaccount ( ** $ \_ . UsageLocation** ) is niet opgegeven ( **-EQ $null** ).
    
- Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).
    
U dient informatie te zien die er ongeveer als volgt uit ziet:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Als u adreslijstsynchronisatie gebruikt voor het maken en beheren van uw Microsoft 365-gebruikers, kunt u weergeven naar welke lokale account een Microsoft 365-gebruiker is geprojecteerd. In de volgende stappen wordt ervan uitgegaan dat Azure AD Connect is geconfigureerd voor gebruik van het standaardbron ankerpunt van ObjectGUID (Zie [Azure AD Connect: ontwerp concepten](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) en wordt ervan uitgegaan dat de Active Directory Domain Services-module voor PowerShell is geïnstalleerd (Zie [RSAT-hulpmiddelen](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
