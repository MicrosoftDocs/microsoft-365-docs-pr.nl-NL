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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418030"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="34d62-103">Ondersteuning voor Azure Information Protection voor Office 365 beheerd door 21Vianet</span><span class="sxs-lookup"><span data-stu-id="34d62-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="34d62-104">In dit artikel worden de verschillen beschreven tussen AIP-ondersteuning (Azure Information Protection) voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen, evenals specifieke instructies voor het configureren van AIP voor klanten in China, waaronder hoe u de on-premises AIP-scanner installeert en inhoudsscantaken &mdash; beheert.</span><span class="sxs-lookup"><span data-stu-id="34d62-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="34d62-105">Verschillen tussen AIP voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="34d62-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="34d62-106">Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze AIP voor Office 365 beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.</span><span class="sxs-lookup"><span data-stu-id="34d62-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="34d62-107">De volgende lijst bevat de bestaande hiaten tussen AIP voor Office 365 beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:</span><span class="sxs-lookup"><span data-stu-id="34d62-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="34d62-108">IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365 Apps voor ondernemingen (build 11731.10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="34d62-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="34d62-109">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="34d62-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="34d62-110">Migratie van Active Directory Rights Management Services (AD RMS) naar AIP is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="34d62-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="34d62-111">Het delen van beveiligde e-mailberichten met gebruikers in de commerciële cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="34d62-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="34d62-112">Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële cloud is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="34d62-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="34d62-113">Dit omvat Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS voor Individuen-licentie.</span><span class="sxs-lookup"><span data-stu-id="34d62-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="34d62-114">IRM met SharePoint (met IRM beveiligde sites en bibliotheken) is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="34d62-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="34d62-115">De mobiele apparaatextensie voor AD RMS is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="34d62-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="34d62-116">De [mobiele viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="34d62-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="34d62-117">Het AIP-gebied van de Azure-portal is niet beschikbaar voor klanten in China.</span><span class="sxs-lookup"><span data-stu-id="34d62-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="34d62-118">Gebruik [PowerShell-opdrachten](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) in plaats van acties uit te voeren in de portal, zoals het installeren van de on-premises scanner en het beheren van uw inhoudsscantaken.</span><span class="sxs-lookup"><span data-stu-id="34d62-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="34d62-119">AIP configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="34d62-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="34d62-120">AIP configureren voor klanten in China:</span><span class="sxs-lookup"><span data-stu-id="34d62-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="34d62-121">[Rights Management inschakelen voor de tenant](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="34d62-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="34d62-122">[DNS-versleuteling configureren.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="34d62-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="34d62-123">[Installeer en configureer de geïntegreerde AIP-labelingclient.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="34d62-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="34d62-124">[AIP-apps configureren in Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="34d62-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="34d62-125">[Installeer de on-premises AIP-scanner en beheer inhoudsscantaken.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="34d62-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="34d62-126">Stap 1: Rights Management inschakelen voor de tenant</span><span class="sxs-lookup"><span data-stu-id="34d62-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="34d62-127">Om de versleuteling correct te laten werken, moet RMS zijn ingeschakeld voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="34d62-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="34d62-128">Controleer of RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="34d62-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="34d62-129">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="34d62-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="34d62-130">Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="34d62-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="34d62-131">Importeer de module met `Import-Module AipService` behulp van .</span><span class="sxs-lookup"><span data-stu-id="34d62-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="34d62-132">Maak verbinding met de service met `Connect-AipService -environmentname azurechinacloud` behulp van .</span><span class="sxs-lookup"><span data-stu-id="34d62-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="34d62-133">Voer `(Get-AipServiceConfiguration).FunctionalState` uit en controleer of de status `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="34d62-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="34d62-134">Als de functionele status `Disabled` is, wordt `Enable-AipService` uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="34d62-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="34d62-135">Stap 2: DNS-versleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="34d62-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="34d62-136">Als versleuteling goed werkt, moeten Office-clienttoepassingen vanaf daar verbinding maken met het China-exemplaar van de service en de bootstrap.</span><span class="sxs-lookup"><span data-stu-id="34d62-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="34d62-137">Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS-SRV-record configureren met informatie over de AZURE RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="34d62-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="34d62-138">Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met het openbare cloud-exemplaar en mislukt deze.</span><span class="sxs-lookup"><span data-stu-id="34d62-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="34d62-139">De aanname is ook dat gebruikers zich zullen aanmelden met een gebruikersnaam die is gebaseerd op het domein van de tenant (bijvoorbeeld), en niet met de `joe@contoso.cn` `onmschina` gebruikersnaam `joe@contoso.onmschina.cn` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="34d62-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="34d62-140">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="34d62-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="34d62-141">DNS-versleuteling configureren - Windows</span><span class="sxs-lookup"><span data-stu-id="34d62-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="34d62-142">De RMS-id krijgen:</span><span class="sxs-lookup"><span data-stu-id="34d62-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="34d62-143">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="34d62-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="34d62-144">Als de AIPService-module niet is geïnstalleerd, kunt u `Install-Module AipService` dit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="34d62-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="34d62-145">Maak verbinding met de service met `Connect-AipService -environmentname azurechinacloud` behulp van .</span><span class="sxs-lookup"><span data-stu-id="34d62-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="34d62-146">Voer `(Get-AipServiceConfiguration).RightsManagementServiceId` uit om de RMS-id op te halen.</span><span class="sxs-lookup"><span data-stu-id="34d62-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="34d62-147">Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="34d62-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="34d62-148">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="34d62-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="34d62-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="34d62-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="34d62-150">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="34d62-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="34d62-151">Doel = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="34d62-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="34d62-152">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="34d62-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="34d62-153">Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="34d62-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="34d62-154">Hiermee voegt u een vermelding toe in DNS, die enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde hebt toevoegt aan de DNS-instellingen.</span><span class="sxs-lookup"><span data-stu-id="34d62-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="34d62-155">Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende globale beheerdersreferenties en voeg het domein (bijvoorbeeld) toe voor het maken `contoso.cn` van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="34d62-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="34d62-156">In het verificatieproces zijn mogelijk extra DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="34d62-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="34d62-157">Wanneer verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="34d62-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="34d62-158">DNS-versleuteling configureren - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="34d62-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="34d62-159">Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="34d62-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="34d62-160">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="34d62-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="34d62-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="34d62-161">Protocol = `_http`</span></span>
- <span data-ttu-id="34d62-162">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="34d62-162">Name = `_tcp`</span></span>
- <span data-ttu-id="34d62-163">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="34d62-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="34d62-164">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="34d62-164">Port = `80`</span></span>
- <span data-ttu-id="34d62-165">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="34d62-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="34d62-166">Stap 3: De geïntegreerde AIP-labelclient installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="34d62-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="34d62-167">Download de geïntegreerde AIP-labelingclient in het [Microsoft Downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="34d62-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="34d62-168">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="34d62-168">For more information, see:</span></span>

- [<span data-ttu-id="34d62-169">AIP-documentatie</span><span class="sxs-lookup"><span data-stu-id="34d62-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="34d62-170">AIP-versiegeschiedenis en ondersteuningsbeleid</span><span class="sxs-lookup"><span data-stu-id="34d62-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="34d62-171">AIP-systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="34d62-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="34d62-172">AIP quickstart: De AIP-client implementeren</span><span class="sxs-lookup"><span data-stu-id="34d62-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="34d62-173">AIP-beheerdershandleiding</span><span class="sxs-lookup"><span data-stu-id="34d62-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="34d62-174">AIP-gebruikershandleiding</span><span class="sxs-lookup"><span data-stu-id="34d62-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="34d62-175">Meer informatie over gevoeligheidslabels voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34d62-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="34d62-176">Stap 4: AIP-apps configureren in Windows</span><span class="sxs-lookup"><span data-stu-id="34d62-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="34d62-177">AIP-apps in Windows hebben de volgende registersleutel nodig om ze te wijzen naar de juiste soevereine cloud voor Azure China:</span><span class="sxs-lookup"><span data-stu-id="34d62-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="34d62-178">Register-knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="34d62-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="34d62-179">Naam = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="34d62-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="34d62-180">Waarde = `6` (standaard = 0)</span><span class="sxs-lookup"><span data-stu-id="34d62-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="34d62-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="34d62-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34d62-182">Zorg ervoor dat u de registersleutel niet verwijdert nadat u de registersleutel hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="34d62-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="34d62-183">Als de sleutel leeg, onjuist of niet aanwezig is, gedraagt de functionaliteit zich als de standaardwaarde (standaardwaarde = 0 voor de commerciële cloud).</span><span class="sxs-lookup"><span data-stu-id="34d62-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="34d62-184">Als de sleutel leeg of onjuist is, wordt er ook een afdrukfout toegevoegd aan het logboek.</span><span class="sxs-lookup"><span data-stu-id="34d62-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="34d62-185">Stap 5: De on-premises AIP-scanner installeren en inhoudsscantaken beheren</span><span class="sxs-lookup"><span data-stu-id="34d62-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="34d62-186">Installeer de on-premises AIP-scanner om uw netwerk- en inhoudsaandelen te scannen op gevoelige gegevens en pas classificatie- en beveiligingslabels toe zoals geconfigureerd in het beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="34d62-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="34d62-187">Wanneer u Azure AD-toepassingen maakt en configureert voor de opdracht  [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) worden in het deelvenster API-machtigingen aanvragen de API's weergegeven die door mijn organisatie worden gebruikt in plaats van op het tabblad Api's van **Microsoft.**  Selecteer de **API's die mijn organisatie gebruikt om** vervolgens Azure Rights Management Services te **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="34d62-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="34d62-188">Wanneer u de scanner installeert en uw inhoudsscantaken beheert, gebruikt u de volgende cmdlets in plaats van de Azure-portalinterface die door de commerciële aanbiedingen wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="34d62-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="34d62-189">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="34d62-189">Cmdlet</span></span> | <span data-ttu-id="34d62-190">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="34d62-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="34d62-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="34d62-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="34d62-192">Hiermee voegt u een nieuwe opslagplaats toe aan uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="34d62-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="34d62-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="34d62-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="34d62-194">Hier krijgt u meer informatie over uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="34d62-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="34d62-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="34d62-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="34d62-196">Hier krijgt u informatie over de opslagplaatsen die zijn gedefinieerd voor uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="34d62-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="34d62-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="34d62-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="34d62-198">Hiermee verwijdert u uw taak voor het scannen van inhoud.</span><span class="sxs-lookup"><span data-stu-id="34d62-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="34d62-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="34d62-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="34d62-200">Hiermee verwijdert u een opslagplaats uit uw taak voor inhoudsscans.</span><span class="sxs-lookup"><span data-stu-id="34d62-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="34d62-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="34d62-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="34d62-202">Hiermee definieert u instellingen voor uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="34d62-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="34d62-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="34d62-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="34d62-204">Hiermee definieert u instellingen voor een bestaande opslagplaats in uw inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="34d62-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="34d62-205">Wanneer [u de scanner installeert,](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)gebruikt u dezelfde clusternaam in de opdracht [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) om meerdere scannerknooppunten aan hetzelfde cluster te koppelen.</span><span class="sxs-lookup"><span data-stu-id="34d62-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="34d62-206">Als u hetzelfde cluster gebruikt voor meerdere scannerknooppunten, kunnen meerdere scanners samenwerken om uw scans uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="34d62-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="34d62-207">Gebruik de [cmdlet Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) om details over uw cluster te retourneren.</span><span class="sxs-lookup"><span data-stu-id="34d62-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="34d62-208">Zie Wat is de geïntegreerde labelscanner voor [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) en [Uw inhoudsscantaken beheren met alleen PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="34d62-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>