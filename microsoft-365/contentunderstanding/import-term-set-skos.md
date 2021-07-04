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
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288513"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="7800c-103">Een termenset met een SKOS-indeling importeren</span><span class="sxs-lookup"><span data-stu-id="7800c-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="7800c-104">U kunt een termenset met een SKOS-indeling importeren.</span><span class="sxs-lookup"><span data-stu-id="7800c-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="7800c-105">Zie [Naslaginformatie over SharePoint-taxonomie SKOS-indeling](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7800c-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="7800c-106">Deze functie vereist een licentie voor [SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="7800c-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="7800c-107">We adviseren om importbestanden te beperken tot 20.000 termen of minder.</span><span class="sxs-lookup"><span data-stu-id="7800c-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="7800c-108">Met grotere bestanden kan de benodigde tijd voor validatie en importeren sterk oplopen.</span><span class="sxs-lookup"><span data-stu-id="7800c-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="7800c-109">Vouw in het SharePoint-beheercentrum **Inhoudsservices** uit en klik op **Termenarchief**.</span><span class="sxs-lookup"><span data-stu-id="7800c-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="7800c-110">Selecteer de termengroep waarin u de termenset wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="7800c-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="7800c-111">Klik in de opdrachtbalk op **Termenset importeren**.</span><span class="sxs-lookup"><span data-stu-id="7800c-111">In the command bar, click **Import term set**.</span></span>

4. <span data-ttu-id="7800c-112">Als u een voorbeeldbestand wilt downloaden om te gebruiken als sjabloon, klikt u op **sample-metadata.ttl** om een voorbeeldbestand te downloaden waarin de SKOS-indeling wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7800c-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>

5. <span data-ttu-id="7800c-113">Maak het importbestand dat de termenset en de termen bevat die u wilt importeren.</span><span class="sxs-lookup"><span data-stu-id="7800c-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6. <span data-ttu-id="7800c-114">Selecteer onder **Bestandsindeling** de optie **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="7800c-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7. <span data-ttu-id="7800c-115">Klik op **Bladeren** om te navigeren naar het bestand en het toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="7800c-115">Click **Browse** and navigate to and add your import file.</span></span>

8. <span data-ttu-id="7800c-116">Klik op **Importeren**.</span><span class="sxs-lookup"><span data-stu-id="7800c-116">Click **Import**.</span></span> <span data-ttu-id="7800c-117">Sluit het deelvenster totdat het importeren is voltooid.</span><span class="sxs-lookup"><span data-stu-id="7800c-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="7800c-118">Wanneer het bestand is geïmporteerd wordt er een bericht weergegeven dat het importeren is geslaagd. Vervolgens wordt het termenarchief vernieuwd en kunt u naar de nieuw gemaakte termensets navigeren.</span><span class="sxs-lookup"><span data-stu-id="7800c-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="7800c-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7800c-119">See also</span></span>

[<span data-ttu-id="7800c-120">Introductie tot beheerde metagegevens</span><span class="sxs-lookup"><span data-stu-id="7800c-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="7800c-121">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="7800c-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="7800c-122">Termensets importeren (siteniveau)</span><span class="sxs-lookup"><span data-stu-id="7800c-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
