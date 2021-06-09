---
title: Herstel beveiligingslekken met Threat and Vulnerability Management
description: Herstel beveiligingszwaktes die zijn ontdekt door beveiligingsaanbevelingen en maak zo nodig uitzonderingen in Threat and Vulnerability Management.
keywords: Microsoft Defender for Endpoint tvm remediation, Microsoft Defender for Endpoint tvm, Threat and Vulnerability Management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
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
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840908"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="79786-104">Herstel beveiligingslekken met Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="79786-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79786-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="79786-105">**Applies to:**</span></span>
- [<span data-ttu-id="79786-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="79786-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="79786-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="79786-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="79786-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79786-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="79786-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="79786-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79786-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="79786-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="79786-111">Herstelverzoeken</span><span class="sxs-lookup"><span data-stu-id="79786-111">Request remediation</span></span>

<span data-ttu-id="79786-112">De Threat and Vulnerability Management in Microsoft Defender voor Eindpunt overbrugt de kloof tussen beveiligings- en IT-beheerders via de werkstroom voor herstelverzoeken.</span><span class="sxs-lookup"><span data-stu-id="79786-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="79786-113">Beveiligingsbeheerders zoals u kunnen de IT-beheerder vragen om  een beveiligingsprobleem op te verhelpen van de pagina's met beveiligingsaanbevelingen naar Intune.</span><span class="sxs-lookup"><span data-stu-id="79786-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="79786-114">Verbinding Microsoft Intune inschakelen</span><span class="sxs-lookup"><span data-stu-id="79786-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="79786-115">Als u deze mogelijkheid wilt gebruiken, kunt u uw Microsoft Intune inschakelen.</span><span class="sxs-lookup"><span data-stu-id="79786-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="79786-116">Ga in Microsoft Defender-beveiligingscentrum naar de **Instellingen**  >  **Algemene**  >  **geavanceerde functies.**</span><span class="sxs-lookup"><span data-stu-id="79786-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="79786-117">Schuif omlaag en zoek naar **Microsoft Intune verbinding.**</span><span class="sxs-lookup"><span data-stu-id="79786-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="79786-118">De schakelknop is standaard uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="79786-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="79786-119">Schakel de **Microsoft Intune-verbinding** **in.**</span><span class="sxs-lookup"><span data-stu-id="79786-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="79786-120">**Opmerking:** Als de Intune-verbinding is ingeschakeld, krijgt u een optie om een Intune-beveiligingstaak te maken wanneer u een herstelaanvraag maakt.</span><span class="sxs-lookup"><span data-stu-id="79786-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="79786-121">Deze optie wordt niet weergegeven als de verbinding niet is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="79786-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="79786-122">Zie [Intune gebruiken om beveiligingslekken](/intune/atp-manage-vulnerabilities) te verhelpen die zijn geïdentificeerd door Microsoft Defender voor Eindpunt voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79786-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="79786-123">Stappen voor herstelverzoeken</span><span class="sxs-lookup"><span data-stu-id="79786-123">Remediation request steps</span></span>

1. <span data-ttu-id="79786-124">Ga naar het Threat and Vulnerability Management navigatiemenu in de Microsoft Defender-beveiligingscentrum en selecteer [**Beveiligingsaanbevelingen.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="79786-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="79786-125">Selecteer een beveiligingsaanbeveling voor wie u herstel wilt aanvragen en selecteer vervolgens **Herstelopties.**</span><span class="sxs-lookup"><span data-stu-id="79786-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="79786-126">Vul het formulier in, inclusief waar u herstel voor aanvraagt, toepasselijke apparaatgroepen, prioriteit, einddatum en optionele notities.</span><span class="sxs-lookup"><span data-stu-id="79786-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="79786-127">Als u de optie 'aandacht vereist' kiest, is het selecteren van een einddatum niet beschikbaar omdat er geen specifieke actie is.</span><span class="sxs-lookup"><span data-stu-id="79786-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="79786-128">Selecteer **Aanvraag indienen.**</span><span class="sxs-lookup"><span data-stu-id="79786-128">Select **Submit request**.</span></span> <span data-ttu-id="79786-129">Als u een herstelaanvraag indient, wordt binnen Threat and Vulnerability Management een herstelactiviteitsitem gemaakt, dat kan worden gebruikt voor het controleren van de herstel voortgang voor deze aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="79786-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="79786-130">Hiermee wordt geen herstel veroorzaakt of worden er geen wijzigingen toegepast op apparaten.</span><span class="sxs-lookup"><span data-stu-id="79786-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="79786-131">Informeer uw IT-beheerder over de nieuwe aanvraag en laat deze zich aanmelden bij Intune om de aanvraag goed te keuren of te weigeren en een pakketimplementatie te starten.</span><span class="sxs-lookup"><span data-stu-id="79786-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="79786-132">Ga naar de [**pagina Herstel om**](tvm-remediation.md) de status van uw herstelaanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="79786-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="79786-133">Als u wilt controleren hoe het ticket in Intune wordt aangegeven, raadpleegt u [Intune](/intune/atp-manage-vulnerabilities) gebruiken om beveiligingslekken te verhelpen die zijn geïdentificeerd door Microsoft Defender voor Eindpunt voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79786-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="79786-134">Als uw aanvraag betrekking heeft op het herstellen van meer dan 10.000 apparaten, kunnen we slechts 10.000 apparaten voor herstel naar Intune verzenden.</span><span class="sxs-lookup"><span data-stu-id="79786-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="79786-135">Nadat de zwakke punten van uw organisatie op het [](tvm-security-recommendation.md)gebied van cyberbeveiliging zijn geïdentificeerd en in kaart zijn gebracht aan actiebare beveiligingsaanbevelingen, begint u met het maken van beveiligingstaken.</span><span class="sxs-lookup"><span data-stu-id="79786-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="79786-136">U kunt taken maken via de integratie met Microsoft Intune waar hersteltickets worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="79786-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="79786-137">Verhoog de blootstelling van uw organisatie door beveiligingsproblemen en verhoog de beveiligingsconfiguratie door de beveiligingsaanbevelingen te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="79786-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="79786-138">Uw herstelactiviteiten weergeven</span><span class="sxs-lookup"><span data-stu-id="79786-138">View your remediation activities</span></span>

<span data-ttu-id="79786-139">Wanneer u een herstelaanvraag vanaf de pagina Beveiligingsaanbevelingen indient, wordt een herstelactiviteit afgetrapt.</span><span class="sxs-lookup"><span data-stu-id="79786-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="79786-140">Er wordt een beveiligingstaak gemaakt die kan worden  bij Threat and Vulnerability Management herstelpagina en een herstelticket wordt gemaakt in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="79786-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="79786-141">Als u de optie 'aandacht vereist' kiest, is er geen voortgangsbalk, ticketstatus of einddatum omdat er geen werkelijke actie is die we kunnen controleren.</span><span class="sxs-lookup"><span data-stu-id="79786-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="79786-142">Wanneer u zich op de pagina Herstel hebt geplaatst, selecteert u de herstelactiviteit die u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="79786-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="79786-143">U kunt de herstelstappen volgen, de voortgang bijhouden, de gerelateerde aanbeveling bekijken, exporteren naar CSV of markeren als voltooid.</span><span class="sxs-lookup"><span data-stu-id="79786-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="79786-144">![Voorbeeld van de pagina Herstel, met een geselecteerde herstelactiviteit, en de flyout van die activiteit met de beschrijving, hulpprogramma's voor IT-service- en apparaatbeheer en de voortgang van de apparaatsanering.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="79786-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="79786-145">Er is een bewaarperiode van 180 dagen voor voltooide herstelactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="79786-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="79786-146">Als u de herstelpagina optimaal wilt laten functioneren, wordt de herstelactiviteit zes maanden na voltooiing verwijderd.</span><span class="sxs-lookup"><span data-stu-id="79786-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="79786-147">Voltooid per kolom</span><span class="sxs-lookup"><span data-stu-id="79786-147">Completed by column</span></span>

<span data-ttu-id="79786-148">Houd bij wie de herstelactiviteit heeft gesloten met de kolom Voltooid door op de pagina Herstel.</span><span class="sxs-lookup"><span data-stu-id="79786-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="79786-149">**E-mailadres:** het e-mailadres van de persoon die de taak handmatig heeft voltooid</span><span class="sxs-lookup"><span data-stu-id="79786-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="79786-150">**Systeembevestiging:** de taak is automatisch voltooid (alle apparaten zijn gesaneerd)</span><span class="sxs-lookup"><span data-stu-id="79786-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="79786-151">**N/B:** Informatie is niet beschikbaar omdat we niet weten hoe deze oudere taak is voltooid</span><span class="sxs-lookup"><span data-stu-id="79786-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Gemaakt door en voltooid door kolommen met twee rijen.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="79786-154">Belangrijkste herstelactiviteiten in het dashboard</span><span class="sxs-lookup"><span data-stu-id="79786-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="79786-155">Bekijk **de belangrijkste herstelactiviteiten** in het [Threat and Vulnerability Management dashboard.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="79786-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="79786-156">Selecteer een van de items om naar de pagina **Herstel te** gaan.</span><span class="sxs-lookup"><span data-stu-id="79786-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="79786-157">U kunt de herstelactiviteit markeren als voltooid nadat het IT-beheerteam de taak heeft gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="79786-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Voorbeeld van de kaart Top herstelactiviteiten met een tabel met de belangrijkste activiteiten die zijn gegenereerd op basis van beveiligingsaanbevelingen.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="79786-159">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="79786-159">Related articles</span></span>

- [<span data-ttu-id="79786-160">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="79786-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="79786-161">Dashboard</span><span class="sxs-lookup"><span data-stu-id="79786-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="79786-162">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="79786-162">Security recommendations</span></span>](tvm-security-recommendation.md)