---
title: App-bewaking en -rapportage in het Microsoft 365-beveiligingscentrum
description: Beschrijft hoe u meer inzicht krijgen in het gebruik van cloud-apps in uw organisatie
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f7b3f2fcaac71eefa2579a0c3fd66666fe00f605
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811328"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="8668d-104">App-bewaking en -rapportage in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8668d-104">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="8668d-105">Deze rapporten geven meer inzicht in hoe cloud-apps in uw organisatie worden gebruikt, inclusief welke soorten apps, hun risiconiveau en waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="8668d-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="8668d-106">E-mailaccounts in gevaar houden</span><span class="sxs-lookup"><span data-stu-id="8668d-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="8668d-107">**E-mailbeveiliging** toont e-mailaccounts die risico lopen.</span><span class="sxs-lookup"><span data-stu-id="8668d-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="8668d-108">U op een account klikken om verder te onderzoeken in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="8668d-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![E-mailbeveiligingskaart](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="8668d-110">App-machtigingen controleren die door gebruikers zijn verleend</span><span class="sxs-lookup"><span data-stu-id="8668d-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="8668d-111">**Cloud App Security - OAuth-apps** bevatten apps die zijn ontdekt door Cloud App Security die door gebruikers zijn verleend.</span><span class="sxs-lookup"><span data-stu-id="8668d-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="8668d-112">De risicocatalogus van Cloud App Security bevat meer dan 16.000 apps die worden beoordeeld aan de hand van meer dan 70 risicofactoren.</span><span class="sxs-lookup"><span data-stu-id="8668d-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="8668d-113">De risicofactoren gaan van algemene informatie, zoals de uitgever van de app, tot beveiligingsmaatregelen en -besturingselementen, zoals of de app ondersteunt voor versleuteling in rust of een controlelogboek van gebruikersactiviteit biedt.</span><span class="sxs-lookup"><span data-stu-id="8668d-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![OAuth-appskaart voor cloud-app-beveiliging](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="8668d-115">Gebruikersaccounts van cloudapps controleren</span><span class="sxs-lookup"><span data-stu-id="8668d-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="8668d-116">**Cloud-app-accounts voor beoordeling** bevatten accounts die mogelijk aandacht nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="8668d-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud App-accounts voor beoordelingskaart](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="8668d-118">Begrijpen welke cloud-apps worden gebruikt</span><span class="sxs-lookup"><span data-stu-id="8668d-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="8668d-119">**Gedetecteerde cloud-apps (categorieën)** laten zien welke soorten apps in uw organisatie worden gebruikt en koppelingen naar het Cloud Discovery-dashboard in Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8668d-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="8668d-120">Zie [Snelstart: Werken met gedetecteerde apps](https://docs.microsoft.com/cloud-app-security/discovered-apps)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8668d-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Kaart voor categorieën van ontdekte cloud-apps](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="8668d-122">Controleren waar gebruikers toegang hebben tot cloud-apps</span><span class="sxs-lookup"><span data-stu-id="8668d-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="8668d-123">**Activiteitenlocaties** voor cloudapps geven aan waar gebruikers toegang hebben tot cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="8668d-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Kaart voor activiteitenlocaties cloud-apps](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="8668d-125">De status van infrastructuurworkloads controleren</span><span class="sxs-lookup"><span data-stu-id="8668d-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="8668d-126">**Infrastructuurstatus** toont statuswaarschuwingen voor infrastructuurworkloads in Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="8668d-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="8668d-127">Azure Security Center biedt uniform beveiligingsbeheer en geavanceerde bedreigingsbeveiliging voor on-premises en cloudworkloads.</span><span class="sxs-lookup"><span data-stu-id="8668d-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="8668d-128">U beveiligingsgegevens verzamelen, doorzoeken en analyseren uit verschillende bronnen, waaronder firewalls en andere partneroplossingen.</span><span class="sxs-lookup"><span data-stu-id="8668d-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="8668d-129">Zie [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8668d-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Infrastructuurgezondheidskaart](../../media/infrastructure-health.png)
