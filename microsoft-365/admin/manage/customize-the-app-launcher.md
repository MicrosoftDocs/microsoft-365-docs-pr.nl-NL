---
title: Aangepaste tegels toevoegen aan het startprogramma voor apps
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Maak snelle koppelingen naar uw e-mail, documenten, apps, SharePoint-sites, externe sites en andere bronnen door aangepaste tegels toe te voegen aan het start startpunt voor apps. '
ms.openlocfilehash: b6ae4deed1566492574e30cf8cb66a750c9858c8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470629"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="51be9-103">Aangepaste tegels toevoegen aan het startprogramma voor apps</span><span class="sxs-lookup"><span data-stu-id="51be9-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="51be9-104">In Microsoft 365 kunt u snel en eenvoudig toegang krijgen tot uw e-mail, agenda's, documenten en apps met behulp van het start start-programma voor apps[(meer informatie).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="51be9-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="51be9-105">Dit zijn apps die u krijgt met Microsoft 365 en aangepaste apps die u toevoegt vanuit de [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) of [Azure AD.](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="51be9-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="51be9-p102">U kunt aan het startprogramma voor apps uw eigen aangepaste tegels toevoegen die verwijzen naar SharePoint-sites, externe sites, oude apps en meer. De aangepaste tegel verschijnt onder **Alle** apps in het startprogramma voor apps, maar u kunt de tegel vastmaken aan de **Start**-apps en uw gebruikers instructies geven dit ook te doen. Hierdoor kunt u eenvoudig sites, apps en resources vinden die relevant zijn bij het uitvoeren van uw taken. In het onderstaande voorbeeld wordt een aangepaste tegel gebruikt met de naam 'Contoso Portal' voor toegang tot de SharePoint-intranetsite van een organisatie.</span><span class="sxs-lookup"><span data-stu-id="51be9-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Start start start-app](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="51be9-111">Een aangepaste tegel toevoegen aan het startprogramma voor apps</span><span class="sxs-lookup"><span data-stu-id="51be9-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="51be9-112">Meld u als globale beheerder aan bij het beheercentrum, ga naar **Instellingen**  >  **organisatieinstellingen** en kies het **tabblad Organisatieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="51be9-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="51be9-113">Kies op **het tabblad** Organisatieprofiel de optie **Aangepaste startpagina voor apps.**</span><span class="sxs-lookup"><span data-stu-id="51be9-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="51be9-114">Selecteer **Een aangepaste tegel toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="51be9-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="51be9-115">Typ in het vak **Tegelnaam** een naam voor de nieuwe tegel.</span><span class="sxs-lookup"><span data-stu-id="51be9-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="51be9-116">Deze naam wordt weergegeven in de tegel.</span><span class="sxs-lookup"><span data-stu-id="51be9-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="51be9-117">Voer een **URL van de website voor** de tegel in.</span><span class="sxs-lookup"><span data-stu-id="51be9-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="51be9-118">Dit is de locatie waar uw gebruikers naartoe moeten gaan wanneer ze de tegel in het start.</span><span class="sxs-lookup"><span data-stu-id="51be9-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="51be9-119">Gebruik HTTPS in de URL.</span><span class="sxs-lookup"><span data-stu-id="51be9-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="51be9-120">TIP: Als u een tegel voor een SharePoint-site maakt, gaat u naar die site, kopieert u de URL en plakt u deze hier.</span><span class="sxs-lookup"><span data-stu-id="51be9-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="51be9-121">De URL van uw standaardteamsite ziet er als volgende uit: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="51be9-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="51be9-122">Voer een **URL in van de afbeelding** voor de tegel.</span><span class="sxs-lookup"><span data-stu-id="51be9-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="51be9-123">De afbeelding wordt weergegeven op de pagina Mijn apps en het startprogramma voor apps.</span><span class="sxs-lookup"><span data-stu-id="51be9-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="51be9-124">TIP: De afbeelding moet 60x60 pixels zijn en beschikbaar zijn voor iedereen in uw organisatie zonder verificatie.</span><span class="sxs-lookup"><span data-stu-id="51be9-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="51be9-125">Voer een **Beschrijving** in voor de tegel.</span><span class="sxs-lookup"><span data-stu-id="51be9-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="51be9-126">U ziet dit wanneer u de tegel op de pagina Mijn apps selecteert en **App-details selecteert.**</span><span class="sxs-lookup"><span data-stu-id="51be9-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="51be9-127">Selecteer **Wijzigingen opslaan om** de aangepaste tegel te maken.</span><span class="sxs-lookup"><span data-stu-id="51be9-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="51be9-128">U en uw gebruikers zien nu de aangepaste tegel in het startprogramma voor apps op het tabblad **Alle**.</span><span class="sxs-lookup"><span data-stu-id="51be9-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="51be9-129">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="51be9-129">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="51be9-130">Ga in het beheercentrum naar het tabblad **Instellingen**  >  **organisatieinstellingen**  >  **organisatieprofiel.** </a></span><span class="sxs-lookup"><span data-stu-id="51be9-130">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="51be9-131">Selecteer op **de profielpagina** Organisatie naast Aangepaste tegels **voor uw organisatie** toevoegen de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="51be9-131">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="51be9-132">Werk de **Tegelnaam**, **URL**, **Beschrijving** of **Afbeeldings-URL** voor de aangepaste tegel bij (zie [Een aangepaste tegel toevoegen aan het startprogramma voor apps](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="51be9-132">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="51be9-133">Selecteer **Bijwerken** \> **sluiten.**</span><span class="sxs-lookup"><span data-stu-id="51be9-133">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="51be9-134">Als u een aangepaste tegel wilt verwijderen, **selecteert** u in het venster Aangepaste tegels de tegel en **selecteert u Tegel**  >  **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="51be9-134">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="51be9-135">En nu?</span><span class="sxs-lookup"><span data-stu-id="51be9-135">What's next?</span></span>

<span data-ttu-id="51be9-136">Naast het toevoegen van tegels aan het startbalk voor apps, kunt u ook tegels voor het startvenster voor apps toevoegen aan de navigatiebalk[(meer informatie).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="51be9-136">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="51be9-137">Zie Het [Microsoft 365-thema](../setup/customize-your-organization-theme.md)aanpassen om het uiterlijk van Microsoft 365 aan te passen aan het merk van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="51be9-137">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
