---
title: Een termenset met een SKOS-indeling importeren
description: Leer hoe u een termenset met een SKOS-indeling kunt importeren
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 96ffa22880aa9bcb70c0f7159ac7587c911b375b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087353"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="78b53-103">Een termenset met een SKOS-indeling importeren</span><span class="sxs-lookup"><span data-stu-id="78b53-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="78b53-104">U kunt een termenset met een SKOS-indeling importeren.</span><span class="sxs-lookup"><span data-stu-id="78b53-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="78b53-105">Zie [Naslaginformatie over SharePoint-taxonomie SKOS-indeling](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="78b53-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="78b53-106">We adviseren om importbestanden te beperken tot 20.000 termen of minder.</span><span class="sxs-lookup"><span data-stu-id="78b53-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="78b53-107">Met grotere bestanden kan de benodigde tijd voor validatie en importeren sterk oplopen.</span><span class="sxs-lookup"><span data-stu-id="78b53-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="78b53-108">Vouw in het SharePoint-beheercentrum **Inhoudsservices** uit en klik op **Termenarchief**.</span><span class="sxs-lookup"><span data-stu-id="78b53-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="78b53-109">Selecteer de termengroep waarin u de termenset wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="78b53-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="78b53-110">Klik in de opdrachtbalk op **Termenset importeren**.</span><span class="sxs-lookup"><span data-stu-id="78b53-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="78b53-111">Als u een voorbeeldbestand wilt downloaden om te gebruiken als sjabloon, klikt u op **sample-metadata.ttl** om een voorbeeldbestand te downloaden waarin de SKOS-indeling wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="78b53-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="78b53-112">Maak het importbestand dat de termenset en de termen bevat die u wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="78b53-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="78b53-113">Selecteer onder **Bestandsindeling** de optie **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="78b53-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="78b53-114">Klik op **Bladeren** om te navigeren naar het bestand en het toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="78b53-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="78b53-115">Klik op **Importeren**.</span><span class="sxs-lookup"><span data-stu-id="78b53-115">Click **Import**.</span></span> <span data-ttu-id="78b53-116">Sluit het deelvenster totdat het importeren is voltooid.</span><span class="sxs-lookup"><span data-stu-id="78b53-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="78b53-117">Wanneer het bestand is geïmporteerd wordt er een bericht weergegeven dat het importeren is geslaagd. Vervolgens wordt het termenarchief vernieuwd en kunt u naar de nieuw gemaakte termensets navigeren.</span><span class="sxs-lookup"><span data-stu-id="78b53-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="78b53-118">Zie ook</span><span class="sxs-lookup"><span data-stu-id="78b53-118">See also</span></span>

[<span data-ttu-id="78b53-119">Introductie tot beheerde metagegevens</span><span class="sxs-lookup"><span data-stu-id="78b53-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="78b53-120">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="78b53-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="78b53-121">Termensets importeren (siteniveau)</span><span class="sxs-lookup"><span data-stu-id="78b53-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)