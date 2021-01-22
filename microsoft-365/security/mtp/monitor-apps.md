---
title: App-controle & rapportage - Beveiligingscentrum
description: Lees hoe u meer inzicht kunt krijgen in het gebruik van de cloud-app in uw organisatie. Omvat verschillende soorten apps, hun risiconiveau en waarschuwingen.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, apps
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930520"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="15700-105">App-controle en -rapportage in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="15700-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15700-106">Deze rapporten bieden meer inzicht in hoe cloud-apps worden gebruikt in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="15700-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="15700-107">Omvat verschillende soorten apps, hun risiconiveau en waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="15700-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="15700-108">Risico's van e-mailaccounts controleren</span><span class="sxs-lookup"><span data-stu-id="15700-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="15700-109">**E-mailbeveiliging** toont risicovolle e-mailaccounts.</span><span class="sxs-lookup"><span data-stu-id="15700-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="15700-110">U kunt een account selecteren om nader te onderzoeken in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="15700-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Kaart voor e-mailbeveiliging](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="15700-112">App-machtigingen controleren die door gebruikers zijn verleend</span><span class="sxs-lookup"><span data-stu-id="15700-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="15700-113">**Cloud-appbeveiliging: OAuth-apps** geven apps weer die door Cloud App-beveiliging zijn ontdekt en die machtigingen van gebruikers hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="15700-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="15700-114">De risicocatalogus van Cloud App Security bevat meer dan 16.000 apps die worden geëvalueerd op basis van meer dan 70 risicofactoren.</span><span class="sxs-lookup"><span data-stu-id="15700-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="15700-115">De risicofactoren beginnen met algemene informatie, zoals de uitgever van de app.</span><span class="sxs-lookup"><span data-stu-id="15700-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="15700-116">Vervolgens worden beveiligingsmaatregelen en -besturingselementen gebruikt, bijvoorbeeld of de app in rust versleuteling ondersteunt of een auditlogboek van gebruikersactiviteit geeft.</span><span class="sxs-lookup"><span data-stu-id="15700-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Kaart met OAuth-apps voor cloud-appbeveiliging](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="15700-118">Gebruikersaccounts voor de cloud-app controleren</span><span class="sxs-lookup"><span data-stu-id="15700-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="15700-119">**Cloud-app-accounts voor het controleren** van accounts die mogelijk aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="15700-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud-app-accounts voor revisiekaart](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="15700-121">Begrijpen welke cloud-apps worden gebruikt</span><span class="sxs-lookup"><span data-stu-id="15700-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="15700-122">**Gevonden cloud-apps (categorieën)** laten zien welke soorten apps in uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="15700-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="15700-123">Het is een koppeling naar het Cloud Discovery-dashboard in Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="15700-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="15700-124">Zie [Quickstart: Werken](https://docs.microsoft.com/cloud-app-security/discovered-apps)met gevonden apps voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="15700-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Kaart voor categorieën van cloud-apps gevonden](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="15700-126">Controleren waar gebruikers toegang hebben tot cloud-apps</span><span class="sxs-lookup"><span data-stu-id="15700-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="15700-127">**Locaties van activiteit in cloud-apps** geven aan waar gebruikers toegang hebben tot cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="15700-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Kaart met activiteitslocaties in cloud-app](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="15700-129">Status controleren op werkbelasting van infrastructuur</span><span class="sxs-lookup"><span data-stu-id="15700-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="15700-130">**De infrastructuurstatus** toont statuswaarschuwingen voor infrastructuurwerkbelastingen in Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="15700-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="15700-131">Azure Defender biedt geïntegreerde beveiligingsbeheer en Defender voor Office 365 voor on-premises en cloud-workloads.</span><span class="sxs-lookup"><span data-stu-id="15700-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="15700-132">U kunt beveiligingsgegevens uit verschillende bronnen verzamelen, doorzoeken en analyseren, waaronder firewalls en andere partneroplossingen.</span><span class="sxs-lookup"><span data-stu-id="15700-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="15700-133">Zie de documentatie bij [Azure Defender voor meer informatie.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="15700-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Infrastructuur statuskaart](../../media/infrastructure-health.png)
