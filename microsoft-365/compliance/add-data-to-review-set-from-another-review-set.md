---
title: Gegevens uit de ene revisieset toevoegen aan een andere revisieset
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
description: Lees hoe u documenten uit de ene revisieset selecteert en er afzonderlijk mee kunt werken in een andere set in Advanced eDiscovery geval.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161525"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="4b1a8-103">Gegevens toevoegen aan een revisieset uit een andere revisieset</span><span class="sxs-lookup"><span data-stu-id="4b1a8-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="4b1a8-104">In sommige gevallen kan het nodig zijn om documenten uit de ene revisieset te selecteren en er afzonderlijk mee te werken in een andere revisieset.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="4b1a8-105">Dit is vooral handig als u inhoud hebt weggeruimd in een revisieset en analyses wilt uitvoeren op de subset met gegevens.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="4b1a8-106">Volg de werkstroom in dit artikel om inhoud van de ene revisieset toe te voegen aan een andere.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="4b1a8-107">Een revisieset maken</span><span class="sxs-lookup"><span data-stu-id="4b1a8-107">Create a review set</span></span>

<span data-ttu-id="4b1a8-108">Voordat u begint, moet u een revisieset maken om de gegevens aan toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="4b1a8-109">Er kan een nieuwe revisieset worden toegevoegd op het tabblad **Revisiesets** van de zaak.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="4b1a8-110">Zie Een [revisieset maken voor meer informatie.](managing-review-sets.md#create-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="4b1a8-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="4b1a8-111">Stap 1: Inhoud identificeren die u wilt toevoegen aan een andere revisieset</span><span class="sxs-lookup"><span data-stu-id="4b1a8-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="4b1a8-112">U kunt inhoud uit de ene revisieset toevoegen aan een andere door specifieke documenten in de bronbeoordelingsset te selecteren of door alle items te selecteren die worden geretourneerd door de query Revisieset.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="4b1a8-113">Als u geselecteerde items toevoegt, selecteert u de items, **selecteert** u Actie en selecteert u **Toevoegen aan een andere revisieset.**</span><span class="sxs-lookup"><span data-stu-id="4b1a8-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Toevoegen aan een andere revisieset in het menu Actie](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="4b1a8-115">Stap 2: Opties opgeven voor het toevoegen aan een andere revisieset</span><span class="sxs-lookup"><span data-stu-id="4b1a8-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="4b1a8-116">Kies op de flyoutpagina Opties voor een andere **revisieset** toevoegen de revisieset aan wie u de items wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="4b1a8-117">Kies of u Alle **zoekresultaten of** Geselecteerde items **wilt toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="4b1a8-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="4b1a8-118">**Aanvullende informatie** bevat opties voor het opnemen van alle metagegevens  van de items en het opnemen van de tags (door het selectievakje Etiketten in te stellen) uit de broncontroleset wanneer de documenten worden toegevoegd aan de nieuwe revisieset.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Opties voor het toevoegen van gegevens aan een andere revisieset](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="4b1a8-120">Nadat u op **Ok hebt geklikt,** wordt er een nieuwe taak (met de naam **Gegevens** toevoegen aan een andere revisieset) gemaakt om de inhoud toe te voegen aan een andere revisieset.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="4b1a8-121">U kunt naar het tabblad **Taken** gaan en de voortgang van deze taak controleren.</span><span class="sxs-lookup"><span data-stu-id="4b1a8-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="4b1a8-122">Zie Taken [beheren voor meer informatie.](managing-jobs-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="4b1a8-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
