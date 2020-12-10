---
title: Een nettolading maken voor de training voor simulatie aanval
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Meer informatie over het maken van een aangepaste nettolading voor simulatie van aanvals simulaties in Microsoft Defender voor Office 365.
ms.openlocfilehash: a8366e6cbf703ef1e1a14e216ada71200668cd14
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616270"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="accdd-103">Een aangepaste nettolading maken voor aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="accdd-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="accdd-104">Microsoft biedt een krachtige versie van de nettolading voor diverse social engineering-technieken voor het koppelen van uw aanvals training.</span><span class="sxs-lookup"><span data-stu-id="accdd-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="accdd-105">U kunt echter wel aangepaste ladingen maken die beter voor uw organisatie kunnen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="accdd-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="accdd-106">Hieronder wordt beschreven hoe u een nettolading maakt voor simulatie van aanvals simulatie via Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="accdd-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="accdd-107">U kunt een nettolading maken door te klikken op **een nettolading maken** op het [tabblad specifieke **nettoladingen**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de [wizard simulatie maken](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="accdd-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="accdd-108">In de eerste stap van de wizard selecteert u een type nettolading.</span><span class="sxs-lookup"><span data-stu-id="accdd-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="accdd-109">**Momenteel is alleen e-mail beschikbaar**.</span><span class="sxs-lookup"><span data-stu-id="accdd-109">**Currently only email is available**.</span></span>

<span data-ttu-id="accdd-110">Selecteer vervolgens een gekoppelde methode.</span><span class="sxs-lookup"><span data-stu-id="accdd-110">Next, select an associated technique.</span></span> <span data-ttu-id="accdd-111">Zie voor meer informatie over technieken bij [het selecteren van een maatschappelijke techniek](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="accdd-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="accdd-112">Geef in de volgende stap de naam uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="accdd-112">In the next step name your payload.</span></span> <span data-ttu-id="accdd-113">U kunt ook een beschrijving opgeven.</span><span class="sxs-lookup"><span data-stu-id="accdd-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="accdd-114">Nettolading configureren</span><span class="sxs-lookup"><span data-stu-id="accdd-114">Configure payload</span></span>

<span data-ttu-id="accdd-115">Nu is het tijd om uw nettolading aan te maken.</span><span class="sxs-lookup"><span data-stu-id="accdd-115">Now it's time to build your payload.</span></span> <span data-ttu-id="accdd-116">Voer de naam van de afzender, het e-mailadres en het onderwerp van de e-mail in het gedeelte **Details van afzender** in.</span><span class="sxs-lookup"><span data-stu-id="accdd-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="accdd-117">Selecteer een phishingwebsite in de lijst met opgegeven URL'S.</span><span class="sxs-lookup"><span data-stu-id="accdd-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="accdd-118">Deze URL wordt later ingesloten in de hoofdtekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="accdd-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="accdd-119">U kunt een interne e-mail voor de afzender van uw nettolading kiezen, zodat de nettolading wordt weergegeven als de naam van een andere werknemer van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="accdd-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="accdd-120">Hierdoor wordt de kans groter voor de nettolading en kunnen werknemers aan het risico van interne bedreigingen zorgen.</span><span class="sxs-lookup"><span data-stu-id="accdd-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="accdd-121">De RTF-editor is beschikbaar voor het maken van uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="accdd-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="accdd-122">U kunt ook een e-mailbericht importeren dat u vooraf hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="accdd-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="accdd-123">Wanneer u de hoofdtekst van het e-mailbericht structureert, profiteert u van de **dynamische Tags** om de e-mail aan te passen aan uw doelen.</span><span class="sxs-lookup"><span data-stu-id="accdd-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="accdd-124">Klik op **phishing** om de eerder geselecteerde phishingwebsite in de hoofdtekst van het e-mailbericht toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="accdd-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![Phishing en dynamische Tags gemarkeerd in het maken van nettolading voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="accdd-126">Als u uw tijd wilt besparen, schakelt u de optie voor het **vervangen van alle koppelingen in het e-mailbericht met de phishing-koppeling uit**.</span><span class="sxs-lookup"><span data-stu-id="accdd-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="accdd-127">Wanneer u klaar bent met het maken van de nettolading, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="accdd-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="accdd-128">Indicatoren toevoegen</span><span class="sxs-lookup"><span data-stu-id="accdd-128">Adding indicators</span></span>

<span data-ttu-id="accdd-129">Indicatoren stellen medewerkers in staat inzicht te krijgen in de simulatie van een aanval in toekomstige aanvallen.</span><span class="sxs-lookup"><span data-stu-id="accdd-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="accdd-130">Als u wilt beginnen, klikt u op **indicator toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="accdd-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="accdd-131">Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="accdd-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="accdd-132">Deze lijst is bedoeld voor de meest voorkomende aanwijzingen die worden weergegeven in malafide e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="accdd-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="accdd-133">Als dit is geselecteerd, controleert u of de positie van de indicator is ingesteld op **in de hoofdtekst van het e-mailbericht** en klikt u op **tekst selecteren**.</span><span class="sxs-lookup"><span data-stu-id="accdd-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="accdd-134">Markeer het gedeelte van uw nettolading waarbij deze indicator wordt weergegeven en klik op **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="accdd-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Gemarkeerde tekst in de berichttekst die moet worden toegevoegd aan een indicator voor simulatie van aanvals training](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="accdd-136">Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik in het frame met het voorbeeld van de indicator om een voorbeeld van de indicator te zien.</span><span class="sxs-lookup"><span data-stu-id="accdd-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="accdd-137">Als u klaar bent, klikt u op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="accdd-137">Once done, click **Add**.</span></span> <span data-ttu-id="accdd-138">Herhaal deze stappen totdat alle indicatoren in uw nettolading zijn besproken.</span><span class="sxs-lookup"><span data-stu-id="accdd-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="accdd-139">Nettolading controleren</span><span class="sxs-lookup"><span data-stu-id="accdd-139">Review payload</span></span>

<span data-ttu-id="accdd-140">U bent klaar met het maken van uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="accdd-140">You're done building your payload.</span></span> <span data-ttu-id="accdd-141">Nu is het tijd om de details te bekijken en een voorbeeld van uw nettolading te bekijken.</span><span class="sxs-lookup"><span data-stu-id="accdd-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="accdd-142">Het voorbeeld bevat alle indicatoren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="accdd-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="accdd-143">U kunt in deze stap elk deel van de nettolading bewerken.</span><span class="sxs-lookup"><span data-stu-id="accdd-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="accdd-144">Als dit is voldaan, **verzendt** u uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="accdd-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="accdd-145">Nettoladingen die u hebt gemaakt, hebben een **Tenant** ingesteld als de bron.</span><span class="sxs-lookup"><span data-stu-id="accdd-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="accdd-146">Wanneer u nettoladingen selecteert, controleert u of de **Tenant** niet is gefilterd.</span><span class="sxs-lookup"><span data-stu-id="accdd-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>