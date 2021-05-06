---
title: Een classificatie opnieuw trainen voor de inhoudsverkenner
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het geven van feedback aan een trainbare classificatie in Inhoudsverkenner.
ms.openlocfilehash: d61437634dcad7f01a6737947b0f32f42de2818e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161914"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="bd826-103">Een classificatie opnieuw trainen voor de inhoudsverkenner</span><span class="sxs-lookup"><span data-stu-id="bd826-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="bd826-104">Een Microsoft 365 trainable classifier is een hulpmiddel dat u kunt trainen om verschillende soorten inhoud te herkennen door deze voorbeelden te geven om naar te kijken.</span><span class="sxs-lookup"><span data-stu-id="bd826-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="bd826-105">Nadat u bent opgeleid, kunt u het gebruiken om het item te identificeren voor de toepassing van Office gevoeligheidslabels, compliancebeleid voor communicatie en bewaarlabelbeleid.</span><span class="sxs-lookup"><span data-stu-id="bd826-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="bd826-106">In dit artikel wordt beschreven hoe u de prestaties van aangepaste, trainbare classificaties en sommige vooraf getrainde classificaties kunt verbeteren door hen extra feedback te geven.</span><span class="sxs-lookup"><span data-stu-id="bd826-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="bd826-107">Zie Meer informatie over leerbare classificaties voor meer informatie over de verschillende typen [classificaties.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="bd826-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="bd826-108">Bekijk deze video voor een beknopt overzicht van het afstemmen en omscholingsproces.</span><span class="sxs-lookup"><span data-stu-id="bd826-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="bd826-109">U moet dit volledige artikel nog steeds lezen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd826-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="bd826-110">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="bd826-110">Permissions</span></span>

<span data-ttu-id="bd826-111">Toegang tot classificaties in het Microsoft 365 compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="bd826-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="bd826-112">de rol van compliancebeheerder of compliancegegevensbeheerder is vereist om een classificatie te trainen</span><span class="sxs-lookup"><span data-stu-id="bd826-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="bd826-113">U hebt accounts met deze machtigingen nodig om classificaties in deze scenario's te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="bd826-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="bd826-114">Scenario bewaarlabelbeleid: rollen recordbeheer en bewaarbeheer</span><span class="sxs-lookup"><span data-stu-id="bd826-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="bd826-115">Algemene werkstroom</span><span class="sxs-lookup"><span data-stu-id="bd826-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd826-116">U geeft feedback in inhoudsverkenner voor het automatisch toepassen van bewaarlabelbeleid op Exchange items en gebruikt de classificatie als voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="bd826-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="bd826-117">**Als u geen bewaarbeleid hebt dat automatisch een bewaarlabel op items Exchange en een classificatie als voorwaarde gebruikt, stopt u hier.**</span><span class="sxs-lookup"><span data-stu-id="bd826-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="bd826-118">Als u uw classificaties gebruikt, kunt u de nauwkeurigheid van de classificaties die ze maken, vergroten.</span><span class="sxs-lookup"><span data-stu-id="bd826-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="bd826-119">U doet dit door de kwaliteit te evalueren van de classificaties die zijn gemaakt voor items die zijn geïdentificeerd als een overeenkomst of geen overeenkomst.</span><span class="sxs-lookup"><span data-stu-id="bd826-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="bd826-120">Nadat u 30 evaluaties voor een classificatie hebt gemaakt, is die feedback nodig en wordt deze automatisch opnieuw opgeleid.</span><span class="sxs-lookup"><span data-stu-id="bd826-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="bd826-121">Zie Processtroom voor het opnieuw bijscholen van een classificatie voor meer informatie over de algehele werkstroom voor het opnieuw bijscholen van een [classificatie.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="bd826-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="bd826-122">Een classificatie moet al zijn gepubliceerd en in gebruik zijn voordat deze opnieuw kan worden opgeleid.</span><span class="sxs-lookup"><span data-stu-id="bd826-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="bd826-123">Een classificatie opnieuw trainen voor de inhoudsverkenner</span><span class="sxs-lookup"><span data-stu-id="bd826-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="bd826-124">Meld u aan bij Microsoft 365 compliancecentrum met roltoegang voor compliancebeheerders of beveiligingsbeheerders en open Microsoft 365 **compliancecentrum**  >  **Gegevensclassificatie**  >  **Inhoudverkenner.**</span><span class="sxs-lookup"><span data-stu-id="bd826-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="bd826-125">Vouw **trainbare classificaties** uit onder de lijst Filter op labels, infotypen of **categorieën.**</span><span class="sxs-lookup"><span data-stu-id="bd826-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd826-126">Het kan maximaal acht dagen duren voordat samengevoegde items worden weergegeven onder de kop met trainbare classificaties.</span><span class="sxs-lookup"><span data-stu-id="bd826-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="bd826-127">Kies de trainbare classificatie die u hebt gebruikt in het beleid voor het automatisch toepassen van bewaarlabels.</span><span class="sxs-lookup"><span data-stu-id="bd826-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="bd826-128">Dit is de trainbare classificatie waar u feedback over geeft.</span><span class="sxs-lookup"><span data-stu-id="bd826-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="bd826-129">Als een item een vermelding heeft in de kolom **Bewaarlabel,** betekent dit dat het item is geclassificeerd als `match` een .</span><span class="sxs-lookup"><span data-stu-id="bd826-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="bd826-130">Als een item geen vermelding heeft  in de kolom Bewaarlabel, betekent dit dat het is geclassificeerd als `close match` een .</span><span class="sxs-lookup"><span data-stu-id="bd826-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="bd826-131">U kunt de precisie van de classificatie het meest verbeteren door feedback te geven over `close match` items.</span><span class="sxs-lookup"><span data-stu-id="bd826-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="bd826-132">Kies een item en open het.</span><span class="sxs-lookup"><span data-stu-id="bd826-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="bd826-133">U kunt feedback geven over meerdere items tegelijk door ze allemaal te kiezen en vervolgens Classificatie **verbeteren** op de opdrachtbalk te kiezen.</span><span class="sxs-lookup"><span data-stu-id="bd826-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="bd826-134">Kies **Feedback geven.**</span><span class="sxs-lookup"><span data-stu-id="bd826-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="bd826-135">Als het **item een echt positief** item is, kiest u in het deelvenster Gedetailleerde feedback de optie **Overeenkomen.**</span><span class="sxs-lookup"><span data-stu-id="bd826-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="bd826-136">Als het item een onwaar positief item is, dat wil zeggen dat het ten onrechte is opgenomen in de categorie, kiest u **Geen overeenkomst.**</span><span class="sxs-lookup"><span data-stu-id="bd826-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="bd826-137">Als er een andere classificatie is die geschikter is voor het item, kunt u dit kiezen in de lijst Andere **trainbare classificaties** voorstellen.</span><span class="sxs-lookup"><span data-stu-id="bd826-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="bd826-138">Hiermee wordt de andere classifier triggerd om het item te evalueren.</span><span class="sxs-lookup"><span data-stu-id="bd826-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="bd826-139">Kies **Feedback verzenden** om uw evaluatie van de classificaties te verzenden en andere `match` `not a match` trainbare classificaties voor te stellen.</span><span class="sxs-lookup"><span data-stu-id="bd826-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="bd826-140">Wanneer u 30 exemplaren van feedback hebt gegeven aan een classificatie, wordt deze automatisch opnieuw opgeleid.</span><span class="sxs-lookup"><span data-stu-id="bd826-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="bd826-141">Omscholing kan één tot vier uur duren.</span><span class="sxs-lookup"><span data-stu-id="bd826-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="bd826-142">Classificaties kunnen slechts twee keer per dag opnieuw worden opgeleid.</span><span class="sxs-lookup"><span data-stu-id="bd826-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd826-143">Deze informatie gaat naar de classificatie in uw tenant, **deze gaat niet terug naar Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="bd826-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="bd826-144">Open **Trainable classifiers**.</span><span class="sxs-lookup"><span data-stu-id="bd826-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="bd826-145">De classificatie die is gebruikt in het compliancebeleid voor communicatie wordt weergegeven onder de **kop Opnieuw trainen.**</span><span class="sxs-lookup"><span data-stu-id="bd826-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classifier in omscholingsstatus](../media/classifier-retraining.png)

11. <span data-ttu-id="bd826-147">Nadat de omscholing is voltooid, kiest u de classificatie om het overzicht van de omscholing te openen.</span><span class="sxs-lookup"><span data-stu-id="bd826-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Overzicht van omscholingsresultaten van classifier](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="bd826-149">Bekijk de aanbevolen actie en de voorspellingsvergelijkingen van de opnieuw getrainde en momenteel gepubliceerde versies van de classificatie.</span><span class="sxs-lookup"><span data-stu-id="bd826-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="bd826-150">Als u tevreden bent over de resultaten van de omscholing, kiest u **Opnieuw publiceren.**</span><span class="sxs-lookup"><span data-stu-id="bd826-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="bd826-151">Als u niet tevreden bent over de resultaten van de omscholing, kunt u ervoor kiezen om extra feedback te geven aan de classificatie in de compliance-interface Communicatie en een andere herscholingscyclus te starten of niets te doen in welk geval de momenteel gepubliceerde versie van de classificatie blijft worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="bd826-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="bd826-152">Details over het opnieuw publiceren van aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="bd826-152">Details on republishing recommendations</span></span>

<span data-ttu-id="bd826-153">Hier vindt u wat informatie over de manier waarop we de aanbeveling formuleren om een omscholingsclassifier opnieuw te publiceren of om verdere omscholing voor te stellen.</span><span class="sxs-lookup"><span data-stu-id="bd826-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="bd826-154">Dit vereist een beetje meer inzicht in de manier waarop trainbare classificaties werken.</span><span class="sxs-lookup"><span data-stu-id="bd826-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="bd826-155">Na een nieuwe training evalueren we de prestaties van de classificatie op zowel de items met feedback als alle items die oorspronkelijk zijn gebruikt om de classificatie te trainen.</span><span class="sxs-lookup"><span data-stu-id="bd826-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="bd826-156">Voor ingebouwde modellen zijn items die worden gebruikt om de classificatie te trainen de items die door Microsoft worden gebruikt om het model te maken.</span><span class="sxs-lookup"><span data-stu-id="bd826-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="bd826-157">Voor aangepaste modellen zijn items die in de oorspronkelijke training worden gebruikt, afkomstig van de sites die u hebt toegevoegd voor testen en controleren.</span><span class="sxs-lookup"><span data-stu-id="bd826-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="bd826-158">We vergelijken de prestatienummers voor beide sets items voor de opnieuw omgeoefde en gepubliceerde classificatie om een aanbeveling te geven over de vraag of er verbetering is in het opnieuw publiceren.</span><span class="sxs-lookup"><span data-stu-id="bd826-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="bd826-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bd826-159">See also</span></span>

- [<span data-ttu-id="bd826-160">Meer informatie over trainbare classificaties</span><span class="sxs-lookup"><span data-stu-id="bd826-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="bd826-161">Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="bd826-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)