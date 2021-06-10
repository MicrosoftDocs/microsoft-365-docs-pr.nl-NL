---
title: Klantcode beheren
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Nadat u Klantsleutel hebt ingesteld, leert u hoe u deze beheert door AKV-sleutels te herstellen, machtigingen te beheren en gegevensversleutelingsbeleid te maken en toe te wijzen.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345056"
---
# <a name="manage-customer-key"></a><span data-ttu-id="fecda-103">Klantcode beheren</span><span class="sxs-lookup"><span data-stu-id="fecda-103">Manage Customer Key</span></span>

<span data-ttu-id="fecda-104">Nadat u Klantcode voor Office 365 hebt ingesteld, moet u een of meer beleidsregels voor gegevensversleuteling (DEP) maken en toewijzen.</span><span class="sxs-lookup"><span data-stu-id="fecda-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="fecda-105">Nadat u de DEP's hebt toegewezen, kunt u uw sleutels beheren, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="fecda-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="fecda-106">Meer informatie over Klantcode in de gerelateerde onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="fecda-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="fecda-107">Een DEP maken voor gebruik met meerdere werkbelastingen voor alle tenantgebruikers</span><span class="sxs-lookup"><span data-stu-id="fecda-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="fecda-108">Controleer voordat u begint of u de taken hebt voltooid die nodig zijn om Klant in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fecda-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="fecda-109">Zie Klantsleutel instellen voor [meer informatie.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="fecda-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="fecda-110">Als u de DEP wilt maken, hebt u de KEY VAULT-URL's nodig die u hebt verkregen tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="fecda-111">Zie De [URI voor elke Azure Key Vault-sleutel verkrijgen](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="fecda-112">Als u een DEP met meerdere werkbelastingen wilt maken, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="fecda-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="fecda-113">Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.</span><span class="sxs-lookup"><span data-stu-id="fecda-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="fecda-114">Als u een DEP wilt maken, gebruikt u New-M365DataAtRestEncryptionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="fecda-115">Waarbij:</span><span class="sxs-lookup"><span data-stu-id="fecda-115">Where:</span></span>

   - <span data-ttu-id="fecda-116">*PolicyName* is de naam die u wilt gebruiken voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="fecda-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="fecda-117">Namen kunnen geen spaties bevatten.</span><span class="sxs-lookup"><span data-stu-id="fecda-117">Names can't contain spaces.</span></span> <span data-ttu-id="fecda-118">U kunt bijvoorbeeld Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="fecda-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="fecda-119">*KeyVaultURI1* is de URI voor de eerste sleutel in het beleid.</span><span class="sxs-lookup"><span data-stu-id="fecda-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="fecda-120">Bijvoorbeeld <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="fecda-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="fecda-121">*KeyVaultURI2* is de URI voor de tweede sleutel in het beleid.</span><span class="sxs-lookup"><span data-stu-id="fecda-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="fecda-122">Bijvoorbeeld <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="fecda-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="fecda-123">Scheid de twee URL's door een komma en een spatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="fecda-124">*Beleidsbeschrijving* is een gebruiksvriendelijke beschrijving van het beleid om u te helpen onthouden waar het beleid voor is.</span><span class="sxs-lookup"><span data-stu-id="fecda-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="fecda-125">U kunt spaties opnemen in de beschrijving.</span><span class="sxs-lookup"><span data-stu-id="fecda-125">You can include spaces in the description.</span></span> <span data-ttu-id="fecda-126">Bijvoorbeeld: 'Hoofdbeleid voor meerdere werkbelastingen voor alle gebruikers in de tenant'.</span><span class="sxs-lookup"><span data-stu-id="fecda-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="fecda-127">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="fecda-128">Beleid voor meerdere werkbelastingen toewijzen</span><span class="sxs-lookup"><span data-stu-id="fecda-128">Assign multi-workload policy</span></span>

<span data-ttu-id="fecda-129">Wijs de DEP toe met de Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="fecda-130">Nadat u het beleid hebt toegewezen, Microsoft 365 de gegevens versleuteld met de sleutel die is geïdentificeerd in het DEP.</span><span class="sxs-lookup"><span data-stu-id="fecda-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="fecda-131">Waarbij *PolicyName* de naam van het beleid is.</span><span class="sxs-lookup"><span data-stu-id="fecda-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="fecda-132">U kunt bijvoorbeeld Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="fecda-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="fecda-133">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="fecda-134">Een DEP maken voor gebruik met Exchange Online postvakken</span><span class="sxs-lookup"><span data-stu-id="fecda-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="fecda-135">Controleer voordat u begint of u de taken hebt voltooid die nodig zijn om Azure Key Vault in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fecda-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="fecda-136">Zie Klantsleutel instellen voor [meer informatie.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="fecda-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="fecda-137">U voltooit deze stappen door op afstand verbinding te maken met Exchange Online met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fecda-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="fecda-138">Een DEP is gekoppeld aan een set sleutels die zijn opgeslagen in Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="fecda-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="fecda-139">U wijst een DEP toe aan een postvak in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fecda-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="fecda-140">Microsoft 365 gebruikt vervolgens de sleutels die zijn geïdentificeerd in het beleid om het postvak te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="fecda-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="fecda-141">Als u de DEP wilt maken, hebt u de KEY VAULT-URL's nodig die u hebt verkregen tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="fecda-142">Zie De [URI voor elke Azure Key Vault-sleutel verkrijgen](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="fecda-143">Vergeet niet!</span><span class="sxs-lookup"><span data-stu-id="fecda-143">Remember!</span></span> <span data-ttu-id="fecda-144">Wanneer u een DEP maakt, geeft u twee sleutels op in twee verschillende Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="fecda-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="fecda-145">Maak deze sleutels in twee afzonderlijke Azure-regio's om te zorgen voor geo-redundantie.</span><span class="sxs-lookup"><span data-stu-id="fecda-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="fecda-146">Als u een DEP wilt maken voor gebruik met een postvak, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="fecda-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="fecda-147">Op uw lokale computer maakt u via een werk- of schoolaccount met globale beheerders- Exchange Online beheerdersmachtigingen in uw organisatie verbinding met Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in een Windows PowerShell venster.</span><span class="sxs-lookup"><span data-stu-id="fecda-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="fecda-148">Als u een DEP wilt maken, gebruikt u New-DataEncryptionPolicy cmdlet door de volgende opdracht te typen.</span><span class="sxs-lookup"><span data-stu-id="fecda-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="fecda-149">Waarbij:</span><span class="sxs-lookup"><span data-stu-id="fecda-149">Where:</span></span>

   - <span data-ttu-id="fecda-150">*PolicyName* is de naam die u wilt gebruiken voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="fecda-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="fecda-151">Namen kunnen geen spaties bevatten.</span><span class="sxs-lookup"><span data-stu-id="fecda-151">Names can't contain spaces.</span></span> <span data-ttu-id="fecda-152">U kunt bijvoorbeeld USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="fecda-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="fecda-153">*Beleidsbeschrijving* is een gebruiksvriendelijke beschrijving van het beleid om u te helpen onthouden waar het beleid voor is.</span><span class="sxs-lookup"><span data-stu-id="fecda-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="fecda-154">U kunt spaties opnemen in de beschrijving.</span><span class="sxs-lookup"><span data-stu-id="fecda-154">You can include spaces in the description.</span></span> <span data-ttu-id="fecda-155">Bijvoorbeeld :'Hoofdsleutel voor postvakken in de VS en de regio's'.</span><span class="sxs-lookup"><span data-stu-id="fecda-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="fecda-156">*KeyVaultURI1* is de URI voor de eerste sleutel in het beleid.</span><span class="sxs-lookup"><span data-stu-id="fecda-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="fecda-157">Bijvoorbeeld <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="fecda-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="fecda-158">*KeyVaultURI2* is de URI voor de tweede sleutel in het beleid.</span><span class="sxs-lookup"><span data-stu-id="fecda-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="fecda-159">Bijvoorbeeld <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="fecda-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="fecda-160">Scheid de twee URL's door een komma en een spatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="fecda-161">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="fecda-162">Zie [New-DataEncryptionPolicy voor](/powershell/module/exchange/new-data-encryptionpolicy)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="fecda-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="fecda-163">Een DEP toewijzen aan een postvak</span><span class="sxs-lookup"><span data-stu-id="fecda-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="fecda-164">Wijs de DEP toe aan een postvak met de Set-Mailbox cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="fecda-165">Nadat u het beleid hebt toegewezen, Microsoft 365 het postvak versleutelen met de sleutel die is geïdentificeerd in het DEP.</span><span class="sxs-lookup"><span data-stu-id="fecda-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="fecda-166">Waarbij *MailboxIdParameter* een gebruikerspostvak aangeeft.</span><span class="sxs-lookup"><span data-stu-id="fecda-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="fecda-167">Zie [Postvak instellen](/powershell/module/exchange/set-mailbox)voor meer Set-Mailbox cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="fecda-168">In hybride omgevingen kunt u een DEP toewijzen aan de on-premises postvakgegevens die worden gesynchroniseerd met uw Exchange Online tenant.</span><span class="sxs-lookup"><span data-stu-id="fecda-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="fecda-169">Als u een DEP wilt toewijzen aan deze gesynchroniseerde postvakgegevens, gebruikt u de Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="fecda-170">Zie [on-premises](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)postvakken met Outlook voor iOS en Android met hybride moderne verificatie voor meer informatie over postvakgegevens in de hybride omgeving.</span><span class="sxs-lookup"><span data-stu-id="fecda-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="fecda-171">Waar *MailUserIdParameter* een e-mailgebruiker (ook wel een gebruiker met e-mail genoemd) aangeeft.</span><span class="sxs-lookup"><span data-stu-id="fecda-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="fecda-172">Zie [Set-MailUser](/powershell/module/exchange/set-mailuser)voor meer Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="fecda-173">Een DEP maken voor gebruik met SharePoint Online OneDrive voor Bedrijven en Teams bestanden</span><span class="sxs-lookup"><span data-stu-id="fecda-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="fecda-174">Controleer voordat u begint of u de taken hebt voltooid die nodig zijn om Azure Key Vault in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fecda-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="fecda-175">Zie Klantsleutel instellen voor [meer informatie.](customer-key-set-up.md)</span><span class="sxs-lookup"><span data-stu-id="fecda-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="fecda-176">Als u klantcode wilt instellen voor SharePoint Online-, OneDrive voor Bedrijven- en Teams-bestanden, kunt u deze stappen voltooien door op afstand verbinding te maken met SharePoint Online met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fecda-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="fecda-177">U koppelt een DEP aan een set sleutels die zijn opgeslagen in Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="fecda-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="fecda-178">U kunt een DEP toepassen op al uw gegevens op één geografische locatie, ook wel een geo genoemd.</span><span class="sxs-lookup"><span data-stu-id="fecda-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="fecda-179">Als u de functie multi-geo van Office 365 gebruikt, kunt u één DEP per geo maken met de mogelijkheid om verschillende toetsen per geo te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fecda-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="fecda-180">Als u geen multi-geo gebruikt, kunt u één DEP in uw organisatie maken voor gebruik met SharePoint Online, OneDrive voor Bedrijven en Teams bestanden.</span><span class="sxs-lookup"><span data-stu-id="fecda-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="fecda-181">Microsoft 365 gebruikt de sleutels die zijn geïdentificeerd in de DEP om uw gegevens in die geo te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="fecda-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="fecda-182">Als u de DEP wilt maken, hebt u de KEY VAULT-URL's nodig die u hebt verkregen tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="fecda-183">Zie De [URI voor elke Azure Key Vault-sleutel verkrijgen](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="fecda-184">Vergeet niet!</span><span class="sxs-lookup"><span data-stu-id="fecda-184">Remember!</span></span> <span data-ttu-id="fecda-185">Wanneer u een DEP maakt, geeft u twee sleutels op in twee verschillende Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="fecda-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="fecda-186">Maak deze sleutels in twee afzonderlijke Azure-regio's om te zorgen voor geo-redundantie.</span><span class="sxs-lookup"><span data-stu-id="fecda-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="fecda-187">Als u een DEP wilt maken, moet u op afstand verbinding maken met SharePoint Online met behulp van Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fecda-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="fecda-188">Gebruik op uw lokale computer een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en Verbinding maken om SharePoint [Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="fecda-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="fecda-189">Voer in Microsoft Office SharePoint Online Management Shell de Register-SPODataEncryptionPolicy als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="fecda-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="fecda-190">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="fecda-191">Wanneer u het DEP registreert, wordt versleuteling gestart op de gegevens in de geo.</span><span class="sxs-lookup"><span data-stu-id="fecda-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="fecda-192">Versleuteling kan enige tijd duren.</span><span class="sxs-lookup"><span data-stu-id="fecda-192">Encryption can take some time.</span></span> <span data-ttu-id="fecda-193">Zie [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)voor meer informatie over het gebruik van deze parameter.</span><span class="sxs-lookup"><span data-stu-id="fecda-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="fecda-194">De DEP's weergeven die u hebt gemaakt voor Exchange Online postvakken</span><span class="sxs-lookup"><span data-stu-id="fecda-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="fecda-195">Als u een lijst wilt weergeven met alle DEP's die u voor postvakken hebt gemaakt, gebruikt u Get-DataEncryptionPolicy PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="fecda-196">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fecda-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="fecda-197">Als u alle DEP's in uw organisatie wilt retourneren, Get-DataEncryptionPolicy de cmdlet zonder parameters.</span><span class="sxs-lookup"><span data-stu-id="fecda-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="fecda-198">Zie [Get-DataEncryptionPolicy (Get-DataEncryptionPolicy)](/powershell/module/exchange/get-dataencryptionpolicy)voor meer informatie over Get-DataEncryptionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="fecda-199">Een DEP toewijzen voordat u een postvak migreert naar de cloud</span><span class="sxs-lookup"><span data-stu-id="fecda-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="fecda-200">Wanneer u de DEP toewijst, Microsoft 365 de inhoud van het postvak versleutelt met behulp van de toegewezen DEP tijdens de migratie.</span><span class="sxs-lookup"><span data-stu-id="fecda-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="fecda-201">Dit proces is efficiënter dan het migreren van het postvak, het toewijzen van de DEP en het wachten op versleuteling, wat uren of mogelijk dagen kan duren.</span><span class="sxs-lookup"><span data-stu-id="fecda-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="fecda-202">Als u een DEP wilt toewijzen aan een postvak voordat u deze migreert naar Office 365, voer u de Set-MailUser cmdlet uit in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fecda-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="fecda-203">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fecda-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="fecda-204">Voer de Set-MailUser cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="fecda-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="fecda-205">Waar *GeneralMailboxOrMailUserIdParameter* een postvak aangeeft en *DataEncryptionPolicyIdParameter* de id van de DEP is.</span><span class="sxs-lookup"><span data-stu-id="fecda-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="fecda-206">Zie [Set-MailUser](/powershell/module/exchange/set-mailuser)voor meer Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="fecda-207">Bepalen welke DEP is toegewezen aan een postvak</span><span class="sxs-lookup"><span data-stu-id="fecda-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="fecda-208">Als u de DEP wilt bepalen die aan een postvak is toegewezen, gebruikt u Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="fecda-209">De cmdlet retourneert een unieke id (GUID).</span><span class="sxs-lookup"><span data-stu-id="fecda-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="fecda-210">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fecda-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="fecda-211">Waar *GeneralMailboxOrMailUserIdParameter* een postvak aangeeft en DataEncryptionPolicyID de GUID van de DEP retourneert.</span><span class="sxs-lookup"><span data-stu-id="fecda-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="fecda-212">Zie [Get-MailboxStatistics (Get-MailboxStatistics)](/powershell/module/exchange/get-mailboxstatistics)voor meer informatie over Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="fecda-213">Voer de Get-DataEncryptionPolicy cmdlet uit om de vriendelijke naam te weten te komen van de DEP waaraan het postvak is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="fecda-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="fecda-214">Waarbij *GUID* de GUID is die wordt geretourneerd door de Get-MailboxStatistics cmdlet in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="fecda-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="fecda-215">Controleren of de klantsleutel is voltooid met versleuteling</span><span class="sxs-lookup"><span data-stu-id="fecda-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="fecda-216">Gebruik de stappen in deze sectie om ervoor te zorgen dat versleuteling wordt voltooid, ongeacht of u een klantsleutel hebt gerold, een nieuw dep hebt toegewezen of een postvak hebt gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="fecda-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="fecda-217">Versleuteling controleren voor Exchange Online postvakken</span><span class="sxs-lookup"><span data-stu-id="fecda-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="fecda-218">Het versleutelen van een postvak kan enige tijd duren.</span><span class="sxs-lookup"><span data-stu-id="fecda-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="fecda-219">Voor de eerste keer versleuteling moet het postvak ook volledig van de ene database naar de andere worden verplaatst voordat de service het postvak kan versleutelen.</span><span class="sxs-lookup"><span data-stu-id="fecda-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="fecda-220">Gebruik de Get-MailboxStatistics cmdlet om te bepalen of een postvak is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="fecda-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="fecda-221">De eigenschap IsEncrypted retourneert een waarde van waar als  het postvak is versleuteld en een waarde van onwaar als het postvak niet is versleuteld. </span><span class="sxs-lookup"><span data-stu-id="fecda-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="fecda-222">De tijd waarop postvak wordt verplaatst, is afhankelijk van het aantal postvakken waaraan u voor het eerst een DEP toewijst en de grootte van de postvakken.</span><span class="sxs-lookup"><span data-stu-id="fecda-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="fecda-223">Als de postvakken niet zijn versleuteld na een week vanaf het moment dat u de DEP hebt toegewezen, neem dan contact op met Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fecda-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="fecda-224">De New-MoveRequest cmdlet is niet meer beschikbaar voor lokale postvakverhuisbewegingen.</span><span class="sxs-lookup"><span data-stu-id="fecda-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="fecda-225">Raadpleeg deze [aankondiging voor](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fecda-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="fecda-226">Versleuteling controleren voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden</span><span class="sxs-lookup"><span data-stu-id="fecda-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="fecda-227">Controleer de status van versleuteling door de Get-SPODataEncryptionPolicy als volgt uit te laten:</span><span class="sxs-lookup"><span data-stu-id="fecda-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="fecda-228">De uitvoer van deze cmdlet omvat:</span><span class="sxs-lookup"><span data-stu-id="fecda-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="fecda-229">De URI van de primaire sleutel.</span><span class="sxs-lookup"><span data-stu-id="fecda-229">The URI of the primary key.</span></span>

- <span data-ttu-id="fecda-230">De URI van de secundaire sleutel.</span><span class="sxs-lookup"><span data-stu-id="fecda-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="fecda-231">De versleutelingsstatus voor de geo.</span><span class="sxs-lookup"><span data-stu-id="fecda-231">The encryption status for the geo.</span></span> <span data-ttu-id="fecda-232">Mogelijke staten zijn:</span><span class="sxs-lookup"><span data-stu-id="fecda-232">Possible states include:</span></span>

  - <span data-ttu-id="fecda-233">**Niet-geregistreerd:** Klantsleutelversleuteling is nog niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="fecda-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="fecda-234">**Registreren:** Klantsleutelversleuteling is toegepast en uw bestanden worden momenteel versleuteld.</span><span class="sxs-lookup"><span data-stu-id="fecda-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="fecda-235">Als de sleutel voor de geo wordt geregistreerd, wordt ook informatie weergegeven over het percentage sites in de geo dat is voltooid, zodat u de voortgang van versleuteling kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="fecda-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="fecda-236">**Geregistreerd:** Klantsleutelversleuteling is toegepast en alle bestanden op alle sites zijn versleuteld.</span><span class="sxs-lookup"><span data-stu-id="fecda-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="fecda-237">**Rollend:** Er wordt een sleutelrol uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="fecda-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="fecda-238">Als de sleutel voor het geo wordt gerold, wordt ook informatie weergegeven over het percentage sites dat de sleutelrolbewerking heeft voltooid, zodat u de voortgang kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="fecda-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="fecda-239">Meer informatie over DEP's die u met meerdere werkbelastingen gebruikt</span><span class="sxs-lookup"><span data-stu-id="fecda-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="fecda-240">Als u meer informatie wilt over alle DEP's die u hebt gemaakt voor gebruik met meerdere werkbelastingen, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="fecda-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="fecda-241">Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.</span><span class="sxs-lookup"><span data-stu-id="fecda-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="fecda-242">Voer deze opdracht uit als u de lijst met alle DEP's met meerdere werkbelastingen in de organisatie wilt retourneren.</span><span class="sxs-lookup"><span data-stu-id="fecda-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="fecda-243">Voer deze opdracht uit als u details over een specifiek dep wilt retourneren.</span><span class="sxs-lookup"><span data-stu-id="fecda-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="fecda-244">Dit voorbeeld retourneert gedetailleerde informatie voor het DEP met de naam 'Contoso_Global'.</span><span class="sxs-lookup"><span data-stu-id="fecda-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="fecda-245">Informatie over DEP-toewijzing met meerdere werkbelastingen</span><span class="sxs-lookup"><span data-stu-id="fecda-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="fecda-246">Als u wilt weten welke DEP momenteel aan uw tenant is toegewezen, volgt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="fecda-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="fecda-247">Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.</span><span class="sxs-lookup"><span data-stu-id="fecda-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="fecda-248">Typ deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="fecda-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="fecda-249">Een DEP met meerdere werkbelastingen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="fecda-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="fecda-250">Voordat u een DEP met meerdere werkbelastingen uit schakelt, moet u de DEP van werkbelastingen in uw tenant verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fecda-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="fecda-251">Als u een DEP wilt uitschakelen die wordt gebruikt met meerdere werkbelastingen, moet u de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="fecda-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="fecda-252">Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.</span><span class="sxs-lookup"><span data-stu-id="fecda-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="fecda-253">Voer de Set-M365DataAtRestEncryptionPolicy cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="fecda-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="fecda-254">Waarbij *PolicyName* de naam of unieke id van het beleid is.</span><span class="sxs-lookup"><span data-stu-id="fecda-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="fecda-255">U kunt bijvoorbeeld Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="fecda-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="fecda-256">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="fecda-257">Azure Key Vault-sleutels herstellen</span><span class="sxs-lookup"><span data-stu-id="fecda-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="fecda-258">Voordat u herstelt, gebruikt u de herstelmogelijkheden van soft delete.</span><span class="sxs-lookup"><span data-stu-id="fecda-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="fecda-259">Alle sleutels die worden gebruikt met klantsleutel zijn vereist om soft delete in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fecda-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="fecda-260">Soft delete werkt als een prullenbak en maakt herstel tot 90 dagen mogelijk zonder dat u het hoeft te herstellen.</span><span class="sxs-lookup"><span data-stu-id="fecda-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="fecda-261">Herstellen is alleen vereist in extreme of ongebruikelijke omstandigheden, bijvoorbeeld als de sleutel- of sleutelkluis verloren gaat.</span><span class="sxs-lookup"><span data-stu-id="fecda-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="fecda-262">Als u een sleutel moet herstellen voor gebruik met klantsleutel, Azure PowerShell u de cmdlet Restore-AzureKeyVaultKey als volgt:</span><span class="sxs-lookup"><span data-stu-id="fecda-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="fecda-263">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="fecda-264">Als de sleutelkluis al een sleutel met dezelfde naam bevat, mislukt de herstelbewerking.</span><span class="sxs-lookup"><span data-stu-id="fecda-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="fecda-265">Restore-AzKeyVaultKey herstelt alle sleutelversies en alle metagegevens voor de sleutel, inclusief de sleutelnaam.</span><span class="sxs-lookup"><span data-stu-id="fecda-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="fecda-266">Machtigingen voor sleutelkluis beheren</span><span class="sxs-lookup"><span data-stu-id="fecda-266">Manage key vault permissions</span></span>

<span data-ttu-id="fecda-267">Er zijn verschillende cmdlets beschikbaar waarmee u machtigingen voor sleutelkluisen kunt bekijken en zo nodig kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fecda-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="fecda-268">Mogelijk moet u machtigingen verwijderen, bijvoorbeeld wanneer een werknemer het team verlaat.</span><span class="sxs-lookup"><span data-stu-id="fecda-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="fecda-269">Voor elk van deze taken gebruikt u Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fecda-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="fecda-270">Zie Overzicht van Azure PowerShell [Azure PowerShell.](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="fecda-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="fecda-271">Als u machtigingen voor de sleutelkluis wilt weergeven, Get-AzKeyVault cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="fecda-272">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="fecda-273">Als u de machtigingen van een beheerder wilt verwijderen, moet u Remove-AzKeyVaultAccessPolicy cmdlet uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="fecda-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="fecda-274">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fecda-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="fecda-275">Terugdraaien van klantsleutel naar beheerde sleutels van Microsoft</span><span class="sxs-lookup"><span data-stu-id="fecda-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="fecda-276">Als u wilt terugkeren naar door Microsoft beheerde sleutels, kunt u dit doen.</span><span class="sxs-lookup"><span data-stu-id="fecda-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="fecda-277">Wanneer u offboard bent, worden uw gegevens opnieuw versleuteld met behulp van standaardversleuteling die door elke afzonderlijke werkbelasting wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="fecda-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="fecda-278">Zo ondersteunt Exchange Online standaardversleuteling met behulp van door Microsoft beheerde sleutels.</span><span class="sxs-lookup"><span data-stu-id="fecda-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fecda-279">Offboarding is niet hetzelfde als een gegevens purge.</span><span class="sxs-lookup"><span data-stu-id="fecda-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="fecda-280">Met een gegevens purge worden de gegevens van uw organisatie definitief verwijderd uit Microsoft 365, offboarding niet.</span><span class="sxs-lookup"><span data-stu-id="fecda-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="fecda-281">U kunt geen gegevens verwijderen voor een beleid voor meerdere werkbelastingen.</span><span class="sxs-lookup"><span data-stu-id="fecda-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="fecda-282">Als u besluit klantsleutel niet meer te gebruiken voor het toewijzen van DEP's met meerdere werkbelastingen, moet u contact op nemen met de Ondersteuning van Microsoft met een verzoek om 'offboard' van klantsleutel.</span><span class="sxs-lookup"><span data-stu-id="fecda-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="fecda-283">Vraag het ondersteuningsteam om een serviceaanvraag in te Microsoft 365 klantsleutelteam.</span><span class="sxs-lookup"><span data-stu-id="fecda-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="fecda-284">Contact op met m365-ck@service.microsoft.com als u vragen hebt.</span><span class="sxs-lookup"><span data-stu-id="fecda-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="fecda-285">Als u afzonderlijke postvakken niet meer wilt versleutelen met DEP's op postvakniveau, kunt u DEP's op postvakniveau uit al uw postvakken verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fecda-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="fecda-286">Als u postvakDEP's wilt verwijderen, gebruikt u Set-Mailbox PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fecda-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="fecda-287">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fecda-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="fecda-288">Voer de Set-Mailbox cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="fecda-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="fecda-289">Als u deze cmdlet uitdeelt, wordt de momenteel toegewezen DEP verwijderd en wordt het postvak opnieuw versleuteld met behulp van de DEP die is gekoppeld aan standaard door Microsoft beheerde sleutels.</span><span class="sxs-lookup"><span data-stu-id="fecda-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="fecda-290">U kunt de DEP die door beheerde sleutels van Microsoft wordt gebruikt, niet lossteken.</span><span class="sxs-lookup"><span data-stu-id="fecda-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="fecda-291">Als u de door Microsoft beheerde sleutels niet wilt gebruiken, kunt u een andere klantcodedep aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="fecda-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="fecda-292">Uw sleutels intrekken en het proces voor het gegevensre purgepad starten</span><span class="sxs-lookup"><span data-stu-id="fecda-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="fecda-293">U kunt de intrekking van alle hoofdsleutels, inclusief de beschikbaarheidssleutel, bepalen.</span><span class="sxs-lookup"><span data-stu-id="fecda-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="fecda-294">Customer Key biedt controle over het planningsaspect van de wettelijke vereisten voor u.</span><span class="sxs-lookup"><span data-stu-id="fecda-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="fecda-295">Als u besluit uw sleutels in te trekken om uw gegevens te verwijderen en de service te verlaten, wordt de beschikbaarheidssleutel verwijderd zodra het gegevens verwijderen is voltooid.</span><span class="sxs-lookup"><span data-stu-id="fecda-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="fecda-296">Dit wordt ondersteund voor klantcode-DEP's die zijn toegewezen aan afzonderlijke postvakken.</span><span class="sxs-lookup"><span data-stu-id="fecda-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="fecda-297">Microsoft 365 controleert en valideert het pad voor het verwijderen van gegevens.</span><span class="sxs-lookup"><span data-stu-id="fecda-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="fecda-298">Zie het SSAE 18 SOC 2-rapport dat beschikbaar is op de Service Trust Portal voor meer [informatie.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="fecda-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="fecda-299">Daarnaast raadt Microsoft de volgende documenten aan:</span><span class="sxs-lookup"><span data-stu-id="fecda-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="fecda-300">Handleiding risicobeoordeling en compliance voor financiële instellingen in de Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="fecda-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="fecda-301">O365 Exit Planning Considerations</span><span class="sxs-lookup"><span data-stu-id="fecda-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="fecda-302">Het zuiveren van DEP met meerdere werkbelastingen wordt niet ondersteund voor Microsoft 365 Klantcode.</span><span class="sxs-lookup"><span data-stu-id="fecda-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="fecda-303">De DEP met meerdere werkbelastingen wordt gebruikt om gegevens te versleutelen voor meerdere werkbelastingen voor alle tenantgebruikers.</span><span class="sxs-lookup"><span data-stu-id="fecda-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="fecda-304">Als u een dergelijke DEP wilt verwijderen, worden gegevens uit meerdere werkbelastingen ontoegankelijk.</span><span class="sxs-lookup"><span data-stu-id="fecda-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="fecda-305">Als u besluit om de services Microsoft 365 afsluiten, kunt u het pad van tenantverhaling volgen volgens het gedocumenteerde proces.</span><span class="sxs-lookup"><span data-stu-id="fecda-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="fecda-306">Zie [hoe u een tenant verwijdert in Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="fecda-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="fecda-307">Uw klantsleutels intrekken en de beschikbaarheidscode voor Exchange Online en Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="fecda-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="fecda-308">Wanneer u het pad voor het verwijderen van gegevens start voor Exchange Online en Skype voor Bedrijven, stelt u een permanente aanvraag voor het verwijderen van gegevens in op een DEP.</span><span class="sxs-lookup"><span data-stu-id="fecda-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="fecda-309">Hierdoor worden versleutelde gegevens definitief verwijderd in de postvakken waaraan die DEP is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="fecda-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="fecda-310">Aangezien u de PowerShell-cmdlet slechts met één DEP tegelijk kunt uitvoeren, kunt u overwegen om één DEP opnieuw toe te staan aan al uw postvakken voordat u het pad voor gegevensre purge start.</span><span class="sxs-lookup"><span data-stu-id="fecda-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="fecda-311">Gebruik het pad voor het verwijderen van gegevens niet om een subset van uw postvakken te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fecda-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="fecda-312">Dit proces is alleen bedoeld voor klanten die de service verlaten.</span><span class="sxs-lookup"><span data-stu-id="fecda-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="fecda-313">Als u het pad voor het verwijderen van gegevens wilt starten, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="fecda-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="fecda-314">Verwijder wrap- en uitpakken-machtigingen voor 'O365 Exchange Online' uit Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="fecda-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="fecda-315">Gebruik een werk- of schoolaccount met globale beheerdersbevoegdheden in uw organisatie en maak [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fecda-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="fecda-316">Voer voor elke DEP die postvakken bevat die u wilt verwijderen de cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) als volgt uit.</span><span class="sxs-lookup"><span data-stu-id="fecda-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="fecda-317">Als de opdracht mislukt, moet u ervoor zorgen dat u de machtigingen Exchange Online beide sleutels in Azure Key Vault hebt verwijderd, zoals eerder in deze taak is opgegeven.</span><span class="sxs-lookup"><span data-stu-id="fecda-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="fecda-318">Wanneer u de permanentdatapurgeRequested-schakelknop hebt ingesteld met de Set-DataEncryptionPolicy-cmdlet, kunt u deze DEP niet meer toewijzen aan postvakken.</span><span class="sxs-lookup"><span data-stu-id="fecda-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="fecda-319">Neem contact op met de ondersteuning van Microsoft en vraag de eDocument data purge aan.</span><span class="sxs-lookup"><span data-stu-id="fecda-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="fecda-320">Op uw verzoek stuurt Microsoft u een juridisch document om het verwijderen van gegevens te bevestigen en te machtigen.</span><span class="sxs-lookup"><span data-stu-id="fecda-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="fecda-321">De persoon in uw organisatie die zich heeft aangemeld als een goedkeurder in de FastTrack-aanbieding tijdens onboarding, moet dit document ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="fecda-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="fecda-322">Normaal gesproken is dit een leidinggevende of een andere aangewezen persoon in uw bedrijf die wettelijk gemachtigd is om het papierwerk namens uw organisatie te ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="fecda-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="fecda-323">Nadat uw vertegenwoordiger het juridische document heeft ondertekend, retourneerd u het document naar Microsoft (meestal via een eDoc-handtekening).</span><span class="sxs-lookup"><span data-stu-id="fecda-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="fecda-324">Nadat Microsoft het juridische document heeft ontvangen, worden cmdlets uitgevoerd om de gegevensreinerering te activeren die eerst het beleid verwijdert, de postvakken markeert voor permanente verwijdering en vervolgens de beschikbaarheidssleutel verwijdert.</span><span class="sxs-lookup"><span data-stu-id="fecda-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="fecda-325">Wanneer het proces voor het verwijderen van gegevens is voltooid, zijn de gegevens verwijderd, zijn ze niet toegankelijk voor Exchange Online en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="fecda-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="fecda-326">Uw klantsleutels en de beschikbaarheidscode intrekken voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden</span><span class="sxs-lookup"><span data-stu-id="fecda-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="fecda-327">Als u het pad voor het verwijderen van gegevens voor SharePoint Online, OneDrive voor Bedrijven en Teams wilt starten, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="fecda-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="fecda-328">Azure Key Vault-toegang intrekken.</span><span class="sxs-lookup"><span data-stu-id="fecda-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="fecda-329">Alle key vault admins moeten ermee akkoord gaan om de toegang in te trekken.</span><span class="sxs-lookup"><span data-stu-id="fecda-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="fecda-330">U verwijdert de Azure Key Vault niet voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fecda-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="fecda-331">Sleutelkluizen kunnen worden gedeeld tussen verschillende SharePoint onlinetententen en DEP's.</span><span class="sxs-lookup"><span data-stu-id="fecda-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="fecda-332">Neem contact op met Microsoft om de beschikbaarheidscode te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fecda-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="fecda-333">Wanneer u contact op wilt nemen met Microsoft om de beschikbaarheidscode te verwijderen, sturen we u een juridisch document.</span><span class="sxs-lookup"><span data-stu-id="fecda-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="fecda-334">De persoon in uw organisatie die zich heeft aangemeld als een goedkeurder in de FastTrack-aanbieding tijdens onboarding, moet dit document ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="fecda-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="fecda-335">Normaal gesproken is dit een leidinggevende of een andere aangewezen persoon in uw bedrijf die wettelijk gemachtigd is om het papierwerk namens uw organisatie te ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="fecda-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="fecda-336">Nadat uw vertegenwoordiger het juridische document heeft ondertekend, retourneert u het document naar Microsoft (meestal via een eDoc-handtekening).</span><span class="sxs-lookup"><span data-stu-id="fecda-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="fecda-337">Zodra Microsoft het juridische document heeft ontvangen, worden cmdlets uitgevoerd om de gegevens te verwijderen waarmee de tenantsleutel, sitesleutel en alle afzonderlijke sleutels per document worden verwijderd, waardoor de sleutelhiërarchie onherroepelijk wordt gebroken.</span><span class="sxs-lookup"><span data-stu-id="fecda-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="fecda-338">Nadat de cmdlets voor het verwijderen van gegevens zijn voltooid, zijn uw gegevens verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fecda-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fecda-339">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="fecda-339">Related articles</span></span>

- [<span data-ttu-id="fecda-340">Serviceversleuteling met klantsleutel</span><span class="sxs-lookup"><span data-stu-id="fecda-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="fecda-341">Meer informatie over de beschikbaarheidssleutel</span><span class="sxs-lookup"><span data-stu-id="fecda-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="fecda-342">Klantsleutel instellen</span><span class="sxs-lookup"><span data-stu-id="fecda-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="fecda-343">Een klantsleutel of een beschikbaarheidssleutel rollen of draaien</span><span class="sxs-lookup"><span data-stu-id="fecda-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="fecda-344">Klanten-lockbox</span><span class="sxs-lookup"><span data-stu-id="fecda-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="fecda-345">Serviceversleuteling</span><span class="sxs-lookup"><span data-stu-id="fecda-345">Service Encryption</span></span>](office-365-service-encryption.md)