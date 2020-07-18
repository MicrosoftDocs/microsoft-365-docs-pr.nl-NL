---
title: Nieuwe Microsoft Edge
description: ''
keywords: browser, Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 916ddaea2bc91c56944d4561771c1e807447d604
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170669"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="40d00-103">Nieuwe Microsoft Edge-app</span><span class="sxs-lookup"><span data-stu-id="40d00-103">New Microsoft Edge app</span></span>

<span data-ttu-id="40d00-104">De nieuwe [Microsoft Edge-browser](https://www.microsoft.com/edge) biedt prestaties van wereldklasse met meer privacy, meer productiviteit en meer waarde terwijl u bladert.</span><span class="sxs-lookup"><span data-stu-id="40d00-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="40d00-105">Microsoft Managed Desktop biedt een openbare preview van de implementatie van de nieuwe Edge-browser in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="40d00-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="40d00-106">Eerste implementatie</span><span class="sxs-lookup"><span data-stu-id="40d00-106">Initial deployment</span></span>

<span data-ttu-id="40d00-107">Als u uw Microsoft Managed Desktop-apparaten wilt migreren naar de nieuwe Microsoft Edge-browser, dient u een IT-ondersteuningsticket in via de Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="40d00-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="40d00-108">We implementeren het Edge Stable-kanaal naar de testgroep wanneer u het ticket indient en implementeren het vervolgens elke 24 uur in elke volgende implementatiegroep.</span><span class="sxs-lookup"><span data-stu-id="40d00-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="40d00-109">Als u de implementatie wilt onderbreken, dient u een ander ticket in waarin operations wordt gevraagd deze vast te houden.</span><span class="sxs-lookup"><span data-stu-id="40d00-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="40d00-110">Updates voor Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="40d00-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="40d00-111">Microsoft Managed Desktop implementeert het [stabiele kanaal](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) van Microsoft Edge, dat ongeveer elke zes weken automatisch wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="40d00-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="40d00-112">Updates op het Stable-kanaal worden [geleidelijk](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) uitgerold door de Microsoft Edge-productgroep om de beste ervaring voor klanten te garanderen.</span><span class="sxs-lookup"><span data-stu-id="40d00-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="40d00-113">Het Microsoft Edge Beta-kanaal is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="40d00-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="40d00-114">Wijzig het [microsoft Edge-updatebeleid](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)niet om ervoor te zorgen dat Microsoft Edge-updates correct worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="40d00-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="40d00-115">Instellingen beheerd door Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="40d00-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="40d00-116">Microsoft Managed Desktop heeft een standaardset beleidsregels gemaakt voor Microsoft Edge om de browser te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="40d00-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="40d00-117">De standaard browserinstellingen zijn als volgt:</span><span class="sxs-lookup"><span data-stu-id="40d00-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="40d00-118">Microsoft Edge-extensies</span><span class="sxs-lookup"><span data-stu-id="40d00-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="40d00-119">Met de beveiligingsbasislijn voor Microsoft Edge op Microsoft Managed Desktop-apparaten worden twee beleidsregels ingesteld om alle Chrome-extensies uit te schakelen en eindgebruikers te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="40d00-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="40d00-120">Zie Instellingen die u beheert als u extensies in uw omgeving wilt inschakelen en implementeren.</span><span class="sxs-lookup"><span data-stu-id="40d00-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="40d00-121">Blokkerlijst van extensie-installatie</span><span class="sxs-lookup"><span data-stu-id="40d00-121">Extension installation blocklist</span></span>
<span data-ttu-id="40d00-122">**Standaardwaarde:** Alle</span><span class="sxs-lookup"><span data-stu-id="40d00-122">**Default value:** All</span></span>

<span data-ttu-id="40d00-123">Microsoft Managed Desktop stelt dit beleid in om te voorkomen dat Chrome-extensies worden geïnstalleerd op beheerde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="40d00-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="40d00-124">Er zijn bekende risico's verbonden aan het Chromium-uitbreidingsmodel, waaronder bescherming tegen gegevensverlies, privacy en andere risico's die apparaten in gevaar kunnen brengen.</span><span class="sxs-lookup"><span data-stu-id="40d00-124">There are known risk sassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="40d00-125">Native messaging-hosts op gebruikersniveau toestaan (geïnstalleerd zonder beheerdersmachtigingen)</span><span class="sxs-lookup"><span data-stu-id="40d00-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="40d00-126">**Standaardwaarde:** Handicap</span><span class="sxs-lookup"><span data-stu-id="40d00-126">**Default value:** Disabled</span></span>

<span data-ttu-id="40d00-127">Door dit beleid uit te schakelen, gebruikt Microsoft Edge alleen native messaging-hosts die op systeemniveau zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="40d00-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="40d00-128">Native messaging hosts zijn een onderdeel van Chrome-extensies waarmee de browser kan communiceren met andere delen van het eindpunt van de gebruiker, waardoor een verscheidenheid aan beveiligingsproblemen ontstaat.</span><span class="sxs-lookup"><span data-stu-id="40d00-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="40d00-129">Secure Sockets Layer (SSL)</span><span class="sxs-lookup"><span data-stu-id="40d00-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="40d00-130">Minimale SSL-versie</span><span class="sxs-lookup"><span data-stu-id="40d00-130">Minimum SSL version</span></span>

<span data-ttu-id="40d00-131">**Standaardwaarde:** Minimaal TLS 1.2 ondersteund</span><span class="sxs-lookup"><span data-stu-id="40d00-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="40d00-132">Als u de minder veilige TLS 1.1 wilt gebruiken, u dit aanvragen.</span><span class="sxs-lookup"><span data-stu-id="40d00-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="40d00-133">Hiermee kunnen gebruikers verder gaan vanaf de SSL-waarschuwingspagina</span><span class="sxs-lookup"><span data-stu-id="40d00-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="40d00-134">**Standaardwaarde:** Handicap</span><span class="sxs-lookup"><span data-stu-id="40d00-134">**Default value:** Disabled</span></span>

<span data-ttu-id="40d00-135">We raden u af deze instelling in te schakelen, omdat gebruikers hiermee sites met SSL-fouten kunnen bezoeken.</span><span class="sxs-lookup"><span data-stu-id="40d00-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="40d00-136">Microsoft Defender-slim scherm</span><span class="sxs-lookup"><span data-stu-id="40d00-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="40d00-137">Microsoft Defender SmartScreen configureren</span><span class="sxs-lookup"><span data-stu-id="40d00-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="40d00-138">**Standaardwaarde:** Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="40d00-138">**Default value:** Enabled</span></span>

<span data-ttu-id="40d00-139">Standaard ingeschakeld om eindgebruikers te beschermen.</span><span class="sxs-lookup"><span data-stu-id="40d00-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="40d00-140">Microsoft Defender SmartScreen vraagt naar sites</span><span class="sxs-lookup"><span data-stu-id="40d00-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="40d00-141">**Standaardwaarde:** Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="40d00-141">**Default value:** Enabled</span></span>

<span data-ttu-id="40d00-142">We raden u af deze instelling uit te schakelen, omdat gebruikers hierdoor waarschuwingen kunnen negeren en mogelijk mogelijk schadelijke sites kunnen blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="40d00-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="40d00-143">Voorkomen dat microsoft Defender SmartScreen-waarschuwingen over downloads worden omzeild</span><span class="sxs-lookup"><span data-stu-id="40d00-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="40d00-144">**Standaardwaarde:** Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="40d00-144">**Default value:** Enabled</span></span>

<span data-ttu-id="40d00-145">We raden u af deze instelling uit te schakelen, omdat gebruikers hierdoor waarschuwingen kunnen negeren en niet-geverifieerde downloads kunnen voltooien.</span><span class="sxs-lookup"><span data-stu-id="40d00-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="40d00-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="40d00-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="40d00-147">Standaardinstelling voor Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="40d00-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="40d00-148">**Standaardwaarde:** Handicap</span><span class="sxs-lookup"><span data-stu-id="40d00-148">**Default value:** Disabled</span></span>

<span data-ttu-id="40d00-149">We raden het gebruik van Flash af vanwege de bijbehorende beveiligingsrisico's.</span><span class="sxs-lookup"><span data-stu-id="40d00-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="40d00-150">Als u nog steeds processen hebt die afhankelijk zijn van Flash, stelt u het beleid **[Voorforurls voor Plug-in](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** ingesteld om Flash in te schakelen voor sites die dit nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="40d00-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="40d00-151">Als u een toegestane lijst met sites niet bijhouden om Flash te gebruiken, dient u een wijzigingsverzoek in om de waarde te wijzigen in **Klik om af te spelen,** waarmee gebruikers kunnen kiezen wanneer het nodig is om Flash uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="40d00-151">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="40d00-152">Wachtwoordmanager</span><span class="sxs-lookup"><span data-stu-id="40d00-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="40d00-153">Wachtwoorden opslaan inschakelen voor de wachtwoordmanager</span><span class="sxs-lookup"><span data-stu-id="40d00-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="40d00-154">**Standaardwaarde:** Handicap</span><span class="sxs-lookup"><span data-stu-id="40d00-154">**Default value:** Disabled</span></span>

<span data-ttu-id="40d00-155">We raden eindgebruikers af om wachtwoorden op hun apparaat op te slaan.</span><span class="sxs-lookup"><span data-stu-id="40d00-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="40d00-156">Andere instellingen</span><span class="sxs-lookup"><span data-stu-id="40d00-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="40d00-157">Site-isolatie inschakelen voor elke site</span><span class="sxs-lookup"><span data-stu-id="40d00-157">Enable site isolation for every site</span></span>

<span data-ttu-id="40d00-158">**Standaardwaarde:** Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="40d00-158">**Default value:** Enabled</span></span>

<span data-ttu-id="40d00-159">Wanneer dit beleid is ingeschakeld, kunnen gebruikers zich niet afmelden voor het standaardgedrag waarin elke site in zijn eigen proces wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="40d00-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="40d00-160">Ondersteunde verificatieschema's</span><span class="sxs-lookup"><span data-stu-id="40d00-160">Supported authentication schemes</span></span>

<span data-ttu-id="40d00-161">**Standaardwaarde:** NTLM, Onderhandelen</span><span class="sxs-lookup"><span data-stu-id="40d00-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="40d00-162">Microsoft Managed Desktop biedt geen ondersteuning voor basis- of digestverificatieschema's.</span><span class="sxs-lookup"><span data-stu-id="40d00-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="40d00-163">De gegevens en instellingen van een andere browser automatisch importeren bij de eerste run</span><span class="sxs-lookup"><span data-stu-id="40d00-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="40d00-164">**Standaardwaarde:** Alle ondersteunde gegevenstypen en -instellingen automatisch importeren vanuit de standaardbrowser</span><span class="sxs-lookup"><span data-stu-id="40d00-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="40d00-165">Met dit beleid toegepast, slaat de first run experience de sectie importeren over, waardoor de interactie van de gebruiker wordt geminimaliseerd.</span><span class="sxs-lookup"><span data-stu-id="40d00-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="40d00-166">De browsergegevens van oudere versies van Microsoft Edge worden altijd geruisloos gemigreerd bij de eerste uitvoering, ongeacht deze instelling.</span><span class="sxs-lookup"><span data-stu-id="40d00-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="40d00-167">Instellingen die u beheert</span><span class="sxs-lookup"><span data-stu-id="40d00-167">Settings you manage</span></span>

<span data-ttu-id="40d00-168">U alle Microsoft Edge-instellingen implementeren die niet eerder zijn beschreven met het profiel Beheerderssjablonen in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="40d00-168">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="40d00-169">Zie Microsoft [Edge-beleidsinstellingen configureren met Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="40d00-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="40d00-170">Als u een beleid wilt evalueren dat momenteel niet is opgenomen in de beheersjablonen van Microsoft Edge in Intune, u aangepaste instellingen gebruiken voor Windows 10-apparaten in Intune.</span><span class="sxs-lookup"><span data-stu-id="40d00-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="40d00-171">Specifieke Chrome-extensies inschakelen</span><span class="sxs-lookup"><span data-stu-id="40d00-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="40d00-172">De beheersjabloon biedt een instelling voor het implementeren van bepaalde Chrome-extensies met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="40d00-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="40d00-173">U het vinden in **Computer configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span><span class="sxs-lookup"><span data-stu-id="40d00-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="40d00-174">Extensies in stilte installeren</span><span class="sxs-lookup"><span data-stu-id="40d00-174">Install extensions silently</span></span>

<span data-ttu-id="40d00-175">U de beheersjabloon ook gebruiken om Microsoft Edge in te stellen extensies te installeren zonder de gebruiker te waarschuwen.</span><span class="sxs-lookup"><span data-stu-id="40d00-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="40d00-176">U het vinden in **Computer Configuration > Microsoft Edge > Extensions > Control welke extensies in stilte zijn geïnstalleerd.**</span><span class="sxs-lookup"><span data-stu-id="40d00-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="40d00-177">Ander gemeenschappelijk ondernemingsbeleid</span><span class="sxs-lookup"><span data-stu-id="40d00-177">Other common enterprise policies</span></span>

<span data-ttu-id="40d00-178">Microsoft Edge biedt een groot aantal aanvullende beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="40d00-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="40d00-179">Dit zijn enkele van de meest voorkomende:</span><span class="sxs-lookup"><span data-stu-id="40d00-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="40d00-180">Sites configureren in de enterprise-sitelijst en de IE-modus</span><span class="sxs-lookup"><span data-stu-id="40d00-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="40d00-181">Start-up, startpagina en nieuwe tabpagina-instellingen configureren</span><span class="sxs-lookup"><span data-stu-id="40d00-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="40d00-182">Surfgame-instelling configureren</span><span class="sxs-lookup"><span data-stu-id="40d00-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="40d00-183">Proxyserverinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="40d00-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

