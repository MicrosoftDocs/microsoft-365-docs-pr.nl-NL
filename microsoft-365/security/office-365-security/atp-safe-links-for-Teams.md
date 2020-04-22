---
title: ATP Safe Links for Teams, safelinks, veilige links, kwaadaardige links blokkeren, office 365 atp, Teams veilige links, voorkomen dat gebruikers op slechte links klikken, kwaadaardige links
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Teams hebben nu toegang tot veilige links op het moment van uw klik. Of u nu chats 1-op-1 chats gebruikt, tussen Groepen of in Kanalen en Tabbladen, als u een abonnement hebt op Office 365 ATP, hebt u de mogelijkheid om deze veiligheidsfunctie in te schakelen en te gebruiken.
ms.openlocfilehash: 88fe9756188eb16a2347d3c0cd4a98b4003ff457
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635996"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="6357b-104">Veilige links in Teams</span><span class="sxs-lookup"><span data-stu-id="6357b-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6357b-105">Deze functie is vanaf 28 februari 2020 in **Public Preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP).</span><span class="sxs-lookup"><span data-stu-id="6357b-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="6357b-106">Deze notitie wordt uit het artikel verwijderd wanneer Safe Links for Teams op grotere schaal beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="6357b-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="6357b-107">Microsoft Teams, een microsoft-cloudtoepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot veilige koppelingen op het moment van uw klik.</span><span class="sxs-lookup"><span data-stu-id="6357b-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="6357b-108">Of u nu chats 1-op-1 chats gebruikt, tussen groepen of in kanalen en tabbladen, als u een abonnement hebt op Office 365 ATP, u hebt de mogelijkheid om deze veiligheidsmaatregel in te schakelen en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6357b-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="6357b-109">Zo werkt het:</span><span class="sxs-lookup"><span data-stu-id="6357b-109">Here's how it works:</span></span> 

1. <span data-ttu-id="6357b-110">Wanneer u de Toepassing Teams start, controleert Microsoft 365 of de gebruiker behoort tot een organisatie met Office 365 ATP en of de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de beveiliging ingeschakeld voor Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6357b-110">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="6357b-111">Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in Tabbladen voor die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="6357b-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="6357b-112">Wat zullen gebruikers ervaren?</span><span class="sxs-lookup"><span data-stu-id="6357b-112">What will users experience?</span></span> 

<span data-ttu-id="6357b-113">Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's:</span><span class="sxs-lookup"><span data-stu-id="6357b-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="6357b-114">Als op de koppeling is geklikt vanuit een Team-gesprek, groepschat of van kanalen, wordt een pagina weergegeven in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="6357b-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="6357b-115">Als er op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de GUI van Teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="6357b-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="6357b-116">Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.</span><span class="sxs-lookup"><span data-stu-id="6357b-116">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="6357b-117">Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, kan hij of zij op de URL op zijn of haar machine klikken en de probleemsite oplossen.</span><span class="sxs-lookup"><span data-stu-id="6357b-117">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="6357b-118">Dit maakt het dubbel belangrijk voor beheerders om zich bewust te zijn van wie hun beschermde gebruikers zijn en moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="6357b-118">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Een pagina Veilige koppelingen voor Teams die een kwaadaardige koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="6357b-120">Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit ertoe leiden dat gebruikers een lege pagina sluiten).</span><span class="sxs-lookup"><span data-stu-id="6357b-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="6357b-121">Als u echter opnieuw op de link klikt, wordt de reputatie van de site opnieuw beoordeeld, zodat deze pagina opnieuw wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6357b-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="6357b-122">Sommige Microsoft 365-beheerders schakelen het bericht **Doorgaan toch** in op de blokkeringspagina.</span><span class="sxs-lookup"><span data-stu-id="6357b-122">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="6357b-123">Echter, als veilige links meet de reputatie van een site en vindt het ontbreekt, geen verdere click-through moet worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="6357b-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="6357b-124">Het wordt niet aanbevolen dat gebruikers veiligheidsmaatregelen omzeilen.</span><span class="sxs-lookup"><span data-stu-id="6357b-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="6357b-125">Gelieve dit af te wegen in uw overwegingen voordat u Toch doorgaan.</span><span class="sxs-lookup"><span data-stu-id="6357b-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

