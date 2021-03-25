---
title: Controleer of uw apparaten correct zijn geconfigureerd
description: Configureer apparaten op de juiste manier om de algehele tolerantie tegen bedreigingen te verbeteren en uw mogelijkheden voor het detecteren en beantwoorden van aanvallen te verbeteren.
keywords: onboard, Intune management, MDATP, WDATP, Microsoft Defender, Windows Defender, advanced threat protection, attack surface reduction, ASR, security baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163361"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="eb7b3-104">Controleer of uw apparaten correct zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="eb7b3-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eb7b3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="eb7b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="eb7b3-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb7b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eb7b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb7b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="eb7b3-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="eb7b3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eb7b3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="eb7b3-110">Met goed geconfigureerde apparaten kunt u de algehele tolerantie tegen bedreigingen vergroten en uw vermogen verbeteren om aanvallen te detecteren en te beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="eb7b3-111">Beveiligingsconfiguratiebeheer zorgt ervoor dat uw apparaten:</span><span class="sxs-lookup"><span data-stu-id="eb7b3-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="eb7b3-112">Onboard to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb7b3-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="eb7b3-113">Voldoen aan of overschrijden van de beveiligingslijnconfiguratie van Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb7b3-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="eb7b3-114">Strategische risicobeperking op het oppervlak van de aanval toepassen</span><span class="sxs-lookup"><span data-stu-id="eb7b3-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="eb7b3-115">Klik **in het** navigatiemenu op Configuratiebeheer om de pagina Apparaatconfiguratiebeheer te openen.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="eb7b3-116">![Pagina Beveiligingsconfiguratiebeheer](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="eb7b3-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="eb7b3-117">*Pagina Apparaatconfiguratiebeheer*</span><span class="sxs-lookup"><span data-stu-id="eb7b3-117">*Device configuration management page*</span></span>

<span data-ttu-id="eb7b3-118">U kunt de configuratiestatus op organisatieniveau bijhouden en snel actie ondernemen als reactie op slechte onboarding-dekking, complianceproblemen en slecht geoptimaliseerde risico's voor aanvalsoppervlak via directe, diepe koppelingen naar pagina's voor apparaatbeheer in het Microsoft Intune- en Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="eb7b3-119">Daarbij profiteert u van:</span><span class="sxs-lookup"><span data-stu-id="eb7b3-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="eb7b3-120">Uitgebreide zichtbaarheid van de gebeurtenissen op uw apparaten</span><span class="sxs-lookup"><span data-stu-id="eb7b3-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="eb7b3-121">Krachtige bedreigingsinformatie en krachtige leertechnologieën voor apparaten voor het verwerken van onbewerkte gebeurtenissen en het identificeren van de inbreukactiviteit en bedreigingsindicatoren</span><span class="sxs-lookup"><span data-stu-id="eb7b3-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="eb7b3-122">Een volledige stapel beveiligingsfuncties die zijn geconfigureerd om de installatie van schadelijke implantaten, het kapen van systeembestanden en -processen, gegevens exfiltratie en andere bedreigingsactiviteiten efficiënt te stoppen</span><span class="sxs-lookup"><span data-stu-id="eb7b3-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="eb7b3-123">Geoptimaliseerde risico's voor aanvallen op het oppervlak, het maximaliseren van strategische verdediging tegen bedreigingsactiviteit en het minimaliseren van de invloed op de productiviteit</span><span class="sxs-lookup"><span data-stu-id="eb7b3-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="eb7b3-124">Apparaten registreren voor Intune-beheer</span><span class="sxs-lookup"><span data-stu-id="eb7b3-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="eb7b3-125">Apparaatconfiguratiebeheer werkt nauw samen met Intune-apparaatbeheer om de inventaris van de apparaten in uw organisatie en de basislijnbeveiligingsconfiguratie vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="eb7b3-126">U kunt configuratieproblemen bijhouden en beheren op Door Intune beheerde Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="eb7b3-127">Voordat u ervoor kunt zorgen dat uw apparaten correct zijn geconfigureerd, moet u deze registreren bij Intune-beheer.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="eb7b3-128">Intune-registratie is robuust en heeft verschillende inschrijvingsopties voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="eb7b3-129">Voor meer informatie over intune-registratieopties leest u over het instellen van [registratie voor Windows-apparaten.](https://docs.microsoft.com/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="eb7b3-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="eb7b3-130">Als u Windows-apparaten wilt registreren bij Intune, moeten beheerders al licenties zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="eb7b3-131">[Lees meer over het toewijzen van licenties voor apparaatinschrijving.](https://docs.microsoft.com/intune/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="eb7b3-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="eb7b3-132">Als u apparaatbeheer wilt optimaliseren via Intune, verbindt u [Intune met Defender voor Eindpunt.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="eb7b3-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="eb7b3-133">Vereiste machtigingen verkrijgen</span><span class="sxs-lookup"><span data-stu-id="eb7b3-133">Obtain required permissions</span></span>
<span data-ttu-id="eb7b3-134">Standaard kunnen alleen gebruikers die de globale beheerder of de rol van Intune-servicebeheerder in Azure AD hebben toegewezen, de apparaatconfiguratieprofielen beheren en toewijzen die nodig zijn voor onboarding-apparaten en de beveiligingslijn implementeren.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="eb7b3-135">Als u andere rollen hebt toegewezen, moet u ervoor zorgen dat u de benodigde machtigingen hebt:</span><span class="sxs-lookup"><span data-stu-id="eb7b3-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="eb7b3-136">Volledige machtigingen voor apparaatconfiguraties</span><span class="sxs-lookup"><span data-stu-id="eb7b3-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="eb7b3-137">Volledige machtigingen voor beveiligingslijnlijnen</span><span class="sxs-lookup"><span data-stu-id="eb7b3-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="eb7b3-138">Leesmachtigingen voor apparaat compliancebeleid</span><span class="sxs-lookup"><span data-stu-id="eb7b3-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="eb7b3-139">Leesmachtigingen voor de organisatie</span><span class="sxs-lookup"><span data-stu-id="eb7b3-139">Read permissions to the organization</span></span>

<span data-ttu-id="eb7b3-140">![Vereiste machtigingen voor intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="eb7b3-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="eb7b3-141">*Apparaatconfiguratiemachtigingen voor Intune*</span><span class="sxs-lookup"><span data-stu-id="eb7b3-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="eb7b3-142">Lees meer over het maken van aangepaste [](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)rollen voor meer informatie over het toewijzen van machtigingen aan Intune.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb7b3-143">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="eb7b3-143">In this section</span></span>
<span data-ttu-id="eb7b3-144">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="eb7b3-144">Topic</span></span> | <span data-ttu-id="eb7b3-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="eb7b3-145">Description</span></span>
:---|:---
[<span data-ttu-id="eb7b3-146">Apparaten in gebruik nemen bij Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="eb7b3-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="eb7b3-147">Volg de onboarding-status van door Intune beheerde apparaten en onboard meer apparaten via Intune.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="eb7b3-148">Naleving van de beveiligingslijn defender voor eindpunt verhogen</span><span class="sxs-lookup"><span data-stu-id="eb7b3-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="eb7b3-149">Houd de naleving van de basislijn en niet-naleving bij.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="eb7b3-150">Implementeer de beveiligingslijn naar meer door Intune beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="eb7b3-151">Asr-regelimplementatie en -detecties optimaliseren</span><span class="sxs-lookup"><span data-stu-id="eb7b3-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="eb7b3-152">Controleer de implementatie van regels en pas detecties aan met behulp van hulpmiddelen voor effectanalyse in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="eb7b3-153">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="eb7b3-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eb7b3-154">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="eb7b3-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
