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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Maak snelle koppelingen naar uw e-mail, documenten, apps, SharePoint-sites, externe sites en andere bronnen door aangepaste tegels toe te voegen aan het startprogramma voor apps. '
ms.openlocfilehash: 44a8af104f6f39bd6b095a08f8ad9b2750d86d11
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053774"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="9e11c-103">Aangepaste tegels toevoegen aan het startprogramma voor apps</span><span class="sxs-lookup"><span data-stu-id="9e11c-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="9e11c-104">In Microsoft 365 u snel en eenvoudig bij uw e-mail, agenda's, documenten en apps komen via het startprogramma voor apps[(meer informatie).](https://support.microsoft.com/en-us/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="9e11c-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/en-us/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="9e11c-105">Dit zijn apps die u krijgt met Microsoft 365 en aangepaste apps die u toevoegt vanuit de [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) of [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="9e11c-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="9e11c-p102">U kunt aan het startprogramma voor apps uw eigen aangepaste tegels toevoegen die verwijzen naar SharePoint-sites, externe sites, oude apps en meer. De aangepaste tegel verschijnt onder **Alle** apps in het startprogramma voor apps, maar u kunt de tegel vastmaken aan de **Start**-apps en uw gebruikers instructies geven dit ook te doen. Hierdoor kunt u eenvoudig sites, apps en resources vinden die relevant zijn bij het uitvoeren van uw taken. In het onderstaande voorbeeld wordt een aangepaste tegel gebruikt met de naam 'Contoso Portal' voor toegang tot de SharePoint-intranetsite van een organisatie.</span><span class="sxs-lookup"><span data-stu-id="9e11c-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Startprogramma voor apps](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="9e11c-111">Een aangepaste tegel toevoegen aan het startprogramma voor apps</span><span class="sxs-lookup"><span data-stu-id="9e11c-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="9e11c-112">Ga in het beheercentrum naar de **instellingen** > **instellingen** en kies het tabblad **Organisatieprofiel.**</span><span class="sxs-lookup"><span data-stu-id="9e11c-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="9e11c-113">Kies op het tabblad **Organizenprofiel** de **optie Aangepaste startprogrammategels voor apps**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="9e11c-114">Selecteer **Een aangepaste tegel toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="9e11c-115">Typ in het vak **Tegelnaam** een naam voor de nieuwe tegel.</span><span class="sxs-lookup"><span data-stu-id="9e11c-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="9e11c-116">Deze naam wordt weergegeven in de tegel.</span><span class="sxs-lookup"><span data-stu-id="9e11c-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="9e11c-117">Voer een **URL van de website** voor de tegel in.</span><span class="sxs-lookup"><span data-stu-id="9e11c-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="9e11c-118">Dit is de locatie waar u wilt dat uw gebruikers naartoe gaan wanneer ze de tegel op het startprogramma voor apps selecteren.</span><span class="sxs-lookup"><span data-stu-id="9e11c-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="9e11c-119">Gebruik HTTPS in de URL.</span><span class="sxs-lookup"><span data-stu-id="9e11c-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="9e11c-120">TIP: Als u een tegel maakt voor een SharePoint-site, navigeert u naar die site, kopieert u de URL en plakt u deze hier.</span><span class="sxs-lookup"><span data-stu-id="9e11c-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="9e11c-121">De URL van uw standaardteamsite ziet er als volgt uit:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="9e11c-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="9e11c-122">Voer een **URL van de afbeelding** voor de tegel in.</span><span class="sxs-lookup"><span data-stu-id="9e11c-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="9e11c-123">De afbeelding wordt weergegeven op de pagina Mijn apps en het startprogramma voor apps.</span><span class="sxs-lookup"><span data-stu-id="9e11c-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="9e11c-124">TIP: De afbeelding moet 60x60 pixels zijn en beschikbaar zijn voor iedereen in uw organisatie zonder verificatie.</span><span class="sxs-lookup"><span data-stu-id="9e11c-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="9e11c-125">Voer een **Beschrijving** in voor de tegel.</span><span class="sxs-lookup"><span data-stu-id="9e11c-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="9e11c-126">U ziet dit wanneer u de tegel selecteert op de pagina Mijn apps en **app-details**selecteert.</span><span class="sxs-lookup"><span data-stu-id="9e11c-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="9e11c-127">Selecteer **Wijzigingen opslaan** om de aangepaste tegel te maken.</span><span class="sxs-lookup"><span data-stu-id="9e11c-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="9e11c-128">U en uw gebruikers zien nu de aangepaste tegel in het startprogramma voor apps op het tabblad **Alle**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="9e11c-129">De tegel promoten in App Launcher</span><span class="sxs-lookup"><span data-stu-id="9e11c-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="9e11c-130">Selecteer het pictogram startprogramma voor apps en selecteer het **pictogram Alle apps**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="9e11c-131">Zoek de nieuwe tegel voor uw app, selecteer de ellips en kies **Vastmaken aan launcher**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="9e11c-132">Als u de aangepaste tegel niet ziet die in de vorige stappen is gemaakt, controleer dan of er een Exchange Online-postvak aan u is toegewezen en of u zich ten minste één keer bij uw postvak hebt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="9e11c-132">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="9e11c-133">Deze stappen zijn vereist voor aangepaste tegels in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e11c-133">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9e11c-134">Zowel u als uw gebruikers moeten deze stappen uitvoeren om aangepaste tegels te promoveren van de pagina Mijn apps naar het startprogramma voor apps.</span><span class="sxs-lookup"><span data-stu-id="9e11c-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="9e11c-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="9e11c-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="9e11c-136">Ga in het beheercentrum naar het profieltabblad **Instellingen** > **instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">organisatie.</a></span><span class="sxs-lookup"><span data-stu-id="9e11c-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="9e11c-137">Selecteer op de pagina **Organisatieprofiel** naast **Aangepaste tegels toevoegen voor uw organisatie**de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="9e11c-138">Werk de **Tegelnaam**, **URL**, **Beschrijving** of **Afbeeldings-URL** voor de aangepaste tegel bij (zie [Een aangepaste tegel toevoegen aan het startprogramma voor apps](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="9e11c-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="9e11c-139">Selecteer **Sluiten bijwerken** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="9e11c-140">Als u een aangepaste tegel wilt verwijderen, selecteert u in het venster **Aangepaste tegels** de tegel en selecteert u Tegel > **Verwijderen** **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="9e11c-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="9e11c-141">En nu?</span><span class="sxs-lookup"><span data-stu-id="9e11c-141">What's next?</span></span>

<span data-ttu-id="9e11c-142">Naast het toevoegen van tegels aan het startprogramma voor apps, u app launcher-tegels toevoegen aan de navigatiebalk[(meer informatie).](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="9e11c-142">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="9e11c-143">Zie [Het Microsoft 365-thema aanpassen](../setup/customize-your-organization-theme.md)om het uiterlijk van Microsoft 365 aan te passen aan het merk van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9e11c-143">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

