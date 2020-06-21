---
title: Distributielijsten upgraden naar Microsoft 365-groepen in Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Meer informatie over het upgraden van een of meerdere distributielijsten naar Microsoft 365-groepen in Outlook en hoe u PowerShell gebruiken om meerdere distributielijsten tegelijk te upgraden.
ms.openlocfilehash: f5748c293d18943c94c3610c0e3c5c33848eb521
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780023"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="cdb43-103">Distributielijsten upgraden naar Microsoft 365-groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="cdb43-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="cdb43-104">U distributielijsten upgraden naar Microsoft 365-groepen met Outlook.</span><span class="sxs-lookup"><span data-stu-id="cdb43-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="cdb43-105">Dit is een geweldige manier om de distributielijsten van uw organisatie alle functies en functionaliteit van Microsoft 365-groepen te geven.</span><span class="sxs-lookup"><span data-stu-id="cdb43-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="cdb43-106">Waarom u een upgrade voor uw distributielijsten moet uitvoeren naar groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="cdb43-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="cdb43-107">U kunt distributielijsten een voor een of allemaal tegelijk upgraden.</span><span class="sxs-lookup"><span data-stu-id="cdb43-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="cdb43-108">Een of meer distributielijsten upgraden naar Microsoft 365-groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="cdb43-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="cdb43-109">U moet een globale beheerder of Exchange-beheerder zijn om een distributielijst te upgraden.</span><span class="sxs-lookup"><span data-stu-id="cdb43-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="cdb43-110">Als u wilt upgraden naar Microsoft 365-groepen, moet een distributiegroep een eigenaar met een postvak hebben.</span><span class="sxs-lookup"><span data-stu-id="cdb43-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="cdb43-111">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="cdb43-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="cdb43-112">Ga in het Exchange-beheercentrum naar **Groepen ontvangers** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="cdb43-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="cdb43-113">U ziet een bericht waarin wordt aangegeven dat u distributielijsten hebt (ook wel **distributiegroepen** genoemd) die in aanmerking komen voor een upgrade naar Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="cdb43-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="cdb43-114">![De knop Aan de slag selecteren](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="cdb43-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="cdb43-115">Selecteer een of meer distributielijsten (ook wel een **distributiegroep** genoemd) op de pagina **groepen**.</span><span class="sxs-lookup"><span data-stu-id="cdb43-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="cdb43-116">![Een distributiegroep selecteren](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="cdb43-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="cdb43-117">Selecteer het upgradepictogram.</span><span class="sxs-lookup"><span data-stu-id="cdb43-117">Select the upgrade icon.</span></span><br/>![Upgraden naar pictogram Microsoft 365-groepen](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="cdb43-119">Selecteer in het **informatiedialoogvenster Ja** om de upgrade te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="cdb43-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="cdb43-120">Het proces begint onmiddellijk.</span><span class="sxs-lookup"><span data-stu-id="cdb43-120">The process begins immediately.</span></span> <span data-ttu-id="cdb43-121">Afhankelijk van de grootte en het aantal DLs dat u upgradet, kan het proces minuten of uren duren.</span><span class="sxs-lookup"><span data-stu-id="cdb43-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="cdb43-122">Als de distributielijst niet kan worden geüpgraded, wordt er een dialoogvenster geopend waarin dit wordt aangegeven.</span><span class="sxs-lookup"><span data-stu-id="cdb43-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="cdb43-123">Zie [Welke distributielijsten niet kunnen worden geüpgraded?](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="cdb43-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="cdb43-124">Als u meerdere distributielijsten upgradet, gebruikt u de vervolgkeuzelijst om te filteren welke distributielijsten zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cdb43-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="cdb43-125">Als de lijst niet is voltooid, wacht u nog even en selecteert u **Vernieuwen** om te zien wat er is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cdb43-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="cdb43-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span><span class="sxs-lookup"><span data-stu-id="cdb43-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="cdb43-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span><span class="sxs-lookup"><span data-stu-id="cdb43-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="cdb43-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span><span class="sxs-lookup"><span data-stu-id="cdb43-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="cdb43-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="cdb43-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="cdb43-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span><span class="sxs-lookup"><span data-stu-id="cdb43-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="cdb43-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span><span class="sxs-lookup"><span data-stu-id="cdb43-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="cdb43-132">Wat u moet doen als de upgrade niet werkt</span><span class="sxs-lookup"><span data-stu-id="cdb43-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="cdb43-133">Distributielijsten die niet kunnen worden geüpgraded, blijven ongewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cdb43-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="cdb43-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="cdb43-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="cdb43-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span><span class="sxs-lookup"><span data-stu-id="cdb43-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="cdb43-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span><span class="sxs-lookup"><span data-stu-id="cdb43-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="cdb43-137">If you want, wait a while and then try to upgrade the DL again.</span><span class="sxs-lookup"><span data-stu-id="cdb43-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="cdb43-138">PowerShell gebruiken om diverse distributielijsten tegelijkertijd te upgraden</span><span class="sxs-lookup"><span data-stu-id="cdb43-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="cdb43-139">Als u een ervaren PowerShell-gebruiker bent, wilt u misschien PowerShell in plaats van de gebruikersinterface gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cdb43-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="cdb43-140">We hebben een set cmdlets die u zullen helpen bij het upgraden van distributielijsten.</span><span class="sxs-lookup"><span data-stu-id="cdb43-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="cdb43-141">Zie hieronder.</span><span class="sxs-lookup"><span data-stu-id="cdb43-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="cdb43-142">Eén DL upgraden</span><span class="sxs-lookup"><span data-stu-id="cdb43-142">Upgrade a single DL</span></span>

<span data-ttu-id="cdb43-143">Als u één DL wilt upgraden, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="cdb43-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="cdb43-144">Als u bijvoorbeeld een DL's wilt upgraden met dl1@contoso.com SMTP-adres, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="cdb43-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="cdb43-145">U ook één distributielijst upgraden naar een Microsoft 365-groep met de [PowerShell-cmdlet New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)</span><span class="sxs-lookup"><span data-stu-id="cdb43-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="cdb43-146">Meerdere DLs in een batch upgraden</span><span class="sxs-lookup"><span data-stu-id="cdb43-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="cdb43-147">U ook meerdere DLs als batch doorgeven en samen upgraden:</span><span class="sxs-lookup"><span data-stu-id="cdb43-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="cdb43-148">Als u bijvoorbeeld vijf DLs wilt upgraden met smtp-adres `dl1@contoso.com` en de volgende opdracht wilt uitvoeren en de volgende opdracht wilt `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="cdb43-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="cdb43-149">Alle in aanmerking komende DLs upgraden</span><span class="sxs-lookup"><span data-stu-id="cdb43-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="cdb43-150">Er zijn twee manieren waarop u alle in aanmerking komende DLs upgraden.</span><span class="sxs-lookup"><span data-stu-id="cdb43-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="cdb43-151">De cmdlet Upgrade-DistributionGroup ontvangt geen gegevens uit de pijplijn, daarom is het nodig om de operator 'foreach-object' te gebruiken {} om succesvol uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cdb43-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="cdb43-152">Haal de in aanmerking komende DLs in de tenant en upgrade ze met de upgradeopdracht:</span><span class="sxs-lookup"><span data-stu-id="cdb43-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="cdb43-153">Download de lijst met alle DL's en upgrade alleen de in aanmerking komende DLs:</span><span class="sxs-lookup"><span data-stu-id="cdb43-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="cdb43-154">Veelgestelde vragen over het upgraden van distributielijsten naar Microsoft 365-groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="cdb43-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="cdb43-155">Welke distributielijsten kunnen niet worden geüpgraded?</span><span class="sxs-lookup"><span data-stu-id="cdb43-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="cdb43-156">U kunt alleen in de cloud beheerde, eenvoudige, niet-geneste distributielijsten upgraden.</span><span class="sxs-lookup"><span data-stu-id="cdb43-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="cdb43-157">In de onderstaande tabel worden distributielijsten weergegeven die **NIET kunnen** worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cdb43-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="cdb43-158">**Eigenschap**</span><span class="sxs-lookup"><span data-stu-id="cdb43-158">**Property**</span></span>|<span data-ttu-id="cdb43-159">**Komt in aanmerking?**</span><span class="sxs-lookup"><span data-stu-id="cdb43-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cdb43-160">On-premises beheerde distributielijst.</span><span class="sxs-lookup"><span data-stu-id="cdb43-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="cdb43-161">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-161">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-162">Nested distribution lists.</span><span class="sxs-lookup"><span data-stu-id="cdb43-162">Nested distribution lists.</span></span> <span data-ttu-id="cdb43-163">Distribution list either has child groups or is a member of another group.</span><span class="sxs-lookup"><span data-stu-id="cdb43-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="cdb43-164">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-164">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-165">Distributielijsten met lid **RecipientTypeDetails,** met uitzondering **van UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="cdb43-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="cdb43-166">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-166">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-167">Distributielijst met meer dan 100 eigenaren</span><span class="sxs-lookup"><span data-stu-id="cdb43-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="cdb43-168">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-168">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-169">Distributielijst met alleen leden, maar geen eigenaar</span><span class="sxs-lookup"><span data-stu-id="cdb43-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="cdb43-170">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-170">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-171">Distributielijst met een alias met speciale tekens</span><span class="sxs-lookup"><span data-stu-id="cdb43-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="cdb43-172">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-172">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-173">Als de distributielijst als een doorstuuradres voor Gedeeld postvak is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="cdb43-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="cdb43-174">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-174">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-175">Als de DL deel uitmaakt van **Sender Restriction** in een andere DL.</span><span class="sxs-lookup"><span data-stu-id="cdb43-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="cdb43-176">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-176">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-177">Beveiligingsgroepen</span><span class="sxs-lookup"><span data-stu-id="cdb43-177">Security groups</span></span>  <br/> |<span data-ttu-id="cdb43-178">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-178">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-179">Dynamische distributielijsten</span><span class="sxs-lookup"><span data-stu-id="cdb43-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="cdb43-180">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-180">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-181">Distributielijsten die zijn geconverteerd naar **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="cdb43-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="cdb43-182">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-182">No</span></span>  <br/> |
|<span data-ttu-id="cdb43-183">Distributielijsten waarin **MemberJoinRestriction** en/of **MemberDepartRestriction** **gesloten** zijn</span><span class="sxs-lookup"><span data-stu-id="cdb43-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="cdb43-184">Nee</span><span class="sxs-lookup"><span data-stu-id="cdb43-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="cdb43-185">Hoe controleer ik welke DLs in aanmerking komen voor een upgrade?</span><span class="sxs-lookup"><span data-stu-id="cdb43-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="cdb43-186">Als u wilt controleren of een DL in aanmerking komt of niet, u de onderstaande opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="cdb43-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="cdb43-187">Als u wilt controleren welke DLs in aanmerking komen voor een upgrade, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="cdb43-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="cdb43-188">Wie kan de upgradescripts uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="cdb43-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="cdb43-189">Mensen met algemene beheerders- of Exchange-beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="cdb43-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="cdb43-190">Waarom wordt op het visitekaartje nog steeds een distributielijst weergegeven?</span><span class="sxs-lookup"><span data-stu-id="cdb43-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="cdb43-191">Wat moet ik doen om te voorkomen dat een geüpgradede distributielijst wordt weergegeven in mijn lijst met automatische suggesties?</span><span class="sxs-lookup"><span data-stu-id="cdb43-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="cdb43-192">Voor Outlook: Wanneer iemand een e-mail probeert te verzenden in Outlook door de naam van de Microsoft 365-groep na migratie te typen, wordt de ontvanger opgelost als de distributielijst in plaats van de groep.</span><span class="sxs-lookup"><span data-stu-id="cdb43-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="cdb43-193">Het visitekaartje van de geadresseerde wordt het visitekaartje van de distributielijsten.</span><span class="sxs-lookup"><span data-stu-id="cdb43-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="cdb43-194">Dit wordt veroorzaakt door de cache met geadresseerden of de cache met bijnamen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="cdb43-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="cdb43-195">De e-mail wordt met succes naar de groep verzonden, maar kan verwarring veroorzaken bij de afzender.</span><span class="sxs-lookup"><span data-stu-id="cdb43-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="cdb43-196">U kunt aan de hand van de stappen in het onderwerp [Informatie over de lijst AutoAanvullen in Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) de cache opnieuw instellen om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="cdb43-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="cdb43-197">Voor de webversie van Outlook: In het geval van de webversie van Outlook blijft de ontvanger van de distributielijst nog steeds in de cache.</span><span class="sxs-lookup"><span data-stu-id="cdb43-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="cdb43-198">U de stappen in [De voorgestelde naam of het e-mailadres verwijderen uit de lijst Automatisch aanvullen](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) volgen om de cache te vernieuwen om het groepscontactkaart te bekijken.</span><span class="sxs-lookup"><span data-stu-id="cdb43-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="cdb43-199">Krijgen nieuwe groepsleden een welkomstbericht in hun postvak IN?</span><span class="sxs-lookup"><span data-stu-id="cdb43-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="cdb43-200">No.</span><span class="sxs-lookup"><span data-stu-id="cdb43-200">No.</span></span> <span data-ttu-id="cdb43-201">The setting to enable welcome messages is set to false by default.</span><span class="sxs-lookup"><span data-stu-id="cdb43-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="cdb43-202">This setting affects both existing and new group members who may join after the migration is complete.</span><span class="sxs-lookup"><span data-stu-id="cdb43-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="cdb43-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span><span class="sxs-lookup"><span data-stu-id="cdb43-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="cdb43-204">Guest members can continue working with the group.</span><span class="sxs-lookup"><span data-stu-id="cdb43-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="cdb43-205">Wat als een of meer van de DLs niet worden geüpgraded?</span><span class="sxs-lookup"><span data-stu-id="cdb43-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="cdb43-206">Er zijn enkele gevallen waarin DL wel in aanmerking komt, maar niet kan worden geüpgraded.</span><span class="sxs-lookup"><span data-stu-id="cdb43-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="cdb43-207">De DL krijgt geen upgrade en blijft als een DL.</span><span class="sxs-lookup"><span data-stu-id="cdb43-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="cdb43-208">Wanneer de beheerder **het groepse-adresbeleid** voor de groepen in een organisatie heeft toegepast en ze dls proberen te upgraden die niet aan de criteria voldoen, wordt de DL niet geüpgraded</span><span class="sxs-lookup"><span data-stu-id="cdb43-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="cdb43-209">DL's met **MemberJoinRestriction** of **MemberDepartRestriction** ingesteld op **Gesloten**, kan niet worden opgewaardeerd</span><span class="sxs-lookup"><span data-stu-id="cdb43-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="cdb43-210">Wat gebeurt er met de distributielijst als de upgrade vanuit het Exchange-beheercentrum mislukt?</span><span class="sxs-lookup"><span data-stu-id="cdb43-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="cdb43-211">The upgrade will happen only when the call is submitted to the server.</span><span class="sxs-lookup"><span data-stu-id="cdb43-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="cdb43-212">If the upgrade fails, your DLs will be intact.</span><span class="sxs-lookup"><span data-stu-id="cdb43-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="cdb43-213">They will work like they used to.</span><span class="sxs-lookup"><span data-stu-id="cdb43-213">They will work like they used to.</span></span>


