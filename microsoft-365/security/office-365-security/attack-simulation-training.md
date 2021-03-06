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
description: Beheerders kunnen informatie krijgen over het nabootsen van phishing-aanvallen en het trainen van hun gebruikers op phishingpreventie met de training voor de aanvalstraining in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509336"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="eb7c5-103">Een phishing-aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="eb7c5-103">Simulate a phishing attack</span></span>

<span data-ttu-id="eb7c5-104">Met de training voor de aanval van een aanval in Microsoft Defender voor Office 365 kunt u benigne cyberaanvallen op uw organisatie uitvoeren om uw beveiligingsbeleid en -procedures te testen en uw werknemers trainen om hen bewuster te maken en hun suscepterbaarheid voor aanvallen te verlagen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="eb7c5-105">In dit artikel wordt u beschreven hoe u een gesimuleerde phishing-aanval kunt maken met behulp van de trainingstraining voor de aanvalstraining.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="eb7c5-106">Zie Aan de slag met de trainingstraining voor de aanvalssyrulatie voor meer [informatie](attack-simulation-training-get-started.md)over de training voor de aanvalsinsulatie.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="eb7c5-107">Als u een gesimuleerde phishing-aanval wilt starten, opent u het [Microsoft 365-beveiligingscentrum,](https://security.microsoft.com/)gaat u naar E-mail **& samenwerkingstraining** voor de aanval- of beveiligingstraining voor aanvallen en gaat u naar het tabblad \>  [**Animaties.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="eb7c5-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="eb7c5-108">Selecteer **onder Lanceringen** de **optie + Start een lancering.**</span><span class="sxs-lookup"><span data-stu-id="eb7c5-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Een knop voor deulatie starten in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="eb7c5-110">U kunt op elk moment tijdens het maken van de creatie van de creatie opslaan en sluiten om de andersing op een later tijdstip te configureren.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="eb7c5-111">Een techniek voor sociaal netwerken selecteren</span><span class="sxs-lookup"><span data-stu-id="eb7c5-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="eb7c5-112">Selecteer uit vier verschillende technieken, geselecteerd op basis van de [MITRE ATT&CK® framework.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="eb7c5-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="eb7c5-113">Er zijn verschillende nettoladingen beschikbaar voor verschillende technieken:</span><span class="sxs-lookup"><span data-stu-id="eb7c5-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="eb7c5-114">**Via referentiegegevens** wordt geprobeerd referenties te verzamelen door gebruikers naar een bekende website met invoervakken te halen om een gebruikersnaam en wachtwoord in te dienen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="eb7c5-115">**Malwarebijlage** voegt een schadelijke bijlage toe aan een bericht.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="eb7c5-116">Wanneer de gebruiker de bijlage opent, wordt er willekeurige code uitgevoerd die de aanvaller kan helpen het apparaat van de doel binnen te halen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="eb7c5-117">**Koppeling in bijlage** is een hybride type referentie voor hybride referenties.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="eb7c5-118">Een aanvaller voegt een URL toe aan een e-mailbijlage.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="eb7c5-119">De URL in de bijlage volgt dezelfde methode als referentiebouw.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="eb7c5-120">**Als u een koppeling** naar malware maakt, wordt er willekeurige code uitgevoerd van een bestand dat wordt gehost op een bekende service voor het delen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="eb7c5-121">Het bericht dat naar de gebruiker wordt verzonden, bevat een koppeling naar dit schadelijke bestand.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="eb7c5-122">Open het bestand en help de aanvaller het apparaat van het doel te ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="eb7c5-123">**Met de URL** voor drive-by-code wordt de gebruiker door de schadelijke URL in het bericht naar een vertrouwde website gestuurd die op de muis wordt uitgevoerd en/of code op het apparaat van de gebruiker installeert.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="eb7c5-124">Als u op **Details weergeven in** de beschrijving van elke techniek klikt, worden meer informatie en de stappen voor de onderering van de techniek weergegeven.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Referentiestappen voor referentievernooiing in de training voor de aanvalsinstulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="eb7c5-126">Nadat u de techniek hebt geselecteerd en op Volgende hebt **geklikt,** geeft u de vereenspeling een naam en desgewenst een beschrijving.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="eb7c5-127">Een nettolading selecteren</span><span class="sxs-lookup"><span data-stu-id="eb7c5-127">Selecting a payload</span></span>

<span data-ttu-id="eb7c5-128">Vervolgens moet u een nettolading selecteren uit de bestaande nettoladingscatalogus.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="eb7c5-129">Nettoladingen hebben een aantal gegevenspunten om u te helpen bij het kiezen:</span><span class="sxs-lookup"><span data-stu-id="eb7c5-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="eb7c5-130">**Met de klikfrequentie** wordt geteld hoeveel personen op deze nettolading hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="eb7c5-131">**Met een voorspelde** compromissnelheid wordt het percentage mensen voorspeld dat wordt gecompromitteerd door deze nettolading op basis van historische gegevens voor de nettolading van Microsoft Defender voor Office 365-klanten.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="eb7c5-132">**Met de bijen** die zijn gestart, wordt geteld hoe vaak deze nettolading is gebruikt in andere keer.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="eb7c5-133">**De complexiteit,** die beschikbaar is via **filters,** wordt berekend op basis van het aantal indicatoren in de nettolading die hints richt op het feit dat het een aanval wordt.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="eb7c5-134">Meer indicatoren leiden tot een lagere complexiteit.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="eb7c5-135">**Bron,** beschikbaar via **filters,** geeft aan of de nettolading is gemaakt in uw tenant of dat deze deel uitmaakt van de bestaande nettoladingscatalogus van Microsoft (global).</span><span class="sxs-lookup"><span data-stu-id="eb7c5-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Geselecteerde nettolading binnen de training voor de aanvalsverplaatsing in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="eb7c5-137">Selecteer een nettolading in de lijst om een voorbeeld van de nettolading te zien met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="eb7c5-138">Als u uw eigen nettolading wilt maken, lees dan een nettolading maken voor training [voor de aanvals-training.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="eb7c5-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="eb7c5-139">Doelgroepen</span><span class="sxs-lookup"><span data-stu-id="eb7c5-139">Audience targeting</span></span>

<span data-ttu-id="eb7c5-140">Nu is het tijd om het publiek van deze groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="eb7c5-141">U kunt ervoor kiezen **om alle gebruikers in uw organisatie** op te nemen of alleen specifieke gebruikers en groepen op te **nemen.**</span><span class="sxs-lookup"><span data-stu-id="eb7c5-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="eb7c5-142">Wanneer u ervoor kiest om **alleen specifieke gebruikers en groepen op te** nemen, kunt u:</span><span class="sxs-lookup"><span data-stu-id="eb7c5-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="eb7c5-143">Voeg gebruikers **toe,** zodat u gebruik kunt maken van de zoekfunctie van uw tenant, evenals geavanceerde zoek- en filtermogelijkheden, zoals gebruikers die in de afgelopen 3 maanden niet zijn gericht door eenulatie.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="eb7c5-144">![Filteren van gebruikers in de training voor de aanval van de aanval in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="eb7c5-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="eb7c5-145">**Door gegevens uit CSV-gegevens** te importeren, kunt u een vooraf gedefinieerde set gebruikers importeren voor deze vereenspeling.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="eb7c5-146">Training toewijzen</span><span class="sxs-lookup"><span data-stu-id="eb7c5-146">Assigning training</span></span>

<span data-ttu-id="eb7c5-147">Het is raadzaam om training toe te wijzen voor elkeulatie, aangezien werknemers die de training volgen, minder gevoelig zijn voor soortgelijke aanvallen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="eb7c5-148">U kunt zelf trainingen aan u toegewezen krijgen of zelf cursussen en modules selecteren.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="eb7c5-149">Selecteer de **einddatum van de** training om ervoor te zorgen dat werknemers hun training tijdig voltooien.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="eb7c5-150">Als u zelf cursussen en modules selecteert, kunt u nog steeds de aanbevolen inhoud en alle beschikbare cursussen en modules zien.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aanbevolen training toevoegen in de training voor de aanvallen van de aanval in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="eb7c5-152">In de volgende stappen moet u **trainingen** toevoegen als u ervoor hebt gekozen om het zelf te selecteren en uw trainingslandingspagina aan te passen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="eb7c5-153">U kunt een voorbeeld van de landingspagina van de training bekijken en de kop- en hoofdtekst ervan wijzigen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="eb7c5-154">Details starten en controleren</span><span class="sxs-lookup"><span data-stu-id="eb7c5-154">Launch details and review</span></span>

<span data-ttu-id="eb7c5-155">Nu alles is geconfigureerd, kunt u deze automatisch starten of deze voor een latere datum plannen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="eb7c5-156">U moet ook kiezen wanneer u deze vereenspeling wilt beëindigen.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="eb7c5-157">We stoppen met het vastleggen van de interactie met dezeulatie na de geselecteerde tijd.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="eb7c5-158">**Schakel de bezorging van tijdzone** op regio's in om gesimuleerde aanvalsberichten aan uw werknemers te verzenden tijdens hun werkuren, afhankelijk van hun regio.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="eb7c5-159">Wanneer u klaar bent, klikt u op **Volgende en** bekijkt u de details van de zelfedulatie.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="eb7c5-160">Klik op **Bewerken** op een van de onderdelen om terug te gaan en alle details te wijzigen die moeten worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="eb7c5-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="eb7c5-161">Klik op Verzenden als u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="eb7c5-161">Once done, click **Submit**.</span></span>
