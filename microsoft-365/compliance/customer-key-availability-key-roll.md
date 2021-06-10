---
title: Een klantsleutel of een beschikbaarheidssleutel rollen of draaien
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
description: Meer informatie over het rollen van de klantwortelsleutels die zijn opgeslagen in Azure Key Vault die worden gebruikt met de klantsleutel. Services zijn Exchange Online, Skype voor Bedrijven, SharePoint Online, OneDrive voor Bedrijven en Teams bestanden.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345116"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="2629e-104">Een klantsleutel of een beschikbaarheidssleutel rollen of draaien</span><span class="sxs-lookup"><span data-stu-id="2629e-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="2629e-105">Rol alleen een versleutelingssleutel die u gebruikt met klantsleutel wanneer uw beveiligings- of compliancevereisten voorschrijven dat u de sleutel moet rollen.</span><span class="sxs-lookup"><span data-stu-id="2629e-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="2629e-106">Verwijder bovendien geen sleutels die zijn of zijn gekoppeld aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="2629e-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="2629e-107">Wanneer u de sleutels rolt, wordt inhoud versleuteld met de vorige toetsen.</span><span class="sxs-lookup"><span data-stu-id="2629e-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="2629e-108">Hoewel actieve postvakken bijvoorbeeld regelmatig opnieuw worden versleuteld, kunnen inactieve, losgekoppelde en uitgeschakelde postvakken nog steeds worden versleuteld met de vorige sleutels.</span><span class="sxs-lookup"><span data-stu-id="2629e-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="2629e-109">SharePoint Online voert back-up van inhoud uit voor herstel- en hersteldoeleinden, zodat er mogelijk nog steeds gearchiveerd inhoud is met oudere sleutels.</span><span class="sxs-lookup"><span data-stu-id="2629e-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="2629e-110">Informatie over het rollen van de beschikbaarheidssleutel</span><span class="sxs-lookup"><span data-stu-id="2629e-110">About rolling the availability key</span></span>

<span data-ttu-id="2629e-111">Microsoft geeft klanten geen directe controle over de beschikbaarheidscode.</span><span class="sxs-lookup"><span data-stu-id="2629e-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="2629e-112">U kunt bijvoorbeeld alleen de sleutels rollen (draaien) die u bezit in Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="2629e-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="2629e-113">Microsoft 365 de beschikbaarheidstoetsen op een intern gedefinieerd schema.</span><span class="sxs-lookup"><span data-stu-id="2629e-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="2629e-114">Er is geen slaovereenkomst op serviceniveau (Customer Facing, Service Level Agreement) voor deze sleutelrolletjes.</span><span class="sxs-lookup"><span data-stu-id="2629e-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="2629e-115">Microsoft 365 de beschikbaarheidssleutel draait met Microsoft 365 servicecode in een geautomatiseerd, niet-handmatig proces.</span><span class="sxs-lookup"><span data-stu-id="2629e-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="2629e-116">Microsoft-beheerders kunnen het rollproces starten.</span><span class="sxs-lookup"><span data-stu-id="2629e-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="2629e-117">De sleutel wordt gerold met behulp van geautomatiseerde mechanismen zonder directe toegang tot het sleutelopslag.</span><span class="sxs-lookup"><span data-stu-id="2629e-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="2629e-118">Toegang tot het geheime winkel van de beschikbaarheidssleutel is niet ingericht voor Microsoft-beheerders.</span><span class="sxs-lookup"><span data-stu-id="2629e-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="2629e-119">Het rollen van beschikbaarheidssleutels maakt gebruik van hetzelfde mechanisme dat wordt gebruikt om de sleutel in eerste instantie te genereren.</span><span class="sxs-lookup"><span data-stu-id="2629e-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="2629e-120">Zie De beschikbaarheidssleutel voor meer informatie over [de beschikbaarheidscode.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="2629e-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2629e-121">Exchange Online en Skype voor Bedrijven kunnen effectief worden gerold door klanten die een nieuwe DEP maken, omdat er een unieke beschikbaarheidssleutel wordt gegenereerd voor elke DEP die u maakt.</span><span class="sxs-lookup"><span data-stu-id="2629e-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="2629e-122">Beschikbaarheidssleutels voor SharePoint Online-, OneDrive voor Bedrijven- en Teams-bestanden bestaan op forestniveau en worden gedeeld tussen DEP's en klanten, wat betekent dat rollen alleen plaatsvindt op een intern gedefinieerde planning van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2629e-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="2629e-123">Als u het risico wilt beperken dat de beschikbaarheidssleutel niet telkens wordt gerold als er een nieuwe DEP wordt gemaakt, rollen SharePoint, OneDrive en Teams de tenant intermediate key (TIK), de sleutel die wordt omwikkeld door de hoofdsleutels en de beschikbaarheidssleutel van de klant, telkens als er een nieuwe DEP wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2629e-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="2629e-124">Een nieuwe versie aanvragen van elke bestaande hoofdsleutel die u wilt rollen</span><span class="sxs-lookup"><span data-stu-id="2629e-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="2629e-125">Wanneer u een sleutel rolt, vraagt u een nieuwe versie van een bestaande sleutel aan.</span><span class="sxs-lookup"><span data-stu-id="2629e-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="2629e-126">Als u een nieuwe versie van een bestaande sleutel wilt aanvragen, gebruikt u dezelfde cmdlet, [Add-AzKeyVaultKey,](/powershell/module/az.keyvault/add-azkeyvaultkey)met dezelfde syntaxis die u hebt gebruikt om de sleutel te maken.</span><span class="sxs-lookup"><span data-stu-id="2629e-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="2629e-127">Nadat u klaar bent met het rollen van een sleutel die is gekoppeld aan een dep (Data Encryption Policy), gebruikt u een andere cmdlet om ervoor te zorgen dat klantsleutel de nieuwe sleutel gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2629e-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="2629e-128">Doe deze stap in elke Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="2629e-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="2629e-129">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2629e-129">For example:</span></span>

1. <span data-ttu-id="2629e-130">Meld u aan bij uw Azure-abonnement met Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2629e-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="2629e-131">Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="2629e-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="2629e-132">Voer de Add-AzKeyVaultKey cmdlet uit zoals wordt weergegeven in het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2629e-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="2629e-133">Aangezien in dit voorbeeld een sleutel met de naam **Contoso-CK-EX-NA-VaultA1-Key001** bestaat in de **contoso-CK-EX-NA-VaultA1-kluis,** wordt met de cmdlet een nieuwe versie van de sleutel gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2629e-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="2629e-134">Met deze bewerking blijven de vorige sleutelversies in de versiegeschiedenis voor de sleutel behouden.</span><span class="sxs-lookup"><span data-stu-id="2629e-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="2629e-135">U hebt de vorige sleutelversie nodig om de gegevens te ontsleutelen die nog steeds worden versleuteld.</span><span class="sxs-lookup"><span data-stu-id="2629e-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="2629e-136">Nadat u het rollen van een sleutel die is gekoppeld aan een DEP hebt voltooid, kunt u een extra cmdlet uitvoeren om ervoor te zorgen dat klantsleutel de nieuwe sleutel gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2629e-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="2629e-137">In de volgende secties worden de cmdlets in meer detail beschreven.</span><span class="sxs-lookup"><span data-stu-id="2629e-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="2629e-138">De toetsen bijwerken voor DEP's met meerdere werkbelastingen</span><span class="sxs-lookup"><span data-stu-id="2629e-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="2629e-139">Wanneer u een van de Azure Key Vault-sleutels rolt die zijn gekoppeld aan een DEP die met meerdere werkbelastingen wordt gebruikt, moet u de DEP bijwerken om naar de nieuwe sleutel te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2629e-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="2629e-140">In dit proces wordt de beschikbaarheidssleutel niet gedraaid.</span><span class="sxs-lookup"><span data-stu-id="2629e-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="2629e-141">Als u de klantsleutel wilt instrueren om de nieuwe sleutel te gebruiken om meerdere werkbelastingen te versleutelen, moet u de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="2629e-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="2629e-142">Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.</span><span class="sxs-lookup"><span data-stu-id="2629e-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="2629e-143">Voer de Set-M365DataAtRestEncryptionPolicy cmdlet uit.</span><span class="sxs-lookup"><span data-stu-id="2629e-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="2629e-144">Waarbij *PolicyName* de naam of unieke id van het beleid is.</span><span class="sxs-lookup"><span data-stu-id="2629e-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="2629e-145">U kunt bijvoorbeeld Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="2629e-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="2629e-146">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2629e-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="2629e-147">De sleutels voor Exchange Online-DEP's bijwerken</span><span class="sxs-lookup"><span data-stu-id="2629e-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="2629e-148">Wanneer u een van de Azure Key Vault-sleutels rolt die zijn gekoppeld aan een DEP die wordt gebruikt met Exchange Online en Skype voor Bedrijven, moet u de DEP bijwerken om naar de nieuwe sleutel te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2629e-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="2629e-149">Hiermee wordt de beschikbaarheidssleutel niet gedraaid.</span><span class="sxs-lookup"><span data-stu-id="2629e-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="2629e-150">Als u klantcode wilt instrueren om de nieuwe sleutel te gebruiken om postvakken te versleutelen, moet u Set-DataEncryptionPolicy cmdlet als volgt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="2629e-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="2629e-151">Voer de Set-DataEncryptionPolicy cmdlet uit in Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2629e-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="2629e-152">Als u de waarde wilt controleren voor de eigenschap DataEncryptionPolicyID voor het postvak, gebruikt u de stappen in Bepalen van de DEP die aan een [postvak is toegewezen.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="2629e-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="2629e-153">De waarde voor deze eigenschap wordt gewijzigd zodra de service de bijgewerkte sleutel heeft toegepast.</span><span class="sxs-lookup"><span data-stu-id="2629e-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="2629e-154">De sleutels voor SharePoint Online OneDrive voor Bedrijven en Teams bijwerken</span><span class="sxs-lookup"><span data-stu-id="2629e-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="2629e-155">SharePoint Online kunt u maar één toets tegelijk rollen.</span><span class="sxs-lookup"><span data-stu-id="2629e-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="2629e-156">Als u beide sleutels in een sleutelkluis wilt rollen, wacht u totdat de eerste bewerking is voltooid.</span><span class="sxs-lookup"><span data-stu-id="2629e-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="2629e-157">Microsoft raadt u aan uw bewerkingen te spreiden om dit probleem te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="2629e-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="2629e-158">Wanneer u een van de Azure Key Vault-sleutels rolt die zijn gekoppeld aan een DEP die wordt gebruikt met SharePoint Online en OneDrive voor Bedrijven, moet u de DEP bijwerken om naar de nieuwe sleutel te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2629e-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="2629e-159">Hiermee wordt de beschikbaarheidssleutel niet gedraaid.</span><span class="sxs-lookup"><span data-stu-id="2629e-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="2629e-160">Voer de Update-SPODataEncryptionPolicy als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="2629e-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="2629e-161">Hoewel met deze cmdlet de sleutelrolbewerking voor SharePoint Online en OneDrive voor Bedrijven wordt gestart, wordt de actie niet onmiddellijk voltooid.</span><span class="sxs-lookup"><span data-stu-id="2629e-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="2629e-162">Als u de voortgang van de sleutelrolbewerking wilt zien, Get-SPODataEncryptionPolicy de cmdlet als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="2629e-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="2629e-163">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="2629e-163">Related articles</span></span>

- [<span data-ttu-id="2629e-164">Serviceversleuteling met klantsleutel voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2629e-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="2629e-165">Klantsleutel instellen voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2629e-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="2629e-166">Klantsleutel beheren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2629e-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="2629e-167">Meer informatie over de beschikbaarheidssleutel</span><span class="sxs-lookup"><span data-stu-id="2629e-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)