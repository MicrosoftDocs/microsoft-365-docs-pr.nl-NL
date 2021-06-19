---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Bekijk de resultaten en belangrijkste bevindingen van geautomatiseerd onderzoek in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, herstel, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9ee2f0402e8cfd184e59dce5a382f835b706d6aa
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022547"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="d5183-104">Details en resultaten van een geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="d5183-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d5183-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d5183-105">**Applies to:**</span></span>
- <span data-ttu-id="d5183-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5183-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d5183-107">Wanneer Microsoft 365 Defender een geautomatiseerd [](m365d-autoir.md) onderzoek wordt uitgevoerd, zijn details over dat onderzoek beschikbaar, zowel tijdens als na het geautomatiseerde onderzoeksproces.</span><span class="sxs-lookup"><span data-stu-id="d5183-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="d5183-108">Als u de [benodigde machtigingen hebt,](m365d-action-center.md#required-permissions-for-action-center-tasks)kunt u deze details bekijken in een weergave met onderzoeksdetails.</span><span class="sxs-lookup"><span data-stu-id="d5183-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="d5183-109">Deze weergave biedt u de actuele status en de mogelijkheid om eventuele in behandeling zijnde acties goed te keuren.</span><span class="sxs-lookup"><span data-stu-id="d5183-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Details van het onderzoek":::

## <a name="new-unified-investigation-page"></a><span data-ttu-id="d5183-111">(NIEUW!) Geïntegreerde onderzoekspagina</span><span class="sxs-lookup"><span data-stu-id="d5183-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="d5183-112">De onderzoekspagina is onlangs bijgewerkt met informatie op uw apparaten, e-mail en samenwerkingsinhoud.</span><span class="sxs-lookup"><span data-stu-id="d5183-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="d5183-113">De nieuwe, geïntegreerde onderzoekspagina definieert een gemeenschappelijke taal en biedt een geïntegreerde ervaring voor automatische onderzoeken in [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor Eindpunt en Microsoft Defender [voor Office 365.](../office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d5183-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="d5183-114">Als u toegang wilt tot de geïntegreerde onderzoekspagina, selecteert u de koppeling in de gele banner die u ziet op:</span><span class="sxs-lookup"><span data-stu-id="d5183-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="d5183-115">Een onderzoekspagina in het Office 365 Beveiligings- & Compliancecentrum ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="d5183-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="d5183-116">Een onderzoekspagina in de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="d5183-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="d5183-117">Elk incident of actiecentrum in de Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="d5183-117">Any incident or Action center experience in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="d5183-118">De weergave onderzoeksdetails openen</span><span class="sxs-lookup"><span data-stu-id="d5183-118">Open the investigation details view</span></span>

<span data-ttu-id="d5183-119">U kunt de weergave onderzoeksdetails openen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="d5183-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="d5183-120">Een item selecteren in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="d5183-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="d5183-121">Een onderzoek selecteren op een pagina met details van incidenten</span><span class="sxs-lookup"><span data-stu-id="d5183-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="d5183-122">Een item selecteren in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="d5183-122">Select an item in the Action center</span></span>

<span data-ttu-id="d5183-123">Het verbeterde [Actiecentrum](m365d-action-center.md) () brengt herstelacties samen op uw [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) apparaten, e-mail & samenwerkingsinhoud en identiteiten. [](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="d5183-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="d5183-124">In de lijst opgenomen acties zijn herstelacties die automatisch of handmatig zijn genomen.</span><span class="sxs-lookup"><span data-stu-id="d5183-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="d5183-125">In het Actiecentrum kunt u acties bekijken die wachten op goedkeuring en acties die al zijn goedgekeurd of voltooid.</span><span class="sxs-lookup"><span data-stu-id="d5183-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="d5183-126">U kunt ook naar meer details navigeren, zoals een onderzoekspagina.</span><span class="sxs-lookup"><span data-stu-id="d5183-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="d5183-127">U moet bepaalde [machtigingen hebben om](m365d-action-center.md#required-permissions-for-action-center-tasks) acties goed te keuren, te weigeren of ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="d5183-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="d5183-128">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="d5183-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="d5183-129">Kies actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="d5183-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="d5183-130">Selecteer een item **op het** **tabblad** In behandeling of Geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="d5183-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="d5183-131">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="d5183-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="d5183-132">Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d5183-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="d5183-133">Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="d5183-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="d5183-134">Selecteer **Goedkeuren om** een actie in behandeling te starten.</span><span class="sxs-lookup"><span data-stu-id="d5183-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="d5183-135">Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.</span><span class="sxs-lookup"><span data-stu-id="d5183-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="d5183-136">Selecteer **Ga op zoek om** naar Geavanceerd zoeken te [gaan.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d5183-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="d5183-137">Een onderzoek openen vanaf een pagina met incidentgegevens</span><span class="sxs-lookup"><span data-stu-id="d5183-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="d5183-138">Gebruik een pagina met incidentdetails om gedetailleerde informatie over een incident weer te geven, inclusief waarschuwingen die zijn geactiveerde informatie over getroffen apparaten, gebruikersaccounts of postvakken.</span><span class="sxs-lookup"><span data-stu-id="d5183-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="d5183-139">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="d5183-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="d5183-140">Kies in het navigatiedeelvenster de optie **Incidenten & waarschuwingen**  >  **Incidenten**.</span><span class="sxs-lookup"><span data-stu-id="d5183-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="d5183-141">Selecteer een item in de lijst en kies vervolgens **Incidentpagina openen.**</span><span class="sxs-lookup"><span data-stu-id="d5183-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="d5183-142">Selecteer het **tabblad Onderzoeken** en selecteer vervolgens een onderzoek in de lijst.</span><span class="sxs-lookup"><span data-stu-id="d5183-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="d5183-143">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="d5183-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="d5183-144">Selecteer **Onderzoekspagina openen.**</span><span class="sxs-lookup"><span data-stu-id="d5183-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="d5183-145">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5183-145">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Details van incidenten":::

## <a name="investigation-details"></a><span data-ttu-id="d5183-147">Details van het onderzoek</span><span class="sxs-lookup"><span data-stu-id="d5183-147">Investigation details</span></span>

<span data-ttu-id="d5183-148">Gebruik de weergave onderzoeksdetails om eerdere, huidige en in behandeling zijnde activiteiten met betrekking tot een onderzoek te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d5183-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="d5183-149">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5183-149">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Details van het onderzoek":::

<span data-ttu-id="d5183-151">In de weergave Details van onderzoek kunt u informatie zien op de tabbladen **Onderzoek**,  **Waarschuwingen**, Apparaten , **Identiteiten**, **Belangrijke** bevindingen **,** Entiteiten , **Logboek** en Acties in behandeling , beschreven in de volgende tabel. </span><span class="sxs-lookup"><span data-stu-id="d5183-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="d5183-152">De specifieke tabbladen die u op een pagina met onderzoeksdetails ziet, zijn afhankelijk van wat uw abonnement bevat.</span><span class="sxs-lookup"><span data-stu-id="d5183-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="d5183-153">Als uw abonnement bijvoorbeeld geen Microsoft Defender bevat voor Office 365 abonnement 2, ziet u geen tabblad **Postvakken.**</span><span class="sxs-lookup"><span data-stu-id="d5183-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="d5183-154">Tab</span><span class="sxs-lookup"><span data-stu-id="d5183-154">Tab</span></span> | <span data-ttu-id="d5183-155">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d5183-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="d5183-156">**Onderzoeksgrafiek**</span><span class="sxs-lookup"><span data-stu-id="d5183-156">**Investigation graph**</span></span>   | <span data-ttu-id="d5183-157">Geeft een visuele weergave van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="d5183-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="d5183-158">Hiermee worden entiteiten en lijsten weergegeven die zijn gevonden, samen met waarschuwingen en of er nog acties moeten worden goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="d5183-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="d5183-159">U kunt een item in de grafiek selecteren om meer details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d5183-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="d5183-160">Als u bijvoorbeeld het pictogram **Bewijs** selecteert, gaat u naar het tabblad Bewijs, waar u gedetecteerde entiteiten en hun vonnissen kunt zien. </span><span class="sxs-lookup"><span data-stu-id="d5183-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="d5183-161">**Waarschuwingen**</span><span class="sxs-lookup"><span data-stu-id="d5183-161">**Alerts**</span></span>    | <span data-ttu-id="d5183-162">Hiermee worden waarschuwingen vermeld die aan het onderzoek zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d5183-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="d5183-163">Waarschuwingen kunnen afkomstig zijn van functies voor bedreigingsbeveiliging op het apparaat van een gebruiker, in Office apps, Microsoft Cloud App Security en andere Microsoft 365 Defender functies.</span><span class="sxs-lookup"><span data-stu-id="d5183-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="d5183-164">**Apparaten**</span><span class="sxs-lookup"><span data-stu-id="d5183-164">**Devices**</span></span> | <span data-ttu-id="d5183-165">Hiermee worden apparaten vermeld die zijn opgenomen in het onderzoek, samen met het herstelniveau.</span><span class="sxs-lookup"><span data-stu-id="d5183-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="d5183-166">(Herstelniveaus komen overeen met het [automatiseringsniveau voor apparaatgroepen](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span><span class="sxs-lookup"><span data-stu-id="d5183-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="d5183-167">**Postvakken**</span><span class="sxs-lookup"><span data-stu-id="d5183-167">**Mailboxes**</span></span> |<span data-ttu-id="d5183-168">Hiermee worden postvakken vermeld die worden beïnvloed door gedetecteerde bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d5183-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="d5183-169">**Gebruikers**</span><span class="sxs-lookup"><span data-stu-id="d5183-169">**Users**</span></span>  | <span data-ttu-id="d5183-170">Hiermee worden gebruikersaccounts vermeld die worden beïnvloed door gedetecteerde bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d5183-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="d5183-171">**Bewijs**</span><span class="sxs-lookup"><span data-stu-id="d5183-171">**Evidence**</span></span> | <span data-ttu-id="d5183-172">Hier worden stukken bewijs vermeld die door waarschuwingen of onderzoeken worden opgesmeld.</span><span class="sxs-lookup"><span data-stu-id="d5183-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="d5183-173">Bevat vonnissen *(Schadelijke,* *Verdachte,* *Onbekende* of *Geen gevonden* bedreigingen) en herstelstatus.</span><span class="sxs-lookup"><span data-stu-id="d5183-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="d5183-174">**Entiteiten**</span><span class="sxs-lookup"><span data-stu-id="d5183-174">**Entities**</span></span>  | <span data-ttu-id="d5183-175">Bevat details over elke geanalyseerde entiteit, inclusief een uitspraak voor elk entiteitstype *(Schadelijk,* *Verdacht* of Geen *gevonden bedreigingen).*</span><span class="sxs-lookup"><span data-stu-id="d5183-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="d5183-176">**Logboek**</span><span class="sxs-lookup"><span data-stu-id="d5183-176">**Log**</span></span>    | <span data-ttu-id="d5183-177">Geeft een chronologische, gedetailleerde weergave van alle onderzoekacties die zijn ondernomen nadat een waarschuwing is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d5183-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="d5183-178">**Geschiedenis van acties in behandeling**</span><span class="sxs-lookup"><span data-stu-id="d5183-178">**Pending actions history**</span></span> | <span data-ttu-id="d5183-179">Hiermee worden items vermeld waarvoor goedkeuring is vereist.</span><span class="sxs-lookup"><span data-stu-id="d5183-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="d5183-180">Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () om acties in behandeling goed te keuren.</span><span class="sxs-lookup"><span data-stu-id="d5183-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="d5183-181">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="d5183-181">Next steps</span></span>

- [<span data-ttu-id="d5183-182">Herstelacties bekijken en goedkeuren</span><span class="sxs-lookup"><span data-stu-id="d5183-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="d5183-183">Meer informatie over herstelacties</span><span class="sxs-lookup"><span data-stu-id="d5183-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
