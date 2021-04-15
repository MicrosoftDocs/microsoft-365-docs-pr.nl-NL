---
title: Gebruikers in Microsoft 365-beveiligingscentrum onderzoeken
description: gebruikers onderzoeken in het Microsoft 365-beveiligingscentrum
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 6535493efb844f1413c569a28ebf36ddb05c167d
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760198"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="3856c-104">Gebruikers in Microsoft 365-beveiligingscentrum onderzoeken</span><span class="sxs-lookup"><span data-stu-id="3856c-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3856c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3856c-105">**Applies to:**</span></span>

- <span data-ttu-id="3856c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3856c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3856c-107">Als onderdeel van uw onderzoek kunt u zien dat een gebruiker is gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="3856c-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="3856c-108">De gebruikerspagina van het Microsoft 365-beveiligingscentrum combineert gegevens van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt).</span><span class="sxs-lookup"><span data-stu-id="3856c-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="3856c-109">Deze pagina is de ideale startplaats voor het onderzoeken van gebruikers en mogelijke incidenten.</span><span class="sxs-lookup"><span data-stu-id="3856c-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="3856c-110">![Gebruikerspagina](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="3856c-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="3856c-111">Op deze pagina ziet u informatie die specifiek is voor het beveiligingsrisico van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3856c-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="3856c-112">Dit omvat een score die helpt bij het beoordelen van risico's, recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het totale risico van de gebruiker, en meer.</span><span class="sxs-lookup"><span data-stu-id="3856c-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="3856c-113">U kunt deze pagina openen vanuit meerdere gebieden in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="3856c-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="3856c-114">U kunt deze pagina openen vanuit een specifiek incident op **het tabblad** Gebruikers. Sommige waarschuwingen kunnen gebruikers bevatten als een specifiek beïnvloed activum.</span><span class="sxs-lookup"><span data-stu-id="3856c-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="3856c-115">U kunt ook zoeken naar gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3856c-115">You can also search for users.</span></span>  

<span data-ttu-id="3856c-116">Meer informatie over het onderzoeken van gebruikers en potentiële risico's [in deze zelfstudie over cloud-appbeveiliging.](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)</span><span class="sxs-lookup"><span data-stu-id="3856c-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3856c-117">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3856c-117">Related topics</span></span>

- [<span data-ttu-id="3856c-118">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="3856c-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="3856c-119">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="3856c-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="3856c-120">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="3856c-120">Manage incidents</span></span>](manage-incidents.md)