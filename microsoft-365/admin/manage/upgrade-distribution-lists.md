---
title: Distributielijsten upgraden naar Microsoft 365 Groepen in Outlook
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
description: Lees hoe u een of meer distributielijsten kunt upgraden naar Microsoft 365 Groepen in Outlook en hoe u PowerShell kunt gebruiken om meerdere distributielijsten tegelijk te upgraden.
ms.openlocfilehash: 7fd6090e00e9099feb93685a276b5e207bd05419
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915000"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="5a9a8-103">Distributielijsten upgraden naar Microsoft 365 Groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="5a9a8-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="5a9a8-104">U kunt distributielijsten upgraden naar Microsoft 365 Groepen met Outlook.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="5a9a8-105">Dit is een geweldige manier om de distributielijsten van uw organisatie te voorzien van alle functies en functionaliteit van Microsoft 365 Groepen.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="5a9a8-106">Waarom u uw distributielijsten moet upgraden naar groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="5a9a8-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="5a9a8-107">U kunt distributielijsten een voor een of allemaal tegelijk upgraden.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="5a9a8-108">Een of meer distributielijsten upgraden naar Microsoft 365 Groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="5a9a8-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="5a9a8-109">U moet een globale beheerder of Exchange-beheerder zijn om een distributielijst te upgraden.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="5a9a8-110">Als u een upgrade wilt uitvoeren naar Microsoft 365 Groepen, moet een distributiegroep een eigenaar met een postvak hebben.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="5a9a8-111">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="5a9a8-112">Ga in het Exchange-beheercentrum naar **Geadresseerdengroepen.** \> </span><span class="sxs-lookup"><span data-stu-id="5a9a8-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="5a9a8-113">U ziet een melding dat u distributielijsten (ook wel distributiegroepen **genoemd)** hebt die in aanmerking komen voor een upgrade naar Microsoft 365 Groepen.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="5a9a8-114">![Selecteer de knop Aan de slag](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="5a9a8-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="5a9a8-115">Selecteer een of meer distributielijsten (ook wel een **distributiegroep** genoemd) op de pagina **groepen**.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="5a9a8-116">![Een distributiegroep selecteren](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="5a9a8-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="5a9a8-117">Selecteer het upgradepictogram.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-117">Select the upgrade icon.</span></span><br/>![Pictogram Upgraden naar Microsoft 365 Groepen](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="5a9a8-119">Selecteer ja in het dialoogvenster Informatie **om** de upgrade te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="5a9a8-120">Het proces begint onmiddellijk.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-120">The process begins immediately.</span></span> <span data-ttu-id="5a9a8-121">Afhankelijk van de grootte en het aantal DL's dat u aan het upgraden bent, kan het proces minuten of uren duren.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="5a9a8-122">Als de distributielijst niet kan worden geüpgraded, wordt er een dialoogvenster geopend waarin dit wordt aangegeven.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="5a9a8-123">Zie [Welke distributielijsten kunnen niet worden bijgewerkt?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="5a9a8-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="5a9a8-124">Als u meerdere distributielijsten bij wilt werken, gebruikt u de vervolgkeuzelijst om te filteren welke distributielijsten zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="5a9a8-125">Als de lijst niet is voltooid, wacht  u nog even en selecteert u Vernieuwen om te zien wat er is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="5a9a8-p106">Er wordt niet gemeld wanneer het upgradeproces is voltooid voor alle distributielijsten die u hebt geselecteerd. U kunt dit zien door te bekijken wat wordt weergegeven onder **Beschikbaar voor upgrade** of **Upgraded DLs** (Geüpgradede distributielijsten).</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="5a9a8-p107">Als u een distributielijst voor upgraden hebt geselecteerd maar deze nog steeds wordt weergegeven op de pagina als Beschikbaar voor upgrade, is het upgraden van de distributielijst mislukt. Zie [Wat u moet doen als de upgrade niet werkt](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="5a9a8-p108">Als u samenvattings-e-mails van de groep ontvangt, wordt er soms onderaan vermeld dat u distributielijsten waarvan u eigenaar bent, kunt upgraden. Zie [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) (Een groepsgesprek hebben in Outlook) voor meer informatie over samenvattings-e-mails.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="5a9a8-132">Wat u moet doen als de upgrade niet werkt</span><span class="sxs-lookup"><span data-stu-id="5a9a8-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="5a9a8-133">Distributielijsten die niet kunnen worden geüpgraded, blijven ongewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="5a9a8-p109">Als een of meer **in aanmerking komende** distributielijsten niet kunnen worden geüpgraded, opent u een [ondersteuningsticket](../contact-support-for-business-products.md). Het probleem moet worden geëscaleerd naar het team Groups Engineering zodat zij kunnen uitzoeken wat het probleem is.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="5a9a8-p110">Het is mogelijk dat de distributielijst niet is geüpgraded vanwege een serviceonderbreking, maar dit is tamelijk onwaarschijnlijk. U kunt ook even wachten en vervolgens opnieuw proberen de distributielijst te upgraden.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="5a9a8-138">PowerShell gebruiken om diverse distributielijsten tegelijkertijd te upgraden</span><span class="sxs-lookup"><span data-stu-id="5a9a8-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="5a9a8-139">Als u een ervaren PowerShell-gebruiker bent, wilt u misschien PowerShell in plaats van de gebruikersinterface gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="5a9a8-140">We hebben een set cmdlets die u helpen bij het upgraden van distributielijsten.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="5a9a8-141">Zie hieronder.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="5a9a8-142">Eén DL upgraden</span><span class="sxs-lookup"><span data-stu-id="5a9a8-142">Upgrade a single DL</span></span>

<span data-ttu-id="5a9a8-143">Voer de volgende opdracht uit om één DL te upgraden:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="5a9a8-144">Als u bijvoorbeeld een upgrade wilt uitvoeren van een DL met SMTP-adres dl1@contoso.com, voer dan de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="5a9a8-145">U kunt ook één distributielijst upgraden naar een Microsoft 365-groep met de [PowerShell-cmdlet New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup)</span><span class="sxs-lookup"><span data-stu-id="5a9a8-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="5a9a8-146">Meerdere DL's in een batch upgraden</span><span class="sxs-lookup"><span data-stu-id="5a9a8-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="5a9a8-147">U kunt ook meerdere DL's als batch doorgeven en samen upgraden:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="5a9a8-148">Als u bijvoorbeeld vijf DL's wilt upgraden met SMTP-adres `dl1@contoso.com` en de volgende opdracht wilt `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="5a9a8-149">Alle in aanmerking komende DL's upgraden</span><span class="sxs-lookup"><span data-stu-id="5a9a8-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="5a9a8-150">Er zijn twee manieren waarop u alle in aanmerking komende DL's kunt upgraden.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="5a9a8-151">De Upgrade-DistributionGroup-cmdlet ontvangt geen gegevens uit de pijplijn, om deze reden is het vereist dat de operator 'foreach-object' wordt gebruikt om deze uit {} te voeren.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="5a9a8-152">Haal de in aanmerking komende DL's in de tenant op en upgrade ze met de opdracht Upgrade:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="5a9a8-153">De lijst met alle DL's en alleen de in aanmerking komende DL's upgraden:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="5a9a8-154">Veelgestelde vragen over het upgraden van distributielijsten naar Microsoft 365 Groepen in Outlook</span><span class="sxs-lookup"><span data-stu-id="5a9a8-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="5a9a8-155">Welke distributielijsten kunnen niet worden bijgewerkt?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="5a9a8-156">U kunt alleen in de cloud beheerde, eenvoudige, niet-geneste distributielijsten upgraden.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="5a9a8-157">In de onderstaande tabel worden distributielijsten weergegeven die **NIET kunnen** worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="5a9a8-158">**Eigenschap**</span><span class="sxs-lookup"><span data-stu-id="5a9a8-158">**Property**</span></span>|<span data-ttu-id="5a9a8-159">**Komt in aanmerking?**</span><span class="sxs-lookup"><span data-stu-id="5a9a8-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a9a8-160">On-premises beheerde distributielijst.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="5a9a8-161">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-161">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-p113">Geneste distributielijsten De distributielijst heeft onderliggende groepen of is lid van een andere groep.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="5a9a8-164">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-164">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-165">Distributielijsten met leden **RecipientTypeDetails** andere dan **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="5a9a8-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="5a9a8-166">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-166">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-167">Distributielijst met meer dan 100 eigenaren</span><span class="sxs-lookup"><span data-stu-id="5a9a8-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="5a9a8-168">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-168">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-169">Distributielijst met alleen leden, maar geen eigenaar</span><span class="sxs-lookup"><span data-stu-id="5a9a8-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="5a9a8-170">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-170">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-171">Distributielijst met een alias met speciale tekens</span><span class="sxs-lookup"><span data-stu-id="5a9a8-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="5a9a8-172">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-172">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-173">Als de distributielijst als een doorstuuradres voor Gedeeld postvak is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="5a9a8-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="5a9a8-174">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-174">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-175">Als de DL deel uitmaakt van **Sender Restriction** in een andere DL.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="5a9a8-176">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-176">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-177">Beveiligingsgroepen</span><span class="sxs-lookup"><span data-stu-id="5a9a8-177">Security groups</span></span>  <br/> |<span data-ttu-id="5a9a8-178">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-178">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-179">Dynamische distributielijsten</span><span class="sxs-lookup"><span data-stu-id="5a9a8-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="5a9a8-180">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-180">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-181">Distributielijsten die zijn geconverteerd **naar RoomLists**</span><span class="sxs-lookup"><span data-stu-id="5a9a8-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="5a9a8-182">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-182">No</span></span>  <br/> |
|<span data-ttu-id="5a9a8-183">Distributielijsten **waarin MemberJoinRestriction** en/of **MemberDepartRestriction** is **gesloten**</span><span class="sxs-lookup"><span data-stu-id="5a9a8-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="5a9a8-184">Nee</span><span class="sxs-lookup"><span data-stu-id="5a9a8-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="5a9a8-185">Controleren welke DL's in aanmerking komen voor een upgrade</span><span class="sxs-lookup"><span data-stu-id="5a9a8-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="5a9a8-186">Als u wilt controleren of een DL al dan niet in aanmerking komt, kunt u de onderstaande opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="5a9a8-187">Als u wilt controleren welke DL's in aanmerking komen voor een upgrade, voer dan de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5a9a8-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="5a9a8-188">Wie kan de upgradescripts uitvoeren?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="5a9a8-189">Personen met globale beheerders- of Exchange-beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="5a9a8-190">Waarom wordt op het visitekaartje nog steeds een distributielijst weergegeven?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="5a9a8-191">Wat moet ik doen om te voorkomen dat een geüpgradede distributielijst wordt weergegeven in mijn lijst met automatische suggesties?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="5a9a8-192">Voor Outlook: Wanneer iemand een e-mail probeert te verzenden in Outlook door de naam van de Microsoft 365-groep na de migratie te typen, wordt de geadresseerde opgelost als de distributielijst in plaats van de groep.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="5a9a8-193">Het visitekaartje van de geadresseerde wordt het visitekaartje van de distributielijsten.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="5a9a8-194">Dit wordt veroorzaakt door de cache met geadresseerden of de cache met bijnamen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="5a9a8-195">De e-mail wordt naar de groep verzonden, maar kan verwarring veroorzaken bij de afzender.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="5a9a8-196">U kunt aan de hand van de stappen in het onderwerp [Informatie over de lijst AutoAanvullen in Outlook](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) de cache opnieuw instellen om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="5a9a8-197">Voor de webversie van Outlook: in het geval van de webversie van Outlook blijft de ontvanger van de distributielijst in de cache.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="5a9a8-198">U kunt de stappen in Voorgestelde naam of [e-mailadres](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) verwijderen uit de lijst Automatisch voltooien volgen om de cache te vernieuwen om het groepscontactkaart te zien.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="5a9a8-199">Krijgen nieuwe groepsleden een welkomstbericht in hun postvak IN?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="5a9a8-p117">Nee. De instelling voor het inschakelen van welkomstberichten is standaard ingesteld op onwaar. Deze instelling geldt voor zowel bestaande als nieuwe groepsleden die kunnen deelnemen nadat de migratie is voltooid. Als de groepseigenaar later gastgebruikers toestaat, ontvangen gastgebruikers geen welkomstbericht in hun postvak IN. Gastleden kunnen het werken met de groep voortzetten.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="5a9a8-205">Wat gebeurt er als een of meer van de DL's niet worden bijgewerkt?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="5a9a8-206">Er zijn enkele gevallen waarin DL wel in aanmerking komt, maar niet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="5a9a8-207">De DL wordt niet bijgewerkt en blijft een DL.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="5a9a8-208">Waar de  beheerder groepsbeleid voor e-mailadres heeft toegepast voor de groepen in een organisatie en ze proberen DL's te upgraden die niet aan de criteria voldoen, wordt de DL niet bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="5a9a8-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="5a9a8-209">DLs met **MemberJoinRestriction** **of MemberDepartRestriction set** to **Closed**, could not be upgraded</span><span class="sxs-lookup"><span data-stu-id="5a9a8-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="5a9a8-210">Wat gebeurt er met de distributielijst als de upgrade vanuit het Exchange-beheercentrum mislukt?</span><span class="sxs-lookup"><span data-stu-id="5a9a8-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="5a9a8-p119">De upgrade vindt alleen plaats als de oproep naar de server wordt verzonden. Als de upgrade mislukt, worden de distributielijsten niet gewijzigd. Ze blijven op dezelfde manier werken.</span><span class="sxs-lookup"><span data-stu-id="5a9a8-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>