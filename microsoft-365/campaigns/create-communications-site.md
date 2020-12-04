---
title: Een communicatiepagina aanmaken
f1.keywords:
- NOCSH
ms.author: samanro
author: samanro
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Maak een communicatiesite voor uw campagne.
ms.openlocfilehash: 5bd0dd36188f5ec1d550c9baa875e18debd99528
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49569961"
---
# <a name="create-a-communications-site-for-your-campaign"></a><span data-ttu-id="287ea-103">Een communicatiesite voor uw campagne maken</span><span class="sxs-lookup"><span data-stu-id="287ea-103">Create a communications site for your campaign</span></span>

<span data-ttu-id="287ea-104">Een fantastische manier om prioriteiten te communiceren, strategie documenten te delen en toekomstige gebeurtenissen te markeren, is door een communicatiesite te gebruiken in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="287ea-104">A great way to communicate priorities, share strategy documents, and highlight upcoming events is to use a communications site in SharePoint.</span></span> <span data-ttu-id="287ea-105">Communicatiesites zijn voor het delen van acties in de hele campagne. het is de interne campagne site.</span><span class="sxs-lookup"><span data-stu-id="287ea-105">Communications sites are for sharing things broadly across your whole campaign; it's your internal campaign site.</span></span>

## <a name="best-practices"></a><span data-ttu-id="287ea-106">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="287ea-106">Best practices</span></span>

<span data-ttu-id="287ea-107">Neem de volgende elementen op uw communicatiesite op:</span><span class="sxs-lookup"><span data-stu-id="287ea-107">Include the following elements in your Communications site:</span></span>

1. <span data-ttu-id="287ea-108">Het logo en de kleuren van een campagne toevoegen als koptekstafbeelding en thema</span><span class="sxs-lookup"><span data-stu-id="287ea-108">Add your campaign logo and colors as a header image and theme</span></span>
2. <span data-ttu-id="287ea-109">Lever uw strategie, berichten, belangrijke documenten, een adreslijst en veelgestelde vragen in een **webonderdeel held**.</span><span class="sxs-lookup"><span data-stu-id="287ea-109">Lead with your strategy, message, important documents, a directory, and FAQ in a **Hero web part**.</span></span>
3. <span data-ttu-id="287ea-110">Neem een kandidaat-overzicht op naar het team in een **webonderdeel tekst**.</span><span class="sxs-lookup"><span data-stu-id="287ea-110">Include a candidate statement to the team in a **Text web part**.</span></span>
4. <span data-ttu-id="287ea-111">Voeg campagne gebeurtenissen toe aan een **webonderdeel gebeurtenissen** zodat iedereen kan zien wat er is.</span><span class="sxs-lookup"><span data-stu-id="287ea-111">Add campaign events to an **Events web part** so everyone can see what's coming up.</span></span>
5. <span data-ttu-id="287ea-112">Voeg Foto's toe die gebruikers kunnen gebruiken of delen met een **webonderdeel Afbeeldingengalerie**.</span><span class="sxs-lookup"><span data-stu-id="287ea-112">Add photos that people can use or share to an **Image gallery web part**.</span></span>

![Diagram van een SharePoint-communicatie pagina met ruimte voor veelgebruikte elementen die een campagne nodig heeft](../media/m365-democracy-comms-site.png)

## <a name="infographic-create-a-communications-site-infographic"></a><span data-ttu-id="287ea-114">Infographic: een communicatie site maken Infographic</span><span class="sxs-lookup"><span data-stu-id="287ea-114">Infographic: Create a Communications Site infographic</span></span> 
<span data-ttu-id="287ea-115">U kunt de volgende koppelingen voor PowerPoint en PDF downloaden en afdrukken in de tabloid-indeling (ook wel bekend als Ledger, 11 x 17 of a3).</span><span class="sxs-lookup"><span data-stu-id="287ea-115">The following links for PowerPoint and PDF can be downloaded and printed in tabloid format (also known as ledger, 11 x 17, or A3).</span></span>

<span data-ttu-id="287ea-116">[![Afbeelding van de infographic van de communicatiesite](../media/M365-Campaigns-CreateCommunicationSite-358-201.png)](downloads/M365CampaignsCreateCommunicationSite.pdf)</span><span class="sxs-lookup"><span data-stu-id="287ea-116">[![Image for communications site infographic](../media/M365-Campaigns-CreateCommunicationSite-358-201.png)](downloads/M365CampaignsCreateCommunicationSite.pdf)</span></span>

<span data-ttu-id="287ea-117">[PDF-bestand](downloads/M365CampaignsCreateCommunicationSite.pdf)  |  [PowerPoint](downloads/M365CampaignsCreateCommunicationSite.pptx)</span><span class="sxs-lookup"><span data-stu-id="287ea-117">[PDF](downloads/M365CampaignsCreateCommunicationSite.pdf) | [PowerPoint](downloads/M365CampaignsCreateCommunicationSite.pptx)</span></span>


## <a name="set-it-up"></a><span data-ttu-id="287ea-118">Instellen</span><span class="sxs-lookup"><span data-stu-id="287ea-118">Set it up</span></span>

1. <span data-ttu-id="287ea-119">Meld u aan bij https://Office.com.</span><span class="sxs-lookup"><span data-stu-id="287ea-119">Sign in to https://Office.com.</span></span>
2. <span data-ttu-id="287ea-120">Selecteer in de linkerbovenhoek van de pagina het startprogramma voor apps en selecteer vervolgens de tegel **SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="287ea-120">In the top-left corner of the page, select the app launcher icon and then select the **SharePoint** tile.</span></span> <span data-ttu-id="287ea-121">Als u de **SharePoint-** tegel niet ziet, klikt u op de tegel **sites** of **Alles** als SharePoint niet zichtbaar is.</span><span class="sxs-lookup"><span data-stu-id="287ea-121">If you don't see the **SharePoint** tile, click the **Sites** tile or **All** if SharePoint isn't visible.</span></span>
3. <span data-ttu-id="287ea-122">Klik boven aan de SharePoint-startpagina op **+ site maken** en kies de optie **communicatiesite** .</span><span class="sxs-lookup"><span data-stu-id="287ea-122">At the top of the SharePoint home page, click **+ Create site** and choose the **Communication site** option.</span></span>

<span data-ttu-id="287ea-123">Meer informatie [over Communicatiesites](https://support.office.com/article/What-is-a-SharePoint-communication-site-94A33429-E580-45C3-A090-5512A8070732) en het [maken van een communicatiesite in SharePoint Online](https://support.microsoft.com/en-us/office/create-a-communication-site-in-sharepoint-online-7fb44b20-a72f-4d2c-9173-fc8f59ba50eb).</span><span class="sxs-lookup"><span data-stu-id="287ea-123">Learn all [about Communications sites](https://support.office.com/article/What-is-a-SharePoint-communication-site-94A33429-E580-45C3-A090-5512A8070732) and how to [create a communication site in SharePoint Online](https://support.microsoft.com/en-us/office/create-a-communication-site-in-sharepoint-online-7fb44b20-a72f-4d2c-9173-fc8f59ba50eb).</span></span>


## <a name="admin-settings"></a><span data-ttu-id="287ea-124">Beheerdersinstellingen</span><span class="sxs-lookup"><span data-stu-id="287ea-124">Admin settings</span></span>

<span data-ttu-id="287ea-125">Als u de koppeling **+ site maken** niet ziet, is het zelf maken van sites mogelijk niet beschikbaar in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="287ea-125">If you don't see the **+ Create** site link, self-service site creation might not be available in Microsoft 365.</span></span> <span data-ttu-id="287ea-126">Neem contact op met de persoon die Microsoft 365 in uw organisatie beheert als u een team site wilt maken.</span><span class="sxs-lookup"><span data-stu-id="287ea-126">To create a team site, contact the person administering Microsoft 365 in your organization.</span></span> <span data-ttu-id="287ea-127">Als u een Microsoft 365-beheerder bent, raadpleegt u [sites maken in SharePoint Online beheren](https://docs.microsoft.com/sharepoint/manage-site-creation) als u het maken van sites met selfservice voor uw organisatie of het [beheren van sites in het nieuwe SharePoint](https://docs.microsoft.com/sharepoint/manage-sites-in-new-admin-center) online-Beheercentrum wilt inschakelen voor het maken van een site.</span><span class="sxs-lookup"><span data-stu-id="287ea-127">If you're a Microsoft 365 admin, see [Manage site creation in SharePoint Online](https://docs.microsoft.com/sharepoint/manage-site-creation) to enable self-service site creation for your organization or [Manage sites in the new SharePoint admin center](https://docs.microsoft.com/sharepoint/manage-sites-in-new-admin-center) to create a site from the SharePoint Online admin center.</span></span>
  
