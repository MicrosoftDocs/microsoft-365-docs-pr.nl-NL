---
title: Voorwaardelijke toegang inschakelen om gebruikers, apparaten en gegevens beter te beveiligen
description: Schakel Voorwaardelijke toegang in om te voorkomen dat toepassingen worden uitgevoerd als een apparaat als risico wordt beschouwd en een toepassing niet compatibel is.
keywords: voorwaardelijke toegang, blokkeringstoepassingen, beveiligingsniveau, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166195"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="215f4-104">Voorwaardelijke toegang inschakelen om gebruikers, apparaten en gegevens beter te beveiligen</span><span class="sxs-lookup"><span data-stu-id="215f4-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="215f4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="215f4-105">**Applies to:**</span></span>
- [<span data-ttu-id="215f4-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="215f4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="215f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="215f4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="215f4-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="215f4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="215f4-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="215f4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="215f4-110">Voorwaardelijke toegang is een mogelijkheid waarmee u uw gebruikers en bedrijfsgegevens beter kunt beschermen door ervoor te zorgen dat alleen beveiligde apparaten toegang hebben tot toepassingen.</span><span class="sxs-lookup"><span data-stu-id="215f4-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="215f4-111">Met Voorwaardelijke toegang kunt u de toegang tot bedrijfsgegevens bepalen op basis van het risiconiveau van een apparaat.</span><span class="sxs-lookup"><span data-stu-id="215f4-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="215f4-112">Hiermee kunt u vertrouwde gebruikers op vertrouwde apparaten houden met behulp van vertrouwde toepassingen.</span><span class="sxs-lookup"><span data-stu-id="215f4-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="215f4-113">U kunt beveiligingsvoorwaarden definiëren waaronder apparaten en toepassingen gegevens vanuit uw netwerk kunnen uitvoeren en openen door beleidsregels uit te voeren om te voorkomen dat toepassingen worden uitgevoerd totdat een apparaat weer compatibel is.</span><span class="sxs-lookup"><span data-stu-id="215f4-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="215f4-114">De implementatie van Voorwaardelijke toegang in Defender voor Eindpunt is gebaseerd op microsoft Intune (Intune) beleid voor apparaat compliance en Azure Active Directory (Azure AD) beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="215f4-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="215f4-115">Het compliancebeleid wordt gebruikt met Voorwaardelijke toegang om alleen apparaten die voldoen aan een of meer regels voor apparaat compliancebeleid toegang te geven tot toepassingen.</span><span class="sxs-lookup"><span data-stu-id="215f4-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="215f4-116">De stroom Voorwaardelijke toegang begrijpen</span><span class="sxs-lookup"><span data-stu-id="215f4-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="215f4-117">Voorwaardelijke toegang wordt zo geïnstalleerd dat wanneer een bedreiging wordt gezien op een apparaat, de toegang tot gevoelige inhoud wordt geblokkeerd totdat de bedreiging wordt vereend.</span><span class="sxs-lookup"><span data-stu-id="215f4-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="215f4-118">De stroom begint met apparaten met een laag, gemiddeld of hoog risico.</span><span class="sxs-lookup"><span data-stu-id="215f4-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="215f4-119">Deze risicobepalingen worden vervolgens verzonden naar Intune.</span><span class="sxs-lookup"><span data-stu-id="215f4-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="215f4-120">Afhankelijk van hoe u beleid configureert in Intune, kan Voorwaardelijke toegang zo worden ingesteld dat wanneer aan bepaalde voorwaarden wordt voldaan, het beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="215f4-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="215f4-121">U kunt Intune bijvoorbeeld zo configureren dat Voorwaardelijke toegang wordt toegepast op apparaten met een hoog risico.</span><span class="sxs-lookup"><span data-stu-id="215f4-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="215f4-122">In Intune wordt een apparaat compliancebeleid gebruikt in combinatie met Azure AD Voorwaardelijke toegang om toegang tot toepassingen te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="215f4-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="215f4-123">Tegelijkertijd wordt een geautomatiseerd onderzoek en herstelproces gestart.</span><span class="sxs-lookup"><span data-stu-id="215f4-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="215f4-124">Een gebruiker kan het apparaat nog steeds gebruiken terwijl het geautomatiseerde onderzoek en herstel plaatsvindt, maar de toegang tot ondernemingsgegevens wordt geblokkeerd totdat de bedreiging volledig is hersteld.</span><span class="sxs-lookup"><span data-stu-id="215f4-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="215f4-125">Als u het risico op een apparaat wilt oplossen, moet u het apparaat terug naar een compatibele status.</span><span class="sxs-lookup"><span data-stu-id="215f4-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="215f4-126">Een apparaat keert terug naar een compatibele status wanneer er geen risico op wordt gezien.</span><span class="sxs-lookup"><span data-stu-id="215f4-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="215f4-127">Er zijn drie manieren om een risico aan te pakken:</span><span class="sxs-lookup"><span data-stu-id="215f4-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="215f4-128">Handmatige of geautomatiseerde herstelmaatregelen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="215f4-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="215f4-129">Actieve waarschuwingen op het apparaat oplossen.</span><span class="sxs-lookup"><span data-stu-id="215f4-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="215f4-130">Hierdoor wordt het risico van het apparaat verwijderd.</span><span class="sxs-lookup"><span data-stu-id="215f4-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="215f4-131">U kunt het apparaat verwijderen uit het actieve beleid en daarom wordt Voorwaardelijke toegang niet toegepast op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="215f4-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="215f4-132">Handmatig herstellen vereist een secops-beheerder om een waarschuwing te onderzoeken en het risico op het apparaat aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="215f4-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="215f4-133">De geautomatiseerde herstel wordt geconfigureerd via configuratie-instellingen in de volgende sectie [Voorwaardelijke toegang configureren.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="215f4-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="215f4-134">Wanneer het risico wordt verwijderd via handmatige of geautomatiseerde herstel, keert het apparaat terug naar een compatibele status en wordt toegang tot toepassingen verleend.</span><span class="sxs-lookup"><span data-stu-id="215f4-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="215f4-135">In de volgende voorbeeldreeks van gebeurtenissen wordt Voorwaardelijke toegang in actie uitgelegd:</span><span class="sxs-lookup"><span data-stu-id="215f4-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="215f4-136">Een gebruiker opent een schadelijk bestand en Defender voor Eindpunt markeert het apparaat als hoog risico.</span><span class="sxs-lookup"><span data-stu-id="215f4-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="215f4-137">De beoordeling van het hoge risico wordt doorgegeven aan Intune.</span><span class="sxs-lookup"><span data-stu-id="215f4-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="215f4-138">Tegelijkertijd wordt een geautomatiseerd onderzoek gestart om de geïdentificeerde bedreiging te herstellen.</span><span class="sxs-lookup"><span data-stu-id="215f4-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="215f4-139">Er kan ook handmatig worden gesaneerd om de geïdentificeerde bedreiging te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="215f4-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="215f4-140">Op basis van het beleid dat is gemaakt in Intune, wordt het apparaat gemarkeerd als niet compatibel.</span><span class="sxs-lookup"><span data-stu-id="215f4-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="215f4-141">De beoordeling wordt vervolgens door het Beleid voor voorwaardelijke toegang in Intune naar Azure AD gecommuniceerd.</span><span class="sxs-lookup"><span data-stu-id="215f4-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="215f4-142">In Azure AD wordt het bijbehorende beleid toegepast om toegang tot toepassingen te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="215f4-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="215f4-143">Het handmatige of geautomatiseerde onderzoek en herstel is voltooid en de bedreiging wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="215f4-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="215f4-144">Defender voor Eindpunt ziet dat er geen risico's zijn op het apparaat en in Intune wordt beoordeeld of het apparaat compatibel is.</span><span class="sxs-lookup"><span data-stu-id="215f4-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="215f4-145">Azure AD past het beleid toe dat toegang biedt tot toepassingen.</span><span class="sxs-lookup"><span data-stu-id="215f4-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="215f4-146">Gebruikers hebben nu toegang tot toepassingen.</span><span class="sxs-lookup"><span data-stu-id="215f4-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="215f4-147">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="215f4-147">Related topic</span></span>
- [<span data-ttu-id="215f4-148">Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="215f4-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
