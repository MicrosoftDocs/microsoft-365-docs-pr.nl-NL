---
title: Problemen met de Microsoft 365 Defender-service oplossen
description: Oplossingen zoeken en een oplossing zoeken voor bekende Problemen met Microsoft 365 Defender
keywords: Microsoft Threat Protection oplossen, problemen oplossen, Azure ATP, problemen, invoegoplossing, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918664"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="c4db0-104">Problemen met de Microsoft 365 Defender-service oplossen</span><span class="sxs-lookup"><span data-stu-id="c4db0-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c4db0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c4db0-105">**Applies to:**</span></span>
- <span data-ttu-id="c4db0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4db0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c4db0-107">In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft 365 Defender-service gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c4db0-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="c4db0-108">Ik zie geen Microsoft 365 Defender-inhoud</span><span class="sxs-lookup"><span data-stu-id="c4db0-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="c4db0-109">Als u geen mogelijkheden ziet in het navigatiedeelvenster, zoals incidenten, actiecentrum of Jagen in uw portal, moet u controleren of uw tenant over de juiste licenties beschikt.</span><span class="sxs-lookup"><span data-stu-id="c4db0-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="c4db0-110">Zie Vereisten voor [meer informatie.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="c4db0-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="c4db0-111">Microsoft Defender voor identiteitswaarschuwingen worden niet weergegeven in de Microsoft 365 Defender-incidenten</span><span class="sxs-lookup"><span data-stu-id="c4db0-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="c4db0-112">Als Microsoft Defender voor identiteit is geïmplementeerd in uw omgeving, maar u geen defender voor identiteitswaarschuwingen ziet als onderdeel van Microsoft 365 Defender-incidenten, moet u ervoor zorgen dat de Microsoft Cloud App Security en Defender voor identiteitsintegratie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c4db0-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="c4db0-113">Zie Microsoft [Defender voor identiteitsintegratie](/cloud-app-security/mdi-integration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4db0-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="c4db0-114">Waar is de pagina met instellingen voor het in- en uitschakelen van de service?</span><span class="sxs-lookup"><span data-stu-id="c4db0-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="c4db0-115">Als u Microsoft 365 Defender wilt in- of uitschakelen, hebt u toegang tot Instellingen **vanuit** het navigatiedeelvenster in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c4db0-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="c4db0-116">Dit navigatie-item is alleen zichtbaar als u de vereiste [machtigingen en licenties hebt.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="c4db0-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>