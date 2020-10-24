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
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="b6018-103">Microsoft 365-gebruikersaccounts maken met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6018-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="b6018-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b6018-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b6018-105">Met PowerShell voor Microsoft 365 kunt u efficiënt gebruikersaccounts maken, waaronder meerdere accounts.</span><span class="sxs-lookup"><span data-stu-id="b6018-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="b6018-106">Wanneer u gebruikersaccounts in PowerShell maakt, zijn bepaalde accounteigenschappen altijd vereist.</span><span class="sxs-lookup"><span data-stu-id="b6018-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="b6018-107">Andere eigenschappen zijn niet vereist maar zijn belangrijk.</span><span class="sxs-lookup"><span data-stu-id="b6018-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="b6018-108">Zie de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="b6018-108">See the following table.</span></span>
  
|<span data-ttu-id="b6018-109">**Naam van eigenschap**</span><span class="sxs-lookup"><span data-stu-id="b6018-109">**Property name**</span></span>|<span data-ttu-id="b6018-110">**Vereist?**</span><span class="sxs-lookup"><span data-stu-id="b6018-110">**Required?**</span></span>|<span data-ttu-id="b6018-111">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="b6018-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6018-112">**Weergave**</span><span class="sxs-lookup"><span data-stu-id="b6018-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="b6018-113">Ja</span><span class="sxs-lookup"><span data-stu-id="b6018-113">Yes</span></span>  <br/> |<span data-ttu-id="b6018-114">Dit is de weergavenaam die wordt gebruikt in Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="b6018-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="b6018-115">Bijvoorbeeld *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="b6018-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="b6018-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="b6018-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="b6018-117">Ja</span><span class="sxs-lookup"><span data-stu-id="b6018-117">Yes</span></span>  <br/> |<span data-ttu-id="b6018-118">Dit is de accountnaam die wordt gebruikt om u aan te melden bij Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="b6018-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="b6018-119">Bijvoorbeeld *CalebS \@ contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="b6018-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="b6018-120">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="b6018-120">**FirstName**</span></span> <br/> |<span data-ttu-id="b6018-121">Nee</span><span class="sxs-lookup"><span data-stu-id="b6018-121">No</span></span>  <br/> ||
|<span data-ttu-id="b6018-122">**Naam**</span><span class="sxs-lookup"><span data-stu-id="b6018-122">**LastName**</span></span> <br/> |<span data-ttu-id="b6018-123">Nee</span><span class="sxs-lookup"><span data-stu-id="b6018-123">No</span></span>  <br/> ||
|<span data-ttu-id="b6018-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="b6018-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="b6018-125">Nee</span><span class="sxs-lookup"><span data-stu-id="b6018-125">No</span></span>  <br/> |<span data-ttu-id="b6018-126">Dit is het licentie plan (ook wel bekend als het licentie plan of SKU) van waaruit een beschikbare licentie aan het gebruikersaccount is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b6018-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="b6018-127">De licentie definieert de Microsoft 365-services die beschikbaar zijn voor het account.</span><span class="sxs-lookup"><span data-stu-id="b6018-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="b6018-128">Wanneer u het account maakt, hoeft u geen licentie toe te wijzen aan een gebruiker, maar het account moet een licentie hebben voor toegang tot services van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6018-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="b6018-129">U hebt een licentie voor het gebruikersaccount van 30 dagen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b6018-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="b6018-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="b6018-130">**Password**</span></span> <br/> |<span data-ttu-id="b6018-131">Nee</span><span class="sxs-lookup"><span data-stu-id="b6018-131">No</span></span>  <br/> | <span data-ttu-id="b6018-132">Als u geen wachtwoord opgeeft, wordt een willekeurig wachtwoord toegewezen aan het gebruikersaccount en wordt het wachtwoord weergegeven in de resultaten van de opdracht.</span><span class="sxs-lookup"><span data-stu-id="b6018-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="b6018-133">Als u een wachtwoord opgeeft, moet u een wachtwoord van 8 tot 16 ASCII-teksttekens van de volgende typen opgeven: kleine letters, hoofdletters, cijfers en symbolen.</span><span class="sxs-lookup"><span data-stu-id="b6018-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="b6018-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="b6018-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="b6018-135">Nee</span><span class="sxs-lookup"><span data-stu-id="b6018-135">No</span></span>  <br/> |<span data-ttu-id="b6018-136">Dit is een geldige ISO 3166-1 alpha-2 landcode.</span><span class="sxs-lookup"><span data-stu-id="b6018-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="b6018-137">Bijvoorbeeld *US* voor de Verenigde Staten en *fr* voor Frankrijk.</span><span class="sxs-lookup"><span data-stu-id="b6018-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="b6018-138">Het is belangrijk dat u deze waarde oplevert omdat sommige Microsoft 365-Services niet beschikbaar zijn in bepaalde landen.</span><span class="sxs-lookup"><span data-stu-id="b6018-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="b6018-139">U kunt geen licentie toewijzen aan een gebruikersaccount, tenzij deze waarde is geconfigureerd voor het account.</span><span class="sxs-lookup"><span data-stu-id="b6018-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="b6018-140">Zie voor meer informatie [over licentiebeperkingen](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="b6018-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="b6018-141">[Meer informatie over het maken van gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) met het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b6018-141">[Learn how to create user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="b6018-142">Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="b6018-142">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b6018-143">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="b6018-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b6018-144">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b6018-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="b6018-145">Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijk account te maken:</span><span class="sxs-lookup"><span data-stu-id="b6018-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="b6018-146">In dit voorbeeld wordt een account gemaakt voor de US User *Caleb Sills*:</span><span class="sxs-lookup"><span data-stu-id="b6018-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b6018-147">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="b6018-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b6018-148">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b6018-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="b6018-149">Een afzonderlijke gebruikersaccount maken</span><span class="sxs-lookup"><span data-stu-id="b6018-149">Create an individual user account</span></span>

<span data-ttu-id="b6018-150">Als u een afzonderlijke account wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b6018-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="b6018-151">PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam.</span><span class="sxs-lookup"><span data-stu-id="b6018-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="b6018-152">Voer de volgende cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6018-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="b6018-153">Met de volgende opdracht kunt u de namen van de beschikbare licentie plannen weergeven:</span><span class="sxs-lookup"><span data-stu-id="b6018-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="b6018-154">In dit voorbeeld wordt een account gemaakt voor de US User *Caleb Sills*en wordt een licentie toegewezen aan het `contoso:ENTERPRISEPACK` licentie plan (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="b6018-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="b6018-155">Meerdere gebruikersaccounts maken</span><span class="sxs-lookup"><span data-stu-id="b6018-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="b6018-156">Maak een CSV-bestand (door komma's gescheiden waarden) met de vereiste gegevens voor het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="b6018-156">Create a comma-separated value (CSV) file that contains the required user account information.</span></span> <span data-ttu-id="b6018-157">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b6018-157">For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="b6018-158">De kolomnamen en hun volgorde in de eerste rij van het CSV-bestand zijn willekeurig.</span><span class="sxs-lookup"><span data-stu-id="b6018-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="b6018-159">Zorg ervoor dat de volgorde van de gegevens in de rest van het bestand overeenkomen met de volgorde van de kolomnamen.</span><span class="sxs-lookup"><span data-stu-id="b6018-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="b6018-160">En gebruik de kolomnamen voor de parameterwaarden in de opdracht PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6018-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="b6018-161">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b6018-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="b6018-162">In dit voorbeeld worden gebruikersaccounts gemaakt van het bestand *c:\mijn Documents\NewAccounts.csv* en worden de resultaten Logboeken in een bestand met de naam *C:\My Documents\NewAccountResults.csv*.</span><span class="sxs-lookup"><span data-stu-id="b6018-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="b6018-163">Controleer het uitvoerbestand om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b6018-163">Review the output file to see the results.</span></span> <span data-ttu-id="b6018-164">We hebben geen wachtwoorden opgegeven, dus de willekeurige wachtwoorden die door Microsoft 365 worden gegenereerd, worden weergegeven in het uitvoerbestand.</span><span class="sxs-lookup"><span data-stu-id="b6018-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b6018-165">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6018-165">See also</span></span>

[<span data-ttu-id="b6018-166">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6018-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b6018-167">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6018-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b6018-168">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b6018-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
