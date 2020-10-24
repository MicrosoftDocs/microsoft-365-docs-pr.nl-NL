---
title: Microsoft 365-gebruikersaccounts maken met PowerShell
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
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell gebruiken om afzonderlijke of meerdere gebruikersaccounts van Microsoft 365 te maken.
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754208"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts maken met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met PowerShell voor Microsoft 365 kunt u efficiënt gebruikersaccounts maken, waaronder meerdere accounts.

Wanneer u gebruikersaccounts in PowerShell maakt, zijn bepaalde accounteigenschappen altijd vereist. Andere eigenschappen zijn niet vereist maar zijn belangrijk. Zie de volgende tabel.
  
|**Naam van eigenschap**|**Vereist?**|**Beschrijving**|
|:-----|:-----|:-----|
|**Weergave** <br/> |Ja  <br/> |Dit is de weergavenaam die wordt gebruikt in Microsoft 365-Services. Bijvoorbeeld *Caleb Sills*. <br/> |
|**UserPrincipalName** <br/> |Ja  <br/> |Dit is de accountnaam die wordt gebruikt om u aan te melden bij Microsoft 365-Services. Bijvoorbeeld *CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**Voornaam** <br/> |Nee  <br/> ||
|**Naam** <br/> |Nee  <br/> ||
|**LicenseAssignment** <br/> |Nee  <br/> |Dit is het licentie plan (ook wel bekend als het licentie plan of SKU) van waaruit een beschikbare licentie aan het gebruikersaccount is toegewezen. De licentie definieert de Microsoft 365-services die beschikbaar zijn voor het account. Wanneer u het account maakt, hoeft u geen licentie toe te wijzen aan een gebruiker, maar het account moet een licentie hebben voor toegang tot services van Microsoft 365. U hebt een licentie voor het gebruikersaccount van 30 dagen nadat u het hebt gemaakt. |
|**Password** <br/> |Nee  <br/> | Als u geen wachtwoord opgeeft, wordt een willekeurig wachtwoord toegewezen aan het gebruikersaccount en wordt het wachtwoord weergegeven in de resultaten van de opdracht. Als u een wachtwoord opgeeft, moet u een wachtwoord van 8 tot 16 ASCII-teksttekens van de volgende typen opgeven: kleine letters, hoofdletters, cijfers en symbolen.<br/> |
|**UsageLocation** <br/> |Nee  <br/> |Dit is een geldige ISO 3166-1 alpha-2 landcode. Bijvoorbeeld *US* voor de Verenigde Staten en *fr* voor Frankrijk. Het is belangrijk dat u deze waarde oplevert omdat sommige Microsoft 365-Services niet beschikbaar zijn in bepaalde landen. U kunt geen licentie toewijzen aan een gebruikersaccount, tenzij deze waarde is geconfigureerd voor het account. Zie voor meer informatie [over licentiebeperkingen](https://go.microsoft.com/fwlink/p/?LinkId=691730).<br/> |

>[!Note]
>[Meer informatie over het maken van gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) met het microsoft 365-Beheercentrum.
> 
> Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijk account te maken:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

In dit voorbeeld wordt een account gemaakt voor de US User *Caleb Sills*:
  
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
>PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam. Voer de volgende cmdlets uit vanuit Windows PowerShell.
>

Met de volgende opdracht kunt u de namen van de beschikbare licentie plannen weergeven:

````powershell
Get-MsolAccountSku
````

In dit voorbeeld wordt een account gemaakt voor de US User *Caleb Sills*en wordt een licentie toegewezen aan het `contoso:ENTERPRISEPACK` licentie plan (Office 365 Enterprise E3).
  
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

   >[!NOTE]
   >De kolomnamen en hun volgorde in de eerste rij van het CSV-bestand zijn willekeurig. Zorg ervoor dat de volgorde van de gegevens in de rest van het bestand overeenkomen met de volgorde van de kolomnamen. En gebruik de kolomnamen voor de parameterwaarden in de opdracht PowerShell voor Microsoft 365.
    
2. Gebruik de volgende syntaxis:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   In dit voorbeeld worden gebruikersaccounts gemaakt van het bestand *c:\mijn Documents\NewAccounts.csv* en worden de resultaten Logboeken in een bestand met de naam *C:\My Documents\NewAccountResults.csv*.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Controleer het uitvoerbestand om de resultaten te bekijken. We hebben geen wachtwoorden opgegeven, dus de willekeurige wachtwoorden die door Microsoft 365 worden gegenereerd, worden weergegeven in het uitvoerbestand.
    
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
