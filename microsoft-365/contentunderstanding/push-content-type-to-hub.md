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
localization_priority: Priority
ms.openlocfilehash: 03e1be51b35447376be5adfc2f2cd3c944cf89fa
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321335"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="58fe3-103">Inhoudstypen naar een hub pushen</span><span class="sxs-lookup"><span data-stu-id="58fe3-103">Push content types to a hub</span></span>

<span data-ttu-id="58fe3-104">Als u belangrijke inhoudstypen op consistente wijze beschikbaar wilt maken voor SharePoint-bibliotheken en -lijsten, kunt u deze naar de gewenste hubs pushen.</span><span class="sxs-lookup"><span data-stu-id="58fe3-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="58fe3-105">Hiermee worden ze automatisch toegevoegd aan nieuwe lijsten en bibliotheken die zijn gemaakt op de sites die zijn gekoppeld aan de hub, en op nieuwe sites die worden toegevoegd aan de hub.</span><span class="sxs-lookup"><span data-stu-id="58fe3-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="58fe3-106">Als u deze functie wilt gebruiken, moeten de inhoudstypen die worden gepusht al zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="58fe3-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="58fe3-107">Inhoudstypen naar hubs pushen</span><span class="sxs-lookup"><span data-stu-id="58fe3-107">To push content types to hubs</span></span>

1. <span data-ttu-id="58fe3-108">Vouw in het SharePoint-beheercentrum **Inhoudsservices** uit en klik op **Inhoudstypegalerie**.</span><span class="sxs-lookup"><span data-stu-id="58fe3-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="58fe3-109">Klik op het inhoudstype dat u naar hubs wilt pushen.</span><span class="sxs-lookup"><span data-stu-id="58fe3-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="58fe3-110">Klik op **Bewerken** op de opdrachtbalk.</span><span class="sxs-lookup"><span data-stu-id="58fe3-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="58fe3-111">Klik op **Hubsites kiezen**.</span><span class="sxs-lookup"><span data-stu-id="58fe3-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="58fe3-112">Selecteer de gewenste hubsites en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="58fe3-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="58fe3-113">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="58fe3-113">Click **Save**.</span></span>

<span data-ttu-id="58fe3-114">Wanneer u de eerste keer een inhoudstype naar een bestaande hub en de bijbehorende sites pusht, kan het wel een uur duren totdat de instellingen in de site zijn bijgewerkt nadat u de hub of gekoppelde sites bezoekt.</span><span class="sxs-lookup"><span data-stu-id="58fe3-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="58fe3-115">Bij nieuwe koppelingen met de hub duurt dit minder lang en zijn de instellingen na een paar minuten gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="58fe3-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="58fe3-116">Zodra dit is geconfigureerd is het inhoudstype met deze instellingen na een paar minuten beschikbaar op elke nieuwe aan de hub gekoppelde site.</span><span class="sxs-lookup"><span data-stu-id="58fe3-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="58fe3-117">Wanneer het inhoudstype beschikbaar is, wordt het automatisch binnen enkele minuten toegevoegd aan elke nieuwe lijst of bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="58fe3-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="58fe3-118">Een gepusht inhoudstype wordt alleen toegevoegd aan een documentbibliotheek als het direct of indirect is afgeleid van het inhoudstype van het document. Een inhoudstype wordt alleen toegevoegd aan een lijst als het niet direct of indirect is afgeleid van het inhoudstype van het document.</span><span class="sxs-lookup"><span data-stu-id="58fe3-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="58fe3-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="58fe3-119">See also</span></span>



  






