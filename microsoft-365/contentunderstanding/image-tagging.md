---
title: Afbeeldingen taggen in SharePoint Syntex
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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over afbeeldingen taggen in SharePoint Syntex
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975863"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="be097-103">Afbeeldingen taggen in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="be097-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="be097-104">(Binnenkort beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="be097-104">(Coming soon)</span></span>

<span data-ttu-id="be097-105">Met afbeeldingen taggen in SharePoint Syntex kunnen gebruikers afbeeldingen vinden door te zoeken op afbeeldingstags en werkstromen te maken op basis van afbeeldingstags.</span><span class="sxs-lookup"><span data-stu-id="be097-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="be097-106">Standaard is het basis taggen van afbeeldingen ingeschakeld voor SharePoint en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="be097-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="be097-107">Afbeeldingen die zijn geüpload naar een van beide locaties, worden automatisch gescand en toepasbare tags worden toegepast, indien beschikbaar, uit een lijst met 37-basistags.</span><span class="sxs-lookup"><span data-stu-id="be097-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="be097-108">Gebruikers kunnen afbeeldingen zoeken via zoeken door de afbeeldingtags te zoeken.</span><span class="sxs-lookup"><span data-stu-id="be097-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="be097-109">Wanneer een gebruiker een afbeelding uploadt, wordt het tagproces automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="be097-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="be097-110">Als een afbeelding wordt bewerkt, wordt het tagproces nogmaals uitgevoerd om de labels bij te werken.</span><span class="sxs-lookup"><span data-stu-id="be097-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="be097-111">Gebruikers met machtigingen voor het afbeeldingsbestand kunnen de tags in het bestandsinformatie paneel of op de pagina met zoekresultaten zien en bewerken.</span><span class="sxs-lookup"><span data-stu-id="be097-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="be097-112">Wanneer een gebruiker de labels van een afbeelding bewerkt, worden er niet langer automatische tags aan de afbeelding toegevoegd, ook niet als deze is bewerkt.</span><span class="sxs-lookup"><span data-stu-id="be097-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="be097-113">Als u taggen uitschakelt, worden afbeeldingen niet meer automatisch getagd.</span><span class="sxs-lookup"><span data-stu-id="be097-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="be097-114">Bestaande tags worden niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="be097-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="be097-115">Door het systeem gegenereerde tags kunnen veranderen bij veranderingen in de afbeelding of de tagging-technologie.</span><span class="sxs-lookup"><span data-stu-id="be097-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="be097-116">Afbeelding taggen configureren</span><span class="sxs-lookup"><span data-stu-id="be097-116">Configure image tagging</span></span>

<span data-ttu-id="be097-117">Na het [instellen van SharePoint Syntex](set-up-content-understanding.md) kunt u taggen van afbeeldingen configureren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="be097-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="be097-118">Taggen van afbeeldingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="be097-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="be097-119">In het Microsoft 365-beheercentrum, klik op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="be097-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="be097-120">Klik onder **Organisatiekennis** op **Meer informatie** over het automatiseren van inhoud.</span><span class="sxs-lookup"><span data-stu-id="be097-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="be097-121">Klik op **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="be097-121">Click **Manage**.</span></span>

4. <span data-ttu-id="be097-122">Klik op het tabblad **Afbeeldingen taggen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="be097-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="be097-123">Geef aan dat **basis-taggen** moet worden toegestaan of schakel tagging **Uit**.</span><span class="sxs-lookup"><span data-stu-id="be097-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="be097-124">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="be097-124">Click **Save**.</span></span>

    ![Schermafbeelding van besturingselement voor afbeeldingen taggen](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
