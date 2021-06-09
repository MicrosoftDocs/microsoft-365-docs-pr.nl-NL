---
title: Beheer Microsoft 365 tenants met Windows PowerShell voor DAP-partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: In dit artikel leert u hoe u PowerShell kunt gebruiken voor Microsoft 365 om uw klantentenancies te beheren.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689077"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Beheer Microsoft 365 tenants met Windows PowerShell voor DAP-partners (Gedelegeerde Toegangsmachtigingen)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Windows PowerShell kunnen syndicatie- en Cloud Solution Provider(CSP)-partners eenvoudig instellingen voor klantpachten beheren en rapporteren die niet beschikbaar zijn in het Microsoft 365 beheercentrum. Houd er rekening mee dat machtigingen voor het beheren namens (AOBO) vereist zijn voor het account van de partnerbeheerder om verbinding te maken met de klanttenancies.
  
DAP-partners (Gedelegeerde Access Permission) zijn Syndication- en Cloud Solution Providers (CSP)-partners. Ze zijn vaak netwerk- of telecomproviders voor andere bedrijven. Ze bundelen Microsoft 365 abonnementen in hun serviceaanbiedingen voor hun klanten. Wanneer ze een Microsoft 365-abonnement verkopen, worden ze automatisch machtigingen voor beheer namens (AOBO) verleend aan de klanten, zodat ze de klantentenancies kunnen beheren en rapporteren.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Voor de procedures in dit onderwerp moet u verbinding maken met Verbinding maken [met Microsoft 365 PowerShell.](connect-to-microsoft-365-powershell.md)
  
U hebt ook de referenties van de partnertenatiebeheerder nodig.
  
## <a name="what-do-you-want-to-do"></a>Wat wilt u doen?

### <a name="list-all-tenant-ids"></a>Alle tenant-ID's op een lijst zetten

> [!NOTE]
> Als u meer dan 500 tenants hebt, kunt u de syntaxis van de cmdlet bereiken met de syntaxis _-Alles_ of _-MaxResultsParameter._ Dit geldt voor andere cmdlets die een grote uitvoer kunnen geven, zoals **Get-MsolUser.**
  
Voer deze opdracht uit om alle klanttenatie-id's weer te geven tot wie u toegang hebt.
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

Hier wordt een lijst weergegeven met alle klanttententen van **TenantId.**

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Een tenant-id krijgen met de domeinnaam

Voer deze opdracht uit om **tenantid** voor een specifieke klant tenant op domeinnaam te krijgen. Vervang _<domainname.onmicrosoft.com>_ door de werkelijke domeinnaam van de klant tenant die u wilt.
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Alle domeinen voor een tenant op een lijst zetten

Voer deze opdracht uit om alle domeinen voor één klantten tenant te krijgen. Vervangen  _<customer TenantId value>_ door de werkelijke waarde.
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

Als u extra domeinen hebt geregistreerd, worden alle domeinen die zijn gekoppeld aan de klant **TenantId, als retourneert.**
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Een toewijzing van alle tenants en geregistreerde domeinen krijgen

In de vorige PowerShell-opdrachten voor Microsoft 365-opdrachten werd getoond hoe u tenant--ed's of domeinen kunt ophalen, maar niet beide tegelijk en zonder dat u ze allemaal duidelijk kunt toewijzen. Met deze opdracht wordt een lijst gegenereerd met al uw tenant-1D's voor klanten en hun domeinen.
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Alle gebruikers voor een tenant krijgen

Hiermee worden de **UserPrincipalName,** **de DisplayName** en de **status isLicensed** weergegeven voor alle gebruikers voor een bepaalde tenant. Vervangen _<customer TenantId value>_ door de werkelijke waarde.
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Alle details over een gebruiker bekijken

Als u alle eigenschappen van een bepaalde gebruiker wilt zien, kunt u deze opdracht uitvoeren. Vervang  _<customer TenantId value>_ en door de werkelijke _<user principal name value>_ waarden.
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Gebruikers toevoegen, opties instellen en licenties toewijzen

Het bulksgewijs maken, configureren en licentieverlenen van Microsoft 365 gebruikers is met name efficiënt door PowerShell te gebruiken voor Microsoft 365. In dit proces in twee stappen maakt u eerst items voor alle gebruikers die u wilt toevoegen in een CSV-bestand (door komma's gescheiden waarde) en importeert u dat bestand vervolgens met PowerShell voor Microsoft 365. 
  
#### <a name="create-a-csv-file"></a>Een CSV-bestand maken

Maak een CSV-bestand met behulp van deze indeling:
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
waarbij:
  
- **UsageLocation:** De waarde hiervoor is de tweeletterig ISO-land-/regiocode van de gebruiker. De land-/regiocodes kunnen worden op gezocht op het[ISO Online Browsing Platform.](https://go.microsoft.com/fwlink/p/?LinkId=532703) De code voor de Verenigde Staten is bijvoorbeeld VS en de code voor Brazilië is BR. 
    
- **LicenseAssignment**: Voor de waarde hiervoor wordt deze indeling gebruikt: `syndication-account:<PROVISIONING_ID>` . Als u bijvoorbeeld klanttenatiegebruikers O365_Business_Premium licenties toewijst, ziet de waarde **LicenseAssignment** er zo uit: **syndication-account:O365_Business_Premium.** U vindt de PROVISIONING_IDs in de Syndication Partner Portal waar u toegang toe hebt als syndication- of CSP-partner.
    
#### <a name="import-the-csv-file-and-create-the-users"></a>Het CSV-bestand importeren en de gebruikers maken

Nadat u uw CSV-bestand hebt gemaakt, kunt u deze opdracht uitvoeren om gebruikersaccounts te maken met niet-verlopende wachtwoorden die de gebruiker bij de eerste aanmelding moet wijzigen en die de licentie toewijst die u opgeeft. Zorg ervoor dat u de juiste CSV-bestandsnaam vervangt.
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>Zie ook

#### 

[Help voor partners](https://go.microsoft.com/fwlink/p/?LinkId=533477)

