---
title: ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop users from clicking bad links, malicious links ATP, ATP ATP, Teams safe links, stop users from clicking bad links, malicious links ATP, ATP
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
description: Teams hebben nu toegang tot veilige links op het moment van uw klik. Of u nu chats 1-op-1 chats gebruikt, tussen groepen of in kanalen en tabbladen, als u een abonnement hebt op Office 365 ATP, u deze veiligheidsfunctie inschakelen en gebruiken.
ms.openlocfilehash: d7586dba86c7ec9f43457b5510a1255e06bb6bf9
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588274"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="401cb-104">Veilige links in teams</span><span class="sxs-lookup"><span data-stu-id="401cb-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="401cb-105">Deze functie is vanaf 28 februari 2020 in **Public Preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP).</span><span class="sxs-lookup"><span data-stu-id="401cb-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="401cb-106">Deze notitie wordt uit het artikel verwijderd wanneer Veilige links voor teams op grotere schaal beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="401cb-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="401cb-107">Microsoft Teams, een cloudtoepassing van Microsoft voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot Veilige koppelingen op het moment van uw klik.</span><span class="sxs-lookup"><span data-stu-id="401cb-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="401cb-108">Of u nu Chats, Groepschats, kanalen of tabbladen gebruikt, als u een abonnement op Office 365 ATP hebt, u deze veiligheidsmaatregel inschakelen en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="401cb-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="401cb-109">Zie [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)voor meer informatie over licentievereisten.</span><span class="sxs-lookup"><span data-stu-id="401cb-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="401cb-110">Zo werkt het:</span><span class="sxs-lookup"><span data-stu-id="401cb-110">Here's how it works:</span></span>

1. <span data-ttu-id="401cb-111">Wanneer u de Teams-toepassing start, controleert Microsoft 365 of de gebruiker deel uitmaakt van een organisatie met Office 365 ATP en of de gebruiker deel uitmaakt van een beleid voor actieve veilige koppelingen met de beveiliging ingeschakeld voor Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="401cb-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="401cb-112">Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in tabbladen voor die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="401cb-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

## <a name="what-will-users-experience"></a><span data-ttu-id="401cb-113">Wat zullen gebruikers ervaren?</span><span class="sxs-lookup"><span data-stu-id="401cb-113">What will users experience?</span></span>

<span data-ttu-id="401cb-114">Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's:</span><span class="sxs-lookup"><span data-stu-id="401cb-114">All protected users will have this experience with hazardous URLs:</span></span>

- <span data-ttu-id="401cb-115">Als er op de koppeling is geklikt vanuit een teamgesprek, groepschat of kanalen, wordt een pagina weergegeven in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="401cb-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="401cb-116">Als er op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de GUI teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="401cb-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="401cb-117">Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.</span><span class="sxs-lookup"><span data-stu-id="401cb-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="401cb-118">Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, is hij of zij vrij om op de URL op zijn of haar computer te klikken en de probleemsite op te lossen.</span><span class="sxs-lookup"><span data-stu-id="401cb-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="401cb-119">Dit maakt het dubbel belangrijk voor beheerders om zich bewust te zijn van wie hun beschermde gebruikers zijn en moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="401cb-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Een pagina Veilige links voor teams die een schadelijke koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="401cb-121">Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit resulteren in een lege pagina die gebruikers kunnen sluiten).</span><span class="sxs-lookup"><span data-stu-id="401cb-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="401cb-122">Het opnieuw klikken op de link zal echter resulteren in een herbeoordeling van de reputatie van de site, zodat deze pagina opnieuw verschijnt.</span><span class="sxs-lookup"><span data-stu-id="401cb-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="401cb-123">Sommige Microsoft 365-beheerders schakelen het bericht **Doorgaan hoe dan ook** in op de blokkeringspagina.</span><span class="sxs-lookup"><span data-stu-id="401cb-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="401cb-124">Als Safe Links echter de reputatie van een site meet en deze niet merkt, moet er geen verdere doorklik worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="401cb-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="401cb-125">Het wordt afgeraden dat gebruikers veiligheidsmaatregelen omzeilen.</span><span class="sxs-lookup"><span data-stu-id="401cb-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="401cb-126">Weeg dit af in uw overwegingen voordat u Doorgaan inschakelt.</span><span class="sxs-lookup"><span data-stu-id="401cb-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span>
