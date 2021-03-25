---
title: Waarschuwingen voor Microsoft Defender voor eindpunten beheren
description: Wijzig de status van waarschuwingen, maak onderdrukkingsregels om waarschuwingen te verbergen, opmerkingen in te dienen en de wijzigingsgeschiedenis voor afzonderlijke waarschuwingen te controleren met het menu Waarschuwing beheren.
keywords: waarschuwingen beheren, beheren, waarschuwingen, status, nieuw, in uitvoering, opgelost, waarschuwingen oplossen, onderdrukken, onderdrukken, onderdrukken, regels, context, geschiedenis, opmerkingen, wijzigingen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186999"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="92394-104">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="92394-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="92394-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="92394-105">**Applies to:**</span></span>
- [<span data-ttu-id="92394-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="92394-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="92394-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92394-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="92394-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="92394-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="92394-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="92394-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="92394-110">Defender voor Eindpunt meldt u via waarschuwingen over mogelijke schadelijke gebeurtenissen, kenmerken en contextuele informatie.</span><span class="sxs-lookup"><span data-stu-id="92394-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="92394-111">Een overzicht van nieuwe waarschuwingen wordt weergegeven in het **dashboard** Beveiligingsbewerkingen en u hebt toegang tot alle waarschuwingen in de **wachtrij Waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="92394-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="92394-112">U kunt waarschuwingen beheren door een waarschuwing te selecteren in de wachtrij Waarschuwingen **of** op het **tabblad** Waarschuwingen van de pagina Apparaat voor een afzonderlijk apparaat.</span><span class="sxs-lookup"><span data-stu-id="92394-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="92394-113">Als u een waarschuwing selecteert op een van deze locaties, wordt het deelvenster **Waarschuwingsbeheer weergegeven.**</span><span class="sxs-lookup"><span data-stu-id="92394-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Afbeelding van waarschuwingsbeheervenster en waarschuwingenwachtrij](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="92394-115">Koppeling maken naar een ander incident</span><span class="sxs-lookup"><span data-stu-id="92394-115">Link to another incident</span></span>
<span data-ttu-id="92394-116">U kunt een nieuw incident maken vanuit de waarschuwing of een koppeling naar een bestaand incident.</span><span class="sxs-lookup"><span data-stu-id="92394-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="92394-117">Waarschuwingen toewijzen</span><span class="sxs-lookup"><span data-stu-id="92394-117">Assign alerts</span></span>
<span data-ttu-id="92394-118">Als er nog geen waarschuwing is toegewezen, kunt u Toewijzen aan **mij** selecteren om de waarschuwing aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="92394-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="92394-119">Waarschuwingen onderdrukken</span><span class="sxs-lookup"><span data-stu-id="92394-119">Suppress alerts</span></span>
<span data-ttu-id="92394-120">Er kunnen scenario's zijn waarin u waarschuwingen wilt onderdrukken die worden weergegeven in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="92394-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="92394-121">Met Defender voor Eindpunt kunt u onderdrukkingsregels maken voor specifieke waarschuwingen die onschadelijk zijn, zoals bekende hulpmiddelen of processen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="92394-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="92394-122">Onderdrukkingsregels kunnen worden gemaakt op een bestaande waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="92394-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="92394-123">Ze kunnen zo nodig worden uitgeschakeld en opnieuw worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="92394-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="92394-124">Wanneer een onderdrukkingsregel wordt gemaakt, wordt deze van kracht vanaf het moment dat de regel wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="92394-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="92394-125">De regel heeft geen invloed op bestaande waarschuwingen die al in de wachtrij staan, voordat de regel wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="92394-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="92394-126">De regel wordt alleen toegepast op waarschuwingen die voldoen aan de voorwaarden die zijn ingesteld nadat de regel is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="92394-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="92394-127">Er zijn twee contexten voor een onderdrukkingsregel waar u uit kunt kiezen:</span><span class="sxs-lookup"><span data-stu-id="92394-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="92394-128">**Waarschuwing onderdrukken op dit apparaat**</span><span class="sxs-lookup"><span data-stu-id="92394-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="92394-129">**Waarschuwing in mijn organisatie onderdrukken**</span><span class="sxs-lookup"><span data-stu-id="92394-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="92394-130">Met de context van de regel kunt u aanpassen wat er in de portal wordt opgedoken en ervoor zorgen dat alleen echte beveiligingswaarschuwingen in de portal worden opgedoken.</span><span class="sxs-lookup"><span data-stu-id="92394-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="92394-131">U kunt de voorbeelden in de volgende tabel gebruiken om de context voor een onderdrukkingsregel te kiezen:</span><span class="sxs-lookup"><span data-stu-id="92394-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="92394-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="92394-132">**Context**</span></span>                           | <span data-ttu-id="92394-133">**Definitie**</span><span class="sxs-lookup"><span data-stu-id="92394-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="92394-134">**Voorbeeldscenario's**</span><span class="sxs-lookup"><span data-stu-id="92394-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="92394-135">**Waarschuwing onderdrukken op dit apparaat**</span><span class="sxs-lookup"><span data-stu-id="92394-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="92394-136">Waarschuwingen met dezelfde waarschuwingstitel en alleen op dat specifieke apparaat worden onderdrukt.</span><span class="sxs-lookup"><span data-stu-id="92394-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="92394-137">Alle andere waarschuwingen op dat apparaat worden niet onderdrukt.</span><span class="sxs-lookup"><span data-stu-id="92394-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="92394-138">Een beveiligingsonderzoeker onderzoekt een schadelijk script dat is gebruikt om andere apparaten in uw organisatie aan te vallen.</span><span class="sxs-lookup"><span data-stu-id="92394-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="92394-139">Een ontwikkelaar maakt regelmatig PowerShell-scripts voor zijn of haar team.</span><span class="sxs-lookup"><span data-stu-id="92394-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="92394-140">**Waarschuwing in mijn organisatie onderdrukken**</span><span class="sxs-lookup"><span data-stu-id="92394-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="92394-141">Waarschuwingen met dezelfde waarschuwingstitel op elk apparaat worden onderdrukt.</span><span class="sxs-lookup"><span data-stu-id="92394-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="92394-142">Een goedaardig beheerhulpmiddel wordt door iedereen in uw organisatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="92394-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="92394-143">Een waarschuwing onderdrukken en een nieuwe onderdrukkingsregel maken:</span><span class="sxs-lookup"><span data-stu-id="92394-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="92394-144">Maak aangepaste regels om te bepalen wanneer waarschuwingen worden onderdrukt of opgelost.</span><span class="sxs-lookup"><span data-stu-id="92394-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="92394-145">U kunt de context bepalen voor wanneer een waarschuwing wordt onderdrukt door de waarschuwingstitel, indicator voor compromissen en de voorwaarden op te geven.</span><span class="sxs-lookup"><span data-stu-id="92394-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="92394-146">Nadat u de context hebt opgegeven, kunt u de actie en het bereik van de waarschuwing configureren.</span><span class="sxs-lookup"><span data-stu-id="92394-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="92394-147">Selecteer de waarschuwing die u wilt onderdrukken.</span><span class="sxs-lookup"><span data-stu-id="92394-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="92394-148">Hiermee wordt het deelvenster **Waarschuwingsbeheer** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="92394-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="92394-149">Selecteer **Een onderdrukkende regel maken.**</span><span class="sxs-lookup"><span data-stu-id="92394-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="92394-150">U kunt een onderdrukkingsvoorwaarde maken met behulp van deze kenmerken.</span><span class="sxs-lookup"><span data-stu-id="92394-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="92394-151">Er wordt een OPERATOR AND toegepast tussen elke voorwaarde, dus onderdrukking vindt alleen plaats als aan alle voorwaarden wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="92394-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="92394-152">Bestand SHA1</span><span class="sxs-lookup"><span data-stu-id="92394-152">File SHA1</span></span>
    * <span data-ttu-id="92394-153">Bestandsnaam - jokerteken ondersteund</span><span class="sxs-lookup"><span data-stu-id="92394-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="92394-154">Mappad - jokerteken ondersteund</span><span class="sxs-lookup"><span data-stu-id="92394-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="92394-155">IP-adres</span><span class="sxs-lookup"><span data-stu-id="92394-155">IP address</span></span>
    * <span data-ttu-id="92394-156">URL - jokerteken ondersteund</span><span class="sxs-lookup"><span data-stu-id="92394-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="92394-157">Opdrachtregel - jokerteken ondersteund</span><span class="sxs-lookup"><span data-stu-id="92394-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="92394-158">Selecteer het **IOC activeren.**</span><span class="sxs-lookup"><span data-stu-id="92394-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="92394-159">Geef de actie en het bereik van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="92394-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="92394-160">U kunt een waarschuwing automatisch oplossen of verbergen in de portal.</span><span class="sxs-lookup"><span data-stu-id="92394-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="92394-161">Waarschuwingen die automatisch worden opgelost, worden weergegeven in de opgeloste sectie van de waarschuwingenwachtrij, waarschuwingspagina en apparaattijdlijn en worden weergegeven als opgelost in defender voor eindpunt-API's.</span><span class="sxs-lookup"><span data-stu-id="92394-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="92394-162">Waarschuwingen die zijn gemarkeerd als verborgen, worden vanaf het hele systeem onderdrukt, zowel op de bijbehorende waarschuwingen van het apparaat als vanuit het dashboard en worden niet gestreamd via API's van Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="92394-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="92394-163">Voer een regelnaam en een opmerking in.</span><span class="sxs-lookup"><span data-stu-id="92394-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="92394-164">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="92394-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="92394-165">De lijst met onderdrukkingsregels weergeven</span><span class="sxs-lookup"><span data-stu-id="92394-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="92394-166">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Waarschuwingsonderdrukking**.</span><span class="sxs-lookup"><span data-stu-id="92394-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="92394-167">De lijst met onderdrukkingsregels bevat alle regels die gebruikers in uw organisatie hebben gemaakt.</span><span class="sxs-lookup"><span data-stu-id="92394-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="92394-168">Zie Onderdrukkingsregels beheren voor meer informatie over het beheren van [onderdrukkingsregels.](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="92394-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="92394-169">De status van een waarschuwing wijzigen</span><span class="sxs-lookup"><span data-stu-id="92394-169">Change the status of an alert</span></span>

<span data-ttu-id="92394-170">U kunt waarschuwingen categoriseren **(als Nieuw**, **In uitvoering** of **Opgelost)** door de status van de waarschuwingen te wijzigen naarmate het onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="92394-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="92394-171">Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="92394-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="92394-172">Een teamleider kan bijvoorbeeld alle nieuwe waarschuwingen **bekijken** en deze toewijzen aan de wachtrij **In voortgang** voor verdere analyse.</span><span class="sxs-lookup"><span data-stu-id="92394-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="92394-173">De teamleider kan de waarschuwing ook  toewijzen aan de wachtrij Opgelost als deze weet dat de waarschuwing goedaardig is, afkomstig is van een apparaat dat niet relevant is (zoals een van een beveiligingsbeheerder) of wordt afgehandeld via een eerdere waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="92394-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="92394-174">Waarschuwingsclassificatie</span><span class="sxs-lookup"><span data-stu-id="92394-174">Alert classification</span></span>
<span data-ttu-id="92394-175">U kunt ervoor kiezen geen classificatie in te stellen of op te geven of een waarschuwing een echte waarschuwing of een onwaar waarschuwing is.</span><span class="sxs-lookup"><span data-stu-id="92394-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="92394-176">Het is belangrijk om de classificatie van waar positief/onwaar positief te geven.</span><span class="sxs-lookup"><span data-stu-id="92394-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="92394-177">Deze classificatie wordt gebruikt om de kwaliteit van waarschuwingen te controleren en waarschuwingen nauwkeuriger te maken.</span><span class="sxs-lookup"><span data-stu-id="92394-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="92394-178">Het veld 'bepaling' definieert extra fidelity voor een 'true positive' classificatie.</span><span class="sxs-lookup"><span data-stu-id="92394-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="92394-179">Opmerkingen toevoegen en de geschiedenis van een waarschuwing weergeven</span><span class="sxs-lookup"><span data-stu-id="92394-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="92394-180">U kunt opmerkingen toevoegen en historische gebeurtenissen bekijken over een waarschuwing om eerdere wijzigingen in de waarschuwing weer te geven.</span><span class="sxs-lookup"><span data-stu-id="92394-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="92394-181">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie **Opmerkingen en geschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="92394-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="92394-182">Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="92394-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="92394-183">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="92394-183">Related topics</span></span>
- [<span data-ttu-id="92394-184">Onderdrukkende regels beheren</span><span class="sxs-lookup"><span data-stu-id="92394-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="92394-185">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="92394-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="92394-186">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="92394-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="92394-187">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="92394-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="92394-188">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="92394-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="92394-189">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="92394-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="92394-190">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="92394-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="92394-191">Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="92394-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
