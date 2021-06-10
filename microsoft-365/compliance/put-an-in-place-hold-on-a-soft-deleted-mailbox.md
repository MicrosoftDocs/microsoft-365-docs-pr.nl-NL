---
title: Een postvak In-Place op een zacht verwijderd postvak in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Informatie over het maken van een In-Place Een postvak in de wacht zetten voor een postvak dat zacht is verwijderd, om het inactief te maken en de inhoud ervan te behouden.
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162104"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="0ae15-103">Een postvak In-Place op een zacht verwijderd postvak in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0ae15-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="0ae15-104">Informatie over het maken van een In-Place Een postvak in de wacht zetten voor een postvak dat zacht is verwijderd, om het inactief te maken en de inhoud ervan te behouden.</span><span class="sxs-lookup"><span data-stu-id="0ae15-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="0ae15-105">Vervolgens kunt u microsoft eDiscovery-hulpprogramma's gebruiken om in het inactieve postvak te zoeken.</span><span class="sxs-lookup"><span data-stu-id="0ae15-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ae15-106">Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange admin center (EAC).</span><span class="sxs-lookup"><span data-stu-id="0ae15-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="0ae15-107">Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ae15-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="0ae15-108">Maar u kunt nog steeds de In-Place in de EAC  beheren of met de cmdlet Postvak Zoeken instellen in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ae15-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="0ae15-109">Vanaf 1 oktober 2020 kunt u de In-Place beheren.</span><span class="sxs-lookup"><span data-stu-id="0ae15-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="0ae15-110">U verwijdert ze alleen in het EAC of met de cmdlet **Remove-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="0ae15-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="0ae15-111">Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="0ae15-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="0ae15-112">U hebt mogelijk een situatie waarbij een persoon uw organisatie heeft verlaten en het bijbehorende gebruikersaccount en bijbehorende postvak zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0ae15-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="0ae15-113">Daarna realiseert u zich dat er informatie in het postvak staat die moet worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="0ae15-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="0ae15-114">Wat kunt u doen?</span><span class="sxs-lookup"><span data-stu-id="0ae15-114">What can you do?</span></span> <span data-ttu-id="0ae15-115">Als de bewaarperiode van het verwijderde postvak nog niet is verlopen, kunt u een In-Place Bewaring op het verwijderde postvak (een postvak met een soft-verwijderd postvak genoemd) zetten en er een inactief postvak van maken.</span><span class="sxs-lookup"><span data-stu-id="0ae15-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="0ae15-116">Een  *inactief postvak*  wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat hij of zij uw organisatie heeft verlaat.</span><span class="sxs-lookup"><span data-stu-id="0ae15-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="0ae15-117">De inhoud van een inactief postvak blijft behouden gedurende de duur van de In-Place Hold die is geplaatst in het postvak dat zacht is verwijderd toen het inactief werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0ae15-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="0ae15-118">Nadat het postvak inactief is gemaakt, kunt u in het postvak zoeken met behulp van In-Place eDiscovery in Exchange Online, Zoeken naar inhoud in het Compliancecentrum voor beveiliging & of het eDiscovery-centrum in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0ae15-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0ae15-119">In Exchange Online is een zacht verwijderd postvak een postvak dat is verwijderd, maar binnen een specifieke bewaarperiode kan worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="0ae15-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="0ae15-120">De bewaarperiode van het postvak in een Exchange Online is 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="0ae15-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="0ae15-121">Dit betekent dat het postvak binnen 30 dagen na het verwijderen kan worden hersteld (of een inactief postvak kan worden gemaakt).</span><span class="sxs-lookup"><span data-stu-id="0ae15-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="0ae15-122">Na 30 dagen is een zacht verwijderd postvak gemarkeerd voor permanent verwijderen en kan niet worden hersteld of inactief worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0ae15-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="0ae15-123">Vereisten voor In-Place-holds</span><span class="sxs-lookup"><span data-stu-id="0ae15-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="0ae15-124">U moet de cmdlet **New-MailboxSearch** in Windows PowerShell gebruiken om een In-Place postvak in een zacht verwijderd postvak te zetten.</span><span class="sxs-lookup"><span data-stu-id="0ae15-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="0ae15-125">U kunt het EAC (Exchange) of het eDiscovery-centrum niet gebruiken in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0ae15-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="0ae15-126">Voor meer informatie over het gebruik Windows PowerShell verbinding maken met Exchange Online, zie [Verbinding maken powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0ae15-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0ae15-127">Voer de volgende opdracht uit om identiteitsgegevens op te halen over de zacht verwijderde postvakken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0ae15-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="0ae15-128">Zie Overzicht van inactieve postvakken in Office 365 voor [meer informatie over inactieve postvakken.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="0ae15-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="0ae15-129">Een postvak In-Place op een zacht verwijderd postvak zetten om er een inactief postvak van te maken</span><span class="sxs-lookup"><span data-stu-id="0ae15-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="0ae15-130">Gebruik de **cmdlet New-MailboxSearch** om van een zacht verwijderd postvak een inactief postvak te maken.</span><span class="sxs-lookup"><span data-stu-id="0ae15-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="0ae15-131">Zie [New-MailboxSearch voor](/powershell/module/exchange/new-mailboxsearch)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ae15-131">For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>
  
1. <span data-ttu-id="0ae15-132">Maak een variabele die de eigenschappen van het postvak bevat.</span><span class="sxs-lookup"><span data-stu-id="0ae15-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="0ae15-133">Gebruik in de vorige opdracht de waarde van de eigenschap **DistinguishedName** of **ExchangeGuid** om het zacht verwijderde postvak te identificeren.</span><span class="sxs-lookup"><span data-stu-id="0ae15-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="0ae15-134">Deze eigenschappen zijn uniek voor elk postvak in uw organisatie, terwijl het mogelijk is dat een actief postvak en een zacht verwijderd postvak hetzelfde primaire SMTP-adres hebben.</span><span class="sxs-lookup"><span data-stu-id="0ae15-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="0ae15-135">Maak een In-Place Houd vast en plaats het op het postvak met een zachte verwijderde postvak.</span><span class="sxs-lookup"><span data-stu-id="0ae15-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="0ae15-136">In dit voorbeeld wordt geen duur van de wachttijd opgegeven.</span><span class="sxs-lookup"><span data-stu-id="0ae15-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="0ae15-137">Dit betekent dat items voor onbepaalde tijd worden gehouden of totdat de wacht wordt verwijderd uit het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="0ae15-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="0ae15-138">U kunt ook een duur van de wacht houden opgeven wanneer u de In-Place maken.</span><span class="sxs-lookup"><span data-stu-id="0ae15-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="0ae15-139">In dit voorbeeld worden items in het inactieve postvak ongeveer 7 jaar in het postvak op het postvak van de gebruiker op de plaats van de inactieve post.</span><span class="sxs-lookup"><span data-stu-id="0ae15-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="0ae15-140">Voer na een paar ogenblikken een van de volgende opdrachten uit om te controleren of het postvak met een zacht verwijderd postvak een inactief postvak is.</span><span class="sxs-lookup"><span data-stu-id="0ae15-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="0ae15-141">Of</span><span class="sxs-lookup"><span data-stu-id="0ae15-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="0ae15-142">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="0ae15-142">More information</span></span>

<span data-ttu-id="0ae15-143">Nadat u van een zacht verwijderd postvak een inactief postvak hebt maken, zijn er een aantal manieren waarop u het postvak kunt beheren.</span><span class="sxs-lookup"><span data-stu-id="0ae15-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="0ae15-144">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="0ae15-144">For more information, see:</span></span>
  
- [<span data-ttu-id="0ae15-145">De duur van bewaring van een inactief postvak wijzigen</span><span class="sxs-lookup"><span data-stu-id="0ae15-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="0ae15-146">Een inactief postvak herstellen</span><span class="sxs-lookup"><span data-stu-id="0ae15-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="0ae15-147">Een inactief postvak terugzetten</span><span class="sxs-lookup"><span data-stu-id="0ae15-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="0ae15-148">[Een inactief postvak verwijderen](delete-an-inactive-mailbox.md) (door de wacht te verwijderen)</span><span class="sxs-lookup"><span data-stu-id="0ae15-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>