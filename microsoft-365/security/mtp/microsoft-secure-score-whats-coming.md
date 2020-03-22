---
title: Wat komt er in Microsoft Secure Score?
description: Beschrijft de Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteringsacties
ms.prod: microsoft-365-enterprise
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
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895439"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="8ea43-104">Wat komt er in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="8ea43-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="8ea43-105">Om van Microsoft Secure Score een betere vertegenwoordiger te maken van uw beveiligingshouding en de bruikbaarheid te verbeteren, brengen we in de nabije toekomst enkele wijzigingen door.</span><span class="sxs-lookup"><span data-stu-id="8ea43-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="8ea43-106">Je score en de hoogst mogelijke score veranderen.</span><span class="sxs-lookup"><span data-stu-id="8ea43-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="8ea43-107">Dit impliceert echter geen verandering in uw beveiligingshouding.</span><span class="sxs-lookup"><span data-stu-id="8ea43-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="8ea43-108">Zie Nieuwe wijzigingen in Microsoft Secure Score voor meer informatie over recente [wijzigingen?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="8ea43-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="8ea43-109">21 april 2020</span><span class="sxs-lookup"><span data-stu-id="8ea43-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="8ea43-110">Het verwijderen van verbeteringsacties die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van de beveiligingshouding bieden</span><span class="sxs-lookup"><span data-stu-id="8ea43-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="8ea43-111">Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.</span><span class="sxs-lookup"><span data-stu-id="8ea43-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8ea43-112">Accounts verwijderen/blokkeren die in de afgelopen 30 dagen niet zijn gebruikt</span><span class="sxs-lookup"><span data-stu-id="8ea43-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="8ea43-113">Minder dan 5 globale beheerders aanwijzen</span><span class="sxs-lookup"><span data-stu-id="8ea43-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="8ea43-114">IRM-beveiligingen toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="8ea43-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="8ea43-115">Beleid ter voorkoming van gegevensverlies toepassen</span><span class="sxs-lookup"><span data-stu-id="8ea43-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="8ea43-116">Extra besturingselementondersteuning toevoegen in de voorbeeldversie</span><span class="sxs-lookup"><span data-stu-id="8ea43-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="8ea43-117">Geef gebruikers geen toestemming voor onbeheerde toepassingen (momenteel beschikbaar in een vrijgegeven versie)</span><span class="sxs-lookup"><span data-stu-id="8ea43-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="8ea43-118">Ondersteuning voor aanvullende verbeteringen voor microsoft cloud-appbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8ea43-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="8ea43-119">Afdrukspoolerservice uitschakelen op domeincontrollers</span><span class="sxs-lookup"><span data-stu-id="8ea43-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="8ea43-120">Onveilige Kerberos-delegaties wijzigen om imitatie te voorkomen</span><span class="sxs-lookup"><span data-stu-id="8ea43-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="8ea43-121">Lokale beheerderswachtwoorden beveiligen en beheren met Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="8ea43-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="8ea43-122">Risico op zijwaarts e-bewegens bewegingspad voor gevoelige entiteiten verminderen</span><span class="sxs-lookup"><span data-stu-id="8ea43-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="8ea43-123">Slapende accounts verwijderen uit gevoelige groepen</span><span class="sxs-lookup"><span data-stu-id="8ea43-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="8ea43-124">Onveilige SID-geschiedeniskenmerken verwijderen uit entiteiten</span><span class="sxs-lookup"><span data-stu-id="8ea43-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="8ea43-125">Onveilige accountkenmerken oplossen</span><span class="sxs-lookup"><span data-stu-id="8ea43-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="8ea43-126">De belichting met wissen van tekstreferenties stoppen</span><span class="sxs-lookup"><span data-stu-id="8ea43-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="8ea43-127">Verouderde protocollen communicatie stoppen</span><span class="sxs-lookup"><span data-stu-id="8ea43-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="8ea43-128">Stop zwak versleutelingsgebruik</span><span class="sxs-lookup"><span data-stu-id="8ea43-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="8ea43-129">Ondersteuning voor beveiligingsaanbevelingen voor Microsoft Defender ATP Threat & Vulnerability Management (TVM)</span><span class="sxs-lookup"><span data-stu-id="8ea43-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="8ea43-130">Alle vrijgegeven beveiligingsaanbevelingen van TVM zijn nu ook beschikbaar in Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="8ea43-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
