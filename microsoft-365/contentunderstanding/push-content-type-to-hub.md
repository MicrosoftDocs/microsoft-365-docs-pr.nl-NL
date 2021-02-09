---
title: Inhoudstypen naar een hub pushen
description: Informatie over het pushen van inhoudstypen naar een hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144969"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="cda32-103">Inhoudstypen naar een hub pushen</span><span class="sxs-lookup"><span data-stu-id="cda32-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="cda32-104">Als u belangrijke inhoudstypen op consistente wijze beschikbaar wilt maken voor SharePoint-bibliotheken en -lijsten, kunt u deze naar de gewenste hubs pushen.</span><span class="sxs-lookup"><span data-stu-id="cda32-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="cda32-105">Hiermee worden ze automatisch toegevoegd aan nieuwe lijsten en bibliotheken die zijn gemaakt op de sites die zijn gekoppeld aan de hub, en op nieuwe sites die worden toegevoegd aan de hub.</span><span class="sxs-lookup"><span data-stu-id="cda32-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span> <span data-ttu-id="cda32-106">Deze functie vereist een licentie voor [SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="cda32-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="cda32-107">Als u deze functie wilt gebruiken, moeten de inhoudstypen die worden gepusht al zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="cda32-107">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="cda32-108">Inhoudstypen naar hubs pushen</span><span class="sxs-lookup"><span data-stu-id="cda32-108">To push content types to hubs</span></span>

1. <span data-ttu-id="cda32-109">Vouw in het SharePoint-beheercentrum **Inhoudsservices** uit en selecteer **Inhoudstypegalerie**.</span><span class="sxs-lookup"><span data-stu-id="cda32-109">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="cda32-110">Klik op het inhoudstype dat u naar hubs wilt pushen.</span><span class="sxs-lookup"><span data-stu-id="cda32-110">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="cda32-111">Selecteer **Bewerken** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="cda32-111">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="cda32-112">Selecteer **Hubsites kiezen**.</span><span class="sxs-lookup"><span data-stu-id="cda32-112">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="cda32-113">Selecteer de hubsites die u wilt gebruiken en kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="cda32-113">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="cda32-114">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cda32-114">Choose **Save**.</span></span>

<span data-ttu-id="cda32-115">Wanneer u de eerste keer een inhoudstype naar een bestaande hub en de bijbehorende sites pusht, kan het wel een uur duren totdat de instellingen in de site zijn bijgewerkt nadat u de hub of gekoppelde sites bezoekt.</span><span class="sxs-lookup"><span data-stu-id="cda32-115">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="cda32-116">Bij nieuwe koppelingen met de hub duurt dit minder lang en zijn de instellingen na een paar minuten gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cda32-116">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="cda32-117">Nadat de instellingen zijn bijgewerkt, is het inhoudstype met deze instellingen na een paar minuten beschikbaar op elke nieuwe aan de hub gekoppelde site.</span><span class="sxs-lookup"><span data-stu-id="cda32-117">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="cda32-118">Vervolgens wordt het automatisch binnen enkele minuten toegevoegd aan elke nieuwe lijst of bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="cda32-118">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="cda32-119">Een gepusht inhoudstype wordt alleen toegevoegd aan een documentbibliotheek als het direct of indirect is afgeleid van het inhoudstype van het document. Een inhoudstype wordt alleen toegevoegd aan een lijst als het niet direct of indirect is afgeleid van het inhoudstype van het document.</span><span class="sxs-lookup"><span data-stu-id="cda32-119">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="cda32-120">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cda32-120">See also</span></span>
