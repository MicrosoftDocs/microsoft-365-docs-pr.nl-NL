---
title: Toegang tot Microsoft 365-services uitschakelen met PowerShell
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
description: In dit artikel leert u hoe u PowerShell kunt gebruiken om de toegang tot Microsoft 365 voor gebruikers uit te schakelen.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689172"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Toegang tot Microsoft 365-services uitschakelen met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Wanneer aan Microsoft 365-account een licentie is toegewezen vanuit een licentieplan, worden Microsoft 365 services beschikbaar gesteld aan de gebruiker via die licentie. U kunt echter wel de Microsoft 365 services die de gebruiker kan openen. Hoewel de licentie bijvoorbeeld toegang biedt tot de SharePoint Online-service, kunt u de toegang tot de service uitschakelen. U kunt PowerShell gebruiken om toegang tot een bepaald aantal services voor een specifiek licentieplan uit te schakelen voor:

- Een afzonderlijk account.
- Een groep accounts.
- Alle accounts in uw organisatie.

>[!Note]
>Er zijn Microsoft 365 serviceafhankelijkheden waardoor u een opgegeven service niet kunt uitschakelen wanneer andere services ervan afhankelijk zijn.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Gebruik vervolgens deze opdracht om uw beschikbare licentieplannen weer te geven, ook wel AccountSkuIds genoemd:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Zie Licenties en services weergeven met PowerShell voor [meer informatie.](view-licenses-and-services-with-microsoft-365-powershell.md)
    
Zie Accountlicentie- en servicedetails weergeven met PowerShell voor en na de resultaten van de procedures in [dit onderwerp.](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Er is een PowerShell-script beschikbaar dat de procedures automatiseert die in dit onderwerp worden beschreven. Met het script kunt u services weergeven en uitschakelen in uw Microsoft 365 organisatie, inclusief Sway. Zie Toegang tot [Sway uitschakelen met PowerShell voor meer informatie.](disable-access-to-sway-with-microsoft-365-powershell.md)
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Specifieke services Microsoft 365 specifieke gebruikers uitschakelen voor een specifiek licentieplan
  
Voer de volgende stappen uit om Microsoft 365 specifieke set services voor gebruikers voor een specifiek licentieplan uit te schakelen:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Stap 1: Identificeer de ongewenste services in het licentieplan met de volgende syntaxis:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

In het volgende voorbeeld wordt een **Object LicenseOptions** gemaakt dat de Office en SharePoint Online-services uit schakelt in het licentieplan met de naam `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Stap 2: Gebruik het **object LicenseOptions** uit stap 1 voor een of meer gebruikers.
    
Als u een nieuw account wilt maken dat de services heeft uitgeschakeld, gebruikt u de volgende syntaxis:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

In het volgende voorbeeld wordt een nieuw account gemaakt voor Allie Bellew, dat de licentie toewijst en de services uit schakelt die worden beschreven in stap 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Zie Gebruikersaccounts maken met [PowerShell](create-user-accounts-with-microsoft-365-powershell.md)voor meer informatie over het maken van gebruikersaccounts in PowerShell voor Microsoft 365.
    
Als u de services voor een bestaande gelicentieerde gebruiker wilt uitschakelen, gebruikt u de volgende syntaxis:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

In dit voorbeeld worden de services voor de BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Als u de services wilt uitschakelen die worden beschreven in stap 1 voor alle bestaande gelicentieerde gebruikers, geeft u de naam van uw Microsoft 365-abonnement op in de weergave van de **Get-MsolAccountSku-cmdlet** (zoals **litwareinc:ENTERPRISEPACK)** en voert u de volgende opdrachten uit:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Als u de **get-MsolUser-cmdlet** gebruikt zonder de _parameter_ Alle te gebruiken, worden alleen de eerste 500 gebruikersaccounts geretourneerd.

Als u de services voor een groep bestaande gebruikers wilt uitschakelen, gebruikt u een van de volgende methoden om de gebruikers te identificeren:
    
**Methode 1. De accounts filteren op basis van een bestaand accountkenmerk** 

Gebruik hiervoor de volgende syntaxis:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

In het volgende voorbeeld worden de services uitgeschakeld voor gebruikers op de afdeling Verkoop in de Verenigde Staten.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Methode 2: Een lijst met specifieke accounts gebruiken** 

Voer hiervoor de volgende stappen uit:
    
1. Maak een tekstbestand met één account op elke regel als dit:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   In dit voorbeeld is het tekstbestand C: \\ Mijn \\ documentenAccounts.txt.
    
2. Voer de volgende opdracht uit:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Als u de toegang tot services voor meerdere licentieplannen wilt uitschakelen, herhaalt u de bovenstaande instructies voor elk licentieplan en zorgt u ervoor dat:

- Aan de gebruikersaccounts is het licentieplan toegewezen.
- De services die u wilt uitschakelen, zijn beschikbaar in het licentieplan.

Als u Microsoft 365 services voor gebruikers wilt uitschakelen terwijl u ze aan een licentieplan toewijst, gaat u naar Toegang tot services uitschakelen tijdens het toewijzen [van gebruikerslicenties.](disable-access-to-services-while-assigning-user-licenses.md)

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Alle services in een licentieplan toewijzen aan een gebruikersaccount

Voor gebruikersaccounts die services hebben uitgeschakeld, kunt u alle services voor een specifiek licentieplan inschakelen met de volgende opdrachten:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Verwant onderwerp

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
