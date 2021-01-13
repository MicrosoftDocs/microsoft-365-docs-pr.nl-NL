---
title: Pariteit tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en commerciële aanbiedingen
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840299"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="78c10-103">Pariteit tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="78c10-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="78c10-104">Hoewel ons doel is alle commerciële functies en functionaliteit te bieden aan klanten in China met onze Azure Information Protection (BEHEERDERSversie) voor Office 365, beheerd door 21Vianet-aanbieding, is er een ontbrekende functionaliteit die we willen markeren.</span><span class="sxs-lookup"><span data-stu-id="78c10-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="78c10-105">De volgende lijst bevat de bestaande hiaten tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:</span><span class="sxs-lookup"><span data-stu-id="78c10-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="78c10-106">IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor Enterprise (build 11731,10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="78c10-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="78c10-107">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="78c10-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="78c10-108">Migratie van Active Directory Rights Management Services (AD RMS) naar Azure Information Protection is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="78c10-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="78c10-109">Het delen van beveiligde e-mailberichten voor gebruikers in de commerciële Cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="78c10-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="78c10-110">Het delen van documenten en e-mailbijlagen aan gebruikers in de commerciële Cloud is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="78c10-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="78c10-111">Dit omvat Office 365, beheerd door 21Vianet-gebruikers in de commerciële Cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële Cloud, en gebruikers met een RMS voor individuen-licentie.</span><span class="sxs-lookup"><span data-stu-id="78c10-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="78c10-112">IRM met SharePoint (sites en bibliotheken met IRM-beveiliging) is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="78c10-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="78c10-113">De extensie van het mobiele apparaat voor AD RMS is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="78c10-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="78c10-114">De [Mobile-Viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21vianet.</span><span class="sxs-lookup"><span data-stu-id="78c10-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="78c10-115">Azure Information Protection configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="78c10-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="78c10-116">Rechtenbeheer inschakelen voor de Tenant</span><span class="sxs-lookup"><span data-stu-id="78c10-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="78c10-117">Voor een juiste werking van de versleuteling moet RMS zijn ingeschakeld voor de Tenant.</span><span class="sxs-lookup"><span data-stu-id="78c10-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="78c10-118">Controleer of de RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="78c10-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="78c10-119">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="78c10-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="78c10-120">Als de AIPService-module niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="78c10-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="78c10-121">Importeer de module met `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="78c10-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="78c10-122">Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="78c10-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="78c10-123">Voer `(Get-AipServiceConfiguration).FunctionalState` en controleer of de status is `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="78c10-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="78c10-124">Voer dit uit als de functionele status wordt `Disabled` uitgevoerd `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="78c10-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="78c10-125">DNS-configuratie voor versleuteling (Windows)</span><span class="sxs-lookup"><span data-stu-id="78c10-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="78c10-126">Voor een juiste werking van versleuteling moet Office-clienttoepassingen verbinding maken met het exemplaar van de service en de bootstrap.</span><span class="sxs-lookup"><span data-stu-id="78c10-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="78c10-127">Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="78c10-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="78c10-128">Zonder de DNS SRV-record probeert de clienttoepassing standaardverbinding te maken met het openbare Cloud exemplaar en mislukt de clienttoepassing.</span><span class="sxs-lookup"><span data-stu-id="78c10-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="78c10-129">Daarnaast is het raadzaam dat gebruikers zich aanmelden met een gebruikersnaam op basis van het domein van de Tenant domein (bijvoorbeeld `joe@contoso.cn` ), en niet de `onmschina` gebruikersnaam (bijvoorbeeld `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="78c10-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="78c10-130">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="78c10-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="78c10-131">De RMS-ID achterhalen:</span><span class="sxs-lookup"><span data-stu-id="78c10-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="78c10-132">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="78c10-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="78c10-133">Als de AIPService-module niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="78c10-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="78c10-134">Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="78c10-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="78c10-135">Uitvoeren `(Get-AipServiceConfiguration).RightsManagementServiceId` om de RMS-id te achterhalen.</span><span class="sxs-lookup"><span data-stu-id="78c10-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="78c10-136">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="78c10-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="78c10-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="78c10-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="78c10-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="78c10-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="78c10-139">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="78c10-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="78c10-140">Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="78c10-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="78c10-141">Prioriteit, gewicht, seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="78c10-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="78c10-142">Koppel het aangepaste domein aan de Tenant in de [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="78c10-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="78c10-143">Hiermee voegt u een vermelding toe aan DNS, wat kan enkele minuten duren voordat deze is toegevoegd aan de DNS-instellingen.</span><span class="sxs-lookup"><span data-stu-id="78c10-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="78c10-144">Meld u aan bij het Microsoft 365-Beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld `contoso.cn` ) voor het maken van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="78c10-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="78c10-145">In het verificatieproces zijn er mogelijk extra DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="78c10-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="78c10-146">Wanneer de verificatie is voltooid, kunnen gebruikers maken.</span><span class="sxs-lookup"><span data-stu-id="78c10-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="78c10-147">DNS-configuratie voor versleuteling (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="78c10-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="78c10-148">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="78c10-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="78c10-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="78c10-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="78c10-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="78c10-150">Protocol = `_http`</span></span>
- <span data-ttu-id="78c10-151">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="78c10-151">Name = `_tcp`</span></span>
- <span data-ttu-id="78c10-152">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="78c10-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="78c10-153">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="78c10-153">Port = `80`</span></span>
- <span data-ttu-id="78c10-154">Prioriteit, gewicht, seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="78c10-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="78c10-155">Clientconfiguratie van beheerders</span><span class="sxs-lookup"><span data-stu-id="78c10-155">AIP client configuration</span></span>

<span data-ttu-id="78c10-156">De collectieve BEHEERDERSversie van het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=53018)kan worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="78c10-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="78c10-157">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="78c10-157">For more information, see:</span></span>

- [<span data-ttu-id="78c10-158">Documentatie voor Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="78c10-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="78c10-159">Beheerdersversie geschiedenis en ondersteuningsbeleid</span><span class="sxs-lookup"><span data-stu-id="78c10-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="78c10-160">Systeemvereisten voor beheerders</span><span class="sxs-lookup"><span data-stu-id="78c10-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="78c10-161">BEHEERDERS-Snelstartgids: de beheerders-client implementeren</span><span class="sxs-lookup"><span data-stu-id="78c10-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="78c10-162">Beheerdershandleiding van beheerders</span><span class="sxs-lookup"><span data-stu-id="78c10-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="78c10-163">Beheerdershandleiding voor beheerders</span><span class="sxs-lookup"><span data-stu-id="78c10-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="78c10-164">Meer informatie over Microsoft 365-reductie-labels</span><span class="sxs-lookup"><span data-stu-id="78c10-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="78c10-165">Configuratie van beheerders-apps (alleen voor Unified-client)</span><span class="sxs-lookup"><span data-stu-id="78c10-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="78c10-166">Voor de oplossing voor samenvoegings labels heeft de beheerders-app in Windows de volgende registersleutel nodig om ze te laten verwijzen naar de juiste soevereine wolk voor Azure China:</span><span class="sxs-lookup"><span data-stu-id="78c10-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="78c10-167">Register knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="78c10-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="78c10-168">Naam = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="78c10-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="78c10-169">Waarde = `6` (standaard = 0)</span><span class="sxs-lookup"><span data-stu-id="78c10-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="78c10-170">Typ = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="78c10-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78c10-171">Zorg dat u de registersleutel niet verwijdert na verwijdering.</span><span class="sxs-lookup"><span data-stu-id="78c10-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="78c10-172">Als de sleutel leeg, ongeldig of niet-bestaand is, werkt de functie als standaardwaarde (standaardwaarde = 0 voor de commerciële Cloud).</span><span class="sxs-lookup"><span data-stu-id="78c10-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="78c10-173">Als de sleutel leeg of onjuist is, wordt een afdrukfout ook toegevoegd aan het logboek.</span><span class="sxs-lookup"><span data-stu-id="78c10-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="78c10-174">Inhouds onderzoek taken voor Azure Information Protection beheren</span><span class="sxs-lookup"><span data-stu-id="78c10-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="78c10-175">Voer de volgende cmdlets uit in plaats van de Azure-portal als u inhoud van de beveiliging van Azure Information Protection wilt beheren met een Azure China-scanner server:</span><span class="sxs-lookup"><span data-stu-id="78c10-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="78c10-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="78c10-176">Cmdlet</span></span> | <span data-ttu-id="78c10-177">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="78c10-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="78c10-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="78c10-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="78c10-179">Hiermee voegt u een nieuwe bibliotheek toe aan uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="78c10-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="78c10-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="78c10-181">Hiermee krijgt u meer informatie over uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="78c10-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="78c10-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="78c10-183">Hiermee krijgt u meer informatie over opslaglocaties die zijn gedefinieerd voor uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="78c10-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="78c10-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="78c10-185">Hiermee verwijdert u uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="78c10-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="78c10-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="78c10-187">Hiermee verwijdert u een bibliotheek van uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="78c10-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="78c10-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="78c10-189">Definieert de instellingen voor uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="78c10-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="78c10-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="78c10-191">Definieert instellingen voor een bestaande bibliotheek in uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="78c10-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="78c10-192">Zie voor meer informatie [uw inhoudsscan taken beheren via PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="78c10-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>