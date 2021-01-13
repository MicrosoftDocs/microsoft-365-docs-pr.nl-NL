---
title: Nieuwe Microsoft Edge-apps
description: Hoe de nieuwe Edge-browser wordt geïmplementeerd en bijgewerkt
keywords: browser, Microsoft beheerde desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841337"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="bdaac-104">Nieuwe Microsoft Edge-app</span><span class="sxs-lookup"><span data-stu-id="bdaac-104">New Microsoft Edge app</span></span>

<span data-ttu-id="bdaac-105">De nieuwe [browser Microsoft Edge](https://www.microsoft.com/edge) biedt wereldwijde prestaties met meer privacy, meer productiviteit en meer tijdens het browsen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="bdaac-106">Microsoft Managed Desktop biedt een openbare preview van de implementatie van de nieuwe Edge-browser in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="bdaac-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="bdaac-107">Eerste implementatie</span><span class="sxs-lookup"><span data-stu-id="bdaac-107">Initial deployment</span></span>

<span data-ttu-id="bdaac-108">Als u uw Microsoft Managed Desktop-apparaten wilt migreren naar de nieuwe Microsoft Edge-browser, kunt u een IT-ondersteunings ticket via de beheerde bureaublad portal van Microsoft opslaan.</span><span class="sxs-lookup"><span data-stu-id="bdaac-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="bdaac-109">We implementeren de Edge stabiel kanaal naar de test groep wanneer u het ticket bijwerkt en het vervolgens in elke volgende implementatiegroep elke 24 uur implementeren.</span><span class="sxs-lookup"><span data-stu-id="bdaac-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="bdaac-110">Als u de implementatie wilt onderbreken, moet u een ander ticket vragen om te worden bewaard.</span><span class="sxs-lookup"><span data-stu-id="bdaac-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="bdaac-111">Het [bèta kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is ook beschikbaar wanneer u daarom aanvraag onderneemt voor een representatieve validering binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bdaac-111">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="bdaac-112">Microsoft Managed Desktop implementeert de toepassing als vereist voor de test en de eerste groepen, zodat al deze gebruikers het bèta-kanaal hebben, naast het stabiele kanaal.</span><span class="sxs-lookup"><span data-stu-id="bdaac-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="bdaac-113">Voor andere gebruikers die toegang hebben tot het Beta-kanaal, voegt u deze toe aan de groep nieuwe gebruikers van de **moderne werkplek** en de gebruikers die deze installeren via de bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="bdaac-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="bdaac-114">Updates voor Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bdaac-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="bdaac-115">Microsoft Managed Desktop implementeert het [stabiele kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) van Microsoft Edge, dat automatisch wordt bijgewerkt, telkens zes weken.</span><span class="sxs-lookup"><span data-stu-id="bdaac-115">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="bdaac-116">Updates op het stabiele kanaal worden [progressief](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) uitgeworpen door de productgroep Microsoft Edge om ervoor te zorgen dat ze de beste ervaring voor klanten zijn.</span><span class="sxs-lookup"><span data-stu-id="bdaac-116">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="bdaac-117">Het [bèta kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) wordt geïmplementeerd op apparaten in zowel de test als de eerste groepen voor de representatieve validatie binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="bdaac-117">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="bdaac-118">Dit kanaal wordt volledig ondersteund en wordt telkens zes weken automatisch bijgewerkt met nieuwe functies.</span><span class="sxs-lookup"><span data-stu-id="bdaac-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="bdaac-119">U kunt ervoor zorgen dat Microsoft Edge correct wordt bijgewerkt door de [Update beleidsregels](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)voor Microsoft Edge niet te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="bdaac-120">Instellingen die worden beheerd door Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="bdaac-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="bdaac-121">Microsoft Managed Desktop heeft een standaardreeks beleidsregels voor Microsoft Edge gemaakt om de browser te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="bdaac-122">De instellingen voor standaardbrowser zijn als volgt:</span><span class="sxs-lookup"><span data-stu-id="bdaac-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="bdaac-123">Microsoft Edge-extensies</span><span class="sxs-lookup"><span data-stu-id="bdaac-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="bdaac-124">Met de beveiligings basis voor Microsoft Edge on Microsoft Managed Desktop devices stelt u twee beleidsregels in om alle chroom extensies en beveiligde gebruikers uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="bdaac-125">Als u extensies wilt inschakelen en implementeren in uw omgeving, raadpleegt u instellingen die u beheert.</span><span class="sxs-lookup"><span data-stu-id="bdaac-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="bdaac-126">Extensies installeren blokkeringslijst geplaatst</span><span class="sxs-lookup"><span data-stu-id="bdaac-126">Extension installation blocklist</span></span>
<span data-ttu-id="bdaac-127">**Standaardwaarde:** Al</span><span class="sxs-lookup"><span data-stu-id="bdaac-127">**Default value:** All</span></span>

<span data-ttu-id="bdaac-128">Microsoft Managed Desktop stelt dit beleid in om te voorkomen dat chroom extensies worden geïnstalleerd op beheerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="bdaac-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="bdaac-129">Er zijn bekende Risico's die zijn gekoppeld aan het Chroom-uitbreidings model, waaronder beveiliging tegen bescherming van gegevensverlies, privacy en andere Risico's waarmee apparaten kunnen worden aangetast.</span><span class="sxs-lookup"><span data-stu-id="bdaac-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="bdaac-130">Native berichten hosten op gebruikersniveau toestaan (geïnstalleerd zonder beheerdersmachtigingen)</span><span class="sxs-lookup"><span data-stu-id="bdaac-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="bdaac-131">**Standaardwaarde:** Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="bdaac-131">**Default value:** Disabled</span></span>

<span data-ttu-id="bdaac-132">Door dit beleid uit te schakelen, wordt Microsoft Edge alleen gebruikt voor de native Messaging-hosts die op systeemniveau zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="bdaac-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="bdaac-133">Hosts voor systeemeigen berichten maken deel uit van chroom extensies, zodat de browser kan communiceren met andere onderdelen van het eindpunt van gebruikers, waardoor diverse beveiligingskwesties worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="bdaac-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="bdaac-134">Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="bdaac-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="bdaac-135">Minimale TLS-versie</span><span class="sxs-lookup"><span data-stu-id="bdaac-135">Minimum TLS version</span></span>

<span data-ttu-id="bdaac-136">**Standaardwaarde:** Minimale TLS-1,2 ondersteund</span><span class="sxs-lookup"><span data-stu-id="bdaac-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="bdaac-137">Als u het minder veilige TLS 1,1 wilt gebruiken, kunt u een verzoek indienen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="bdaac-138">Gebruikers kunnen doorgaan op de pagina SSL-waarschuwing</span><span class="sxs-lookup"><span data-stu-id="bdaac-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="bdaac-139">**Standaardwaarde:** Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="bdaac-139">**Default value:** Disabled</span></span>

<span data-ttu-id="bdaac-140">We raden u aan deze instelling niet in te schakelen omdat gebruikers sites kunnen bezoeken met een TSL-fout.</span><span class="sxs-lookup"><span data-stu-id="bdaac-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="bdaac-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="bdaac-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="bdaac-142">Windows Defender SmartScreen configureren</span><span class="sxs-lookup"><span data-stu-id="bdaac-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="bdaac-143">**Standaardwaarde:** Enabled</span><span class="sxs-lookup"><span data-stu-id="bdaac-143">**Default value:** Enabled</span></span>

<span data-ttu-id="bdaac-144">Deze optie is standaard ingeschakeld om gebruikers te helpen beschermen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="bdaac-145">Windows Defender SmartScreen vraagt voor sites</span><span class="sxs-lookup"><span data-stu-id="bdaac-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="bdaac-146">**Standaardwaarde:** Enabled</span><span class="sxs-lookup"><span data-stu-id="bdaac-146">**Default value:** Enabled</span></span>

<span data-ttu-id="bdaac-147">U wordt aangeraden deze instelling uit te schakelen omdat gebruikers waarschuwingen negeren en doorgaan naar potentieel schadelijke sites.</span><span class="sxs-lookup"><span data-stu-id="bdaac-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="bdaac-148">Negeering van Windows Defender SmartScreen-waarschuwingen over downloads voorkomen</span><span class="sxs-lookup"><span data-stu-id="bdaac-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="bdaac-149">**Standaardwaarde:** Enabled</span><span class="sxs-lookup"><span data-stu-id="bdaac-149">**Default value:** Enabled</span></span>

<span data-ttu-id="bdaac-150">U wordt aangeraden deze instelling uit te schakelen omdat gebruikers waarschuwingen negeren en niet-geverifieerde downloads voltooien.</span><span class="sxs-lookup"><span data-stu-id="bdaac-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="bdaac-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="bdaac-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="bdaac-152">Standaardinstelling voor Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="bdaac-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="bdaac-153">**Standaardwaarde:** Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="bdaac-153">**Default value:** Disabled</span></span>

<span data-ttu-id="bdaac-154">We raden u niet aan gebruik te maken van Flash vanwege bijbehorende beveiligingsrisico's.</span><span class="sxs-lookup"><span data-stu-id="bdaac-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="bdaac-155">Als u nog steeds processen hebt die van Flash werken, stelt u het **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** -beleid in om Flash voor sites die nodig zijn, in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="bdaac-156">Als u een toegestane lijst met sites niet kunt bewaren voor gebruik van Flash, moet u een wijzigingsaanvraag indienen om de waarde te wijzigen om **te worden afgespeeld**, zodat gebruikers kunnen kiezen wanneer deze nodig zijn om Flash uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bdaac-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="bdaac-157">Wachtwoordbeheer</span><span class="sxs-lookup"><span data-stu-id="bdaac-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="bdaac-158">Het opslaan van wachtwoorden naar wachtwoordbeheer inschakelen</span><span class="sxs-lookup"><span data-stu-id="bdaac-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="bdaac-159">**Standaardwaarde:** Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="bdaac-159">**Default value:** Disabled</span></span>

<span data-ttu-id="bdaac-160">U wordt aangeraden gebruikers niet in staat te stellen om wachtwoorden op hun apparaat op te slaan.</span><span class="sxs-lookup"><span data-stu-id="bdaac-160">We do not recommend allowing users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="bdaac-161">Internet Explorer-modus in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bdaac-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="bdaac-162">Met de IE-modus op Microsoft Edge kunt u eenvoudig gebruikmaken van alle sites die uw organisatie nodig heeft in één browser.</span><span class="sxs-lookup"><span data-stu-id="bdaac-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="bdaac-163">Met de geïntegreerde toepassing van chroom voor sites die compatibel zijn met de chroom beeldrendering-engine, wordt de Trident MSHTML-engine van Internet Explorer 11 (IE11) gebruikt voor sites die geen of geen afhankelijkheden hebben van de IE-functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="bdaac-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="bdaac-164">[Meer informatie] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="bdaac-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="bdaac-165">Microsoft Managed Desktop schakelt standaard de Internet Explorer-modus voor uw apparaten in</span><span class="sxs-lookup"><span data-stu-id="bdaac-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="bdaac-166">Integratie van de Internet Explorer-modus</span><span class="sxs-lookup"><span data-stu-id="bdaac-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="bdaac-167">**Standaardwaarde:** De modus Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="bdaac-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="bdaac-168">Apparaten zijn standaard ingesteld op de modus Internet Explorer, maar u kunt ze instellen voor het openen van sites in een zelfstandig, Internet Explorer 11-venster.</span><span class="sxs-lookup"><span data-stu-id="bdaac-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="bdaac-169">Als u dit gedrag wilt wijzigen, moet u een ondersteuningsaanvraag indienen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-169">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="bdaac-170">Sites toevoegen aan de site lijst van de ondernemingsmodus</span><span class="sxs-lookup"><span data-stu-id="bdaac-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="bdaac-171">Voor sites die u wilt openen in de Internet Explorer-modus, moet u deze opnemen in de [lijst met bedrijfssites](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span><span class="sxs-lookup"><span data-stu-id="bdaac-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="bdaac-172">Het onderhoud en de implementatie van de ondernemings site lijst is uw eigen verantwoordelijkheid.</span><span class="sxs-lookup"><span data-stu-id="bdaac-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="bdaac-173">Voor meer informatie raadpleegt u [configureren met behulp van het site lijstbeleid Enterprise mode configureren](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="bdaac-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="bdaac-174">Andere instellingen</span><span class="sxs-lookup"><span data-stu-id="bdaac-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="bdaac-175">Site-isolatie inschakelen voor elke site</span><span class="sxs-lookup"><span data-stu-id="bdaac-175">Enable site isolation for every site</span></span>

<span data-ttu-id="bdaac-176">**Standaardwaarde:** Enabled</span><span class="sxs-lookup"><span data-stu-id="bdaac-176">**Default value:** Enabled</span></span>

<span data-ttu-id="bdaac-177">Wanneer dit beleid is ingeschakeld, kunnen gebruikers niet deelnemen aan het standaardgedrag waarbij de afzonderlijke sites in een eigen proces worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bdaac-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="bdaac-178">Ondersteunde verificatieschema's</span><span class="sxs-lookup"><span data-stu-id="bdaac-178">Supported authentication schemes</span></span>

<span data-ttu-id="bdaac-179">**Standaardwaarde:** NTLM, Negotiate</span><span class="sxs-lookup"><span data-stu-id="bdaac-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="bdaac-180">Microsoft Managed Desktop biedt geen ondersteuning voor basisverificatie en verificatieschema's.</span><span class="sxs-lookup"><span data-stu-id="bdaac-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="bdaac-181">De gegevens en instellingen van een andere browser automatisch importeren bij de eerste uitvoering</span><span class="sxs-lookup"><span data-stu-id="bdaac-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="bdaac-182">**Standaardwaarde:** Automatisch alle ondersteunde gegevenstypen en instellingen in de standaardbrowser importeren</span><span class="sxs-lookup"><span data-stu-id="bdaac-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="bdaac-183">Met deze beleidsinstelling wordt de eerste uitvoering van de ervaring overgeslagen en wordt de functie voor het importeren van de gebruikersinteractie overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="bdaac-184">De browser gegevens uit oudere versies van Microsoft Edge worden altijd Silent gemigreerd naar de eerste sessie, ongeacht deze instelling.</span><span class="sxs-lookup"><span data-stu-id="bdaac-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="bdaac-185">Instellingen die u beheert</span><span class="sxs-lookup"><span data-stu-id="bdaac-185">Settings you manage</span></span>

<span data-ttu-id="bdaac-186">U kunt alle instellingen voor Microsoft Edge die niet eerder zijn beschreven, implementeren met behulp van het Profielbeheer sjablonen in Microsoft intune.</span><span class="sxs-lookup"><span data-stu-id="bdaac-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="bdaac-187">Zie [Microsoft Edge-beleidsinstellingen met Microsoft intune configureren](https://docs.microsoft.com/deployedge/configure-edge-with-intune)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bdaac-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="bdaac-188">Als u een beleid wilt beoordelen dat nog niet is opgenomen in de beheersjablonen van Microsoft Edge in intune, kunt u aangepaste instellingen voor Windows 10-apparaten gebruiken in intune.</span><span class="sxs-lookup"><span data-stu-id="bdaac-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="bdaac-189">Specifieke Chrome-extensies inschakelen</span><span class="sxs-lookup"><span data-stu-id="bdaac-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="bdaac-190">De sjabloon beheerder biedt een instelling voor het implementeren van bepaalde Chrome-uitbreidingen met Microsoft intune.</span><span class="sxs-lookup"><span data-stu-id="bdaac-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="bdaac-191">U vindt het bestand in **computer configuratie > Microsoft Edge > extensies > de mogelijkheid om bepaalde extensies te installeren**.</span><span class="sxs-lookup"><span data-stu-id="bdaac-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="bdaac-192">Extensies op de achtergrond installeren</span><span class="sxs-lookup"><span data-stu-id="bdaac-192">Install extensions silently</span></span>

<span data-ttu-id="bdaac-193">U kunt ook de beheersjabloon gebruiken om Microsoft Edge te installeren om uitbreidingen te installeren zonder dat u een melding krijgt van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="bdaac-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="bdaac-194">U vindt het bestand in **computer configuratie > Microsoft Edge > extensies > bepalen welke extensies op de achtergrond worden geïnstalleerd**.</span><span class="sxs-lookup"><span data-stu-id="bdaac-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="bdaac-195">Updatebeleid voor Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bdaac-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="bdaac-196">U kunt ervoor zorgen dat Microsoft Edge correct wordt bijgewerkt door de [Update beleidsregels](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)voor Microsoft Edge niet te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bdaac-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="bdaac-197">Overig algemeen ondernemingsbeleid</span><span class="sxs-lookup"><span data-stu-id="bdaac-197">Other common enterprise policies</span></span>

<span data-ttu-id="bdaac-198">Microsoft Edge biedt een groot aantal andere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="bdaac-198">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="bdaac-199">Dit zijn enkele van de meest voorkomende versies:</span><span class="sxs-lookup"><span data-stu-id="bdaac-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="bdaac-200">Sites configureren in de lijst met ondernemings sites en de IE-modus</span><span class="sxs-lookup"><span data-stu-id="bdaac-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="bdaac-201">Instellingen voor opstarten, startpagina en nieuw tabblad configureren</span><span class="sxs-lookup"><span data-stu-id="bdaac-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="bdaac-202">Instellingen voor een surf spel configureren</span><span class="sxs-lookup"><span data-stu-id="bdaac-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="bdaac-203">Instellingen voor proxyserver configureren</span><span class="sxs-lookup"><span data-stu-id="bdaac-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

