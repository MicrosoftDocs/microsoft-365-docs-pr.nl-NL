---
title: Een payload maken voor training voor de aanvalssimulatie
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe u aangepaste payloads kunt maken voor de training voor de aanvalssimulatie in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204074"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="8b923-103">Een aangepaste nettolading maken voor aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="8b923-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="8b923-104">Microsoft biedt een krachtige payloadcatalogus voor diverse social engineering-technieken die u kunt koppelen aan uw trainingstraining voor aanvalssimulaties.</span><span class="sxs-lookup"><span data-stu-id="8b923-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="8b923-105">U kunt echter aangepaste payloads maken die beter werken voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8b923-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="8b923-106">In dit artikel wordt beschreven hoe u een payload kunt maken in De training voor de aanvalssimulatie in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b923-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="8b923-107">U kunt een payload maken door op Een payload maken **te** klikken op het speciale tabblad [ **Payloads**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de wizard voor het maken [van de simulatie.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="8b923-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="8b923-108">Bij de eerste stap in de wizard selecteert u een laadvermogenstype.</span><span class="sxs-lookup"><span data-stu-id="8b923-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="8b923-109">**Momenteel is alleen e-mail beschikbaar.**</span><span class="sxs-lookup"><span data-stu-id="8b923-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="8b923-110">Selecteer vervolgens een gekoppelde techniek.</span><span class="sxs-lookup"><span data-stu-id="8b923-110">Next, select an associated technique.</span></span> <span data-ttu-id="8b923-111">Zie meer informatie over technieken bij [Het selecteren van een social engineering-techniek.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="8b923-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="8b923-112">In de volgende stap de naam van uw laadvermogen.</span><span class="sxs-lookup"><span data-stu-id="8b923-112">In the next step name your payload.</span></span> <span data-ttu-id="8b923-113">Desgewenst kunt u het een beschrijving geven.</span><span class="sxs-lookup"><span data-stu-id="8b923-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="8b923-114">Laadvermogen configureren</span><span class="sxs-lookup"><span data-stu-id="8b923-114">Configure payload</span></span>

<span data-ttu-id="8b923-115">Nu is het tijd om uw laadvermogen te bouwen.</span><span class="sxs-lookup"><span data-stu-id="8b923-115">Now it's time to build your payload.</span></span> <span data-ttu-id="8b923-116">Voer de naam, het e-mailadres en het onderwerp van de e-mail in in de **sectie Afzenderdetails.**</span><span class="sxs-lookup"><span data-stu-id="8b923-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="8b923-117">Kies een phishing-URL in de opgegeven lijst.</span><span class="sxs-lookup"><span data-stu-id="8b923-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="8b923-118">Deze URL wordt later ingesloten in de tekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="8b923-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="8b923-119">U kunt een interne e-mail kiezen voor de afzender van uw payload, waardoor de payload wordt weergegeven als afkomstig van een andere werknemer van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="8b923-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="8b923-120">Dit vergroot de gevoeligheid voor de payload en helpt werknemers bij het informeren van het risico op interne bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="8b923-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="8b923-121">Er is een rich text editor beschikbaar om uw payload te maken.</span><span class="sxs-lookup"><span data-stu-id="8b923-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="8b923-122">U kunt ook een e-mailbericht importeren dat u van tevoren hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8b923-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="8b923-123">Gebruik de dynamische **tags** om de e-mail aan uw doelen te personaliseren terwijl u de hoofding van de e-mail maakt.</span><span class="sxs-lookup"><span data-stu-id="8b923-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="8b923-124">Klik **op Phishing-koppeling** om de eerder geselecteerde phishing-URL toe te voegen aan de tekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="8b923-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishingkoppeling en dynamische tags gemarkeerd in het maken van payloads voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="8b923-126">Als u tijd wilt besparen, schakelt u de optie in om alle koppelingen in het e-mailbericht te vervangen **door de phishingkoppeling.**</span><span class="sxs-lookup"><span data-stu-id="8b923-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="8b923-127">Wanneer u klaar bent met het opbouwen van de payload naar wens, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8b923-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="8b923-128">Indicatoren toevoegen</span><span class="sxs-lookup"><span data-stu-id="8b923-128">Adding indicators</span></span>

<span data-ttu-id="8b923-129">Indicatoren helpen werknemers bij het uitvoeren van de aanvalssimulatie inzicht te krijgen in de aanwijzingen die ze kunnen zoeken in toekomstige aanvallen.</span><span class="sxs-lookup"><span data-stu-id="8b923-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="8b923-130">Als u wilt beginnen, klikt u **op Indicator toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8b923-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="8b923-131">Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="8b923-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="8b923-132">Deze lijst is samengesteld om de meest voorkomende aanwijzingen te bevatten die worden weergegeven in phishing-e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="8b923-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="8b923-133">Nadat u deze optie hebt geselecteerd, moet u ervoor zorgen dat de indicatorpositie is ingesteld op Van de boventekst van het **e-mailbericht** en klikt u op **Tekst selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8b923-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="8b923-134">Markeer het deel van uw laadvermogen waar deze indicator wordt weergegeven en klik op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="8b923-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Gemarkeerde tekst in berichttekst om toe te voegen aan een indicator in training voor aanvalssimulatie](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="8b923-136">Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik in het voorbeeldkader van de indicator om een voorbeeld van de indicator te zien.</span><span class="sxs-lookup"><span data-stu-id="8b923-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="8b923-137">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8b923-137">Once done, click **Add**.</span></span> <span data-ttu-id="8b923-138">Herhaal deze stappen totdat u alle indicatoren in uw laadvermogen hebt behandeld.</span><span class="sxs-lookup"><span data-stu-id="8b923-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="8b923-139">Laadvermogen controleren</span><span class="sxs-lookup"><span data-stu-id="8b923-139">Review payload</span></span>

<span data-ttu-id="8b923-140">U bent klaar met het opbouwen van uw laadvermogen.</span><span class="sxs-lookup"><span data-stu-id="8b923-140">You're done building your payload.</span></span> <span data-ttu-id="8b923-141">Nu is het tijd om de details te bekijken en een voorbeeld van uw laadvermogen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8b923-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="8b923-142">Het voorbeeld bevat alle indicatoren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8b923-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="8b923-143">U kunt elk deel van de payload bewerken vanuit deze stap.</span><span class="sxs-lookup"><span data-stu-id="8b923-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="8b923-144">Wanneer u tevreden bent, kunt u **uw laadvermogen** verzenden.</span><span class="sxs-lookup"><span data-stu-id="8b923-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b923-145">Payloads die u hebt gemaakt, hebben **Tenant** als bron.</span><span class="sxs-lookup"><span data-stu-id="8b923-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="8b923-146">Wanneer u payloads selecteert, moet u ervoor zorgen dat tenant niet wordt **uitgefilterd.**</span><span class="sxs-lookup"><span data-stu-id="8b923-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="8b923-147">Verwante koppelingen</span><span class="sxs-lookup"><span data-stu-id="8b923-147">Related links</span></span>

[<span data-ttu-id="8b923-148">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="8b923-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="8b923-149">Een phishing-aanvalssimulatie maken</span><span class="sxs-lookup"><span data-stu-id="8b923-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="8b923-150">Meer inzicht krijgen middels aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="8b923-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
