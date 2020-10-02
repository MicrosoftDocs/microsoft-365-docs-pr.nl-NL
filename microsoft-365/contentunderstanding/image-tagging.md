---
title: Afbeeldingen taggen in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Meer informatie over afbeeldingen taggen in SharePoint Syntex
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321251"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="af88b-103">Afbeeldingen taggen in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="af88b-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="af88b-104">Met afbeeldingen taggen in SharePoint Syntex kunnen gebruikers afbeeldingen vinden door te zoeken op afbeeldingstags en werkstromen te maken op basis van afbeeldingstags.</span><span class="sxs-lookup"><span data-stu-id="af88b-104">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="af88b-105">Standaard is het basis taggen van afbeeldingen ingeschakeld voor SharePoint en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="af88b-105">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="af88b-106">Afbeeldingen die zijn geüpload naar een van beide locaties, worden automatisch gescand en toepasbare tags worden toegepast, indien beschikbaar, uit een lijst met 37-basistags.</span><span class="sxs-lookup"><span data-stu-id="af88b-106">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="af88b-107">Gebruikers kunnen afbeeldingen zoeken via zoeken door de afbeeldingtags te zoeken.</span><span class="sxs-lookup"><span data-stu-id="af88b-107">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="af88b-108">Wanneer een gebruiker een afbeelding uploadt, wordt het tagproces automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="af88b-108">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="af88b-109">Als een afbeelding wordt bewerkt, wordt het tagproces nogmaals uitgevoerd om de labels bij te werken.</span><span class="sxs-lookup"><span data-stu-id="af88b-109">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="af88b-110">Gebruikers met machtigingen voor het afbeeldingsbestand kunnen de tags in het bestandsinformatie paneel of op de pagina met zoekresultaten zien en bewerken.</span><span class="sxs-lookup"><span data-stu-id="af88b-110">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="af88b-111">Wanneer een gebruiker de labels van een afbeelding bewerkt, worden er niet langer automatische tags aan de afbeelding toegevoegd, ook niet als deze is bewerkt.</span><span class="sxs-lookup"><span data-stu-id="af88b-111">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="af88b-112">Als u taggen uitschakelt, worden afbeeldingen niet meer automatisch getagd.</span><span class="sxs-lookup"><span data-stu-id="af88b-112">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="af88b-113">Bestaande tags worden niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af88b-113">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="af88b-114">Door het systeem gegenereerde tags kunnen veranderen bij veranderingen in de afbeelding of de tagging-technologie.</span><span class="sxs-lookup"><span data-stu-id="af88b-114">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="af88b-115">Afbeelding taggen configureren</span><span class="sxs-lookup"><span data-stu-id="af88b-115">Configure image tagging</span></span>

<span data-ttu-id="af88b-116">Na het [instellen van SharePoint Syntex](set-up-content-understanding.md) kunt u taggen van afbeeldingen configureren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="af88b-116">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="af88b-117">Taggen van afbeeldingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="af88b-117">To turn image tagging on or off</span></span>

1. <span data-ttu-id="af88b-118">In het Microsoft 365-beheercentrum, klik op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="af88b-118">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="af88b-119">Klik onder **Organisatiekennis** op **Meer informatie** over het automatiseren van inhoud.</span><span class="sxs-lookup"><span data-stu-id="af88b-119">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="af88b-120">Klik op **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="af88b-120">Click **Manage**.</span></span>

4. <span data-ttu-id="af88b-121">Klik op het tabblad **Afbeeldingen taggen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="af88b-121">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="af88b-122">Geef aan dat **basis-taggen** moet worden toegestaan of schakel tagging **Uit**.</span><span class="sxs-lookup"><span data-stu-id="af88b-122">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="af88b-123">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="af88b-123">Click **Save**.</span></span>

    ![Schermafbeelding van besturingselement voor afbeeldingen taggen](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
