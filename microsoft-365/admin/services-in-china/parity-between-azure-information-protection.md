---
title: Azure Information Protection-ondersteuning voor Office 365 beheerd door 21Vianet
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
description: Meer informatie over Azure Information Protection (AIP) voor Office 365 beheerd door 21Vianet en hoe u dit configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099676"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="365da-103">Azure Information Protection-ondersteuning voor Office 365 beheerd door 21Vianet</span><span class="sxs-lookup"><span data-stu-id="365da-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="365da-104">In dit artikel worden de verschillen beschreven tussen AIP-ondersteuning (Azure Information Protection) voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen, evenals specifieke instructies voor het configureren van AIP voor klanten in China, waaronder hoe u de on-premises AIP-scanner installeert en inhoudsscantaken &mdash; beheert.</span><span class="sxs-lookup"><span data-stu-id="365da-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="365da-105">Verschillen tussen AIP voor Office 365 beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="365da-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="365da-106">Hoewel we alle commerciële functies en functionaliteit willen aanbieden aan klanten in China met onze AIP voor Office 365 beheerd door 21Vianet, is er een aantal ontbrekende functionaliteit die we willen benadrukken.</span><span class="sxs-lookup"><span data-stu-id="365da-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="365da-107">De volgende lijst bevat de bestaande hiaten tussen AIP voor Office 365 beheerd door 21Vianet en onze commerciële aanbiedingen vanaf januari 2021:</span><span class="sxs-lookup"><span data-stu-id="365da-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="365da-108">IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor ondernemingen (build 11731.10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="365da-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="365da-109">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="365da-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="365da-110">Migratie van AD RMS (Active Directory Rights Management Services) naar AIP is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="365da-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="365da-111">Het delen van beveiligde e-mailberichten met gebruikers in de commerciële cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="365da-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="365da-112">Het delen van documenten en e-mailbijlagen met gebruikers in de commerciële cloud is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="365da-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="365da-113">Dit omvat Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 beheerd door 21Vianet-gebruikers in de commerciële cloud, en gebruikers met een RMS voor individuen-licentie.</span><span class="sxs-lookup"><span data-stu-id="365da-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="365da-114">IRM met SharePoint (met IRM beveiligde sites en bibliotheken) is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="365da-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="365da-115">De extensie voor mobiele apparaten voor AD RMS is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="365da-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="365da-116">De [Mobile-viewer](/azure/information-protection/rms-client/mobile-app-faq) wordt niet ondersteund door Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="365da-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="365da-117">Het gebied AIP van de Azure Portal is niet beschikbaar voor klanten in China.</span><span class="sxs-lookup"><span data-stu-id="365da-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="365da-118">Gebruik [PowerShell-opdrachten](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) in plaats van acties uit te voeren in de portal, zoals het installeren van de on-premises scanner en het beheren van uw inhoudsscantaken.</span><span class="sxs-lookup"><span data-stu-id="365da-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="365da-119">AIP configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="365da-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="365da-120">AIP configureren voor klanten in China:</span><span class="sxs-lookup"><span data-stu-id="365da-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="365da-121">[Rights Management inschakelen voor de tenant.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="365da-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="365da-122">[DNS-versleuteling configureren.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="365da-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="365da-123">[Installeer en configureer de geïntegreerde AIP-labelclient.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="365da-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="365da-124">[Configureer AIP-apps in Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="365da-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="365da-125">[Installeer de on-premises AIP-scanner en beheer inhoudsscantaken.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="365da-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="365da-126">Stap 1: Rights Management inschakelen voor de tenant</span><span class="sxs-lookup"><span data-stu-id="365da-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="365da-127">RmS moet zijn ingeschakeld voor de tenant om de versleuteling correct te laten werken.</span><span class="sxs-lookup"><span data-stu-id="365da-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="365da-128">Controleer of RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="365da-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="365da-129">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="365da-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="365da-130">Voer de AIPService-module uit als deze niet is `Install-Module AipService` geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="365da-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="365da-131">Importeer de module met `Import-Module AipService` behulp van .</span><span class="sxs-lookup"><span data-stu-id="365da-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="365da-132">Maak verbinding met de service via `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="365da-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="365da-133">Voer `(Get-AipServiceConfiguration).FunctionalState` de status uit en controleer of dit de status `Enabled` is.</span><span class="sxs-lookup"><span data-stu-id="365da-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="365da-134">Als dit de functionele status `Disabled` is, moet u de functie `Enable-AipService` uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="365da-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="365da-135">Stap 2: DNS-versleuteling configureren</span><span class="sxs-lookup"><span data-stu-id="365da-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="365da-136">Versleuteling werkt alleen correct als Office-clienttoepassingen verbinding maken met het China-exemplaar van de service en van daardaan bootstrap.</span><span class="sxs-lookup"><span data-stu-id="365da-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="365da-137">Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="365da-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="365da-138">Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met het openbare cloud-exemplaar en mislukt dit.</span><span class="sxs-lookup"><span data-stu-id="365da-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="365da-139">Bovendien wordt aangenomen dat gebruikers zich zullen aanmelden met een gebruikersnaam die is gebaseerd op het domein van tenants (bijvoorbeeld ) en niet met de gebruikersnaam `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="365da-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="365da-140">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="365da-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="365da-141">DNS-versleuteling configureren - Windows</span><span class="sxs-lookup"><span data-stu-id="365da-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="365da-142">Krijg de RMS-id:</span><span class="sxs-lookup"><span data-stu-id="365da-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="365da-143">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="365da-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="365da-144">Voer de AIPService-module uit als deze niet is `Install-Module AipService` geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="365da-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="365da-145">Maak verbinding met de service via `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="365da-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="365da-146">Voer `(Get-AipServiceConfiguration).RightsManagementServiceId` uit om de RMS-id op te halen.</span><span class="sxs-lookup"><span data-stu-id="365da-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="365da-147">Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="365da-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="365da-148">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="365da-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="365da-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="365da-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="365da-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="365da-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="365da-151">Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="365da-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="365da-152">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="365da-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="365da-153">Koppel het aangepaste domein aan de tenant in de [Azure Portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="365da-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="365da-154">Er wordt dan een vermelding in de DNS-adressen gebruikt. Dit kan enkele minuten duren voordat de waarde is geverifieerd nadat u de waarde hebt toevoegt aan de DNS-instellingen.</span><span class="sxs-lookup"><span data-stu-id="365da-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="365da-155">Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld) voor het maken van `contoso.cn` gebruikers.</span><span class="sxs-lookup"><span data-stu-id="365da-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="365da-156">Tijdens het verificatieproces zijn mogelijk extra DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="365da-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="365da-157">Wanneer verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="365da-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="365da-158">DNS-versleuteling configureren - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="365da-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="365da-159">Meld u aan bij uw DNS-provider, ga naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="365da-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="365da-160">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="365da-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="365da-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="365da-161">Protocol = `_http`</span></span>
- <span data-ttu-id="365da-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="365da-162">Name = `_tcp`</span></span>
- <span data-ttu-id="365da-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="365da-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="365da-164">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="365da-164">Port = `80`</span></span>
- <span data-ttu-id="365da-165">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="365da-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="365da-166">Stap 3: de geïntegreerde AIP-labelclient installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="365da-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="365da-167">Download de geïntegreerde AIP-labelclient van [het Microsoft Downloadcentrum.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="365da-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="365da-168">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="365da-168">For more information, see:</span></span>

- [<span data-ttu-id="365da-169">AIP-documentatie</span><span class="sxs-lookup"><span data-stu-id="365da-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="365da-170">AIP-versiegeschiedenis en ondersteuningsbeleid</span><span class="sxs-lookup"><span data-stu-id="365da-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="365da-171">AIP-systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="365da-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="365da-172">AIP-snelstart: De AIP-client implementeren</span><span class="sxs-lookup"><span data-stu-id="365da-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="365da-173">AIP-beheerdershandleiding</span><span class="sxs-lookup"><span data-stu-id="365da-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="365da-174">AIP-gebruikershandleiding</span><span class="sxs-lookup"><span data-stu-id="365da-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="365da-175">Meer informatie over gevoeligheidslabels voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="365da-175">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="365da-176">Stap 4: AIP-apps configureren in Windows</span><span class="sxs-lookup"><span data-stu-id="365da-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="365da-177">AIP-apps in Windows hebben de volgende registersleutel nodig om ze te laten wijzen naar de juiste soevereine cloud voor Azure China:</span><span class="sxs-lookup"><span data-stu-id="365da-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="365da-178">Register-knooppunt = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="365da-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="365da-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="365da-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="365da-180">Waarde = `6` (standaard = 0)</span><span class="sxs-lookup"><span data-stu-id="365da-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="365da-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="365da-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="365da-182">Zorg ervoor dat u de registersleutel niet verwijdert nadat u de installatie hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="365da-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="365da-183">Als de sleutel leeg, onjuist of niet aanwezig is, gedraagt de functionaliteit zich als de standaardwaarde (standaardwaarde = 0 voor de commerciële cloud).</span><span class="sxs-lookup"><span data-stu-id="365da-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="365da-184">Als de sleutel leeg of onjuist is, wordt ook een afdrukfout aan het logboek toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="365da-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="365da-185">Stap 5: de on-premises AIP-scanner installeren en inhoudsscantaken beheren</span><span class="sxs-lookup"><span data-stu-id="365da-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="365da-186">Installeer de on-premises AIP-scanner om uw netwerk- en inhouds shares te scannen op gevoelige gegevens en pas classificatie- en beveiligingslabels toe zoals geconfigureerd in het beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="365da-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="365da-187">Wanneer u de scanner installeert en uw inhoudsscantaken beheert, gebruikt u de volgende cmdlets in plaats van de Azure Portal-interface die door de commerciële aanbiedingen wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="365da-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="365da-188">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="365da-188">Cmdlet</span></span> | <span data-ttu-id="365da-189">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="365da-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="365da-190">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="365da-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="365da-191">Hiermee voegt u een nieuwe opslagplaats toe aan uw inhoudsscan taak.</span><span class="sxs-lookup"><span data-stu-id="365da-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="365da-192">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="365da-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="365da-193">Hier worden details over de inhoudsscan uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="365da-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="365da-194">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="365da-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="365da-195">Haalt informatie op over de opslagplaatsen die zijn gedefinieerd voor uw inhoudsscan..</span><span class="sxs-lookup"><span data-stu-id="365da-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="365da-196">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="365da-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="365da-197">Hiermee verwijdert u de inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="365da-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="365da-198">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="365da-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="365da-199">Hiermee verwijdert u een opslagplaats uit de inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="365da-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="365da-200">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="365da-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="365da-201">Hiermee definieert u instellingen voor de inhoudsscan.</span><span class="sxs-lookup"><span data-stu-id="365da-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="365da-202">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="365da-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="365da-203">Hiermee definieert u instellingen voor een bestaande opslagplaats in uw inhoudsscan..</span><span class="sxs-lookup"><span data-stu-id="365da-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="365da-204">Zie wat is de geïntegreerde labelscanner van Azure Information Protection voor meer [informatie?](/azure/information-protection/deploy-aip-scanner) En beheer de taken voor inhoudsscans [met alleen PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="365da-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
