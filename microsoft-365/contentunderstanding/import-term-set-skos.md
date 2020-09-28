---
title: Een termenset importeren met een op SKOS gebaseerde indeling
description: Meer informatie over het importeren van een termenset met een op SKOS gebaseerde indeling
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295893"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="4f2a8-103">Een termenset importeren met een op SKOS gebaseerde indeling</span><span class="sxs-lookup"><span data-stu-id="4f2a8-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="4f2a8-104">U kunt een termenset importeren met een op SKOS gebaseerde indeling.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="4f2a8-105">Zie voor meer informatie over de indeling naslaginformatie voor het maken van een [SharePoint-taxonomie skos](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a8-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="4f2a8-106">U wordt aangeraden uw importbestanden te houden naar minder dan 20.000 termen.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="4f2a8-107">Grotere bestanden kunnen de tijd voor validatie en import verlengen.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="4f2a8-108">Vouw in het SharePoint-Beheercentrum **inhouds Services**uit en klik op **termenarchief**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="4f2a8-109">Selecteer de termen groep waarin u de termenset wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="4f2a8-110">Klik op de opdrachtbalk op **termenset importeren**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="4f2a8-111">Als u een voorbeeld van een bestand wilt downloaden dat u als sjabloon wilt gebruiken, klikt u op **sample-metadata. TTL** om een voorbeeldbestand te downloaden dat gebruikmaakt van de op skos gebaseerde indeling.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="4f2a8-112">Maak het importbestand dat de termensets bevat & termen die u wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="4f2a8-113">Selecteer onder **bestandsindeling**de optie **SKOS (\*. TTL)**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="4f2a8-114">Klik op **Bladeren** en ga naar uw importbestand toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="4f2a8-115">Klik op **importeren**.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-115">Click **Import**.</span></span> <span data-ttu-id="4f2a8-116">Sluit het deelvenster niet totdat het importeren is voltooid.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="4f2a8-117">Bij het importeren van het bestand wordt een succes bericht weergegeven en wordt het termenarchief vernieuwd en kunt u naar de nieuwe termensets navigeren.</span><span class="sxs-lookup"><span data-stu-id="4f2a8-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f2a8-118">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4f2a8-118">See also</span></span>

[<span data-ttu-id="4f2a8-119">Inleiding in beheerde metagegevens</span><span class="sxs-lookup"><span data-stu-id="4f2a8-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="4f2a8-120">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="4f2a8-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="4f2a8-121">Termensets importeren (siteniveau)</span><span class="sxs-lookup"><span data-stu-id="4f2a8-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)