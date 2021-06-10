---
title: Feedbacklus blokkeren
description: Het blokkeren van feedbackluss, ook wel snelle beveiliging genoemd, maakt deel uit van de mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender voor Eindpunt
keywords: gedrag blokkeren, snelle beveiliging, feedback blokkeren, Microsoft Defender voor eindpunt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842456"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="eb037-104">Feedbacklus blokkeren</span><span class="sxs-lookup"><span data-stu-id="eb037-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eb037-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="eb037-105">**Applies to:**</span></span>
- [<span data-ttu-id="eb037-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="eb037-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="eb037-107">Overzicht</span><span class="sxs-lookup"><span data-stu-id="eb037-107">Overview</span></span>

<span data-ttu-id="eb037-108">Het blokkeren van feedbackluss, ook wel snelle beveiliging genoemd, is een onderdeel van de mogelijkheden voor het blokkeren en inperking van gedrag [in](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) Microsoft Defender [voor Eindpunt.](/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="eb037-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="eb037-109">Met het blokkeren van feedbacklus zijn apparaten in uw organisatie beter beveiligd tegen aanvallen.</span><span class="sxs-lookup"><span data-stu-id="eb037-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="eb037-110">Hoe het blokkeren van feedback-loop werkt</span><span class="sxs-lookup"><span data-stu-id="eb037-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="eb037-111">Wanneer een verdacht gedrag of bestand wordt gedetecteerd, zoals door [Microsoft Defender Antivirus,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)wordt informatie over dat artefact naar meerdere classificaties verzonden.</span><span class="sxs-lookup"><span data-stu-id="eb037-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="eb037-112">De engine snelle beveiligingslus controleert en correleert de informatie met andere signalen om tot een beslissing te komen over het blokkeren van een bestand.</span><span class="sxs-lookup"><span data-stu-id="eb037-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="eb037-113">Het controleren en classificeren van artefacten gebeurt snel.</span><span class="sxs-lookup"><span data-stu-id="eb037-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="eb037-114">Dit resulteert in een snelle blokkering van bevestigd malware en biedt bescherming in het hele ecosysteem.</span><span class="sxs-lookup"><span data-stu-id="eb037-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="eb037-115">Met snelle beveiliging kan een aanval worden gestopt op een apparaat, andere apparaten in de organisatie en apparaten in andere organisaties, omdat een aanval probeert de voet aan de grond te krijgen.</span><span class="sxs-lookup"><span data-stu-id="eb037-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="eb037-116">Feedbackloop blokkeren configureren</span><span class="sxs-lookup"><span data-stu-id="eb037-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="eb037-117">Als uw organisatie Defender voor Eindpunt gebruikt, is het blokkeren van feedbacklussen standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="eb037-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="eb037-118">Snelle beveiliging vindt echter plaats door een combinatie van De mogelijkheden van Defender voor eindpunten, functies voor machine learning-beveiliging en signaal delen in microsoft-beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="eb037-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="eb037-119">Zorg ervoor dat de volgende functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="eb037-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="eb037-120">Basislijnen van Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="eb037-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="eb037-121">Apparaten die zijn aan boord van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="eb037-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="eb037-122">EDR in blokkeringsmodus</span><span class="sxs-lookup"><span data-stu-id="eb037-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="eb037-123">Kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="eb037-123">Attack surface reduction</span></span>](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="eb037-124">[Beveiliging van de volgende generatie](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="eb037-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="eb037-125">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="eb037-125">Related articles</span></span>

- [<span data-ttu-id="eb037-126">Gedragsblokkering en -insluiting</span><span class="sxs-lookup"><span data-stu-id="eb037-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="eb037-127">(Blog) Blokkering en insluiting van gedrag: optica transformeren in beveiliging</span><span class="sxs-lookup"><span data-stu-id="eb037-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="eb037-128">Nuttige Microsoft Defender voor eindpuntbronnen</span><span class="sxs-lookup"><span data-stu-id="eb037-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
