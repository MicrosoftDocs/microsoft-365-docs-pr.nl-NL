---
title: Clientgedragsblokkering
description: Clientgedragsblokkering maakt deel uit van de mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender ATP
keywords: behavior blocking, rapid protection, client behavior, Microsoft Defender ATP
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
ms.openlocfilehash: c37a1180f9def51daa4229418b05abe7cf787aa3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165259"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="22220-104">Clientgedragsblokkering</span><span class="sxs-lookup"><span data-stu-id="22220-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22220-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="22220-105">**Applies to:**</span></span>
- [<span data-ttu-id="22220-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="22220-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22220-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22220-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="22220-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="22220-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="22220-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="22220-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="22220-110">Overzicht</span><span class="sxs-lookup"><span data-stu-id="22220-110">Overview</span></span>

<span data-ttu-id="22220-111">Clientgedragsblokkering is een onderdeel van de mogelijkheden voor het blokkeren en [inperking](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) van gedrag in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="22220-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="22220-112">Aangezien verdacht gedrag wordt gedetecteerd op apparaten (ook wel clients of eindpunten genoemd), worden artefacten (zoals bestanden of toepassingen) automatisch geblokkeerd, gecontroleerd en gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="22220-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- en clientbeveiliging":::

<span data-ttu-id="22220-114">Antivirusbeveiliging werkt het beste in combinatie met cloudbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="22220-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="22220-115">Hoe clientgedragsblokkering werkt</span><span class="sxs-lookup"><span data-stu-id="22220-115">How client behavioral blocking works</span></span>

<span data-ttu-id="22220-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) kan verdacht gedrag, schadelijke code, bestandsloze en in-memory-aanvallen en meer detecteren op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="22220-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="22220-117">Wanneer verdacht gedrag wordt gedetecteerd, controleert en verzendt Microsoft Defender Antivirus deze verdachte gedragingen en hun procesbomen naar de cloudbeveiligingsservice.</span><span class="sxs-lookup"><span data-stu-id="22220-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="22220-118">Machine learning maakt binnen milliseconden onderscheid tussen schadelijke toepassingen en goed gedrag en classificeert elk artefact.</span><span class="sxs-lookup"><span data-stu-id="22220-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="22220-119">In bijna realtime, zodra een artefact schadelijk blijkt te zijn, wordt het geblokkeerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="22220-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="22220-120">Wanneer een verdacht gedrag wordt gedetecteerd, wordt er een [waarschuwing](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) gegenereerd en is deze zichtbaar in het Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="22220-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="22220-121">Clientgedragsblokkering is effectief omdat hiermee niet alleen wordt voorkomen dat een aanval wordt gestart, maar het kan ook helpen een aanval te stoppen die is begonnen met uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="22220-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="22220-122">En, met [het blokkeren van feedback-loop](feedback-loop-blocking.md) (een andere mogelijkheid voor het blokkeren en inperking van gedrag) worden aanvallen op andere apparaten in uw organisatie voorkomen.</span><span class="sxs-lookup"><span data-stu-id="22220-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="22220-123">Detecties op basis van gedrag</span><span class="sxs-lookup"><span data-stu-id="22220-123">Behavior-based detections</span></span>

<span data-ttu-id="22220-124">Op gedrag gebaseerde detecties worden benoemd op basis van de [MITRE ATT-&CK Matrix voor Enterprise.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="22220-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="22220-125">De naamgevingsconventie helpt bij het identificeren van de aanvalsfase waarin het schadelijke gedrag is waargenomen:</span><span class="sxs-lookup"><span data-stu-id="22220-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="22220-126">Tactiek</span><span class="sxs-lookup"><span data-stu-id="22220-126">Tactic</span></span> |   <span data-ttu-id="22220-127">Naam van detectiebedreiging</span><span class="sxs-lookup"><span data-stu-id="22220-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="22220-128">Eerste toegang</span><span class="sxs-lookup"><span data-stu-id="22220-128">Initial Access</span></span> | <span data-ttu-id="22220-129">Gedrag:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="22220-130">Uitvoering</span><span class="sxs-lookup"><span data-stu-id="22220-130">Execution</span></span>  | <span data-ttu-id="22220-131">Gedrag:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="22220-132">Persistentie</span><span class="sxs-lookup"><span data-stu-id="22220-132">Persistence</span></span>    | <span data-ttu-id="22220-133">Gedrag:Win32/Persistentie.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="22220-134">Escalatie van bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="22220-134">Privilege Escalation</span></span>   | <span data-ttu-id="22220-135">Gedrag:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="22220-136">Defense Ontwijking</span><span class="sxs-lookup"><span data-stu-id="22220-136">Defense Evasion</span></span>    | <span data-ttu-id="22220-137">Gedrag:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="22220-138">Referentietoegang</span><span class="sxs-lookup"><span data-stu-id="22220-138">Credential Access</span></span>  | <span data-ttu-id="22220-139">Gedrag:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="22220-140">Detectie</span><span class="sxs-lookup"><span data-stu-id="22220-140">Discovery</span></span>  | <span data-ttu-id="22220-141">Gedrag:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="22220-142">Zijbeweging</span><span class="sxs-lookup"><span data-stu-id="22220-142">Lateral Movement</span></span> | <span data-ttu-id="22220-143">Gedrag:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="22220-144">Verzameling</span><span class="sxs-lookup"><span data-stu-id="22220-144">Collection</span></span> |   <span data-ttu-id="22220-145">Gedrag:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="22220-146">Command and Control</span><span class="sxs-lookup"><span data-stu-id="22220-146">Command and Control</span></span> | <span data-ttu-id="22220-147">Gedrag:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="22220-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="22220-148">Exfiltration</span></span>   | <span data-ttu-id="22220-149">Gedrag:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="22220-150">Gevolg</span><span class="sxs-lookup"><span data-stu-id="22220-150">Impact</span></span> | <span data-ttu-id="22220-151">Gedrag:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="22220-152">Niet-gecategoriseerd</span><span class="sxs-lookup"><span data-stu-id="22220-152">Uncategorized</span></span>  | <span data-ttu-id="22220-153">Gedrag:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="22220-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="22220-154">Zie recente wereldwijde bedreigingsactiviteit voor meer informatie **[over specifieke bedreigingen.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="22220-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="22220-155">Clientgedragsblokkering configureren</span><span class="sxs-lookup"><span data-stu-id="22220-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="22220-156">Als uw organisatie Defender voor Eindpunt gebruikt, is clientgedragsblokkering standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="22220-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="22220-157">Zorg er echter voor dat de volgende [](behavioral-blocking-containment.md)functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd om te profiteren van alle Mogelijkheden van Defender voor eindpunten, inclusief het blokkeren en inperking van gedragingen:</span><span class="sxs-lookup"><span data-stu-id="22220-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="22220-158">Defender voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="22220-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="22220-159">Apparaten die zijn aan boord van Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="22220-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="22220-160">EDR in blokmodus</span><span class="sxs-lookup"><span data-stu-id="22220-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="22220-161">Surface-beperking voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="22220-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="22220-162">[Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="22220-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="22220-163">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="22220-163">Related articles</span></span>

- [<span data-ttu-id="22220-164">Gedrag blokkeren en insluiting</span><span class="sxs-lookup"><span data-stu-id="22220-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="22220-165">Feedback-lus blokkeren</span><span class="sxs-lookup"><span data-stu-id="22220-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="22220-166">(Blog) Blokkering en insluiting van gedrag: optica transformeren in beveiliging</span><span class="sxs-lookup"><span data-stu-id="22220-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="22220-167">Nuttige Defender voor eindpuntresources</span><span class="sxs-lookup"><span data-stu-id="22220-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
