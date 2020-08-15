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
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="5e306-103">Microsoft 365-tenants beheren met Windows PowerShell voor Microsoft gemachtigde toegangsmachtigingen (DAP)-partners</span><span class="sxs-lookup"><span data-stu-id="5e306-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="5e306-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5e306-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5e306-105">Windows PowerShell biedt ondersteuning voor RSS-en Cloud solution providers voor het gemakkelijk beheren en rapporteren van instellingen voor klant pacht die niet beschikbaar zijn in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5e306-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5e306-106">Houd er rekening mee dat de machtigingen van de partner beheerder namens (AOBO) moeten worden beheerd om verbinding te maken met de klant tenancies.</span><span class="sxs-lookup"><span data-stu-id="5e306-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>
  
<span data-ttu-id="5e306-107">De partners van de gedelegeerde toegang (machtigingen) zijn syndicaties en partners van een Cloud solution provider.</span><span class="sxs-lookup"><span data-stu-id="5e306-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="5e306-108">Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="5e306-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="5e306-109">Ze bundelt Microsoft 365-abonnementen in hun serviceaanbiedingen voor hun klanten.</span><span class="sxs-lookup"><span data-stu-id="5e306-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="5e306-110">Wanneer iemand een Microsoft 365-abonnement verkoopt, worden er automatisch beheermachtigingen verleend namens (AOBO) aan de klant tenancies zodat ze de klant tenancies kunnen beheren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="5e306-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5e306-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5e306-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="5e306-112">Voor de procedures in dit onderwerp moet u verbinding kunnen maken met [Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5e306-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="5e306-113">U hebt ook uw Tenant-beheerderreferenties voor uw partners nodig.</span><span class="sxs-lookup"><span data-stu-id="5e306-113">You also need your partner tenant administrator credentials.</span></span>
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="5e306-114">Wat wilt u doen?</span><span class="sxs-lookup"><span data-stu-id="5e306-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="5e306-115">Alle Tenant-Id's weergeven</span><span class="sxs-lookup"><span data-stu-id="5e306-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="5e306-116">Als u meer dan 500 tenants hebt, bereik dan de syntaxis van de cmdlet met  _all_ of _-MaxResultsParameter_.</span><span class="sxs-lookup"><span data-stu-id="5e306-116">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_.</span></span> <span data-ttu-id="5e306-117">Dit geldt voor andere cmdlets die een grote uitvoer kunnen bieden, zoals **Get-MsolUser**.</span><span class="sxs-lookup"><span data-stu-id="5e306-117">This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>
  
<span data-ttu-id="5e306-118">Voer de volgende opdracht uit om alle Tenant-Id's van klanten weer te geven waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="5e306-118">To list all customer tenant Ids that you have access to, run this command.</span></span>
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="5e306-119">Hiermee wordt een lijst met al uw tenants van uw klanten weergegeven op **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="5e306-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="5e306-120">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="5e306-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5e306-121">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e306-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="5e306-122">Een Tenant-ID aanvragen met behulp van de domeinnaam</span><span class="sxs-lookup"><span data-stu-id="5e306-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="5e306-123">Voer de volgende opdracht uit om de **TenantId** voor een specifieke klant Tenant op domeinnaam op te zoeken.</span><span class="sxs-lookup"><span data-stu-id="5e306-123">To get the **TenantId** for a specific customer tenant by domain name, run this command.</span></span> <span data-ttu-id="5e306-124">Vervang _<domainname.onmicrosoft.com->_ door de werkelijke domeinnaam van de Tenant van de klant die u wilt.</span><span class="sxs-lookup"><span data-stu-id="5e306-124">Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="5e306-125">Alle domeinen voor een Tenant weergeven</span><span class="sxs-lookup"><span data-stu-id="5e306-125">List all domains for a tenant</span></span>

<span data-ttu-id="5e306-126">Voer deze opdracht uit om alle domeinen voor één klant Tenant op te zoeken.</span><span class="sxs-lookup"><span data-stu-id="5e306-126">To get all domains for any one customer tenant, run this command.</span></span> <span data-ttu-id="5e306-127">Vervangen  _<customer TenantId value>_ door de huidige waarde.</span><span class="sxs-lookup"><span data-stu-id="5e306-127">Replace  _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="5e306-128">Als u extra domeinen hebt geregistreerd, worden alle domeinen weergegeven die zijn gekoppeld aan de klant **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="5e306-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="5e306-129">Een toewijzing van alle tenants en geregistreerde domeinen weergeven</span><span class="sxs-lookup"><span data-stu-id="5e306-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="5e306-130">De eerdere PowerShell voor Microsoft 365-opdrachten laten we u zien hoe u Tenant-Id's of domeinen kunt ophalen, maar niet beide tegelijkertijd, en zonder duidelijke toewijzingen.</span><span class="sxs-lookup"><span data-stu-id="5e306-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="5e306-131">Met deze opdracht wordt een lijst met al uw Tenant-Id's en de domeinen van de klant gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="5e306-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="5e306-132">Alle gebruikers voor een Tenant aanvragen</span><span class="sxs-lookup"><span data-stu-id="5e306-132">Get all users for a tenant</span></span>

<span data-ttu-id="5e306-133">Hierdoor worden de **userPrincipalName**, de **DisplayName**en de status van de **isLicensed** weergegeven voor alle gebruikers van een bepaalde Tenant.</span><span class="sxs-lookup"><span data-stu-id="5e306-133">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant.</span></span> <span data-ttu-id="5e306-134">Vervangen _<customer TenantId value>_ door de huidige waarde.</span><span class="sxs-lookup"><span data-stu-id="5e306-134">Replace _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="5e306-135">Alle details van een gebruiker weergeven</span><span class="sxs-lookup"><span data-stu-id="5e306-135">Get all details about a user</span></span>

<span data-ttu-id="5e306-136">Als u alle eigenschappen van een bepaalde gebruiker wilt zien, voert u deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="5e306-136">If you want to see all the properties of a particular user, run this command.</span></span> <span data-ttu-id="5e306-137">Vervangen  _<customer TenantId value>_ door _<user principal name value>_ de werkelijke waarden.</span><span class="sxs-lookup"><span data-stu-id="5e306-137">Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="5e306-138">Gebruikers toevoegen, opties instellen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="5e306-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="5e306-139">De bulk creatie, configuratie en licenties van Microsoft 365-gebruikers is met name efficiënt met behulp van PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e306-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="5e306-140">In deze twee stappen maakt u eerst vermeldingen voor alle gebruikers die u wilt toevoegen in een CSV-bestand (door komma's gescheiden waarden) en importeert u vervolgens dat bestand met behulp van PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e306-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span> 
  
#### <a name="create-a-csv-file"></a><span data-ttu-id="5e306-141">Een CSV-bestand maken</span><span class="sxs-lookup"><span data-stu-id="5e306-141">Create a CSV file</span></span>

<span data-ttu-id="5e306-142">Maak een CSV-bestand met de volgende indeling:</span><span class="sxs-lookup"><span data-stu-id="5e306-142">Create a CSV file by using this format:</span></span>
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
<span data-ttu-id="5e306-143">waarbij:</span><span class="sxs-lookup"><span data-stu-id="5e306-143">where:</span></span>
  
- <span data-ttu-id="5e306-144">**UsageLocation**: de waarde voor dit is de ISO-land/regiocode van twee tekens van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5e306-144">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user.</span></span> <span data-ttu-id="5e306-145">De landen/regio's kunnen worden opgezocht op het[ISO online-browser platform](https://go.microsoft.com/fwlink/p/?LinkId=532703).</span><span class="sxs-lookup"><span data-stu-id="5e306-145">The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703).</span></span> <span data-ttu-id="5e306-146">De code voor de Verenigde Staten is bijvoorbeeld US en de code voor Brazilië is BR.</span><span class="sxs-lookup"><span data-stu-id="5e306-146">For example, the code for the United States is US, and the code for Brazil is BR.</span></span> 
    
- <span data-ttu-id="5e306-147">**LicenseAssignment**: de waarde voor dit gebruik wordt in de `syndication-account:<PROVISIONING_ID>` volgende indeling gebruikt:</span><span class="sxs-lookup"><span data-stu-id="5e306-147">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`.</span></span> <span data-ttu-id="5e306-148">Als u bijvoorbeeld Tenant gebruikers voor de klant toewijst O365_Business_Premium licenties, ziet de waarde van **LicenseAssignment** er als volgt uit: **publicatie van extern account: O365_Business_Premium**.</span><span class="sxs-lookup"><span data-stu-id="5e306-148">For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**.</span></span> <span data-ttu-id="5e306-149">U ziet het PROVISIONING_IDs in de portal van de syndicatie-partner waartoe u toegang hebt als een syndicatie-of CSP-partner.</span><span class="sxs-lookup"><span data-stu-id="5e306-149">You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>
    
#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="5e306-150">Het CSV-bestand importeren en de gebruikers maken</span><span class="sxs-lookup"><span data-stu-id="5e306-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="5e306-151">Nadat u uw CSV-bestand hebt gemaakt, voert u deze opdracht uit om gebruikersaccounts te maken met niet-vertraagde wachtwoorden die de gebruiker moet wijzigen bij de eerste aanmelding en de door u opgegeven licentie wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="5e306-151">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify.</span></span> <span data-ttu-id="5e306-152">Zorg ervoor dat u de juiste naam van het CSV-bestand vervangt.</span><span class="sxs-lookup"><span data-stu-id="5e306-152">Be sure to substitute the correct CSV file name.</span></span>
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="5e306-153">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5e306-153">See also</span></span>

#### 

[<span data-ttu-id="5e306-154">Help voor partners</span><span class="sxs-lookup"><span data-stu-id="5e306-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)

