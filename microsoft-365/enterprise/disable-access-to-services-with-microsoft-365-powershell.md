---
title: Toegang tot Microsoft 365-Services met PowerShell uitschakelen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: In dit artikel wordt uitgelegd hoe u PowerShell gebruikt om de toegang tot Microsoft 365-Services voor gebruikers uit te schakelen.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689172"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Toegang tot Microsoft 365-Services met PowerShell uitschakelen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Wanneer aan een Microsoft 365-account een licentie is toegewezen vanuit een licentie plan, worden Microsoft 365-services beschikbaar gesteld aan de gebruiker uit die licentie. U kunt echter de Microsoft 365-Services beheren waartoe de gebruiker toegang heeft. Hoewel de licentie toegang kan krijgen tot de SharePoint Online-service, kunt u dit bijvoorbeeld uitschakelen. U kunt PowerShell gebruiken om de toegang tot een willekeurig aantal services uit te schakelen voor een specifiek licentie plan:

- Een afzonderlijk account.
- Een groep accounts.
- Alle accounts in uw organisatie.

>[!Note]
>Er zijn Microsoft 365-serviceafhankelijkheden waarmee u een opgegeven service niet kunt uitschakelen wanneer andere services hiervan afhankelijk zijn.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Vervolgens gebruikt u deze opdracht om uw beschikbare licentie-abonnementen, ook wel bekend als AccountSkuIds, weer te geven:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Zie [licenties en services in PowerShell weergeven](view-licenses-and-services-with-microsoft-365-powershell.md)voor meer informatie.
    
Zie [account licentie en servicedetails weergeven met PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)voor een overzicht van de voor-en naresultaten van de procedures in dit onderwerp.
    
Er is een PowerShell-script beschikbaar waarmee de procedures die in dit onderwerp worden beschreven, worden geautomatiseerd. Met name kunt u met het script services weergeven en uitschakelen in uw Microsoft 365-organisatie, waaronder Sway. Zie [toegang tot Sway met PowerShell uitschakelen](disable-access-to-sway-with-microsoft-365-powershell.md)voor meer informatie.
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Specifieke Microsoft 365-Services uitschakelen voor specifieke gebruikers voor een specifiek licentie plan
  
Voer de volgende stappen uit als u een bepaalde set Microsoft 365-Services wilt uitschakelen voor gebruikers voor een specifiek licentie plan:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Stap 1: Identificeer de ongewenste services in het licentie plan met behulp van de volgende syntaxis:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

In het volgende voorbeeld wordt een **LicenseOptions** -object gemaakt waarmee de Office-en SharePoint Online-Services worden uitgeschakeld in het licentie plan `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Stap 2: het **LicenseOptions** -object uit stap 1 van een of meer gebruikers gebruiken.
    
Als u een nieuw account wilt maken waarbij de services zijn uitgeschakeld, gebruikt u de volgende syntaxis:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

In het volgende voorbeeld wordt een nieuw account gemaakt voor Laure Claasen waarmee de licentie wordt toegewezen en de services die worden beschreven in stap 1 uitgeschakeld.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Voor meer informatie over het maken van gebruikersaccounts in PowerShell voor Microsoft 365, raadpleegt u [gebruikersaccounts maken met PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
Gebruik de volgende syntaxis om de services voor een bestaande gelicentieerde gebruiker uit te schakelen:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

In dit voorbeeld worden de services uitgeschakeld voor de gebruiker BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Als u de services uit stap 1 van alle bestaande gebruikers met een licentie wilt uitschakelen, geeft u de naam van uw Microsoft 365-abonnement op via de weergave van de **Get-MsolAccountSku** -cmdlet (zoals **abonnement litwareinc: Enterprise Pack**) en voert u de volgende opdrachten uit:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Als u de cmdlet **Get-MsolUser** gebruikt zonder de parameter _all_ te gebruiken, worden alleen de eerste 500-gebruikersaccounts geretourneerd.

Als u de services voor een groep bestaande gebruikers wilt uitschakelen, gebruikt u een van de volgende methoden om de gebruikers te identificeren:
    
**Methode 1. De accounts filteren op basis van een bestaand account kenmerk** 

Gebruik hiervoor de volgende syntaxis:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

In het volgende voorbeeld worden de services voor gebruikers in de verkoopafdeling in de Verenigde Staten uitgeschakeld.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Methode 2: een lijst met specifieke accounts gebruiken** 

Voer de volgende stappen uit om dit te doen:
    
1. Een tekstbestand maken met één account op elke regel, zoals deze:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   In dit voorbeeld is het tekstbestand C: \\ Mijn documenten \\Accounts.txt.
    
2. Voer de volgende opdracht uit:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Als u de toegang tot services voor meerdere licentie plannen wilt uitschakelen, herhaalt u de bovenstaande instructies voor elk licentie plan, zodat u het volgende kunt doen:

- Aan de gebruikersaccounts is het licentie plan toegewezen.
- De services die u wilt uitschakelen, zijn beschikbaar in het licentie plan.

Als u Microsoft 365-Services wilt uitschakelen voor gebruikers wanneer u ze toewijst aan een licentie plan, raadpleegt [u de toegang tot services uitschakelen tijdens het toewijzen van gebruikerslicenties](disable-access-to-services-while-assigning-user-licenses.md).

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Alle services in een licentie plan toewijzen aan een gebruikersaccount

Voor gebruikersaccounts waarvoor services zijn uitgeschakeld, kunt u alle services inschakelen voor een specifiek licentie plan met de volgende opdrachten:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Verwante onderwerpen

[Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
