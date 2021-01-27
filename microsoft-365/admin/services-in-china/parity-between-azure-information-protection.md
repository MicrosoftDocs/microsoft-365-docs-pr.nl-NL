---
title: Ondersteuning voor Azure Information Protection voor Office 365, beheerd door 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Lees meer over Azure Information Protection (BEHEERDERSversie van Azure Information Protection) voor Office 365, beheerd door 21Vianet, en hoe u deze kunt configureren voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988042"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="c16f1-103">Ondersteuning voor Azure Information Protection voor Office 365, beheerd door 21Vianet</span><span class="sxs-lookup"><span data-stu-id="c16f1-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="c16f1-104">Dit artikel gaat over de verschillen tussen de ondersteuning van Azure Information Protection (BEHEERDERSversie) van Office 365, beheerd door 21Vianet en commerciële aanbiedingen, en specifieke instructies voor het configureren van beheerders namen voor klanten in China, &mdash; waaronder het installeren van de on-premises scanner van beheerders en het beheren van inhoudsscan taken.</span><span class="sxs-lookup"><span data-stu-id="c16f1-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="c16f1-105">Verschillen tussen beheerders van Office 365, beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="c16f1-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="c16f1-106">Hoewel ons doel is om alle commerciële functies en functionaliteit te bieden aan klanten in China met onze BEHEERDERSversie van Office 365 die wordt beheerd door 21Vianet-aanbieding, is er een ontbrekende functionaliteit die we willen markeren.</span><span class="sxs-lookup"><span data-stu-id="c16f1-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="c16f1-107">De volgende lijst bevat de bestaande hiaten tussen beheerders van Office 365, beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:</span><span class="sxs-lookup"><span data-stu-id="c16f1-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="c16f1-108">IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor Enterprise (build 11731,10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="c16f1-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="c16f1-109">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c16f1-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="c16f1-110">Migratie van Active Directory Rights Management Services (AD RMS) naar een beheerders service is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="c16f1-111">Het delen van beveiligde e-mailberichten met gebruikers in de commerciële Cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c16f1-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="c16f1-112">Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële Cloud is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="c16f1-113">Dit omvat Office 365, beheerd door 21Vianet-gebruikers in de commerciële Cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële Cloud, en gebruikers met een RMS voor individuen-licentie.</span><span class="sxs-lookup"><span data-stu-id="c16f1-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="c16f1-114">IRM met SharePoint (sites en bibliotheken met IRM-beveiliging) is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="c16f1-115">De extensie van het mobiele apparaat voor AD RMS is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="c16f1-116">De [Mobile-Viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21vianet.</span><span class="sxs-lookup"><span data-stu-id="c16f1-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="c16f1-117">Beheerders configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="c16f1-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="c16f1-118">Beheerders configureren voor klanten in China:</span><span class="sxs-lookup"><span data-stu-id="c16f1-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="c16f1-119">[Schakel Rights Management in voor de Tenant](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="c16f1-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="c16f1-120">[DNS-versleuteling configureren](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="c16f1-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="c16f1-121">[Installeer en configureer de toepassing beheerders Unified-labels](#step-3-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="c16f1-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="c16f1-122">Het [configureren van beheerders apps in Windows](#step-4-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="c16f1-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="c16f1-123">[Installeer de on-premises scanner van beheerders en beheertaken voor inhouds onderzoek](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span><span class="sxs-lookup"><span data-stu-id="c16f1-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="c16f1-124">Stap 1: het rechtenbeheer inschakelen voor de Tenant</span><span class="sxs-lookup"><span data-stu-id="c16f1-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="c16f1-125">Voor een juiste werking van de versleuteling moet RMS zijn ingeschakeld voor de Tenant.</span><span class="sxs-lookup"><span data-stu-id="c16f1-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="c16f1-126">Controleren of RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="c16f1-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="c16f1-127">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="c16f1-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="c16f1-128">Als de AIPService-module niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="c16f1-129">Importeer de module met `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="c16f1-130">Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="c16f1-131">Voer `(Get-AipServiceConfiguration).FunctionalState` en controleer of de status is `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="c16f1-132">Voer dit uit als de functionele status wordt `Disabled` uitgevoerd `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="c16f1-133">Stap 2: DNS-versleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="c16f1-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="c16f1-134">Voor een juiste werking van versleuteling moet Office-clienttoepassingen verbinding maken met het exemplaar van de service en de bootstrap.</span><span class="sxs-lookup"><span data-stu-id="c16f1-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="c16f1-135">Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="c16f1-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="c16f1-136">Zonder de DNS SRV-record probeert de clienttoepassing standaardverbinding te maken met het openbare Cloud exemplaar en mislukt de clienttoepassing.</span><span class="sxs-lookup"><span data-stu-id="c16f1-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="c16f1-137">Daarnaast is het raadzaam dat gebruikers zich aanmelden met een gebruikersnaam op basis van het domein van de Tenant domein (bijvoorbeeld `joe@contoso.cn` ), en niet de `onmschina` gebruikersnaam (bijvoorbeeld `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="c16f1-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="c16f1-138">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="c16f1-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="c16f1-139">DNS-versleuteling configureren-Windows</span><span class="sxs-lookup"><span data-stu-id="c16f1-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="c16f1-140">De RMS-ID achterhalen:</span><span class="sxs-lookup"><span data-stu-id="c16f1-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="c16f1-141">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="c16f1-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="c16f1-142">Als de AIPService-module niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="c16f1-143">Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="c16f1-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="c16f1-144">Uitvoeren `(Get-AipServiceConfiguration).RightsManagementServiceId` om de RMS-id te achterhalen.</span><span class="sxs-lookup"><span data-stu-id="c16f1-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="c16f1-145">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="c16f1-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="c16f1-146">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="c16f1-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="c16f1-147">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="c16f1-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="c16f1-148">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="c16f1-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="c16f1-149">Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="c16f1-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="c16f1-150">Prioriteit, gewicht, seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="c16f1-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="c16f1-151">Koppel het aangepaste domein aan de Tenant in de [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="c16f1-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="c16f1-152">Hiermee voegt u een vermelding toe aan DNS, wat kan enkele minuten duren voordat deze is toegevoegd aan de DNS-instellingen.</span><span class="sxs-lookup"><span data-stu-id="c16f1-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="c16f1-153">Meld u aan bij het Microsoft 365-Beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld `contoso.cn` ) voor het maken van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c16f1-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="c16f1-154">In het verificatieproces zijn er mogelijk extra DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="c16f1-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="c16f1-155">Wanneer de verificatie is voltooid, kunnen gebruikers maken.</span><span class="sxs-lookup"><span data-stu-id="c16f1-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="c16f1-156">DNS-versleuteling configureren-Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="c16f1-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="c16f1-157">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="c16f1-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="c16f1-158">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="c16f1-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="c16f1-159">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="c16f1-159">Protocol = `_http`</span></span>
- <span data-ttu-id="c16f1-160">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="c16f1-160">Name = `_tcp`</span></span>
- <span data-ttu-id="c16f1-161">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="c16f1-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="c16f1-162">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="c16f1-162">Port = `80`</span></span>
- <span data-ttu-id="c16f1-163">Prioriteit, gewicht, seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="c16f1-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="c16f1-164">Stap 3: de client van het beheerders bare Unified-etiket installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="c16f1-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="c16f1-165">Download de BEHEERDERSversie van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="c16f1-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="c16f1-166">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="c16f1-166">For more information, see:</span></span>

- [<span data-ttu-id="c16f1-167">BEHEERDERS documentatie</span><span class="sxs-lookup"><span data-stu-id="c16f1-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="c16f1-168">Beheerdersversie geschiedenis en ondersteuningsbeleid</span><span class="sxs-lookup"><span data-stu-id="c16f1-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="c16f1-169">Systeemvereisten voor beheerders</span><span class="sxs-lookup"><span data-stu-id="c16f1-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="c16f1-170">BEHEERDERS-Snelstartgids: de beheerders-client implementeren</span><span class="sxs-lookup"><span data-stu-id="c16f1-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="c16f1-171">Beheerdershandleiding van beheerders</span><span class="sxs-lookup"><span data-stu-id="c16f1-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="c16f1-172">Beheerdershandleiding voor beheerders</span><span class="sxs-lookup"><span data-stu-id="c16f1-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="c16f1-173">Meer informatie over Microsoft 365-reductie-labels</span><span class="sxs-lookup"><span data-stu-id="c16f1-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="c16f1-174">Stap 4: beheerders-apps configureren in Windows</span><span class="sxs-lookup"><span data-stu-id="c16f1-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="c16f1-175">In de online-apps van Windows is de volgende registersleutel nodig om ze te laten verwijzen naar de juiste soevereine wolk voor Azure China:</span><span class="sxs-lookup"><span data-stu-id="c16f1-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="c16f1-176">Register knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="c16f1-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="c16f1-177">Naam = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="c16f1-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="c16f1-178">Waarde = `6` (standaard = 0)</span><span class="sxs-lookup"><span data-stu-id="c16f1-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="c16f1-179">Typ = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="c16f1-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c16f1-180">Zorg dat u de registersleutel niet verwijdert na verwijdering.</span><span class="sxs-lookup"><span data-stu-id="c16f1-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="c16f1-181">Als de sleutel leeg, ongeldig of niet-bestaand is, werkt de functie als standaardwaarde (standaardwaarde = 0 voor de commerciële Cloud).</span><span class="sxs-lookup"><span data-stu-id="c16f1-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="c16f1-182">Als de sleutel leeg of onjuist is, wordt een afdrukfout ook toegevoegd aan het logboek.</span><span class="sxs-lookup"><span data-stu-id="c16f1-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="c16f1-183">Stap 5: de on-premises scanner van de BEHEERDERSversie installeren en inhoudsscan taken beheren</span><span class="sxs-lookup"><span data-stu-id="c16f1-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="c16f1-184">Installeer de on-premises on-premises scanner van de BEHEERDERSversie om uw netwerk-en inhouds aandelen te scannen op gevoelige gegevens en om classificatie-en beveiligings etiketten toe te passen, zoals geconfigureerd in het beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c16f1-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="c16f1-185">Wanneer u de scanner installeert en uw inhoudsscan taken beheert, gebruikt u de volgende cmdlets in plaats van de Azure Portal-interface die wordt gebruikt door de commerciële aanbiedingen:</span><span class="sxs-lookup"><span data-stu-id="c16f1-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="c16f1-186">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c16f1-186">Cmdlet</span></span> | <span data-ttu-id="c16f1-187">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c16f1-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="c16f1-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c16f1-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="c16f1-189">Hiermee voegt u een nieuwe bibliotheek toe aan uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="c16f1-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c16f1-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="c16f1-191">Hiermee krijgt u meer informatie over uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="c16f1-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c16f1-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="c16f1-193">Hiermee krijgt u meer informatie over opslaglocaties die zijn gedefinieerd voor uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="c16f1-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c16f1-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="c16f1-195">Hiermee verwijdert u uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="c16f1-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c16f1-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="c16f1-197">Hiermee verwijdert u een bibliotheek van uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="c16f1-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c16f1-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="c16f1-199">Definieert de instellingen voor uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="c16f1-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c16f1-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="c16f1-201">Definieert instellingen voor een bestaande bibliotheek in uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="c16f1-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="c16f1-202">Zie voor meer informatie [Wat is de uitgebreide scanner van Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) en [beheertaken voor inhouds onderzoek via PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="c16f1-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>