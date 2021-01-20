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
- m365initiative-defender-office365
description: Beheerders kunnen aangepaste ladingen maken voor simulatie van aanvals vaardigheden in Microsoft Defender voor Office 365.
ms.openlocfilehash: 86a962dc3117708ac71195b9efc336fa30c573dd
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908339"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="990e4-103">Een aangepaste nettolading maken voor aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="990e4-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="990e4-104">Microsoft biedt een robuuste nettolading-catalogus voor diverse social engineering-technieken voor het koppelen van uw aanvals training.</span><span class="sxs-lookup"><span data-stu-id="990e4-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="990e4-105">U kunt echter wel aangepaste ladingen maken die beter voor uw organisatie kunnen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="990e4-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="990e4-106">In dit artikel wordt uitgelegd hoe u een nettolading maakt voor de training voor simulatie aanval in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="990e4-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="990e4-107">U kunt een nettolading maken door te klikken op **een nettolading maken** op het [tabblad specifieke **nettoladingen**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de [wizard simulatie maken](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="990e4-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="990e4-108">In de eerste stap van de wizard selecteert u een type nettolading.</span><span class="sxs-lookup"><span data-stu-id="990e4-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="990e4-109">**Momenteel is alleen e-mail beschikbaar**.</span><span class="sxs-lookup"><span data-stu-id="990e4-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="990e4-110">Selecteer vervolgens een gekoppelde methode.</span><span class="sxs-lookup"><span data-stu-id="990e4-110">Next, select an associated technique.</span></span> <span data-ttu-id="990e4-111">Zie voor meer informatie over technieken bij [het selecteren van een maatschappelijke techniek](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="990e4-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="990e4-112">Geef in de volgende stap de naam uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="990e4-112">In the next step name your payload.</span></span> <span data-ttu-id="990e4-113">U kunt ook een beschrijving opgeven.</span><span class="sxs-lookup"><span data-stu-id="990e4-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="990e4-114">Nettolading configureren</span><span class="sxs-lookup"><span data-stu-id="990e4-114">Configure payload</span></span>

<span data-ttu-id="990e4-115">Nu is het tijd om uw nettolading aan te maken.</span><span class="sxs-lookup"><span data-stu-id="990e4-115">Now it's time to build your payload.</span></span> <span data-ttu-id="990e4-116">Voer de naam en het e-mailadres van de afzender en het onderwerp van de e-mail in het gedeelte **Details van afzender** in.</span><span class="sxs-lookup"><span data-stu-id="990e4-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="990e4-117">Selecteer een phishingwebsite in de opgegeven lijst.</span><span class="sxs-lookup"><span data-stu-id="990e4-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="990e4-118">Deze URL wordt later ingesloten in de hoofdtekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="990e4-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="990e4-119">U kunt een interne e-mail voor de afzender van uw nettolading kiezen, zodat de nettolading wordt weergegeven als de naam van een andere werknemer van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="990e4-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="990e4-120">Hierdoor wordt de kans groter voor de nettolading en kunnen werknemers aan het risico van interne bedreigingen zorgen.</span><span class="sxs-lookup"><span data-stu-id="990e4-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="990e4-121">De RTF-editor is beschikbaar voor het maken van uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="990e4-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="990e4-122">U kunt ook een e-mailbericht importeren dat u vooraf hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="990e4-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="990e4-123">Wanneer u de hoofdtekst van het e-mailbericht maakt, profiteert u van de **dynamische Tags** om de e-mail te personaliseren met uw doelen.</span><span class="sxs-lookup"><span data-stu-id="990e4-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="990e4-124">Klik op **phishing** om de eerder geselecteerde phishingwebsite toe te voegen aan de hoofdtekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="990e4-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishing en dynamische Tags gemarkeerd in het maken van nettolading voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="990e4-126">Als u tijd wilt besparen, schakelt u de optie voor het **vervangen van alle koppelingen in het e-mailbericht met de phishingwebsite** in.</span><span class="sxs-lookup"><span data-stu-id="990e4-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="990e4-127">Wanneer u klaar bent met het maken van de nettolading, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="990e4-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="990e4-128">Indicatoren toevoegen</span><span class="sxs-lookup"><span data-stu-id="990e4-128">Adding indicators</span></span>

<span data-ttu-id="990e4-129">Indicatoren stellen medewerkers in staat inzicht te krijgen in de aantasting van de aanval in toekomstige aanvallen.</span><span class="sxs-lookup"><span data-stu-id="990e4-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="990e4-130">Als u wilt beginnen, klikt u op **indicator toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="990e4-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="990e4-131">Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="990e4-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="990e4-132">Deze lijst is bedoeld voor de meest voorkomende aanwijzingen die worden weergegeven in malafide e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="990e4-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="990e4-133">Als dit is geselecteerd, controleert u of de positie van de indicator is ingesteld op **in de hoofdtekst van het e-mailbericht** en klikt u op **tekst selecteren**.</span><span class="sxs-lookup"><span data-stu-id="990e4-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="990e4-134">Markeer het gedeelte van uw nettolading waarbij deze indicator wordt weergegeven en klik op **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="990e4-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Gemarkeerde tekst in de berichttekst die moet worden toegevoegd aan een indicator voor simulatie van aanvals training](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="990e4-136">Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik in het frame met het voorbeeld van de indicator om een voorbeeld van de indicator te zien.</span><span class="sxs-lookup"><span data-stu-id="990e4-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="990e4-137">Als u klaar bent, klikt u op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="990e4-137">Once done, click **Add**.</span></span> <span data-ttu-id="990e4-138">Herhaal deze stappen totdat alle indicatoren in uw nettolading zijn besproken.</span><span class="sxs-lookup"><span data-stu-id="990e4-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="990e4-139">Nettolading controleren</span><span class="sxs-lookup"><span data-stu-id="990e4-139">Review payload</span></span>

<span data-ttu-id="990e4-140">U bent klaar met het maken van uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="990e4-140">You're done building your payload.</span></span> <span data-ttu-id="990e4-141">Nu is het tijd om de details te bekijken en een voorbeeld van uw nettolading te bekijken.</span><span class="sxs-lookup"><span data-stu-id="990e4-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="990e4-142">Het voorbeeld bevat alle indicatoren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="990e4-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="990e4-143">U kunt in deze stap elk deel van de nettolading bewerken.</span><span class="sxs-lookup"><span data-stu-id="990e4-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="990e4-144">Als dit is voldaan, kunt u uw nettolading **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="990e4-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="990e4-145">Nettoladingen die u hebt gemaakt, hebben de **Tenant** als de bron.</span><span class="sxs-lookup"><span data-stu-id="990e4-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="990e4-146">Zorg er bij het selecteren van nettolading voor dat u de **Tenant** niet hoeft te filteren.</span><span class="sxs-lookup"><span data-stu-id="990e4-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="990e4-147">Verwante koppelingen</span><span class="sxs-lookup"><span data-stu-id="990e4-147">Related links</span></span>

[<span data-ttu-id="990e4-148">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="990e4-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="990e4-149">Een simulatie van een malafide aanval maken</span><span class="sxs-lookup"><span data-stu-id="990e4-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="990e4-150">Meer inzicht krijgen middels aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="990e4-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
