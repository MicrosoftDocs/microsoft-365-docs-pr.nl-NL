---
title: Microsoft 365-gebruikersaccounts maken met PowerShell
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
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: In dit artikel vindt u informatie over het gebruik van PowerShell voor het maken van gebruikersaccounts of meerdere Microsoft 365-gebruikersaccounts.
ms.openlocfilehash: 00ae8806e786eada092704febd65c72c72382788
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235592"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts maken met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met PowerShell voor Microsoft 365 kunt u efficiënt gebruikersaccounts maken, met name meerdere gebruikersaccounts. Wanneer u gebruikersaccounts in PowerShell maakt, zijn bepaalde accounteigenschappen altijd vereist. Andere eigenschappen zijn niet vereist voor het maken van het account, maar zijn anders belangrijk. De eigenschappen in de volgende tabel worden beschreven:
  
|**Naam van eigenschap**|**Vereist?**|**Beschrijving**|
|:-----|:-----|:-----|
|**Weergave** <br/> |Ja  <br/> |Dit is de weergavenaam die wordt gebruikt in Microsoft 365-Services. Bijvoorbeeld Caleb Sills.  <br/> |
|**UserPrincipalName** <br/> |Ja  <br/> |Dit is de accountnaam die wordt gebruikt om u aan te melden bij Microsoft 365-Services. Bijvoorbeeld CalebS@contoso.onmicrosoft.com.  <br/> |
|**Voornaam** <br/> |Nee  <br/> ||
|**Naam** <br/> |Nee  <br/> ||
|**LicenseAssignment** <br/> |Nee  <br/> |Dit is het licentie plan (ook wel bekend als het licentie plan of SKU) van waaruit een beschikbare licentie aan het gebruikersaccount is toegewezen. De licentie definieert de Microsoft 365-services die beschikbaar zijn voor account. Wanneer u het account maakt, hoeft u geen licentie toe te wijzen aan een gebruiker, maar het account vereist een licentie voor toegang tot Microsoft 365-Services. U hebt een licentie voor het gebruikersaccount van 30 dagen nadat u het hebt gemaakt. |
|**Password** <br/> |Nee  <br/> | Als u geen wachtwoord opgeeft, wordt een willekeurig wachtwoord toegewezen aan het gebruikersaccount en wordt het wachtwoord weergegeven in de resultaten van de opdracht. Als u een wachtwoord opgeeft, moet u een wachtwoord van maximaal 16 ASCII-tekens opgeven, van een van de volgende drie typen: kleine letters, hoofdletters, cijfers en symbolen. <br/> |
|**UsageLocation** <br/> |Nee  <br/> |Dit is een geldige ISO 3166-1 alpha-2 landcode. Bijvoorbeeld US voor de Verenigde Staten en FR voor Frankrijk. Het is belangrijk dat u deze waarde oplevert omdat sommige Microsoft 365-Services niet beschikbaar zijn in bepaalde landen, zodat u geen licentie kunt toewijzen aan een gebruikersaccount, tenzij deze waarde is geconfigureerd voor het account. Zie voor meer informatie [over licentiebeperkingen](https://go.microsoft.com/fwlink/p/?LinkId=691730).  <br/> |

>[!Note]
>[Meer informatie over het maken van gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) met het microsoft 365-Beheercentrum. Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Wanneer u verbinding hebt, gebruikt u de volgende syntaxis om een account te maken:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

In dit voorbeeld wordt een account gemaakt voor de gebruikers van de Verenigde Staten met de naam Caleb Sills:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="create-an-individual-user-account"></a>Een afzonderlijke gebruikersaccount maken

Als u een afzonderlijke account wilt maken, gebruikt u de volgende syntaxis:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Met de volgende opdracht kunt u de namen van de beschikbare licentie plannen weergeven:

````powershell
Get-MsolAccountSku
````

In het volgende voorbeeld wordt een account gemaakt voor de gebruikers van de Verenigde Staten met de naam Caleb Sills en wordt een licentie toegewezen aan het `contoso:ENTERPRISEPACK` licentie plan van Office 365 Enterprise E3.
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Meerdere gebruikersaccounts maken

1. Maak een CSV-bestand (door komma's gescheiden waarden) met de vereiste gegevens voor het gebruikersaccount. Bijvoorbeeld:
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
>De kolomnamen en de volgorde van de kolomnamen in de eerste rij van het CSV-bestand zijn willekeurig, maar zorg ervoor dat de gegevens in de rest van het bestand overeenkomen met de volgorde van de kolomnamen en gebruik de kolomnamen voor de parameterwaarden in de PowerShell-opdracht voor Microsoft 365.
    
2. Gebruik de volgende syntaxis:
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

In dit voorbeeld worden de gebruikersaccounts gemaakt van het bestand C:\Mijn Documents\NewAccounts.csv en worden de resultaten van het bestand met de naam C:\Mijn Documents\NewAccountResults.csv vastgelegd.
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. Controleer het uitvoerbestand om de resultaten te bekijken. We hebben geen wachtwoorden opgegeven, dus de willekeurige wachtwoorden die door Microsoft 365 worden gegenereerd, worden weergegeven in het uitvoerbestand.
    
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
