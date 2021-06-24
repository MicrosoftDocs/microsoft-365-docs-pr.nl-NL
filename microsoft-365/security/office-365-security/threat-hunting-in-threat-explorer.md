---
title: Bedreigingsjacht in Threat Explorer voor Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gebruik Threat Explorer of realtime detecties in de Microsoft 365 Defender portal om bedreigingen efficiënt te onderzoeken en te beantwoorden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ad5d73abae71cc7cc00e12665d96b2020da0c41
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105427"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="31b1a-103">Bedreigingsjacht in Threat Explorer voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="31b1a-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="31b1a-104">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="31b1a-104">In this article:</span></span>

- [<span data-ttu-id="31b1a-105">Threat Explorer-walk-through</span><span class="sxs-lookup"><span data-stu-id="31b1a-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="31b1a-106">E-mailonderzoek</span><span class="sxs-lookup"><span data-stu-id="31b1a-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="31b1a-107">E-mailsanering</span><span class="sxs-lookup"><span data-stu-id="31b1a-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="31b1a-108">Verbeteringen in de bedreigingsjachtervaring</span><span class="sxs-lookup"><span data-stu-id="31b1a-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="31b1a-109">Dit maakt deel uit van een reeks van drie artikelen over **Threat Explorer (Explorer),** **e-mailbeveiliging** **en** explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken).</span><span class="sxs-lookup"><span data-stu-id="31b1a-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="31b1a-110">De andere twee artikelen in deze reeks zijn [E-mailbeveiliging met de](email-security-in-microsoft-defender.md) basisbeginselen Bedreigingsverkenner en [Threat Explorer en realtime detecties.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="31b1a-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="31b1a-111">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="31b1a-111">**Applies to**</span></span>
- [<span data-ttu-id="31b1a-112">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="31b1a-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="31b1a-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31b1a-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="31b1a-114">Als uw organisatie [Microsoft Defender](defender-for-office-365.md)heeft voor Office 365 en u beschikt over de [machtigingen,](#required-licenses-and-permissions)kunt u **Explorer** of **realtimedetecties** gebruiken om bedreigingen te detecteren en te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="31b1a-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="31b1a-115">Ga in Microsoft 365 Defender portal ( ) naar E-mail & samenwerking en kies vervolgens <https://security.microsoft.com> **Verkenner** of **Realtime detecties.** </span><span class="sxs-lookup"><span data-stu-id="31b1a-115">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** or **Real-time detections**.</span></span> <span data-ttu-id="31b1a-116">Als u rechtstreeks naar de pagina wilt gaan, gebruikt <https://security.microsoft.com/threatexplorer> u of <https://security.microsoft.com/realtimereports></span><span class="sxs-lookup"><span data-stu-id="31b1a-116">To do directly to the page, use <https://security.microsoft.com/threatexplorer> or <https://security.microsoft.com/realtimereports></span></span>

<span data-ttu-id="31b1a-117">Met deze hulpmiddelen kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="31b1a-117">With these tools, you can:</span></span>

- <span data-ttu-id="31b1a-118">Malware zien die is gedetecteerd door Microsoft 365 beveiligingsfuncties</span><span class="sxs-lookup"><span data-stu-id="31b1a-118">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="31b1a-119">Phishing-URL weergeven en op vonnisgegevens klikken</span><span class="sxs-lookup"><span data-stu-id="31b1a-119">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="31b1a-120">Een geautomatiseerd onderzoek- en antwoordproces starten vanuit een weergave in Explorer</span><span class="sxs-lookup"><span data-stu-id="31b1a-120">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="31b1a-121">Schadelijke e-mail onderzoeken en meer</span><span class="sxs-lookup"><span data-stu-id="31b1a-121">Investigate malicious email, and more</span></span>

<span data-ttu-id="31b1a-122">Zie E-mailbeveiliging [met Threat Explorer voor meer informatie.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="31b1a-122">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="31b1a-123">Threat Explorer-walk-through</span><span class="sxs-lookup"><span data-stu-id="31b1a-123">Threat Explorer walk-through</span></span>

<span data-ttu-id="31b1a-124">In Microsoft Defender voor Office 365 zijn er twee abonnementen: Abonnement 1 en Abonnement 2.</span><span class="sxs-lookup"><span data-stu-id="31b1a-124">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="31b1a-125">Handmatig beheerde hulpprogramma's voor het zoeken naar bedreigingen bestaan in beide plannen, onder verschillende namen en met verschillende mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="31b1a-125">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="31b1a-126">Defender voor Office 365 Plan 1 maakt gebruik van *realtime detecties,* een subset van het *zoekprogramma Threat Explorer* (ook wel Verkenner genoemd) in Plan 2. </span><span class="sxs-lookup"><span data-stu-id="31b1a-126">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="31b1a-127">In deze reeks artikelen zijn de meeste voorbeelden gemaakt met de volledige Threat Explorer.</span><span class="sxs-lookup"><span data-stu-id="31b1a-127">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="31b1a-128">Beheerders moeten alle stappen in realtimedetecties testen om te zien waar ze van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="31b1a-128">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="31b1a-129">Nadat u standaard **naar Verkenner** bent gaan, komt u op  de pagina **Malware,** maar gebruikt u de vervolgkeuzekeuzepagina Beeld om vertrouwd te raken met uw opties.</span><span class="sxs-lookup"><span data-stu-id="31b1a-129">After you go to **Explorer**, by default, you'll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="31b1a-130">Als u op Phish jaagt of een bedreigingscampagne bekijkt, kiest u deze weergaven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-130">If you're hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-131">![Vervolgkeuzekeuzeweergave in Threat Explorer](../../media/view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-131">![View drop down in Threat Explorer](../../media/view-drop-down.png)</span></span>

<span data-ttu-id="31b1a-132">Wanneer een persoon met beveiligingsbewerkingen (Sec Ops) de gegevens selecteert die hij of zij wil zien, of het bereik een smalle weergave is, zoals gebruikersinzendingen of een bredere weergave, zoals **Alle** e-mail, kunnen ze de knop **Afzender** gebruiken om verder te filteren.</span><span class="sxs-lookup"><span data-stu-id="31b1a-132">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="31b1a-133">Selecteer Vernieuwen om uw filteracties te voltooien.</span><span class="sxs-lookup"><span data-stu-id="31b1a-133">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-134">![Knop Afzender in Threat Explorer](../../media/sender-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-134">![Sender button in Threat Explorer](../../media/sender-drop-down.png)</span></span>

<span data-ttu-id="31b1a-135">U kunt de focus in Explorer of realtimedetectie in lagen verfijnen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-135">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="31b1a-136">De eerste is **Weergave.**</span><span class="sxs-lookup"><span data-stu-id="31b1a-136">The first is **View**.</span></span> <span data-ttu-id="31b1a-137">De tweede kan worden gedacht als een *gefilterde focus.*</span><span class="sxs-lookup"><span data-stu-id="31b1a-137">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="31b1a-138">U kunt bijvoorbeeld de stappen die u hebt genomen bij het vinden van een bedreiging, traceren door uw beslissingen op te nemen zoals deze: Als u het probleem wilt vinden in Explorer, heb ik de malwareweergave gekozen met de **filterfocus Geadresseerde.**</span><span class="sxs-lookup"><span data-stu-id="31b1a-138">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="31b1a-139">Dit maakt het gemakkelijker om uw stappen te volgen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-139">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="31b1a-140">Als Sec Ops Tags gebruikt **om** accounts te markeren die ze als hoog gewaardeerde doelen beschouwen, kunnen ze selecties maken, zoals *Phish-weergave* met de filterfocus Tags (inclusief een datumbereik indien gebruikt).</span><span class="sxs-lookup"><span data-stu-id="31b1a-140">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="31b1a-141">Op deze manier kunnen ze phishingpogingen zien die zijn gericht op hun hoge gebruikersdoelen gedurende een bepaalde periode (zoals datums waarop bepaalde phishingaanvallen veel voor hun branche plaatsvinden).</span><span class="sxs-lookup"><span data-stu-id="31b1a-141">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span>

<span data-ttu-id="31b1a-142">Verfijningen kunnen worden aangebracht op datumbereiken met behulp van de besturingselementen voor het datumbereik.</span><span class="sxs-lookup"><span data-stu-id="31b1a-142">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="31b1a-143">Hier ziet u Verkenner in **de malwareweergave,** met de **filterfocus Detectietechnologie.**</span><span class="sxs-lookup"><span data-stu-id="31b1a-143">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="31b1a-144">Maar het is de knop **Geavanceerd filter** waarmee Sec Ops-teams diep kunnen graven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-144">But it's the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-145">![Geavanceerd filter in Threat Explorer](../../media/advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-145">![Advanced filter in Threat Explorer](../../media/advanced-filter.png)</span></span>

<span data-ttu-id="31b1a-146">Als u op het filter Geavanceerd **klikt,** wordt een deelvenster weergegeven waarmee sec ops-jagers zelf query's kunnen maken, zodat ze de informatie kunnen opnemen of uitsluiten die ze nodig hebben om te zien.</span><span class="sxs-lookup"><span data-stu-id="31b1a-146">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="31b1a-147">Zowel de grafiek als de tabel op de pagina Explorer geven de resultaten weer.</span><span class="sxs-lookup"><span data-stu-id="31b1a-147">Both the chart and table on the Explorer page will reflect their results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-148">![Resultaten van een query](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-148">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="31b1a-149">Gebruik de **knop Kolomopties** om het soort informatie in de tabel op te halen dat het meest nuttig is:</span><span class="sxs-lookup"><span data-stu-id="31b1a-149">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-150">![Knop Kolomopties gemarkeerd](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-150">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-151">![Beschikbare opties in kolommen](../../media/column-options.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-151">![Available options in Columns](../../media/column-options.png)</span></span>

<span data-ttu-id="31b1a-152">Test in dezelfde mien de weergaveopties.</span><span class="sxs-lookup"><span data-stu-id="31b1a-152">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="31b1a-153">Verschillende doelgroepen reageren goed op verschillende presentaties met dezelfde gegevens.</span><span class="sxs-lookup"><span data-stu-id="31b1a-153">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="31b1a-154">Voor sommige gebruikers kan de **e-mail origins-kaart** laten zien  dat een bedreiging breder of discreter is dan de weergaveoptie Campagne direct er naast.</span><span class="sxs-lookup"><span data-stu-id="31b1a-154">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="31b1a-155">Sec Ops kan gebruik maken van deze beeldschermen om de beste punten te maken die de noodzaak onderstrepen van beveiliging en beveiliging, of voor latere vergelijking, om de effectiviteit van hun acties aan te tonen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-155">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-156">![E-mail origins-kaart](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-156">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-157">![Weergaveopties voor campagne](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-157">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="31b1a-158">E-mailonderzoek</span><span class="sxs-lookup"><span data-stu-id="31b1a-158">Email investigation</span></span>

<span data-ttu-id="31b1a-159">Wanneer u een verdacht e-mailbericht ziet, klikt u op de naam om de flyout aan de rechterkant uit te vouwen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-159">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="31b1a-160">Hier is de banner waarmee Sec Ops de pagina [e-mailentiteit kan](mdo-email-entity-page.md) zien, beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="31b1a-160">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="31b1a-161">Op de pagina e-mailentiteit wordt inhoud verzameld die kan worden gevonden onder **Details**, **Bijlagen**, **Apparaten**, maar bevat meer geordende gegevens.</span><span class="sxs-lookup"><span data-stu-id="31b1a-161">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="31b1a-162">Dit omvat zaken als DMARC-resultaten, het weergeven van tekst zonder tekst van de e-mailkop met een kopieeroptie, informatie over bijlagen die veilig zijn ontploft en bestanden die detonaties laten vallen (kunnen IP-adressen bevatten die zijn gecontacteerd en schermafbeeldingen van pagina's of bestanden).</span><span class="sxs-lookup"><span data-stu-id="31b1a-162">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="31b1a-163">URL's en hun vonnissen worden ook vermeld met vergelijkbare details die zijn gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="31b1a-163">URLs and their verdicts are also listed with similar details reported.</span></span>

<span data-ttu-id="31b1a-164">Wanneer u deze fase bereikt, is de pagina e-mailentiteit essentieel voor de laatste stap:*herstel.*</span><span class="sxs-lookup"><span data-stu-id="31b1a-164">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-165">![De pagina e-mailentiteit](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-165">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="31b1a-166">Klik hier voor meer informatie over de  pagina met uitgebreide e-mailentiteit (hieronder te zien op het tabblad Analyse), met inbegrip van de resultaten van ontstekte bijlagen, bevindingen voor opgenomen URL's en een veilig voorbeeld van e-mail. [](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="31b1a-166">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-167">![Tabblad Analyse van de pagina e-mailentiteit](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-167">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="31b1a-168">E-mailsanering</span><span class="sxs-lookup"><span data-stu-id="31b1a-168">Email remediation</span></span>

<span data-ttu-id="31b1a-169">Zodra een Sec Ops-persoon vaststelt dat een e-mail een bedreiging is, is de volgende Explorer- of Realtimedetectiestap bezig met het afhandelen van de bedreiging en het herstellen van de bedreiging.</span><span class="sxs-lookup"><span data-stu-id="31b1a-169">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="31b1a-170">U kunt dit doen door terug te keren naar Threat Explorer, het selectievakje voor het probleem-e-mailbericht in te selecteren en de knop **Acties te** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="31b1a-170">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-171">![Knop Acties in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-171">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="31b1a-172">Hier kan de analist acties ondernemen, zoals het rapporteren van de e-mail als Spam, Phishing of Malware, contact opnemen met geadresseerden of verdere onderzoeken die kunnen bestaan uit het activeren van playbooks voor Geautomatiseerd onderzoek en antwoord (of AIR) (als u abonnement 2 hebt).</span><span class="sxs-lookup"><span data-stu-id="31b1a-172">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="31b1a-173">Of de e-mail kan ook als schoon worden gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="31b1a-173">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-174">![De vervolgkeuzekeuze van Acties](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-174">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="31b1a-175">Verbeteringen in de bedreigingsjachtervaring</span><span class="sxs-lookup"><span data-stu-id="31b1a-175">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="31b1a-176">Waarschuwings-id</span><span class="sxs-lookup"><span data-stu-id="31b1a-176">Alert ID</span></span>

<span data-ttu-id="31b1a-177">Wanneer u vanuit een waarschuwing naar  Threat Explorer navigeert, wordt de weergave gefilterd op **waarschuwings-id.**</span><span class="sxs-lookup"><span data-stu-id="31b1a-177">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="31b1a-178">Dit geldt ook voor realtimedetectie.</span><span class="sxs-lookup"><span data-stu-id="31b1a-178">This also applies in Real-time detection.</span></span> <span data-ttu-id="31b1a-179">Berichten die relevant zijn voor de specifieke waarschuwing en een e-mailtotaal (aantal) worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-179">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="31b1a-180">U kunt zien of een bericht deel uitmaakte van een waarschuwing en van dat bericht naar de bijbehorende waarschuwing navigeren.</span><span class="sxs-lookup"><span data-stu-id="31b1a-180">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="31b1a-181">Ten slotte wordt de waarschuwings-id opgenomen in de URL, bijvoorbeeld: `https://https://security.microsoft.com/viewalerts`</span><span class="sxs-lookup"><span data-stu-id="31b1a-181">Finally, alert ID is included in the URL, for example: `https://https://security.microsoft.com/viewalerts`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-182">![Filteren op waarschuwings-id](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-182">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-183">![Waarschuwings-id in details flyout](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-183">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="31b1a-184">Gegevensretentie en zoeklimiet voor proeften tenants verlengen in Explorer (en realtime detecties)</span><span class="sxs-lookup"><span data-stu-id="31b1a-184">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span>

<span data-ttu-id="31b1a-185">Als onderdeel van deze wijziging kunnen analisten e-mailgegevens zoeken en filteren over 30 dagen (verhoogd van zeven dagen) in Threat Explorer en real-time detecties voor zowel Defender voor Office P1- als P2-proeften tenants.</span><span class="sxs-lookup"><span data-stu-id="31b1a-185">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="31b1a-186">Dit heeft geen invloed op productieten tenants voor zowel P1- als P2 E5-klanten, waarbij de standaard bewaartermijn al 30 dagen is.</span><span class="sxs-lookup"><span data-stu-id="31b1a-186">This doesn't impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="31b1a-187">Bijgewerkte exportlimiet</span><span class="sxs-lookup"><span data-stu-id="31b1a-187">Updated Export limit</span></span>

<span data-ttu-id="31b1a-188">Het aantal E-mailrecords dat kan worden geëxporteerd vanuit Threat Explorer is nu 200.000 (was 9990).</span><span class="sxs-lookup"><span data-stu-id="31b1a-188">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="31b1a-189">De set kolommen die kunnen worden geëxporteerd, blijft ongewijzigd.</span><span class="sxs-lookup"><span data-stu-id="31b1a-189">The set of columns that can be exported is unchanged.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="31b1a-190">Tags in Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="31b1a-190">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="31b1a-191">De functie gebruikerslabels is beschikbaar in Preview en is mogelijk niet voor iedereen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="31b1a-191">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="31b1a-192">Previews kunnen ook worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="31b1a-192">Also, Previews are subject to change.</span></span> <span data-ttu-id="31b1a-193">Voor informatie over de releaseplanning raadpleegt u de Microsoft 365 routekaart.</span><span class="sxs-lookup"><span data-stu-id="31b1a-193">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="31b1a-194">Gebruikerslabels identificeren specifieke groepen gebruikers in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="31b1a-194">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="31b1a-195">Zie Gebruikerslabels voor meer informatie over tags, waaronder licenties en [configuratie.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="31b1a-195">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="31b1a-196">In Threat Explorer ziet u informatie over gebruikerslabels in de volgende ervaringen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-196">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="31b1a-197">E-mailrasterweergave</span><span class="sxs-lookup"><span data-stu-id="31b1a-197">Email grid view</span></span>

<span data-ttu-id="31b1a-198">Wanneer analisten de kolom **Tags** het e-mailraster bekijken, zien ze alle tags die zijn toegepast op postvakken van afzenders of geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="31b1a-198">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="31b1a-199">Systeemlabels zoals *prioriteitsaccounts* worden standaard eerst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-199">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-200">![Labels filteren in de e-mailrasterweergave](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-200">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="31b1a-201">Filteren</span><span class="sxs-lookup"><span data-stu-id="31b1a-201">Filtering</span></span>

<span data-ttu-id="31b1a-202">Tags kunnen worden gebruikt als filters.</span><span class="sxs-lookup"><span data-stu-id="31b1a-202">Tags can be used as filters.</span></span> <span data-ttu-id="31b1a-203">Zoek alleen naar prioriteitsaccounts of gebruik op deze manier specifieke scenario's voor gebruikerslabels.</span><span class="sxs-lookup"><span data-stu-id="31b1a-203">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="31b1a-204">U kunt ook resultaten met bepaalde tags uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="31b1a-204">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="31b1a-205">Combineer Tags met andere filters en datumbereiken om uw onderzoeksbereik te beperken.</span><span class="sxs-lookup"><span data-stu-id="31b1a-205">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span>

<span data-ttu-id="31b1a-206">[![Filterlabels](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="31b1a-206">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-207">![Geen filterlabels](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-207">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="31b1a-208">Flyout voor e-maildetails</span><span class="sxs-lookup"><span data-stu-id="31b1a-208">Email detail flyout</span></span>

<span data-ttu-id="31b1a-209">Als u de afzonderlijke tags voor afzender en geadresseerde wilt weergeven, selecteert u een e-mailbericht om de flyout berichtdetails te openen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-209">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="31b1a-210">Op het **tabblad** Overzicht worden de afzender- en geadresseerdelabels afzonderlijk weergegeven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-210">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="31b1a-211">De informatie over afzonderlijke tags voor afzender en geadresseerde kan worden geëxporteerd als CSV-gegevens.</span><span class="sxs-lookup"><span data-stu-id="31b1a-211">The information about individual tags for sender and recipient can be exported as CSV data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-212">![Tags voor e-maildetails](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-212">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="31b1a-213">Informatie over tags wordt ook weergegeven in de flyout klikken op URL's.</span><span class="sxs-lookup"><span data-stu-id="31b1a-213">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="31b1a-214">Ga naar het tabblad Phish of Alle e-mailweergave > **URL's** **of URL-klikken** om deze te bekijken. Selecteer een afzonderlijke URL-flyout voor meer informatie over klikken voor die URL, inclusief alle tags die aan die klik zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="31b1a-214">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="31b1a-215">Bijgewerkte tijdlijnweergave</span><span class="sxs-lookup"><span data-stu-id="31b1a-215">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-216">![URL-tags](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-216">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="31b1a-217">Meer informatie vindt u in [deze video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span><span class="sxs-lookup"><span data-stu-id="31b1a-217">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="31b1a-218">Uitgebreide mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="31b1a-218">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="31b1a-219">Best getargete gebruikers</span><span class="sxs-lookup"><span data-stu-id="31b1a-219">Top targeted users</span></span>

<span data-ttu-id="31b1a-220">Top Malware Families toont de **meest gerichte gebruikers** in de sectie Malware.</span><span class="sxs-lookup"><span data-stu-id="31b1a-220">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="31b1a-221">Top targeted users will be extended through Phish and All Email views too.</span><span class="sxs-lookup"><span data-stu-id="31b1a-221">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="31b1a-222">Analisten kunnen de vijf meest gerichte gebruikers zien, samen met het aantal pogingen voor elke gebruiker in elke weergave.</span><span class="sxs-lookup"><span data-stu-id="31b1a-222">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span>

<span data-ttu-id="31b1a-223">Beveiligingsbewerkingen personen kunnen de lijst met doelgebruikers exporteren, tot een limiet van 3.000, samen met het aantal pogingen, voor offlineanalyse voor elke e-mailweergave.</span><span class="sxs-lookup"><span data-stu-id="31b1a-223">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="31b1a-224">Als u het aantal pogingen selecteert (bijvoorbeeld 13 pogingen in de onderstaande afbeelding), wordt er een gefilterde weergave geopend in Threat Explorer, zodat u meer informatie over e-mailberichten en bedreigingen voor die gebruiker kunt zien.</span><span class="sxs-lookup"><span data-stu-id="31b1a-224">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-225">![Best getargete gebruikers](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-225">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="31b1a-226">Exchange transportregels</span><span class="sxs-lookup"><span data-stu-id="31b1a-226">Exchange transport rules</span></span>

<span data-ttu-id="31b1a-227">Het beveiligingsteam kan in de weergave E-mailraster alle transportregels (Exchange E-mailstroomregels) zien die zijn toegepast op een bericht.</span><span class="sxs-lookup"><span data-stu-id="31b1a-227">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="31b1a-228">Selecteer **Kolomopties** in het raster en voeg **Exchange transportregel toe** vanuit de kolomopties.</span><span class="sxs-lookup"><span data-stu-id="31b1a-228">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="31b1a-229">De Exchange de optie transportregels is ook zichtbaar in de flyout **Details** in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="31b1a-229">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="31b1a-230">Namen en GUID's van de transportregels die op het bericht zijn toegepast, worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-230">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="31b1a-231">Analisten kunnen berichten zoeken met de naam van de transportregel.</span><span class="sxs-lookup"><span data-stu-id="31b1a-231">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="31b1a-232">Dit is een CONTAINS-zoekopdracht, wat betekent dat u ook gedeeltelijke zoekopdrachten kunt doen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-232">This is a CONTAINS search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31b1a-233">Exchange zoek- en naambeschikbaarheid van transportregel is afhankelijk van de specifieke rol die aan u is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-233">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="31b1a-234">U moet een van de volgende rollen of machtigingen hebben om de namen en zoekopdrachten van de transportregel weer te geven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-234">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="31b1a-235">Zelfs zonder de onderstaande rollen of machtigingen kan een analist echter het label van de transportregel en de GUID-gegevens in de e-mailgegevens zien.</span><span class="sxs-lookup"><span data-stu-id="31b1a-235">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="31b1a-236">Andere ervaringen met het weergeven van records in e-mailrasters, e-mail flyouts, Filters en Export worden niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="31b1a-236">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="31b1a-237">Exchange Online Alleen - Preventie van gegevensverlies: Alles</span><span class="sxs-lookup"><span data-stu-id="31b1a-237">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="31b1a-238">Exchange Online Alleen - O365SupportViewConfig: Alle</span><span class="sxs-lookup"><span data-stu-id="31b1a-238">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="31b1a-239">Microsoft Azure Active Directory of Exchange Online - Beveiligingsbeheerder: Alles</span><span class="sxs-lookup"><span data-stu-id="31b1a-239">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="31b1a-240">Azure Active Directory of Exchange Online - Beveiligingslezer: Alles</span><span class="sxs-lookup"><span data-stu-id="31b1a-240">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="31b1a-241">Exchange Online Alleen - Transportregels: Alles</span><span class="sxs-lookup"><span data-stu-id="31b1a-241">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="31b1a-242">Exchange Online Alleen - View-Only Configuratie: Alles</span><span class="sxs-lookup"><span data-stu-id="31b1a-242">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="31b1a-243">In het e-mailraster, de flyout Details en de geëxporteerde CSV worden de ETR's weergegeven met een Naam/GUID zoals hieronder wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="31b1a-243">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="31b1a-244">![Exchange Transportregels](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-244">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="31b1a-245">Binnenkomende verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="31b1a-245">Inbound connectors</span></span>

<span data-ttu-id="31b1a-246">Connectors zijn een verzameling instructies die aanpassen hoe uw e-mail van en naar uw Microsoft 365 of Office 365 organisatie loopt.</span><span class="sxs-lookup"><span data-stu-id="31b1a-246">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="31b1a-247">Hiermee kunt u beveiligingsbeperkingen of besturingselementen toepassen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-247">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="31b1a-248">In Threat Explorer kunt u de verbindingslijnen weergeven die zijn gerelateerd aan een e-mail en e-mailberichten zoeken met behulp van connectornamen.</span><span class="sxs-lookup"><span data-stu-id="31b1a-248">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span>

<span data-ttu-id="31b1a-249">Het zoeken naar verbindingslijnen is een CONTAINS-query, wat betekent dat gedeeltelijke trefwoordzoekingen kunnen werken:</span><span class="sxs-lookup"><span data-stu-id="31b1a-249">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31b1a-250">![Connectordetails](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="31b1a-250">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="31b1a-251">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="31b1a-251">Required licenses and permissions</span></span>

<span data-ttu-id="31b1a-252">U moet [Microsoft Defender hebben om Office 365](defender-for-office-365.md) explorer of realtime detecties te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="31b1a-252">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="31b1a-253">Explorer is opgenomen in Defender voor Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="31b1a-253">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="31b1a-254">Het realtimedetectierapport is opgenomen in Defender voor Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="31b1a-254">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="31b1a-255">Plan om licenties toe te wijzen voor alle gebruikers die moeten worden beveiligd door Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="31b1a-255">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="31b1a-256">Explorer- en realtimedetecties tonen detectiegegevens voor gelicentieerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="31b1a-256">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="31b1a-257">Als u Explorer- of realtimedetecties wilt bekijken en gebruiken, moet u de volgende machtigingen hebben:</span><span class="sxs-lookup"><span data-stu-id="31b1a-257">To view and use Explorer or Real-time detections, you must have the following permissions:</span></span>

- <span data-ttu-id="31b1a-258">Voor de Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="31b1a-258">For the Microsoft 365 Defender portal:</span></span>
  - <span data-ttu-id="31b1a-259">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="31b1a-259">Organization Management</span></span>
  - <span data-ttu-id="31b1a-260">Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory beheercentrum ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="31b1a-260">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="31b1a-261">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="31b1a-261">Security Reader</span></span>
- <span data-ttu-id="31b1a-262">Voor Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="31b1a-262">For Exchange Online:</span></span>
  - <span data-ttu-id="31b1a-263">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="31b1a-263">Organization Management</span></span>
  - <span data-ttu-id="31b1a-264">View-Only Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="31b1a-264">View-Only Organization Management</span></span>
  - <span data-ttu-id="31b1a-265">View-Only Geadresseerden</span><span class="sxs-lookup"><span data-stu-id="31b1a-265">View-Only Recipients</span></span>
  - <span data-ttu-id="31b1a-266">Compliancebeheer</span><span class="sxs-lookup"><span data-stu-id="31b1a-266">Compliance Management</span></span>

<span data-ttu-id="31b1a-267">Zie de volgende bronnen voor meer informatie over rollen en machtigingen:</span><span class="sxs-lookup"><span data-stu-id="31b1a-267">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="31b1a-268">Machtigingen in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="31b1a-268">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="31b1a-269">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="31b1a-269">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="31b1a-270">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="31b1a-270">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="31b1a-271">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="31b1a-271">More information</span></span>

- [<span data-ttu-id="31b1a-272">Schadelijke e-mail zoeken en onderzoeken die is bezorgd</span><span class="sxs-lookup"><span data-stu-id="31b1a-272">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="31b1a-273">Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31b1a-273">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="31b1a-274">Een overzicht krijgen van de weergaven in Threat Explorer (en realtime detecties)</span><span class="sxs-lookup"><span data-stu-id="31b1a-274">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="31b1a-275">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="31b1a-275">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="31b1a-276">Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="31b1a-276">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
- [<span data-ttu-id="31b1a-277">E-mailberichten onderzoeken met de pagina E-mailentiteit</span><span class="sxs-lookup"><span data-stu-id="31b1a-277">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
