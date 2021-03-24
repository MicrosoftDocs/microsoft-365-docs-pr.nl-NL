---
title: Feedback-lus blokkeren
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
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060549"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="f1fd4-104">Feedback-lus blokkeren</span><span class="sxs-lookup"><span data-stu-id="f1fd4-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f1fd4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f1fd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1fd4-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1fd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="f1fd4-107">Overzicht</span><span class="sxs-lookup"><span data-stu-id="f1fd4-107">Overview</span></span>

<span data-ttu-id="f1fd4-108">Het blokkeren van feedbackluss, ook wel snelle beveiliging genoemd, is een onderdeel van de mogelijkheden voor het blokkeren en inperking van gedrag [in](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) Microsoft Defender [voor Eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="f1fd4-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span></span> <span data-ttu-id="f1fd4-109">Met het blokkeren van feedbacklus zijn apparaten in uw organisatie beter beveiligd tegen aanvallen.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="f1fd4-110">Hoe het blokkeren van feedback-loop werkt</span><span class="sxs-lookup"><span data-stu-id="f1fd4-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="f1fd4-111">Wanneer een verdacht gedrag of bestand wordt gedetecteerd, zoals door [Microsoft Defender Antivirus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)wordt informatie over dat artefact naar meerdere classificaties verzonden.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="f1fd4-112">De engine snelle beveiligingslus controleert en correleert de informatie met andere signalen om tot een beslissing te komen over het blokkeren van een bestand.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="f1fd4-113">Het controleren en classificeren van artefacten gebeurt snel.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="f1fd4-114">Dit resulteert in een snelle blokkering van bevestigd malware en biedt bescherming in het hele ecosysteem.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="f1fd4-115">Met snelle beveiliging kan een aanval worden gestopt op een apparaat, andere apparaten in de organisatie en apparaten in andere organisaties, omdat een aanval probeert de voet aan de grond te krijgen.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="f1fd4-116">Feedbackloop blokkeren configureren</span><span class="sxs-lookup"><span data-stu-id="f1fd4-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="f1fd4-117">Als uw organisatie Defender voor Eindpunt gebruikt, is het blokkeren van feedbacklussen standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="f1fd4-118">Snelle beveiliging vindt echter plaats door een combinatie van De mogelijkheden van Defender voor eindpunten, functies voor machine learning-beveiliging en signaal delen in microsoft-beveiligingsservices.</span><span class="sxs-lookup"><span data-stu-id="f1fd4-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="f1fd4-119">Zorg ervoor dat de volgende functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="f1fd4-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="f1fd4-120">Basislijnen van Microsoft Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="f1fd4-120">Microsoft Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="f1fd4-121">Apparaten die zijn aan boord van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f1fd4-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="f1fd4-122">EDR in blokmodus</span><span class="sxs-lookup"><span data-stu-id="f1fd4-122">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="f1fd4-123">Surface-beperking voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="f1fd4-123">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="f1fd4-124">[Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="f1fd4-124">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="f1fd4-125">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f1fd4-125">Related articles</span></span>

- [<span data-ttu-id="f1fd4-126">Gedrag blokkeren en insluiting</span><span class="sxs-lookup"><span data-stu-id="f1fd4-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="f1fd4-127">(Blog) Blokkering en insluiting van gedrag: optica transformeren in beveiliging</span><span class="sxs-lookup"><span data-stu-id="f1fd4-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="f1fd4-128">Nuttige Microsoft Defender voor eindpuntbronnen</span><span class="sxs-lookup"><span data-stu-id="f1fd4-128">Helpful Microsoft Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
