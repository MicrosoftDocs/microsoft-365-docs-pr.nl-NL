---
title: Netwerkapparaatdetectie en -vulnerability management
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
ms.openlocfilehash: da15519211599bfc248c20c36cfab456c1661caa
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862065"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="879c3-104">Netwerkapparaatdetectie en -vulnerability management</span><span class="sxs-lookup"><span data-stu-id="879c3-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="879c3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="879c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="879c3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="879c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="879c3-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="879c3-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="879c3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="879c3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="879c3-109">**Het scannen en beheren van netwerkapparaten wordt momenteel in een openbaar voorbeeld weergegeven**</span><span class="sxs-lookup"><span data-stu-id="879c3-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="879c3-110">Deze preview-versie wordt geleverd zonder serviceovereenkomst en wordt niet aanbevolen voor productiebelastingen.</span><span class="sxs-lookup"><span data-stu-id="879c3-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="879c3-111">Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="879c3-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="879c3-112">Zie De preview-functies [van Microsoft Defender voor Eindpunt voor meer informatie.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="879c3-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="879c3-113">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="879c3-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="879c3-114">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="879c3-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="879c3-115">De [netwerkapparaatdetectie-](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) en kwetsbaarheidsbeoordelingen Blog \( gepubliceerd op 04-13-2021 biedt inzicht in de nieuwe mogelijkheden voor netwerkapparaatdetectie \) in Defender voor  Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="879c3-115">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="879c3-116">In dit artikel vindt u een overzicht van de uitdaging waarop netwerkapparaatdetectie **is** ontworpen en gedetailleerde informatie over hoe u aan de slag gaat met deze nieuwe mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="879c3-116">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="879c3-117">Netwerkdetectiemogelijkheden zijn beschikbaar in de sectie **Apparaatvoorraad** van het Microsoft 365 beveiligingscentrum en Microsoft Defender-beveiligingscentrum consoles.</span><span class="sxs-lookup"><span data-stu-id="879c3-117">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="879c3-118">Een aangewezen Microsoft Defender voor Eindpunt-apparaat wordt in elk netwerksegment gebruikt om periodieke geverifieerde scans van vooraf geconfigureerde netwerkapparaten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="879c3-118">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="879c3-119">Nadat deze zijn ontdekt, bieden de functies van Defender voor Endpoint Threat and Vulnerability Management geïntegreerde werkstromen voor het beveiligen van gevonden schakelopties, routers, WLAN-controllers, firewalls en VPN-gateways.</span><span class="sxs-lookup"><span data-stu-id="879c3-119">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="879c3-120">Zodra de netwerkapparaten zijn gevonden en geclassificeerd, kunnen beveiligingsbeheerders de meest recente beveiligingsaanbevelingen ontvangen en onlangs ontdekte beveiligingsproblemen bekijken op netwerkapparaten die in hun organisatie zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="879c3-120">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="879c3-121">Benadering</span><span class="sxs-lookup"><span data-stu-id="879c3-121">Approach</span></span>

<span data-ttu-id="879c3-122">Netwerkapparaten worden niet beheerd als standaard eindpunten, omdat Defender voor Eindpunt geen sensor heeft ingebouwd in de netwerkapparaten zelf.</span><span class="sxs-lookup"><span data-stu-id="879c3-122">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="879c3-123">Voor deze typen apparaten is een agentloze benadering vereist waarbij een externe scan de benodigde informatie van de apparaten haalt.</span><span class="sxs-lookup"><span data-stu-id="879c3-123">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="879c3-124">Afhankelijk van de netwerktopologie en -kenmerken worden met één apparaat of een paar apparaten die zijn aan boord van Microsoft Defender voor Eindpunt geverifieerde scans uitgevoerd van netwerkapparaten met SNMP (alleen-lezen).</span><span class="sxs-lookup"><span data-stu-id="879c3-124">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="879c3-125">Er zijn twee typen apparaten waar u rekening mee moet houden:</span><span class="sxs-lookup"><span data-stu-id="879c3-125">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="879c3-126">**Evaluatieapparaat:** een apparaat dat al is aan boord dat u gebruikt om de netwerkapparaten te scannen.</span><span class="sxs-lookup"><span data-stu-id="879c3-126">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="879c3-127">**Netwerkapparaten:** de netwerkapparaten die u wilt scannen en aan boord gaan.</span><span class="sxs-lookup"><span data-stu-id="879c3-127">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="879c3-128">Beveiligingsprobleembeheer voor netwerkapparaten</span><span class="sxs-lookup"><span data-stu-id="879c3-128">Vulnerability management for network devices</span></span> 

<span data-ttu-id="879c3-129">Zodra de netwerkapparaten zijn gevonden en geclassificeerd, kunnen beveiligingsbeheerders de meest recente beveiligingsaanbevelingen ontvangen en onlangs ontdekte beveiligingsproblemen bekijken op netwerkapparaten die in hun organisatie zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="879c3-129">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="879c3-130">Besturingssystemen die worden ondersteund</span><span class="sxs-lookup"><span data-stu-id="879c3-130">Operating systems that are supported</span></span>

<span data-ttu-id="879c3-131">De volgende besturingssystemen worden momenteel ondersteund:</span><span class="sxs-lookup"><span data-stu-id="879c3-131">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="879c3-132">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="879c3-132">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="879c3-133">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="879c3-133">Juniper JUNOS</span></span>
- <span data-ttu-id="879c3-134">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="879c3-134">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="879c3-135">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="879c3-135">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="879c3-136">In de tijd worden er meer netwerkleveranciers en besturingssysteem toegevoegd, op basis van gegevens die afkomstig zijn van klantgebruik.</span><span class="sxs-lookup"><span data-stu-id="879c3-136">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="879c3-137">Daarom wordt u aangeraden om al uw netwerkapparaten te configureren, zelfs als ze niet zijn opgegeven in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="879c3-137">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="879c3-138">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="879c3-138">How to get started</span></span>

<span data-ttu-id="879c3-139">De eerste stap is het selecteren van een apparaat dat de geverifieerde netwerkscans gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="879c3-139">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="879c3-140">Beslis over een aan boord van Defender voor Endpoint-apparaat (client of server) dat een netwerkverbinding met de beheerpoort heeft voor de netwerkapparaten die u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="879c3-140">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="879c3-141">SNMP-verkeer tussen het Defender for Endpoint-evaluatieapparaat en de beoogde netwerkapparaten moet zijn toegestaan (bijvoorbeeld door de Firewall).</span><span class="sxs-lookup"><span data-stu-id="879c3-141">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="879c3-142">Bepaal welke netwerkapparaten worden beoordeeld op beveiligingsproblemen (bijvoorbeeld een Cisco-switch of een Firewall van Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="879c3-142">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="879c3-143">Zorg ervoor dat alleen-lezen SNMP is ingeschakeld op alle geconfigureerde netwerkapparaten, zodat het defender for Endpoint-beoordelingsapparaat de geconfigureerde netwerkapparaten kan query's uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="879c3-143">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="879c3-144">'SNMP write' is niet nodig voor de juiste functionaliteit van deze functie.</span><span class="sxs-lookup"><span data-stu-id="879c3-144">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="879c3-145">Verkrijg de IP-adressen van de netwerkapparaten die moeten worden gescand (of de subnetten waar deze apparaten worden geïmplementeerd).</span><span class="sxs-lookup"><span data-stu-id="879c3-145">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="879c3-146">Verkrijg de SNMP-referenties van de netwerkapparaten (bijvoorbeeld: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="879c3-146">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="879c3-147">U moet de referenties verstrekken bij het configureren van een nieuwe beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="879c3-147">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="879c3-148">Configuratie van proxyclient: Er is geen extra configuratie vereist, anders dan de proxyvereisten voor defender voor eindpuntapparaat.</span><span class="sxs-lookup"><span data-stu-id="879c3-148">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="879c3-149">Als u wilt toestaan dat de netwerkscanner wordt geverifieerd en correct werkt, is het essentieel dat u de volgende domeinen/URL's toevoegt:</span><span class="sxs-lookup"><span data-stu-id="879c3-149">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="879c3-150">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="879c3-150">login.windows.net</span></span>  
    - <span data-ttu-id="879c3-151">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="879c3-151">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="879c3-152">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="879c3-152">login.microsoftonline.com</span></span>
    - <span data-ttu-id="879c3-153">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="879c3-153">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="879c3-154">Niet alle URL's worden opgegeven in de lijst met gedocumenteerde gegevensverzamelingen van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="879c3-154">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="879c3-155">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="879c3-155">Permissions</span></span>

<span data-ttu-id="879c3-156">Als u evaluatietaken wilt configureren, is de volgende optie voor gebruikersmachtiging vereist: **Beveiligingsinstellingen beheren in het Beveiligingscentrum.**</span><span class="sxs-lookup"><span data-stu-id="879c3-156">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="879c3-157">U kunt de machtiging vinden door naar Instellingen  >  **Rollen.**</span><span class="sxs-lookup"><span data-stu-id="879c3-157">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="879c3-158">Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer voor meer informatie.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="879c3-158">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="879c3-159">De netwerkscanner installeren</span><span class="sxs-lookup"><span data-stu-id="879c3-159">Install the network scanner</span></span>

1. <span data-ttu-id="879c3-160">Ga naar **Microsoft 365**  >  **beveiligingstaken Instellingen**  >  **Endpoints**  >  **Assessment jobs** (onder **Netwerkbeoordelingen).**</span><span class="sxs-lookup"><span data-stu-id="879c3-160">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="879c3-161">Ga in Microsoft Defender-beveiligingscentrum naar de pagina Instellingen > Taken beoordelen.</span><span class="sxs-lookup"><span data-stu-id="879c3-161">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="879c3-162">Download de netwerkscanner en installeer deze op het aangewezen defender voor eindpuntbeoordelingsapparaat.</span><span class="sxs-lookup"><span data-stu-id="879c3-162">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="879c3-163">![Knop Scanner downloaden](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="879c3-163">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="879c3-164">Installatie van netwerkscanners & registratie</span><span class="sxs-lookup"><span data-stu-id="879c3-164">Network scanner installation & registration</span></span>

<span data-ttu-id="879c3-165">Het aanmeldingsproces kan worden voltooid op het aangewezen beoordelingsapparaat zelf of op een ander apparaat (bijvoorbeeld uw persoonlijke clientapparaat).</span><span class="sxs-lookup"><span data-stu-id="879c3-165">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="879c3-166">Het registratieproces van de netwerkscanner voltooien:</span><span class="sxs-lookup"><span data-stu-id="879c3-166">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="879c3-167">Kopieer en volg de URL die op de opdrachtregel wordt weergegeven en gebruik de meegeleverde installatiecode om het registratieproces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="879c3-167">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="879c3-168">Mogelijk moet u de instellingen voor opdrachtprompt wijzigen om de URL te kunnen kopiëren.</span><span class="sxs-lookup"><span data-stu-id="879c3-168">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="879c3-169">Voer de code in en meld u aan met een Microsoft-account met de machtiging Defender voor eindpunt genaamd 'Beveiligingsinstellingen beheren in beveiligingscentrum'.</span><span class="sxs-lookup"><span data-stu-id="879c3-169">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="879c3-170">Wanneer u klaar bent, ziet u een bericht waarin wordt bevestigd dat u zich hebt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="879c3-170">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="879c3-171">Een nieuwe evaluatieklus configureren</span><span class="sxs-lookup"><span data-stu-id="879c3-171">Configure a new assessment job</span></span>  

<span data-ttu-id="879c3-172">Selecteer op de pagina **Evaluatietaken** in Instellingen de optie **Netwerkbeoordelingstaken toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="879c3-172">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="879c3-173">Volg het set-upproces om netwerkapparaten te kiezen die regelmatig moeten worden gescand en toegevoegd aan de apparaatvoorraad.</span><span class="sxs-lookup"><span data-stu-id="879c3-173">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="879c3-174">Als u duplicatie van apparaten in de netwerkapparaatvoorraad wilt voorkomen, moet u ervoor zorgen dat elk IP-adres slechts eenmaal is geconfigureerd op meerdere beoordelingsapparaten.</span><span class="sxs-lookup"><span data-stu-id="879c3-174">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="879c3-175">![Knop Netwerkbeoordelingsbaan toevoegen](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="879c3-175">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="879c3-176">Een netwerkbeoordelingsbaan toevoegen:</span><span class="sxs-lookup"><span data-stu-id="879c3-176">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="879c3-177">Kies de naam 'Beoordelingsbaan' en het 'Assessment-apparaat' waarop de netwerkscanner is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="879c3-177">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="879c3-178">Dit apparaat voert de periodieke geverifieerde scans uit.</span><span class="sxs-lookup"><span data-stu-id="879c3-178">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="879c3-179">Voeg IP-adressen toe van doelnetwerkapparaten die moeten worden gescand (of de subnetten waar deze apparaten worden geïmplementeerd).</span><span class="sxs-lookup"><span data-stu-id="879c3-179">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="879c3-180">Voeg vereiste SNMP-referenties van de doelnetwerkapparaten toe.</span><span class="sxs-lookup"><span data-stu-id="879c3-180">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="879c3-181">Sla de nieuw geconfigureerde netwerkbeoordelings taak op om de periodieke netwerkscan te starten.</span><span class="sxs-lookup"><span data-stu-id="879c3-181">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="879c3-182">Netwerkapparaten scannen en toevoegen</span><span class="sxs-lookup"><span data-stu-id="879c3-182">Scan and add network devices</span></span>

<span data-ttu-id="879c3-183">Tijdens het instellen kunt u een een keer testen om te controleren of:</span><span class="sxs-lookup"><span data-stu-id="879c3-183">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="879c3-184">Er is verbinding tussen het defender voor eindpuntbeoordelingsapparaat en de geconfigureerde doelnetwerkapparaten.</span><span class="sxs-lookup"><span data-stu-id="879c3-184">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="879c3-185">De geconfigureerde SNMP-referenties zijn correct.</span><span class="sxs-lookup"><span data-stu-id="879c3-185">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="879c3-186">Elk beoordelingsapparaat kan maximaal 1500 geslaagde IP-adressen scannen.</span><span class="sxs-lookup"><span data-stu-id="879c3-186">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="879c3-187">Als u bijvoorbeeld 10 verschillende subnetten scant waarbij slechts 100 IP-adressen succesvolle resultaten opleveren, kunt u 1.400 EXTRA IP-adressen scannen van andere subnetten op hetzelfde beoordelingsapparaat.</span><span class="sxs-lookup"><span data-stu-id="879c3-187">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="879c3-188">Als er meerdere IP-adresbereiken/subnetten moeten worden gescand, duurt het enkele minuten voordat de testresultaten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="879c3-188">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="879c3-189">Er is een testscan beschikbaar voor maximaal 1.024 adressen.</span><span class="sxs-lookup"><span data-stu-id="879c3-189">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="879c3-190">Wanneer de resultaten worden vermeld, kunt u kiezen welke apparaten worden opgenomen in de periodieke scan.</span><span class="sxs-lookup"><span data-stu-id="879c3-190">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="879c3-191">Als u het weergeven van de scanresultaten overslaat, worden alle geconfigureerde IP-adressen toegevoegd aan de netwerkbeoordelings taak (ongeacht de reactie van het apparaat).</span><span class="sxs-lookup"><span data-stu-id="879c3-191">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="879c3-192">De scanresultaten kunnen ook worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="879c3-192">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="879c3-193">Apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="879c3-193">Device inventory</span></span>

<span data-ttu-id="879c3-194">Nieuw ontdekte apparaten worden weergegeven onder het nieuwe tabblad **Netwerkapparaten** op de **pagina Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="879c3-194">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="879c3-195">Het kan maximaal twee uur duren nadat u een beoordelings taak hebt toegevoegd totdat de apparaten zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="879c3-195">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="879c3-196">![Sectie Netwerkapparaten in de apparaatvoorraad](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="879c3-196">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="879c3-197">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="879c3-197">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="879c3-198">Installatie van netwerkscanner is mislukt</span><span class="sxs-lookup"><span data-stu-id="879c3-198">Network scanner installation has failed</span></span>

<span data-ttu-id="879c3-199">Controleer of de vereiste URL's zijn toegevoegd aan de toegestane domeinen in uw firewallinstellingen.</span><span class="sxs-lookup"><span data-stu-id="879c3-199">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="879c3-200">Zorg er ook voor dat proxy-instellingen zijn geconfigureerd zoals beschreven in Instellingen voor [apparaatproxy en internetverbinding configureren.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="879c3-200">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="879c3-201">De Microsoft.com/devicelogin webpagina is niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="879c3-201">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="879c3-202">Controleer of de vereiste URL's zijn toegevoegd aan de toegestane domeinen in uw firewall.</span><span class="sxs-lookup"><span data-stu-id="879c3-202">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="879c3-203">Zorg er ook voor dat proxy-instellingen zijn geconfigureerd zoals beschreven in Instellingen voor [apparaatproxy en internetverbinding configureren.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="879c3-203">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="879c3-204">Netwerkapparaten worden na enkele uren niet weergegeven in de apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="879c3-204">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="879c3-205">De scanresultaten moeten enkele uren na de eerste scan worden bijgewerkt na het voltooien van de configuratie van de beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="879c3-205">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="879c3-206">Als apparaten nog steeds niet worden weergegeven, controleert u of de service 'MdatpNetworkScanService' wordt uitgevoerd op uw beoordelingsapparaten, waarop u de netwerkscanner hebt geïnstalleerd, en voert u een 'Scan uitvoeren' uit in de desbetreffende configuratie van de beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="879c3-206">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="879c3-207">Als u na 5 minuten nog steeds geen resultaten krijgt, start u de service opnieuw.</span><span class="sxs-lookup"><span data-stu-id="879c3-207">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="879c3-208">Apparaten die voor het laatst zijn gezien, zijn langer dan 24 uur</span><span class="sxs-lookup"><span data-stu-id="879c3-208">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="879c3-209">Controleer of de scanner correct wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="879c3-209">Validate that the scanner is running properly.</span></span> <span data-ttu-id="879c3-210">Ga vervolgens naar de scandefinitie en selecteer 'Test uitvoeren'.</span><span class="sxs-lookup"><span data-stu-id="879c3-210">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="879c3-211">Controleer welke foutberichten van de betreffende IP-adressen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="879c3-211">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="879c3-212">Vereist Threat and Vulnerability Management gebruikersmachtiging</span><span class="sxs-lookup"><span data-stu-id="879c3-212">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="879c3-213">Registratie is voltooid met een fout: 'Het lijkt erop dat u niet over voldoende machtigingen voor het toevoegen van een nieuwe agent hebt.</span><span class="sxs-lookup"><span data-stu-id="879c3-213">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="879c3-214">De vereiste machtiging is 'Beveiligingsinstellingen beheren in het Beveiligingscentrum'.</span><span class="sxs-lookup"><span data-stu-id="879c3-214">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="879c3-215">Druk op een toets om af te sluiten.</span><span class="sxs-lookup"><span data-stu-id="879c3-215">Press any key to exit.</span></span>

<span data-ttu-id="879c3-216">Vraag de systeembeheerder u de vereiste machtigingen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="879c3-216">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="879c3-217">U kunt ook een ander relevant lid vragen u te helpen bij het aanmeldingsproces door hen de aanmeldingscode en koppeling te geven.</span><span class="sxs-lookup"><span data-stu-id="879c3-217">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="879c3-218">Registratieproces mislukt met behulp van de opgegeven koppeling in de opdrachtregel in het registratieproces</span><span class="sxs-lookup"><span data-stu-id="879c3-218">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="879c3-219">Probeer een andere browser of kopieer de aanmeldingskoppeling en -code naar een ander apparaat.</span><span class="sxs-lookup"><span data-stu-id="879c3-219">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="879c3-220">Tekst te klein of kan geen tekst uit opdrachtregel kopiëren</span><span class="sxs-lookup"><span data-stu-id="879c3-220">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="879c3-221">Wijzig de instellingen voor de opdrachtregel op uw apparaat om het kopiëren en wijzigen van de tekstgrootte toe te staan.</span><span class="sxs-lookup"><span data-stu-id="879c3-221">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="879c3-222">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="879c3-222">Related articles</span></span>

- [<span data-ttu-id="879c3-223">Apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="879c3-223">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="879c3-224">Geavanceerde functies configureren</span><span class="sxs-lookup"><span data-stu-id="879c3-224">Configure advanced features</span></span>](advanced-features.md)
