---
title: Waarschuwingen voor anomaliedetectie onderzoeken
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Waarschuwingen voor anomaliedetectie onderzoeken.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420242"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="99cc6-103">Waarschuwingen voor anomaliedetectie onderzoeken</span><span class="sxs-lookup"><span data-stu-id="99cc6-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="99cc6-104">Microsoft App-governance biedt beveiligingsdetecties en -waarschuwingen voor schadelijke activiteiten.</span><span class="sxs-lookup"><span data-stu-id="99cc6-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="99cc6-105">Het doel van deze handleiding is om u algemene en praktische informatie te bieden over elke waarschuwing, om u te helpen bij uw onderzoeks- en hersteltaken.</span><span class="sxs-lookup"><span data-stu-id="99cc6-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="99cc6-106">Deze handleiding bevat algemene informatie over de voorwaarden voor het activeren van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="99cc6-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="99cc6-107">Omdat anomaliedetecties van nature niet-deterministisch zijn, worden ze alleen geactiveerd wanneer er gedrag plaatsvindt dat afwijkt van de norm.</span><span class="sxs-lookup"><span data-stu-id="99cc6-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="99cc6-108">Ten slotte kunnen sommige waarschuwingen in preview zijn, dus bekijk regelmatig de officiële documentatie voor de bijgewerkte waarschuwingsstatus.</span><span class="sxs-lookup"><span data-stu-id="99cc6-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="99cc6-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="99cc6-109">MITRE ATT&CK</span></span>

<span data-ttu-id="99cc6-110">Om het gemakkelijker te maken om de relatie tussen waarschuwingen voor Microsoft-app-governance en de bekende MITRE ATT&CK Matrix in kaart te brengen, hebben we de waarschuwingen gecategoriseerd op basis van hun overeenkomstige MITRE ATT&CK-tactiek.</span><span class="sxs-lookup"><span data-stu-id="99cc6-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="99cc6-111">Deze aanvullende verwijzing maakt het gemakkelijker om de vermoedelijke aanvalstechniek te begrijpen die mogelijk wordt gebruikt wanneer de Microsoft Application Security en Governance-waarschuwing wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="99cc6-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="99cc6-112">Deze handleiding bevat informatie over het onderzoeken en oplossen van waarschuwingen voor Microsoft-app-governance in de volgende categorieën.</span><span class="sxs-lookup"><span data-stu-id="99cc6-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="99cc6-113">Initiële toegang</span><span class="sxs-lookup"><span data-stu-id="99cc6-113">Initial Access</span></span>
- <span data-ttu-id="99cc6-114">Uitvoering</span><span class="sxs-lookup"><span data-stu-id="99cc6-114">Execution</span></span>
- <span data-ttu-id="99cc6-115">Persistentie</span><span class="sxs-lookup"><span data-stu-id="99cc6-115">Persistence</span></span>
- <span data-ttu-id="99cc6-116">Escalatie van bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="99cc6-116">Privilege Escalation</span></span>
- <span data-ttu-id="99cc6-117">Ontwijking van verdediging</span><span class="sxs-lookup"><span data-stu-id="99cc6-117">Defense Evasion</span></span>
- <span data-ttu-id="99cc6-118">Toegang tot referenties</span><span class="sxs-lookup"><span data-stu-id="99cc6-118">Credential Access</span></span>
- <span data-ttu-id="99cc6-119">Verzameling</span><span class="sxs-lookup"><span data-stu-id="99cc6-119">Collection</span></span>
- <span data-ttu-id="99cc6-120">Exfiltratie</span><span class="sxs-lookup"><span data-stu-id="99cc6-120">Exfiltration</span></span>
- <span data-ttu-id="99cc6-121">Impact</span><span class="sxs-lookup"><span data-stu-id="99cc6-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="99cc6-122">Classificaties van beveiligingswaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="99cc6-122">Security alert classifications</span></span>

<span data-ttu-id="99cc6-123">Na goed onderzoek kunnen alle waarschuwingen voor Microsoft-app-governance worden geclassificeerd als een van de volgende activiteitstypen:</span><span class="sxs-lookup"><span data-stu-id="99cc6-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="99cc6-124">Terecht-positief (TP): een waarschuwing over een bevestigde schadelijke activiteit.</span><span class="sxs-lookup"><span data-stu-id="99cc6-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="99cc6-125">Goedaardig terecht-positief (B-TP): een waarschuwing over verdachte maar niet schadelijke activiteiten, zoals een penetratietest of andere geautoriseerde verdachte actie.</span><span class="sxs-lookup"><span data-stu-id="99cc6-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="99cc6-126">Fout-positief (FP): een waarschuwing voor een niet-schadelijke activiteit.</span><span class="sxs-lookup"><span data-stu-id="99cc6-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="99cc6-127">Algemene onderzoeksstappen</span><span class="sxs-lookup"><span data-stu-id="99cc6-127">General investigation steps</span></span>

<span data-ttu-id="99cc6-128">Gebruik de volgende algemene richtlijnen bij het onderzoeken van een type waarschuwing om een duidelijker beeld te krijgen van de mogelijke bedreiging voordat u de aanbevolen actie toepast.</span><span class="sxs-lookup"><span data-stu-id="99cc6-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="99cc6-129">Controleer het ernstniveau van de app en vergelijk deze met de rest van de apps in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="99cc6-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="99cc6-130">Met deze beoordeling kunt u bepalen welke apps in uw Tenant een groter risico vormen.</span><span class="sxs-lookup"><span data-stu-id="99cc6-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="99cc6-131">Als u een TP identificeert, bekijk dan alle app-activiteiten om inzicht te krijgen in de impact.</span><span class="sxs-lookup"><span data-stu-id="99cc6-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="99cc6-132">Bekijk bijvoorbeeld de volgende app-informatie:</span><span class="sxs-lookup"><span data-stu-id="99cc6-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="99cc6-133">Bereiken waarvoor toegang is verleend</span><span class="sxs-lookup"><span data-stu-id="99cc6-133">Scopes granted access</span></span>
  - <span data-ttu-id="99cc6-134">Ongebruikelijk gedrag</span><span class="sxs-lookup"><span data-stu-id="99cc6-134">Unusual behavior</span></span>  
  - <span data-ttu-id="99cc6-135">IP-adres en locatie</span><span class="sxs-lookup"><span data-stu-id="99cc6-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="99cc6-136">Waarschuwingen voor initiële toegang</span><span class="sxs-lookup"><span data-stu-id="99cc6-136">Initial access alerts</span></span>

<span data-ttu-id="99cc6-137">In deze sectie worden waarschuwingen beschreven die aangeven dat een schadelijke app probeert voet aan de grond te houden in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="99cc6-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="99cc6-138">Gecodeerde app-naam met verdachte toestemmingsbereiken</span><span class="sxs-lookup"><span data-stu-id="99cc6-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="99cc6-139">**Ernst**: gemiddeld</span><span class="sxs-lookup"><span data-stu-id="99cc6-139">**Severity:** Medium</span></span>

<span data-ttu-id="99cc6-140">**Beschrijving**: met deze detectie worden OAuth-apps geïdentificeerd met tekens, zoals Unicode- of gecodeerde tekens, die zijn aangevraagd voor verdachte toestemmingsbereiken en die toegang hebben verkregen tot e-mailmappen van gebruikers via de Graph API.</span><span class="sxs-lookup"><span data-stu-id="99cc6-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="99cc6-141">Deze waarschuwing kan duiden op een poging om een schadelijke app te camoufleren als een bekende en vertrouwde app, zodat kwaadwillenden de gebruikers kunnen misleiden om toestemming te geven voor de schadelijke app.</span><span class="sxs-lookup"><span data-stu-id="99cc6-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="99cc6-142">**TP of FP?**</span><span class="sxs-lookup"><span data-stu-id="99cc6-142">**TP or FP?**</span></span>

- <span data-ttu-id="99cc6-143">**TP-**: als u kunt bevestigen dat de OAuth-app de weergavenaam heeft gecodeerd met verdachte bereiken die afkomstig zijn van een onbekende bron, wordt een terecht-positief aangegeven.</span><span class="sxs-lookup"><span data-stu-id="99cc6-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="99cc6-144">**Aanbevolen actie**: controleer het machtigingsniveau dat door deze app is aangevraagd en welke gebruikers toegang hebben verleend.</span><span class="sxs-lookup"><span data-stu-id="99cc6-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="99cc6-145">Op basis van uw onderzoek kunt u ervoor kiezen om de toegang tot deze app te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="99cc6-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="99cc6-146">Als u de toegang tot de app wilt blokkeren, selecteert u op de pagina OAuth-apps, in de rij met de app die u wilt blokkeren, het blokkeringspictogram.</span><span class="sxs-lookup"><span data-stu-id="99cc6-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="99cc6-147">U kunt kiezen of u gebruikers wilt laten weten dat de app die ze hebben geïnstalleerd en geautoriseerd, is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="99cc6-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="99cc6-148">De melding laat gebruikers weten dat de app wordt uitgeschakeld en dat ze niet langer toegang hebben tot de verbonden app.</span><span class="sxs-lookup"><span data-stu-id="99cc6-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="99cc6-149">Als u niet wilt dat ze het te weten komen, deselecteert u Gebruikers informeren die toegang hebben verleend tot deze verboden app in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="99cc6-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="99cc6-150">We raden u aan app-gebruikers te laten weten dat hun app binnenkort wordt geblokkeerd voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="99cc6-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="99cc6-151">**FP**: als u wilt bevestigen dat de app een gecodeerde naam heeft, maar een legitiem zakelijk gebruik in de organisatie heeft.</span><span class="sxs-lookup"><span data-stu-id="99cc6-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="99cc6-152">**Aanbevolen actie**: sluit de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="99cc6-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="99cc6-153">Inzicht in het bereik van de schending</span><span class="sxs-lookup"><span data-stu-id="99cc6-153">Understand the scope of the breach</span></span>

<span data-ttu-id="99cc6-154">Volg de zelfstudie over het [onderzoeken van riskante OAuth-apps](/cloud-app-security/investigate-risky-oauth).</span><span class="sxs-lookup"><span data-stu-id="99cc6-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="99cc6-155">OAuth-app met leesbereiken heeft verdachte antwoord-URL</span><span class="sxs-lookup"><span data-stu-id="99cc6-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="99cc6-156">**Ernst**: gemiddeld</span><span class="sxs-lookup"><span data-stu-id="99cc6-156">**Severity**: Medium</span></span>

<span data-ttu-id="99cc6-157">**Beschrijving**: deze detectie identificeert een OAuth-app met alleen leesbereiken zoals User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared omleiden naar verdachte antwoord-URL via Graph API.</span><span class="sxs-lookup"><span data-stu-id="99cc6-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="99cc6-158">Met deze activiteit wordt geprobeerd aan te geven dat schadelijke apps met minder machtigingen (zoals leesbereiken) kunnen worden misbruikt om gebruikersaccountverkenningen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="99cc6-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="99cc6-159">**TP of FP?**</span><span class="sxs-lookup"><span data-stu-id="99cc6-159">**TP or FP?**</span></span>

- <span data-ttu-id="99cc6-160">**TP-**: als u kunt bevestigen dat de OAuth-app met leesbereik wordt geleverd vanuit een onbekende bron en wordt omgeleid naar een verdachte URL, wordt een terecht-positief aangegeven.</span><span class="sxs-lookup"><span data-stu-id="99cc6-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="99cc6-161">**Aanbevolen actie**: controleer de antwoord-URL en bereiken die door de app zijn aangevraagd.</span><span class="sxs-lookup"><span data-stu-id="99cc6-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="99cc6-162">Op basis van uw onderzoek kunt u ervoor kiezen om de toegang tot deze app te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="99cc6-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="99cc6-163">Controleer het machtigingsniveau dat door deze app is aangevraagd en welke gebruikers toegang hebben verleend.</span><span class="sxs-lookup"><span data-stu-id="99cc6-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="99cc6-164">Als u de toegang tot de app wilt blokkeren, selecteert u op de pagina OAuth-apps, in de rij met de app die u wilt blokkeren, het blokkeringspictogram.</span><span class="sxs-lookup"><span data-stu-id="99cc6-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="99cc6-165">U kunt kiezen of u gebruikers wilt laten weten dat de app die ze hebben geïnstalleerd en geautoriseerd, is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="99cc6-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="99cc6-166">De melding laat gebruikers weten dat de app wordt uitgeschakeld en dat ze niet langer toegang hebben tot de verbonden app.</span><span class="sxs-lookup"><span data-stu-id="99cc6-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="99cc6-167">Als u niet wilt dat ze het te weten komen, deselecteert u Gebruikers informeren die toegang hebben verleend tot deze verboden app in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="99cc6-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="99cc6-168">We raden u aan app-gebruikers te laten weten dat hun app binnenkort wordt geblokkeerd voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="99cc6-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="99cc6-169">**B-TP-**: als u na onderzoek kunt bevestigen dat de app een legitiem zakelijk gebruik heeft in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="99cc6-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="99cc6-170">**Aanbevolen actie**: sluit de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="99cc6-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="99cc6-171">Inzicht in het bereik van de schending</span><span class="sxs-lookup"><span data-stu-id="99cc6-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="99cc6-172">Bekijk alle activiteiten die door de app zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="99cc6-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="99cc6-173">Als u vermoedt dat een app verdacht is, raden we u aan de naam en antwoord-URL van de app te onderzoeken in verschillende app-stores.</span><span class="sxs-lookup"><span data-stu-id="99cc6-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="99cc6-174">Wanneer u app-stores controleert, richt u zich op de volgende typen apps:</span><span class="sxs-lookup"><span data-stu-id="99cc6-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="99cc6-175">Apps die onlangs zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="99cc6-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="99cc6-176">Apps met een verdachte antwoord-URL</span><span class="sxs-lookup"><span data-stu-id="99cc6-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="99cc6-177">Apps die niet recent zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="99cc6-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="99cc6-178">Als er geen updates zijn, wordt de app mogelijk niet meer ondersteund.</span><span class="sxs-lookup"><span data-stu-id="99cc6-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="99cc6-179">Als u nog steeds vermoedt dat een app verdacht is, kunt u de naam van de app, de naam van de uitgever en de antwoord-URL online onderzoeken</span><span class="sxs-lookup"><span data-stu-id="99cc6-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="99cc6-180">Persistentiewaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="99cc6-180">Persistence alerts</span></span>

<span data-ttu-id="99cc6-181">In deze sectie worden waarschuwingen beschreven die aangeven dat een kwaadwillende actor probeert voet aan de grond te houden in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="99cc6-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="99cc6-182">App met verdacht OAuth-bereik maakt Postvak IN-regel</span><span class="sxs-lookup"><span data-stu-id="99cc6-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="99cc6-183">**Ernst**: gemiddeld</span><span class="sxs-lookup"><span data-stu-id="99cc6-183">**Severity**: Medium</span></span>

<span data-ttu-id="99cc6-184">**MITRE-id's**: T1137.005, T1114</span><span class="sxs-lookup"><span data-stu-id="99cc6-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="99cc6-185">Deze detectie identificeert een OAuth-app die toestemming heeft verleend voor verdachte bereiken, een verdachte regel voor Postvak IN heeft gemaakt en vervolgens de e-mailmappen en berichten van gebruikers heeft geopend via de Graph API.</span><span class="sxs-lookup"><span data-stu-id="99cc6-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="99cc6-186">Regels voor Postvak IN, zoals het doorsturen van alle of specifieke e-mailberichten naar een ander e-mailaccount en Graph-aanroepen voor toegang tot e-mailberichten en het verzenden naar een ander e-mailaccount, kunnen een poging zijn om gegevens van uw organisatie te exfiltreren.</span><span class="sxs-lookup"><span data-stu-id="99cc6-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="99cc6-187">**TP of FP?**</span><span class="sxs-lookup"><span data-stu-id="99cc6-187">**TP or FP?**</span></span>

- <span data-ttu-id="99cc6-188">**TP**: als u kunt bevestigen dat de regel voor postvak IN is gemaakt door een OAuth-app van derden met verdachte bereiken die afkomstig zijn van een onbekende bron, wordt een terecht-positief aangegeven.</span><span class="sxs-lookup"><span data-stu-id="99cc6-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="99cc6-189">**Aanbevolen actie**: de app uitschakelen en verwijderen, het wachtwoord opnieuw instellen en de regel postvak IN verwijderen.</span><span class="sxs-lookup"><span data-stu-id="99cc6-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="99cc6-190">Volg de zelfstudie over het opnieuw instellen van een wachtwoord met Azure Active Directory en volg de zelfstudie over het verwijderen van regels voor Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="99cc6-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="99cc6-191">**FP**: als u kunt bevestigen dat de app om legitieme redenen een regel voor postvak IN heeft gemaakt voor een nieuw of persoonlijk extern e-mailaccount.</span><span class="sxs-lookup"><span data-stu-id="99cc6-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="99cc6-192">**Aanbevolen actie**: sluit de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="99cc6-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="99cc6-193">Inzicht in het bereik van de schending</span><span class="sxs-lookup"><span data-stu-id="99cc6-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="99cc6-194">Bekijk alle activiteiten die door de app zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="99cc6-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="99cc6-195">Controleer de bereiken die door de app zijn verleend.</span><span class="sxs-lookup"><span data-stu-id="99cc6-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="99cc6-196">Controleer de regelactie en voorwaarde voor postvak IN die door de app zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="99cc6-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="99cc6-197">Verzamelingswaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="99cc6-197">Collection alerts</span></span>

<span data-ttu-id="99cc6-198">In deze sectie worden waarschuwingen beschreven die aangeven dat een kwaadwillende actor mogelijk gegevens probeert te verzamelen die van belang zijn voor het doel van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="99cc6-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="99cc6-199">App heeft afwijkende Graph-aanroepen gedaan om e-mail te lezen</span><span class="sxs-lookup"><span data-stu-id="99cc6-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="99cc6-200">**Ernst**: gemiddeld</span><span class="sxs-lookup"><span data-stu-id="99cc6-200">**Severity**: Medium</span></span>

<span data-ttu-id="99cc6-201">**MITRE-ID**: T1114</span><span class="sxs-lookup"><span data-stu-id="99cc6-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="99cc6-202">Deze detectie identificeert wanneer de Line of Business (LOB) OAuth-app toegang krijgt tot een ongebruikelijk en groot aantal e-mailmappen en berichten van gebruikers via de Graph API, wat kan wijzen op een poging tot inbreuk op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="99cc6-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="99cc6-203">**TP of FP?**</span><span class="sxs-lookup"><span data-stu-id="99cc6-203">**TP or FP?**</span></span>

- <span data-ttu-id="99cc6-204">**TP**: als u kunt bevestigen dat de ongebruikelijke Graph-activiteit is uitgevoerd door de Line of Business (LOB) OAuth-app, wordt een terecht-positief aangegeven.</span><span class="sxs-lookup"><span data-stu-id="99cc6-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="99cc6-205">**Acties aanbevelen**: schakel de app tijdelijk uit, stel het wachtwoord opnieuw in en schakel de app opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="99cc6-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="99cc6-206">Volg de zelfstudie over het Opnieuw instellen van een wachtwoord met behulp van Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99cc6-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="99cc6-207">**FP**: als u kunt bevestigen dat de app is bedoeld om ongebruikelijk grote hoeveelheden Graph-aanroepen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="99cc6-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="99cc6-208">**Aanbevolen actie**: sluit de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="99cc6-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="99cc6-209">Inzicht in het bereik van de schending</span><span class="sxs-lookup"><span data-stu-id="99cc6-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="99cc6-210">Controleer het activiteitenlogboek op gebeurtenissen die door deze app worden uitgevoerd om meer inzicht te krijgen in andere Graph-activiteiten om e-mailberichten te lezen en gevoelige e-mailgegevens van gebruikers te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="99cc6-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="99cc6-211">Controleer op onverwachte referenties die worden toegevoegd aan de app.</span><span class="sxs-lookup"><span data-stu-id="99cc6-211">Monitor for unexpected credential being added to the app.</span></span>
