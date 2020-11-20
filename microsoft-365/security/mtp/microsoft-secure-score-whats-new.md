---
title: Nieuw in Microsoft Secure Score
description: Beschrijft welke nieuwe wijzigingen zijn doorgevoerd in Microsoft Secure Score in het Microsoft 365-Beveiligingscentrum.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center
ms.prod: microsoft-365-enterprise
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
- seo-marvel-jun2020
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367107"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="ce509-104">Nieuw in Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="ce509-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ce509-105">Als u Microsoft Secure Score een betere vertegenwoordiger van uw beveiligings Posture wilt maken, hebben we enkele wijzigingen aangebracht.</span><span class="sxs-lookup"><span data-stu-id="ce509-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="ce509-106">Zie voor meer informatie over geplande wijzigingen wat er wordt weergegeven [in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="ce509-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="ce509-107">November 2020</span><span class="sxs-lookup"><span data-stu-id="ce509-107">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="ce509-108">Voor Microsoft Defender voor eindpunt zijn 3 extra uitbreidingen voor kwaliteitsverbetering toegevoegd (voorheen Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="ce509-108">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="ce509-109">Het service traject voor niet-geciteerde Windows-Services oplossen</span><span class="sxs-lookup"><span data-stu-id="ce509-109">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="ce509-110">Het uitvoerbare pad van de service wijzigen in een bekende beveiligde locatie</span><span class="sxs-lookup"><span data-stu-id="ce509-110">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="ce509-111">Serviceaccount wijzigen om het wachtwoord in de cache te vermijden in het Windows-register</span><span class="sxs-lookup"><span data-stu-id="ce509-111">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="ce509-112">Oktober 2020</span><span class="sxs-lookup"><span data-stu-id="ce509-112">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="ce509-113">Actie voor verbetering van Microsoft Defender voor eindpunt verwijderen</span><span class="sxs-lookup"><span data-stu-id="ce509-113">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="ce509-114">Microsoft Windows Store voor de Windows Store-app voor Windows Store voor de spellingcontrole instellen op waarschuwen</span><span class="sxs-lookup"><span data-stu-id="ce509-114">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="ce509-115">Augustus 2020</span><span class="sxs-lookup"><span data-stu-id="ce509-115">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="ce509-116">Actie voor verbetering van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ce509-116">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="ce509-117">Beleid inschakelen voor het blokkeren van oudere verificatie</span><span class="sxs-lookup"><span data-stu-id="ce509-117">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="ce509-118">Incompatibiliteit met identificatie beveiligings Score en Graph-API</span><span class="sxs-lookup"><span data-stu-id="ce509-118">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="ce509-119">In de recente versie van Microsoft Secure Score is een verbeterd score model uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="ce509-119">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="ce509-120">Met deze wijzigingen kunt u een flexibele en nauwkeurige weergave van uw beveiligings posture.</span><span class="sxs-lookup"><span data-stu-id="ce509-120">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="ce509-121">Deze updates hebben echter de Microsoft Secure Score tijdelijk niet compatibel gemaakt met identiteitsbeveiliging en de Graph API.</span><span class="sxs-lookup"><span data-stu-id="ce509-121">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="ce509-122">In tijd wordt de identiteitsbeveiliging Score en de Graph API het nieuwe score model.</span><span class="sxs-lookup"><span data-stu-id="ce509-122">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="ce509-123">Vervolgens zien klanten verschillen in de scores die zijn gerapporteerd door Microsoft Secure Score, Identity Secure Score en Graph API.</span><span class="sxs-lookup"><span data-stu-id="ce509-123">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="ce509-124">Onze excuses voor het ongemak, en werken om ervoor te zorgen dat deze functies in de toekomst verder compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="ce509-124">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="ce509-125">Gewijzigde acties voor verbetering</span><span class="sxs-lookup"><span data-stu-id="ce509-125">Updated improvement actions</span></span>

- <span data-ttu-id="ce509-126">Azure Active Directory-verbeterings acties toegevoegd</span><span class="sxs-lookup"><span data-stu-id="ce509-126">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="ce509-127">Microsoft Defender heeft toegevoegd voor Identity-verbeterings acties</span><span class="sxs-lookup"><span data-stu-id="ce509-127">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="ce509-128">Ondersteuning voor Microsoft Defender voor de [bedreiging &](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="ce509-128">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="ce509-129">Alle vrijgegeven beveiligingsaanbevelingen van TVM zijn nu beschikbaar</span><span class="sxs-lookup"><span data-stu-id="ce509-129">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="ce509-130">Bijgewerkte interface en functionaliteit</span><span class="sxs-lookup"><span data-stu-id="ce509-130">Updated interface and functionality</span></span>

* <span data-ttu-id="ce509-131">Alle nieuwe metrische en trends weergaven voor discussies voor CISO en potentiële klanten</span><span class="sxs-lookup"><span data-stu-id="ce509-131">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="ce509-132">Nieuwe manieren om uw score bij te houden en te verenigen</span><span class="sxs-lookup"><span data-stu-id="ce509-132">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="ce509-133">Betere tracking en uitleg voor Score regressies</span><span class="sxs-lookup"><span data-stu-id="ce509-133">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="ce509-134">De acties voor verbetering filteren, markeren, zoeken en groeperen</span><span class="sxs-lookup"><span data-stu-id="ce509-134">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="ce509-135">Uw toekomstige doelen beheren met behulp van Score projecties en geplande acties</span><span class="sxs-lookup"><span data-stu-id="ce509-135">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="ce509-136">En nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="ce509-136">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="ce509-137">We horen graag van u</span><span class="sxs-lookup"><span data-stu-id="ce509-137">We want to hear from you</span></span>

<span data-ttu-id="ce509-138">Als u problemen ondervindt, kunt u het ons laten weten dat u de community [beveiliging, Privacy & naleving](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="ce509-138">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="ce509-139">We volgen de community en bieden hulp.</span><span class="sxs-lookup"><span data-stu-id="ce509-139">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="ce509-140">Verwante informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="ce509-140">Related resources</span></span>

- [<span data-ttu-id="ce509-141">Uw beveiligingspositie vaststellen</span><span class="sxs-lookup"><span data-stu-id="ce509-141">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="ce509-142">De geschiedenis van uw Microsoft Secure Score bijhouden en bereiken</span><span class="sxs-lookup"><span data-stu-id="ce509-142">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="ce509-143">Binnenkort beschikbaar</span><span class="sxs-lookup"><span data-stu-id="ce509-143">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
