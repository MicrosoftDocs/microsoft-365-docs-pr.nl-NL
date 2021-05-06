---
title: Aan de slag met trainbare classificaties
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Een Microsoft 365-classificatie is een hulpmiddel dat u kunt trainen om verschillende soorten inhoud te herkennen door deze voorbeelden te geven om naar te kijken. In dit artikel wordt beschreven hoe u een aangepaste classificatie kunt maken en trainen en hoe u deze opnieuw kunt trainen om de nauwkeurigheid te vergroten.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161919"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="17611-104">Aan de slag met trainbare classificaties</span><span class="sxs-lookup"><span data-stu-id="17611-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="17611-105">Een Microsoft 365 trainable classifier is een hulpmiddel dat u kunt trainen om verschillende soorten inhoud te herkennen door deze voorbeelden te geven om naar te kijken.</span><span class="sxs-lookup"><span data-stu-id="17611-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="17611-106">Nadat u bent opgeleid, kunt u het gebruiken om het item te identificeren voor de toepassing van Office gevoeligheidslabels, compliancebeleid voor communicatie en bewaarlabelbeleid.</span><span class="sxs-lookup"><span data-stu-id="17611-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="17611-107">Bij het maken van een aangepaste, trainbare classificatie moet u eerst steekproeven geven die door de mens zijn genomen en die positief overeenkomen met de categorie.</span><span class="sxs-lookup"><span data-stu-id="17611-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="17611-108">Nadat deze zijn verwerkt, test u de mogelijkheid voor classificaties om te voorspellen door een combinatie van positieve en negatieve steekproeven te geven.</span><span class="sxs-lookup"><span data-stu-id="17611-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="17611-109">In dit artikel wordt beschreven hoe u een aangepaste classificatie kunt maken en trainen en hoe u de prestaties van aangepaste, trainbare classificaties en vooraf getrainde classificaties gedurende hun hele leven kunt verbeteren door omscholing.</span><span class="sxs-lookup"><span data-stu-id="17611-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="17611-110">Zie Meer informatie over leerbare classificaties voor meer informatie over de verschillende typen [classificaties.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="17611-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="17611-111">Bekijk deze video voor een beknopt overzicht van het maken van een trainbare classificatie.</span><span class="sxs-lookup"><span data-stu-id="17611-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="17611-112">U moet dit volledige artikel nog steeds lezen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="17611-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="17611-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="17611-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="17611-114">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="17611-114">Licensing requirements</span></span>

<span data-ttu-id="17611-115">Classificaties zijn een Microsoft 365 E5 of E5 Compliance-functie.</span><span class="sxs-lookup"><span data-stu-id="17611-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="17611-116">U moet een van deze abonnementen hebben om er gebruik van te kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="17611-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="17611-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="17611-117">Permissions</span></span>

<span data-ttu-id="17611-118">Toegang tot classificaties in de gebruikersinterface:</span><span class="sxs-lookup"><span data-stu-id="17611-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="17611-119">de globale beheerder moet ervoor kiezen om aangepaste classificaties te maken voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="17611-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="17611-120">De rol compliancebeheerder is vereist voor het trainen van een classificatie.</span><span class="sxs-lookup"><span data-stu-id="17611-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="17611-121">U hebt accounts met deze machtigingen nodig om classificaties in deze scenario's te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="17611-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="17611-122">Scenario bewaarlabelbeleid: rollen recordbeheer en bewaarbeheer</span><span class="sxs-lookup"><span data-stu-id="17611-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="17611-123">Scenario gevoeligheidslabelbeleid: beveiligingsbeheerder, compliancebeheerder, compliancegegevensbeheerder</span><span class="sxs-lookup"><span data-stu-id="17611-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="17611-124">Scenario communicatie compliancebeleid: Insider Risk Management Admin, Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="17611-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="17611-125">Standaard kan alleen de gebruiker die een aangepaste classificatie maakt voorspellingen trainen en bekijken die door die classificatie zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="17611-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="17611-126">Voorbereiden op een aangepaste, trainbare classificatie</span><span class="sxs-lookup"><span data-stu-id="17611-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="17611-127">Het is handig om te begrijpen wat er nodig is bij het maken van een aangepaste, trainbare classificatie voordat u binnen duikt.</span><span class="sxs-lookup"><span data-stu-id="17611-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="17611-128">Tijdlijn</span><span class="sxs-lookup"><span data-stu-id="17611-128">Timeline</span></span>

<span data-ttu-id="17611-129">Deze tijdlijn weerspiegelt een voorbeeldimplementatie van trainable classifiers.</span><span class="sxs-lookup"><span data-stu-id="17611-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="17611-131">Opt-in is de eerste keer vereist voor trainbare classificaties.</span><span class="sxs-lookup"><span data-stu-id="17611-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="17611-132">Het duurt twaalf dagen voordat Microsoft 365 een basislijnevaluatie van de inhoud van uw organisatie voltooit.</span><span class="sxs-lookup"><span data-stu-id="17611-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="17611-133">Neem contact op met de globale beheerder om het opt-inproces te starten.</span><span class="sxs-lookup"><span data-stu-id="17611-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="17611-134">Algemene werkstroom</span><span class="sxs-lookup"><span data-stu-id="17611-134">Overall workflow</span></span>

<span data-ttu-id="17611-135">Zie Process flow for creating customer trainable classifiers (Processtroom voor het maken van [klants trainable classifiers)](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)voor meer informatie over de algehele werkstroom van het maken van aangepaste, trainbare classificaties.</span><span class="sxs-lookup"><span data-stu-id="17611-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="17611-136">Inhoud van het zaad</span><span class="sxs-lookup"><span data-stu-id="17611-136">Seed content</span></span>

<span data-ttu-id="17611-137">Als u wilt dat een trainbare classificatie een item onafhankelijk en nauwkeurig identificeert als een bepaalde inhoudscategorie, moet u eerst veel voorbeelden van het type inhoud in de categorie presenteren.</span><span class="sxs-lookup"><span data-stu-id="17611-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="17611-138">Deze voeding van steekproeven aan de trainbare classificatie wordt *seeding genoemd.*</span><span class="sxs-lookup"><span data-stu-id="17611-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="17611-139">De inhoud van het zaad wordt geselecteerd door een mens en wordt beoordeeld als de categorie met inhoud.</span><span class="sxs-lookup"><span data-stu-id="17611-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="17611-140">U moet ten minste 50 positieve steekproeven hebben en maar liefst 500.</span><span class="sxs-lookup"><span data-stu-id="17611-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="17611-141">De trainable classifier verwerkt maximaal de 500 meest recente gemaakte steekproeven (per bestand dat datum-/tijdstempel is gemaakt).</span><span class="sxs-lookup"><span data-stu-id="17611-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="17611-142">Hoe meer steekproeven u op geeft, hoe nauwkeuriger de voorspellingen die de classificatie zal maken.</span><span class="sxs-lookup"><span data-stu-id="17611-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="17611-143">Inhoud testen</span><span class="sxs-lookup"><span data-stu-id="17611-143">Testing content</span></span>

<span data-ttu-id="17611-144">Nadat de trainbare classificatie voldoende positieve steekproeven heeft verwerkt om een voorspellingsmodel te maken, moet u de voorspellingen testen om te zien of de classificatie correct onderscheid kan maken tussen items die overeenkomen met de categorie en items die niet overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="17611-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="17611-145">U doet dit door een andere, hopelijk grotere, reeks door de mens genomen inhoud te selecteren die bestaat uit steekproeven die in de categorie moeten vallen en steekproeven die dat niet doen.</span><span class="sxs-lookup"><span data-stu-id="17611-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="17611-146">U moet testen met andere gegevens dan de eerste begingegevens die u voor het eerst hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="17611-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="17611-147">Wanneer deze zijn verwerkt, gaat u handmatig door de resultaten en controleert u of elke voorspelling juist, onjuist of niet zeker is.</span><span class="sxs-lookup"><span data-stu-id="17611-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="17611-148">De trainable classifier gebruikt deze feedback om het voorspellingsmodel te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="17611-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="17611-149">Voor de beste resultaten moet u ten minste 200 items in uw testvoorbeeldset hebben met een gelijkmatige verdeling van positieve en negatieve overeenkomsten.</span><span class="sxs-lookup"><span data-stu-id="17611-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="17611-150">Een trainbare classificatie maken</span><span class="sxs-lookup"><span data-stu-id="17611-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="17611-151">Verzamel tussen de 50-500 inhoudsitems voor zaad.</span><span class="sxs-lookup"><span data-stu-id="17611-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="17611-152">Dit moeten alleen steekproeven zijn die sterk het type inhoud vertegenwoordigen dat door de trainbare classificatie wordt bepaald als zijnde in de classificatiecategorie.</span><span class="sxs-lookup"><span data-stu-id="17611-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="17611-153">Zie Standaard [verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) voor de ondersteunde bestandstypen.</span><span class="sxs-lookup"><span data-stu-id="17611-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="17611-154">De zaad- en testvoorbeelditems mogen niet worden versleuteld en moeten in het Engels zijn.</span><span class="sxs-lookup"><span data-stu-id="17611-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="17611-155">Zorg ervoor dat de items in de zaadset sterke **voorbeelden van** de categorie zijn.</span><span class="sxs-lookup"><span data-stu-id="17611-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="17611-156">De trainable classifier bouwt in eerste instantie zijn model op basis van wat u het start.</span><span class="sxs-lookup"><span data-stu-id="17611-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="17611-157">De classificatie gaat ervan uit dat alle zaadmonsters sterke positieve punten zijn en dat u niet weet of een steekproef een zwakke of negatieve overeenkomst met de categorie is.</span><span class="sxs-lookup"><span data-stu-id="17611-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="17611-158">Plaats de inhoud van het zaad in een SharePoint onlinemap die alleen bestemd is voor het vasthouden van *de inhoud van het zaad.*</span><span class="sxs-lookup"><span data-stu-id="17611-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="17611-159">Noteer de URL van de site, bibliotheek en map.</span><span class="sxs-lookup"><span data-stu-id="17611-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="17611-160">Als u een nieuwe site en map maakt voor uw seedgegevens, moet u ten minste een uur toestaan dat die locatie wordt geïndexeerd voordat u de trainbare classificatie maakt waarmee die seedgegevens worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="17611-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="17611-161">Meld u aan bij Microsoft 365 compliancecentrum met roltoegang voor compliancebeheerders of beveiligingsbeheerders en open Microsoft 365 **compliancecentrum** of Microsoft 365 **beveiligingscentrum**  >  **Gegevensclassificatie.**</span><span class="sxs-lookup"><span data-stu-id="17611-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="17611-162">Kies het **tabblad Trainable classifiers.**</span><span class="sxs-lookup"><span data-stu-id="17611-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="17611-163">Kies **Trainable classifier maken.**</span><span class="sxs-lookup"><span data-stu-id="17611-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="17611-164">Vul de juiste waarden in voor de en velden van de categorie items die u wilt identificeren met `Name` `Description` deze trainbare classificatie.</span><span class="sxs-lookup"><span data-stu-id="17611-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="17611-165">Kies de SharePoint onlinesite, bibliotheek en map-URL voor de site met inhoud van het zaad in stap 2.</span><span class="sxs-lookup"><span data-stu-id="17611-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="17611-166">Kies `Add` .</span><span class="sxs-lookup"><span data-stu-id="17611-166">Choose `Add`.</span></span>

8. <span data-ttu-id="17611-167">Controleer de instellingen en kies `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="17611-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="17611-168">Binnen 24 uur verwerkt de trainbare classificatie de seedgegevens en maakt u een voorspellingsmodel.</span><span class="sxs-lookup"><span data-stu-id="17611-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="17611-169">De classificatiestatus is terwijl `In progress` de seedgegevens worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="17611-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="17611-170">Wanneer de classificatie klaar is met de verwerking van de seedgegevens, wordt de status gewijzigd in `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="17611-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="17611-171">U kunt nu de detailspagina bekijken door de classificatie te kiezen.</span><span class="sxs-lookup"><span data-stu-id="17611-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="17611-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="17611-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="17611-173">Verzamel ten minste 200 testinhouditems (maximaal 10.000) voor de beste resultaten.</span><span class="sxs-lookup"><span data-stu-id="17611-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="17611-174">Dit moet een combinatie zijn van items die sterke positieven, sterke negatieven en sommige items zijn die iets minder duidelijk zijn in hun aard.</span><span class="sxs-lookup"><span data-stu-id="17611-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="17611-175">Zie Standaard [verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) voor de ondersteunde bestandstypen.</span><span class="sxs-lookup"><span data-stu-id="17611-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="17611-176">De voorbeelditems mogen niet worden versleuteld en moeten in het Engels zijn.</span><span class="sxs-lookup"><span data-stu-id="17611-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="17611-177">Plaats de testinhoud in een SharePoint onlinemap die alleen is bedoeld om de *testinhoud vast te houden.*</span><span class="sxs-lookup"><span data-stu-id="17611-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="17611-178">Noteer de SharePoint onlinesite, bibliotheek en map-URL.</span><span class="sxs-lookup"><span data-stu-id="17611-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="17611-179">Als u een nieuwe site en map voor uw testgegevens maakt, moet u ten minste een uur toestaan dat die locatie wordt geïndexeerd voordat u de trainbare classificatie maakt waarmee die seedgegevens worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="17611-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="17611-180">Kies `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="17611-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="17611-181">Kies de SharePoint url van de onlinesite, bibliotheek en map voor de testinhoudssite uit stap 12.</span><span class="sxs-lookup"><span data-stu-id="17611-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="17611-182">Kies `Add` .</span><span class="sxs-lookup"><span data-stu-id="17611-182">Choose `Add`.</span></span>

15. <span data-ttu-id="17611-183">Maak de wizard af door te kiezen `Done` .</span><span class="sxs-lookup"><span data-stu-id="17611-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="17611-184">Het duurt maximaal een uur voordat de testbestanden worden verwerkt door uw trainbare classificatie.</span><span class="sxs-lookup"><span data-stu-id="17611-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="17611-185">Wanneer de trainable classifier klaar is met het verwerken van uw testbestanden, wordt de status op de detailspagina gewijzigd in `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="17611-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="17611-186">Als u de grootte van het testvoorbeeld wilt vergroten, kiest en laat u de `Add items to test` trainbare classifier de extra items verwerken.</span><span class="sxs-lookup"><span data-stu-id="17611-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="17611-187">![Schermafbeelding bekijken](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="17611-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="17611-188">Kies `Tested items to review` het tabblad om items te bekijken.</span><span class="sxs-lookup"><span data-stu-id="17611-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="17611-189">Microsoft 365 presenteert 30 items tegelijk.</span><span class="sxs-lookup"><span data-stu-id="17611-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="17611-190">Bekijk ze en kies in `We predict this item is "Relevant". Do you agree?` het vak een of of `Yes` `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="17611-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="17611-191">De nauwkeurigheid van het model wordt automatisch bijgewerkt na elke 30 items.</span><span class="sxs-lookup"><span data-stu-id="17611-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="17611-192">![het vak Items bekijken](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="17611-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="17611-193">Bekijk *ten minste* 200 items.</span><span class="sxs-lookup"><span data-stu-id="17611-193">Review *at least* 200 items.</span></span> <span data-ttu-id="17611-194">Zodra de nauwkeurigheidsscore is  gestabiliseerd, wordt de publicatieoptie beschikbaar en wordt de classificatiestatus ervan in het gelijk `Ready to use` gesteld.</span><span class="sxs-lookup"><span data-stu-id="17611-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="17611-195">![nauwkeurigheidsscore en klaar om te publiceren](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="17611-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="17611-196">Publiceer de classificatie.</span><span class="sxs-lookup"><span data-stu-id="17611-196">Publish the classifier.</span></span>

21. <span data-ttu-id="17611-197">Nadat uw classificatie is [gepubliceerd,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) is uw classificatie beschikbaar als voorwaarde in [Office autolabels](apply-sensitivity-label-automatically.md)met gevoeligheidslabels , automatisch bewaarlabelbeleid toepassen op basis van een voorwaarde en in [Communicatie compliance](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="17611-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>