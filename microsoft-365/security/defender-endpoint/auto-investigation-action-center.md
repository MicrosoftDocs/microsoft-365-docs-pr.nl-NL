---
title: Ga naar het Actiecentrum om herstelacties te zien
description: Het actiecentrum gebruiken om details en resultaten weer te geven na een geautomatiseerd onderzoek
keywords: actie, centreren, autoir, geautomatiseerd, onderzoek, antwoord, herstel
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844908"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="05743-104">Ga naar het Actiecentrum om herstelacties te zien</span><span class="sxs-lookup"><span data-stu-id="05743-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="05743-105">Tijdens en na een geautomatiseerd onderzoek worden herstelacties voor bedreigingsdetecties geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="05743-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="05743-106">Afhankelijk van de specifieke bedreiging en de configuratie van [Microsoft Defender voor](/windows/security/threat-protection) Eindpunt voor uw organisatie, worden sommige herstelacties automatisch genomen en moeten andere worden goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="05743-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="05743-107">Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u in behandeling zijnde en voltooide herstelacties bekijken [in](manage-auto-investigation.md#remediation-actions) het **Actiecentrum.**</span><span class="sxs-lookup"><span data-stu-id="05743-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="05743-108">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="05743-108">**Applies to:**</span></span>
- [<span data-ttu-id="05743-109">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="05743-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05743-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05743-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="05743-111">(NIEUW!) Een geïntegreerd actiecentrum</span><span class="sxs-lookup"><span data-stu-id="05743-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="05743-112">We zijn blij om een nieuw, geïntegreerd actiecentrum aan te kondigen ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!</span><span class="sxs-lookup"><span data-stu-id="05743-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Actiecentrum in Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="05743-114">In de volgende tabel wordt het nieuwe, geïntegreerde actiecentrum vergeleken met het vorige Actiecentrum.</span><span class="sxs-lookup"><span data-stu-id="05743-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="05743-115">Het nieuwe, geïntegreerde actiecentrum</span><span class="sxs-lookup"><span data-stu-id="05743-115">The new, unified Action center</span></span>  |<span data-ttu-id="05743-116">Het vorige actiecentrum</span><span class="sxs-lookup"><span data-stu-id="05743-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="05743-117">Lijsten in behandeling en voltooide acties voor apparaten en e-mail op één locatie</span><span class="sxs-lookup"><span data-stu-id="05743-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="05743-118">([Microsoft Defender voor Eindpunt](microsoft-defender-endpoint.md) plus Microsoft Defender voor [Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="05743-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="05743-119">Lijsten in behandeling en voltooide acties voor apparaten</span><span class="sxs-lookup"><span data-stu-id="05743-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="05743-120">([Alleen Microsoft Defender voor eindpunt)](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="05743-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="05743-121">Bevindt zich op:</span><span class="sxs-lookup"><span data-stu-id="05743-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="05743-122">Bevindt zich op:</span><span class="sxs-lookup"><span data-stu-id="05743-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="05743-123">Kies in Microsoft 365 beveiligingscentrum de optie **Actiecentrum.**</span><span class="sxs-lookup"><span data-stu-id="05743-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigeren naar het Actiecentrum in het Microsoft 365 beveiligingscentrum"::: | <span data-ttu-id="05743-125">Kies in Microsoft Defender-beveiligingscentrum **Actiecentrum Voor automatische onderzoeken.**  >  </span><span class="sxs-lookup"><span data-stu-id="05743-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigeren naar het actiecentrum vanaf het Microsoft Defender-beveiligingscentrum":::  |

<span data-ttu-id="05743-127">Het geïntegreerde Actiecentrum brengt herstelacties samen in Defender voor Eindpunt en Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="05743-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="05743-128">Het definieert een gemeenschappelijke taal voor alle herstelacties en biedt een geïntegreerde onderzoekservaring.</span><span class="sxs-lookup"><span data-stu-id="05743-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="05743-129">U kunt het geïntegreerde actiecentrum gebruiken als u de juiste machtigingen en een of meer van de volgende abonnementen hebt:</span><span class="sxs-lookup"><span data-stu-id="05743-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="05743-130">Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="05743-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="05743-131">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="05743-131">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="05743-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05743-132">Microsoft 365 Defender</span></span>](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="05743-133">Zie Vereisten voor meer [informatie.](/microsoft-365/security/mtp/prerequisites)</span><span class="sxs-lookup"><span data-stu-id="05743-133">To learn more, see [Requirements](/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="05743-134">Het actiecentrum gebruiken</span><span class="sxs-lookup"><span data-stu-id="05743-134">Using the Action center</span></span>

<span data-ttu-id="05743-135">Ga als eerste naar het geïntegreerde Actiecentrum in het verbeterde Microsoft 365 beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="05743-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="05743-136">Ga naar het Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="05743-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="05743-137">Selecteer actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="05743-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="05743-138">Wanneer u het Actiecentrum bezoekt, ziet u twee tabbladen: **Acties in behandeling** en **Geschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="05743-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="05743-139">De volgende tabel bevat een overzicht van wat u op elk tabblad ziet:</span><span class="sxs-lookup"><span data-stu-id="05743-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="05743-140">Tab</span><span class="sxs-lookup"><span data-stu-id="05743-140">Tab</span></span>  |<span data-ttu-id="05743-141">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="05743-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="05743-142">**In behandeling**</span><span class="sxs-lookup"><span data-stu-id="05743-142">**Pending**</span></span>     | <span data-ttu-id="05743-143">Hiermee wordt een lijst weergegeven met acties die aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="05743-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="05743-144">U kunt acties één voor één goedkeuren of weigeren of meerdere acties selecteren als ze hetzelfde type actie hebben (zoals **Quarantainebestand).**</span><span class="sxs-lookup"><span data-stu-id="05743-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="05743-145">**TIP:** Controleer en keur in behandeling zijnde acties zo snel mogelijk goed [(of weiger)](manage-auto-investigation.md) zodat uw geautomatiseerde onderzoeken tijdig kunnen worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="05743-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="05743-146">**Geschiedenis**</span><span class="sxs-lookup"><span data-stu-id="05743-146">**History**</span></span>     | <span data-ttu-id="05743-147">Fungeert als een auditlogboek voor acties die zijn uitgevoerd, zoals:</span><span class="sxs-lookup"><span data-stu-id="05743-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="05743-148">- Herstelacties die zijn ondernomen als gevolg van geautomatiseerde onderzoeken</span><span class="sxs-lookup"><span data-stu-id="05743-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="05743-149">- Herstelacties die zijn goedgekeurd door uw beveiligingsteam</span><span class="sxs-lookup"><span data-stu-id="05743-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="05743-150">- Opdrachten die zijn uitgevoerd en herstelacties die zijn toegepast tijdens livereactiesessies</span><span class="sxs-lookup"><span data-stu-id="05743-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="05743-151">- Herstelacties die zijn ondernomen door functies voor bedreigingsbeveiliging in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="05743-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="05743-152">Biedt een manier om bepaalde acties ongedaan te maken (zie [Voltooide acties ongedaan maken).](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="05743-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="05743-153">U kunt gegevens aanpassen, sorteren, filteren en exporteren in het Actiecentrum.</span><span class="sxs-lookup"><span data-stu-id="05743-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Kolommen en filters in het actiecentrum":::

- <span data-ttu-id="05743-155">Selecteer een kolomkoppen om items in oplopende of aflopende volgorde te sorteren.</span><span class="sxs-lookup"><span data-stu-id="05743-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="05743-156">Gebruik het tijdsperiodefilter om gegevens voor de afgelopen dag, week, 30 dagen of 6 maanden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="05743-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="05743-157">Kies de kolommen die u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="05743-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="05743-158">Geef op hoeveel items u wilt opnemen op elke pagina met gegevens.</span><span class="sxs-lookup"><span data-stu-id="05743-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="05743-159">Gebruik filters om alleen de items te bekijken die u wilt zien.</span><span class="sxs-lookup"><span data-stu-id="05743-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="05743-160">Selecteer **Exporteren** om resultaten te exporteren naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="05743-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="05743-161">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="05743-161">Next steps</span></span>

- [<span data-ttu-id="05743-162">Herstelacties bekijken en goedkeuren</span><span class="sxs-lookup"><span data-stu-id="05743-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="05743-163">Zie de interactieve handleiding: Bedreigingen onderzoeken en corrigeren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="05743-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="05743-164">Zie ook</span><span class="sxs-lookup"><span data-stu-id="05743-164">See also</span></span>

- [<span data-ttu-id="05743-165">Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="05743-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
