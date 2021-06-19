---
title: Problemen Microsoft 365 Defender service oplossen
description: Oplossingen en tijdelijke oplossingen zoeken voor bekende Microsoft 365 Defender problemen
keywords: problemen Microsoft 365 Defender, probleemoplossing, Microsoft Defender voor identiteit, problemen, invoegvoegoplossing, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 14033ffeb3d08efad7f45eb4c319ac0401b7df09
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028451"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="c0e0e-104">Problemen Microsoft 365 Defender service oplossen</span><span class="sxs-lookup"><span data-stu-id="c0e0e-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c0e0e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c0e0e-105">**Applies to:**</span></span>
- <span data-ttu-id="c0e0e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0e0e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c0e0e-107">In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft 365 Defender gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="c0e0e-108">Ik zie geen Microsoft 365 Defender inhoud</span><span class="sxs-lookup"><span data-stu-id="c0e0e-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="c0e0e-109">Als u geen mogelijkheden ziet in het navigatiedeelvenster, zoals incidenten, actiecentrum of Jagen in uw portal, moet u controleren of uw tenant over de juiste licenties beschikt.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="c0e0e-110">Zie Vereisten voor [meer informatie.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="c0e0e-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="c0e0e-111">Microsoft Defender voor identiteitswaarschuwingen worden niet weergegeven in de Microsoft 365 Defender incidenten</span><span class="sxs-lookup"><span data-stu-id="c0e0e-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="c0e0e-112">Als Microsoft Defender voor identiteit is geïmplementeerd in uw omgeving, maar u geen meldingen van Defender voor identiteit ziet als onderdeel van Microsoft 365 Defender-incidenten, moet u ervoor zorgen dat de integratie van Microsoft Cloud App Security en Defender voor identiteit is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="c0e0e-113">Zie Microsoft [Defender voor identiteitsintegratie](/cloud-app-security/mdi-integration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="c0e0e-114">Waar is de pagina met instellingen voor het in- en uitschakelen van de service?</span><span class="sxs-lookup"><span data-stu-id="c0e0e-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="c0e0e-115">Als u Microsoft 365 Defender wilt in- of uitschakelen, **Instellingen** het navigatiedeelvenster in het Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="c0e0e-116">Dit navigatie-item is alleen zichtbaar als u de vereiste [machtigingen en licenties hebt.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="c0e0e-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="c0e0e-117">Hoe maak ik een uitzondering voor mijn bestand/URL?</span><span class="sxs-lookup"><span data-stu-id="c0e0e-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="c0e0e-118">Een fout-positief is een bestand of URL dat wordt gedetecteerd als schadelijk, maar geen bedreiging is.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="c0e0e-119">U kunt indicatoren maken en uitsluitingen definiëren om bepaalde bestanden/URL's te deblokkeren en toe te staan.</span><span class="sxs-lookup"><span data-stu-id="c0e0e-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="c0e0e-120">Zie [Fout-positieve/negatieven adresseert in Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span><span class="sxs-lookup"><span data-stu-id="c0e0e-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


