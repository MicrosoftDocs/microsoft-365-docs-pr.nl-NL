---
title: Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Meer informatie over het instellen van bepaalde afzonderlijke gebruikerswachtwoorden die nooit verlopen met Windows PowerShell.
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806353"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="254a3-103">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="254a3-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="254a3-104">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="254a3-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="254a3-105">Ga in het beheercentrum naar de privacypagina **Instellingenbeveiliging** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">&.</a></span><span class="sxs-lookup"><span data-stu-id="254a3-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="254a3-106">Selecteer naast **het wachtwoordbeleid** **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="254a3-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="254a3-107">Als wachtwoorden nooit verlopen, stelt u de schakelaar in op **Uitschakelen.**</span><span class="sxs-lookup"><span data-stu-id="254a3-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="254a3-108">U krijgt de optie om het aantal dagen op te geven totdat wachtwoorden verlopen.</span><span class="sxs-lookup"><span data-stu-id="254a3-108">You'll get the option to specify the number of days until passwords expire.</span></span> 


## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="254a3-109">Het wachtwoordverloopbeleid instellen voor individuele gebruikers</span><span class="sxs-lookup"><span data-stu-id="254a3-109">Set the password expiration policy for individual users</span></span> 

<span data-ttu-id="254a3-110">Een globale beheerder voor een Microsoft-cloudservice kan de Microsoft Azure AD-module voor Windows PowerShell gebruiken om in te stellen dat wachtwoorden niet verlopen voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="254a3-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="254a3-111">U ook Windows PowerShell-cmdlets gebruiken om de nooit verlopen configuratie te verwijderen of om te zien welke gebruikerswachtwoorden nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="254a3-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span> 

<span data-ttu-id="254a3-112">Deze handleiding is van toepassing op andere providers, zoals Intune en Office 365, die ook afhankelijk zijn van Azure AD voor identiteits- en directoryservices.</span><span class="sxs-lookup"><span data-stu-id="254a3-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="254a3-113">Het verlopen van wachtwoorden is het enige onderdeel van het beleid dat kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="254a3-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="254a3-114">Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen worden geconfigureerd om niet te verlopen.</span><span class="sxs-lookup"><span data-stu-id="254a3-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="254a3-115">Zie AD verbinden met Azure [AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="254a3-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>


### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="254a3-116">Het verloopbeleid controleren op een wachtwoord</span><span class="sxs-lookup"><span data-stu-id="254a3-116">How to check the expiration policy for a password</span></span>

* <span data-ttu-id="254a3-117">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="254a3-117">Run one of the following commands:</span></span>

   * <span data-ttu-id="254a3-118">Als u wilt zien of het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com)* of de gebruikers-id van de gebruiker die u wilt controleren:</span><span class="sxs-lookup"><span data-stu-id="254a3-118">To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
<span data-ttu-id="254a3-119">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="254a3-119">Example:</span></span>
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * <span data-ttu-id="254a3-120">Voer de volgende cmdlet uit om de instelling Wachtwoord nooit voor alle gebruikers **te bekijken:**</span><span class="sxs-lookup"><span data-stu-id="254a3-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span> 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* <span data-ttu-id="254a3-121">Een rapport van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="254a3-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* <span data-ttu-id="254a3-122">Een rapport van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="254a3-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a><span data-ttu-id="254a3-123">Een wachtwoord instellen om te verlopen</span><span class="sxs-lookup"><span data-stu-id="254a3-123">Set a password to expire</span></span>

<span data-ttu-id="254a3-124">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="254a3-124">Run one of the following commands:</span></span>

   * <span data-ttu-id="254a3-125">Als u het wachtwoord van één gebruiker wilt instellen zodat het wachtwoord verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="254a3-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * <span data-ttu-id="254a3-126">Als u de wachtwoorden van alle gebruikers in de organisatie zo wilt instellen dat ze verlopen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="254a3-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="254a3-127">Een wachtwoord instellen dat nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="254a3-127">Set a password to never expire</span></span>

<span data-ttu-id="254a3-128">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="254a3-128">Run one of the following commands:</span></span>

   * <span data-ttu-id="254a3-129">Als u wilt instellen dat het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="254a3-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span> 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * <span data-ttu-id="254a3-130">Voer de volgende cmdlet uit om de wachtwoorden van alle gebruikers in een organisatie nooit te laten verlopen:</span><span class="sxs-lookup"><span data-stu-id="254a3-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span> 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > <span data-ttu-id="254a3-131">Wachtwoorden ingesteld `-PasswordPolicies DisablePasswordExpiration` op leeftijd `pwdLastSet` op basis van het kenmerk.</span><span class="sxs-lookup"><span data-stu-id="254a3-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="254a3-132">Als u de gebruikerswachtwoorden nooit laat verlopen en vervolgens meer dan 90 dagen voorbij gaat, verlopen de wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="254a3-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="254a3-133">Op basis `pwdLastSet` van het kenmerk moeten `-PasswordPolicies None`alle wachtwoorden die `pwdLastSet` ouder zijn dan 90 dagen, als u de vervaldatum wijzigt, deze de volgende keer dat hij zich aanmeldt, wijzigen.</span><span class="sxs-lookup"><span data-stu-id="254a3-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="254a3-134">Deze wijziging kan gevolgen hebben voor een groot aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="254a3-134">This change can affect a large number of users.</span></span> 
