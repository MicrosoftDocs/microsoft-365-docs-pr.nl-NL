---
title: Aan de slag met het waarschuwingsdashboard voor de preventie van gegevensverlies
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Ga aan de slag met het definiëren en beheren van waarschuwingen voor preventiebeleid voor gegevensverlies.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843864"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="8351b-103">Aan de slag met het waarschuwingsdashboard voor de preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="8351b-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="8351b-104">DLP-beleid (Data Loss Prevention) kan beschermende acties uitvoeren om onbedoeld delen van gevoelige items te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="8351b-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="8351b-105">Wanneer een actie wordt ondernomen voor een gevoelig item, kunt u een melding krijgen door waarschuwingen voor DLP te configureren.</span><span class="sxs-lookup"><span data-stu-id="8351b-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="8351b-106">In dit artikel wordt beschreven hoe u beleidsregels voor rich alert kunt definiëren die zijn gekoppeld aan uw DLP-beleid (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="8351b-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="8351b-107">U ziet hoe u het DLP-waarschuwingsbeheerdashboard in het [Microsoft 365 compliancecentrum](https://compliance.microsoft.com/) kunt gebruiken om waarschuwingen, gebeurtenissen en bijbehorende metagegevens voor DLP-beleidsovertredingen weer te geven. [](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)</span><span class="sxs-lookup"><span data-stu-id="8351b-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="8351b-108">Als U nog geen DLP-waarschuwingen hebt, bekijkt u Meer informatie over het dashboard waarschuwingen [voor preventie van gegevensverlies](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="8351b-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8351b-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="8351b-109">Before you begin</span></span>

<span data-ttu-id="8351b-110">Voordat u begint, moet u de benodigde vereisten hebben:</span><span class="sxs-lookup"><span data-stu-id="8351b-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="8351b-111">Licenties voor het DLP-waarschuwingenbeheerdashboard</span><span class="sxs-lookup"><span data-stu-id="8351b-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="8351b-112">Licenties voor configuratieopties voor waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8351b-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="8351b-113">Rollen</span><span class="sxs-lookup"><span data-stu-id="8351b-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="8351b-114">Licenties voor het DLP-waarschuwingsbeheerdashboard</span><span class="sxs-lookup"><span data-stu-id="8351b-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="8351b-115">Alle in aanmerking komende tenants voor Office 365 DLP hebben toegang tot het DLP-waarschuwingsbeheerdashboard.</span><span class="sxs-lookup"><span data-stu-id="8351b-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="8351b-116">Om aan de slag te gaan, moet u in aanmerking komen voor Office 365 DLP voor Exchange Online, SharePoint Online en OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="8351b-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="8351b-117">Zie Welke licenties bieden een gebruiker de rechten om van de service te profiteren voor meer informatie over de licentievereisten voor Office 365 DLP? voor [meer informatie](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)over de licentievereisten voor DLP.</span><span class="sxs-lookup"><span data-stu-id="8351b-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="8351b-118">Klanten die [Endpoint DLP](endpoint-dlp-learn-about.md) gebruiken die in aanmerking komen voor [Teams DLP,](dlp-microsoft-teams.md) zien hun waarschuwingen voor DLP-eindpuntbeleid en Teams DLP-beleidswaarschuwingen in het DLP-dashboard voor waarschuwingsbeheer.</span><span class="sxs-lookup"><span data-stu-id="8351b-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="8351b-119">De **functie Inhoudsvoorbeeld** is alleen beschikbaar voor deze licenties:</span><span class="sxs-lookup"><span data-stu-id="8351b-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="8351b-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8351b-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="8351b-121">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8351b-121">Office 365 (E5)</span></span>
- <span data-ttu-id="8351b-122">Advanced Compliance (E5) add on</span><span class="sxs-lookup"><span data-stu-id="8351b-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="8351b-123">Microsoft 365 E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="8351b-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="8351b-124">Microsft 365 E5/A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="8351b-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="8351b-125">Licenties voor configuratieopties voor waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8351b-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="8351b-126">Configuratie van een waarschuwing met één gebeurtenis: organisaties met een E1-, F1- of G1-abonnement of een E3- of **G3-abonnement** kunnen alleen waarschuwingsbeleid maken wanneer een waarschuwing wordt geactiveerd telkens wanneer een activiteit plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="8351b-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="8351b-127">**Configuratie van geaggregeerde** waarschuwingen: als u statistisch waarschuwingsbeleid wilt configureren op basis van een drempelwaarde, moet u een van de volgende licentieconfiguraties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8351b-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="8351b-128">Een E5- of G5-abonnement</span><span class="sxs-lookup"><span data-stu-id="8351b-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="8351b-129">Een E1-, F1- of G1-abonnement of een E3- of G3-abonnement met een van de volgende functies:</span><span class="sxs-lookup"><span data-stu-id="8351b-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="8351b-130">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="8351b-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="8351b-131">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="8351b-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="8351b-132">Microsoft 365 invoeglicentie voor eDiscovery en Audit</span><span class="sxs-lookup"><span data-stu-id="8351b-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="8351b-133">Rollen</span><span class="sxs-lookup"><span data-stu-id="8351b-133">Roles</span></span>


<span data-ttu-id="8351b-134">Als u het DLP-waarschuwingsbeheerdashboard wilt weergeven of de configuratieopties voor waarschuwingen in een DLP-beleid wilt bewerken, moet u lid zijn van een van deze rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="8351b-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="8351b-135">Compliancebeheerder</span><span class="sxs-lookup"><span data-stu-id="8351b-135">Compliance Administrator</span></span>
- <span data-ttu-id="8351b-136">Compliancegegevensbeheerder</span><span class="sxs-lookup"><span data-stu-id="8351b-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="8351b-137">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="8351b-137">Security Administrator</span></span>
- <span data-ttu-id="8351b-138">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="8351b-138">Security Operator</span></span>
- <span data-ttu-id="8351b-139">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="8351b-139">Security Reader</span></span>

<span data-ttu-id="8351b-140">Als u het DLP-dashboard voor waarschuwingsbeheer wilt openen, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="8351b-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="8351b-141">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="8351b-141">Manage alerts</span></span>

<span data-ttu-id="8351b-142">en een van deze twee rollen:</span><span class="sxs-lookup"><span data-stu-id="8351b-142">and either of these two roles:</span></span>

- <span data-ttu-id="8351b-143">DLP-compliancebeheer</span><span class="sxs-lookup"><span data-stu-id="8351b-143">DLP Compliance Management</span></span>
- <span data-ttu-id="8351b-144">View-Only DLP Compliance Management</span><span class="sxs-lookup"><span data-stu-id="8351b-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="8351b-145">Als u toegang wilt tot de functie Inhoudsvoorbeeld en de overeenkomende gevoelige inhoud en contextfuncties, moet u lid zijn van:</span><span class="sxs-lookup"><span data-stu-id="8351b-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="8351b-146">Inhoudsverkenner Inhoudsviewer-rollengroep</span><span class="sxs-lookup"><span data-stu-id="8351b-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="8351b-147">waarin de rol van de viewer voor gegevensclassificatieinhoud vooraf is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8351b-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="8351b-148">DLP-waarschuwingsconfiguratie</span><span class="sxs-lookup"><span data-stu-id="8351b-148">DLP alert configuration</span></span>

<span data-ttu-id="8351b-149">Zie Waar moet u beginnen met preventie van gegevensverlies voor meer informatie over het configureren van een waarschuwing in [uw DLP-beleid.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="8351b-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="8351b-150">Configuratie van gebeurteniswaarschuwingen aggregeren</span><span class="sxs-lookup"><span data-stu-id="8351b-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="8351b-151">Als uw organisatie is gelicentieerd [voor](#licensing-for-alert-configuration-options)configuratieopties voor samengevoegde waarschuwingen, ziet u deze opties wanneer u een DLP-beleid maakt of bewerkt.</span><span class="sxs-lookup"><span data-stu-id="8351b-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Schermafbeelding met opties voor incidentenrapporten voor gebruikers die in aanmerking komen voor statistische configuratieopties voor waarschuwingen." border="false":::

<span data-ttu-id="8351b-153">Met deze configuratie kunt u een beleid instellen om een waarschuwing te genereren telkens wanneer een activiteit overeenkomt met de beleidsvoorwaarden of wanneer een bepaalde drempel wordt overschreden, op basis van het aantal activiteiten of op basis van het volume van geëfiltreerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="8351b-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="8351b-154">Configuratie van waarschuwingsgegevens voor één gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="8351b-154">Single event alert configuration</span></span>

<span data-ttu-id="8351b-155">Als uw organisatie is gelicentieerd voor configuratieopties voor een waarschuwing voor één gebeurtenis, ziet u deze opties wanneer u een [DLP-beleid](#licensing-for-alert-configuration-options)maakt of bewerkt.</span><span class="sxs-lookup"><span data-stu-id="8351b-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="8351b-156">Gebruik deze optie om een waarschuwing te maken die telkens wordt verhoogd wanneer een DLP-regel wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8351b-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Schermafbeelding met opties voor incidentrapporten voor gebruikers die in aanmerking komen voor configuratieopties voor een waarschuwing voor één gebeurtenis." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="8351b-158">Een DLP-waarschuwing onderzoeken</span><span class="sxs-lookup"><span data-stu-id="8351b-158">Investigate a DLP alert</span></span>

<span data-ttu-id="8351b-159">Werken met het DLP-dashboard voor waarschuwingsbeheer:</span><span class="sxs-lookup"><span data-stu-id="8351b-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="8351b-160">Ga in [Microsoft 365 compliancecentrum](https://www.compliance.microsoft.com)naar **Preventie van gegevensverlies.**</span><span class="sxs-lookup"><span data-stu-id="8351b-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="8351b-161">Selecteer het **tabblad Waarschuwingen** om het dashboard met DLP-waarschuwingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8351b-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="8351b-162">Selecteer een waarschuwing om details te zien:</span><span class="sxs-lookup"><span data-stu-id="8351b-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Schermafbeelding met waarschuwingsdetails in het DLP-dashboard voor waarschuwingsbeheer." border="false":::

4. <span data-ttu-id="8351b-164">Selecteer het **tabblad** Gebeurtenissen om alle gebeurtenissen weer te geven die aan de waarschuwing zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="8351b-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="8351b-165">U kunt een bepaalde gebeurtenis kiezen om de details ervan weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8351b-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="8351b-166">Zie Meer informatie over het dashboard Waarschuwingen voor preventie van gegevensverlies voor een lijst met enkele beschikbare [gebeurtenisdetails.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="8351b-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="8351b-167">Selecteer **Details** om de pagina **Overzicht voor** de waarschuwing te openen.</span><span class="sxs-lookup"><span data-stu-id="8351b-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="8351b-168">De overzichtspagina bevat een overzicht:</span><span class="sxs-lookup"><span data-stu-id="8351b-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="8351b-169">van wat er is gebeurd</span><span class="sxs-lookup"><span data-stu-id="8351b-169">of what happened</span></span>
    1. <span data-ttu-id="8351b-170">wie de acties heeft uitgevoerd die de beleidsmatch hebben veroorzaakt</span><span class="sxs-lookup"><span data-stu-id="8351b-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="8351b-171">informatie over het overeenkomende beleid en meer</span><span class="sxs-lookup"><span data-stu-id="8351b-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="8351b-172">Kies het **tabblad Gebeurtenissen** om toegang te krijgen tot het volgende:</span><span class="sxs-lookup"><span data-stu-id="8351b-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="8351b-173">betrokken inhoud</span><span class="sxs-lookup"><span data-stu-id="8351b-173">content involved</span></span>
    1. <span data-ttu-id="8351b-174">overeenkomende typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="8351b-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="8351b-175">metagegevens</span><span class="sxs-lookup"><span data-stu-id="8351b-175">metadata</span></span>

7. <span data-ttu-id="8351b-176">Selecteer het **tabblad Gevoelige infotypen** om details weer te geven over de gevoelige informatietypen die in de inhoud zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8351b-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="8351b-177">Details zijn betrouwbaarheid, aantal en de inhoud die overeenkomt met het gevoelige informatietype.</span><span class="sxs-lookup"><span data-stu-id="8351b-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="8351b-178">Nadat u de waarschuwing hebt  onderzocht, gaat u terug naar het tabblad Overzicht waar u triage kunt beheren en de positie van de waarschuwing kunt beheren en opmerkingen kunt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="8351b-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="8351b-179">Als u de geschiedenis van werkstroombeheer wilt bekijken, kiest u **Managementlogboek.**</span><span class="sxs-lookup"><span data-stu-id="8351b-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="8351b-180">Nadat u de vereiste actie voor de waarschuwing hebt ondernomen, stelt u de status van de waarschuwing in op **Opgelost.**</span><span class="sxs-lookup"><span data-stu-id="8351b-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8351b-181">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8351b-181">See also</span></span>

- [<span data-ttu-id="8351b-182">Meer informatie over waarschuwingen voor preventie van gegevensverlies en het dashboard waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="8351b-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="8351b-183">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="8351b-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)