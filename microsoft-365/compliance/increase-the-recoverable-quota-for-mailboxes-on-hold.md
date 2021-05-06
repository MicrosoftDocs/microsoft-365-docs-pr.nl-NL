---
title: De quota verhogen voor herstelbare items voor postvakken in bewaring
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: Schakel het archiefpostvak in en schakel automatisch uitbreidende archivering in om de map Herstelbare items voor een postvak in Microsoft 365.
ms.openlocfilehash: 7b4ee808bc3004438c9eb7424a89c01567fc04d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161893"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="0fc8b-103">De quota verhogen voor herstelbare items voor postvakken in bewaring</span><span class="sxs-lookup"><span data-stu-id="0fc8b-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="0fc8b-104">Het standaardbeleid Exchange bewaarbeleid(met de naam Standaard *MRM-beleid)* dat automatisch wordt toegepast op nieuwe postvakken in Exchange Online bevat een bewaarlabel met de naam Herstelbare items die 14 dagen naar het archief worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="0fc8b-105">Met deze bewaartag worden items verplaatst van de map Herstelbare items in het primaire postvak van de gebruiker naar de map Herstelbare items in het archiefpostvak van de gebruiker nadat de bewaarperiode van 14 dagen voor een item is verlopen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="0fc8b-106">Hiervoor moet het archiefpostvak van de gebruiker zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="0fc8b-107">Als het archiefpostvak niet is ingeschakeld, wordt er geen actie ondernomen. Dit betekent dat items in de map Herstelbare items voor een postvak in bewaring niet worden verplaatst naar het archiefpostvak nadat de bewaarperiode van 14 dagen is verlopen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="0fc8b-108">Omdat er niets wordt verwijderd uit een postvak in bewaring, is het mogelijk dat het opslagquotum voor de map Herstelbare items kan worden overschreden, met name als het archiefpostvak van de gebruiker niet is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="0fc8b-109">Om de kans op het overschrijden van deze limiet te verkleinen, wordt het opslagquotum voor de map Herstelbare items automatisch verhoogd van 30 GB naar 100 GB wanneer een bewaring in een postvak in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="0fc8b-110">Als het archiefpostvak is ingeschakeld, wordt het opslagquotum voor de map Herstelbare items in het archiefpostvak ook verhoogd van 30 GB naar 100 GB.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="0fc8b-111">Als de functie voor automatisch archiveren in Exchange Online is ingeschakeld, is het opslagquotum voor de map Herstelbare items in het archief van de gebruiker onbeperkt.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="0fc8b-112">In de volgende tabel wordt het opslagquotum voor de map Herstelbare items samengevat.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="0fc8b-113">**Locatie van de map Herstelbare items**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="0fc8b-114">**Postvakken die niet in de wacht staan**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="0fc8b-115">**Postvakken in de wacht**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0fc8b-116">Primair postvak</span><span class="sxs-lookup"><span data-stu-id="0fc8b-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="0fc8b-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="0fc8b-117">30 GB</span></span>  <br/> |<span data-ttu-id="0fc8b-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="0fc8b-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="0fc8b-119">Archiefpostvak<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0fc8b-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="0fc8b-120">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="0fc8b-120">Unlimited</span></span>  <br/> |<span data-ttu-id="0fc8b-121">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="0fc8b-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="0fc8b-122">**Totaal opslagquotum voor de map Herstelbare items**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="0fc8b-123">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="0fc8b-123">Unlimited</span></span>  <br/> |<span data-ttu-id="0fc8b-124">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="0fc8b-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="0fc8b-125"><sup>\*</sup>Het oorspronkelijke opslagquotum voor het archiefpostvak is 100 GB voor gebruikers met een Exchange Online (Abonnement 2) licentie.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="0fc8b-126">Wanneer het automatisch uitbreiden van archivering is ingeschakeld voor postvakken in bewaring, wordt het opslagquotum voor zowel het archiefpostvak als de map Herstelbare items verhoogd tot 110 GB.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="0fc8b-127">Indien nodig wordt extra archiefopslagruimte ingericht, wat resulteert in een onbeperkte hoeveelheid archiefopslag.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="0fc8b-128">Zie Overzicht van onbeperkt archiveren in Office 365 voor meer informatie over het automatisch uitbreiden [van archivering.](unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="0fc8b-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="0fc8b-129">Wanneer het opslagquotum voor de map Herstelbare items in het primaire postvak van een postvak in bewaring bijna de limiet heeft bereikt, kunt u de volgende dingen doen:</span><span class="sxs-lookup"><span data-stu-id="0fc8b-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="0fc8b-130">**Schakel het archiefpostvak in en schakel automatisch uitbreidende archivering in.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="0fc8b-131">U kunt een onbeperkte opslagcapaciteit voor de map Herstelbare items inschakelen door het archiefpostvak in te stellen en vervolgens de functie voor automatisch uitbreiden van archivering in te Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="0fc8b-132">Dit resulteert in 110 GB voor de map Herstelbare items in het primaire postvak en een onbeperkte opslagcapaciteit voor de map Herstelbare items in het archief van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="0fc8b-133">Zie hoe: [Archiefpostvakken inschakelen in](enable-archive-mailboxes.md) het Beveiligings- & compliancecentrum en [Onbeperkt archiveren inschakelen in Office 365.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="0fc8b-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0fc8b-134">Nadat u het archief hebt ingeschakeld voor een postvak dat bijna het opslagquotum voor de map Herstelbare items overschrijdt, wilt u mogelijk de assistent beheerde map uitvoeren om de assistent handmatig te activeren om het postvak te verwerken, zodat verlopen items worden verplaatst naar de map Herstelbare items in het archiefpostvak.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="0fc8b-135">Zie [Stap 4 voor](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) instructies.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="0fc8b-136">Houd er rekening mee dat andere items in het postvak van de gebruiker mogelijk worden verplaatst naar het nieuwe archiefpostvak.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="0fc8b-137">U kunt de gebruiker laten weten dat dit kan gebeuren nadat u het archiefpostvak hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="0fc8b-138">**Maak een aangepast Exchange bewaarbeleid voor postvakken in bewaring.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="0fc8b-139">Naast het inschakelen van het archiefpostvak en het automatisch uitbreiden van archivering voor postvakken in bewaring of In-Place Bewaring, kunt u ook een aangepast Exchange bewaarbeleid voor postvakken in bewaring maken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="0fc8b-140">Hiermee kunt u een bewaarbeleid toepassen op postvakken in bewaring die verschillen van het standaard MRM-beleid dat is toegepast op postvakken die niet in bewaring staan en kunt u bewaarlabels toepassen die zijn ontworpen voor postvakken in bewaring.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="0fc8b-141">Dit omvat het maken van een nieuwe bewaartag voor de map Herstelbare items.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="0fc8b-142">In de rest van dit onderwerp worden de stapsgewijs procedures beschreven voor het maken van een aangepast Exchange bewaarbeleid voor postvakken in bewaring.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="0fc8b-143">Stap 1: een aangepaste bewaartag maken voor de map Herstelbare items</span><span class="sxs-lookup"><span data-stu-id="0fc8b-143">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[<span data-ttu-id="0fc8b-144">Stap 2: Een nieuw bewaarbeleid Exchange voor postvakken in bewaring</span><span class="sxs-lookup"><span data-stu-id="0fc8b-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="0fc8b-145">Stap 3: Het nieuwe bewaarbeleid voor Exchange toepassen op postvakken in bewaring</span><span class="sxs-lookup"><span data-stu-id="0fc8b-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="0fc8b-146">(Optioneel) Stap 4: De assistent voor beheerde mappen uitvoeren om de nieuwe bewaarinstellingen toe te passen</span><span class="sxs-lookup"><span data-stu-id="0fc8b-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="0fc8b-147">Stap 1: een aangepaste bewaartag maken voor de map Herstelbare items</span><span class="sxs-lookup"><span data-stu-id="0fc8b-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="0fc8b-148">De eerste stap is het maken van een aangepaste bewaartag (een zogenaamde bewaarbeleidstag of RPT) voor de map Herstelbare items.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="0fc8b-149">Zoals eerder uitgelegd, worden met dit RPT items verplaatst van de map Herstelbare items in het primaire postvak van de gebruiker naar de map Herstelbare items in het archiefpostvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="0fc8b-150">U moet PowerShell gebruiken om een RPT te maken voor de map Herstelbare items.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="0fc8b-151">U kunt het beheercentrum Exchange (EAC) niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-151">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="0fc8b-152">Maak verbinding met Exchange Online via externe PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fc8b-152">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="0fc8b-153">Voer de volgende opdracht uit om een nieuwe RPT te maken voor de map Herstelbare items:</span><span class="sxs-lookup"><span data-stu-id="0fc8b-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="0fc8b-154">Met de volgende opdracht wordt bijvoorbeeld een RPT gemaakt voor de map Herstelbare items met de naam 'Herstelbare items 30 dagen voor postvakken in bewaring', met een bewaarperiode van 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="0fc8b-155">Dit betekent dat een item na 30 dagen in de map Herstelbare items wordt verplaatst naar de map Herstelbare items in het archiefpostvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="0fc8b-156">Het is raadzaam dat de bewaarperiode (gedefinieerd door de parameter  _AgeLimitForRetention)_ voor de RPT Herstelbare items hetzelfde is als de bewaarperiode voor verwijderde items voor de postvakken waar het RPT op wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="0fc8b-157">Hierdoor kan een gebruiker de hele bewaarperiode voor verwijderde items herstellen voordat deze naar het archiefpostvak worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="0fc8b-158">In het vorige voorbeeld is de bewaarperiode ingesteld op 30 dagen op basis van de aanname dat de bewaarperiode voor verwijderde items voor postvakken ook 30 dagen is.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="0fc8b-159">Een Exchange Online postvak is standaard geconfigureerd om verwijderde items 14 dagen te bewaren.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="0fc8b-160">U kunt deze instelling echter wijzigen in maximaal 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="0fc8b-161">Zie De bewaarperiode voor [verwijderde items](https://www.microsoft.com/?ref=go)wijzigen voor een postvak in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="0fc8b-162">Stap 2: Een nieuw bewaarbeleid Exchange voor postvakken in bewaring</span><span class="sxs-lookup"><span data-stu-id="0fc8b-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="0fc8b-163">De volgende stap is het maken van een nieuw bewaarbeleid en het toevoegen van bewaarlabels, inclusief de RPT Herstelbare items die u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-163">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="0fc8b-164">Dit nieuwe beleid wordt in de volgende stap toegepast op postvakken die in de wacht staan.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-164">This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="0fc8b-165">Voordat u het nieuwe bewaarbeleid maakt, bepaalt u de extra bewaarlabels die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-165">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="0fc8b-166">Zie het volgende voor een lijst met bewaarlabels die zijn toegevoegd aan het standaard MRM-beleid en voor informatie over het maken van nieuwe bewaarlabels:</span><span class="sxs-lookup"><span data-stu-id="0fc8b-166">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="0fc8b-167">Standaard bewaarbeleid in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0fc8b-167">Default Retention Policy in Exchange Online </span></span>](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)
    
- [<span data-ttu-id="0fc8b-168">Standaardmappen die bewaarbeleidslabels ondersteunen</span><span class="sxs-lookup"><span data-stu-id="0fc8b-168">Default folders that support Retention Policy Tags</span></span>](/exchange/security-and-compliance/messaging-records-management/default-folders)
    
- <span data-ttu-id="0fc8b-169">De sectie Een bewaarlabel maken in het [onderwerp Bewaarbeleid](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) maken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-169">The "Create a retention tag" section in the [Create a Retention Policy](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) topic.</span></span>
    
<span data-ttu-id="0fc8b-170">U kunt het EAC of Exchange Online PowerShell gebruiken om een bewaarbeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="0fc8b-171">Het EAC gebruiken om een bewaarbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="0fc8b-171">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="0fc8b-172">Ga in het EAC naar **Bewaarbeleid voor nalevingsbeheer** \> en klik vervolgens **op Pictogram** ![ ](../media/ITPro-EAC-AddIcon.gif) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="0fc8b-173">Typ op **de pagina Nieuw** bewaarbeleid onder **Naam** een naam die het doel van het bewaarbeleid beschrijft. bijvoorbeeld **MRM-beleid voor postvakken in de wacht.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="0fc8b-174">Klik **onder Bewaarlabels** op **Pictogram** ![ ](../media/ITPro-EAC-AddIcon.gif) toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="0fc8b-175">Selecteer in de lijst met bewaarlabels de RPT Herstelbare items die u hebt gemaakt in stap 1 en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Het aangepaste bewaarlabel voor herstelbare items selecteren](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="0fc8b-177">Selecteer extra bewaarlabels die u wilt toevoegen aan het bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-177">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="0fc8b-178">U kunt bijvoorbeeld dezelfde tags toevoegen die zijn opgenomen in het standaard MRM-beleid.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-178">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="0fc8b-179">Wanneer u klaar bent met het toevoegen van bewaarlabels, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-179">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="0fc8b-180">Klik **op Opslaan** om het nieuwe bewaarbeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-180">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="0fc8b-181">De bewaarlabels die zijn gekoppeld aan het bewaarbeleid, worden weergegeven in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![Bewaarlabels die zijn gekoppeld aan het bewaarbeleid, worden weergegeven in het detailvenster](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="0fc8b-183">PowerShell Exchange Online gebruiken om een bewaarbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="0fc8b-183">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="0fc8b-184">Voer de volgende opdracht uit om nieuw bewaarbeleid voor postvakken in bewaring te maken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-184">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="0fc8b-185">Met de volgende opdracht worden bijvoorbeeld het bewaarbeleid en gekoppelde bewaarlabels gemaakt die in de vorige afbeelding worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="0fc8b-186">Stap 3: Het nieuwe bewaarbeleid voor Exchange toepassen op postvakken in bewaring</span><span class="sxs-lookup"><span data-stu-id="0fc8b-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="0fc8b-187">De laatste stap is het toepassen van het nieuwe bewaarbeleid dat u in stap 2 hebt gemaakt op postvakken in bewaring in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="0fc8b-188">U kunt het EAC of Exchange Online PowerShell gebruiken om het bewaarbeleid toe te passen op één postvak of op meerdere postvakken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="0fc8b-189">Het EAC gebruiken om het nieuwe bewaarbeleid toe te passen</span><span class="sxs-lookup"><span data-stu-id="0fc8b-189">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="0fc8b-190">Ga naar **Geadresseerdenpostvakken.**  >  </span><span class="sxs-lookup"><span data-stu-id="0fc8b-190">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="0fc8b-191">Selecteer in de lijstweergave het postvak waar u het bewaarbeleid op wilt toepassen en klik vervolgens op **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="0fc8b-192">Klik op **de pagina Gebruikerspostvak** op **Postvakfuncties.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="0fc8b-193">Selecteer **onder Bewaarbeleid** het bewaarbeleid dat u hebt gemaakt in stap 2 en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="0fc8b-194">U kunt het EAC ook gebruiken om het bewaarbeleid toe te passen op meerdere postvakken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="0fc8b-195">Ga naar **Geadresseerdenpostvakken.**  >  </span><span class="sxs-lookup"><span data-stu-id="0fc8b-195">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="0fc8b-196">Gebruik in de lijstweergave de toetsen Shift of Ctrl om meerdere postvakken te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="0fc8b-197">Klik in het detailvenster op **Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-197">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="0fc8b-198">Klik **onder Bewaarbeleid** op **Bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-198">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="0fc8b-199">Selecteer op **de pagina Bewaarbeleid bulksgewijs** toewijzen het bewaarbeleid dat u hebt gemaakt in stap 2 en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="0fc8b-200">Gebruik Exchange Online PowerShell om het nieuwe bewaarbeleid toe te passen</span><span class="sxs-lookup"><span data-stu-id="0fc8b-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="0fc8b-201">U kunt Exchange Online PowerShell gebruiken om een nieuw bewaarbeleid toe te passen op één postvak.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="0fc8b-202">Maar de echte kracht van PowerShell is dat u deze kunt gebruiken om snel alle postvakken in uw organisatie te identificeren die in bewaring staan voor juridische procedures of In-Place Bewaring en vervolgens het nieuwe bewaarbeleid toepassen op alle postvakken die in bewaring staan in één opdracht.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="0fc8b-203">Hier zijn enkele voorbeelden van het gebruik Exchange PowerShell om een bewaarbeleid toe te passen op een of meer postvakken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="0fc8b-204">In alle voorbeelden wordt het bewaarbeleid toegepast dat is gemaakt in stap 2.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-204">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="0fc8b-205">In dit voorbeeld wordt het nieuwe bewaarbeleid toegepast op het postvak van Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="0fc8b-206">In dit voorbeeld wordt het nieuwe bewaarbeleid toegepast op alle postvakken in de organisatie die in bewaring staan voor rechtszaken.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="0fc8b-207">In dit voorbeeld wordt het nieuwe bewaarbeleid toegepast op alle postvakken in de organisatie die In-Place bewaring.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="0fc8b-208">U kunt de **cmdlet Postvak** IN gebruiken om te controleren of het nieuwe bewaarbeleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="0fc8b-209">Hier zijn enkele voorbeelden om te controleren of de opdrachten in de vorige voorbeelden het bewaarbeleid 'MRM-beleid voor postvakken in bewaring' hebben toegepast op postvakken in De bewaring van geschillen en postvakken in In-Place Bewaring.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="0fc8b-210">(Optioneel) Stap 4: De assistent voor beheerde mappen uitvoeren om de nieuwe bewaarinstellingen toe te passen</span><span class="sxs-lookup"><span data-stu-id="0fc8b-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="0fc8b-211">Nadat u het nieuwe Exchange bewaarbeleid hebt toegepast op postvakken in bewaring, kan het tot 7 dagen in Exchange Online duren voordat de assistent voor beheerde mappen deze postvakken verwerkt met de instellingen in het nieuwe bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="0fc8b-212">In plaats van te wachten totdat de beheerde mapassistent wordt uitgevoerd, kunt u de **cmdlet Start-ManagedFolderAssistant** gebruiken om de assistent handmatig te activeren om de postvakken te verwerken waarin u het nieuwe bewaarbeleid hebt toegepast.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="0fc8b-213">Voer de volgende opdracht uit om de beheerde mapassistent voor het postvak van Pilar Pinilla te starten.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="0fc8b-214">Voer de volgende opdrachten uit om de Beheerde mapassistent voor alle postvakken in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="0fc8b-215">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="0fc8b-215">More information</span></span>

- <span data-ttu-id="0fc8b-216">Nadat u het archiefpostvak van een gebruiker hebt ingeschakeld, kunt u de gebruiker laten weten dat andere items in het postvak (niet alleen items in de map Herstelbare items) mogelijk worden verplaatst naar het archiefpostvak.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="0fc8b-217">Dit komt omdat het standaard MRM-beleid dat is toegewezen aan Exchange Online-postvakken een bewaarlabel bevat (met de naam Standaard 2 jaar verplaatsen naar archiveren) dat items naar het archiefpostvak verplaatst twee jaar na de datum waarop het item in het postvak is bezorgd of door de gebruiker is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="0fc8b-218">Zie Standaard bewaarbeleid [in](/exchange/security-and-compliance/messaging-records-management/default-retention-policy) Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0fc8b-218">For more information, see [Default Retention Policy in Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span></span>
    
- <span data-ttu-id="0fc8b-219">Nadat u het archiefpostvak van een gebruiker hebt ingeschakeld, kunt u de gebruiker ook laten weten dat hij of zij verwijderde items kan herstellen in de map Herstelbare items in het archiefpostvak.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="0fc8b-220">Ze kunnen dit doen in Outlook door de map Verwijderde **items** in het archiefpostvak te selecteren en vervolgens op Verwijderde items van **Server** herstellen op het tabblad Start **te** klikken. Zie Verwijderde items herstellen in Outlook voor Windows voor meer informatie over het herstellen [van verwijderde items.](https://go.microsoft.com/fwlink/p/?LinkId=624829)</span><span class="sxs-lookup"><span data-stu-id="0fc8b-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span>