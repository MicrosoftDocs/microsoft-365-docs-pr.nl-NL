---
title: Een nettolading maken voor de training voor de aanvals-training
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
description: Beheerders kunnen leren hoe ze aangepaste nettoladingen kunnen maken voor training voor de aanvalstraining voor de aanval in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929188"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="21f5c-103">Een aangepaste nettolading maken voor aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="21f5c-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="21f5c-104">Microsoft biedt een krachtige nettoladingscatalogus voor diverse social-engineering-technieken om te koppelen aan uw training voor de aanvalssinulatie.</span><span class="sxs-lookup"><span data-stu-id="21f5c-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="21f5c-105">Mogelijk wilt u echter aangepaste nettolading maken die beter werkt voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="21f5c-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="21f5c-106">In dit artikel wordt beschreven hoe u een nettolading kunt maken in de training voor de attack-training in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="21f5c-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="21f5c-107">U kunt een nettolading maken door op Nettolading maken te klikken **op** het speciale tabblad [ **Nettolading**](https://security.microsoft.com/attacksimulator?viewid=payload) of in de wizard voor het maken van [de activering.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="21f5c-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="21f5c-108">Bij de eerste stap in de wizard selecteert u een nettoladingstype.</span><span class="sxs-lookup"><span data-stu-id="21f5c-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="21f5c-109">**Momenteel is alleen e-mail beschikbaar.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="21f5c-110">Selecteer vervolgens een gekoppelde techniek.</span><span class="sxs-lookup"><span data-stu-id="21f5c-110">Next, select an associated technique.</span></span> <span data-ttu-id="21f5c-111">Meer informatie over technieken bij [Het selecteren van een techniek voor sociaal netwerken.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="21f5c-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="21f5c-112">In de volgende stap noemt u uw nettolading.</span><span class="sxs-lookup"><span data-stu-id="21f5c-112">In the next step name your payload.</span></span> <span data-ttu-id="21f5c-113">Desgewenst kunt u er een beschrijving aan geven.</span><span class="sxs-lookup"><span data-stu-id="21f5c-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="21f5c-114">Nettolading configureren</span><span class="sxs-lookup"><span data-stu-id="21f5c-114">Configure payload</span></span>

<span data-ttu-id="21f5c-115">Nu is het tijd om uw nettolading te bouwen.</span><span class="sxs-lookup"><span data-stu-id="21f5c-115">Now it's time to build your payload.</span></span> <span data-ttu-id="21f5c-116">Voer de naam, het e-mailadres en het onderwerp van het e-mailbericht in de **sectie Sender details** in.</span><span class="sxs-lookup"><span data-stu-id="21f5c-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="21f5c-117">Kies een phishing-URL uit de opgegeven lijst.</span><span class="sxs-lookup"><span data-stu-id="21f5c-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="21f5c-118">Deze URL wordt later in de bericht zelf ingesloten.</span><span class="sxs-lookup"><span data-stu-id="21f5c-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="21f5c-119">U kunt een interne e-mail voor de afzender van uw nettolading kiezen, zodat de nettolading lijkt afkomstig te zijn van een andere werknemer van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="21f5c-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="21f5c-120">Hierdoor wordt de nettolading groter en kunnen werknemers beter informeren over het risico op interne bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="21f5c-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="21f5c-121">Er is een rich text-editor beschikbaar om uw nettolading te maken.</span><span class="sxs-lookup"><span data-stu-id="21f5c-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="21f5c-122">U kunt ook een e-mailbericht importeren dat u van tevoren hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="21f5c-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="21f5c-123">Wanneer u de hoofd-inhoud van de e-mail maakt, kunt u de dynamische tags gebruiken **om** het e-mailbericht aan uw doelen aan te persoonlijke voorkeur aan te maken.</span><span class="sxs-lookup"><span data-stu-id="21f5c-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="21f5c-124">Klik **op Phishing-koppeling** om de eerder geselecteerde phishing-URL toe te voegen aan de tekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="21f5c-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Phishing-koppeling en dynamische tags gemarkeerd bij het maken van nettolading voor Microsoft Defender voor Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="21f5c-126">Om tijd te besparen, schakelt u de optie in om alle koppelingen in het e-mailbericht te vervangen **door de phishing-koppeling.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="21f5c-127">Als u klaar bent met het bouwen van de nettolading naar wens, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="21f5c-128">Indicatoren toevoegen</span><span class="sxs-lookup"><span data-stu-id="21f5c-128">Adding indicators</span></span>

<span data-ttu-id="21f5c-129">Indicatoren helpen werknemers om de aanvalsinding te bekijken, en begrijpen de aanwijzingen die ze kunnen vinden in toekomstige aanvallen.</span><span class="sxs-lookup"><span data-stu-id="21f5c-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="21f5c-130">Klik op Indicator toevoegen om **te beginnen.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="21f5c-131">Selecteer een indicator die u wilt gebruiken in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="21f5c-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="21f5c-132">Deze lijst bevat de meest voorkomende aanwijzingen die voorkomen in phishing-e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="21f5c-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="21f5c-133">Wanneer deze optie is geselecteerd, zorgt u ervoor dat de positie van de indicator is ingesteld op **Vanaf** de tekst van het e-mailbericht en klikt u op **Tekst selecteren.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="21f5c-134">Markeer het gedeelte van uw nettolading waar deze indicator wordt weergegeven en klik op **Selecteren.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Gemarkeerde tekst in berichttekst om toe te voegen aan een indicator in de training voor de aanvalstraining](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="21f5c-136">Voeg een aangepaste beschrijving toe om de indicator te beschrijven en klik binnen het frame van het indicatorvoorbeeld om een voorbeeld van de indicator te zien.</span><span class="sxs-lookup"><span data-stu-id="21f5c-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="21f5c-137">Als u klaar bent, klikt u **op Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-137">Once done, click **Add**.</span></span> <span data-ttu-id="21f5c-138">Herhaal deze stappen totdat u alle indicatoren in uw nettolading hebt gedekt.</span><span class="sxs-lookup"><span data-stu-id="21f5c-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="21f5c-139">Nettolading controleren</span><span class="sxs-lookup"><span data-stu-id="21f5c-139">Review payload</span></span>

<span data-ttu-id="21f5c-140">U hebt uw nettolading gebouwd.</span><span class="sxs-lookup"><span data-stu-id="21f5c-140">You're done building your payload.</span></span> <span data-ttu-id="21f5c-141">Nu is het tijd om de details te bekijken en een voorbeeld van uw nettolading te bekijken.</span><span class="sxs-lookup"><span data-stu-id="21f5c-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="21f5c-142">Het voorbeeld bevat alle indicatoren die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="21f5c-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="21f5c-143">U kunt in deze stap elk deel van de nettolading bewerken.</span><span class="sxs-lookup"><span data-stu-id="21f5c-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="21f5c-144">Zodra u tevreden bent, kunt u **uw nettolading** indienen.</span><span class="sxs-lookup"><span data-stu-id="21f5c-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f5c-145">Nettoladingen die u hebt gemaakt, hebben **tenant** als bron.</span><span class="sxs-lookup"><span data-stu-id="21f5c-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="21f5c-146">Als u nettolading selecteert, moet u ervoor zorgen dat u Tenant niet **uitfiltert.**</span><span class="sxs-lookup"><span data-stu-id="21f5c-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="21f5c-147">Verwante koppelingen</span><span class="sxs-lookup"><span data-stu-id="21f5c-147">Related links</span></span>

[<span data-ttu-id="21f5c-148">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="21f5c-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="21f5c-149">Een phishing-aanval maken</span><span class="sxs-lookup"><span data-stu-id="21f5c-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="21f5c-150">Meer inzicht krijgen middels aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="21f5c-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
