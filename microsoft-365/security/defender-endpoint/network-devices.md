---
title: Netwerkapparaatdetectie en beveiligingsprobleembeheer
description: Beveiligingsaanbevelingen en beveiligingsdetectie zijn nu beschikbaar voor besturingssystemen van schakelopties, routers, WLAN-controllers en firewalls.
keywords: netwerkapparaten, detectie van kwetsbaarheid van netwerkapparaten, besturingssystemen van schakelopties, routers, WLAN-controllers en firewalls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d0ae82c2e284235d96531c04dc2240063d4e4183
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2021
ms.locfileid: "51657039"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="bd692-104">Netwerkapparaatdetectie en beveiligingsprobleembeheer</span><span class="sxs-lookup"><span data-stu-id="bd692-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd692-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bd692-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd692-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bd692-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bd692-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="bd692-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bd692-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd692-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="bd692-109">**Het scannen en beheren van netwerkapparaten wordt momenteel in een openbaar voorbeeld weergegeven**</span><span class="sxs-lookup"><span data-stu-id="bd692-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="bd692-110">Deze preview-versie wordt geleverd zonder serviceovereenkomst en wordt niet aanbevolen voor productiebelastingen.</span><span class="sxs-lookup"><span data-stu-id="bd692-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="bd692-111">Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="bd692-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="bd692-112">Zie De preview-functies [van Microsoft Defender voor Eindpunt voor meer informatie.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="bd692-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="bd692-113">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bd692-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bd692-114">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bd692-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="bd692-115">Mogelijkheden voor netwerkdetectie zijn beschikbaar in de sectie **Apparaatvoorraad** van het Microsoft 365-beveiligingscentrum en de consoles van het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="bd692-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="bd692-116">Een aangewezen Microsoft Defender voor Eindpunt-apparaat wordt in elk netwerksegment gebruikt om periodieke geverifieerde scans van vooraf geconfigureerde netwerkapparaten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bd692-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="bd692-117">Nadat deze zijn ontdekt, bieden de mogelijkheden voor bedreigings- en kwetsbaarheidsbeheer van Defender voor Eindpunt geïntegreerde werkstromen voor het beveiligen van gevonden schakelopties, routers, WLAN-controllers, firewalls en VPN-gateways.</span><span class="sxs-lookup"><span data-stu-id="bd692-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="bd692-118">Zodra de netwerkapparaten zijn gevonden en geclassificeerd, kunnen beveiligingsbeheerders de meest recente beveiligingsaanbevelingen ontvangen en onlangs ontdekte beveiligingsproblemen bekijken op netwerkapparaten die in hun organisatie zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="bd692-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="bd692-119">Benadering</span><span class="sxs-lookup"><span data-stu-id="bd692-119">Approach</span></span>

<span data-ttu-id="bd692-120">Netwerkapparaten worden niet beheerd als standaard eindpunten, omdat Defender voor Eindpunt geen sensor heeft ingebouwd in de netwerkapparaten zelf.</span><span class="sxs-lookup"><span data-stu-id="bd692-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="bd692-121">Voor deze typen apparaten is een agentloze benadering vereist waarbij een externe scan de benodigde informatie van de apparaten haalt.</span><span class="sxs-lookup"><span data-stu-id="bd692-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="bd692-122">Afhankelijk van de netwerktopologie en -kenmerken worden met één apparaat of een paar apparaten die zijn aan boord van Microsoft Defender voor Eindpunt geverifieerde scans uitgevoerd van netwerkapparaten met SNMP (alleen-lezen).</span><span class="sxs-lookup"><span data-stu-id="bd692-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="bd692-123">Er zijn twee typen apparaten waar u rekening mee moet houden:</span><span class="sxs-lookup"><span data-stu-id="bd692-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="bd692-124">**Evaluatieapparaat:** een apparaat dat al is aan boord dat u gebruikt om de netwerkapparaten te scannen.</span><span class="sxs-lookup"><span data-stu-id="bd692-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="bd692-125">**Netwerkapparaten:** de netwerkapparaten die u wilt scannen en aan boord gaan.</span><span class="sxs-lookup"><span data-stu-id="bd692-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="bd692-126">Beveiligingsprobleembeheer voor netwerkapparaten</span><span class="sxs-lookup"><span data-stu-id="bd692-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="bd692-127">Zodra de netwerkapparaten zijn gevonden en geclassificeerd, kunnen beveiligingsbeheerders de meest recente beveiligingsaanbevelingen ontvangen en onlangs ontdekte beveiligingsproblemen bekijken op netwerkapparaten die in hun organisatie zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="bd692-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="bd692-128">Besturingssystemen die worden ondersteund</span><span class="sxs-lookup"><span data-stu-id="bd692-128">Operating systems that are supported</span></span>

<span data-ttu-id="bd692-129">De volgende besturingssystemen worden momenteel ondersteund:</span><span class="sxs-lookup"><span data-stu-id="bd692-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="bd692-130">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="bd692-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="bd692-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="bd692-131">Juniper JUNOS</span></span>
- <span data-ttu-id="bd692-132">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="bd692-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="bd692-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="bd692-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="bd692-134">In de tijd worden er meer netwerkleveranciers en besturingssysteem toegevoegd, op basis van gegevens die afkomstig zijn van klantgebruik.</span><span class="sxs-lookup"><span data-stu-id="bd692-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="bd692-135">Daarom wordt u aangeraden om al uw netwerkapparaten te configureren, zelfs als ze niet zijn opgegeven in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="bd692-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="bd692-136">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="bd692-136">How to get started</span></span>

<span data-ttu-id="bd692-137">De eerste stap is het selecteren van een apparaat dat de geverifieerde netwerkscans gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="bd692-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="bd692-138">Beslis over een aan boord van Defender voor Endpoint-apparaat (client of server) dat een netwerkverbinding met de beheerpoort heeft voor de netwerkapparaten die u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="bd692-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="bd692-139">SNMP-verkeer tussen het Defender for Endpoint-evaluatieapparaat en de beoogde netwerkapparaten moet zijn toegestaan (bijvoorbeeld door de Firewall).</span><span class="sxs-lookup"><span data-stu-id="bd692-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="bd692-140">Bepaal welke netwerkapparaten worden beoordeeld op beveiligingsproblemen (bijvoorbeeld een Cisco-switch of een Firewall van Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="bd692-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="bd692-141">Zorg ervoor dat alleen-lezen SNMP is ingeschakeld op alle geconfigureerde netwerkapparaten, zodat het defender for Endpoint-beoordelingsapparaat de geconfigureerde netwerkapparaten kan query's uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="bd692-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="bd692-142">'SNMP write' is niet nodig voor de juiste functionaliteit van deze functie.</span><span class="sxs-lookup"><span data-stu-id="bd692-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="bd692-143">Verkrijg de IP-adressen van de netwerkapparaten die moeten worden gescand (of de subnetten waar deze apparaten worden geïmplementeerd).</span><span class="sxs-lookup"><span data-stu-id="bd692-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="bd692-144">Verkrijg de SNMP-referenties van de netwerkapparaten (bijvoorbeeld: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="bd692-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="bd692-145">U moet de referenties verstrekken bij het configureren van een nieuwe beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="bd692-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="bd692-146">Configuratie van proxyclient: Er is geen extra configuratie vereist, anders dan de proxyvereisten voor defender voor eindpuntapparaat.</span><span class="sxs-lookup"><span data-stu-id="bd692-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="bd692-147">Als u wilt toestaan dat de netwerkscanner wordt geverifieerd en correct werkt, is het essentieel dat u de volgende domeinen/URL's toevoegt:</span><span class="sxs-lookup"><span data-stu-id="bd692-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="bd692-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="bd692-148">login.windows.net</span></span>  
    - <span data-ttu-id="bd692-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="bd692-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="bd692-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bd692-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="bd692-151">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="bd692-151">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    <span data-ttu-id="bd692-152">Opmerking: Niet alle URL's worden opgegeven in de lijst met gedocumenteerde gegevensverzamelingen van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="bd692-152">Note: Not all URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="bd692-153">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="bd692-153">Permissions</span></span>

<span data-ttu-id="bd692-154">Als u evaluatietaken wilt configureren, is de volgende optie voor gebruikersmachtiging vereist: **Beveiligingsinstellingen beheren in het Beveiligingscentrum.**</span><span class="sxs-lookup"><span data-stu-id="bd692-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="bd692-155">U kunt de machtiging vinden door naar Instellingen Rollen  >  **te gaan.**</span><span class="sxs-lookup"><span data-stu-id="bd692-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="bd692-156">Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer](user-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bd692-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="bd692-157">De netwerkscanner installeren</span><span class="sxs-lookup"><span data-stu-id="bd692-157">Install the network scanner</span></span>

1. <span data-ttu-id="bd692-158">Ga naar **Microsoft 365 security**  >  **Settings**  >  **Endpoints**  >  **Assessment jobs** (under 'Network assessments').</span><span class="sxs-lookup"><span data-stu-id="bd692-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="bd692-159">Ga in het Microsoft Defender-beveiligingscentrum naar de pagina Instellingen > Evaluatietaken.</span><span class="sxs-lookup"><span data-stu-id="bd692-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="bd692-160">Download de netwerkscanner en installeer deze op het aangewezen defender voor eindpuntbeoordelingsapparaat.</span><span class="sxs-lookup"><span data-stu-id="bd692-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![Knop Scanner downloaden](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="bd692-162">Installatie van netwerkscanners & registratie</span><span class="sxs-lookup"><span data-stu-id="bd692-162">Network scanner installation & registration</span></span>

<span data-ttu-id="bd692-163">Het aanmeldingsproces kan worden voltooid op het aangewezen beoordelingsapparaat zelf of op een ander apparaat (bijvoorbeeld uw persoonlijke clientapparaat).</span><span class="sxs-lookup"><span data-stu-id="bd692-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="bd692-164">Het registratieproces van de netwerkscanner voltooien:</span><span class="sxs-lookup"><span data-stu-id="bd692-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="bd692-165">Kopieer en volg de URL die op de opdrachtregel wordt weergegeven en gebruik de meegeleverde installatiecode om het registratieproces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="bd692-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="bd692-166">Opmerking: Mogelijk moet u de instellingen voor opdrachtprompt wijzigen om de URL te kunnen kopiëren.</span><span class="sxs-lookup"><span data-stu-id="bd692-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="bd692-167">Voer de code in en meld u aan met een Microsoft-account met de machtiging Defender voor eindpunt genaamd 'Beveiligingsinstellingen beheren in beveiligingscentrum'.</span><span class="sxs-lookup"><span data-stu-id="bd692-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="bd692-168">Wanneer u klaar bent, ziet u een bericht waarin wordt bevestigd dat u zich hebt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="bd692-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="bd692-169">Een nieuwe evaluatieklus configureren</span><span class="sxs-lookup"><span data-stu-id="bd692-169">Configure a new assessment job</span></span>  

<span data-ttu-id="bd692-170">Selecteer op de pagina Evaluatietaken in **Instellingen** de optie **Netwerkbeoordelingstaken toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="bd692-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="bd692-171">Volg het set-upproces om netwerkapparaten te kiezen die regelmatig moeten worden gescand en toegevoegd aan de apparaatvoorraad.</span><span class="sxs-lookup"><span data-stu-id="bd692-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="bd692-172">Als u duplicatie van apparaten in de netwerkapparaatvoorraad wilt voorkomen, moet u ervoor zorgen dat elk IP-adres slechts eenmaal is geconfigureerd op meerdere beoordelingsapparaten.</span><span class="sxs-lookup"><span data-stu-id="bd692-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![Knop Netwerkbeoordelingsbaan toevoegen](images/assessment-jobs-add.png)

<span data-ttu-id="bd692-174">Een netwerkbeoordelingsbaan toevoegen:</span><span class="sxs-lookup"><span data-stu-id="bd692-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="bd692-175">Kies de naam 'Beoordelingsbaan' en het 'Assessment-apparaat' waarop de netwerkscanner is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="bd692-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="bd692-176">Dit apparaat voert de periodieke geverifieerde scans uit.</span><span class="sxs-lookup"><span data-stu-id="bd692-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="bd692-177">Voeg IP-adressen toe van doelnetwerkapparaten die moeten worden gescand (of de subnetten waar deze apparaten worden geïmplementeerd).</span><span class="sxs-lookup"><span data-stu-id="bd692-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="bd692-178">Voeg vereiste SNMP-referenties van de doelnetwerkapparaten toe.</span><span class="sxs-lookup"><span data-stu-id="bd692-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="bd692-179">Sla de nieuw geconfigureerde netwerkbeoordelings taak op om de periodieke netwerkscan te starten.</span><span class="sxs-lookup"><span data-stu-id="bd692-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="bd692-180">Netwerkapparaten scannen en toevoegen</span><span class="sxs-lookup"><span data-stu-id="bd692-180">Scan and add network devices</span></span>

<span data-ttu-id="bd692-181">Tijdens het instellen kunt u een een keer testen om te controleren of:</span><span class="sxs-lookup"><span data-stu-id="bd692-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="bd692-182">Er is verbinding tussen het defender voor eindpuntbeoordelingsapparaat en de geconfigureerde doelnetwerkapparaten.</span><span class="sxs-lookup"><span data-stu-id="bd692-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="bd692-183">De geconfigureerde SNMP-referenties zijn correct.</span><span class="sxs-lookup"><span data-stu-id="bd692-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="bd692-184">Elk beoordelingsapparaat kan maximaal 1500 geslaagde IP-adressen scannen.</span><span class="sxs-lookup"><span data-stu-id="bd692-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="bd692-185">Als u bijvoorbeeld 10 verschillende subnetten scant waarbij slechts 100 IP-adressen succesvolle resultaten opleveren, kunt u 1.400 EXTRA IP-adressen scannen van andere subnetten op hetzelfde beoordelingsapparaat.</span><span class="sxs-lookup"><span data-stu-id="bd692-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="bd692-186">Als er meerdere IP-adresbereiken/subnetten moeten worden gescand, duurt het enkele minuten voordat de testresultaten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bd692-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="bd692-187">Er is een testscan beschikbaar voor maximaal 1.024 adressen.</span><span class="sxs-lookup"><span data-stu-id="bd692-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="bd692-188">Wanneer de resultaten worden vermeld, kunt u kiezen welke apparaten worden opgenomen in de periodieke scan.</span><span class="sxs-lookup"><span data-stu-id="bd692-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="bd692-189">Als u het weergeven van de scanresultaten overslaat, worden alle geconfigureerde IP-adressen toegevoegd aan de netwerkbeoordelings taak (ongeacht de reactie van het apparaat).</span><span class="sxs-lookup"><span data-stu-id="bd692-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="bd692-190">De scanresultaten kunnen ook worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="bd692-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="bd692-191">Apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="bd692-191">Device inventory</span></span>

<span data-ttu-id="bd692-192">Nieuw ontdekte apparaten worden weergegeven onder het nieuwe tabblad **Netwerkapparaten** op de **pagina Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="bd692-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="bd692-193">Het kan maximaal twee uur duren nadat u een beoordelings taak hebt toegevoegd totdat de apparaten zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="bd692-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![Sectie Netwerkapparaten in de apparaatvoorraad](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="bd692-195">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="bd692-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="bd692-196">Installatie van netwerkscanner is mislukt</span><span class="sxs-lookup"><span data-stu-id="bd692-196">Network scanner installation has failed</span></span>

<span data-ttu-id="bd692-197">Controleer of de vereiste URL's zijn toegevoegd aan de toegestane domeinen in uw firewallinstellingen.</span><span class="sxs-lookup"><span data-stu-id="bd692-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="bd692-198">Zorg er ook voor dat proxy-instellingen zijn geconfigureerd zoals beschreven in Instellingen voor [apparaatproxy en internetverbinding configureren](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="bd692-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="bd692-199">De Microsoft.com/devicelogin webpagina is niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="bd692-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="bd692-200">Controleer of de vereiste URL's zijn toegevoegd aan de toegestane domeinen in uw firewall.</span><span class="sxs-lookup"><span data-stu-id="bd692-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="bd692-201">Zorg er ook voor dat proxy-instellingen zijn geconfigureerd zoals beschreven in Instellingen voor [apparaatproxy en internetverbinding configureren.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="bd692-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="bd692-202">Netwerkapparaten worden na enkele uren niet weergegeven in de apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="bd692-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="bd692-203">De scanresultaten moeten enkele uren na de eerste scan worden bijgewerkt na het voltooien van de configuratie van de beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="bd692-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="bd692-204">Als apparaten nog steeds niet worden weergegeven, controleert u of de service 'MdatpNetworkScanService' wordt uitgevoerd op uw beoordelingsapparaten, waarop u de netwerkscanner hebt geïnstalleerd, en voert u een 'Scan uitvoeren' uit in de desbetreffende configuratie van de beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="bd692-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="bd692-205">Als u na 5 minuten nog steeds geen resultaten krijgt, start u de service opnieuw.</span><span class="sxs-lookup"><span data-stu-id="bd692-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="bd692-206">Apparaten die voor het laatst zijn gezien, zijn langer dan 24 uur</span><span class="sxs-lookup"><span data-stu-id="bd692-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="bd692-207">Controleer of de scanner correct wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bd692-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="bd692-208">Ga vervolgens naar de scandefinitie en selecteer 'Test uitvoeren'.</span><span class="sxs-lookup"><span data-stu-id="bd692-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="bd692-209">Controleer welke foutberichten van de betreffende IP-adressen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="bd692-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="bd692-210">Vereiste gebruikersmachtigingen voor bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="bd692-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="bd692-211">Registratie is voltooid met een fout: 'Het lijkt erop dat u niet over voldoende machtigingen voor het toevoegen van een nieuwe agent hebt.</span><span class="sxs-lookup"><span data-stu-id="bd692-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="bd692-212">De vereiste machtiging is 'Beveiligingsinstellingen beheren in het Beveiligingscentrum'.</span><span class="sxs-lookup"><span data-stu-id="bd692-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="bd692-213">Druk op een toets om af te sluiten.</span><span class="sxs-lookup"><span data-stu-id="bd692-213">Press any key to exit.</span></span>

<span data-ttu-id="bd692-214">Vraag de systeembeheerder u de vereiste machtigingen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="bd692-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="bd692-215">U kunt ook een ander relevant lid vragen u te helpen bij het aanmeldingsproces door hen de aanmeldingscode en koppeling te geven.</span><span class="sxs-lookup"><span data-stu-id="bd692-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="bd692-216">Registratieproces mislukt met behulp van de opgegeven koppeling in de opdrachtregel in het registratieproces</span><span class="sxs-lookup"><span data-stu-id="bd692-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="bd692-217">Probeer een andere browser of kopieer de aanmeldingskoppeling en -code naar een ander apparaat.</span><span class="sxs-lookup"><span data-stu-id="bd692-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="bd692-218">Tekst te klein of kan geen tekst uit opdrachtregel kopiëren</span><span class="sxs-lookup"><span data-stu-id="bd692-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="bd692-219">Wijzig de instellingen voor de opdrachtregel op uw apparaat om het kopiëren en wijzigen van de tekstgrootte toe te staan.</span><span class="sxs-lookup"><span data-stu-id="bd692-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bd692-220">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="bd692-220">Related articles</span></span>

- [<span data-ttu-id="bd692-221">Apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="bd692-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="bd692-222">Geavanceerde functies configureren</span><span class="sxs-lookup"><span data-stu-id="bd692-222">Configure advanced features</span></span>](advanced-features.md)
