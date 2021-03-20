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
description: PowerShell gebruiken om afzonderlijke of meerdere Microsoft 365-gebruikersaccounts te maken.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907562"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts maken met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt PowerShell voor Microsoft 365 gebruiken om efficiënt gebruikersaccounts te maken, waaronder meerdere accounts.

Wanneer u gebruikersaccounts maakt in PowerShell, zijn bepaalde accounteigenschappen altijd vereist. Andere eigenschappen zijn niet vereist, maar zijn belangrijk. Zie de volgende tabel.
  
|**Eigenschapsnaam**|**Vereist?**|**Beschrijving**|
|:-----|:-----|:-----|
|**Weergavenaam** <br/> |Ja  <br/> |Dit is de weergavenaam die wordt gebruikt in Microsoft 365-services. Bijvoorbeeld: *Caleb Sills.* <br/> |
|**UserPrincipalName** <br/> |Ja  <br/> |Dit is de accountnaam die wordt gebruikt om u aan te melden bij Microsoft 365-services. Bijvoorbeeld: *CalebS \@ contoso.onmicrosoft.com.*  <br/> |
|**Voornaam** <br/> |Nee  <br/> ||
|**Achternaam** <br/> |Nee  <br/> ||
|**LicenseAssignment** <br/> |Nee  <br/> |Dit is het licentieplan (ook wel bekend als het licentieplan of SKU) waaruit een beschikbare licentie is toegewezen aan het gebruikersaccount. De licentie definieert de Microsoft 365-services die beschikbaar zijn voor het account. U hoeft geen licentie toe te wijzen aan een gebruiker wanneer u het account maakt, maar het account moet een licentie hebben voor toegang tot Microsoft 365-services. U hebt 30 dagen de tijd om een licentie voor het gebruikersaccount toe te staan nadat u het hebt aangemaakt. |
|**Password** <br/> |Nee  <br/> | Als u geen wachtwoord opgeeft, wordt een willekeurig wachtwoord toegewezen aan het gebruikersaccount en is het wachtwoord zichtbaar in de resultaten van de opdracht. Als u een wachtwoord opgeeft, moet dit 8 tot 16 ASCII-teksttekens van de volgende typen zijn: kleine letters, hoofdletters, cijfers en symbolen.<br/> |
|**UsageLocation** <br/> |Nee  <br/> |Dit is een geldige ISO 3166-1 alfa-2-landcode. Bijvoorbeeld VS *voor* de Verenigde Staten en *FR* voor Frankrijk. Het is belangrijk om deze waarde te leveren, omdat sommige Microsoft 365-services niet beschikbaar zijn in bepaalde landen. U kunt geen licentie toewijzen aan een gebruikersaccount, tenzij deze waarde is geconfigureerd voor het account. Zie Over licentiebeperkingen [voor meer informatie.](https://go.microsoft.com/fwlink/p/?LinkId=691730)<br/> |

>[!Note]
>[Meer informatie over het maken van gebruikersaccounts](../admin/add-users/add-users.md) met behulp van het Microsoft 365-beheercentrum.
> 
> Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De Azure Active Directory PowerShell voor Graph-module gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijk account te maken:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

In dit voorbeeld wordt een account gemaakt voor de Amerikaanse gebruiker *Caleb Sills:*
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="create-an-individual-user-account"></a>Een individueel gebruikersaccount maken

Als u een afzonderlijk account wilt maken, gebruikt u de volgende syntaxis:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory Module voor Windows PowerShell-module en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.
>

Gebruik deze opdracht om de beschikbare namen van licentieplannen op te geven:

````powershell
Get-MsolAccountSku
````

In dit voorbeeld wordt een account gemaakt voor de Amerikaanse gebruiker *Caleb Sills* en wordt een licentie toegewezen vanuit het `contoso:ENTERPRISEPACK` licentieplan (Office 365 Enterprise E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Meerdere gebruikersaccounts maken

1. Maak een CSV-bestand (door komma's gescheiden waarde) dat de vereiste gebruikersaccountgegevens bevat. Bijvoorbeeld:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >De kolomnamen en de volgorde in de eerste rij van het CSV-bestand zijn willekeurig. Maar zorg ervoor dat de volgorde van de gegevens in de rest van het bestand overeenkomt met de volgorde van de kolomnamen. En gebruik de kolomnamen voor de parameterwaarden in de opdracht PowerShell voor Microsoft 365.
    
2. Gebruik de volgende syntaxis:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   In dit voorbeeld worden gebruikersaccounts gemaakt van het bestand *C:\Mijn Documents\NewAccounts.csv* en worden de resultaten in een bestand met de naam *C:\Mijn Documents\NewAccountResults.csv.*
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Controleer het uitvoerbestand om de resultaten te zien. We hebben geen wachtwoorden opgegeven, dus de willekeurige wachtwoorden die microsoft 365 heeft gegenereerd, zijn zichtbaar in het uitvoerbestand.
    
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)