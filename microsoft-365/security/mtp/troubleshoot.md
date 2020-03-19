---
title: Problemen met de service voor bedreigingsbeveiliging van Microsoft oplossen
description: Oplossingen en oplossingen vinden voor bekende problemen met microsoft-bedreigingenbescherming
keywords: problemen met Microsoft Threat Protection, problemen oplossen, Azure ATP, problemen, add-on, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "42809535"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="ca646-104">Problemen met de service voor bedreigingsbeveiliging van Microsoft oplossen</span><span class="sxs-lookup"><span data-stu-id="ca646-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="ca646-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ca646-105">**Applies to:**</span></span>
- <span data-ttu-id="ca646-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="ca646-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ca646-107">In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft Threat Protection-service gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ca646-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="ca646-108">Ik zie geen inhoud voor Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ca646-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="ca646-109">Als u geen mogelijkheden ziet in het navigatiedeelvenster, zoals het incidenten, actiecentrum of jagen in uw portal, moet u controleren of uw tenant over de juiste licenties beschikt.</span><span class="sxs-lookup"><span data-stu-id="ca646-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="ca646-110">Zie [Vereisten](prerequisites.md)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="ca646-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="ca646-111">Azure ATP-waarschuwingen worden niet weergegeven in de microsoft-incidenten voor bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="ca646-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="ca646-112">Als Azure ATP is geïmplementeerd in uw omgeving, maar u Azure ATP-waarschuwingen niet ziet als onderdeel van microsoft-incidenten voor bedreigingsbeveiliging, moet u ervoor zorgen dat de Microsoft Cloud App Security en Azure ATP-integratie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ca646-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="ca646-113">Zie [Azure ATP-integratie](https://docs.microsoft.com/cloud-app-security/aatp-integration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ca646-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="ca646-114">Is Microsoft Threat Protection beschikbaar voor GCC (Us Government Community Cloud) of GCC High?</span><span class="sxs-lookup"><span data-stu-id="ca646-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="ca646-115">Op dit moment is het niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ca646-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="ca646-116">Waar is de instellingenpagina voor het inschakelen van de service?</span><span class="sxs-lookup"><span data-stu-id="ca646-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="ca646-117">Als u Microsoft Threat Protection wilt inschakelen, krijgt u toegang tot **instellingen** via het navigatiedeelvenster in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ca646-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="ca646-118">Dit navigatie-item is alleen zichtbaar als u de [vereiste machtigingen en licenties](mtp-enable.md#check-license-eligibility-and-required-permissions)hebt.</span><span class="sxs-lookup"><span data-stu-id="ca646-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="ca646-119">Kan ik een add-on gebruiken in plaats van de vereiste E5-licenties?</span><span class="sxs-lookup"><span data-stu-id="ca646-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="ca646-120">Er zijn momenteel geen add-ons voor Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ca646-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="ca646-121">Zie licentievereisten</span><span class="sxs-lookup"><span data-stu-id="ca646-121">See licensing requirements</span></span>](prerequisites.md) 

