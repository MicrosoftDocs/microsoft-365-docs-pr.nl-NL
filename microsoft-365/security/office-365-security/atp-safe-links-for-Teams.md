---
title: Office 365 ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop gebruikers van het klikken op slechte links, kwaadaardige links
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Teams hebben nu toegang tot veilige links op het moment van uw klik. Of u nu chats 1-op-1 Chats, tussen groepen of in kanalen en tabbladen gebruikt, als u een abonnement hebt op Office 365 ATP, u deze veiligheidsfunctie inschakelen en gebruiken.
ms.openlocfilehash: ba7ef2ae63b788ec94fbbb15c3c00312177a59d5
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42809634"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="e3293-104">Veilige koppelingen in Office 365 in teams</span><span class="sxs-lookup"><span data-stu-id="e3293-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3293-105">Deze functie is vanaf 28 februari 2020 in **Openbare preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP).</span><span class="sxs-lookup"><span data-stu-id="e3293-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="e3293-106">Deze notitie wordt uit het artikel verwijderd wanneer veilige koppelingen voor teams breder beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="e3293-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="e3293-107">Microsoft Teams, een office 365 Cloud-gebaseerde toepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot veilige koppelingen op het moment van uw klik.</span><span class="sxs-lookup"><span data-stu-id="e3293-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="e3293-108">Of u nu chats 1-op-1 Chats, tussen groepen of in kanalen en tabbladen gebruikt, als u een abonnement hebt op Office 365 ATP, u deze veiligheidsmaatregel inschakelen en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e3293-108">Whether you’re using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="e3293-109">Zo werkt het:</span><span class="sxs-lookup"><span data-stu-id="e3293-109">Here’s how it works:</span></span> 

1. <span data-ttu-id="e3293-110">Wanneer u de toepassing Teams start, controleert Office 365 of de gebruiker deel uitmaakt van een organisatie die Office 365 ATP heeft en of de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de beveiliging die is ingeschakeld voor Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e3293-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="e3293-111">Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in Tabbladen voor die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e3293-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="e3293-112">Wat zullen gebruikers ervaren?</span><span class="sxs-lookup"><span data-stu-id="e3293-112">What will users experience?</span></span> 

<span data-ttu-id="e3293-113">Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's:</span><span class="sxs-lookup"><span data-stu-id="e3293-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="e3293-114">Als er op de koppeling is geklikt vanuit een teamgesprek, groepschat of via kanalen, wordt een pagina weergegeven in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="e3293-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="e3293-115">Als op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de Gui Teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="e3293-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="e3293-116">Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.</span><span class="sxs-lookup"><span data-stu-id="e3293-116">This user will be blocked from proceeding to the URL’s site.</span></span>

<span data-ttu-id="e3293-117">Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, is hij of zij vrij om op de URL op zijn of haar machine te klikken en de probleemsite op te lossen.</span><span class="sxs-lookup"><span data-stu-id="e3293-117">If the user who sent the link isn’t protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="e3293-118">Dit maakt het dubbel belangrijk voor Office 365-beheerders om zich bewust te zijn van wie hun beveiligde gebruikers zijn en moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="e3293-118">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![Een pagina Veilige koppelingen voor teams die een schadelijke koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="e3293-120">Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit resulteren in een lege pagina die gebruikers kunnen afsluiten).</span><span class="sxs-lookup"><span data-stu-id="e3293-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="e3293-121">Als u echter opnieuw op de koppeling klikt, wordt de reputatie van de site opnieuw beoordeeld, zodat deze pagina opnieuw wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e3293-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="e3293-122">Sommige Office 365-beheerders schakelen het **bericht Doorgaan hoe dan ook** in op de blokkeringspagina.</span><span class="sxs-lookup"><span data-stu-id="e3293-122">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="e3293-123">Echter, als veilige links maatregelen van de reputatie van een site en vindt het ontbreekt, geen verdere click-through moet worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="e3293-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="e3293-124">Het wordt afgeraden dat gebruikers veiligheidsmaatregelen omzeilen.</span><span class="sxs-lookup"><span data-stu-id="e3293-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="e3293-125">Weeg dit af in uw overwegingen voordat u Doorgaan toch inschakelt.</span><span class="sxs-lookup"><span data-stu-id="e3293-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

