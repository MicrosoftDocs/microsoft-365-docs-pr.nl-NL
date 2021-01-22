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
description: 'Snel koppelingen maken naar uw e-mailberichten, documenten, apps, SharePoint-sites, externe sites en andere bronnen door aangepaste tegels toe te voegen aan het startpunt voor apps. '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926232"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="aabab-103">Aangepaste tegels toevoegen aan het startprogramma voor apps</span><span class="sxs-lookup"><span data-stu-id="aabab-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="aabab-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="aabab-104">The admin center is changing.</span></span> <span data-ttu-id="aabab-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="aabab-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="aabab-106">In Microsoft 365 hebt u snel en eenvoudig toegang tot uw e-mail, agenda's, documenten en apps met behulp van het start programma voor apps[(meer informatie).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="aabab-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="aabab-107">Dit zijn apps die u krijgt bij Microsoft 365, evenals aangepaste apps die u toevoegt uit [de SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) of [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="aabab-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="aabab-p103">U kunt aan het startprogramma voor apps uw eigen aangepaste tegels toevoegen die verwijzen naar SharePoint-sites, externe sites, oude apps en meer. De aangepaste tegel verschijnt onder **Alle** apps in het startprogramma voor apps, maar u kunt de tegel vastmaken aan de **Start**-apps en uw gebruikers instructies geven dit ook te doen. Hierdoor kunt u eenvoudig sites, apps en resources vinden die relevant zijn bij het uitvoeren van uw taken. In het onderstaande voorbeeld wordt een aangepaste tegel gebruikt met de naam 'Contoso Portal' voor toegang tot de SharePoint-intranetsite van een organisatie.</span><span class="sxs-lookup"><span data-stu-id="aabab-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Start start voor apps](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="aabab-113">Een aangepaste tegel toevoegen aan het startprogramma voor apps</span><span class="sxs-lookup"><span data-stu-id="aabab-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="aabab-114">Meld u aan bij het beheercentrum als globale beheerder, ga naar Instellingen organisatie-instellingen en kies  >  het **tabblad Organisatieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="aabab-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="aabab-115">Kies op **het tabblad Organisatieprofiel** de **tegel Aangepaste startpagina voor apps.**</span><span class="sxs-lookup"><span data-stu-id="aabab-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="aabab-116">Selecteer **Een aangepaste tegel toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aabab-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="aabab-117">Typ in het vak **Tegelnaam** een naam voor de nieuwe tegel.</span><span class="sxs-lookup"><span data-stu-id="aabab-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="aabab-118">Deze naam wordt weergegeven in de tegel.</span><span class="sxs-lookup"><span data-stu-id="aabab-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="aabab-119">Voer een **URL van de website** in voor de tegel.</span><span class="sxs-lookup"><span data-stu-id="aabab-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="aabab-120">Dit is de locatie waar u uw gebruikers naartoe wilt laten gaan wanneer ze de tegel selecteren in het startaar voor apps.</span><span class="sxs-lookup"><span data-stu-id="aabab-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="aabab-121">Gebruik HTTPS in de URL.</span><span class="sxs-lookup"><span data-stu-id="aabab-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="aabab-122">TIP: Als u een tegel voor een SharePoint-site maakt, gaat u naar die site, kopieert u de URL en plakt u deze hier.</span><span class="sxs-lookup"><span data-stu-id="aabab-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="aabab-123">De URL van uw standaardteamsite ziet er zo uit: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="aabab-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="aabab-124">Voer een **URL van de afbeelding voor** de tegel in.</span><span class="sxs-lookup"><span data-stu-id="aabab-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="aabab-125">De afbeelding wordt weergegeven op de pagina Mijn apps en het startprogramma voor apps.</span><span class="sxs-lookup"><span data-stu-id="aabab-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="aabab-126">TIP: De afbeelding moet 60x60 pixels zijn en beschikbaar zijn voor iedereen in uw organisatie, zonder verificatie te vereisen.</span><span class="sxs-lookup"><span data-stu-id="aabab-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="aabab-127">Voer een **Beschrijving** in voor de tegel.</span><span class="sxs-lookup"><span data-stu-id="aabab-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="aabab-128">U ziet dit wanneer u de tegel selecteert op de pagina Mijn apps en **app-details selecteert.**</span><span class="sxs-lookup"><span data-stu-id="aabab-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="aabab-129">Selecteer **Wijzigingen opslaan** om de aangepaste tegel te maken.</span><span class="sxs-lookup"><span data-stu-id="aabab-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="aabab-130">U en uw gebruikers zien nu de aangepaste tegel in het startprogramma voor apps op het tabblad **Alle**.</span><span class="sxs-lookup"><span data-stu-id="aabab-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="aabab-131">De tegel promoveren naar het start start starten van apps</span><span class="sxs-lookup"><span data-stu-id="aabab-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="aabab-132">Selecteer het pictogram voor het startpictogram voor apps en selecteer **alle apps.**</span><span class="sxs-lookup"><span data-stu-id="aabab-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="aabab-133">Zoek de nieuwe tegel voor uw app, selecteer het beletselteken en kies **Vastmaken aan starter.**</span><span class="sxs-lookup"><span data-stu-id="aabab-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="aabab-134">Als u de aangepaste tegel niet ziet die in de vorige stappen is gemaakt, controleer dan of er een Exchange Online-postvak aan u is toegewezen en of u zich ten minste één keer bij uw postvak hebt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="aabab-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="aabab-135">Deze stappen zijn vereist voor aangepaste tegels in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aabab-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="aabab-136">Zowel u als uw gebruikers moeten deze stappen uitvoeren om aangepaste tegels te promoveren van de pagina Mijn apps naar het startprogramma voor apps.</span><span class="sxs-lookup"><span data-stu-id="aabab-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="aabab-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="aabab-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="aabab-138">Ga in het beheercentrum naar het tabblad **Organisatieprofiel**  >  **instellingen**  >   </a> organisatie.</span><span class="sxs-lookup"><span data-stu-id="aabab-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="aabab-139">Selecteer Op de **profielpagina Organisatie,** naast **Aangepaste tegels toevoegen voor** uw organisatie, de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="aabab-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="aabab-140">Werk de **Tegelnaam**, **URL**, **Beschrijving** of **Afbeeldings-URL** voor de aangepaste tegel bij (zie [Een aangepaste tegel toevoegen aan het startprogramma voor apps](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="aabab-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="aabab-141">Selecteer **Bijwerken** \> **sluiten.**</span><span class="sxs-lookup"><span data-stu-id="aabab-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="aabab-142">Als u een aangepaste tegel wilt verwijderen, **selecteert** u de tegel in het venster Aangepaste tegels en **selecteert u Tegel**  >  **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="aabab-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="aabab-143">En nu?</span><span class="sxs-lookup"><span data-stu-id="aabab-143">What's next?</span></span>

<span data-ttu-id="aabab-144">Naast het toevoegen van tegels aan het startvenster voor apps, kunt u ook tegels uit het startvenster voor apps toevoegen aan de navigatiebalk[(meer informatie).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="aabab-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="aabab-145">Zie Het thema [Microsoft 365](../setup/customize-your-organization-theme.md)aanpassen om het uiterlijk van Microsoft 365 aan te passen aan het merk van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aabab-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
