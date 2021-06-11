---
title: Gedragsblokkering van cliënt
description: Clientgedragsblokkering maakt deel uit van de mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender voor eindpunt
keywords: behavior blocking, rapid protection, client behavior, Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: fcf2310929937d1dacfc9c101d3e14414bad262b
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903742"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="43933-104">Gedragsblokkering van cliënt</span><span class="sxs-lookup"><span data-stu-id="43933-104">Client behavioral blocking</span></span>

<span data-ttu-id="43933-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="43933-105">**Applies to:**</span></span>
- [<span data-ttu-id="43933-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="43933-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43933-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43933-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="43933-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="43933-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="43933-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="43933-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="43933-110">Overzicht</span><span class="sxs-lookup"><span data-stu-id="43933-110">Overview</span></span>

<span data-ttu-id="43933-111">Clientgedragsblokkering is een onderdeel van de mogelijkheden voor het blokkeren en [inperking](behavioral-blocking-containment.md) van gedrag in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="43933-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="43933-112">Aangezien verdacht gedrag wordt gedetecteerd op apparaten (ook wel clients of eindpunten genoemd), worden artefacten (zoals bestanden of toepassingen) automatisch geblokkeerd, gecontroleerd en gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="43933-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- en clientbeveiliging":::

<span data-ttu-id="43933-114">Antivirusbeveiliging werkt het beste in combinatie met cloudbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="43933-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="43933-115">Hoe clientgedragsblokkering werkt</span><span class="sxs-lookup"><span data-stu-id="43933-115">How client behavioral blocking works</span></span>

<span data-ttu-id="43933-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) kan verdacht gedrag, schadelijke code, bestandsloze en in-memory-aanvallen en meer detecteren op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="43933-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="43933-117">Wanneer verdacht gedrag wordt gedetecteerd, Microsoft Defender Antivirus en verzendt u die verdachte gedragingen en hun procesbomen naar de cloudbeveiligingsservice.</span><span class="sxs-lookup"><span data-stu-id="43933-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="43933-118">Machine learning maakt binnen milliseconden onderscheid tussen schadelijke toepassingen en goed gedrag en classificeert elk artefact.</span><span class="sxs-lookup"><span data-stu-id="43933-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="43933-119">In bijna realtime, zodra een artefact schadelijk blijkt te zijn, wordt het geblokkeerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="43933-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="43933-120">Wanneer een verdacht gedrag wordt gedetecteerd, wordt er een [waarschuwing](alerts-queue.md) gegenereerd en is deze zichtbaar in [Microsoft 365 Defender](microsoft-defender-security-center.md) (voorheen de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )).</span><span class="sxs-lookup"><span data-stu-id="43933-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in [Microsoft 365 Defender](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))).</span></span>

<span data-ttu-id="43933-121">Clientgedragsblokkering is effectief omdat hiermee niet alleen wordt voorkomen dat een aanval wordt gestart, maar het kan ook helpen een aanval te stoppen die is begonnen met uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="43933-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="43933-122">En, met [het blokkeren van feedback-loop](feedback-loop-blocking.md) (een andere mogelijkheid voor het blokkeren en inperking van gedrag) worden aanvallen op andere apparaten in uw organisatie voorkomen.</span><span class="sxs-lookup"><span data-stu-id="43933-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="43933-123">Detecties op basis van gedrag</span><span class="sxs-lookup"><span data-stu-id="43933-123">Behavior-based detections</span></span>

<span data-ttu-id="43933-124">Op gedrag gebaseerde detecties worden benoemd op basis van de [MITRE ATT-&CK Matrix voor Enterprise.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="43933-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="43933-125">De naamgevingsconventie helpt bij het identificeren van de aanvalsfase waarin het schadelijke gedrag is waargenomen:</span><span class="sxs-lookup"><span data-stu-id="43933-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="43933-126">Tactiek</span><span class="sxs-lookup"><span data-stu-id="43933-126">Tactic</span></span> |   <span data-ttu-id="43933-127">Naam van detectiebedreiging</span><span class="sxs-lookup"><span data-stu-id="43933-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="43933-128">Eerste toegang</span><span class="sxs-lookup"><span data-stu-id="43933-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="43933-129">Uitvoering</span><span class="sxs-lookup"><span data-stu-id="43933-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="43933-130">Persistentie</span><span class="sxs-lookup"><span data-stu-id="43933-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="43933-131">Escalatie van bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="43933-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="43933-132">Defense Ontwijking</span><span class="sxs-lookup"><span data-stu-id="43933-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="43933-133">Referentietoegang</span><span class="sxs-lookup"><span data-stu-id="43933-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="43933-134">Detectie</span><span class="sxs-lookup"><span data-stu-id="43933-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="43933-135">Zijbeweging</span><span class="sxs-lookup"><span data-stu-id="43933-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="43933-136">Verzameling</span><span class="sxs-lookup"><span data-stu-id="43933-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="43933-137">Command and Control</span><span class="sxs-lookup"><span data-stu-id="43933-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="43933-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="43933-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="43933-139">Gevolg</span><span class="sxs-lookup"><span data-stu-id="43933-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="43933-140">Niet-gecategoriseerd</span><span class="sxs-lookup"><span data-stu-id="43933-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="43933-141">Zie recente wereldwijde bedreigingsactiviteit voor meer informatie **[over specifieke bedreigingen.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="43933-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="43933-142">Clientgedragsblokkering configureren</span><span class="sxs-lookup"><span data-stu-id="43933-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="43933-143">Als uw organisatie Defender voor Eindpunt gebruikt, is clientgedragsblokkering standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="43933-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="43933-144">Zorg er echter voor dat de volgende [](behavioral-blocking-containment.md)functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd om te profiteren van alle Mogelijkheden van Defender voor eindpunten, inclusief het blokkeren en inperking van gedragingen:</span><span class="sxs-lookup"><span data-stu-id="43933-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="43933-145">Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="43933-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="43933-146">Apparaten die zijn aan boord van Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="43933-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="43933-147">EDR in blokkeringsmodus</span><span class="sxs-lookup"><span data-stu-id="43933-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="43933-148">Kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="43933-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="43933-149">[Beveiliging van de volgende generatie](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware en andere mogelijkheden voor bedreigingsbeveiliging)</span><span class="sxs-lookup"><span data-stu-id="43933-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

