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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541105"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="64df3-104">Wat komt er in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="64df3-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="64df3-105">Om van Microsoft Secure Score een betere vertegenwoordiger te maken van uw beveiligingshouding en de bruikbaarheid te verbeteren, brengen we in de nabije toekomst enkele wijzigingen door.</span><span class="sxs-lookup"><span data-stu-id="64df3-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="64df3-106">Je score en de hoogst mogelijke score veranderen.</span><span class="sxs-lookup"><span data-stu-id="64df3-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="64df3-107">Dit impliceert echter geen verandering in uw beveiligingshouding.</span><span class="sxs-lookup"><span data-stu-id="64df3-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="64df3-108">Zie Nieuwe wijzigingen in Microsoft Secure Score voor meer informatie over recente [wijzigingen?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="64df3-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="64df3-109">21 april 2020</span><span class="sxs-lookup"><span data-stu-id="64df3-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="64df3-110">Het verwijderen van verbeteringsacties die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van de beveiligingshouding bieden</span><span class="sxs-lookup"><span data-stu-id="64df3-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="64df3-111">Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.</span><span class="sxs-lookup"><span data-stu-id="64df3-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="64df3-112">IRM-beveiligingen toepassen op documenten</span><span class="sxs-lookup"><span data-stu-id="64df3-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="64df3-113">Beleid ter voorkoming van gegevensverlies toepassen</span><span class="sxs-lookup"><span data-stu-id="64df3-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="64df3-114">Azure AD-verbeteringsactie toevoegen in de voorbeeldversie</span><span class="sxs-lookup"><span data-stu-id="64df3-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="64df3-115">Geef gebruikers geen toestemming voor onbeheerde toepassingen (momenteel beschikbaar in een vrijgegeven versie)</span><span class="sxs-lookup"><span data-stu-id="64df3-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="64df3-116">Azure ATP-verbeteringsacties toevoegen in de preview-versie</span><span class="sxs-lookup"><span data-stu-id="64df3-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="64df3-117">Afdrukspoolerservice uitschakelen op domeincontrollers</span><span class="sxs-lookup"><span data-stu-id="64df3-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="64df3-118">Onveilige Kerberos-delegaties wijzigen om imitatie te voorkomen</span><span class="sxs-lookup"><span data-stu-id="64df3-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="64df3-119">Lokale beheerderswachtwoorden beveiligen en beheren met Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="64df3-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="64df3-120">Risico op zijwaarts e-bewegens bewegingspad voor gevoelige entiteiten verminderen</span><span class="sxs-lookup"><span data-stu-id="64df3-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="64df3-121">Slapende accounts verwijderen uit gevoelige groepen</span><span class="sxs-lookup"><span data-stu-id="64df3-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="64df3-122">Onveilige SID-geschiedeniskenmerken verwijderen uit entiteiten</span><span class="sxs-lookup"><span data-stu-id="64df3-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="64df3-123">Onveilige accountkenmerken oplossen</span><span class="sxs-lookup"><span data-stu-id="64df3-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="64df3-124">De belichting met wissen van tekstreferenties stoppen</span><span class="sxs-lookup"><span data-stu-id="64df3-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="64df3-125">Verouderde protocollen communicatie stoppen</span><span class="sxs-lookup"><span data-stu-id="64df3-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="64df3-126">Stop zwak versleutelingsgebruik</span><span class="sxs-lookup"><span data-stu-id="64df3-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="64df3-127">Ondersteuning voor beveiligingsaanbevelingen van Microsoft Defender ATP-& Vulnerability Management (TVM) in de preview-versie</span><span class="sxs-lookup"><span data-stu-id="64df3-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="64df3-128">Alle vrijgegeven beveiligingsaanbevelingen van TVM zijn nu ook beschikbaar in Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="64df3-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
