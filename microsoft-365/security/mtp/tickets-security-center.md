---
title: ServiceNow-tickets maken en bijhouden in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het maken en bijhouden van tickets in ServiceNow vanuit microsoft 365-beveiligingscentrum.
keywords: beveiliging, Microsoft 365, M365, secure score, security center, ServiceNow, tickets, taken
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
ms.openlocfilehash: 16ee37b1c7bf33c902db35af2d29744f42830ea7
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094832"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="22332-104">ServiceNow-tickets maken en bijhouden in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="22332-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="22332-105">Het [Microsoft 365-beveiligingscentrum](overview-security-center.md) is verbeterd met de mogelijkheid om in ServiceNow native tickets te maken en bij te houden.</span><span class="sxs-lookup"><span data-stu-id="22332-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="22332-106">Meer informatie over ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22332-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="22332-107">In het beveiligingscentrum kunnen beveiligingsbeheerders een [microsoft secure score-verbeteringsactie](microsoft-secure-score.md) rechtstreeks naar ServiceNow verzenden en een ticket maken.</span><span class="sxs-lookup"><span data-stu-id="22332-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="22332-108">Zowel incident management en change management tickets kunnen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="22332-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="22332-109">Ze kunnen vervolgens worden gevolgd op de startpagina van het beveiligingscentrum en ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="22332-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="22332-110">**Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing**</span><span class="sxs-lookup"><span data-stu-id="22332-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="22332-111">**ServiceNow-tickets beheren in het compliance center** (binnenkort beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="22332-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="22332-112">Microsoft 365-beveiligingscentrum verbinden met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22332-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="22332-113">Navigeer naar de startpagina van het Microsoft 365-beveiligingscentrum om de ServiceNow-verbindingskaart te bekijken.</span><span class="sxs-lookup"><span data-stu-id="22332-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Gebruikt u ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="22332-115">Selecteer 'Verbinding maken met ServiceNow' om naar de servicenow-instellingspagina te gaan.</span><span class="sxs-lookup"><span data-stu-id="22332-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="22332-116">Volg de instructies voor het autoriseren van de Microsoft 365 Connector-app.</span><span class="sxs-lookup"><span data-stu-id="22332-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="22332-117">Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u de aanmelding en het wachtwoord van de integratiegebruiker gebruiken die u in de installatiestappen hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="22332-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="22332-118">Gebruik uw persoonlijke referenties niet.</span><span class="sxs-lookup"><span data-stu-id="22332-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="22332-119">Nadat u de aanwijzingen hebt gevolgd en de verbinding hebt geautoriseerd, bekijkt u de verbindingsstatus op zowel de verbindingspagina van microsoft 365-beveiligingscentrum als in de ServiceNow Microsoft 365 Ticketing Connector-app-ervaring.</span><span class="sxs-lookup"><span data-stu-id="22332-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="22332-120">Nu bent u helemaal klaar om te beginnen met het maken van taken!</span><span class="sxs-lookup"><span data-stu-id="22332-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="22332-121">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="22332-121">Troubleshooting</span></span>

<span data-ttu-id="22332-122">Lees algemene fouten die u in het verbindingsproces tegenkomen en hoe u deze beperken in de [sectie Probleemoplossing](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="22332-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="22332-123">Een taak maken en delen met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="22332-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="22332-124">Zodra de integratie is ingesteld, maakt u ServiceNow-taken op basis van specifieke microsoft Secure Score-verbeteringsacties. [Microsoft Secure Score](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="22332-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="22332-125">Ga naar een verbeteringsactie in Secure Score in de Microsoft 365-beveiligingscentrumportal en selecteer **Delen**.</span><span class="sxs-lookup"><span data-stu-id="22332-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select **Share**.</span></span> <span data-ttu-id="22332-126">Een van de vervolgkeuzeopties is ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="22332-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="22332-127">Er wordt een taak gegenereerd waarin u de prioriteit instellen en de naam, beschrijving of vervaldatum bewerken.</span><span class="sxs-lookup"><span data-stu-id="22332-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="22332-128">Zodra alle vereiste velden zijn ingevuld, stuurt u de taak naar ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="22332-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="22332-129">De taak is zichtbaar in ServiceNow als een Microsoft 365-aanvraag voor beveiligings- en configuratiewijziging.</span><span class="sxs-lookup"><span data-stu-id="22332-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="22332-130">Tickets volgen</span><span class="sxs-lookup"><span data-stu-id="22332-130">Track tickets</span></span>

<span data-ttu-id="22332-131">Zodra ServiceNow change management en incident management tickets zijn gemaakt, worden ze weergegeven op kaarten in de Microsoft 365 security center startpagina.</span><span class="sxs-lookup"><span data-stu-id="22332-131">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="22332-132">Met deze kaarten u een ticket maken, alle tickets bekijken of de ServiceNow-configuratie beheren.</span><span class="sxs-lookup"><span data-stu-id="22332-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow wijzigbeheertickets](../../media/change-management-375.png)  ![ServiceNow incident management tickets](../../media/incident-management-375.png)

<span data-ttu-id="22332-135">Als u uw ServiceNow-integratie in het Microsoft 365-beveiligingscentrum opnieuw wilt inrichten of beheren, selecteert u **ServiceNow-configuratie beheren** op een van de kaarten.</span><span class="sxs-lookup"><span data-stu-id="22332-135">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="22332-136">Verwijder van daaruit de huidige ServiceNow-verbinding en pas de namen van de ticketstatus aan.</span><span class="sxs-lookup"><span data-stu-id="22332-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="22332-137">Met ServiceNow-tickets die zichtbaar zijn in het Microsoft 365-beveiligingscentrum, wonen uw taken op een plaats waar ze kunnen worden gevolgd en waarop, naast uw andere beveiligingsdashboarditems, kan worden gereageerd.</span><span class="sxs-lookup"><span data-stu-id="22332-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="22332-138">Resources</span><span class="sxs-lookup"><span data-stu-id="22332-138">Resources</span></span>

- [<span data-ttu-id="22332-139">Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing</span><span class="sxs-lookup"><span data-stu-id="22332-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="22332-140">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="22332-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)