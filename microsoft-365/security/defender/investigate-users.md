---
title: Gebruikers in Microsoft 365 Defender onderzoeken
description: Gebruikers onderzoeken op een incident in het beveiligingscentrum Microsoft 365.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps, incident, analyseren, reactie
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572799"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="8bb8f-104">Gebruikers in Microsoft 365 Defender onderzoeken</span><span class="sxs-lookup"><span data-stu-id="8bb8f-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8bb8f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8bb8f-105">**Applies to:**</span></span>

- <span data-ttu-id="8bb8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bb8f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8bb8f-107">Een deel van uw incidentonderzoek kan gebruikersaccounts bevatten.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="8bb8f-108">Begin met het tabblad **Gebruikers** voor een incident van **incidenten & waarschuwingen >** *incident* **> gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een gebruikerspagina voor een incident":::

<span data-ttu-id="8bb8f-110">Als u een snel overzicht wilt krijgen van een gebruikersaccount voor het incident, selecteert u het vinkje naast de naam van de gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="8bb8f-111">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Voorbeeld van het overzichtsvenster van de gebruikersaccount voor een incident in het beveiligingscentrum Microsoft 365":::

> [!NOTE]
> <span data-ttu-id="8bb8f-113">Op de pagina Gebruiker wordt Azure Active Directory (Azure AD)-organisatie en groepen weergegeven, zodat u inzicht hebt in de groepen en machtigingen die aan een gebruiker zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="8bb8f-114">Op deze fly-outpagina kunt u informatie over gebruikersbedreiging bekijken, inclusief actuele incidenten, actieve waarschuwingen en risiconiveau, evenals blootstelling van gebruikers, accounts, apparaten en meer.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="8bb8f-115">Bovendien kunt u rechtstreeks actie ondernemen in het beveiligingscentrum Microsoft 365 om een gecompromitteerde gebruiker aan te spreken, te bevestigen dat de gebruiker is gecompromitteerd of dat deze opnieuw moet worden aangemeld.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="8bb8f-116">Vanaf hier kunt u **Ga naar gebruikerspagina** selecteren om de details van een gebruikersaccount te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="8bb8f-117">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Voorbeeld van de gebruikersaccountpagina voor een incident in het beveiligingscentrum Microsoft 365":::

<span data-ttu-id="8bb8f-119">U kunt deze pagina ook bekijken door de naam van het gebruikersaccount te selecteren in de lijst op de pagina **Gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="8bb8f-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="8bb8f-120">De gebruikerspagina van het beveiligingscentrum Microsoft 365 combineert informatie van Microsoft Defender voor eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt).</span><span class="sxs-lookup"><span data-stu-id="8bb8f-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="8bb8f-121">Op deze pagina vindt u informatie die specifiek is voor het beveiligingsrisico van een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="8bb8f-122">Dit omvat een score die helpt bij het beoordelen van risico's en recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het algehele risico van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="8bb8f-123">Vanaf deze pagina kunt u deze aanvullende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="8bb8f-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="8bb8f-124">Het gebruikersaccount markeren als gecompromitteerd</span><span class="sxs-lookup"><span data-stu-id="8bb8f-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="8bb8f-125">Vereisen dat de gebruiker zich opnieuw aanmeldt</span><span class="sxs-lookup"><span data-stu-id="8bb8f-125">Require the user to sign in again</span></span>
- <span data-ttu-id="8bb8f-126">Het gebruikersaccount opschorten</span><span class="sxs-lookup"><span data-stu-id="8bb8f-126">Suspend the user account</span></span>
- <span data-ttu-id="8bb8f-127">De instellingen van het gebruikersaccount van Azure Active Directory (Azure AD) bekijken</span><span class="sxs-lookup"><span data-stu-id="8bb8f-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="8bb8f-128">De bestanden weergeven die eigendom zijn van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="8bb8f-128">View the files owned by the user account</span></span>
- <span data-ttu-id="8bb8f-129">Bestanden weergeven die met deze gebruiker zijn gedeeld.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-129">View files shared with this user.</span></span> 

<span data-ttu-id="8bb8f-130">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8bb8f-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Voorbeeld van de acties op een gebruikersaccount voor een incident in het beveiligingscentrum Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="8bb8f-132">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="8bb8f-132">Next steps</span></span>

<span data-ttu-id="8bb8f-133">Als dat nodig is voor incidenten in het proces, gaat u verder met uw [onderzoek.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="8bb8f-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bb8f-134">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8bb8f-134">See also</span></span>

- [<span data-ttu-id="8bb8f-135">Overzicht incidenten</span><span class="sxs-lookup"><span data-stu-id="8bb8f-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8bb8f-136">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="8bb8f-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="8bb8f-137">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="8bb8f-137">Manage incidents</span></span>](manage-incidents.md)