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
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062148"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="0189e-104">Netwerkapparaatdetectie en -vulnerability management</span><span class="sxs-lookup"><span data-stu-id="0189e-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0189e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0189e-105">**Applies to:**</span></span>

- [<span data-ttu-id="0189e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0189e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0189e-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="0189e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="0189e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0189e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0189e-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0189e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0189e-110">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="0189e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="0189e-111">De [netwerkapparaatdetectie-](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) en kwetsbaarheidsbeoordelingen Blog \( gepubliceerd op 04-13-2021 biedt inzicht in de nieuwe mogelijkheden voor netwerkapparaatdetectie \) in Defender voor  Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="0189e-111">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="0189e-112">In dit artikel vindt u een overzicht van de uitdaging waarop netwerkapparaatdetectie **is** ontworpen en gedetailleerde informatie over hoe u aan de slag gaat met deze nieuwe mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="0189e-112">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="0189e-113">Netwerkdetectiemogelijkheden zijn beschikbaar in de sectie **Apparaatvoorraad** van het Microsoft 365 beveiligingscentrum en Microsoft Defender-beveiligingscentrum consoles.</span><span class="sxs-lookup"><span data-stu-id="0189e-113">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="0189e-114">Een aangewezen Microsoft Defender voor Eindpunt-apparaat wordt in elk netwerksegment gebruikt om periodieke geverifieerde scans van vooraf geconfigureerde netwerkapparaten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0189e-114">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="0189e-115">Nadat deze zijn ontdekt, bieden de functies van Defender voor Endpoint Threat and Vulnerability Management geïntegreerde werkstromen voor het beveiligen van gevonden schakelopties, routers, WLAN-controllers, firewalls en VPN-gateways.</span><span class="sxs-lookup"><span data-stu-id="0189e-115">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="0189e-116">Zodra de netwerkapparaten zijn gevonden en geclassificeerd, kunnen beveiligingsbeheerders de meest recente beveiligingsaanbevelingen ontvangen en onlangs ontdekte beveiligingsproblemen bekijken op netwerkapparaten die in hun organisatie zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-116">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="0189e-117">Benadering</span><span class="sxs-lookup"><span data-stu-id="0189e-117">Approach</span></span>

<span data-ttu-id="0189e-118">Netwerkapparaten worden niet beheerd als standaard eindpunten, omdat Defender voor Eindpunt geen sensor heeft ingebouwd in de netwerkapparaten zelf.</span><span class="sxs-lookup"><span data-stu-id="0189e-118">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="0189e-119">Voor deze typen apparaten is een agentloze benadering vereist waarbij een externe scan de benodigde informatie van de apparaten haalt.</span><span class="sxs-lookup"><span data-stu-id="0189e-119">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="0189e-120">Afhankelijk van de netwerktopologie en -kenmerken worden met één apparaat of een paar apparaten die zijn aan boord van Microsoft Defender voor Eindpunt geverifieerde scans uitgevoerd van netwerkapparaten met SNMP (alleen-lezen).</span><span class="sxs-lookup"><span data-stu-id="0189e-120">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="0189e-121">Er zijn twee typen apparaten waar u rekening mee moet houden:</span><span class="sxs-lookup"><span data-stu-id="0189e-121">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="0189e-122">**Evaluatieapparaat:** een apparaat dat al is aan boord dat u gebruikt om de netwerkapparaten te scannen.</span><span class="sxs-lookup"><span data-stu-id="0189e-122">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="0189e-123">**Netwerkapparaten:** de netwerkapparaten die u wilt scannen en aan boord gaan.</span><span class="sxs-lookup"><span data-stu-id="0189e-123">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="0189e-124">Beveiligingsprobleembeheer voor netwerkapparaten</span><span class="sxs-lookup"><span data-stu-id="0189e-124">Vulnerability management for network devices</span></span> 

<span data-ttu-id="0189e-125">Zodra de netwerkapparaten zijn gevonden en geclassificeerd, kunnen beveiligingsbeheerders de meest recente beveiligingsaanbevelingen ontvangen en onlangs ontdekte beveiligingsproblemen bekijken op netwerkapparaten die in hun organisatie zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-125">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="0189e-126">Besturingssystemen die worden ondersteund</span><span class="sxs-lookup"><span data-stu-id="0189e-126">Operating systems that are supported</span></span>

<span data-ttu-id="0189e-127">De volgende besturingssystemen worden momenteel ondersteund:</span><span class="sxs-lookup"><span data-stu-id="0189e-127">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="0189e-128">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="0189e-128">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="0189e-129">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="0189e-129">Juniper JUNOS</span></span>
- <span data-ttu-id="0189e-130">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="0189e-130">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="0189e-131">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="0189e-131">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="0189e-132">In de tijd worden er meer netwerkleveranciers en besturingssysteem toegevoegd, op basis van gegevens die afkomstig zijn van klantgebruik.</span><span class="sxs-lookup"><span data-stu-id="0189e-132">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="0189e-133">Daarom wordt u aangeraden om al uw netwerkapparaten te configureren, zelfs als ze niet zijn opgegeven in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="0189e-133">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="0189e-134">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="0189e-134">How to get started</span></span>

<span data-ttu-id="0189e-135">De eerste stap is het selecteren van een apparaat dat de geverifieerde netwerkscans gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0189e-135">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="0189e-136">Beslis over een aan boord van Defender voor Endpoint-apparaat (client of server) dat een netwerkverbinding met de beheerpoort heeft voor de netwerkapparaten die u wilt scannen.</span><span class="sxs-lookup"><span data-stu-id="0189e-136">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="0189e-137">SNMP-verkeer tussen het Defender for Endpoint-evaluatieapparaat en de beoogde netwerkapparaten moet zijn toegestaan (bijvoorbeeld door de Firewall).</span><span class="sxs-lookup"><span data-stu-id="0189e-137">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="0189e-138">Bepaal welke netwerkapparaten worden beoordeeld op beveiligingsproblemen (bijvoorbeeld een Cisco-switch of een Firewall van Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="0189e-138">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="0189e-139">Zorg ervoor dat alleen-lezen SNMP is ingeschakeld op alle geconfigureerde netwerkapparaten, zodat het defender for Endpoint-beoordelingsapparaat de geconfigureerde netwerkapparaten kan query's uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0189e-139">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="0189e-140">'SNMP write' is niet nodig voor de juiste functionaliteit van deze functie.</span><span class="sxs-lookup"><span data-stu-id="0189e-140">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="0189e-141">Verkrijg de IP-adressen van de netwerkapparaten die moeten worden gescand (of de subnetten waar deze apparaten worden geïmplementeerd).</span><span class="sxs-lookup"><span data-stu-id="0189e-141">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="0189e-142">Verkrijg de SNMP-referenties van de netwerkapparaten (bijvoorbeeld: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="0189e-142">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="0189e-143">U moet de referenties verstrekken bij het configureren van een nieuwe beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="0189e-143">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="0189e-144">Configuratie van proxyclient: Er is geen extra configuratie vereist, anders dan de proxyvereisten voor defender voor eindpuntapparaat.</span><span class="sxs-lookup"><span data-stu-id="0189e-144">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="0189e-145">Als u wilt toestaan dat de netwerkscanner wordt geverifieerd en correct werkt, is het essentieel dat u de volgende domeinen/URL's toevoegt:</span><span class="sxs-lookup"><span data-stu-id="0189e-145">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="0189e-146">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="0189e-146">login.windows.net</span></span>  
    - <span data-ttu-id="0189e-147">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="0189e-147">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="0189e-148">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="0189e-148">login.microsoftonline.com</span></span>
    - <span data-ttu-id="0189e-149">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="0189e-149">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="0189e-150">Niet alle URL's worden opgegeven in de lijst met gedocumenteerde gegevensverzamelingen van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="0189e-150">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="0189e-151">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="0189e-151">Permissions</span></span>

<span data-ttu-id="0189e-152">Als u evaluatietaken wilt configureren, is de volgende optie voor gebruikersmachtiging vereist: **Beveiligingsinstellingen beheren in het Beveiligingscentrum.**</span><span class="sxs-lookup"><span data-stu-id="0189e-152">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="0189e-153">U kunt de machtiging vinden door naar Instellingen  >  **Rollen.**</span><span class="sxs-lookup"><span data-stu-id="0189e-153">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="0189e-154">Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer voor meer informatie.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0189e-154">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="0189e-155">De netwerkscanner installeren</span><span class="sxs-lookup"><span data-stu-id="0189e-155">Install the network scanner</span></span>

1. <span data-ttu-id="0189e-156">Ga naar **Microsoft 365**  >  **beveiligingstaken Instellingen**  >  **Endpoints**  >  **Assessment jobs** (onder **Netwerkbeoordelingen).**</span><span class="sxs-lookup"><span data-stu-id="0189e-156">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="0189e-157">Ga in Microsoft Defender-beveiligingscentrum naar de pagina Instellingen > Taken beoordelen.</span><span class="sxs-lookup"><span data-stu-id="0189e-157">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="0189e-158">Download de netwerkscanner en installeer deze op het aangewezen defender voor eindpuntbeoordelingsapparaat.</span><span class="sxs-lookup"><span data-stu-id="0189e-158">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0189e-159">![Knop Scanner downloaden](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="0189e-159">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="0189e-160">Installatie van netwerkscanners & registratie</span><span class="sxs-lookup"><span data-stu-id="0189e-160">Network scanner installation & registration</span></span>

<span data-ttu-id="0189e-161">Het aanmeldingsproces kan worden voltooid op het aangewezen beoordelingsapparaat zelf of op een ander apparaat (bijvoorbeeld uw persoonlijke clientapparaat).</span><span class="sxs-lookup"><span data-stu-id="0189e-161">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="0189e-162">Het registratieproces van de netwerkscanner voltooien:</span><span class="sxs-lookup"><span data-stu-id="0189e-162">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="0189e-163">Kopieer en volg de URL die op de opdrachtregel wordt weergegeven en gebruik de meegeleverde installatiecode om het registratieproces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0189e-163">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0189e-164">Mogelijk moet u de instellingen voor opdrachtprompt wijzigen om de URL te kunnen kopiëren.</span><span class="sxs-lookup"><span data-stu-id="0189e-164">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="0189e-165">Voer de code in en meld u aan met een Microsoft-account met de machtiging Defender voor eindpunt genaamd 'Beveiligingsinstellingen beheren in beveiligingscentrum'.</span><span class="sxs-lookup"><span data-stu-id="0189e-165">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="0189e-166">Wanneer u klaar bent, ziet u een bericht waarin wordt bevestigd dat u zich hebt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="0189e-166">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="0189e-167">Een nieuwe evaluatieklus configureren</span><span class="sxs-lookup"><span data-stu-id="0189e-167">Configure a new assessment job</span></span>  

<span data-ttu-id="0189e-168">Selecteer op de pagina **Evaluatietaken** in Instellingen de optie **Netwerkbeoordelingstaken toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0189e-168">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="0189e-169">Volg het set-upproces om netwerkapparaten te kiezen die regelmatig moeten worden gescand en toegevoegd aan de apparaatvoorraad.</span><span class="sxs-lookup"><span data-stu-id="0189e-169">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="0189e-170">Als u duplicatie van apparaten in de netwerkapparaatvoorraad wilt voorkomen, moet u ervoor zorgen dat elk IP-adres slechts eenmaal is geconfigureerd op meerdere beoordelingsapparaten.</span><span class="sxs-lookup"><span data-stu-id="0189e-170">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0189e-171">![Knop Netwerkbeoordelingsbaan toevoegen](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="0189e-171">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="0189e-172">Een netwerkbeoordelingsbaan toevoegen:</span><span class="sxs-lookup"><span data-stu-id="0189e-172">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="0189e-173">Kies de naam 'Beoordelingsbaan' en het 'Assessment-apparaat' waarop de netwerkscanner is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-173">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="0189e-174">Dit apparaat voert de periodieke geverifieerde scans uit.</span><span class="sxs-lookup"><span data-stu-id="0189e-174">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="0189e-175">Voeg IP-adressen toe van doelnetwerkapparaten die moeten worden gescand (of de subnetten waar deze apparaten worden geïmplementeerd).</span><span class="sxs-lookup"><span data-stu-id="0189e-175">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="0189e-176">Voeg vereiste SNMP-referenties van de doelnetwerkapparaten toe.</span><span class="sxs-lookup"><span data-stu-id="0189e-176">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="0189e-177">Sla de nieuw geconfigureerde netwerkbeoordelings taak op om de periodieke netwerkscan te starten.</span><span class="sxs-lookup"><span data-stu-id="0189e-177">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="0189e-178">Netwerkapparaten scannen en toevoegen</span><span class="sxs-lookup"><span data-stu-id="0189e-178">Scan and add network devices</span></span>

<span data-ttu-id="0189e-179">Tijdens het instellen kunt u een een keer testen om te controleren of:</span><span class="sxs-lookup"><span data-stu-id="0189e-179">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="0189e-180">Er is verbinding tussen het defender voor eindpuntbeoordelingsapparaat en de geconfigureerde doelnetwerkapparaten.</span><span class="sxs-lookup"><span data-stu-id="0189e-180">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="0189e-181">De geconfigureerde SNMP-referenties zijn correct.</span><span class="sxs-lookup"><span data-stu-id="0189e-181">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="0189e-182">Elk beoordelingsapparaat kan maximaal 1500 geslaagde IP-adressen scannen.</span><span class="sxs-lookup"><span data-stu-id="0189e-182">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="0189e-183">Als u bijvoorbeeld 10 verschillende subnetten scant waarbij slechts 100 IP-adressen succesvolle resultaten opleveren, kunt u 1.400 EXTRA IP-adressen scannen van andere subnetten op hetzelfde beoordelingsapparaat.</span><span class="sxs-lookup"><span data-stu-id="0189e-183">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="0189e-184">Als er meerdere IP-adresbereiken/subnetten moeten worden gescand, duurt het enkele minuten voordat de testresultaten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-184">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="0189e-185">Er is een testscan beschikbaar voor maximaal 1.024 adressen.</span><span class="sxs-lookup"><span data-stu-id="0189e-185">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="0189e-186">Wanneer de resultaten worden vermeld, kunt u kiezen welke apparaten worden opgenomen in de periodieke scan.</span><span class="sxs-lookup"><span data-stu-id="0189e-186">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="0189e-187">Als u het weergeven van de scanresultaten overslaat, worden alle geconfigureerde IP-adressen toegevoegd aan de netwerkbeoordelings taak (ongeacht de reactie van het apparaat).</span><span class="sxs-lookup"><span data-stu-id="0189e-187">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="0189e-188">De scanresultaten kunnen ook worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-188">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="0189e-189">Apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="0189e-189">Device inventory</span></span>

<span data-ttu-id="0189e-190">Nieuw ontdekte apparaten worden weergegeven onder het nieuwe tabblad **Netwerkapparaten** op de **pagina Apparaatvoorraad.**</span><span class="sxs-lookup"><span data-stu-id="0189e-190">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="0189e-191">Het kan maximaal twee uur duren nadat u een beoordelings taak hebt toegevoegd totdat de apparaten zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0189e-191">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0189e-192">![Sectie Netwerkapparaten in de apparaatvoorraad](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="0189e-192">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0189e-193">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="0189e-193">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="0189e-194">Installatie van netwerkscanner is mislukt</span><span class="sxs-lookup"><span data-stu-id="0189e-194">Network scanner installation has failed</span></span>

<span data-ttu-id="0189e-195">Controleer of de vereiste URL's zijn toegevoegd aan de toegestane domeinen in uw firewallinstellingen.</span><span class="sxs-lookup"><span data-stu-id="0189e-195">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="0189e-196">Zorg er ook voor dat proxy-instellingen zijn geconfigureerd zoals beschreven in Instellingen voor [apparaatproxy en internetverbinding configureren.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="0189e-196">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="0189e-197">De Microsoft.com/devicelogin webpagina is niet weergegeven</span><span class="sxs-lookup"><span data-stu-id="0189e-197">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="0189e-198">Controleer of de vereiste URL's zijn toegevoegd aan de toegestane domeinen in uw firewall.</span><span class="sxs-lookup"><span data-stu-id="0189e-198">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="0189e-199">Zorg er ook voor dat proxy-instellingen zijn geconfigureerd zoals beschreven in Instellingen voor [apparaatproxy en internetverbinding configureren.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="0189e-199">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="0189e-200">Netwerkapparaten worden na enkele uren niet weergegeven in de apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="0189e-200">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="0189e-201">De scanresultaten moeten enkele uren na de eerste scan worden bijgewerkt na het voltooien van de configuratie van de beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="0189e-201">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="0189e-202">Als apparaten nog steeds niet worden weergegeven, controleert u of de service 'MdatpNetworkScanService' wordt uitgevoerd op uw beoordelingsapparaten, waarop u de netwerkscanner hebt geïnstalleerd, en voert u een 'Scan uitvoeren' uit in de desbetreffende configuratie van de beoordelingsbaan.</span><span class="sxs-lookup"><span data-stu-id="0189e-202">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="0189e-203">Als u na 5 minuten nog steeds geen resultaten krijgt, start u de service opnieuw.</span><span class="sxs-lookup"><span data-stu-id="0189e-203">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="0189e-204">Apparaten die voor het laatst zijn gezien, zijn langer dan 24 uur</span><span class="sxs-lookup"><span data-stu-id="0189e-204">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="0189e-205">Controleer of de scanner correct wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0189e-205">Validate that the scanner is running properly.</span></span> <span data-ttu-id="0189e-206">Ga vervolgens naar de scandefinitie en selecteer 'Test uitvoeren'.</span><span class="sxs-lookup"><span data-stu-id="0189e-206">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="0189e-207">Controleer welke foutberichten van de betreffende IP-adressen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="0189e-207">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="0189e-208">Vereist Threat and Vulnerability Management gebruikersmachtiging</span><span class="sxs-lookup"><span data-stu-id="0189e-208">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="0189e-209">Registratie is voltooid met een fout: 'Het lijkt erop dat u niet over voldoende machtigingen voor het toevoegen van een nieuwe agent hebt.</span><span class="sxs-lookup"><span data-stu-id="0189e-209">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="0189e-210">De vereiste machtiging is 'Beveiligingsinstellingen beheren in het Beveiligingscentrum'.</span><span class="sxs-lookup"><span data-stu-id="0189e-210">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="0189e-211">Druk op een toets om af te sluiten.</span><span class="sxs-lookup"><span data-stu-id="0189e-211">Press any key to exit.</span></span>

<span data-ttu-id="0189e-212">Vraag de systeembeheerder u de vereiste machtigingen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="0189e-212">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="0189e-213">U kunt ook een ander relevant lid vragen u te helpen bij het aanmeldingsproces door hen de aanmeldingscode en koppeling te geven.</span><span class="sxs-lookup"><span data-stu-id="0189e-213">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="0189e-214">Registratieproces mislukt met behulp van de opgegeven koppeling in de opdrachtregel in het registratieproces</span><span class="sxs-lookup"><span data-stu-id="0189e-214">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="0189e-215">Probeer een andere browser of kopieer de aanmeldingskoppeling en -code naar een ander apparaat.</span><span class="sxs-lookup"><span data-stu-id="0189e-215">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="0189e-216">Tekst te klein of kan geen tekst uit opdrachtregel kopiëren</span><span class="sxs-lookup"><span data-stu-id="0189e-216">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="0189e-217">Wijzig de instellingen voor de opdrachtregel op uw apparaat om het kopiëren en wijzigen van de tekstgrootte toe te staan.</span><span class="sxs-lookup"><span data-stu-id="0189e-217">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0189e-218">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0189e-218">Related articles</span></span>

- [<span data-ttu-id="0189e-219">Apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="0189e-219">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="0189e-220">Geavanceerde functies configureren</span><span class="sxs-lookup"><span data-stu-id="0189e-220">Configure advanced features</span></span>](advanced-features.md)
