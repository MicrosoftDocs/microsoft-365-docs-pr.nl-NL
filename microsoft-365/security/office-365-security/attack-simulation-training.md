---
title: Een phishing-aanval simuleren met Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Beheerders kunnen een malafide aanval simuleren en hun gebruikers trainen via phishing met behulp van simulatie gerichte training in Microsoft Defender voor Office 365.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667553"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="ee2f4-103">Een malafide aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="ee2f4-103">Simulate a phishing attack</span></span>

<span data-ttu-id="ee2f4-104">Met aanval van een aanval met Office 365 kunt u in Microsoft Defender voor Office uw eigen beveiligingsbeleid en-procedures testen en de aandacht vestigen op uw medewerkers en de betasting ervan verlagen voor aanvallen.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-104">Attack simulator training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="ee2f4-105">In dit artikel wordt u stapsgewijs begeleid bij het maken van een simulatie aanval via een aanval via een aanval.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-105">This article walks you through creating  a simulated phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ee2f4-106">Als u een gesimuleerde malafide aanval wilt starten, opent u het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/), gaat u naar **e-mail & Collaboration** \> **Simulator** en gaat u naar het tabblad [**simulaties**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="ee2f4-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulator**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="ee2f4-107">Selecteer onder **simulaties** **de optie + een simulatie starten**.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Een simulatie knop starten in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="ee2f4-109">U kunt op elk gewenst moment tijdens het maken van een simulatie de werktijd opslaan en sluiten om de simulatie later verder te configureren.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="ee2f4-110">Een maatschappelijke techniek selecteren</span><span class="sxs-lookup"><span data-stu-id="ee2f4-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="ee2f4-111">Selecteer een van de vier verschillende technieken, met een curator van de [Mitre ATT&a® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="ee2f4-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="ee2f4-112">Verschillende nettoladingen zijn beschikbaar voor verschillende technieken:</span><span class="sxs-lookup"><span data-stu-id="ee2f4-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="ee2f4-113">**Credential oogst** probeert referenties te verzamelen door gebruikers te laten weten dat ze een bekende, op een bekende, juiste website met invoervakken voor het verzenden van een gebruikersnaam en wachtwoord in te voeren.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="ee2f4-114">**Bijlage met schadelijke software** voegt een kwaadaardige bijlage toe aan een bericht.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="ee2f4-115">Wanneer de gebruiker de bijlage opent, wordt willekeurige code uitgevoerd die de aanvaller helpt het apparaat van de doel te manipuleren.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="ee2f4-116">**Koppeling in bijlage** is een type referentie oogst waartoe hybride.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="ee2f4-117">Een aanvaller voegt een URL in een e-mailbijlage in.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="ee2f4-118">De URL in de bijlage volgt dezelfde methode als de oogst van de Credential.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="ee2f4-119">**Koppeling naar malware** voert sommige willekeurige code uit vanuit een bestand dat wordt gehost op een bekende bestands Sharing-service.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="ee2f4-120">Het bericht dat naar de gebruiker is verzonden, bevat een koppeling naar dit schadelijke bestand.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="ee2f4-121">Het bestand wordt geopend en Help de kwaadwillende persoon kan zich betrekken bij het doelapparaat.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="ee2f4-122">Door te klikken op **Details weergeven** in de beschrijving van de verschillende technieken, worden aanvullende informatie en de simulatie stappen voor de techniek weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Simulatie stappen voor het verzamelen van referenties binnen een aanvals training in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="ee2f4-124">Wanneer u de techniek hebt geselecteerd en op **volgende** hebt geklikt, geeft u een simulatie een naam en eventueel een beschrijving.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="ee2f4-125">Een nettolading selecteren</span><span class="sxs-lookup"><span data-stu-id="ee2f4-125">Selecting a payload</span></span>

<span data-ttu-id="ee2f4-126">Vervolgens moet u een nettolading selecteren in de reeds bestaande nettolading.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="ee2f4-127">Nettoladingen bevatten een aantal gegevenspunten waarmee u kunt kiezen:</span><span class="sxs-lookup"><span data-stu-id="ee2f4-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="ee2f4-128">**Klik op rente** telt het aantal personen dat op deze nettolading heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="ee2f4-129">Voor **speld** percentage voor speling voorspelt, voorspelt het percentage personen dat met deze nettolading wordt geknoeid op basis van historische gegevens voor de nettolading van Microsoft Defender voor Office 365-klanten.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="ee2f4-130">**Gestarte simulaties** Hiermee wordt het aantal keren geteld dat deze nettolading in andere simulaties werd gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="ee2f4-131">De **complexiteit**, die beschikbaar is via **filters**, wordt berekend op basis van het aantal indicatoren binnen de nettolading, wat er op de computer een aanval van maakt.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="ee2f4-132">Meer indicatoren leiden tot een lagere complexiteit.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="ee2f4-133">**Bron**, beschikbaar via **filters**, geeft aan of de nettolading is gemaakt met de Tenant of dat deze deel uitmaakt van de reeds bestaande nettoladingen catalogus van Microsoft (globaal).</span><span class="sxs-lookup"><span data-stu-id="ee2f4-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Geselecteerde nettolading binnen aanval simulatie training in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="ee2f4-135">Selecteer een nettolading in de lijst als u een voorbeeld van de nettolading met aanvullende informatie hierover wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="ee2f4-136">Als u uw eigen nettolading wilt maken, raadpleegt u [een nettolading maken voor de training voor simulatie van aanval](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="ee2f4-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="ee2f4-137">Doelgroepen</span><span class="sxs-lookup"><span data-stu-id="ee2f4-137">Audience targeting</span></span>

<span data-ttu-id="ee2f4-138">Nu is het tijd om het publiek van deze simulatie te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="ee2f4-139">U kunt ervoor kiezen om **alle gebruikers in uw organisatie** op te nemen of **alleen bepaalde gebruikers en groepen toe te voegen**.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="ee2f4-140">Wanneer u ervoor kiest om **alleen bepaalde gebruikers en groepen toe te voegen,** hebt u de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="ee2f4-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="ee2f4-141">**Voeg gebruikers toe**, zodat u kunt zoeken naar uw Tenant en de functies voor Geavanceerd zoeken en filteren, zoals het doel van gebruikers die niet zijn gericht op een simulatie in de afgelopen drie maanden.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="ee2f4-142">![Gebruiker filteren bij simulatie van aanval in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="ee2f4-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="ee2f4-143">**Met importeren vanuit CSV** kunt u een vooraf gedefinieerde set gebruikers voor deze simulatie importeren.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="ee2f4-144">Training toewijzen</span><span class="sxs-lookup"><span data-stu-id="ee2f4-144">Assigning training</span></span>

<span data-ttu-id="ee2f4-145">U wordt geadviseerd training voor elke simulatie toe te wijzen, aangezien de werknemers die training volgen minder gevoelig zijn voor soortgelijke aanvallen.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="ee2f4-146">U kunt ervoor kiezen om training voor u te laten voor u of voor de cursus zelf trainingen en modules te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="ee2f4-147">Selecteer de **einddatum** van de opleiding om ervoor te zorgen dat werknemers op een redelijke manier hun training kunnen voltooien.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="ee2f4-148">Als u ervoor kiest cursussen en modules zelf te selecteren, kunt u de aanbevolen inhoud wel en alle beschikbare cursussen en modules weergeven.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Aanbevolen training toevoegen in simulatie simulatie van aanval in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="ee2f4-150">In de volgende stappen dient u **trainingen toe te voegen** als u ervoor hebt gekozen om zelf een training te selecteren en de landingspagina aan te passen.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="ee2f4-151">U kunt een voorbeeld bekijken van de pagina voor het aanbrengen van een opleiding en ook de koptekst en de tekst ervan wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="ee2f4-152">Details starten en controleren</span><span class="sxs-lookup"><span data-stu-id="ee2f4-152">Launch details and review</span></span>

<span data-ttu-id="ee2f4-153">Nu alles is geconfigureerd, kunt u deze simulatie direct starten of plannen voor een latere datum.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="ee2f4-154">U moet ook kiezen wanneer u deze simulatie wilt beëindigen.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="ee2f4-155">We zullen niet langer de interactie met deze simulatie na de geselecteerde tijd beëindigen.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="ee2f4-156">**Ondersteuning voor regio detectie van tijdzones** voor de levering van de gesimuleerde aanvals berichten voor uw werknemers gedurende hun werktijden op basis van hun regio.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="ee2f4-157">Wanneer u klaar bent, klikt u op **volgende** en controleert u de details van uw simulatie.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="ee2f4-158">Klik op **bewerken** bij een van de onderdelen om terug te gaan en de gegevens te wijzigen die moeten worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="ee2f4-159">Klik vervolgens op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="ee2f4-159">Once done, click **Submit**.</span></span>
