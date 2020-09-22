---
title: ServiceNow tickets maken en bijhouden in het Microsoft 365-Beveiligingscentrum
description: Informatie over het maken en bijhouden van tickets in ServiceNow vanuit het Microsoft 365 Beveiligingscentrum.
keywords: beveiliging, Microsoft 365, M365, Secure Score, beveiliging centrum, ServiceNow, tickets, taken
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: f57fc83f9102e5eeea61deaaadc17203bad030ac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195533"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="8e85e-104">ServiceNow tickets maken en bijhouden in het Microsoft 365-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8e85e-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8e85e-105">Het [Microsoft 365 Beveiligingscentrum](overview-security-center.md) is verbeterd met de mogelijkheid voor het zelf maken en bijhouden van tickets in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8e85e-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="8e85e-106">Meer informatie over ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8e85e-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="8e85e-107">In het Beveiligingscentrum kunnen beveiligingsbeheerders rechtstreeks een actie ondernemen voor het oplossen van beveiligings punten voor [Microsoft](microsoft-secure-score.md) voor ServiceNow en een ticket maken.</span><span class="sxs-lookup"><span data-stu-id="8e85e-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="8e85e-108">Beide ticket beheer en het wijzigen van beheer tickets kunnen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8e85e-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="8e85e-109">Spoor tickets in de startpagina van het Beveiligingscentrum en in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8e85e-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="8e85e-110">**Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing**</span><span class="sxs-lookup"><span data-stu-id="8e85e-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="8e85e-111">**ServiceNow tickets beheren in het compliance Center** (binnenkort beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="8e85e-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="8e85e-112">Microsoft 365-Beveiligingscentrum verbinden met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8e85e-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="8e85e-113">Ga naar de startpagina van het Microsoft 365-Beveiligingscentrum om de ServiceNow-verbindings kaart weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8e85e-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Gebruikt u ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="8e85e-115">Selecteer "verbinding maken met ServiceNow" om naar de instellingenpagina van ServiceNow te gaan.</span><span class="sxs-lookup"><span data-stu-id="8e85e-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="8e85e-116">Volg de instructies om de Microsoft 365 connector-app te machtigen.</span><span class="sxs-lookup"><span data-stu-id="8e85e-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="8e85e-117">Voordat u de verbinding tussen Microsoft 365 Beveiligingscentrum en ServiceNow machtigt, moet u ervoor zorgen dat u de aanmeldingsgegevens van gebruikers en wachtwoorden van de gebruikers die u in de installatiestappen hebt gemaakt, gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8e85e-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="8e85e-118">Gebruik geen persoonlijke referenties.</span><span class="sxs-lookup"><span data-stu-id="8e85e-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="8e85e-119">Nadat u de instructies hebt gevolgd en de verbinding hebt geautoriseerd, bekijkt u de status van de verbinding op de verbinding van het Microsoft 365-Beveiligingscentrum en in de ServiceNow Microsoft 365 ticketing connector app Experience.</span><span class="sxs-lookup"><span data-stu-id="8e85e-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="8e85e-120">U bent nu klaar om taken te maken.</span><span class="sxs-lookup"><span data-stu-id="8e85e-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="8e85e-121">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="8e85e-121">Troubleshooting</span></span>

<span data-ttu-id="8e85e-122">Veelvoorkomende fouten bij het maken van een verbindingsprocedure en de manier waarop u deze problemen kunt oplossen, vindt u in de [sectie Probleemoplossing](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="8e85e-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="8e85e-123">Een taak maken en delen in ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8e85e-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="8e85e-124">Wanneer de integratie is geconfigureerd, maakt u ServiceNow taken op basis van specifieke acties van [Microsoft Secure scores](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="8e85e-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="8e85e-125">Ga naar het Microsoft 365-Beveiligingscentrum en selecteer **delen**.</span><span class="sxs-lookup"><span data-stu-id="8e85e-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="8e85e-126">Een van de opties voor vervolgkeuzelijsten is ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8e85e-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="8e85e-127">Er wordt een taak gegenereerd waarbij u de prioriteit kunt instellen en de naam, de beschrijving of de vervaldatum kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8e85e-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="8e85e-128">Wanneer alle verplichte velden zijn ingevuld, verzendt u de taak naar ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8e85e-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="8e85e-129">De taak wordt weergegeven in ServiceNow als een aanvraag voor het wijzigen van de beveiligings-en configuratie van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e85e-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="8e85e-130">Tickets bijhouden</span><span class="sxs-lookup"><span data-stu-id="8e85e-130">Track tickets</span></span>

<span data-ttu-id="8e85e-131">Wanneer ServiceNow-en ticket beheer tickets zijn gemaakt, worden deze weergegeven op kaarten op de startpagina van het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8e85e-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="8e85e-132">Met deze kaarten kunt u een ticket maken, alle tickets weergeven of de ServiceNow-configuratie beheren.</span><span class="sxs-lookup"><span data-stu-id="8e85e-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow tickets voor wijzigingsbeheer](../../media/change-management-375.png)  ![ServiceNow-tickets voor incidentbeheer](../../media/incident-management-375.png)

<span data-ttu-id="8e85e-135">Als u uw ServiceNow-integratie wilt in het Microsoft 365-Beveiligingscentrum wilt inrichten of beheren, selecteert u **ServiceNow-configuratie beheren** op een van de kaarten.</span><span class="sxs-lookup"><span data-stu-id="8e85e-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="8e85e-136">Vervolgens verwijdert u de huidige ServiceNow-verbinding en wijzigt u de namen van ticket Staten.</span><span class="sxs-lookup"><span data-stu-id="8e85e-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="8e85e-137">Met ServiceNow-tickets die zichtbaar zijn in het Microsoft 365-Beveiligingscentrum, worden uw taken weergegeven op een plaats waar ze op uw andere beveiligings dashboarditems kunnen worden bijgehouden en afgehandeld.</span><span class="sxs-lookup"><span data-stu-id="8e85e-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="8e85e-138">Resources</span><span class="sxs-lookup"><span data-stu-id="8e85e-138">Resources</span></span>

- [<span data-ttu-id="8e85e-139">Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing</span><span class="sxs-lookup"><span data-stu-id="8e85e-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="8e85e-140">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="8e85e-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)
