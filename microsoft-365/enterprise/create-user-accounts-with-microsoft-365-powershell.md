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
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="c1f81-103">Microsoft 365-gebruikersaccounts maken met PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1f81-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="c1f81-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c1f81-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c1f81-105">U kunt PowerShell voor Microsoft 365 gebruiken om efficiënt gebruikersaccounts te maken, waaronder meerdere accounts.</span><span class="sxs-lookup"><span data-stu-id="c1f81-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="c1f81-106">Wanneer u gebruikersaccounts maakt in PowerShell, zijn bepaalde accounteigenschappen altijd vereist.</span><span class="sxs-lookup"><span data-stu-id="c1f81-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="c1f81-107">Andere eigenschappen zijn niet vereist, maar zijn belangrijk.</span><span class="sxs-lookup"><span data-stu-id="c1f81-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="c1f81-108">Zie de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="c1f81-108">See the following table.</span></span>
  
|<span data-ttu-id="c1f81-109">**Eigenschapsnaam**</span><span class="sxs-lookup"><span data-stu-id="c1f81-109">**Property name**</span></span>|<span data-ttu-id="c1f81-110">**Vereist?**</span><span class="sxs-lookup"><span data-stu-id="c1f81-110">**Required?**</span></span>|<span data-ttu-id="c1f81-111">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="c1f81-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1f81-112">**Weergavenaam**</span><span class="sxs-lookup"><span data-stu-id="c1f81-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="c1f81-113">Ja</span><span class="sxs-lookup"><span data-stu-id="c1f81-113">Yes</span></span>  <br/> |<span data-ttu-id="c1f81-114">Dit is de weergavenaam die wordt gebruikt in Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="c1f81-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="c1f81-115">Bijvoorbeeld: *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="c1f81-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="c1f81-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="c1f81-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="c1f81-117">Ja</span><span class="sxs-lookup"><span data-stu-id="c1f81-117">Yes</span></span>  <br/> |<span data-ttu-id="c1f81-118">Dit is de accountnaam die wordt gebruikt om u aan te melden bij Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="c1f81-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="c1f81-119">Bijvoorbeeld: *CalebS \@ contoso.onmicrosoft.com.*</span><span class="sxs-lookup"><span data-stu-id="c1f81-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="c1f81-120">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="c1f81-120">**FirstName**</span></span> <br/> |<span data-ttu-id="c1f81-121">Nee</span><span class="sxs-lookup"><span data-stu-id="c1f81-121">No</span></span>  <br/> ||
|<span data-ttu-id="c1f81-122">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="c1f81-122">**LastName**</span></span> <br/> |<span data-ttu-id="c1f81-123">Nee</span><span class="sxs-lookup"><span data-stu-id="c1f81-123">No</span></span>  <br/> ||
|<span data-ttu-id="c1f81-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="c1f81-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="c1f81-125">Nee</span><span class="sxs-lookup"><span data-stu-id="c1f81-125">No</span></span>  <br/> |<span data-ttu-id="c1f81-126">Dit is het licentieplan (ook wel bekend als het licentieplan of SKU) waaruit een beschikbare licentie is toegewezen aan het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="c1f81-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="c1f81-127">De licentie definieert de Microsoft 365-services die beschikbaar zijn voor het account.</span><span class="sxs-lookup"><span data-stu-id="c1f81-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="c1f81-128">U hoeft geen licentie toe te wijzen aan een gebruiker wanneer u het account maakt, maar het account moet een licentie hebben voor toegang tot Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="c1f81-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="c1f81-129">U hebt 30 dagen de tijd om een licentie voor het gebruikersaccount toe te staan nadat u het hebt aangemaakt.</span><span class="sxs-lookup"><span data-stu-id="c1f81-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="c1f81-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="c1f81-130">**Password**</span></span> <br/> |<span data-ttu-id="c1f81-131">Nee</span><span class="sxs-lookup"><span data-stu-id="c1f81-131">No</span></span>  <br/> | <span data-ttu-id="c1f81-132">Als u geen wachtwoord opgeeft, wordt een willekeurig wachtwoord toegewezen aan het gebruikersaccount en is het wachtwoord zichtbaar in de resultaten van de opdracht.</span><span class="sxs-lookup"><span data-stu-id="c1f81-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="c1f81-133">Als u een wachtwoord opgeeft, moet dit 8 tot 16 ASCII-teksttekens van de volgende typen zijn: kleine letters, hoofdletters, cijfers en symbolen.</span><span class="sxs-lookup"><span data-stu-id="c1f81-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="c1f81-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="c1f81-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="c1f81-135">Nee</span><span class="sxs-lookup"><span data-stu-id="c1f81-135">No</span></span>  <br/> |<span data-ttu-id="c1f81-136">Dit is een geldige ISO 3166-1 alfa-2-landcode.</span><span class="sxs-lookup"><span data-stu-id="c1f81-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="c1f81-137">Bijvoorbeeld VS *voor* de Verenigde Staten en *FR* voor Frankrijk.</span><span class="sxs-lookup"><span data-stu-id="c1f81-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="c1f81-138">Het is belangrijk om deze waarde te leveren, omdat sommige Microsoft 365-services niet beschikbaar zijn in bepaalde landen.</span><span class="sxs-lookup"><span data-stu-id="c1f81-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="c1f81-139">U kunt geen licentie toewijzen aan een gebruikersaccount, tenzij deze waarde is geconfigureerd voor het account.</span><span class="sxs-lookup"><span data-stu-id="c1f81-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="c1f81-140">Zie Over licentiebeperkingen [voor meer informatie.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="c1f81-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="c1f81-141">[Meer informatie over het maken van gebruikersaccounts](../admin/add-users/add-users.md) met behulp van het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="c1f81-141">[Learn how to create user accounts](../admin/add-users/add-users.md) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="c1f81-142">Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="c1f81-142">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c1f81-143">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="c1f81-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c1f81-144">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c1f81-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="c1f81-145">Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijk account te maken:</span><span class="sxs-lookup"><span data-stu-id="c1f81-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="c1f81-146">In dit voorbeeld wordt een account gemaakt voor de Amerikaanse gebruiker *Caleb Sills:*</span><span class="sxs-lookup"><span data-stu-id="c1f81-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c1f81-147">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="c1f81-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c1f81-148">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c1f81-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="c1f81-149">Een individueel gebruikersaccount maken</span><span class="sxs-lookup"><span data-stu-id="c1f81-149">Create an individual user account</span></span>

<span data-ttu-id="c1f81-150">Als u een afzonderlijk account wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="c1f81-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="c1f81-151">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory Module voor Windows PowerShell-module en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="c1f81-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="c1f81-152">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f81-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="c1f81-153">Gebruik deze opdracht om de beschikbare namen van licentieplannen op te geven:</span><span class="sxs-lookup"><span data-stu-id="c1f81-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="c1f81-154">In dit voorbeeld wordt een account gemaakt voor de Amerikaanse gebruiker *Caleb Sills* en wordt een licentie toegewezen vanuit het `contoso:ENTERPRISEPACK` licentieplan (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="c1f81-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="c1f81-155">Meerdere gebruikersaccounts maken</span><span class="sxs-lookup"><span data-stu-id="c1f81-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="c1f81-156">Maak een CSV-bestand (door komma's gescheiden waarde) dat de vereiste gebruikersaccountgegevens bevat.</span><span class="sxs-lookup"><span data-stu-id="c1f81-156">Create a comma-separated value (CSV) file that contains the required user account information.</span></span> <span data-ttu-id="c1f81-157">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c1f81-157">For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="c1f81-158">De kolomnamen en de volgorde in de eerste rij van het CSV-bestand zijn willekeurig.</span><span class="sxs-lookup"><span data-stu-id="c1f81-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="c1f81-159">Maar zorg ervoor dat de volgorde van de gegevens in de rest van het bestand overeenkomt met de volgorde van de kolomnamen.</span><span class="sxs-lookup"><span data-stu-id="c1f81-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="c1f81-160">En gebruik de kolomnamen voor de parameterwaarden in de opdracht PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1f81-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="c1f81-161">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="c1f81-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="c1f81-162">In dit voorbeeld worden gebruikersaccounts gemaakt van het bestand *C:\Mijn Documents\NewAccounts.csv* en worden de resultaten in een bestand met de naam *C:\Mijn Documents\NewAccountResults.csv.*</span><span class="sxs-lookup"><span data-stu-id="c1f81-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="c1f81-163">Controleer het uitvoerbestand om de resultaten te zien.</span><span class="sxs-lookup"><span data-stu-id="c1f81-163">Review the output file to see the results.</span></span> <span data-ttu-id="c1f81-164">We hebben geen wachtwoorden opgegeven, dus de willekeurige wachtwoorden die microsoft 365 heeft gegenereerd, zijn zichtbaar in het uitvoerbestand.</span><span class="sxs-lookup"><span data-stu-id="c1f81-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c1f81-165">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c1f81-165">See also</span></span>

[<span data-ttu-id="c1f81-166">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1f81-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c1f81-167">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1f81-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c1f81-168">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1f81-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)