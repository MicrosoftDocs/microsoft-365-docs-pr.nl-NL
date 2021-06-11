---
title: Een phishing-aanval simuleren met Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe ze phishingaanvallen kunnen simuleren en hun gebruikers kunnen trainen op phishingpreventie met behulp van training voor aanvalssimulatie in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: d82e7544e6795e4514cf1949645107c53fc69c61
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878362"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="35175-103">Een phishing-aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="35175-103">Simulate a phishing attack</span></span>

<span data-ttu-id="35175-104">**Van toepassing op** [Microsoft Defender voor Office 365 abonnement 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="35175-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="35175-105">Met training voor aanvalssimulatie in Microsoft Defender voor Office 365 kunt u goedaardige cyberaanvallensimulaties uitvoeren op uw organisatie om uw beveiligingsbeleid en -procedures te testen, en uw werknemers trainen om hun bekendheid te vergroten en hun gevoeligheid voor aanvallen te verminderen.</span><span class="sxs-lookup"><span data-stu-id="35175-105">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="35175-106">In dit artikel wordt u beschreven hoe u een gesimuleerde phishing-aanval maakt met behulp van training voor een aanvalssimulatie.</span><span class="sxs-lookup"><span data-stu-id="35175-106">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="35175-107">Zie Aan de slag met de trainingstraining [Aanvalssimulatie](attack-simulation-training-get-started.md)voor informatie over de training voor aanvalssimulaties.</span><span class="sxs-lookup"><span data-stu-id="35175-107">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="35175-108">Als u een gesimuleerde phishing-aanval wilt starten, opent u de Microsoft 365 Defender-portal (), gaat u naar E-mail & samenwerkingSsimulatietraining aanvallen en gaat u naar het tabblad <https://security.microsoft.com/>  \>  **[Simulaties.](https://security.microsoft.com/attacksimulator?viewid=simulations)**</span><span class="sxs-lookup"><span data-stu-id="35175-108">To launch a simulated phishing attack, open the Microsoft 365 Defender portal (<https://security.microsoft.com/>), go to **Email & collaboration** \> **Attack simulation training**, and switch to the **[Simulations](https://security.microsoft.com/attacksimulator?viewid=simulations)** tab.</span></span>

<span data-ttu-id="35175-109">Selecteer **onder Simulaties** de **optie + Een simulatie starten.**</span><span class="sxs-lookup"><span data-stu-id="35175-109">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Een simulatieknop starten in de Microsoft 365 Defender-portal](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="35175-111">Op elk moment tijdens het maken van de simulatie kunt u opslaan en sluiten om de simulatie op een later tijdstip te blijven configureren.</span><span class="sxs-lookup"><span data-stu-id="35175-111">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="35175-112">Een social engineering-techniek selecteren</span><span class="sxs-lookup"><span data-stu-id="35175-112">Selecting a social engineering technique</span></span>

<span data-ttu-id="35175-113">Selecteer uit 4 verschillende technieken, samengesteld uit het [MITRE ATT-&CK® framework.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="35175-113">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="35175-114">Er zijn verschillende payloads beschikbaar voor verschillende technieken:</span><span class="sxs-lookup"><span data-stu-id="35175-114">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="35175-115">**Referentiesoogst** probeert referenties te verzamelen door gebruikers naar een bekende website te nemen met invoervakken om een gebruikersnaam en wachtwoord in te dienen.</span><span class="sxs-lookup"><span data-stu-id="35175-115">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="35175-116">**Malwarebijlage** voegt een schadelijke bijlage toe aan een bericht.</span><span class="sxs-lookup"><span data-stu-id="35175-116">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="35175-117">Wanneer de gebruiker de bijlage opent, wordt willekeurige code uitgevoerd die de aanvaller helpt het apparaat van het doel te compromitteerden.</span><span class="sxs-lookup"><span data-stu-id="35175-117">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="35175-118">**Koppeling in bijlage** is een type referentieoogst hybride.</span><span class="sxs-lookup"><span data-stu-id="35175-118">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="35175-119">Een aanvaller voegt een URL in een e-mailbijlage in.</span><span class="sxs-lookup"><span data-stu-id="35175-119">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="35175-120">De URL in de bijlage volgt dezelfde techniek als referentieoogst.</span><span class="sxs-lookup"><span data-stu-id="35175-120">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="35175-121">**Als u een koppeling naar malware** maakt, wordt een willekeurige code uitgevoerd van een bestand dat wordt gehost op een bekende service voor het delen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="35175-121">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="35175-122">Het bericht dat naar de gebruiker wordt verzonden, bevat een koppeling naar dit schadelijke bestand.</span><span class="sxs-lookup"><span data-stu-id="35175-122">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="35175-123">Het bestand openen en de aanvaller helpen het apparaat van het doel te compromitteerden.</span><span class="sxs-lookup"><span data-stu-id="35175-123">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="35175-124">**De URL van** Station by is de plaats waar de schadelijke URL in het bericht de gebruiker naar een vertrouwde website brengt die in stilte codecode op het apparaat van de gebruiker wordt uitgevoerd en/of installeert.</span><span class="sxs-lookup"><span data-stu-id="35175-124">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="35175-125">Als u op **Details weergeven klikt** in de beschrijving van elke techniek, worden meer informatie en de simulatiestappen voor de techniek weergegeven.</span><span class="sxs-lookup"><span data-stu-id="35175-125">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulatiestappen voor de oogst van referenties in de training voor aanvalssimulatie in Microsoft 365 Defender-portal](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="35175-127">Nadat u de techniek hebt geselecteerd en op Volgende hebt **geklikt,** geeft u de simulatie een naam en eventueel een beschrijving.</span><span class="sxs-lookup"><span data-stu-id="35175-127">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="35175-128">Een laadvermogen selecteren</span><span class="sxs-lookup"><span data-stu-id="35175-128">Selecting a payload</span></span>

<span data-ttu-id="35175-129">Vervolgens moet u een payload selecteren in de bestaande payloadcatalogus.</span><span class="sxs-lookup"><span data-stu-id="35175-129">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="35175-130">Payloads hebben een aantal gegevenspunten om u te helpen kiezen:</span><span class="sxs-lookup"><span data-stu-id="35175-130">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="35175-131">**Klikfrequentie** telt hoeveel personen op deze payload hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="35175-131">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="35175-132">**Voorspelde compromissnelheid** voorspelt het percentage personen dat wordt gecompromitteerd door deze payload op basis van historische gegevens voor de payload in Microsoft Defender voor Office 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="35175-132">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="35175-133">**Met gestarte simulaties** wordt het aantal keren geteld dat deze payload is gebruikt in andere simulaties.</span><span class="sxs-lookup"><span data-stu-id="35175-133">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="35175-134">**Complexiteit ,** beschikbaar via **filters,** wordt berekend op basis van het aantal indicatoren binnen de payload waarin wordt aangestuurd op een aanval.</span><span class="sxs-lookup"><span data-stu-id="35175-134">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="35175-135">Meer indicatoren leiden tot een lagere complexiteit.</span><span class="sxs-lookup"><span data-stu-id="35175-135">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="35175-136">**Bron**, beschikbaar via **filters**, geeft aan of de payload is gemaakt op uw tenant of deel uitmaakt van de bestaande payloadcatalogus van Microsoft (globaal).</span><span class="sxs-lookup"><span data-stu-id="35175-136">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Geselecteerde payload in de training voor aanvalssimulatie in Microsoft 365 Defender-portal](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="35175-138">Selecteer een laadvermogen in de lijst om een voorbeeld van de payload te bekijken met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="35175-138">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="35175-139">Als u uw eigen payload wilt maken, leest u [een payload maken voor training voor aanvalssimulatie.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="35175-139">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="35175-140">Doelgroeptargeting</span><span class="sxs-lookup"><span data-stu-id="35175-140">Audience targeting</span></span>

<span data-ttu-id="35175-141">Nu is het tijd om het publiek van deze simulatie te selecteren.</span><span class="sxs-lookup"><span data-stu-id="35175-141">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="35175-142">U kunt ervoor kiezen om **alle gebruikers in uw organisatie op te** nemen of alleen specifieke gebruikers en groepen op te **nemen.**</span><span class="sxs-lookup"><span data-stu-id="35175-142">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="35175-143">Wanneer u ervoor kiest om **alleen specifieke gebruikers en groepen** op te nemen, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="35175-143">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="35175-144">**Voeg gebruikers** toe, waarmee u de zoekfunctie voor uw tenant kunt gebruiken, evenals geavanceerde zoek- en filtermogelijkheden, zoals gebruikers die de afgelopen drie maanden niet zijn getarget door een simulatie.</span><span class="sxs-lookup"><span data-stu-id="35175-144">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>

  ![Gebruikersfilters in training voor aanvalssimulatie in Microsoft 365 Defender-portal](../../media/attack-sim-preview-user-targeting.png)

- <span data-ttu-id="35175-146">**Met Importeren uit CSV** kunt u een vooraf gedefinieerde set gebruikers importeren voor deze simulatie.</span><span class="sxs-lookup"><span data-stu-id="35175-146">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="35175-147">Training toewijzen</span><span class="sxs-lookup"><span data-stu-id="35175-147">Assigning training</span></span>

<span data-ttu-id="35175-148">Het is raadzaam om training toe te wijzen voor elke simulatie, omdat werknemers die een training volgen, minder gevoelig zijn voor soortgelijke aanvallen.</span><span class="sxs-lookup"><span data-stu-id="35175-148">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="35175-149">U kunt ervoor kiezen om training aan u toe te laten of zelf cursussen en modules te selecteren.</span><span class="sxs-lookup"><span data-stu-id="35175-149">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="35175-150">Selecteer de **einddatum van de** training om ervoor te zorgen dat werknemers hun training tijdig voltooien.</span><span class="sxs-lookup"><span data-stu-id="35175-150">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="35175-151">Als u ervoor kiest om zelf cursussen en modules te selecteren, kunt u nog steeds de aanbevolen inhoud en alle beschikbare cursussen en modules zien.</span><span class="sxs-lookup"><span data-stu-id="35175-151">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aanbevolen training toevoegen in de training voor aanvalssimulatie in Microsoft 365 Defender-portal](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="35175-153">In de volgende stappen moet  u trainingen toevoegen als u ervoor hebt gekozen om deze zelf te selecteren en uw trainingslandingspagina aan te passen.</span><span class="sxs-lookup"><span data-stu-id="35175-153">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="35175-154">U kunt een voorbeeld van de landingspagina van de training bekijken en de koptekst en de hoofdtekst ervan wijzigen.</span><span class="sxs-lookup"><span data-stu-id="35175-154">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="35175-155">Details starten en controleren</span><span class="sxs-lookup"><span data-stu-id="35175-155">Launch details and review</span></span>

<span data-ttu-id="35175-156">Nu alles is geconfigureerd, kunt u deze simulatie direct starten of plannen voor een latere datum.</span><span class="sxs-lookup"><span data-stu-id="35175-156">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="35175-157">U moet ook kiezen wanneer u deze simulatie wilt beëindigen.</span><span class="sxs-lookup"><span data-stu-id="35175-157">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="35175-158">We stoppen met het vastleggen van de interactie met deze simulatie na de geselecteerde tijd.</span><span class="sxs-lookup"><span data-stu-id="35175-158">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="35175-159">**Schakel regiobewuste tijdzonebezorging** in om gesimuleerde aanvalsberichten te leveren aan uw werknemers tijdens hun werkuren op basis van hun regio.</span><span class="sxs-lookup"><span data-stu-id="35175-159">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="35175-160">Wanneer u klaar bent, klikt u op **Volgende** en bekijkt u de details van de simulatie.</span><span class="sxs-lookup"><span data-stu-id="35175-160">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="35175-161">Klik op **Bewerken** op een van de onderdelen om terug te gaan en de details te wijzigen die moeten worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="35175-161">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="35175-162">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="35175-162">Once done, click **Submit**.</span></span>
