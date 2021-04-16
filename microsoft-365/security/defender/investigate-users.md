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
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861258"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="33b88-104">Gebruikers in Microsoft 365-beveiligingscentrum onderzoeken</span><span class="sxs-lookup"><span data-stu-id="33b88-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="33b88-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="33b88-105">**Applies to:**</span></span>

- <span data-ttu-id="33b88-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33b88-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="33b88-107">Een deel van uw incidentonderzoek kan gebruikersaccounts zijn.</span><span class="sxs-lookup"><span data-stu-id="33b88-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="33b88-108">Begin met het **tabblad Gebruikers** voor een incident van Incidenten & **waarschuwingen >** incident *>* **Gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="33b88-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een pagina Gebruikers voor een incident":::

<span data-ttu-id="33b88-110">Als u een beknopt overzicht wilt krijgen van een gebruikersaccount voor het incident, selecteert u het vinkje naast de naam van het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="33b88-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="33b88-111">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="33b88-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Voorbeeld van het overzichtsvenster voor gebruikersaccounts voor een incident in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="33b88-113">Hier kunt u Ga naar gebruikerspagina selecteren **om** de details van een gebruikersaccount te bekijken.</span><span class="sxs-lookup"><span data-stu-id="33b88-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="33b88-114">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="33b88-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Voorbeeld van de pagina met gebruikersaccounts voor een incident in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="33b88-116">U kunt deze pagina ook zien door de naam van het gebruikersaccount te selecteren in de lijst op de **pagina** Gebruikers.</span><span class="sxs-lookup"><span data-stu-id="33b88-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="33b88-117">De gebruikerspagina van het Microsoft 365-beveiligingscentrum combineert gegevens van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt).</span><span class="sxs-lookup"><span data-stu-id="33b88-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="33b88-118">Op deze pagina ziet u informatie die specifiek is voor het beveiligingsrisico van een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="33b88-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="33b88-119">Dit omvat een score die helpt bij het beoordelen van risico's en recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het algehele risico van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="33b88-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="33b88-120">Op deze pagina kunt u deze extra acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="33b88-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="33b88-121">Het gebruikersaccount markeren als gecompromitteerd</span><span class="sxs-lookup"><span data-stu-id="33b88-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="33b88-122">De gebruiker verplichten zich opnieuw aan te melden</span><span class="sxs-lookup"><span data-stu-id="33b88-122">Require the user to sign in again</span></span>
- <span data-ttu-id="33b88-123">Het gebruikersaccount opschorten</span><span class="sxs-lookup"><span data-stu-id="33b88-123">Suspend the user account</span></span>
- <span data-ttu-id="33b88-124">De gebruikersaccountinstellingen van Azure Active Directory (Azure AD) bekijken</span><span class="sxs-lookup"><span data-stu-id="33b88-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="33b88-125">De bestanden weergeven die eigendom zijn van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="33b88-125">View the files owned by the user account</span></span>
- <span data-ttu-id="33b88-126">Bestanden weergeven die met deze gebruiker zijn gedeeld.</span><span class="sxs-lookup"><span data-stu-id="33b88-126">View files shared with this user.</span></span> 

<span data-ttu-id="33b88-127">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="33b88-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Voorbeeld van de acties op een gebruikersaccount voor een incident in het Microsoft 365-beveiligingscentrum":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="33b88-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="33b88-129">Related topics</span></span>

- [<span data-ttu-id="33b88-130">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="33b88-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="33b88-131">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="33b88-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="33b88-132">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="33b88-132">Manage incidents</span></span>](manage-incidents.md)