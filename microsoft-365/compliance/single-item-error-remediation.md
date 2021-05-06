---
title: Foutherstel voor één item
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: U kunt een verwerkingsfout in een document in een revisieset in Advanced eDiscovery oplossen zonder dat u het proces voor het bulksgewijs herstellen van fouten moet volgen.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161657"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="bb02f-103">Herstel van fout met één item in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bb02f-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="bb02f-104">Foutsanering biedt Advanced eDiscovery gebruikers de mogelijkheid om gegevensproblemen op te lossen die voorkomen dat Advanced eDiscovery inhoud correct verwerkt.</span><span class="sxs-lookup"><span data-stu-id="bb02f-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="bb02f-105">Bestanden die met een wachtwoord zijn beveiligd, kunnen bijvoorbeeld niet worden verwerkt omdat deze bestanden zijn vergrendeld of versleuteld.</span><span class="sxs-lookup"><span data-stu-id="bb02f-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="bb02f-106">Voorheen kon u alleen bulksgewijs fouten corrigeren met [behulp van deze werkstroom.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="bb02f-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="bb02f-107">Maar soms is het niet zinvol om fouten in meerdere bestanden te corrigeren wanneer u niet zeker weet of een van deze bestanden reageert op de zaak die u onderzoekt.</span><span class="sxs-lookup"><span data-stu-id="bb02f-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="bb02f-108">Het is ook mogelijk niet zinvol om fouten te corrigeren voordat u de kans hebt gehad om de bestandsmetagegevens (zoals bestandslocatie of wie toegang had) te bekijken, om u te helpen bij het nemen van beslissingen over reactiesnelheid.</span><span class="sxs-lookup"><span data-stu-id="bb02f-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="bb02f-109">Een nieuwe functie met de naam single *item error remediation geeft* eDiscovery-managers de mogelijkheid om de metagegevens van bestanden te bekijken met een verwerkingsfout en zo nodig de fout rechtstreeks in de revisieset te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="bb02f-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="bb02f-110">In het artikel wordt beschreven hoe u bestanden kunt identificeren, negeren en corrigeren met verwerkingsfouten in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="bb02f-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="bb02f-111">Documenten identificeren met fouten</span><span class="sxs-lookup"><span data-stu-id="bb02f-111">Identify documents with errors</span></span>

<span data-ttu-id="bb02f-112">Documenten met verwerkingsfouten in een revisieset worden nu geïdentificeerd (met een banner).</span><span class="sxs-lookup"><span data-stu-id="bb02f-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="bb02f-113">U kunt de fout corrigeren of negeren.</span><span class="sxs-lookup"><span data-stu-id="bb02f-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="bb02f-114">In de volgende schermafbeelding ziet u de bewerkingsfoutbanner voor een Word-document in een revisieset die met een wachtwoord is beveiligd.</span><span class="sxs-lookup"><span data-stu-id="bb02f-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="bb02f-115">U ziet ook dat u de bestandsmetagegevens van documenten met verwerkingsfouten kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="bb02f-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banner weergegeven voor document met verwerkingsfout](../media/SIERimage1.png)

<span data-ttu-id="bb02f-117">U kunt ook zoeken naar documenten met verwerkingsfouten met behulp van de **statusstatus** verwerken bij het query's uitvoeren van [de documenten in een revisieset.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="bb02f-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![De voorwaarde Verwerkingsstatus gebruiken om te zoeken naar foutdocumenten](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="bb02f-119">Fouten negeren</span><span class="sxs-lookup"><span data-stu-id="bb02f-119">Ignore errors</span></span>

<span data-ttu-id="bb02f-120">U kunt een verwerkingsfout negeren door te klikken op **Negeren** in de banner met verwerkingsfouten.</span><span class="sxs-lookup"><span data-stu-id="bb02f-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="bb02f-121">Wanneer u een fout negeert, wordt het document verwijderd uit de [werkstroom bulksgewijs herstellen van fouten.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="bb02f-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="bb02f-122">Nadat een fout is genegeerd, verandert de documentbanner van kleur en wordt aangegeven dat de verwerkingsfout is genegeerd.</span><span class="sxs-lookup"><span data-stu-id="bb02f-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="bb02f-123">U kunt de beslissing om de fout te negeren op elk moment herstellen door op **Terugkeren te klikken.**</span><span class="sxs-lookup"><span data-stu-id="bb02f-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Klik op Negeren om de verwerkingsfout te negeren](../media/SIERimage3.png)

<span data-ttu-id="bb02f-125">U kunt ook zoeken naar alle documenten met een verwerkingsfout die is genegeerd met de voorwaarde Genegeerde verwerkingsfouten bij het opvragen van documenten in een revisieset. </span><span class="sxs-lookup"><span data-stu-id="bb02f-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![De voorwaarde Genegeerde verwerkingsfouten gebruiken om te zoeken naar genegeerde foutdocumenten](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="bb02f-127">Een document herstellen met fouten</span><span class="sxs-lookup"><span data-stu-id="bb02f-127">Remediate a document with errors</span></span>

<span data-ttu-id="bb02f-128">Soms moet u mogelijk een verwerkingsfout in documenten herstellen (door een wachtwoord te verwijderen, een versleuteld bestand te ontsleutelen of een beschadigd document te herstellen) en vervolgens het herstelde document toe te voegen aan de revisieset.</span><span class="sxs-lookup"><span data-stu-id="bb02f-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="bb02f-129">Op deze manier kunt u het foutdocument samen met de andere documenten in de revisieset bekijken en exporteren.</span><span class="sxs-lookup"><span data-stu-id="bb02f-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="bb02f-130">Als u één document wilt herstellen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="bb02f-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="bb02f-131">Klik **op Origineel**  >  **downloaden** om een kopie van het bestand naar een lokale computer te downloaden.</span><span class="sxs-lookup"><span data-stu-id="bb02f-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Het document downloaden met de verwerkingsfout](../media/SIERimage5.png)

2. <span data-ttu-id="bb02f-133">Herstel de fout in het bestand offline.</span><span class="sxs-lookup"><span data-stu-id="bb02f-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="bb02f-134">Voor versleutelde bestanden, waarvoor ontsleutelingssoftware vereist is, moet u wachtwoordbeveiliging verwijderen door het wachtwoord op te geven en het bestand op te slaan of een wachtwoordkraker te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bb02f-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="bb02f-135">Nadat u het bestand hebt gesaneerd, gaat u naar de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="bb02f-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="bb02f-136">Selecteer in de revisieset het bestand met de verwerkingsfout die u hebt gesaneerd en klik vervolgens op **Herstel**.</span><span class="sxs-lookup"><span data-stu-id="bb02f-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Klik op Herstel in de banner van het document met verwerkingsfout](../media/SIERimage6.png)


4. <span data-ttu-id="bb02f-138">Klik **op Bladeren,** ga naar de locatie van het bestand op uw lokale computer en selecteer het bestand.</span><span class="sxs-lookup"><span data-stu-id="bb02f-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Klik op Bladeren en selecteer het herstelbestand op uw lokale computer](../media/SIERimage7.png)

    <span data-ttu-id="bb02f-140">Nadat u het bestand hebt geselecteerd, wordt het automatisch geüpload naar de revisieset.</span><span class="sxs-lookup"><span data-stu-id="bb02f-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="bb02f-141">U kunt de verwerkingsstatus van het bestand bijhouden.</span><span class="sxs-lookup"><span data-stu-id="bb02f-141">You can track the processing status of the file.</span></span>

    ![De status van het herstelproces wordt weergegeven](../media/SIERimage8.png)

   <span data-ttu-id="bb02f-143">Nadat de verwerking is voltooid, kunt u het gesaneerd document bekijken.</span><span class="sxs-lookup"><span data-stu-id="bb02f-143">After processing is completed, you can view the remediated document.</span></span>

    ![U kunt het gesaneerd bestand weergeven in de oorspronkelijke indeling in de revisieset](../media/SIERimage9.png)

<span data-ttu-id="bb02f-145">Zie Wat gebeurt er wanneer bestanden worden gesaneerd voor meer informatie over wat er gebeurt wanneer een document [wordt gesaneerd.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)</span><span class="sxs-lookup"><span data-stu-id="bb02f-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="bb02f-146">Zoeken naar hersteldocumenten</span><span class="sxs-lookup"><span data-stu-id="bb02f-146">Search for remediated documents</span></span>

<span data-ttu-id="bb02f-147">U kunt zoeken naar alle documenten in een revisieset  die zijn gesaneerd met behulp van de voorwaarde Trefwoorden en de volgende eigenschap:waardepaar opgeven: **IsFromErrorRemediation:true.**</span><span class="sxs-lookup"><span data-stu-id="bb02f-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="bb02f-148">Deze eigenschap is ook beschikbaar in het exportladingsbestand wanneer u documenten exporteert uit een revisieset.</span><span class="sxs-lookup"><span data-stu-id="bb02f-148">This property is also available in the export load file when you export documents from a review set.</span></span>
