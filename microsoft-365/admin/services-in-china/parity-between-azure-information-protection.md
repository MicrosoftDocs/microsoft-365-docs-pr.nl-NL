---
title: Ondersteuning voor Azure Information Protection voor Office 365 beheerd door 21Vianet
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
description: Meer informatie over Azure Information Protection (AIP) voor Office 365 beheerd door 21Vianet en hoe u deze configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535840"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="e6a8e-103">Ondersteuning voor Azure Information Protection voor Office 365 beheerd door 21Vianet</span><span class="sxs-lookup"><span data-stu-id="e6a8e-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="e6a8e-104">In dit artikel worden de verschillen beschreven tussen AIP-ondersteuning (Azure Information Protection) voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen, evenals specifieke instructies voor het configureren van AIP voor klanten in China, waaronder hoe u de on-premises AIP-scanner installeert en inhoudsscantaken &mdash; beheert.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="e6a8e-105">Verschillen tussen AIP voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="e6a8e-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="e6a8e-106">Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze AIP voor Office 365 beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="e6a8e-107">De volgende lijst bevat de bestaande hiaten tussen AIP Office 365 beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="e6a8e-108">IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor ondernemingen (build 11731.10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="e6a8e-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="e6a8e-109">Office 2010, Office 2013 en andere versies Office 2016 worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="e6a8e-110">Migratie van Active Directory Rights Management Services (AD RMS) naar AIP is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="e6a8e-111">Het delen van beveiligde e-mailberichten met gebruikers in de commerciële cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="e6a8e-112">Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële cloud is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="e6a8e-113">Dit omvat Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS voor Individuen-licentie.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="e6a8e-114">IRM met SharePoint (met IRM beveiligde sites en bibliotheken) is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="e6a8e-115">De mobiele apparaatextensie voor AD RMS is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="e6a8e-116">De [mobiele viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="e6a8e-117">Het AIP-gebied van de Azure-portal is niet beschikbaar voor klanten in China.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="e6a8e-118">Gebruik [PowerShell-opdrachten](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) in plaats van acties uit te voeren in de portal, zoals het beheren en uitvoeren van uw inhoudsscantaken.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="e6a8e-119">AIP configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="e6a8e-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="e6a8e-120">AIP configureren voor klanten in China:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="e6a8e-121">[Rights Management inschakelen voor de tenant](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="e6a8e-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="e6a8e-122">[Voeg de microsoft information protection sync service service principal toe.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="e6a8e-123">[DNS-versleuteling configureren.](#step-3-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="e6a8e-124">[Installeer en configureer de geïntegreerde AIP-labelingclient.](#step-4-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="e6a8e-125">[AIP-apps configureren op Windows.](#step-5-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="e6a8e-126">[Installeer de on-premises AIP-scanner en beheer inhoudsscantaken.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="e6a8e-127">Stap 1: Rights Management inschakelen voor de tenant</span><span class="sxs-lookup"><span data-stu-id="e6a8e-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="e6a8e-128">Om de versleuteling correct te laten werken, moet RMS zijn ingeschakeld voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="e6a8e-129">Controleer of RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="e6a8e-130">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="e6a8e-131">Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="e6a8e-132">Importeer de module met `Import-Module AipService` behulp van .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="e6a8e-133">Verbinding maken naar de service met `Connect-AipService -environmentname azurechinacloud` behulp van .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="e6a8e-134">Voer `(Get-AipServiceConfiguration).FunctionalState` uit en controleer of de status `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="e6a8e-135">Als de functionele status `Disabled` is, wordt `Enable-AipService` uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="e6a8e-136">Stap 2: De Microsoft Information Protection Sync Service-service toevoegen</span><span class="sxs-lookup"><span data-stu-id="e6a8e-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="e6a8e-137">De **Microsoft Information Protection Sync Service service** principal is standaard niet beschikbaar in Azure China-tenants en is vereist voor Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="e6a8e-138">Maak deze service-principal handmatig met behulp van [de cmdlet New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) en de toepassings-id voor `870c4f2e-85b6-4d43-bdda-6ed9a579b725` de Microsoft Information Protection Sync Service.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="e6a8e-139">Nadat u de serviceprincipaal hebt toegevoegd, voegt u de benodigde machtigingen toe aan de service.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="e6a8e-140">Stap 3: DNS-versleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="e6a8e-141">Als versleuteling goed werkt, Office clienttoepassingen vanaf daar verbinding maken met het china-exemplaar van de service en de bootstrap.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="e6a8e-142">Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS-SRV-record configureren met informatie over de AZURE RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="e6a8e-143">Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met het openbare cloud-exemplaar en mislukt deze.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="e6a8e-144">De aanname is ook dat gebruikers zich zullen aanmelden met een gebruikersnaam die is gebaseerd op het domein van de tenant (bijvoorbeeld), en niet met de `joe@contoso.cn` `onmschina` gebruikersnaam `joe@contoso.onmschina.cn` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="e6a8e-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="e6a8e-145">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="e6a8e-146">DNS-versleuteling configureren - Windows</span><span class="sxs-lookup"><span data-stu-id="e6a8e-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="e6a8e-147">De RMS-id krijgen:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="e6a8e-148">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="e6a8e-149">Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="e6a8e-150">Verbinding maken naar de service met `Connect-AipService -environmentname azurechinacloud` behulp van .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="e6a8e-151">Voer `(Get-AipServiceConfiguration).RightsManagementServiceId` uit om de RMS-id op te halen.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="e6a8e-152">Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="e6a8e-153">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="e6a8e-154">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="e6a8e-155">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="e6a8e-156">Doel = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="e6a8e-157">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="e6a8e-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="e6a8e-158">Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="e6a8e-159">Hiermee voegt u een vermelding toe in DNS, die enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde hebt toevoegt aan de DNS-instellingen.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="e6a8e-160">Meld u aan bij het Microsoft 365 beheercentrum met de bijbehorende globale beheerdersreferenties en voeg het domein (bijvoorbeeld) toe voor het maken `contoso.cn` van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="e6a8e-161">In het verificatieproces zijn mogelijk extra DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="e6a8e-162">Wanneer verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="e6a8e-163">DNS-versleuteling configureren - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="e6a8e-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="e6a8e-164">Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="e6a8e-165">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="e6a8e-166">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-166">Protocol = `_http`</span></span>
- <span data-ttu-id="e6a8e-167">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-167">Name = `_tcp`</span></span>
- <span data-ttu-id="e6a8e-168">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="e6a8e-169">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-169">Port = `80`</span></span>
- <span data-ttu-id="e6a8e-170">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="e6a8e-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="e6a8e-171">Stap 4: De geïntegreerde AIP-labelingclient installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="e6a8e-172">Download en installeer de geïntegreerde AIP-labelingclient vanuit [het Microsoft Downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="e6a8e-173">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-173">For more information, see:</span></span>

- [<span data-ttu-id="e6a8e-174">AIP-documentatie</span><span class="sxs-lookup"><span data-stu-id="e6a8e-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="e6a8e-175">AIP-versiegeschiedenis en ondersteuningsbeleid</span><span class="sxs-lookup"><span data-stu-id="e6a8e-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="e6a8e-176">AIP-systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="e6a8e-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="e6a8e-177">AIP quickstart: De AIP-client implementeren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="e6a8e-178">AIP-beheerdershandleiding</span><span class="sxs-lookup"><span data-stu-id="e6a8e-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="e6a8e-179">AIP-gebruikershandleiding</span><span class="sxs-lookup"><span data-stu-id="e6a8e-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="e6a8e-180">Meer informatie over Microsoft 365 gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="e6a8e-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="e6a8e-181">Stap 5: AIP-apps configureren op Windows</span><span class="sxs-lookup"><span data-stu-id="e6a8e-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="e6a8e-182">AIP-apps op Windows hebben de volgende registersleutel nodig om ze te wijzen naar de juiste soevereine cloud voor Azure China:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="e6a8e-183">Register-knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="e6a8e-184">Naam = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="e6a8e-185">Waarde = `6` (standaard = 0)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="e6a8e-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6a8e-187">Zorg ervoor dat u de registersleutel niet verwijdert nadat u de registersleutel hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="e6a8e-188">Als de sleutel leeg, onjuist of niet aanwezig is, gedraagt de functionaliteit zich als de standaardwaarde (standaardwaarde = 0 voor de commerciële cloud).</span><span class="sxs-lookup"><span data-stu-id="e6a8e-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="e6a8e-189">Als de sleutel leeg of onjuist is, wordt er ook een afdrukfout toegevoegd aan het logboek.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="e6a8e-190">Stap 6: De on-premises AIP-scanner installeren en inhoudsscantaken beheren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="e6a8e-191">Installeer de on-premises AIP-scanner om uw netwerk- en inhoudsaandelen te scannen op gevoelige gegevens en pas classificatie- en beveiligingslabels toe zoals geconfigureerd in het beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="e6a8e-192">Wanneer u uw inhoudsscantaken configureert en beheert, gebruikt u de volgende procedure in plaats van de [Azure-portalinterface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) die door de commerciële aanbiedingen wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="e6a8e-193">Zie Wat is de geïntegreerde labelscanner voor [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) en [Uw inhoudsscantaken beheren met alleen PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="e6a8e-194">**Uw scanner installeren en configureren:**</span><span class="sxs-lookup"><span data-stu-id="e6a8e-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="e6a8e-195">Meld u aan bij Windows servercomputer waarin de scanner wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="e6a8e-196">Gebruik een account met lokale beheerdersrechten en die machtigingen heeft om naar de hoofddatabase SQL Server schrijven.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="e6a8e-197">Begin met PowerShell gesloten.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-197">Start with PowerShell closed.</span></span> <span data-ttu-id="e6a8e-198">Als u eerder de AIP-client en -scanner hebt geïnstalleerd, moet u ervoor zorgen dat de **AIPScanner-service** is gestopt.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="e6a8e-199">Open een Windows PowerShell sessie met de optie **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="e6a8e-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="e6a8e-200">Voer de [cmdlet Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) uit en geef uw SQL Server-exemplaar op waarop u een database wilt maken voor de Azure Information Protection-scanner en een duidelijke naam voor het scannercluster.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="e6a8e-201">U kunt dezelfde clusternaam gebruiken in de opdracht [Installeren-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) om meerdere scannerknooppunten aan hetzelfde cluster te koppelen.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="e6a8e-202">Als u hetzelfde cluster gebruikt voor meerdere scannerknooppunten, kunnen meerdere scanners samenwerken om uw scans uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="e6a8e-203">Controleer of de service nu is geïnstalleerd met **Beheerhulpmiddelen**  >  **Services.**</span><span class="sxs-lookup"><span data-stu-id="e6a8e-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="e6a8e-204">De geïnstalleerde service heeft de naam **Azure Information Protection Scanner** en is geconfigureerd voor gebruik met het scannerserviceaccount dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="e6a8e-205">Een Azure-token gebruiken voor uw scanner.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="e6a8e-206">Met een Azure AD-token kan de scanner zich verifiëren bij de Azure Information Protection-service, zodat de scanner niet-interactief kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="e6a8e-207">Open de Azure-portal en maak een Azure AD-toepassing om een toegangs token voor verificatie op te geven.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="e6a8e-208">Zie Bestanden op een [niet-interactieve](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)manier labelen voor Azure Information Protection voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="e6a8e-209">Wanneer u Azure AD-toepassingen maakt en configureert voor de opdracht  [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) worden in het deelvenster API-machtigingen aanvragen de API's weergegeven die door mijn organisatie worden gebruikt in plaats van op het tabblad Api's van **Microsoft.**  Selecteer de **API's die mijn organisatie gebruikt** om vervolgens Azure Rights Management **Services.**</span><span class="sxs-lookup"><span data-stu-id="e6a8e-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="e6a8e-210">Meld u aan met dit account en start een  PowerShell-sessie als aan uw scannerserviceaccount lokaal is toegewezen voor de installatie, Windows servercomputer.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="e6a8e-211">Als uw scannerserviceaccount niet  kan worden verleend aan het lokaal aanmelden voor de installatie, gebruikt u de parameter *OnBehalfOf* met [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), zoals wordt beschreven in Bestanden [niet-interactief](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)labelen voor Azure Information Protection .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="e6a8e-212">[Voer Set-AIPAuthentication uit](/powershell/module/azureinformationprotection/set-aipauthentication)en geef waarden op die zijn gekopieerd uit uw Azure AD-toepassing:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="e6a8e-213">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="e6a8e-214">De scanner heeft nu een token om te verifiëren bij Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="e6a8e-215">Dit token is geldig voor één jaar, twee jaar of nooit, volgens uw configuratie van de **web-app /API-clientgeheim** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="e6a8e-216">Wanneer het token verloopt, moet u deze procedure herhalen.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="e6a8e-217">Voer de [cmdlet Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) uit om de scanner in te stellen op functie in de offlinemodus.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="e6a8e-218">Uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="e6a8e-219">Voer de [cmdlet Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) uit om een standaard taak voor inhoudsscans te maken.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="e6a8e-220">De enige vereiste parameter in de **cmdlet Set-AIPScannerContentScanJob** is **Afdwingen.**</span><span class="sxs-lookup"><span data-stu-id="e6a8e-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="e6a8e-221">Mogelijk wilt u op dit moment echter andere instellingen definiëren voor uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="e6a8e-222">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="e6a8e-223">De syntaxis hierboven configureert de volgende instellingen terwijl u doorgaat met de configuratie:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="e6a8e-224">De planning van de scanner wordt handmatig *uitgevoerd*</span><span class="sxs-lookup"><span data-stu-id="e6a8e-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="e6a8e-225">Hiermee stelt u de informatietypen in die moeten worden gevonden op basis van het beleid voor gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="e6a8e-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="e6a8e-226">Wordt *een beleid* voor het labelen van gevoeligheid niet afgedwongen</span><span class="sxs-lookup"><span data-stu-id="e6a8e-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="e6a8e-227">Bestanden automatisch labelen op basis van inhoud, met behulp van het standaardlabel dat is gedefinieerd voor het beleid voor gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="e6a8e-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="e6a8e-228">Het *opnieuw* labelen van bestanden is niet toegestaan</span><span class="sxs-lookup"><span data-stu-id="e6a8e-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="e6a8e-229">Behoudt bestandsdetails tijdens het scannen en automatisch labelen, inclusief *datum gewijzigd,* *laatst* gewijzigd en gewijzigd *door* waarden</span><span class="sxs-lookup"><span data-stu-id="e6a8e-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="e6a8e-230">Hiermee stelt u de scanner in om MSG- en TMP-bestanden uit te sluiten tijdens het uitvoeren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="e6a8e-231">Stelt de standaardeigenaar in op het account dat u wilt gebruiken bij het uitvoeren van de scanner</span><span class="sxs-lookup"><span data-stu-id="e6a8e-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="e6a8e-232">Gebruik de [cmdlet Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) om de opslagplaatsen te definiëren die u wilt scannen in uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="e6a8e-233">Voer bijvoorbeeld het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="e6a8e-234">Gebruik een van de volgende syntaxis, afhankelijk van het type opslagplaats dat u toevoegt:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="e6a8e-235">Gebruik voor een netwerk delen `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="e6a8e-236">Gebruik voor SharePoint bibliotheek `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="e6a8e-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="e6a8e-237">Voor een lokaal pad: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="e6a8e-238">Voor een UNC-pad: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="e6a8e-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6a8e-239">Jokertekens worden niet ondersteund en WebDav-locaties worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="e6a8e-240">Als u de opslagplaats later wilt wijzigen, gebruikt u in plaats daarvan [de cmdlet Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="e6a8e-241">Ga zo nodig verder met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="e6a8e-242">Een detectiecyclus uitvoeren en rapporten voor de scanner weergeven</span><span class="sxs-lookup"><span data-stu-id="e6a8e-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="e6a8e-243">PowerShell gebruiken om de scanner zo te configureren dat classificatie en beveiliging worden toegepast</span><span class="sxs-lookup"><span data-stu-id="e6a8e-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="e6a8e-244">PowerShell gebruiken om een DLP-beleid met de scanner te configureren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="e6a8e-245">De volgende tabel bevat PowerShell-cmdlets die relevant zijn voor het installeren van de scanner en het beheren van uw inhoudsscantaken:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="e6a8e-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e6a8e-246">Cmdlet</span></span> | <span data-ttu-id="e6a8e-247">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e6a8e-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="e6a8e-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e6a8e-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="e6a8e-249">Hiermee voegt u een nieuwe opslagplaats toe aan uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="e6a8e-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6a8e-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="e6a8e-251">Retourneert details over uw cluster.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="e6a8e-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="e6a8e-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="e6a8e-253">Hier krijgt u meer informatie over uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="e6a8e-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e6a8e-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="e6a8e-255">Hier krijgt u informatie over de opslagplaatsen die zijn gedefinieerd voor uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="e6a8e-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="e6a8e-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="e6a8e-257">Hiermee verwijdert u uw taak voor het scannen van inhoud.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="e6a8e-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e6a8e-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="e6a8e-259">Hiermee verwijdert u een opslagplaats uit uw taak voor inhoudsscans.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="e6a8e-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="e6a8e-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="e6a8e-261">Hiermee definieert u instellingen voor uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="e6a8e-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e6a8e-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="e6a8e-263">Hiermee definieert u instellingen voor een bestaande opslagplaats in uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="e6a8e-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="e6a8e-264">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="e6a8e-264">For more information, see:</span></span>

- [<span data-ttu-id="e6a8e-265">Wat is de geïntegreerde labelscanner voor Azure Information Protection?</span><span class="sxs-lookup"><span data-stu-id="e6a8e-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="e6a8e-266">De geïntegreerde labelingsscanner voor Azure Information Protection (AIP) configureren en installeren</span><span class="sxs-lookup"><span data-stu-id="e6a8e-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="e6a8e-267">[Beheer uw inhoudsscantaken alleen met PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="e6a8e-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
