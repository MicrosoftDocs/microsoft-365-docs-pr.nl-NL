---
title: Gebruikers analyseren in het Microsoft 365-beveiligingscentrum
description: Gebruikers analyseren in het Microsoft 365-beveiligingscentrum
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps, incident, analyseren, antwoord
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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957603"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="ae93e-104">Gebruikers analyseren in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="ae93e-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ae93e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ae93e-105">**Applies to:**</span></span>

- <span data-ttu-id="ae93e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae93e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ae93e-107">Een deel van uw incidentanalyse kan gebruikersaccounts bevatten.</span><span class="sxs-lookup"><span data-stu-id="ae93e-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="ae93e-108">Begin met het **tabblad Gebruikers** voor een incident van Incidenten & **waarschuwingen >** incident *>* **Gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="ae93e-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een pagina Gebruikers voor een incident":::

<span data-ttu-id="ae93e-110">Als u een beknopt overzicht wilt krijgen van een gebruikersaccount voor het incident, selecteert u het vinkje naast de naam van het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="ae93e-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="ae93e-111">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ae93e-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Voorbeeld van het overzichtsvenster voor gebruikersaccounts voor een incident in het Microsoft 365-beveiligingscentrum":::

> [!NOTE]
> <span data-ttu-id="ae93e-113">Op de pagina Gebruiker ziet u een Azure Active Directory-organisatie (AD) en groepen, zodat u inzicht krijgt in de groepen en machtigingen die aan een gebruiker zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ae93e-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="ae93e-114">Op deze fly-outpagina kunt u informatie over bedreigingen van gebruikers bekijken, waaronder actuele incidenten, actieve waarschuwingen en risiconiveau, evenals blootstelling van gebruikers, accounts, apparaten en meer.</span><span class="sxs-lookup"><span data-stu-id="ae93e-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="ae93e-115">Daarnaast kunt u rechtstreeks actie ondernemen in het Microsoft 365-beveiligingscentrum om een gecompromitteerde gebruiker aan te pakken, om te bevestigen dat de gebruiker is gecompromitteerd of dat hij of zij zich opnieuw moet aanmelden.</span><span class="sxs-lookup"><span data-stu-id="ae93e-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="ae93e-116">Hier kunt u Ga naar gebruikerspagina selecteren **om** de details van een gebruikersaccount te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ae93e-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="ae93e-117">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ae93e-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Voorbeeld van de pagina met gebruikersaccounts voor een incident in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="ae93e-119">U kunt deze pagina ook zien door de naam van het gebruikersaccount te selecteren in de lijst op de **pagina** Gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ae93e-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="ae93e-120">De gebruikerspagina van het Microsoft 365-beveiligingscentrum combineert gegevens van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt).</span><span class="sxs-lookup"><span data-stu-id="ae93e-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="ae93e-121">Op deze pagina ziet u informatie die specifiek is voor het beveiligingsrisico van een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="ae93e-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="ae93e-122">Dit omvat een score die helpt bij het beoordelen van risico's en recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het algehele risico van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ae93e-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="ae93e-123">Op deze pagina kunt u deze extra acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="ae93e-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="ae93e-124">Het gebruikersaccount markeren als gecompromitteerd</span><span class="sxs-lookup"><span data-stu-id="ae93e-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="ae93e-125">De gebruiker verplichten zich opnieuw aan te melden</span><span class="sxs-lookup"><span data-stu-id="ae93e-125">Require the user to sign in again</span></span>
- <span data-ttu-id="ae93e-126">Het gebruikersaccount opschorten</span><span class="sxs-lookup"><span data-stu-id="ae93e-126">Suspend the user account</span></span>
- <span data-ttu-id="ae93e-127">De gebruikersaccountinstellingen van Azure Active Directory (Azure AD) bekijken</span><span class="sxs-lookup"><span data-stu-id="ae93e-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="ae93e-128">De bestanden weergeven die eigendom zijn van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="ae93e-128">View the files owned by the user account</span></span>
- <span data-ttu-id="ae93e-129">Bestanden weergeven die met deze gebruiker zijn gedeeld.</span><span class="sxs-lookup"><span data-stu-id="ae93e-129">View files shared with this user.</span></span> 

<span data-ttu-id="ae93e-130">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ae93e-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Voorbeeld van de acties op een gebruikersaccount voor een incident in het Microsoft 365-beveiligingscentrum":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="ae93e-132">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ae93e-132">Related topics</span></span>

- [<span data-ttu-id="ae93e-133">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="ae93e-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ae93e-134">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="ae93e-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ae93e-135">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="ae93e-135">Manage incidents</span></span>](manage-incidents.md)