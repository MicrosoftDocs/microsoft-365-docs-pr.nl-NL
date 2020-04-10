---
title: Office 365 ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop users from clicking bad links, malicious links
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
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212543"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="b40aa-104">Veilige koppelingen voor Office 365 in Teams</span><span class="sxs-lookup"><span data-stu-id="b40aa-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b40aa-105">Deze functie is vanaf 28 februari 2020 in **Public Preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP).</span><span class="sxs-lookup"><span data-stu-id="b40aa-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="b40aa-106">Deze notitie wordt uit het artikel verwijderd wanneer Safe Links for Teams op grotere schaal beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="b40aa-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="b40aa-107">Microsoft Teams, een office 365 Cloud-toepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot veilige koppelingen op het moment van uw klik.</span><span class="sxs-lookup"><span data-stu-id="b40aa-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="b40aa-108">Of u nu chats 1-op-1 chats gebruikt, tussen groepen of in kanalen en tabbladen, als u een abonnement hebt op Office 365 ATP, u hebt de mogelijkheid om deze veiligheidsmaatregel in te schakelen en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b40aa-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="b40aa-109">Zo werkt het:</span><span class="sxs-lookup"><span data-stu-id="b40aa-109">Here's how it works:</span></span> 

1. <span data-ttu-id="b40aa-110">Wanneer u de Toepassing Teams start, controleert Office 365 of de gebruiker behoort tot een organisatie met Office 365 ATP en of de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de beveiliging ingeschakeld voor Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b40aa-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="b40aa-111">Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in Tabbladen voor die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b40aa-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

> [!NOTE]
> <span data-ttu-id="b40aa-112">Veilige links beschermt gebruikers tegen links die worden verzonden door gastgebruikers, Federatieve gebruikers, tenantgebruikers.</span><span class="sxs-lookup"><span data-stu-id="b40aa-112">Safe links safeguards users from links sent by Guest users, Federated users, tenant users.</span></span> <span data-ttu-id="b40aa-113">Als de aangemelde gebruiker veilige koppelingen voor Teams heeft ingeschakeld, zijn er veilige koppelingen van toepassing.</span><span class="sxs-lookup"><span data-stu-id="b40aa-113">If the user logged in has safe links for Teams enabled, then safe links protections will apply.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="b40aa-114">Wat zullen gebruikers ervaren?</span><span class="sxs-lookup"><span data-stu-id="b40aa-114">What will users experience?</span></span> 

<span data-ttu-id="b40aa-115">Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's:</span><span class="sxs-lookup"><span data-stu-id="b40aa-115">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="b40aa-116">Als op de koppeling is geklikt vanuit een Team-gesprek, groepschat of van kanalen, wordt een pagina weergegeven in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="b40aa-116">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="b40aa-117">Als er op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de GUI van Teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="b40aa-117">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="b40aa-118">Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.</span><span class="sxs-lookup"><span data-stu-id="b40aa-118">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="b40aa-119">Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, kan hij of zij op de URL op zijn of haar machine klikken en de probleemsite oplossen.</span><span class="sxs-lookup"><span data-stu-id="b40aa-119">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="b40aa-120">Dit maakt het dubbel belangrijk voor Office 365-beheerders om zich bewust te zijn van wie hun beschermde gebruikers zijn en moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="b40aa-120">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![Een pagina Veilige koppelingen voor Teams die een kwaadaardige koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="b40aa-122">Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit ertoe leiden dat gebruikers een lege pagina sluiten).</span><span class="sxs-lookup"><span data-stu-id="b40aa-122">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="b40aa-123">Als u echter opnieuw op de link klikt, wordt de reputatie van de site opnieuw beoordeeld, zodat deze pagina opnieuw wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b40aa-123">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="b40aa-124">Sommige Office 365-beheerders schakelen het bericht **Doorgaan toch** in op de blokkeringspagina.</span><span class="sxs-lookup"><span data-stu-id="b40aa-124">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="b40aa-125">Echter, als veilige links meet de reputatie van een site en vindt het ontbreekt, geen verdere click-through moet worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="b40aa-125">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="b40aa-126">Het wordt niet aanbevolen dat gebruikers veiligheidsmaatregelen omzeilen.</span><span class="sxs-lookup"><span data-stu-id="b40aa-126">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="b40aa-127">Gelieve dit af te wegen in uw overwegingen voordat u Toch doorgaan.</span><span class="sxs-lookup"><span data-stu-id="b40aa-127">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

