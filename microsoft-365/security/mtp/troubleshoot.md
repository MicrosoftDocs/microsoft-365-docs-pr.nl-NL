---
title: Problemen met Microsoft 365 Defender-service oplossen
description: Oplossingen zoeken en de problemen met bekende Microsoft 365 Defender oplossen
keywords: problemen oplossen met Microsoft Threat Protection, problemen oplossen, Azure ATP, problemen, invoegtoepassing, pagina instellingen
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760456"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="13459-104">Problemen met Microsoft 365 Defender-service oplossen</span><span class="sxs-lookup"><span data-stu-id="13459-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="13459-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="13459-105">**Applies to:**</span></span>
- <span data-ttu-id="13459-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13459-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="13459-107">In deze sectie worden problemen beschreven die kunnen optreden wanneer u de Microsoft 365 Defender-service gebruikt.</span><span class="sxs-lookup"><span data-stu-id="13459-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="13459-108">Ik zie de inhoud van Microsoft 365 Defender niet</span><span class="sxs-lookup"><span data-stu-id="13459-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="13459-109">Als u de mogelijkheden van het navigatiedeelvenster, zoals het geval, het Onderhoudscentrum of de jacht niet ziet in de portal, moet u controleren of de Tenant de juiste licenties heeft.</span><span class="sxs-lookup"><span data-stu-id="13459-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="13459-110">Zie [vereisten](prerequisites.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="13459-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="13459-111">Microsoft Defender voor identiteits waarschuwingen worden niet weergegeven in de Microsoft 365 Defender-incidenten</span><span class="sxs-lookup"><span data-stu-id="13459-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="13459-112">Als Microsoft Defender voor de identiteit is geïmplementeerd in uw omgeving, maar als u in de Microsoft 365-versie van Microsoft 2010 niet werkt met de identiteits waarschuwingen, moet u ervoor zorgen dat de beveiligings-app voor Microsoft Cloud app en Defender voor identiteits integratie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="13459-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="13459-113">Zie [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/mdi-integration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="13459-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="13459-114">Waar is de pagina instellingen voor het inschakelen van de service?</span><span class="sxs-lookup"><span data-stu-id="13459-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="13459-115">Als u Microsoft 365 Defender wilt inschakelen, opent u de **instellingen** van het navigatiedeelvenster in het microsoft 365 Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="13459-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="13459-116">Dit navigatie-item is alleen zichtbaar als u beschikt over de [vereiste machtigingen en licenties](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="13459-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
