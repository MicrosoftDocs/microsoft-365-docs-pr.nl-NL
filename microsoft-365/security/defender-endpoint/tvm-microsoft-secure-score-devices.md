---
title: Microsoft Secure Score voor apparaten
description: Uw score voor apparaten toont de collectieve beveiligingsconfiguratie van uw apparaten in toepassings-, besturingssysteem-, netwerk-, accounts- en beveiligingsbesturingselementen.
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, threat and vulnerability management, security controls, improvement opportunities, security configuration score over time, security posture, baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934079"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="48a6a-104">Microsoft Secure Score voor apparaten</span><span class="sxs-lookup"><span data-stu-id="48a6a-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48a6a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="48a6a-105">**Applies to:**</span></span>

- [<span data-ttu-id="48a6a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="48a6a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="48a6a-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="48a6a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="48a6a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48a6a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="48a6a-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="48a6a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48a6a-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="48a6a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="48a6a-111">Configuratiescore maakt nu deel uit van bedreigings- en kwetsbaarheidsbeheer als Microsoft Secure Score voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="48a6a-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="48a6a-112">Uw score voor apparaten is zichtbaar in het dashboard [bedreigings- en kwetsbaarheidsbeheer](tvm-dashboard-insights.md) van het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="48a6a-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="48a6a-113">Een hogere Microsoft Secure Score voor apparaten betekent dat uw eindpunten beter bestand zijn tegen cyberbeveiligingsaanvallen.</span><span class="sxs-lookup"><span data-stu-id="48a6a-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="48a6a-114">Het geeft de status van de collectieve beveiligingsconfiguratie van uw apparaten weer in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="48a6a-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="48a6a-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="48a6a-115">Application</span></span>
- <span data-ttu-id="48a6a-116">Besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="48a6a-116">Operating system</span></span>
- <span data-ttu-id="48a6a-117">Netwerk</span><span class="sxs-lookup"><span data-stu-id="48a6a-117">Network</span></span>
- <span data-ttu-id="48a6a-118">Accounts</span><span class="sxs-lookup"><span data-stu-id="48a6a-118">Accounts</span></span>
- <span data-ttu-id="48a6a-119">Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="48a6a-119">Security controls</span></span>

<span data-ttu-id="48a6a-120">Selecteer een categorie om naar de pagina [**Beveiligingsaanbevelingen te**](tvm-security-recommendation.md) gaan en de relevante aanbevelingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="48a6a-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="48a6a-121">De Microsoft Secure Score-connector in-</span><span class="sxs-lookup"><span data-stu-id="48a6a-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="48a6a-122">Doorsturen van Microsoft Defender voor eindpuntsignalen, zodat Microsoft Secure Score inzicht krijgt in de beveiligingsstatus van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="48a6a-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="48a6a-123">Doorgestuurde gegevens worden opgeslagen en verwerkt op dezelfde locatie als uw Microsoft Secure Score-gegevens.</span><span class="sxs-lookup"><span data-stu-id="48a6a-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="48a6a-124">Het kan enkele uren duren voordat wijzigingen worden doorgevoerd in het dashboard.</span><span class="sxs-lookup"><span data-stu-id="48a6a-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="48a6a-125">Ga in het navigatiedeelvenster naar **Geavanceerde**  >  **functies instellingen**</span><span class="sxs-lookup"><span data-stu-id="48a6a-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="48a6a-126">Schuif omlaag naar **Microsoft Secure Score** en zet de instelling in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="48a6a-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="48a6a-127">Selecteer **Voorkeuren opslaan.**</span><span class="sxs-lookup"><span data-stu-id="48a6a-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="48a6a-128">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="48a6a-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="48a6a-129">Microsoft Secure Score for Devices ondersteunt momenteel configuraties die zijn ingesteld via groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="48a6a-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="48a6a-130">Vanwege de huidige gedeeltelijke Intune-ondersteuning kunnen configuraties die mogelijk zijn ingesteld via Intune, als onjuist geconfigureerd worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="48a6a-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="48a6a-131">Neem contact op met uw IT-beheerder om de werkelijke configuratiestatus te controleren voor het geval uw organisatie Intune gebruikt voor veilig configuratiebeheer.</span><span class="sxs-lookup"><span data-stu-id="48a6a-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="48a6a-132">De gegevens in de Kaart Microsoft Secure Score voor apparaten zijn het product van een zorgvuldig en voortdurend detectieproces voor beveiligingsleed.</span><span class="sxs-lookup"><span data-stu-id="48a6a-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="48a6a-133">Het wordt samengevoegd met configuratiedetectiebeoordelingen die continu:</span><span class="sxs-lookup"><span data-stu-id="48a6a-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="48a6a-134">Verzamelde configuraties vergelijken met de verzamelde benchmarks om verkeerd geconfigureerde assets te ontdekken</span><span class="sxs-lookup"><span data-stu-id="48a6a-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="48a6a-135">Configuraties in kaart brengen aan beveiligingslekken die kunnen worden gesaneerd of gedeeltelijk kunnen worden gesaneerd (risicobeperking)</span><span class="sxs-lookup"><span data-stu-id="48a6a-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="48a6a-136">Benchmarks voor best practice-configuratie verzamelen en onderhouden (leveranciers, beveiligingsfeeds, interne onderzoeksteams)</span><span class="sxs-lookup"><span data-stu-id="48a6a-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="48a6a-137">Wijzigingen van de configuratietoestand voor beveiligingsbesturingselementen verzamelen en controleren op basis van alle assets</span><span class="sxs-lookup"><span data-stu-id="48a6a-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="48a6a-138">Uw beveiligingsconfiguratie verbeteren</span><span class="sxs-lookup"><span data-stu-id="48a6a-138">Improve your security configuration</span></span>

<span data-ttu-id="48a6a-139">Verbeter uw beveiligingsconfiguratie door problemen op te lossen vanuit de lijst met beveiligingsaanbevelingen.</span><span class="sxs-lookup"><span data-stu-id="48a6a-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="48a6a-140">Terwijl u dit doet, verbetert uw Microsoft Secure Score voor apparaten en wordt uw organisatie beter bestand tegen cyberbeveiligingsdreigingen en -beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="48a6a-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="48a6a-141">Selecteer in de kaart Microsoft Secure Score voor apparaten in het dashboard bedreigings- en kwetsbaarheidsbeheer de categorieën.</span><span class="sxs-lookup"><span data-stu-id="48a6a-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="48a6a-142">U ziet de lijst met aanbevelingen die betrekking hebben op die categorie.</span><span class="sxs-lookup"><span data-stu-id="48a6a-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="48a6a-143">U gaat naar de pagina [**Beveiligingsaanbevelingen.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="48a6a-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="48a6a-144">Als u alle beveiligingsaanbevelingen wilt zien, kunt u het zoekveld verwijderen zodra u bij de pagina Beveiligingsaanbevelingen bent.</span><span class="sxs-lookup"><span data-stu-id="48a6a-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="48a6a-145">Selecteer een item in de lijst.</span><span class="sxs-lookup"><span data-stu-id="48a6a-145">Select an item on the list.</span></span> <span data-ttu-id="48a6a-146">Het flyout-deelvenster wordt geopend met informatie over de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="48a6a-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="48a6a-147">Selecteer **Herstelopties.**</span><span class="sxs-lookup"><span data-stu-id="48a6a-147">Select **Remediation options**.</span></span>

   ![Beveiligingsbesturingselementen gerelateerde beveiligingsaanbevelingen](images/tvm_security_controls.png)

3. <span data-ttu-id="48a6a-149">Lees de beschrijving om de context van het probleem te begrijpen en wat u daarna moet doen.</span><span class="sxs-lookup"><span data-stu-id="48a6a-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="48a6a-150">Selecteer een einddatum, voeg notities toe en selecteer Alle herstelactiviteitsgegevens exporteren naar **CSV,** zodat u deze kunt toevoegen aan een e-mail voor opvolging.</span><span class="sxs-lookup"><span data-stu-id="48a6a-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="48a6a-151">**Aanvraag indienen**.</span><span class="sxs-lookup"><span data-stu-id="48a6a-151">**Submit request**.</span></span> <span data-ttu-id="48a6a-152">U ziet een bevestigingsbericht dat de hersteltaak is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="48a6a-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="48a6a-153">![Bevestiging van het maken van hersteltaak](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="48a6a-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="48a6a-154">Sla uw CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="48a6a-154">Save your CSV file.</span></span>
   <span data-ttu-id="48a6a-155">![CSV-bestand opslaan](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="48a6a-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="48a6a-156">Stuur een follow-up-e-mail naar uw IT-beheerder en laat de tijd die u hebt toegewezen om de hersteltijd in het systeem door te geven.</span><span class="sxs-lookup"><span data-stu-id="48a6a-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="48a6a-157">Controleer nogmaals **de Microsoft Secure Score for Devices-kaart** op het dashboard.</span><span class="sxs-lookup"><span data-stu-id="48a6a-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="48a6a-158">Het aantal aanbevelingen voor beveiligingsbesturingselementen neemt af.</span><span class="sxs-lookup"><span data-stu-id="48a6a-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="48a6a-159">Wanneer u **Beveiligingsbesturingselementen** selecteert om terug te gaan naar de pagina Beveiligingsaanbevelingen, wordt het item dat u hebt geadresseerd daar niet meer weergegeven. </span><span class="sxs-lookup"><span data-stu-id="48a6a-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="48a6a-160">Uw Microsoft Secure Score voor apparaten moet toenemen.</span><span class="sxs-lookup"><span data-stu-id="48a6a-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="48a6a-161">Download de volgende verplichte beveiligingsupdates en implementeer deze in uw netwerk om de detectiepercentages voor beveiligingsrisico's te verhogen:</span><span class="sxs-lookup"><span data-stu-id="48a6a-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="48a6a-162">19H1-klanten | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="48a6a-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="48a6a-163">RS5-klanten | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="48a6a-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="48a6a-164">RS4-klanten | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="48a6a-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="48a6a-165">RS3-klanten | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="48a6a-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="48a6a-166">De beveiligingsupdates downloaden:</span><span class="sxs-lookup"><span data-stu-id="48a6a-166">To download the security updates:</span></span>
>1. <span data-ttu-id="48a6a-167">Ga naar [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span><span class="sxs-lookup"><span data-stu-id="48a6a-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="48a6a-168">Key-in the security update KB number that you need to download, then click **Search**.</span><span class="sxs-lookup"><span data-stu-id="48a6a-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="48a6a-169">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="48a6a-169">Related topics</span></span>

- [<span data-ttu-id="48a6a-170">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="48a6a-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="48a6a-171">Dashboard</span><span class="sxs-lookup"><span data-stu-id="48a6a-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="48a6a-172">Blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="48a6a-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="48a6a-173">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="48a6a-173">Security recommendations</span></span>](tvm-security-recommendation.md)
