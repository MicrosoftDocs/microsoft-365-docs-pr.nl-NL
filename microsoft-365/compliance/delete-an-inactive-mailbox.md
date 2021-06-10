---
title: Een inactief postvak verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Wanneer u de inhoud van een inactief postvak niet meer Microsoft 365, kunt u het inactieve postvak definitief verwijderen.
ms.openlocfilehash: 077a71bfdd82721e0992e5d14073aa037b7cfd1b
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162864"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="9a31f-103">Een inactief postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="9a31f-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="9a31f-104">Een inactief postvak wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat deze uw organisatie heeft verlaten.</span><span class="sxs-lookup"><span data-stu-id="9a31f-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="9a31f-105">Als u de inhoud van een inactief postvak niet meer wilt behouden, kunt u het inactieve postvak definitief verwijderen door de wacht te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="9a31f-106">Het is ook mogelijk dat meerdere postvakken in een inactief postvak worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="9a31f-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="9a31f-107">Een inactief postvak kan bijvoorbeeld worden geplaatst in de wacht voor rechtszaken en op een of meer In-Place In- In-Place.</span><span class="sxs-lookup"><span data-stu-id="9a31f-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="9a31f-108">Daarnaast kan een bewaarbeleid (gemaakt in het beveiligings- en compliancecentrum in Office 365 of Microsoft 365) worden toegepast op het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="9a31f-109">U moet alle bewaarbeleidsregels uit een inactief postvak verwijderen om het te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="9a31f-110">Nadat u het bewaarbeleid hebt verwijderd, wordt het inactieve postvak gemarkeerd voor verwijdering en definitief verwijderd nadat het is verwerkt.</span><span class="sxs-lookup"><span data-stu-id="9a31f-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a31f-111">Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9a31f-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="9a31f-112">Dit betekent dat u beleidsregels voor bewaring en bewaring van rechtszaken moet gebruiken om een inactief postvak te maken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="9a31f-113">Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9a31f-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="9a31f-114">Maar u kunt de duur van de wachttijd van een In-Place in een inactief postvak wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="9a31f-115">Vanaf 1 oktober 2020 kunt u de duur van de wachttijd echter niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="9a31f-116">U kunt alleen een inactief postvak verwijderen door de In-Place verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="9a31f-117">Bestaande inactieve postvakken die in de wacht In-Place blijven behouden totdat de wacht wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9a31f-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="9a31f-118">Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="9a31f-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="9a31f-119">Zie de [sectie Meer informatie](#more-information) voor een beschrijving van wat er gebeurt nadat een postvak is verwijderd uit een inactief postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="9a31f-120">Voordat u een inactief postvak verwijdert</span><span class="sxs-lookup"><span data-stu-id="9a31f-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="9a31f-121">U moet powershell Exchange Online gebruiken om een geschil in een inactief postvak te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="9a31f-122">U kunt het beheercentrum Exchange (EAC) niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="9a31f-123">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="9a31f-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9a31f-124">U kunt de inhoud van een inactief postvak naar een ander postvak kopiëren voordat u de wacht houdt en een inactief postvak verwijdert.</span><span class="sxs-lookup"><span data-stu-id="9a31f-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="9a31f-125">Zie Een [inactief postvak terugzetten in](restore-an-inactive-mailbox.md)Office 365 voor meer Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a31f-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="9a31f-126">Als u het bewaar- of bewaringsbeleid uit een inactief postvak verwijdert en de bewaarperiode voor het postvak is verlopen, wordt het postvak definitief verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9a31f-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="9a31f-127">Nadat het is verwijderd, kan het niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="9a31f-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="9a31f-128">Voordat u de wacht houdt, moet u ervoor zorgen dat u de inhoud in het postvak niet meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="9a31f-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="9a31f-129">Als u een inactief postvak opnieuw wilt activeren, kunt u het herstellen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="9a31f-130">Zie Een [inactief postvak herstellen in](recover-an-inactive-mailbox.md)Office 365 voor meer Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a31f-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="9a31f-131">Zie Inactieve postvakken in Office 365 voor meer informatie over inactieve [postvakken.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9a31f-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="9a31f-132">Stap 1: De inboxen in een inactief postvak identificeren</span><span class="sxs-lookup"><span data-stu-id="9a31f-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="9a31f-133">Zoals eerder vermeld, kan een beleid voor In-Place bewaring, bewaring of bewaring in een inactief postvak worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="9a31f-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="9a31f-134">De eerste stap is het identificeren van de ophoudt in een inactief postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="9a31f-135">Voer de volgende opdracht uit om de wachtgegevens weer te geven voor alle inactieve postvakken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9a31f-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="9a31f-136">De waarde van **Waar** voor de **eigenschap LitigationHoldEnabled** geeft aan dat het inactieve postvak zich in de procesvaste procedure houdt.</span><span class="sxs-lookup"><span data-stu-id="9a31f-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="9a31f-137">Als een In-Place in een inactief postvak wordt geplaatst, wordt de GUID voor de hold weergegeven als de waarde voor de eigenschap **InPlaceHolds.**</span><span class="sxs-lookup"><span data-stu-id="9a31f-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="9a31f-138">Uit de volgende resultaten voor twee inactieve postvakken blijkt bijvoorbeeld dat er een procedurele bewaring wordt geplaatst op Ann Beebe en dat er een In-Place Bewaringsbeleid wordt geplaatst op Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="9a31f-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="9a31f-139">Als een groot aantal In-Place bewaarbeleid in een inactief postvak wordt geplaatst, worden niet alle In-Place Guids voor bewaring weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9a31f-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="9a31f-140">U kunt de volgende opdracht uitvoeren om alle GUID's weer te geven in de eigenschap InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="9a31f-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="9a31f-141">Zie Het type wacht in een postvak identificeren voor meer informatie over het identificeren van [wachtvakken.](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="9a31f-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="9a31f-142">Stap 2: Een greep uit een inactief postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="9a31f-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="9a31f-143">Nadat u hebt bepaald welk type wacht in het inactieve postvak wordt geplaatst (en of er meerdere wachtvakken zijn), is de volgende stap het verwijderen van de wacht in het postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="9a31f-144">Zoals eerder vermeld, moet u alle in- en uitvakken verwijderen om een inactief postvak definitief te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="9a31f-145">Een geschil in de wacht zetten verwijderen</span><span class="sxs-lookup"><span data-stu-id="9a31f-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="9a31f-146">Zoals eerder is aangegeven, moet u een Windows PowerShell om een geschil in een inactief postvak te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="9a31f-147">U kunt het EAC niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-147">You can't use the EAC.</span></span> <span data-ttu-id="9a31f-148">Voer de volgende opdracht uit om een proces in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="9a31f-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="9a31f-149">De beste manier om een inactief postvak te identificeren, is door de distinguished name of Exchange GUID-waarde te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="9a31f-150">Als u een van deze waarden gebruikt, voorkomt u dat per ongeluk het verkeerde postvak wordt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="9a31f-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="9a31f-151">Een inactief postvak verwijderen uit een bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="9a31f-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="9a31f-152">De procedure voor het verwijderen van een inactief postvak uit een Microsoft 365 bewaarbeleid is afhankelijk van of het bewaarbeleid dat aan het inactieve postvak is toegewezen, organisatiebreed of expliciet is.</span><span class="sxs-lookup"><span data-stu-id="9a31f-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="9a31f-153">over het type bewaarbeleid dat is toegewezen aan het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="9a31f-154">Bewaarbeleid voor de hele organisatie dat is toegewezen aan alle postvakken in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="9a31f-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="9a31f-155">Gebruik de **Get-OrganizationConfig-cmdlet** in Exchange Online PowerShell voor informatie over bewaarbeleid voor de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="9a31f-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="9a31f-156">Specifiek beleid voor het bewaren van locaties dat is toegewezen aan specifieke postvakken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="9a31f-157">Dit zijn beleidsregels die zijn toegewezen aan de inhoudslocaties van specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9a31f-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="9a31f-158">Gebruik de **cmdlet Get-Mailbox -IncludeInactiveMailbox** in Exchange Online PowerShell voor informatie over bewaarbeleid dat is toegewezen aan specifieke inactieve postvakken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="9a31f-159">Een inactief postvak verwijderen uit een bewaarbeleid voor de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="9a31f-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="9a31f-160">Voer de volgende opdracht uit in Exchange Online PowerShell om een inactief postvak uit te sluiten van een bewaarbeleid voor de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="9a31f-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="9a31f-161">Zie de sectie 'Get-OrganizationConfig' in How to identify the type of hold placed on a mailbox (Get-OrganizationConfig) in How to identify the type of hold placed on a mailbox (Get-OrganizationConfig) (Get-OrganizationConfig) in How to identify the type of hold placed [on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)(Get-OrganizationConfig) (Get-OrganizationConfig) voor meer informatie over het bepalen van het bewaarbeleid voor een inactief postvak en het verkrijgen van de GUID voor een bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="9a31f-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="9a31f-162">U kunt ook de volgende opdracht uitvoeren om het inactieve postvak te verwijderen uit alle beleidsregels voor de hele organisatie:</span><span class="sxs-lookup"><span data-stu-id="9a31f-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="9a31f-163">Een inactief postvak verwijderen uit een specifiek bewaarbeleid voor locaties</span><span class="sxs-lookup"><span data-stu-id="9a31f-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="9a31f-164">Voer de volgende opdracht uit in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) om een inactief postvak te verwijderen uit een expliciet bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="9a31f-164">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="9a31f-165">Zie de sectie Postvak IN in Het [type](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)bewaring dat in een postvak is geplaatst voor meer informatie over het specifieke beleid voor het bewaren van locaties dat is toegepast op een inactief postvak en het verkrijgen van de GUID voor een bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="9a31f-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="9a31f-166">Houd In-Place verwijderen</span><span class="sxs-lookup"><span data-stu-id="9a31f-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="9a31f-167">Er zijn twee manieren om een In-Place uit een inactief postvak te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="9a31f-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="9a31f-168">**Verwijder het In-Place Hold-object**.</span><span class="sxs-lookup"><span data-stu-id="9a31f-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="9a31f-169">Als het inactieve postvak dat u permanent wilt verwijderen, het enige bronpostvak is voor een In-Place-wacht, kunt u het In-Place Object in wacht houden.</span><span class="sxs-lookup"><span data-stu-id="9a31f-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9a31f-170">U moet de wacht houden uitschakelen voordat u een object In-Place verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-170">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="9a31f-171">Als u probeert een object In-Place hold te verwijderen waarin de wacht is ingeschakeld, ontvangt u een foutbericht.</span><span class="sxs-lookup"><span data-stu-id="9a31f-171">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="9a31f-172">**Verwijder het inactieve postvak als bronpostvak van een In-Place Wacht.**</span><span class="sxs-lookup"><span data-stu-id="9a31f-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="9a31f-173">Als u andere bronpostvakken wilt behouden voor een In-Place Hold, kunt u het inactieve postvak verwijderen uit de lijst met bronpostvakken en het object In-Place behouden.</span><span class="sxs-lookup"><span data-stu-id="9a31f-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="9a31f-174">Een wacht In-Place verwijderen</span><span class="sxs-lookup"><span data-stu-id="9a31f-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="9a31f-175">Maak een variabele met de eigenschappen van de In-Place Hold die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-175">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="9a31f-176">Gebruik de In-Place GUID in de wacht houden die u hebt verkregen in stap 1: Identificeer de wacht in [een inactief postvak.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="9a31f-176">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="9a31f-177">De wacht op de In-Place uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="9a31f-178">Verwijder de In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="9a31f-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="9a31f-179">Een inactief postvak uit een In-Place verwijderen</span><span class="sxs-lookup"><span data-stu-id="9a31f-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="9a31f-180">Als de In-Place een groot aantal bronpostvakken bevat, is het mogelijk dat het inactieve postvak niet wordt weergegeven op de pagina Bronnen in het EAC. </span><span class="sxs-lookup"><span data-stu-id="9a31f-180">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="9a31f-181">Er worden maximaal 3000 postvakken weergegeven  op de pagina Bronnen wanneer u een In-Place bewerken.</span><span class="sxs-lookup"><span data-stu-id="9a31f-181">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="9a31f-182">Als een inactief postvak niet wordt  weergegeven op de pagina Bronnen, kunt u Exchange Online PowerShell gebruiken om het uit de In-Place verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-182">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="9a31f-183">Maak een variabele met de eigenschappen van de In-Place in het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-183">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="9a31f-184">Gebruik de In-Place GUID in de wacht houden die u hebt verkregen in stap 1: Identificeer de wacht in [een inactief postvak.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="9a31f-184">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="9a31f-185">Controleer of het inactieve postvak wordt weergegeven als een bronpostvak voor de In-Place Inactief.</span><span class="sxs-lookup"><span data-stu-id="9a31f-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="9a31f-186">De *eigenschap* Bronnen van de In-Place Hold identificeert de bronpostvakken aan de hand van de *eigenschappen van LegacyExchangeDN.*</span><span class="sxs-lookup"><span data-stu-id="9a31f-186">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="9a31f-187">Omdat met deze eigenschap unieke inactieve postvakken worden geïdentificeerd, voorkomt u het verwijderen van het verkeerde postvak met de eigenschap Bronnen uit de In-Place Hold. </span><span class="sxs-lookup"><span data-stu-id="9a31f-187">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="9a31f-188">Dit helpt ook om problemen te voorkomen als twee postvakken dezelfde alias of SMTP-adres hebben.</span><span class="sxs-lookup"><span data-stu-id="9a31f-188">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="9a31f-189">Verwijder het inactieve postvak uit de lijst met bronpostvakken in de variabele.</span><span class="sxs-lookup"><span data-stu-id="9a31f-189">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="9a31f-190">Gebruik de **LegacyExchangeDN** van het inactieve postvak dat wordt geretourneerd door de opdracht in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="9a31f-190">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="9a31f-191">Met de volgende opdracht wordt bijvoorbeeld het inactieve postvak voor Pilar Pinilla verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9a31f-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="9a31f-192">Controleer of het inactieve postvak is verwijderd uit de lijst met bronpostvakken in de variabele.</span><span class="sxs-lookup"><span data-stu-id="9a31f-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="9a31f-193">Wijzig de In-Place De wacht houden met de bijgewerkte lijst met bronpostvakken, die niet het inactieve postvak bevat.</span><span class="sxs-lookup"><span data-stu-id="9a31f-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="9a31f-194">Controleer of het inactieve postvak is verwijderd uit de lijst met bronpostvakken voor de In-Place in de wacht.</span><span class="sxs-lookup"><span data-stu-id="9a31f-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="9a31f-195">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="9a31f-195">More information</span></span>

- <span data-ttu-id="9a31f-196">**Een inactief postvak is een type postvak dat wordt verwijderd.**</span><span class="sxs-lookup"><span data-stu-id="9a31f-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="9a31f-197">In Exchange Online is een zacht verwijderd postvak een postvak dat is verwijderd, maar binnen een specifieke bewaarperiode kan worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="9a31f-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="9a31f-198">Een eerder inactief postvak is 183 dagen beschikbaar als een zacht verwijderd postvak in Exchange Online 183 dagen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-198">A previously inactive mailbox will be available as a soft-deleted mailbox in Exchange Online for 183 days.</span></span> <span data-ttu-id="9a31f-199">Dit betekent dat het postvak binnen 183 dagen na de soft-deleted kan worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="9a31f-199">This means that the mailbox can be recovered within 183 days of being soft-deleted.</span></span> <span data-ttu-id="9a31f-200">Na 183 dagen wordt een zacht verwijderd postvak gemarkeerd voor permanent verwijderen en kan het niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="9a31f-200">After 183 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="9a31f-201">**Wat gebeurt er nadat u de wacht op een inactief postvak hebt verwijderd?**</span><span class="sxs-lookup"><span data-stu-id="9a31f-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="9a31f-202">Het postvak wordt behandeld als andere zacht verwijderde postvakken en is gemarkeerd voor permanente verwijdering nadat de bewaarperiode van het 183 dagen verwijderde postvak is verlopen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 183-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="9a31f-203">Deze bewaarperiode begint op de datum waarop het postvak voor het eerst inactief is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9a31f-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="9a31f-204">Deze datum wordt de zacht verwijderde datum genoemd, de datum waarop het bijbehorende gebruikersaccount is verwijderd of wanneer het **Exchange Online-postvak** is verwijderd met de cmdlet Postvak verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9a31f-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="9a31f-205">De zacht verwijderde datum is niet de datum waarop u de wacht houdt.</span><span class="sxs-lookup"><span data-stu-id="9a31f-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="9a31f-206">**Wordt een inactief postvak permanent verwijderd direct nadat de wacht is verwijderd?**</span><span class="sxs-lookup"><span data-stu-id="9a31f-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="9a31f-207">Een voorheen inactief postvak is 183 dagen beschikbaar in de status van de soft-verwijderde postvak.</span><span class="sxs-lookup"><span data-stu-id="9a31f-207">A formerly inactive mailbox will be available in the soft-deleted state for 183 days.</span></span> <span data-ttu-id="9a31f-208">Na 183 dagen wordt het postvak gemarkeerd voor permanente verwijdering.</span><span class="sxs-lookup"><span data-stu-id="9a31f-208">After 183 days the mailbox will be marked for permanent deletion.</span></span>

- <span data-ttu-id="9a31f-209">**Hoe geeft u informatie weer over een inactief postvak nadat de wacht is verwijderd?**</span><span class="sxs-lookup"><span data-stu-id="9a31f-209">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="9a31f-210">Nadat een greep is verwijderd en het inactieve postvak weer wordt teruggevormd naar een zacht verwijderd postvak, wordt  het niet geretourneerd met de parameter *InactiveMailboxOnly* met de cmdlet Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="9a31f-210">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="9a31f-211">U kunt echter wel informatie over het postvak weergeven met de opdracht **Postvak -SoftDeletedMailbox.**</span><span class="sxs-lookup"><span data-stu-id="9a31f-211">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="9a31f-212">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9a31f-212">For example:</span></span>

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  <span data-ttu-id="9a31f-213">In het bovenstaande voorbeeld geeft de *eigenschap WhenSoftDeleted* de datum aan die in dit voorbeeld 16 juni 2020 is.</span><span class="sxs-lookup"><span data-stu-id="9a31f-213">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is June 16, 2020.</span></span> <span data-ttu-id="9a31f-214">De *eigenschap WasInactiveMailbox* wordt weergegeven als omdat het eerder een `True` inactief postvak was.</span><span class="sxs-lookup"><span data-stu-id="9a31f-214">The *WasInactiveMailbox* property is listed as `True` because it was previously an inactive mailbox.</span></span> <span data-ttu-id="9a31f-215">Het postvak wordt 183 dagen na 30 september 2020 definitief verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9a31f-215">The mailbox will be permanently deleted 183 days after September 30, 2020.</span></span>

