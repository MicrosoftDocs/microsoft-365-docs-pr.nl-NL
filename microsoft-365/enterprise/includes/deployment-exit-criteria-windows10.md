<a name="crit-windows10-step1"></a>
### <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="5e013-101">Vereist: uw Microsoft 365-domeinen zijn toegevoegd en gecontroleerd</span><span class="sxs-lookup"><span data-stu-id="5e013-101">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="5e013-102">De Azure AD-tenant voor uw Office 365- en Intune-abonnementen is geconfigureerd met uw internetdomeinnamen (zoals contoso.com), in plaats van alleen een domeinnaam die "onmicrosoft.com" bevat.</span><span class="sxs-lookup"><span data-stu-id="5e013-102">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="5e013-103">Als u dit niet doet, bent u beperkt in de verificatiemethoden die u kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="5e013-103">If you do not do so, you will be limited in the authentication methods that you can configure.</span></span> <span data-ttu-id="5e013-104">Pass-through en federatieve verificatie kunnen bijvoorbeeld niet de domeinnaam 'onmicrosoft.com' gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5e013-104">For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="5e013-105">[Stap 1](../windows10-prepare-your-org.md) kan u bij deze optie desgewenst helpen.</span><span class="sxs-lookup"><span data-stu-id="5e013-105">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this requirement.</span></span>

### <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="5e013-106">Optioneel: uw gebruikers worden toegevoegd en gelicentieerd</span><span class="sxs-lookup"><span data-stu-id="5e013-106">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="5e013-107">De accounts die overeenkomen met uw gebruikers worden toegevoegd, ofwel rechtstreeks aan uw Azure AD-tenant voor uw Office 365- en Intune-abonnementen, of door adreslijstsynchronisatie vanuit uw on-premises Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5e013-107">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="5e013-108">Zodra de gebruikers zijn toegevoegd, kunt u aan hen Microsoft 365 Enterprise-licenties toewijzen, hetzij rechtstreeks als globale of gebruikersbeheerder, of automatisch via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="5e013-108">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="5e013-109">[Stap 1](../windows10-prepare-your-org.md) kan u bij deze optie desgewenst helpen.</span><span class="sxs-lookup"><span data-stu-id="5e013-109">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

### <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="5e013-110">Optioneel: diagnostiek is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="5e013-110">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="5e013-111">U hebt instellingen voor diagnostische gegevens ingeschakeld met Groepsbeleid, Microsoft Intune, de Register-editor of met de opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="5e013-111">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="5e013-112">[Stap 1](../windows10-prepare-your-org.md) kan u bij deze optie desgewenst helpen.</span><span class="sxs-lookup"><span data-stu-id="5e013-112">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
### <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="5e013-113">Vereist voor in-place upgrade: een Configuration Manager-takenreeks gemaakt voor een besturingssysteemimplementatie</span><span class="sxs-lookup"><span data-stu-id="5e013-113">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="5e013-114">Om een takenreeks van Configuration Manager te starten om een interne upgrade uit te voeren op een apparaat met Windows 7 of Windows 8.1, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="5e013-114">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="5e013-115">Stel het juiste gegevensniveau voor diagnostische gegevens van Windows in</span><span class="sxs-lookup"><span data-stu-id="5e013-115">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="5e013-116">Verifieer de gereedheid voor een upgrade van Windows</span><span class="sxs-lookup"><span data-stu-id="5e013-116">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="5e013-117">Maak een Configuration Manager-takenreeks met een apparaatverzameling en een besturingssysteemimplementatie met een Windows 10 OS-installatiekopie</span><span class="sxs-lookup"><span data-stu-id="5e013-117">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="5e013-118">Zodra dit is gebeurd, kunt u in-place upgrades uitvoeren op apparaten die gereed zijn om Windows te upgraden.</span><span class="sxs-lookup"><span data-stu-id="5e013-118">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows.</span></span> <span data-ttu-id="5e013-119">Upgrade zoveel mogelijk apparaten met Windows 7 en Windows 8.1 om het maximale uit Microsoft 365 Enterprise te halen.</span><span class="sxs-lookup"><span data-stu-id="5e013-119">To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="5e013-120">Elk apparaat met Windows 10 Enterprise kan profiteren van de voordelen van de geïntegreerde oplossing van Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5e013-120">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="5e013-121">Op de overige apparaten met Windows 7 of Windows 8.1 kunt u geen gebruikmaken van de met de cloud verbonden technologieën en geavanceerde beveiligingsfuncties van Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5e013-121">The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="5e013-122">Via [Stap 2](../windows10-deploy-inplaceupgrade.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="5e013-122">If needed, [Step 2](../windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
### <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="5e013-123">Vereist voor nieuwe apparaten: geconfigureerde Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="5e013-123">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="5e013-124">Voor het gebruik van Windows Autopilot om Windows 10 Enterprise te implementeren en aan te passen op een nieuw apparaat, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="5e013-124">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="5e013-125">Stel het juiste gegevensniveau voor diagnostische gegevens van Windows in</span><span class="sxs-lookup"><span data-stu-id="5e013-125">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="5e013-126">Configureer de vereisten voor Windows Autopilot, waaronder:</span><span class="sxs-lookup"><span data-stu-id="5e013-126">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="5e013-127">Apparaatregistratie en OOBE-aanpassing</span><span class="sxs-lookup"><span data-stu-id="5e013-127">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="5e013-128">Bedrijfshuisstijl voor OOBE</span><span class="sxs-lookup"><span data-stu-id="5e013-128">Company branding for OOBE</span></span>
   - <span data-ttu-id="5e013-129">Automatische MDM-inschrijving in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5e013-129">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="5e013-130">Netwerkverbindingen met cloudservices die worden gebruikt door Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="5e013-130">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="5e013-131">Apparaten die vooraf zijn geïnstalleerd met Windows 10, versie 1703 of hoger</span><span class="sxs-lookup"><span data-stu-id="5e013-131">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="5e013-132">Selecteer het Windows Autopilot Deployment Program voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="5e013-132">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="5e013-133">Zodra de Windows Autopilot-configuratie aanwezig is, kunt u deze gebruiken om Windows 10 Enterprise te configureren en aan te passen voor de kant-en-klare ervaring (OOBE) voor:</span><span class="sxs-lookup"><span data-stu-id="5e013-133">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="5e013-134">Nieuwe apparaten</span><span class="sxs-lookup"><span data-stu-id="5e013-134">New devices</span></span>
- <span data-ttu-id="5e013-135">Apparaten die al een kant-en-klare installatie van uw organisatie hebben voltooid.</span><span class="sxs-lookup"><span data-stu-id="5e013-135">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="5e013-136">Windows Autopilot configureert het apparaat en verbindt het met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e013-136">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="5e013-137">Zonder Windows Autopilot moet u nieuwe apparaten handmatig configureren, inclusief de verbinding met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5e013-137">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="5e013-138">Via [Stap 3](../windows10-deploy-autopilot.md) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="5e013-138">If needed, [Step 3](../windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
### <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="5e013-139">Optioneel: u gebruikt Windows Analytics Device Health om uw Windows 10 Enterprise-apparaten te bewaken</span><span class="sxs-lookup"><span data-stu-id="5e013-139">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="5e013-140">U hebt de gegevens van Device Health gebruikt om de status van apparaten te controleren en om problemen te ontdekken en op te lossen die gevolgen hebben voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5e013-140">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users.</span></span> <span data-ttu-id="5e013-141">Door snel problemen met eindgebruikers aan te pakken, kunt u uw ondersteuningskosten verlagen en uw gebruikers laten zien dat IT zich inzet voor Windows 10 Enterprise, wat de acceptatie binnen uw organisatie kan stimuleren.</span><span class="sxs-lookup"><span data-stu-id="5e013-141">Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="5e013-142">[Stap 4](../windows10-enable-windows-analytics.md) kan u bij deze optie desgewenst helpen.</span><span class="sxs-lookup"><span data-stu-id="5e013-142">If needed, [Step 4](../windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
### <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="5e013-143">Vereist: u gebruikt Windows Defender Antivirus of uw eigen antimalware-oplossing</span><span class="sxs-lookup"><span data-stu-id="5e013-143">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="5e013-144">U hebt Windows Defender Antivirus of uw eigen antivirusoplossing geïmplementeerd om uw apparaten met Windows 10 Enterprise te beveiligen tegen schadelijke software.</span><span class="sxs-lookup"><span data-stu-id="5e013-144">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software.</span></span> <span data-ttu-id="5e013-145">Als u Windows Defender Antivirus heeft geïmplementeerd, heeft u een rapportagemethode geïmplementeerd, zoals Microsoft Endpoint Configuration Manager of Microsoft Intune, om antivirusgebeurtenissen en -activiteiten te monitoren.</span><span class="sxs-lookup"><span data-stu-id="5e013-145">If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="5e013-146">Via [Stap 5](../windows10-enable-security-features.md#windows10-sec-av) kunt u zo nodig aan deze vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="5e013-146">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
### <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="5e013-147">Vereist: u gebruikt Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="5e013-147">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="5e013-148">U hebt Windows Defender Exploit Guard ingezet om uw apparaten met Windows 10 Enterprise te beschermen tegen inbraak en heeft een rapportagemethode geïmplementeerd, zoals Configuration Manager of Microsoft Intune, om inbraakgebeurtenissen en -activiteiten te bewaken.</span><span class="sxs-lookup"><span data-stu-id="5e013-148">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="5e013-149">[Stap 5](../windows10-enable-security-features.md#windows10-sec-eg) kan u bij deze optie desgewenst helpen.</span><span class="sxs-lookup"><span data-stu-id="5e013-149">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
### <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="5e013-150">Vereist: u gebruikt Microsoft Defender Advanced Threat Protection (alleen Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="5e013-150">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="5e013-151">U hebt Microsoft Defender Advanced Threat Protection (ATP) ingezet om geavanceerde bedreigingen tegen uw netwerk en apparaten met Windows 10 Enterprise te detecteren, te onderzoeken en erop te reageren.</span><span class="sxs-lookup"><span data-stu-id="5e013-151">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="5e013-152">U hebt Microsoft Defender ATP als optie geïntegreerd met andere tools om de mogelijkheden uit te breiden.</span><span class="sxs-lookup"><span data-stu-id="5e013-152">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="5e013-153">[Stap 5](../windows10-enable-security-features.md#windows10-sec-atp) kan u bij deze optie desgewenst helpen.</span><span class="sxs-lookup"><span data-stu-id="5e013-153">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>
