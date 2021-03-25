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
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204501"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="2a638-103">Een phishing-aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="2a638-103">Simulate a phishing attack</span></span>

<span data-ttu-id="2a638-104">Met training voor aanvalssimulatie in Microsoft Defender voor Office 365 kunt u goedaardige cyberaanvallensimulaties uitvoeren op uw organisatie om uw beveiligingsbeleid en -procedures te testen, en uw werknemers trainen om hun bekendheid te vergroten en hun gevoeligheid voor aanvallen te verminderen.</span><span class="sxs-lookup"><span data-stu-id="2a638-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="2a638-105">In dit artikel wordt u beschreven hoe u een gesimuleerde phishing-aanval maakt met behulp van training voor een aanvalssimulatie.</span><span class="sxs-lookup"><span data-stu-id="2a638-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="2a638-106">Zie Aan de slag met de trainingstraining [Aanvalssimulatie](attack-simulation-training-get-started.md)voor informatie over de training voor aanvalssimulaties.</span><span class="sxs-lookup"><span data-stu-id="2a638-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="2a638-107">Als u een gesimuleerde phishing-aanval wilt starten, opent u het [Microsoft 365-beveiligingscentrum,](https://security.microsoft.com/)gaat u naar E-mail **& samenwerking** Aanvalssimulatietraining en gaat u naar het tabblad \>  [**Simulaties.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="2a638-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="2a638-108">Selecteer **onder Simulaties** de **optie + Een simulatie starten.**</span><span class="sxs-lookup"><span data-stu-id="2a638-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Een simulatieknop starten in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="2a638-110">Op elk moment tijdens het maken van de simulatie kunt u opslaan en sluiten om de simulatie op een later tijdstip te blijven configureren.</span><span class="sxs-lookup"><span data-stu-id="2a638-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="2a638-111">Een social engineering-techniek selecteren</span><span class="sxs-lookup"><span data-stu-id="2a638-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="2a638-112">Selecteer uit 4 verschillende technieken, samengesteld uit het [MITRE ATT-&CK® framework.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="2a638-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="2a638-113">Er zijn verschillende payloads beschikbaar voor verschillende technieken:</span><span class="sxs-lookup"><span data-stu-id="2a638-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="2a638-114">**Referentiesoogst** probeert referenties te verzamelen door gebruikers naar een bekende website te nemen met invoervakken om een gebruikersnaam en wachtwoord in te dienen.</span><span class="sxs-lookup"><span data-stu-id="2a638-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="2a638-115">**Malwarebijlage** voegt een schadelijke bijlage toe aan een bericht.</span><span class="sxs-lookup"><span data-stu-id="2a638-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="2a638-116">Wanneer de gebruiker de bijlage opent, wordt willekeurige code uitgevoerd die de aanvaller helpt het apparaat van het doel te compromitteerden.</span><span class="sxs-lookup"><span data-stu-id="2a638-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="2a638-117">**Koppeling in bijlage** is een type referentieoogst hybride.</span><span class="sxs-lookup"><span data-stu-id="2a638-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="2a638-118">Een aanvaller voegt een URL in een e-mailbijlage in.</span><span class="sxs-lookup"><span data-stu-id="2a638-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="2a638-119">De URL in de bijlage volgt dezelfde techniek als referentieoogst.</span><span class="sxs-lookup"><span data-stu-id="2a638-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="2a638-120">**Als u een koppeling naar malware** maakt, wordt een willekeurige code uitgevoerd van een bestand dat wordt gehost op een bekende service voor het delen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="2a638-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="2a638-121">Het bericht dat naar de gebruiker wordt verzonden, bevat een koppeling naar dit schadelijke bestand.</span><span class="sxs-lookup"><span data-stu-id="2a638-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="2a638-122">Het bestand openen en de aanvaller helpen het apparaat van het doel te compromitteerden.</span><span class="sxs-lookup"><span data-stu-id="2a638-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="2a638-123">**De URL van** Station by is de plaats waar de schadelijke URL in het bericht de gebruiker naar een vertrouwde website brengt die in stilte codecode op het apparaat van de gebruiker wordt uitgevoerd en/of installeert.</span><span class="sxs-lookup"><span data-stu-id="2a638-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="2a638-124">Als u op **Details weergeven klikt** in de beschrijving van elke techniek, worden meer informatie en de simulatiestappen voor de techniek weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a638-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulatiestappen voor de oogst van referenties in de training voor aanvalssimulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="2a638-126">Nadat u de techniek hebt geselecteerd en op Volgende hebt **geklikt,** geeft u de simulatie een naam en eventueel een beschrijving.</span><span class="sxs-lookup"><span data-stu-id="2a638-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="2a638-127">Een laadvermogen selecteren</span><span class="sxs-lookup"><span data-stu-id="2a638-127">Selecting a payload</span></span>

<span data-ttu-id="2a638-128">Vervolgens moet u een payload selecteren in de bestaande payloadcatalogus.</span><span class="sxs-lookup"><span data-stu-id="2a638-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="2a638-129">Payloads hebben een aantal gegevenspunten om u te helpen kiezen:</span><span class="sxs-lookup"><span data-stu-id="2a638-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="2a638-130">**Klikfrequentie** telt hoeveel personen op deze payload hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="2a638-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="2a638-131">**Voorspelde snelheid** van compromissen voorspelt het percentage personen dat wordt gecompromitteerd door deze payload op basis van historische gegevens voor het laadvermogen in Microsoft Defender voor Office 365-klanten.</span><span class="sxs-lookup"><span data-stu-id="2a638-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="2a638-132">**Met gestarte simulaties** wordt het aantal keren geteld dat deze payload is gebruikt in andere simulaties.</span><span class="sxs-lookup"><span data-stu-id="2a638-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="2a638-133">**Complexiteit ,** beschikbaar via **filters,** wordt berekend op basis van het aantal indicatoren binnen de payload waarin wordt aangestuurd op een aanval.</span><span class="sxs-lookup"><span data-stu-id="2a638-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="2a638-134">Meer indicatoren leiden tot een lagere complexiteit.</span><span class="sxs-lookup"><span data-stu-id="2a638-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="2a638-135">**Bron**, beschikbaar via **filters**, geeft aan of de payload is gemaakt op uw tenant of deel uitmaakt van de bestaande payloadcatalogus van Microsoft (globaal).</span><span class="sxs-lookup"><span data-stu-id="2a638-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Geselecteerde payload in de training voor aanvalssimulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="2a638-137">Selecteer een laadvermogen in de lijst om een voorbeeld van de payload te bekijken met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="2a638-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="2a638-138">Als u uw eigen payload wilt maken, leest u [een payload maken voor training voor aanvalssimulatie.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="2a638-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="2a638-139">Doelgroeptargeting</span><span class="sxs-lookup"><span data-stu-id="2a638-139">Audience targeting</span></span>

<span data-ttu-id="2a638-140">Nu is het tijd om het publiek van deze simulatie te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2a638-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="2a638-141">U kunt ervoor kiezen om **alle gebruikers in uw organisatie op te** nemen of alleen specifieke gebruikers en groepen op te **nemen.**</span><span class="sxs-lookup"><span data-stu-id="2a638-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="2a638-142">Wanneer u ervoor kiest om **alleen specifieke gebruikers en groepen** op te nemen, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="2a638-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="2a638-143">**Voeg gebruikers** toe, waarmee u de zoekfunctie voor uw tenant kunt gebruiken, evenals geavanceerde zoek- en filtermogelijkheden, zoals gebruikers die de afgelopen drie maanden niet zijn getarget door een simulatie.</span><span class="sxs-lookup"><span data-stu-id="2a638-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="2a638-144">![Gebruikersfilters in training voor aanvalssimulatie in microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="2a638-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="2a638-145">**Met Importeren uit CSV** kunt u een vooraf gedefinieerde set gebruikers importeren voor deze simulatie.</span><span class="sxs-lookup"><span data-stu-id="2a638-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="2a638-146">Training toewijzen</span><span class="sxs-lookup"><span data-stu-id="2a638-146">Assigning training</span></span>

<span data-ttu-id="2a638-147">Het is raadzaam om training toe te wijzen voor elke simulatie, omdat werknemers die een training volgen, minder gevoelig zijn voor soortgelijke aanvallen.</span><span class="sxs-lookup"><span data-stu-id="2a638-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="2a638-148">U kunt ervoor kiezen om training aan u toe te laten of zelf cursussen en modules te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2a638-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="2a638-149">Selecteer de **einddatum van de** training om ervoor te zorgen dat werknemers hun training tijdig voltooien.</span><span class="sxs-lookup"><span data-stu-id="2a638-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="2a638-150">Als u ervoor kiest om zelf cursussen en modules te selecteren, kunt u nog steeds de aanbevolen inhoud en alle beschikbare cursussen en modules zien.</span><span class="sxs-lookup"><span data-stu-id="2a638-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aanbevolen training toevoegen in training voor aanvalssimulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="2a638-152">In de volgende stappen moet  u trainingen toevoegen als u ervoor hebt gekozen om deze zelf te selecteren en uw trainingslandingspagina aan te passen.</span><span class="sxs-lookup"><span data-stu-id="2a638-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="2a638-153">U kunt een voorbeeld van de landingspagina van de training bekijken en de koptekst en de hoofdtekst ervan wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2a638-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="2a638-154">Details starten en controleren</span><span class="sxs-lookup"><span data-stu-id="2a638-154">Launch details and review</span></span>

<span data-ttu-id="2a638-155">Nu alles is geconfigureerd, kunt u deze simulatie direct starten of plannen voor een latere datum.</span><span class="sxs-lookup"><span data-stu-id="2a638-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="2a638-156">U moet ook kiezen wanneer u deze simulatie wilt beëindigen.</span><span class="sxs-lookup"><span data-stu-id="2a638-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="2a638-157">We stoppen met het vastleggen van de interactie met deze simulatie na de geselecteerde tijd.</span><span class="sxs-lookup"><span data-stu-id="2a638-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="2a638-158">**Schakel regiobewuste tijdzonebezorging** in om gesimuleerde aanvalsberichten te leveren aan uw werknemers tijdens hun werkuren op basis van hun regio.</span><span class="sxs-lookup"><span data-stu-id="2a638-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="2a638-159">Wanneer u klaar bent, klikt u op **Volgende** en bekijkt u de details van de simulatie.</span><span class="sxs-lookup"><span data-stu-id="2a638-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="2a638-160">Klik op **Bewerken** op een van de onderdelen om terug te gaan en de details te wijzigen die moeten worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2a638-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="2a638-161">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="2a638-161">Once done, click **Submit**.</span></span>
