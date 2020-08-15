---
title: Microsoft 365-tenants beheren met Windows PowerShell voor DAP partners
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
description: In dit artikel vindt u informatie over het gebruik van PowerShell voor Microsoft 365 voor het beheren van uw klant tenancies.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689077"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Microsoft 365-tenants beheren met Windows PowerShell voor Microsoft gemachtigde toegangsmachtigingen (DAP)-partners

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Windows PowerShell biedt ondersteuning voor RSS-en Cloud solution providers voor het gemakkelijk beheren en rapporteren van instellingen voor klant pacht die niet beschikbaar zijn in het Microsoft 365-Beheercentrum. Houd er rekening mee dat de machtigingen van de partner beheerder namens (AOBO) moeten worden beheerd om verbinding te maken met de klant tenancies.
  
De partners van de gedelegeerde toegang (machtigingen) zijn syndicaties en partners van een Cloud solution provider. Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven. Ze bundelt Microsoft 365-abonnementen in hun serviceaanbiedingen voor hun klanten. Wanneer iemand een Microsoft 365-abonnement verkoopt, worden er automatisch beheermachtigingen verleend namens (AOBO) aan de klant tenancies zodat ze de klant tenancies kunnen beheren en rapporteren.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Voor de procedures in dit onderwerp moet u verbinding kunnen maken met [Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md).
  
U hebt ook uw Tenant-beheerderreferenties voor uw partners nodig.
  
## <a name="what-do-you-want-to-do"></a>Wat wilt u doen?

### <a name="list-all-tenant-ids"></a>Alle Tenant-Id's weergeven

> [!NOTE]
> Als u meer dan 500 tenants hebt, bereik dan de syntaxis van de cmdlet met  _all_ of _-MaxResultsParameter_. Dit geldt voor andere cmdlets die een grote uitvoer kunnen bieden, zoals **Get-MsolUser**.
  
Voer de volgende opdracht uit om alle Tenant-Id's van klanten weer te geven waartoe u toegang hebt.
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

Hiermee wordt een lijst met al uw tenants van uw klanten weergegeven op **TenantId**.

>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Een Tenant-ID aanvragen met behulp van de domeinnaam

Voer de volgende opdracht uit om de **TenantId** voor een specifieke klant Tenant op domeinnaam op te zoeken. Vervang _<domainname.onmicrosoft.com->_ door de werkelijke domeinnaam van de Tenant van de klant die u wilt.
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Alle domeinen voor een Tenant weergeven

Voer deze opdracht uit om alle domeinen voor één klant Tenant op te zoeken. Vervangen  _<customer TenantId value>_ door de huidige waarde.
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

Als u extra domeinen hebt geregistreerd, worden alle domeinen weergegeven die zijn gekoppeld aan de klant **TenantId**.
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Een toewijzing van alle tenants en geregistreerde domeinen weergeven

De eerdere PowerShell voor Microsoft 365-opdrachten laten we u zien hoe u Tenant-Id's of domeinen kunt ophalen, maar niet beide tegelijkertijd, en zonder duidelijke toewijzingen. Met deze opdracht wordt een lijst met al uw Tenant-Id's en de domeinen van de klant gegenereerd.
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Alle gebruikers voor een Tenant aanvragen

Hierdoor worden de **userPrincipalName**, de **DisplayName**en de status van de **isLicensed** weergegeven voor alle gebruikers van een bepaalde Tenant. Vervangen _<customer TenantId value>_ door de huidige waarde.
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Alle details van een gebruiker weergeven

Als u alle eigenschappen van een bepaalde gebruiker wilt zien, voert u deze opdracht uit. Vervangen  _<customer TenantId value>_ door _<user principal name value>_ de werkelijke waarden.
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Gebruikers toevoegen, opties instellen en licenties toewijzen

De bulk creatie, configuratie en licenties van Microsoft 365-gebruikers is met name efficiënt met behulp van PowerShell voor Microsoft 365. In deze twee stappen maakt u eerst vermeldingen voor alle gebruikers die u wilt toevoegen in een CSV-bestand (door komma's gescheiden waarden) en importeert u vervolgens dat bestand met behulp van PowerShell voor Microsoft 365. 
  
#### <a name="create-a-csv-file"></a>Een CSV-bestand maken

Maak een CSV-bestand met de volgende indeling:
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
waarbij:
  
- **UsageLocation**: de waarde voor dit is de ISO-land/regiocode van twee tekens van de gebruiker. De landen/regio's kunnen worden opgezocht op het[ISO online-browser platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). De code voor de Verenigde Staten is bijvoorbeeld US en de code voor Brazilië is BR. 
    
- **LicenseAssignment**: de waarde voor dit gebruik wordt in de `syndication-account:<PROVISIONING_ID>` volgende indeling gebruikt: Als u bijvoorbeeld Tenant gebruikers voor de klant toewijst O365_Business_Premium licenties, ziet de waarde van **LicenseAssignment** er als volgt uit: **publicatie van extern account: O365_Business_Premium**. U ziet het PROVISIONING_IDs in de portal van de syndicatie-partner waartoe u toegang hebt als een syndicatie-of CSP-partner.
    
#### <a name="import-the-csv-file-and-create-the-users"></a>Het CSV-bestand importeren en de gebruikers maken

Nadat u uw CSV-bestand hebt gemaakt, voert u deze opdracht uit om gebruikersaccounts te maken met niet-vertraagde wachtwoorden die de gebruiker moet wijzigen bij de eerste aanmelding en de door u opgegeven licentie wordt toegewezen. Zorg ervoor dat u de juiste naam van het CSV-bestand vervangt.
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>Zie ook

#### 

[Help voor partners](https://go.microsoft.com/fwlink/p/?LinkId=533477)

