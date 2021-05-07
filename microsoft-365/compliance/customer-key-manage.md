---
title: Klantcode beheren
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Nadat u Klantsleutel hebt ingesteld, leert u hoe u deze beheert door AKV-sleutels te herstellen en machtigingen en uw gegevensversleutelingsbeleid te beheren.
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162484"
---
# <a name="manage-customer-key"></a><span data-ttu-id="9e05b-103">Klantcode beheren</span><span class="sxs-lookup"><span data-stu-id="9e05b-103">Manage Customer Key</span></span>

<span data-ttu-id="9e05b-104">Nadat u Klantcode voor Office 365 hebt ingesteld, kunt u uw sleutels beheren, zoals in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="9e05b-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="9e05b-105">Meer informatie over Klantcode in de gerelateerde onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="9e05b-106">Azure Key Vault-sleutels herstellen</span><span class="sxs-lookup"><span data-stu-id="9e05b-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="9e05b-107">Voordat u herstelt, gebruikt u de herstelmogelijkheden van soft delete.</span><span class="sxs-lookup"><span data-stu-id="9e05b-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="9e05b-108">Alle sleutels die worden gebruikt met klantsleutel zijn vereist om soft delete in te stellen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="9e05b-109">Soft delete werkt als een prullenbak en maakt herstel tot 90 dagen mogelijk zonder dat u het hoeft te herstellen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="9e05b-110">Herstellen is alleen vereist in extreme of ongebruikelijke omstandigheden, bijvoorbeeld als de sleutel- of sleutelkluis verloren gaat.</span><span class="sxs-lookup"><span data-stu-id="9e05b-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="9e05b-111">Als u een sleutel moet herstellen voor gebruik met klantsleutel, Azure PowerShell u de cmdlet Restore-AzureKeyVaultKey als volgt:</span><span class="sxs-lookup"><span data-stu-id="9e05b-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="9e05b-112">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9e05b-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="9e05b-113">Als de sleutelkluis al een sleutel met dezelfde naam bevat, mislukt de herstelbewerking.</span><span class="sxs-lookup"><span data-stu-id="9e05b-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="9e05b-114">Restore-AzKeyVaultKey herstelt alle sleutelversies en alle metagegevens voor de sleutel, inclusief de sleutelnaam.</span><span class="sxs-lookup"><span data-stu-id="9e05b-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="9e05b-115">Machtigingen voor sleutelkluis beheren</span><span class="sxs-lookup"><span data-stu-id="9e05b-115">Manage key vault permissions</span></span>

<span data-ttu-id="9e05b-116">Er zijn verschillende cmdlets beschikbaar waarmee u machtigingen voor sleutelkluisen kunt bekijken en zo nodig kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="9e05b-117">Mogelijk moet u machtigingen verwijderen, bijvoorbeeld wanneer een werknemer het team verlaat.</span><span class="sxs-lookup"><span data-stu-id="9e05b-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="9e05b-118">Voor elk van deze taken gebruikt u Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e05b-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="9e05b-119">Zie Overzicht van [Azure PowerShell.](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="9e05b-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="9e05b-120">Als u machtigingen voor de sleutelkluis wilt weergeven, Get-AzKeyVault cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e05b-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="9e05b-121">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9e05b-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="9e05b-122">Als u de machtigingen van een beheerder wilt verwijderen, moet u Remove-AzKeyVaultAccessPolicy cmdlet uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="9e05b-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="9e05b-123">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9e05b-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="9e05b-124">Beleid voor gegevensversleuteling (DEP's) beheren met klantcode</span><span class="sxs-lookup"><span data-stu-id="9e05b-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="9e05b-125">Klantsleutel verwerkt DEP's anders tussen de verschillende services.</span><span class="sxs-lookup"><span data-stu-id="9e05b-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="9e05b-126">U kunt bijvoorbeeld een ander aantal DEP's voor de verschillende services maken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="9e05b-127">**Exchange Online en Skype voor Bedrijven:** U kunt maximaal 50 DEP's maken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="9e05b-128">Zie Een [dep (Data Encryption Policy) maken voor](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)gebruik met Exchange Online en Skype voor Bedrijven voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9e05b-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="9e05b-129">**SharePoint Online, OneDrive voor Bedrijven en Teams bestanden:** Een DEP is van toepassing op gegevens op één geografische locatie, ook wel een _geo genoemd._</span><span class="sxs-lookup"><span data-stu-id="9e05b-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="9e05b-130">Als u de functie multi-geo van Office 365 gebruikt, kunt u één DEP per geo maken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="9e05b-131">Als u geen multi-geo gebruikt, kunt u één DEP maken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="9e05b-132">Normaal gesproken maakt u de DEP wanneer u Klantcode in stelt.</span><span class="sxs-lookup"><span data-stu-id="9e05b-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="9e05b-133">Zie Een [dep (Data Encryption Policy) maken](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)voor elke SharePoint Online en OneDrive voor Bedrijven geo voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9e05b-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="9e05b-134">Bekijk de DEP's die u hebt gemaakt voor Exchange Online en Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9e05b-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="9e05b-135">Als u een lijst wilt weergeven met alle DEP's die u hebt gemaakt voor Exchange Online en Skype voor Bedrijven met de powershell-cmdlet Get-DataEncryptionPolicy PowerShell, moet u deze stappen voltooien.</span><span class="sxs-lookup"><span data-stu-id="9e05b-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="9e05b-136">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e05b-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="9e05b-137">Als u alle DEP's in uw organisatie wilt retourneren, Get-DataEncryptionPolicy de cmdlet zonder parameters.</span><span class="sxs-lookup"><span data-stu-id="9e05b-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="9e05b-138">Zie [Get-DataEncryptionPolicy (Get-DataEncryptionPolicy)](/powershell/module/exchange/get-dataencryptionpolicy)voor meer informatie over Get-DataEncryptionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e05b-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="9e05b-139">Een DEP toewijzen voordat u een postvak migreert naar de cloud</span><span class="sxs-lookup"><span data-stu-id="9e05b-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="9e05b-140">Wanneer u de DEP toewijst, Microsoft 365 de inhoud van het postvak versleutelt met behulp van de toegewezen DEP tijdens de migratie.</span><span class="sxs-lookup"><span data-stu-id="9e05b-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="9e05b-141">Dit proces is efficiënter dan het migreren van het postvak, het toewijzen van de DEP en het wachten op versleuteling, wat uren of mogelijk dagen kan duren.</span><span class="sxs-lookup"><span data-stu-id="9e05b-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="9e05b-142">Als u een DEP wilt toewijzen aan een postvak voordat u deze migreert naar Office 365, voer u de Set-MailUser cmdlet uit in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9e05b-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="9e05b-143">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e05b-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="9e05b-144">Voer de Set-MailUser cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="9e05b-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="9e05b-145">Waar *GeneralMailboxOrMailUserIdParameter* een postvak aangeeft en *DataEncryptionPolicyIdParameter* de id van de DEP is.</span><span class="sxs-lookup"><span data-stu-id="9e05b-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="9e05b-146">Zie [Set-MailUser](/powershell/module/exchange/set-mailuser)voor meer Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e05b-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="9e05b-147">Bepalen welke DEP is toegewezen aan een postvak</span><span class="sxs-lookup"><span data-stu-id="9e05b-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="9e05b-148">Als u de DEP wilt bepalen die aan een postvak is toegewezen, gebruikt u Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e05b-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="9e05b-149">De cmdlet retourneert een unieke id (GUID).</span><span class="sxs-lookup"><span data-stu-id="9e05b-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="9e05b-150">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e05b-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="9e05b-151">Waar *GeneralMailboxOrMailUserIdParameter* een postvak aangeeft en DataEncryptionPolicyID de GUID van de DEP retourneert.</span><span class="sxs-lookup"><span data-stu-id="9e05b-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="9e05b-152">Zie [Get-MailboxStatistics (Get-MailboxStatistics)](/powershell/module/exchange/get-mailboxstatistics)voor meer informatie over Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e05b-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="9e05b-153">Voer de Get-DataEncryptionPolicy cmdlet uit om de vriendelijke naam te weten te komen van de DEP waaraan het postvak is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="9e05b-154">Waarbij *GUID* de GUID is die wordt geretourneerd door de Get-MailboxStatistics cmdlet in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="9e05b-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="9e05b-155">Controleren of de klantsleutel is voltooid met versleuteling</span><span class="sxs-lookup"><span data-stu-id="9e05b-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="9e05b-156">Gebruik de stappen in deze sectie om ervoor te zorgen dat versleuteling wordt voltooid, ongeacht of u zojuist een klantsleutel hebt gerold, een nieuw dep hebt toegewezen of een postvak hebt gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="9e05b-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="9e05b-157">Versleuteling controleren voor Exchange Online en Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9e05b-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="9e05b-158">Het versleutelen van een postvak kan enige tijd duren.</span><span class="sxs-lookup"><span data-stu-id="9e05b-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="9e05b-159">U wordt aangeraden 72 uur te wachten voordat u versleuteling probeert te valideren nadat u een DEP hebt gewijzigd of de eerste keer dat u een DEP aan een postvak toewijst.</span><span class="sxs-lookup"><span data-stu-id="9e05b-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="9e05b-160">Gebruik de Get-MailboxStatistics cmdlet om te bepalen of een postvak is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="9e05b-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="9e05b-161">De eigenschap IsEncrypted retourneert een waarde van **waar** als het postvak is versleuteld en een waarde van **onwaar** als het postvak niet is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="9e05b-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="9e05b-162">De tijd om postvak te voltooien is afhankelijk van de grootte van het postvak.</span><span class="sxs-lookup"><span data-stu-id="9e05b-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="9e05b-163">Als klantcode het postvak na 72 uur vanaf het moment dat u een nieuwe DEP toewijst, nog niet volledig heeft versleuteld, neem dan contact op met microsoft-ondersteuning voor hulp.</span><span class="sxs-lookup"><span data-stu-id="9e05b-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="9e05b-164">De New-MoveRequest cmdlet is niet meer beschikbaar voor lokale postvakverhuisbewegingen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="9e05b-165">Raadpleeg deze [aankondiging voor](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9e05b-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="9e05b-166">Versleuteling controleren voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden</span><span class="sxs-lookup"><span data-stu-id="9e05b-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="9e05b-167">Controleer de status van versleuteling door de Get-SPODataEncryptionPolicy als volgt uit te laten:</span><span class="sxs-lookup"><span data-stu-id="9e05b-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="9e05b-168">De uitvoer van deze cmdlet omvat:</span><span class="sxs-lookup"><span data-stu-id="9e05b-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="9e05b-169">De URI van de primaire sleutel.</span><span class="sxs-lookup"><span data-stu-id="9e05b-169">The URI of the primary key.</span></span>

- <span data-ttu-id="9e05b-170">De URI van de secundaire sleutel.</span><span class="sxs-lookup"><span data-stu-id="9e05b-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="9e05b-171">De versleutelingsstatus voor de geo.</span><span class="sxs-lookup"><span data-stu-id="9e05b-171">The encryption status for the geo.</span></span> <span data-ttu-id="9e05b-172">Mogelijke staten zijn:</span><span class="sxs-lookup"><span data-stu-id="9e05b-172">Possible states include:</span></span>

  - <span data-ttu-id="9e05b-173">**Niet-geregistreerd:** Klantsleutelversleuteling is nog niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="9e05b-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="9e05b-174">**Registreren:** Klantsleutelversleuteling is toegepast en uw bestanden worden momenteel versleuteld.</span><span class="sxs-lookup"><span data-stu-id="9e05b-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="9e05b-175">Als de sleutel voor de geo wordt geregistreerd, wordt ook informatie weergegeven over het percentage sites in de geo dat is voltooid, zodat u de voortgang van versleuteling kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="9e05b-176">**Geregistreerd:** Klantsleutelversleuteling is toegepast en alle bestanden op alle sites zijn versleuteld.</span><span class="sxs-lookup"><span data-stu-id="9e05b-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="9e05b-177">**Rollend:** Er wordt een sleutelrol uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9e05b-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="9e05b-178">Als de sleutel voor het geo wordt gerold, wordt ook informatie weergegeven over het percentage sites dat de sleutelrolbewerking heeft voltooid, zodat u de voortgang kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="9e05b-179">Terugdraaien van klantsleutel naar beheerde sleutels van Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e05b-179">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="9e05b-180">Voor Klantsleutel op tenantniveau moet u contact op nemen met Microsoft met een verzoek om 'offboarding' van klantsleutel.</span><span class="sxs-lookup"><span data-stu-id="9e05b-180">For Customer Key at the tenant level, you'll need to reach out to Microsoft with a request for “offboarding” from Customer Key.</span></span> <span data-ttu-id="9e05b-181">De aanvraag wordt afgehandeld door het on-call engineering-team.</span><span class="sxs-lookup"><span data-stu-id="9e05b-181">The request will be handled by the On Call Engineering team.</span></span>

<span data-ttu-id="9e05b-182">Voor Klantsleutel op toepassingsniveau doet u dit door een DEP uit postvakken te verwijderen met behulp van de PowerShell-cmdlet Set-mailbox en de instelling voor `DataEncryptionPolicy` `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="9e05b-182">For Customer Key at the application level, you do this by unassigning a DEP from mailboxes using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="9e05b-183">Als u deze cmdlet uitdeelt, wordt de momenteel toegewezen DEP verwijderd en wordt het postvak opnieuw versleuteld met behulp van de DEP die is gekoppeld aan standaard beheerde microsoft-sleutels.</span><span class="sxs-lookup"><span data-stu-id="9e05b-183">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="9e05b-184">U kunt de DEP die door beheerde sleutels van Microsoft wordt gebruikt, niet lossteken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-184">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="9e05b-185">Als u de beheerde sleutels van Microsoft niet wilt gebruiken, kunt u een andere klantcodedep aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-185">If you don't want to use Microsoft managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

<span data-ttu-id="9e05b-186">Als u de DEP uit een postvak wilt verwijderen met de Set-Mailbox PowerShell-cmdlet, moet u deze stappen voltooien.</span><span class="sxs-lookup"><span data-stu-id="9e05b-186">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="9e05b-187">Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e05b-187">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="9e05b-188">Voer de Set-Mailbox cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="9e05b-188">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="9e05b-189">Uw sleutels intrekken en het proces voor het gegevensre purgepad starten</span><span class="sxs-lookup"><span data-stu-id="9e05b-189">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="9e05b-190">U kunt de intrekking van alle hoofdsleutels, inclusief de beschikbaarheidssleutel, bepalen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-190">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="9e05b-191">Customer Key biedt controle over het planningsaspect van de wettelijke vereisten voor u.</span><span class="sxs-lookup"><span data-stu-id="9e05b-191">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="9e05b-192">Als u besluit uw sleutels in te trekken om uw gegevens te verwijderen en de service te verlaten, wordt de beschikbaarheidssleutel verwijderd zodra het gegevens verwijderen is voltooid.</span><span class="sxs-lookup"><span data-stu-id="9e05b-192">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="9e05b-193">U kunt geen gegevens verwijderen voor een tenantbeleid.</span><span class="sxs-lookup"><span data-stu-id="9e05b-193">You can't perform a data purge for a tenant-level policy.</span></span>

<span data-ttu-id="9e05b-194">Microsoft 365 controleert en valideert het pad voor het verwijderen van gegevens.</span><span class="sxs-lookup"><span data-stu-id="9e05b-194">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="9e05b-195">Zie het SSAE 18 SOC 2-rapport dat beschikbaar is op de Service Trust Portal voor meer [informatie.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="9e05b-195">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="9e05b-196">Daarnaast raadt Microsoft de volgende documenten aan:</span><span class="sxs-lookup"><span data-stu-id="9e05b-196">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="9e05b-197">Handleiding risicobeoordeling en compliance voor financiële instellingen in de Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="9e05b-197">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="9e05b-198">O365 Exit Planning Considerations</span><span class="sxs-lookup"><span data-stu-id="9e05b-198">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="9e05b-199">Het pad voor het verwijderen van gegevens verschilt enigszins tussen de verschillende services.</span><span class="sxs-lookup"><span data-stu-id="9e05b-199">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="9e05b-200">Uw klantsleutels intrekken en de beschikbaarheidscode voor Exchange Online en Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9e05b-200">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="9e05b-201">Wanneer u het pad voor het verwijderen van gegevens start voor Exchange Online en Skype voor Bedrijven, stelt u een permanente aanvraag voor het verwijderen van gegevens in op een DEP.</span><span class="sxs-lookup"><span data-stu-id="9e05b-201">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="9e05b-202">Hierdoor worden versleutelde gegevens definitief verwijderd in de postvakken waaraan die DEP is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-202">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="9e05b-203">Aangezien u de PowerShell-cmdlet slechts met één DEP tegelijk kunt uitvoeren, kunt u overwegen om één DEP opnieuw toe te staan aan al uw postvakken voordat u het pad voor gegevensre purge start.</span><span class="sxs-lookup"><span data-stu-id="9e05b-203">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="9e05b-204">Gebruik het pad voor het verwijderen van gegevens niet om een subset van uw postvakken te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-204">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="9e05b-205">Dit proces is alleen bedoeld voor klanten die de service verlaten.</span><span class="sxs-lookup"><span data-stu-id="9e05b-205">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="9e05b-206">Als u het pad voor het verwijderen van gegevens wilt starten, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="9e05b-206">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="9e05b-207">Verwijder wrap- en uitpakken-machtigingen voor 'O365 Exchange Online' uit Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="9e05b-207">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="9e05b-208">Gebruik een werk- of schoolaccount met globale beheerdersbevoegdheden in uw organisatie en maak [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e05b-208">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="9e05b-209">Voer voor elke DEP die postvakken bevat die u wilt verwijderen de cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) als volgt uit.</span><span class="sxs-lookup"><span data-stu-id="9e05b-209">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="9e05b-210">Als de opdracht mislukt, moet u ervoor zorgen dat u de machtigingen Exchange Online beide sleutels in Azure Key Vault hebt verwijderd, zoals eerder in deze taak is opgegeven.</span><span class="sxs-lookup"><span data-stu-id="9e05b-210">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="9e05b-211">Wanneer u de permanentdatapurgeRequested-schakelknop hebt ingesteld met de Set-DataEncryptionPolicy-cmdlet, kunt u deze DEP niet meer toewijzen aan postvakken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-211"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="9e05b-212">Neem contact op met de ondersteuning van Microsoft en vraag de eDocument data purge aan.</span><span class="sxs-lookup"><span data-stu-id="9e05b-212">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="9e05b-213">Op uw verzoek stuurt Microsoft u een juridisch document om het verwijderen van gegevens te bevestigen en te machtigen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-213">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="9e05b-214">De persoon in uw organisatie die zich heeft aangemeld als een goedkeurder in de FastTrack-aanbieding tijdens onboarding, moet dit document ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-214">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="9e05b-215">Normaal gesproken is dit een leidinggevende of een andere aangewezen persoon in uw bedrijf die wettelijk gemachtigd is om het papierwerk namens uw organisatie te ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-215">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="9e05b-216">Nadat uw vertegenwoordiger het juridische document heeft ondertekend, retourneerd u het document naar Microsoft (meestal via een eDoc-handtekening).</span><span class="sxs-lookup"><span data-stu-id="9e05b-216">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="9e05b-217">Nadat Microsoft het juridische document heeft ontvangen, worden cmdlets uitgevoerd om de gegevensreinerering te activeren die eerst het beleid verwijdert, de postvakken markeert voor permanente verwijdering en vervolgens de beschikbaarheidssleutel verwijdert.</span><span class="sxs-lookup"><span data-stu-id="9e05b-217">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="9e05b-218">Wanneer het proces voor het verwijderen van gegevens is voltooid, zijn de gegevens verwijderd, zijn ze niet toegankelijk voor Exchange Online en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="9e05b-218">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="9e05b-219">Uw klantsleutels en de beschikbaarheidscode intrekken voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden</span><span class="sxs-lookup"><span data-stu-id="9e05b-219">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="9e05b-220">Als u het pad voor het verwijderen van gegevens voor SharePoint Online, OneDrive voor Bedrijven en Teams wilt starten, gaat u als volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="9e05b-220">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="9e05b-221">Azure Key Vault-toegang intrekken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-221">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="9e05b-222">Alle key vault admins moeten ermee akkoord gaan om de toegang in te trekken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-222">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="9e05b-223">U verwijdert de Azure Key Vault niet voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9e05b-223">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="9e05b-224">Sleutelkluizen kunnen worden gedeeld tussen verschillende SharePoint onlinetententen en DEP's.</span><span class="sxs-lookup"><span data-stu-id="9e05b-224">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="9e05b-225">Neem contact op met Microsoft om de beschikbaarheidscode te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-225">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="9e05b-226">Wanneer u contact op wilt nemen met Microsoft om de beschikbaarheidscode te verwijderen, sturen we u een juridisch document.</span><span class="sxs-lookup"><span data-stu-id="9e05b-226">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="9e05b-227">De persoon in uw organisatie die zich heeft aangemeld als een goedkeurder in de FastTrack-aanbieding tijdens onboarding, moet dit document ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-227">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="9e05b-228">Normaal gesproken is dit een leidinggevende of een andere aangewezen persoon in uw bedrijf die wettelijk gemachtigd is om het papierwerk namens uw organisatie te ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="9e05b-228">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="9e05b-229">Nadat uw vertegenwoordiger het juridische document heeft ondertekend, retourneert u het document naar Microsoft (meestal via een eDoc-handtekening).</span><span class="sxs-lookup"><span data-stu-id="9e05b-229">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="9e05b-230">Zodra Microsoft het juridische document heeft ontvangen, worden cmdlets uitgevoerd om de gegevens te verwijderen waarmee de tenantsleutel, sitesleutel en alle afzonderlijke sleutels per document worden verwijderd, waardoor de sleutelhiërarchie onherroepelijk wordt gebroken.</span><span class="sxs-lookup"><span data-stu-id="9e05b-230">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="9e05b-231">Nadat de cmdlets voor het verwijderen van gegevens zijn voltooid, zijn uw gegevens verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9e05b-231">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9e05b-232">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="9e05b-232">Related articles</span></span>

- [<span data-ttu-id="9e05b-233">Serviceversleuteling met klantsleutel</span><span class="sxs-lookup"><span data-stu-id="9e05b-233">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="9e05b-234">Meer informatie over de beschikbaarheidssleutel</span><span class="sxs-lookup"><span data-stu-id="9e05b-234">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="9e05b-235">Klantsleutel instellen</span><span class="sxs-lookup"><span data-stu-id="9e05b-235">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="9e05b-236">Een klantsleutel of een beschikbaarheidssleutel rollen of draaien</span><span class="sxs-lookup"><span data-stu-id="9e05b-236">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="9e05b-237">Klanten-lockbox</span><span class="sxs-lookup"><span data-stu-id="9e05b-237">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="9e05b-238">Serviceversleuteling</span><span class="sxs-lookup"><span data-stu-id="9e05b-238">Service Encryption</span></span>](office-365-service-encryption.md)