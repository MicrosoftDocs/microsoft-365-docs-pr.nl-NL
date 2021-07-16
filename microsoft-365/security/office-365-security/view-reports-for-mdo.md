---
title: Defender voor Office 365-rapporten weergeven
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe ze de Defender kunnen vinden en gebruiken voor Office 365 rapporten die beschikbaar zijn in de Microsoft 365 Defender portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454719"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c426e-103">Defender weergeven voor Office 365 rapporten in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="c426e-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c426e-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c426e-104">**Applies to**</span></span>
- [<span data-ttu-id="c426e-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c426e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c426e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c426e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c426e-107">Microsoft Defender voor Office 365-organisaties (bijvoorbeeld Microsoft 365 E5-abonnementen of Microsoft Defender voor Office 365 Plan 1 of Microsoft Defender voor Office 365 Abonnement 2-invoegtoepassingen) bevatten diverse beveiligingsgerelateerde rapporten.</span><span class="sxs-lookup"><span data-stu-id="c426e-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="c426e-108">Als u de [benodigde](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)machtigingen hebt, kunt u deze rapporten  bekijken in de Microsoft 365 Defender-portal door naar Rapporten e-mail & samenwerking e-mail & \>  \> **samenwerkingsrapporten.**</span><span class="sxs-lookup"><span data-stu-id="c426e-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c426e-109">Als u rechtstreeks naar de pagina **E-mail & samenwerkingsrapporten** wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="c426e-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina & samenwerkingsrapporten in de Microsoft 365 Defender portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="c426e-111">E-mailbeveiligingsrapporten waarvoor Defender niet nodig is Office 365 worden beschreven in E-mailbeveiligingsrapporten [weergeven in de Microsoft 365 Defender portal.](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="c426e-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="c426e-112">Rapporten die zijn gerelateerd aan de e-mailstroom, zijn nu in het Exchange beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="c426e-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="c426e-113">Zie E-mailstroomrapporten in het nieuwe Exchange [beheercentrum voor meer informatie over deze rapporten.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="c426e-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="c426e-114">Safe Rapport Bestandstypen bijlagen</span><span class="sxs-lookup"><span data-stu-id="c426e-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="c426e-115">Het **Safe bestandstypen van** bijlagen wordt uiteindelijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c426e-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="c426e-116">Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="c426e-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="c426e-117">Safe Berichtbezettingsrapport bijlagen</span><span class="sxs-lookup"><span data-stu-id="c426e-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="c426e-118">Het **Safe berichtbezettingsrapport** bijlagen wordt uiteindelijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c426e-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="c426e-119">Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="c426e-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="c426e-120">E-maillatentierapport</span><span class="sxs-lookup"><span data-stu-id="c426e-120">Mail latency report</span></span>

<span data-ttu-id="c426e-121">In **het rapport E-maillatentie** ziet u een statistische weergave van de latentie van e-mailbezorging en detonatie binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c426e-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="c426e-122">E-mailbezorgingstijden in de service worden beïnvloed door een aantal factoren en de absolute levertijd in seconden is vaak geen goede indicator voor succes of een probleem.</span><span class="sxs-lookup"><span data-stu-id="c426e-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="c426e-123">Een trage levertijd op één dag kan worden beschouwd als een gemiddelde levertijd op een andere dag, of omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="c426e-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="c426e-124">Hiermee wordt geprobeerd berichtbezorging te kwalificeren op basis van statistische gegevens over de waargenomen levertijden van andere berichten.</span><span class="sxs-lookup"><span data-stu-id="c426e-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="c426e-125">Clientzijde en netwerklatentie zijn niet inbegrepen.</span><span class="sxs-lookup"><span data-stu-id="c426e-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="c426e-126">Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender portal](https://security.microsoft.com), gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="c426e-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c426e-127">Zoek op **de pagina & e-mailsamenwerkingsrapporten** naar **het rapport E-maillatentie** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="c426e-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="c426e-128">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="c426e-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Rapportwidget e-maillatentie op de pagina E-mail & samenwerkingsrapporten](../../media/mail-latency-report-widget.png)

<span data-ttu-id="c426e-130">Op de **pagina E-maillatentierapport** zijn de volgende tabbladen beschikbaar op de pagina **E-maillatentierapport:**</span><span class="sxs-lookup"><span data-stu-id="c426e-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="c426e-131">**50e percentiel:** dit is het midden voor bezorgingstijden van berichten.</span><span class="sxs-lookup"><span data-stu-id="c426e-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="c426e-132">U kunt deze waarde beschouwen als een gemiddelde levertijd.</span><span class="sxs-lookup"><span data-stu-id="c426e-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="c426e-133">Dit tabblad is standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="c426e-133">This tab is selected by default.</span></span>
- <span data-ttu-id="c426e-134">**90e percentiel:** dit geeft een hoge latentie voor berichtbezorging aan.</span><span class="sxs-lookup"><span data-stu-id="c426e-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="c426e-135">Slechts 10% van de berichten duurde langer dan deze waarde.</span><span class="sxs-lookup"><span data-stu-id="c426e-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="c426e-136">**99e percentiel:** dit geeft de hoogste latentie voor berichtbezorging aan.</span><span class="sxs-lookup"><span data-stu-id="c426e-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="c426e-137">Ongeacht het tabblad dat u selecteert, worden in de grafiek berichten weergegeven die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="c426e-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="c426e-138">**Latentie voor e-mailbezorging**</span><span class="sxs-lookup"><span data-stu-id="c426e-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="c426e-139">**Detonaties**</span><span class="sxs-lookup"><span data-stu-id="c426e-139">**Detonations**</span></span>

<span data-ttu-id="c426e-140">Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, ziet u een uitsplitsing van de latentie in elke categorie.</span><span class="sxs-lookup"><span data-stu-id="c426e-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![50e percentielweergave van het rapport E-maillatentie](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="c426e-142">Als u op **Filter** klikt, kunt u zowel de grafiek als de detailtabel filteren op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="c426e-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="c426e-143">**Datum (UTC)**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="c426e-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="c426e-144">**Berichtweergave:** Een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="c426e-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="c426e-145">**Alle berichten**</span><span class="sxs-lookup"><span data-stu-id="c426e-145">**All messages**</span></span>
  - <span data-ttu-id="c426e-146">**Berichten met bijlagen of URL's**</span><span class="sxs-lookup"><span data-stu-id="c426e-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="c426e-147">**Ontplofte berichten**</span><span class="sxs-lookup"><span data-stu-id="c426e-147">**Detonated messages**</span></span>

<span data-ttu-id="c426e-148">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="c426e-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="c426e-149">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="c426e-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="c426e-150">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="c426e-150">**Date (UTC)**</span></span>
- <span data-ttu-id="c426e-151">**Percentielen:** **50,** **90** of **99**</span><span class="sxs-lookup"><span data-stu-id="c426e-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="c426e-152">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="c426e-152">**Message count**</span></span>
- <span data-ttu-id="c426e-153">**Algehele latentie**</span><span class="sxs-lookup"><span data-stu-id="c426e-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="c426e-154">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="c426e-154">Threat protection status report</span></span>

<span data-ttu-id="c426e-155">Het rapport Status **van** bedreigingsbeveiliging is één weergave waarin informatie wordt bijeengehouden over schadelijke inhoud en schadelijke e-mail die is gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="c426e-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c426e-156">Zie Rapport [bedreigingsbeveiligingsstatus voor](view-email-security-reports.md#threat-protection-status-report)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c426e-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="c426e-157">URL-bedreigingsbeveiligingsrapport</span><span class="sxs-lookup"><span data-stu-id="c426e-157">URL threat protection report</span></span>

<span data-ttu-id="c426e-158">Het **rapport URL-bedreigingsbeveiliging** bevat overzichts- en trendweergaven voor gedetecteerde bedreigingen en acties die zijn ondernomen op URL-klikken als onderdeel [van Safe Koppelingen.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="c426e-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="c426e-159">In dit rapport zijn geen klikgegevens van gebruikers waar Safe beleid voor koppelingen is toegepast, is de optie **Gebruikersklikken** niet bijhouden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="c426e-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="c426e-160">Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender portal](https://security.microsoft.com), gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="c426e-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="c426e-161">Zoek op **de pagina & samenwerkingsrapporten** naar **de pagina URL-beveiliging** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="c426e-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="c426e-162">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="c426e-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Widget urlbeveiligingsrapport op de pagina E-mail & samenwerkingsrapporten](../../media/url-protection-report-widget.png)

<span data-ttu-id="c426e-164">De beschikbare weergaven op de **rapportpagina VOOR URL-bedreigingsbeveiliging** worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="c426e-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="c426e-165">Dit is een *beveiligingstrendrapport, wat* betekent dat gegevens trends vertegenwoordigen in een grotere gegevensset.</span><span class="sxs-lookup"><span data-stu-id="c426e-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="c426e-166">Hierdoor zijn de gegevens in de grafieken hier niet in realtime beschikbaar, maar de gegevens in de detailtabel wel, zodat er mogelijk een kleine afwijking tussen de twee wordt gezien.</span><span class="sxs-lookup"><span data-stu-id="c426e-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="c426e-167">De grafieken worden eenmaal per vier uur vernieuwd en bevatten gegevens voor de afgelopen 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="c426e-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="c426e-168">Gegevens weergeven op URL klik op beveiligingsactie</span><span class="sxs-lookup"><span data-stu-id="c426e-168">View data by URL click protection action</span></span>

![URL klik op beveiligingsactieweergave in het rapport URL-bedreigingsbeveiliging](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="c426e-170">In **de weergave Gegevens per URL klikken op beveiligingsactieweergave** ziet u het aantal URL-klikken van gebruikers in de organisatie en de resultaten van de klik:</span><span class="sxs-lookup"><span data-stu-id="c426e-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="c426e-171">**Toegestaan:** de gebruiker mocht naar de URL navigeren.</span><span class="sxs-lookup"><span data-stu-id="c426e-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="c426e-172">**Geblokkeerd:** De gebruiker is geblokkeerd voor het navigeren naar de URL.</span><span class="sxs-lookup"><span data-stu-id="c426e-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="c426e-173">**Geblokkeerd en doorgeklikt:** De gebruiker heeft ervoor gekozen om door te gaan met navigeren naar de URL.</span><span class="sxs-lookup"><span data-stu-id="c426e-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="c426e-174">**Doorgeklikt tijdens de scan:** De gebruiker heeft op de koppeling geklikt voordat de scan was voltooid.</span><span class="sxs-lookup"><span data-stu-id="c426e-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="c426e-175">Een klik geeft aan dat de gebruiker via de blokpagina naar de schadelijke website heeft geklikt (beheerders kunnen klikken uitschakelen in Safe Koppelingenbeleid).</span><span class="sxs-lookup"><span data-stu-id="c426e-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="c426e-176">Als u op **Filters** klikt, kunt u het rapport en de detailtabel wijzigen door een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="c426e-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="c426e-177">**Datum (UTC)**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="c426e-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="c426e-178">**Detectie**:</span><span class="sxs-lookup"><span data-stu-id="c426e-178">**Detection**:</span></span>
  - <span data-ttu-id="c426e-179">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="c426e-179">**Allowed**</span></span>
  - <span data-ttu-id="c426e-180">**Geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="c426e-180">**Blocked**</span></span>
  - <span data-ttu-id="c426e-181">**Geblokkeerd en doorgeklikt**</span><span class="sxs-lookup"><span data-stu-id="c426e-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="c426e-182">**Doorgeklikt tijdens de scan**</span><span class="sxs-lookup"><span data-stu-id="c426e-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="c426e-183">**Domeinen:** de URL-domeinen die worden vermeld in de rapportresultaten.</span><span class="sxs-lookup"><span data-stu-id="c426e-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="c426e-184">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="c426e-184">**Recipients**</span></span>

<span data-ttu-id="c426e-185">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="c426e-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="c426e-186">De detailtabel onder de grafiek bevat de volgende bijna-realtime weergave van alle klikken die de afgelopen 7 dagen binnen de organisatie hebben plaatsgevonden:</span><span class="sxs-lookup"><span data-stu-id="c426e-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="c426e-187">**Klik op tijd**</span><span class="sxs-lookup"><span data-stu-id="c426e-187">**Click time**</span></span>
- <span data-ttu-id="c426e-188">**Gebruiker**</span><span class="sxs-lookup"><span data-stu-id="c426e-188">**User**</span></span>
- <span data-ttu-id="c426e-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="c426e-189">**URL**</span></span>
- <span data-ttu-id="c426e-190">**Actie**</span><span class="sxs-lookup"><span data-stu-id="c426e-190">**Action**</span></span>
- <span data-ttu-id="c426e-191">**App**</span><span class="sxs-lookup"><span data-stu-id="c426e-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="c426e-192">Gegevens weergeven op URL klik op toepassing</span><span class="sxs-lookup"><span data-stu-id="c426e-192">View data by URL click by application</span></span>

![URL-klik op toepassingsweergave in het rapport URL-bedreigingsbeveiliging](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="c426e-194">In de weergave Gegevens **weergeven op URL op** toepassing wordt het aantal URL-klikken weergegeven door apps die ondersteuning bieden Safe Koppelingen:</span><span class="sxs-lookup"><span data-stu-id="c426e-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="c426e-195">**E-mailclient**</span><span class="sxs-lookup"><span data-stu-id="c426e-195">**Email client**</span></span>
- <span data-ttu-id="c426e-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="c426e-196">**PowerPoint**</span></span>
- <span data-ttu-id="c426e-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="c426e-197">**Word**</span></span>
- <span data-ttu-id="c426e-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="c426e-198">**Excel**</span></span>
- <span data-ttu-id="c426e-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="c426e-199">**OneNote**</span></span>
- <span data-ttu-id="c426e-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="c426e-200">**Visio**</span></span>
- <span data-ttu-id="c426e-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="c426e-201">**Teams**</span></span>
- <span data-ttu-id="c426e-202">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="c426e-202">**Others**</span></span>

<span data-ttu-id="c426e-203">Als u op **Filters** klikt, kunt u het rapport en de detailtabel wijzigen door een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="c426e-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="c426e-204">**Datum (UTC)**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="c426e-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="c426e-205">**Detectie:** Beschikbare apps in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="c426e-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="c426e-206">**Domeinen:** de URL-domeinen die worden vermeld in de rapportresultaten.</span><span class="sxs-lookup"><span data-stu-id="c426e-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="c426e-207">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="c426e-207">**Recipients**</span></span>

<span data-ttu-id="c426e-208">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="c426e-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="c426e-209">De detailtabel onder de grafiek bevat de volgende bijna-realtime weergave van alle klikken die de afgelopen 7 dagen binnen de organisatie hebben plaatsgevonden:</span><span class="sxs-lookup"><span data-stu-id="c426e-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="c426e-210">**Klik op tijd**</span><span class="sxs-lookup"><span data-stu-id="c426e-210">**Click time**</span></span>
- <span data-ttu-id="c426e-211">**Gebruiker**</span><span class="sxs-lookup"><span data-stu-id="c426e-211">**User**</span></span>
- <span data-ttu-id="c426e-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="c426e-212">**URL**</span></span>
- <span data-ttu-id="c426e-213">**Actie**</span><span class="sxs-lookup"><span data-stu-id="c426e-213">**Action**</span></span>
- <span data-ttu-id="c426e-214">**App**</span><span class="sxs-lookup"><span data-stu-id="c426e-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="c426e-215">Aanvullende rapporten die u wilt weergeven</span><span class="sxs-lookup"><span data-stu-id="c426e-215">Additional reports to view</span></span>

<span data-ttu-id="c426e-216">Naast de rapporten die in dit artikel worden beschreven, zijn er verschillende andere rapporten beschikbaar, zoals beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="c426e-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="c426e-217">Rapport</span><span class="sxs-lookup"><span data-stu-id="c426e-217">Report</span></span>|<span data-ttu-id="c426e-218">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="c426e-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="c426e-219">**Explorer** (Microsoft Defender voor Office 365 plan 2) of **realtime detecties** (Microsoft Defender voor Office 365 abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="c426e-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="c426e-220">Bedreigingsverkenner (en realtime detecties)</span><span class="sxs-lookup"><span data-stu-id="c426e-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="c426e-221">E-mailbeveiligingsrapporten waarvoor Defender niet nodig is voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c426e-221">Email security reports that don't require Defender for Office 365</span></span>|[<span data-ttu-id="c426e-222">E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="c426e-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="c426e-223">E-mailstroomrapporten in het Exchange-beheercentrum (EAC)</span><span class="sxs-lookup"><span data-stu-id="c426e-223">Mail flow reports in the Exchange admin center (EAC)</span></span>|[<span data-ttu-id="c426e-224">E-mailstroomrapporten in het nieuwe Exchange beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c426e-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

<span data-ttu-id="c426e-225">PowerShell-rapportage-cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c426e-225">PowerShell reporting cmdlets:</span></span>

<br>

****

|<span data-ttu-id="c426e-226">Rapport</span><span class="sxs-lookup"><span data-stu-id="c426e-226">Report</span></span>|<span data-ttu-id="c426e-227">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="c426e-227">Topic</span></span>|
|---|---|
|<span data-ttu-id="c426e-228">Belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="c426e-228">Top senders and recipients</span></span>|[<span data-ttu-id="c426e-229">Get-MailTrafficTopReport</span><span class="sxs-lookup"><span data-stu-id="c426e-229">Get-MailTrafficTopReport</span></span>](/powershell/module/exchange/get-mailtraffictopreport) <p> [<span data-ttu-id="c426e-230">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="c426e-230">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="c426e-231">Top malware</span><span class="sxs-lookup"><span data-stu-id="c426e-231">Top malware</span></span>|[<span data-ttu-id="c426e-232">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="c426e-232">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="c426e-233">E-mailverkeer</span><span class="sxs-lookup"><span data-stu-id="c426e-233">Mail traffic</span></span>|[<span data-ttu-id="c426e-234">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="c426e-234">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport) <p> [<span data-ttu-id="c426e-235">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="c426e-235">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|<span data-ttu-id="c426e-236">Veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="c426e-236">Safe Links</span></span>|[<span data-ttu-id="c426e-237">Get-SafeLinksAggregateReport</span><span class="sxs-lookup"><span data-stu-id="c426e-237">Get-SafeLinksAggregateReport</span></span>](/powershell/module/exchange/get-safelinksaggregatereport) <p> [<span data-ttu-id="c426e-238">Get-SafeLinksDetailReport</span><span class="sxs-lookup"><span data-stu-id="c426e-238">Get-SafeLinksDetailReport</span></span>](/powershell/module/exchange/get-safelinksdetailreport)|
|<span data-ttu-id="c426e-239">Gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="c426e-239">Compromised users</span></span>|[<span data-ttu-id="c426e-240">Get-CompromisedUserAggregateReport</span><span class="sxs-lookup"><span data-stu-id="c426e-240">Get-CompromisedUserAggregateReport</span></span>](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [<span data-ttu-id="c426e-241">Get-CompromisedUserDetailReport</span><span class="sxs-lookup"><span data-stu-id="c426e-241">Get-CompromisedUserDetailReport</span></span>](/powershell/module/exchange/get-compromiseduserdetailreport)|
|<span data-ttu-id="c426e-242">E-mailstroomstatus</span><span class="sxs-lookup"><span data-stu-id="c426e-242">Mail flow status</span></span>|[<span data-ttu-id="c426e-243">Get-MailflowStatusReport</span><span class="sxs-lookup"><span data-stu-id="c426e-243">Get-MailflowStatusReport</span></span>](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="c426e-244">Welke machtigingen zijn nodig om de Defender voor Office 365 weergeven?</span><span class="sxs-lookup"><span data-stu-id="c426e-244">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="c426e-245">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="c426e-245">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="c426e-246">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="c426e-246">**Organization Management**</span></span>
- <span data-ttu-id="c426e-247">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="c426e-247">**Security Administrator**</span></span>
- <span data-ttu-id="c426e-248">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="c426e-248">**Security Reader**</span></span>
- <span data-ttu-id="c426e-249">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="c426e-249">**Global Reader**</span></span>

<span data-ttu-id="c426e-250">Zie [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c426e-250">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="c426e-251">**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c426e-251">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c426e-252">Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c426e-252">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="c426e-253">Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?</span><span class="sxs-lookup"><span data-stu-id="c426e-253">What if the reports aren't showing data?</span></span>

<span data-ttu-id="c426e-254">Als u geen gegevens ziet in uw Defender voor Office 365 rapporten, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="c426e-254">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="c426e-255">Uw organisatie moet Safe [beleidsregels](set-up-safe-links-policies.md) voor koppelingen en Safe [bijlagen](set-up-safe-attachments-policies.md) hebben gedefinieerd, zodat Defender Office 365 beveiliging kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c426e-255">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="c426e-256">Zie ook [Anti-spam en anti-malwarebeveiliging.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c426e-256">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c426e-257">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c426e-257">Related topics</span></span>

[<span data-ttu-id="c426e-258">Slimme rapporten en inzichten in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="c426e-258">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="c426e-259">Rolmachtigingen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c426e-259">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
