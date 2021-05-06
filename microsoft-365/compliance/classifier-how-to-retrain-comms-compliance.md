---
title: Een classificatie opnieuw trainen voor communicatiecompliance
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
description: Meer informatie over het geven van feedback aan een trainbare classificatie in communicatie compliance.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161916"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="ccc79-103">Een classificatie opnieuw trainen voor communicatiecompliance</span><span class="sxs-lookup"><span data-stu-id="ccc79-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="ccc79-104">Een Microsoft 365 trainable classifier is een hulpmiddel dat u kunt trainen om verschillende soorten inhoud te herkennen door deze voorbeelden te geven om naar te kijken.</span><span class="sxs-lookup"><span data-stu-id="ccc79-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="ccc79-105">Nadat u bent opgeleid, kunt u het gebruiken om het item te identificeren voor de toepassing van Office gevoeligheidslabels, compliancebeleid voor communicatie en bewaarlabelbeleid.</span><span class="sxs-lookup"><span data-stu-id="ccc79-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="ccc79-106">In dit artikel wordt beschreven hoe u de prestaties van aangepaste, trainbare classificaties en sommige vooraf getrainde classificaties kunt verbeteren door hen extra feedback te geven.</span><span class="sxs-lookup"><span data-stu-id="ccc79-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="ccc79-107">Zie Meer informatie over leerbare classificaties voor meer informatie over de verschillende typen [classificaties.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="ccc79-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="ccc79-108">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="ccc79-108">Permissions</span></span>

<span data-ttu-id="ccc79-109">Toegang tot classificaties in het Microsoft 365 compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="ccc79-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="ccc79-110">de rol van compliancebeheerder of compliancegegevensbeheerder is vereist om een classificatie te trainen</span><span class="sxs-lookup"><span data-stu-id="ccc79-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="ccc79-111">U hebt accounts met deze machtigingen nodig om classificaties in deze scenario's te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="ccc79-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="ccc79-112">Scenario communicatie compliancebeleid: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="ccc79-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="ccc79-113">Algemene werkstroom</span><span class="sxs-lookup"><span data-stu-id="ccc79-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccc79-114">U geeft feedback in de compliance-oplossing die de classificatie gebruikt als voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="ccc79-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="ccc79-115">**Als u geen communicatie-compliancebeleid hebt dat een classificatie als voorwaarde gebruikt, stopt u hier.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="ccc79-116">Als u uw classificaties gebruikt, kunt u de nauwkeurigheid van de classificaties die ze maken, vergroten.</span><span class="sxs-lookup"><span data-stu-id="ccc79-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="ccc79-117">U doet dit door de kwaliteit te evalueren van de classificaties die zijn gemaakt voor items die zijn geïdentificeerd als een overeenkomst of geen overeenkomst.</span><span class="sxs-lookup"><span data-stu-id="ccc79-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="ccc79-118">Nadat u 30 evaluaties voor een classificatie hebt gemaakt, is die feedback nodig en wordt deze automatisch opnieuw opgeleid.</span><span class="sxs-lookup"><span data-stu-id="ccc79-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="ccc79-119">Zie Processtroom voor het opnieuw bijscholen van een classificatie voor meer informatie over de algehele werkstroom voor het opnieuw bijscholen van een [classificatie.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="ccc79-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="ccc79-120">Een classificatie moet al zijn gepubliceerd en in gebruik zijn voordat deze opnieuw kan worden opgeleid.</span><span class="sxs-lookup"><span data-stu-id="ccc79-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="ccc79-121">Een classificatie opnieuw trainen in communicatie compliancebeleid</span><span class="sxs-lookup"><span data-stu-id="ccc79-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="ccc79-122">Open het communicatie-compliancebeleid dat een classificatie gebruikt als voorwaarde en kies een van de geïdentificeerde items in de lijst **In** behandeling.</span><span class="sxs-lookup"><span data-stu-id="ccc79-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="ccc79-123">Kies het beletselteken en **de classificatie Verbeteren.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="ccc79-124">Als het **item een echt positief** item is, kiest u in het deelvenster Gedetailleerde feedback de optie **Overeenkomen.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="ccc79-125">Als het item een onwaar positief item is, dat wil zeggen dat het ten onrechte is opgenomen in de categorie, kiest u **Geen overeenkomst.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="ccc79-126">Als er een andere classificatie is die geschikter is voor het item, kunt u dit kiezen in de lijst Andere **trainbare classificaties** voorstellen.</span><span class="sxs-lookup"><span data-stu-id="ccc79-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="ccc79-127">Hiermee wordt de andere classifier triggerd om het item te evalueren.</span><span class="sxs-lookup"><span data-stu-id="ccc79-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="ccc79-128">U kunt feedback geven over meerdere items tegelijk door ze allemaal te kiezen en vervolgens **Gedetailleerde feedback geven** op de opdrachtbalk te kiezen.</span><span class="sxs-lookup"><span data-stu-id="ccc79-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="ccc79-129">Kies **Feedback verzenden** om uw evaluatie van de classificaties te verzenden en andere `match` `not a match` trainbare classificaties voor te stellen.</span><span class="sxs-lookup"><span data-stu-id="ccc79-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="ccc79-130">Wanneer u 30 exemplaren van feedback hebt gegeven aan een classificatie, wordt deze automatisch opnieuw opgeleid.</span><span class="sxs-lookup"><span data-stu-id="ccc79-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="ccc79-131">Omscholing kan tussen 1 en 4 uur duren.</span><span class="sxs-lookup"><span data-stu-id="ccc79-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="ccc79-132">Classificaties kunnen slechts twee keer per dag opnieuw worden opgeleid.</span><span class="sxs-lookup"><span data-stu-id="ccc79-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccc79-133">Deze informatie gaat naar de classificatie in uw tenant, **deze gaat niet terug naar Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="ccc79-134">Open de **pagina Gegevensclassificatie** in **het Microsoft 365 compliancecentrum**.</span><span class="sxs-lookup"><span data-stu-id="ccc79-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="ccc79-135">Open **Trainable classifiers**.</span><span class="sxs-lookup"><span data-stu-id="ccc79-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="ccc79-136">De classificatie die is gebruikt in het compliancebeleid voor communicatie wordt weergegeven onder de **kop Opnieuw trainen.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![classifier in omscholingsstatus](../media/classifier-retraining.png)

9. <span data-ttu-id="ccc79-138">Nadat de omscholing is voltooid, kiest u de classificatie om het overzicht van de omscholing te openen.</span><span class="sxs-lookup"><span data-stu-id="ccc79-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Overzicht van omscholingsresultaten van classifier](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="ccc79-140">Bekijk de aanbevolen actie en de voorspellingsvergelijkingen van de opnieuw getrainde en momenteel gepubliceerde versies van de classificatie.</span><span class="sxs-lookup"><span data-stu-id="ccc79-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="ccc79-141">Als u tevreden bent over de resultaten van de omscholing, kiest u **Opnieuw publiceren.**</span><span class="sxs-lookup"><span data-stu-id="ccc79-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="ccc79-142">Als u niet tevreden bent over de resultaten van de omscholing, kunt u ervoor kiezen om extra feedback te geven aan de classificatie in de compliance-interface Communicatie en een andere herscholingscyclus te starten of niets te doen in welk geval de momenteel gepubliceerde versie van de classificatie blijft worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ccc79-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="ccc79-143">Details over het opnieuw publiceren van aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="ccc79-143">Details on republishing recommendations</span></span>

<span data-ttu-id="ccc79-144">Hier vindt u wat informatie over de manier waarop we de aanbeveling formuleren om een omscholingsclassifier opnieuw te publiceren of om verdere omscholing voor te stellen.</span><span class="sxs-lookup"><span data-stu-id="ccc79-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="ccc79-145">Dit vereist een beetje meer inzicht in de manier waarop trainbare classificaties werken.</span><span class="sxs-lookup"><span data-stu-id="ccc79-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="ccc79-146">Na een nieuwe training evalueren we de prestaties van de classificatie op zowel de items met feedback als alle items die oorspronkelijk zijn gebruikt om de classificatie te trainen.</span><span class="sxs-lookup"><span data-stu-id="ccc79-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="ccc79-147">Voor ingebouwde modellen zijn items die worden gebruikt om de classificatie te trainen de items die door Microsoft worden gebruikt om het model te maken.</span><span class="sxs-lookup"><span data-stu-id="ccc79-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="ccc79-148">Voor aangepaste modellen zijn items die in de oorspronkelijke training worden gebruikt, afkomstig van de sites die u hebt toegevoegd voor testen en controleren.</span><span class="sxs-lookup"><span data-stu-id="ccc79-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="ccc79-149">We vergelijken de prestatienummers voor beide sets items voor de opnieuw omgeoefde en gepubliceerde classificatie om een aanbeveling te geven over de vraag of er verbetering is in het opnieuw publiceren.</span><span class="sxs-lookup"><span data-stu-id="ccc79-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ccc79-150">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ccc79-150">See also</span></span>

- [<span data-ttu-id="ccc79-151">Meer informatie over trainbare classificaties</span><span class="sxs-lookup"><span data-stu-id="ccc79-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="ccc79-152">Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ccc79-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)