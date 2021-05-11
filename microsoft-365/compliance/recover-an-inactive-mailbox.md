---
title: Een inactief postvak herstellen
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Informatie over het herstellen van de inhoud van een inactief postvak in Office 365 door het te converteren naar een nieuw postvak met de inhoud van het inactieve postvak.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162115"
---
# <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="be16d-103">Een inactief postvak herstellen</span><span class="sxs-lookup"><span data-stu-id="be16d-103">Recover an inactive mailbox</span></span>

<span data-ttu-id="be16d-104">Een inactief postvak (een type postvak dat wordt verwijderd) wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat hij of zij uw organisatie heeft verlaat.</span><span class="sxs-lookup"><span data-stu-id="be16d-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="be16d-105">Als die werknemer terugkeert naar uw organisatie of als een andere werknemer de taakverantwoordelijkheden van de voormalige werknemer op zich neemt, kunt u de inhoud van het inactieve postvak op twee manieren beschikbaar stellen aan een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="be16d-105">If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span>

- <span data-ttu-id="be16d-106">**Een inactief postvak herstellen.**</span><span class="sxs-lookup"><span data-stu-id="be16d-106">**Recover an inactive mailbox.**</span></span> <span data-ttu-id="be16d-107">Als de voormalige werknemer terugkeert naar uw organisatie of als een nieuwe werknemer wordt aangenomen om de taaktaken van de voormalige werknemer op zich te nemen, kunt u de inhoud van het inactieve postvak herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-107">If the former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the former employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="be16d-108">Met deze methode wordt het inactieve postvak ge converteerd naar een nieuw, actief postvak dat de inhoud van het inactieve postvak bevat.</span><span class="sxs-lookup"><span data-stu-id="be16d-108">This method converts the inactive mailbox to a new, active mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="be16d-109">Nadat het is hersteld, bestaat het inactieve postvak niet meer.</span><span class="sxs-lookup"><span data-stu-id="be16d-109">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="be16d-110">In de procedures in dit onderwerp wordt deze methode beschreven.</span><span class="sxs-lookup"><span data-stu-id="be16d-110">The procedures in this topic describe this method.</span></span>

- <span data-ttu-id="be16d-111">**Een inactief postvak herstellen.**</span><span class="sxs-lookup"><span data-stu-id="be16d-111">**Restore an inactive mailbox.**</span></span> <span data-ttu-id="be16d-112">Als een andere werknemer de taakverantwoordelijkheden van de voormalige werknemer op zich neemt of als een andere gebruiker toegang nodig heeft tot de inhoud van het inactieve postvak, kunt u de inhoud van het inactieve postvak herstellen (of samenvoegen) naar een bestaand postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-112">If another employee takes on the job responsibilities of the former employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="be16d-113">U kunt het archief ook herstellen vanuit een inactief postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-113">You can also restore the archive from an inactive mailbox.</span></span> <span data-ttu-id="be16d-114">Zie Een inactief postvak terugzetten in Office 365 voor de procedures [voor deze methode.](restore-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-114">For the procedures for this method, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

<span data-ttu-id="be16d-115">Zie de [sectie Meer](#more-information) informatie voor meer informatie over de verschillen tussen het herstellen en herstellen van een inactief postvak en voor een beschrijving van wat er gebeurt wanneer een inactief postvak wordt hersteld.</span><span class="sxs-lookup"><span data-stu-id="be16d-115">See the [More information](#more-information) section for more details about the differences between recovering and restoring an inactive mailbox, and for a description of what happens when an inactive mailbox is recovered.</span></span>

> [!NOTE]
> <span data-ttu-id="be16d-116">U kunt een inactief postvak dat is geconfigureerd met een automatisch uitbreidend archief, niet herstellen of herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-116">You can't recover or restore an inactive mailbox that's configured with an auto-expanding archive.</span></span> <span data-ttu-id="be16d-117">Als u gegevens wilt herstellen uit een inactief postvak met een automatisch uitbreidend archief, gebruikt u inhoud zoeken om de gegevens uit het postvak te exporteren en vervolgens te importeren in een ander postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-117">If you need to recover data from an inactive mailbox with an auto-expanding archive, use content search to export the data from the mailbox and then import to another mailbox.</span></span> <span data-ttu-id="be16d-118">Zie de volgende onderwerpen voor instructies:</span><span class="sxs-lookup"><span data-stu-id="be16d-118">For instructions, see following topics:</span></span>
>
> - [<span data-ttu-id="be16d-119">Inhoud zoeken</span><span class="sxs-lookup"><span data-stu-id="be16d-119">Content search</span></span>](content-search.md)
> - [<span data-ttu-id="be16d-120">Zoekresultaten voor inhoud exporteren</span><span class="sxs-lookup"><span data-stu-id="be16d-120">Export content search results</span></span>](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a><span data-ttu-id="be16d-121">Vereisten voor het herstellen van een inactief postvak</span><span class="sxs-lookup"><span data-stu-id="be16d-121">Requirements to recover an inactive mailbox</span></span>

- <span data-ttu-id="be16d-122">U moet powershell Exchange Online gebruiken om een inactief postvak te herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-122">You have to use Exchange Online PowerShell to recover an inactive mailbox.</span></span> <span data-ttu-id="be16d-123">U kunt het beheercentrum Exchange (EAC) niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="be16d-123">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="be16d-124">Zie voor stapsgewijs instructies de [Verbinding maken powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="be16d-124">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="be16d-125">Voer de volgende opdracht uit om identiteitsgegevens op te halen voor de inactieve postvakken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="be16d-125">Run the following command to get identity information for the inactive mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  <span data-ttu-id="be16d-126">Gebruik de gegevens die door deze opdracht worden geretourneerd om een specifiek inactief postvak te herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-126">Use the information returned by this command to recover a specific inactive mailbox.</span></span>

## <a name="recover-inactive-mailboxes"></a><span data-ttu-id="be16d-127">Inactieve postvakken herstellen</span><span class="sxs-lookup"><span data-stu-id="be16d-127">Recover inactive mailboxes</span></span>

<span data-ttu-id="be16d-128">Gebruik de **cmdlet Nieuw postvak** met de parameter  *InactiveMailbox*  om een inactief postvak te herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-128">Use the **New-Mailbox** cmdlet with the  *InactiveMailbox*  parameter to recover an inactive mailbox.</span></span>

1. <span data-ttu-id="be16d-129">Maak een variabele die de eigenschappen van het inactieve postvak bevat.</span><span class="sxs-lookup"><span data-stu-id="be16d-129">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="be16d-130">Gebruik in de vorige opdracht de waarde van de eigenschap **DistinguishedName** of **ExchangeGUID** om het inactieve postvak te identificeren.</span><span class="sxs-lookup"><span data-stu-id="be16d-130">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="be16d-131">Deze eigenschappen zijn uniek voor elk postvak in uw organisatie, terwijl het mogelijk is dat een actief en inactief postvak hetzelfde primaire SMTP-adres heeft.</span><span class="sxs-lookup"><span data-stu-id="be16d-131">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="be16d-132">In dit voorbeeld worden de eigenschappen gebruikt die zijn verkregen in de vorige opdracht en wordt het inactieve postvak hersteld naar een actief postvak voor de gebruiker Ann Beebe.</span><span class="sxs-lookup"><span data-stu-id="be16d-132">This example uses the properties obtained in the previous command and recovers the inactive mailbox to an active mailbox for the user Ann Beebe.</span></span> <span data-ttu-id="be16d-133">Zorg ervoor dat de waarden die zijn opgegeven voor de parameters  *Naam*  en  *MicrosoftOnlineServicesID*  uniek zijn binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="be16d-133">Be sure that the values specified for the  *Name*  and  *MicrosoftOnlineServicesID*  parameters are unique within your organization.</span></span>

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   <span data-ttu-id="be16d-134">Het primaire SMTP-adres voor het herstelde inactieve postvak heeft dezelfde waarde als het adres dat is opgegeven door de *parameter MicrosoftOnlineServicesID.*</span><span class="sxs-lookup"><span data-stu-id="be16d-134">The primary SMTP address for the recovered inactive mailbox will have the same value as the one specified by the  *MicrosoftOnlineServicesID*  parameter.</span></span>

<span data-ttu-id="be16d-135">Nadat u een inactief postvak hebt hersteld, wordt er ook een nieuw gebruikersaccount gemaakt.</span><span class="sxs-lookup"><span data-stu-id="be16d-135">After you recover an inactive mailbox, a new user account is also created.</span></span> <span data-ttu-id="be16d-136">U moet dit gebruikersaccount activeren door een licentie toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="be16d-136">You need to activate this user account by assigning a license.</span></span> <span data-ttu-id="be16d-137">Als u een licentie wilt toewijzen in Microsoft 365 beheercentrum, zie Gebruikers toevoegen en tegelijkertijd licenties [toewijzen.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-137">To assign a license in the Microsoft 365 admin center, see [Add users and assign licenses at the same time](../admin/add-users/add-users.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="be16d-138">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="be16d-138">More information</span></span>

- <span data-ttu-id="be16d-139">**Wat is het belangrijkste verschil tussen het herstellen en herstellen van een inactief postvak?**</span><span class="sxs-lookup"><span data-stu-id="be16d-139">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="be16d-140">Wanneer u een inactief postvak herstelt, wordt het postvak geconverteerd naar een nieuw postvak, blijven de inhoud en mapstructuur van het inactieve postvak behouden en is het postvak gekoppeld aan een nieuw gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="be16d-140">When you recover an inactive mailbox, the mailbox is converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="be16d-141">Nadat het is hersteld, bestaat het inactieve postvak niet meer en zijn wijzigingen in de inhoud in het nieuwe postvak van invloed op de inhoud die oorspronkelijk in de wacht stond in het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-141">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="be16d-142">Wanneer u een inactief postvak herstelt, wordt de inhoud echter alleen gekopieerd naar een ander postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-142">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="be16d-143">Het inactieve postvak blijft behouden en blijft een inactief postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-143">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="be16d-144">Wijzigingen in de inhoud in het doelpostvak hebben geen invloed op de oorspronkelijke inhoud in het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-144">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="be16d-145">Het inactieve postvak kan nog steeds worden doorzocht met In-Place eDiscovery, de inhoud ervan kan worden hersteld naar een ander postvak of op een later tijdstip worden hersteld of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be16d-145">The inactive mailbox can still be searched by using In-Place eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span>

- <span data-ttu-id="be16d-146">**Wat gebeurt er wanneer u een inactief postvak herstelt?**</span><span class="sxs-lookup"><span data-stu-id="be16d-146">**What happens when you recover an inactive mailbox?**</span></span> <span data-ttu-id="be16d-147">Wanneer u een inactief postvak herstelt, treden de volgende dingen op:</span><span class="sxs-lookup"><span data-stu-id="be16d-147">When you recover an inactive mailbox, the following things occur:</span></span>

  - <span data-ttu-id="be16d-148">De wacht die is toegepast op een inactief postvak wordt gewijzigd of verwijderd op basis van het type wacht die is toegepast op het inactieve postvak voordat het werd hersteld.</span><span class="sxs-lookup"><span data-stu-id="be16d-148">The hold that was applied to an inactive mailbox is changed or removed based on the type of hold that was applied to the inactive mailbox before it was recovered.</span></span>

    - <span data-ttu-id="be16d-149">**Procesvoering.**</span><span class="sxs-lookup"><span data-stu-id="be16d-149">**Litigation Hold.**</span></span> <span data-ttu-id="be16d-150">Als De procedure voor het inactief postvak is ingeschakeld, wordt het verwijderd uit het herstelde postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-150">If Litigation Hold was enabled for the inactive mailbox, it's removed from the recovered mailbox.</span></span>

    - <span data-ttu-id="be16d-151">**In-Place Hold In-Place** Holds worden verwijderd uit het herstelde postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-151">**In-Place Hold** In-Place Holds are removed from the recovered mailbox.</span></span> <span data-ttu-id="be16d-152">Dit betekent dat het herstelde postvak wordt verwijderd als een bronpostvak uit In-Place eDiscoveryIn-Place zoeken.</span><span class="sxs-lookup"><span data-stu-id="be16d-152">This means the recovered mailbox is removed as a source mailbox from any In-Place Hold or In-Place eDiscovery search.</span></span>

    - <span data-ttu-id="be16d-153">**Microsoft 365 bewaarbeleid met Bewaringsvergrendeling.**</span><span class="sxs-lookup"><span data-stu-id="be16d-153">**Microsoft 365 retention policy with Preservation Lock.**</span></span> <span data-ttu-id="be16d-154">Als het inactieve postvak is toegewezen aan een bewaarbeleid met Bewaringsvergrendeling (een vergrendeld bewaarbeleid *genoemd),* wordt het herstelde postvak toegewezen aan hetzelfde vergrendelde bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="be16d-154">If the inactive mailbox was assigned to a retention policy with Preservation Lock (called a *locked retention policy*), the recovered mailbox is assigned to the same locked retention policy.</span></span> <span data-ttu-id="be16d-155">Zie [ Bewaringsvergrendeling gebruiken om wijzigingen in bewaarbeleid en bewaarlabelbeleid te beperken voor meer informatie over vergrendeld[bewaarbeleid.](retention-preservation-lock.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-155">For more information about locked retention policies, see [[Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

    - <span data-ttu-id="be16d-156">**Microsoft 365 bewaarbeleid zonder Bewaringsvergrendeling.**</span><span class="sxs-lookup"><span data-stu-id="be16d-156">**Microsoft 365 retention policy without Preservation Lock.**</span></span> <span data-ttu-id="be16d-157">Het inactieve postvak wordt verwijderd uit een ontgrendeld Microsoft 365 bewaarbeleid dat erop is toegepast.</span><span class="sxs-lookup"><span data-stu-id="be16d-157">The inactive mailbox is removed from any unlocked Microsoft 365 retention policy that was applied to it.</span></span> <span data-ttu-id="be16d-158">De bewaring van rechtszaken is echter ingeschakeld in het herstelde postvak om te voorkomen dat postvakinhoud wordt verwijderd op basis van een organisatiebreed bewaarbeleid dat inhoud verwijdert die ouder is dan een bepaalde leeftijd.</span><span class="sxs-lookup"><span data-stu-id="be16d-158">However, Litigation Hold is enabled on the recovered mailbox to prevent the deletion of mailbox content based on any organization-wide retention policies that delete content older than a specific age.</span></span> <span data-ttu-id="be16d-159">U kunt de procedure in de wacht houden of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be16d-159">You can keep the Litigation Hold or remove it.</span></span> <span data-ttu-id="be16d-160">Zie Een proces in de wacht [houden voor meer informatie.](create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-160">For more information, see [Create a Litigation Hold](create-a-litigation-hold.md).</span></span>

  - <span data-ttu-id="be16d-161">De herstelperiode voor één item (die wordt gedefinieerd door de eigenschap **RetainDeletedItemsFor)** is ingesteld op 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="be16d-161">The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days.</span></span> <span data-ttu-id="be16d-162">Wanneer een nieuw postvak wordt gemaakt in Exchange Online, wordt deze bewaarperiode ingesteld op 14 dagen.</span><span class="sxs-lookup"><span data-stu-id="be16d-162">Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days.</span></span> <span data-ttu-id="be16d-163">Als u dit instelt op de maximumwaarde van 30 dagen, hebt u meer tijd om gegevens te herstellen die permanent zijn verwijderd (of verwijderd) uit het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-163">Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox.</span></span> <span data-ttu-id="be16d-164">U kunt ook het herstel van één item uitschakelen of de herstelperiode voor één item instellen op de standaardwaarde van 14 dagen.</span><span class="sxs-lookup"><span data-stu-id="be16d-164">You can also disable single item recovery or set the single item recovery period back to the default of 14 days.</span></span> <span data-ttu-id="be16d-165">Zie Herstel van één item voor een postvak in- [of uitschakelen voor meer informatie.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)</span><span class="sxs-lookup"><span data-stu-id="be16d-165">For more information, see [Enable or disable single item recovery for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).</span></span>

  - <span data-ttu-id="be16d-166">Bewaar bewaring is ingeschakeld en de duur van de bewaring is ingesteld op 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="be16d-166">Retention hold is enabled, and the retention hold duration is set to 30 days.</span></span> <span data-ttu-id="be16d-167">Dit betekent dat het standaard bewaarbeleid Exchange de hele organisatie en alle Exchange-brede Microsoft 365 bewaarbeleidsregels die aan het nieuwe postvak zijn toegewezen, niet worden verwerkt voor 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="be16d-167">This means that the default Exchange retention policy and any organization-wide or Exchange-wide Microsoft 365 retention policies that are assigned to the new mailbox won't be processed for 30 days.</span></span> <span data-ttu-id="be16d-168">Dit geeft de terugkerende werknemer of de nieuwe eigenaar van het herstelde inactieve postvak de tijd om de oude berichten te beheren.</span><span class="sxs-lookup"><span data-stu-id="be16d-168">This gives the returning employee or the new owner of the recovered inactive mailbox time to manage the old messages.</span></span> <span data-ttu-id="be16d-169">Anders worden in het Exchange- of Microsoft 365-bewaarbeleid mogelijk oude postvakitems verwijderd (of items naar het archiefpostvak verplaatst als dit is ingeschakeld) die zijn verlopen op basis van de instellingen die zijn geconfigureerd voor het bewaarbeleid van Exchange of Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be16d-169">Otherwise, the Exchange or Microsoft 365 retention policy might delete old mailbox items (or move items to the archive mailbox, if it's enabled) that have expired based on the settings configured for the Exchange or Microsoft 365 retention policies.</span></span> <span data-ttu-id="be16d-170">Na 30 dagen verloopt de bewaringstermijn, is de eigenschap **RetentionHoldEnabled** postvak ingesteld op Onwaar **en** begint de beheerde mapassistent met het verwerken van het beleid dat aan het postvak is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="be16d-170">After 30 days, the retention hold expires, the **RetentionHoldEnabled** mailbox property is set to **False**, and the Managed Folder Assistant starts processing the policies assigned to the mailbox.</span></span> <span data-ttu-id="be16d-171">Als u deze extra tijd niet nodig hebt, kunt u de bewaring gewoon verwijderen.</span><span class="sxs-lookup"><span data-stu-id="be16d-171">If you don't need this additional time, you can just remove the retention hold.</span></span> <span data-ttu-id="be16d-172">U kunt ook de duur van de bewaring verlengen met de opdracht **Set-Mailbox -EndDateForRetentionHold.**</span><span class="sxs-lookup"><span data-stu-id="be16d-172">Alternatively, you can increase the duration of the retention hold by using the **Set-Mailbox -EndDateForRetentionHold** command.</span></span> <span data-ttu-id="be16d-173">Zie Een postvak in bewaring [plaatsen voor meer informatie.](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)</span><span class="sxs-lookup"><span data-stu-id="be16d-173">For more information, see [Place a mailbox on retention hold](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).</span></span>

- <span data-ttu-id="be16d-174">**Houd het herstelde postvak in de wacht als u de oorspronkelijke status van het inactieve postvak wilt behouden.**</span><span class="sxs-lookup"><span data-stu-id="be16d-174">**Put a hold on the recovered mailbox if you need to preserve the original state of the inactive mailbox.**</span></span> <span data-ttu-id="be16d-175">Als u wilt voorkomen dat de nieuwe eigenaar van het postvak of het bewaarbeleid berichten definitief uit het herstelde inactieve postvak verwijderd, kunt u het postvak in bewaring plaatsen.</span><span class="sxs-lookup"><span data-stu-id="be16d-175">To prevent the new mailbox owner or retention policy from permanently deleting any messages from the recovered inactive mailbox, you can place the mailbox on Litigation Hold.</span></span> <span data-ttu-id="be16d-176">Zie Een proces in de wacht [houden voor meer informatie.](./create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-176">For more information, see [Create a Litigation Hold](./create-a-litigation-hold.md).</span></span>

- <span data-ttu-id="be16d-177">**Welke gebruikers-id kunt u gebruiken bij het herstellen van een inactief postvak?**</span><span class="sxs-lookup"><span data-stu-id="be16d-177">**What user ID can you use when recovering an inactive mailbox?**</span></span> <span data-ttu-id="be16d-178">Wanneer u een inactief postvak herstelt, kan de waarde die u opgeeft voor de  *parameter MicrosoftOnlineServicesID,*  verschillen van de oorspronkelijke waarde die is gekoppeld aan het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-178">When you recover an inactive mailbox, the value that you specify for the  *MicrosoftOnlineServicesID*  parameter can be different from the original one that was associated with the inactive mailbox.</span></span> <span data-ttu-id="be16d-179">U kunt ook de oorspronkelijke gebruikers-id gebruiken.</span><span class="sxs-lookup"><span data-stu-id="be16d-179">You can also use the original user ID.</span></span> <span data-ttu-id="be16d-180">Maar zoals eerder vermeld, moet u ervoor zorgen dat de waarden die worden gebruikt voor  *Naam*  en  *MicrosoftOnlineServicesID*  uniek zijn binnen uw organisatie wanneer u het inactieve postvak herstelt.</span><span class="sxs-lookup"><span data-stu-id="be16d-180">But as previously stated, make sure that the values used for  *Name*  and  *MicrosoftOnlineServicesID*  are unique within your organization when you recover the inactive mailbox.</span></span>

- <span data-ttu-id="be16d-181">**Wat gebeurt er als de bewaarperiode voor het postvak voor het inactieve postvak niet is verlopen?**</span><span class="sxs-lookup"><span data-stu-id="be16d-181">**What if the mailbox retention period for the inactive mailbox hasn't expired?**</span></span> <span data-ttu-id="be16d-182">Als een inactief postvak minder dan 30 dagen geleden is verwijderd, kunt u de opdracht **Nieuw-Postvak -InactiveMailbox** niet gebruiken om het te herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-182">If an inactive mailbox was soft-deleted less than 30 days ago, you can't use the **New-Mailbox -InactiveMailbox** command to recover it.</span></span> <span data-ttu-id="be16d-183">U moet het herstellen door het bijbehorende gebruikersaccount te herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-183">You need to recover it by restoring the corresponding user account.</span></span> <span data-ttu-id="be16d-184">Zie Een gebruiker uit uw organisatie [verwijderen voor meer informatie.](../admin/add-users/delete-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-184">For more information, see [Delete a user from your organization](../admin/add-users/delete-a-user.md).</span></span>

- <span data-ttu-id="be16d-185">**Hoe weet u of de bewaarperiode voor een postvak met een zacht verwijderd postvak voor een inactief postvak is verlopen?**</span><span class="sxs-lookup"><span data-stu-id="be16d-185">**How do you know if the soft-deleted mailbox retention period for an inactive mailbox has expired?**</span></span> <span data-ttu-id="be16d-186">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="be16d-186">Run the following command.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  <span data-ttu-id="be16d-187">Als er geen waarde is voor de eigenschap **ExternalDirectoryObjectId,** is de bewaarperiode van het postvak verlopen en kunt u het inactieve postvak herstellen door de opdracht **Nieuw-Postvak -InactiveMailbox** uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="be16d-187">If there isn't a value for the **ExternalDirectoryObjectId** property, the mailbox retention period has expired, and you can recover the inactive mailbox by running the **New-Mailbox -InactiveMailbox** command.</span></span> <span data-ttu-id="be16d-188">Als er een waarde is voor de eigenschap **ExternalDirectoryObjectId,** is de bewaarperiode van het postvak met een zachte verwijderde postvak niet verlopen en moet u het postvak herstellen door het gebruikersaccount te herstellen.</span><span class="sxs-lookup"><span data-stu-id="be16d-188">If there is a value for the **ExternalDirectoryObjectId** property, the soft-deleted mailbox retention period hasn't expired and you have to recover the mailbox by restoring the user account.</span></span> <span data-ttu-id="be16d-189">Zie [Een gebruiker uit uw organisatie verwijderen.](../admin/add-users/delete-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="be16d-189">See [Delete a user from your organization](../admin/add-users/delete-a-user.md).</span></span>

- <span data-ttu-id="be16d-190">**Overweeg het archiefpostvak in te stellen nadat u een inactief postvak hebt hersteld.**</span><span class="sxs-lookup"><span data-stu-id="be16d-190">**Consider enabling the archive mailbox after you recover an inactive mailbox.**</span></span> <span data-ttu-id="be16d-191">Hierdoor kan de terugkerende gebruiker of nieuwe werknemer oude berichten naar het archiefpostvak verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="be16d-191">This lets the returning user or new employee move old messages to the archive mailbox.</span></span> <span data-ttu-id="be16d-192">En wanneer de bewaring verloopt, worden items die twee jaar of ouder zijn, verplaatst met het archiefbeleid dat deel uitmaakt van het standaard bewaarbeleid Exchange dat is toegewezen aan Exchange Online-postvakken items die twee jaar of ouder zijn, naar het archiefpostvak.</span><span class="sxs-lookup"><span data-stu-id="be16d-192">And when the retention hold expires, the archive policy that is part of the default Exchange retention policy assigned to Exchange Online mailboxes will move items that are two years or older to the archive mailbox.</span></span> <span data-ttu-id="be16d-193">Als u het archiefpostvak niet inschakelen, blijven items ouder dan twee jaar in het primaire postvak van de gebruiker staan.</span><span class="sxs-lookup"><span data-stu-id="be16d-193">If you don't enable the archive mailbox, items older than two years will remain in the user's primary mailbox.</span></span> <span data-ttu-id="be16d-194">Zie Archiefpostvakken [inschakelen voor](enable-archive-mailboxes.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="be16d-194">For more information, see [Enable archive mailboxes](enable-archive-mailboxes.md).</span></span>