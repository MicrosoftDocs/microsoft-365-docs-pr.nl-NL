---
title: Implementatie met een ander MDM-systeem (Mobile Device Management) voor Microsoft Defender ATP voor Mac
description: Microsoft Defender ATP voor Mac installeren op andere beheeroplossingen.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3343eb433a6ae5c708651abf298bd4f061817543
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764131"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1c446-104">Implementatie met een ander MDM-systeem (Mobile Device Management) voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="1c446-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1c446-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1c446-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c446-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1c446-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1c446-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c446-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1c446-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1c446-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1c446-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1c446-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="1c446-110">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="1c446-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="1c446-111">Voordat u aan de slag gaat, bekijkt u de hoofdpagina van Microsoft Defender voor Eindpunt op [macOS](microsoft-defender-endpoint-mac.md) voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.</span><span class="sxs-lookup"><span data-stu-id="1c446-111">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="approach"></a><span data-ttu-id="1c446-112">Benadering</span><span class="sxs-lookup"><span data-stu-id="1c446-112">Approach</span></span>

> [!CAUTION]

> <span data-ttu-id="1c446-113">Momenteel ondersteunt Microsoft officieel alleen Intune en JAMF voor de implementatie en het beheer van Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="1c446-113">Currently, Microsoft officially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="1c446-114">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de onderstaande informatie.</span><span class="sxs-lookup"><span data-stu-id="1c446-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="1c446-115">Als uw organisatie een MDM-oplossing (Mobile Device Management) gebruikt die niet officieel wordt ondersteund, betekent dit niet dat u Microsoft Defender voor Eindpunt niet kunt implementeren of uitvoeren op macOS.</span><span class="sxs-lookup"><span data-stu-id="1c446-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="1c446-116">Microsoft Defender voor Eindpunt voor macOS is niet afhankelijk van specifieke functies van leveranciers.</span><span class="sxs-lookup"><span data-stu-id="1c446-116">Microsoft Defender for Endpoint on macOS does not depend on any vendor-specific features.</span></span> <span data-ttu-id="1c446-117">Deze kan worden gebruikt met elke MDM-oplossing die de volgende functies ondersteunt:</span><span class="sxs-lookup"><span data-stu-id="1c446-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="1c446-118">Een macOS .pkg implementeren op beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="1c446-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="1c446-119">MacOS-systeemconfiguratieprofielen implementeren op beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="1c446-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="1c446-120">Voer een willekeurig door de beheerder geconfigureerd hulpprogramma/script uit op beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="1c446-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="1c446-121">De meeste moderne MDM-oplossingen bevatten deze functies, maar ze kunnen ze anders noemen.</span><span class="sxs-lookup"><span data-stu-id="1c446-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="1c446-122">U kunt Defender echter implementeren zonder de laatste vereiste uit de vorige lijst:</span><span class="sxs-lookup"><span data-stu-id="1c446-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="1c446-123">U kunt de status niet op een gecentraliseerde manier verzamelen</span><span class="sxs-lookup"><span data-stu-id="1c446-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="1c446-124">Als u Besluit Defender te verwijderen, moet u zich lokaal aanmelden bij het clientapparaat als beheerder</span><span class="sxs-lookup"><span data-stu-id="1c446-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="1c446-125">Implementatie</span><span class="sxs-lookup"><span data-stu-id="1c446-125">Deployment</span></span>

<span data-ttu-id="1c446-126">De meeste MDM-oplossingen gebruiken hetzelfde model voor het beheren van macOS-apparaten, met vergelijkbare terminologie.</span><span class="sxs-lookup"><span data-stu-id="1c446-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="1c446-127">Gebruik [DE IMPLEMENTATIE OP BASIS VAN JAMF](mac-install-with-jamf.md) als sjabloon.</span><span class="sxs-lookup"><span data-stu-id="1c446-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="1c446-128">Pakket</span><span class="sxs-lookup"><span data-stu-id="1c446-128">Package</span></span>

<span data-ttu-id="1c446-129">Configureer de implementatie [van een vereist toepassingspakket,](mac-install-with-jamf.md)met het installatiepakket (wdav.pkg) gedownload van het Microsoft Defender Security [Center](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="1c446-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="1c446-130">Als u het pakket wilt implementeren in uw bedrijf, gebruikt u de instructies die zijn gekoppeld aan uw MDM-oplossing.</span><span class="sxs-lookup"><span data-stu-id="1c446-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="1c446-131">Licentie-instellingen</span><span class="sxs-lookup"><span data-stu-id="1c446-131">License settings</span></span>

<span data-ttu-id="1c446-132">Een [systeemconfiguratieprofiel instellen.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="1c446-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> 

<span data-ttu-id="1c446-133">Uw MDM-oplossing kan dit zoiets noemen als 'Profiel aangepaste instellingen', omdat Microsoft Defender voor Eindpunt op macOS geen deel uitmaakt van macOS.</span><span class="sxs-lookup"><span data-stu-id="1c446-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint on macOS is not part of macOS.</span></span>

<span data-ttu-id="1c446-134">Gebruik de lijst met eigenschappen, jamf/WindowsDefenderATPOnboarding.plist, die kan worden gehaald uit een onboarding-pakket dat is gedownload van [het Microsoft Defender-beveiligingscentrum.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="1c446-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="1c446-135">Uw systeem ondersteunt mogelijk een lijst met willekeurige eigenschappen in XML-indeling.</span><span class="sxs-lookup"><span data-stu-id="1c446-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="1c446-136">U kunt het bestand jamf/WindowsDefenderATPOnboarding.plist zoals in dat geval uploaden.</span><span class="sxs-lookup"><span data-stu-id="1c446-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="1c446-137">U moet de lijst met eigenschappen mogelijk eerst converteren naar een andere indeling.</span><span class="sxs-lookup"><span data-stu-id="1c446-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="1c446-138">Meestal heeft uw aangepaste profiel een id, naam of domeinkenmerk.</span><span class="sxs-lookup"><span data-stu-id="1c446-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="1c446-139">U moet precies 'com.microsoft.wdav.atp' voor deze waarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1c446-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="1c446-140">MDM gebruikt het bestand om het instellingenbestand te implementeren naar **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** op een clientapparaat en Defender gebruikt dit bestand voor het laden van de onboarding-informatie.</span><span class="sxs-lookup"><span data-stu-id="1c446-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="1c446-141">Beleid voor kernelextensie</span><span class="sxs-lookup"><span data-stu-id="1c446-141">Kernel extension policy</span></span>

<span data-ttu-id="1c446-142">Een KEXT- of kernelextensiebeleid instellen.</span><span class="sxs-lookup"><span data-stu-id="1c446-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="1c446-143">Gebruik teamaanduiding **UBF8T346G9** om kernelextensies van Microsoft toe te staan.</span><span class="sxs-lookup"><span data-stu-id="1c446-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

> [!CAUTION]
> <span data-ttu-id="1c446-144">Als uw omgeving uit M1-apparaten (Apple Silicon) bestaat, ontvangen deze machines geen configuratieprofielen met KEXT-beleid.</span><span class="sxs-lookup"><span data-stu-id="1c446-144">If your environment consists of Apple Silicon (M1) devices, these machines should not receive configuration profiles with KEXT policies.</span></span>
> <span data-ttu-id="1c446-145">Apple biedt geen ondersteuning voor KEXT op deze machines, de implementatie van een dergelijk profiel zou mislukken op M1-machines.</span><span class="sxs-lookup"><span data-stu-id="1c446-145">Apple does not support KEXT on these machines, deployment of such profile would fail on M1 machines.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="1c446-146">Systeemextensiebeleid</span><span class="sxs-lookup"><span data-stu-id="1c446-146">System extension policy</span></span>

<span data-ttu-id="1c446-147">Een systeemextensiebeleid instellen.</span><span class="sxs-lookup"><span data-stu-id="1c446-147">Set up a system extension policy.</span></span> <span data-ttu-id="1c446-148">Gebruik teamaanduiding **UBF8T346G9** en keur de volgende bundelaanduidingen goed:</span><span class="sxs-lookup"><span data-stu-id="1c446-148">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="1c446-149">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="1c446-149">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="1c446-150">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="1c446-150">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="1c446-151">Beleid voor volledige schijftoegang</span><span class="sxs-lookup"><span data-stu-id="1c446-151">Full disk access policy</span></span>

<span data-ttu-id="1c446-152">Volledige schijftoegang verlenen aan de volgende onderdelen:</span><span class="sxs-lookup"><span data-stu-id="1c446-152">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="1c446-153">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1c446-153">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="1c446-154">Id: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="1c446-154">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="1c446-155">Id-type: bundel-id</span><span class="sxs-lookup"><span data-stu-id="1c446-155">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="1c446-156">Codevereiste: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="1c446-156">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="1c446-157">Microsoft Defender voor endpoint-beveiligingsextensie</span><span class="sxs-lookup"><span data-stu-id="1c446-157">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="1c446-158">Id: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="1c446-158">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="1c446-159">Id-type: bundel-id</span><span class="sxs-lookup"><span data-stu-id="1c446-159">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="1c446-160">Codevereiste: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="1c446-160">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="1c446-161">Beleid voor netwerkextensie</span><span class="sxs-lookup"><span data-stu-id="1c446-161">Network extension policy</span></span>

<span data-ttu-id="1c446-162">Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoorden controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="1c446-162">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="1c446-163">Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="1c446-163">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="1c446-164">Filtertype: Invoegvoeginvoeging</span><span class="sxs-lookup"><span data-stu-id="1c446-164">Filter type: Plugin</span></span>
- <span data-ttu-id="1c446-165">Id van de invoegbundel: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="1c446-165">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="1c446-166">Gegevensproviderbundel-id filteren: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="1c446-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="1c446-167">Vereiste filtergegevensprovider: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="1c446-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="1c446-168">Filterdozen: `true`</span><span class="sxs-lookup"><span data-stu-id="1c446-168">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="1c446-169">Installatiestatus controleren</span><span class="sxs-lookup"><span data-stu-id="1c446-169">Check installation status</span></span>

<span data-ttu-id="1c446-170">Voer [Microsoft Defender voor Eindpunt uit](mac-install-with-jamf.md) op een clientapparaat om de onboarding-status te controleren.</span><span class="sxs-lookup"><span data-stu-id="1c446-170">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
