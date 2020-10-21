---
title: Pariteit tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en commerciële aanbiedingen
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
description: Meer informatie over Azure Information Protection voor Office 365, beheerd door 21Vianet, en hoe u dit configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: ad3420483701c83ffef65994996047de56a7085c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644661"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="2e6f2-103">Pariteit tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="2e6f2-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="2e6f2-104">Hoewel ons doel is om alle commerciële functies en functionaliteit te bieden aan klanten in China met onze Azure Information Protection voor Office 365, beheerd door 21Vianet-aanbieding, is er een ontbrekende functionaliteit die we willen markeren.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="2e6f2-105">De volgende lijst bevat de bestaande hiaten tussen Azure Information Protection voor Office 365, beheerd door 21Vianet en onze commerciële aanbiedingen vanaf juli 2019:</span><span class="sxs-lookup"><span data-stu-id="2e6f2-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="2e6f2-106">IRM (Information Rights Management) wordt alleen ondersteund voor Microsoft 365-apps voor Enterprise (build 11731,10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="2e6f2-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="2e6f2-107">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="2e6f2-108">Migratie van Active Directory Rights Management Services (AD RMS) naar Azure Information Protection is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="2e6f2-109">Het delen van beveiligde e-mailberichten voor gebruikers in de commerciële Cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="2e6f2-110">Het delen van documenten en e-mailbijlagen aan gebruikers in de commerciële Cloud is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="2e6f2-111">Dit omvat Office 365, beheerd door 21Vianet-gebruikers in de commerciële Cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële Cloud, en gebruikers met een RMS voor individuen-licentie.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="2e6f2-112">IRM met SharePoint (sites en bibliotheken met IRM-beveiliging) is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="2e6f2-113">De Rights Management-connector is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="2e6f2-114">De extensie van het mobiele apparaat voor AD RMS is op dit moment niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="2e6f2-115">Azure Information Protection configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="2e6f2-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="2e6f2-116">Rechtenbeheer inschakelen voor de Tenant</span><span class="sxs-lookup"><span data-stu-id="2e6f2-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="2e6f2-117">Voor een juiste werking van de versleuteling moet RMS zijn ingeschakeld voor de Tenant.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="2e6f2-118">Controleer of de RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="2e6f2-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="2e6f2-119">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2e6f2-120">Als de module AIPService niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2e6f2-121">Importeer de module met `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="2e6f2-122">Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="2e6f2-123">Voer `(Get-AipServiceConfiguration).FunctionalState` en controleer of de status is `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="2e6f2-124">Voer dit uit als de functionele status wordt `Disabled` uitgevoerd `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="2e6f2-125">DNS-configuratie voor versleuteling (Windows)</span><span class="sxs-lookup"><span data-stu-id="2e6f2-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="2e6f2-126">Voor een juiste werking van versleuteling moet Office-clienttoepassingen verbinding maken met het exemplaar van de service en de bootstrap.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="2e6f2-127">Als u clienttoepassingen wilt omleiden naar het juiste service-exemplaar, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de Azure RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="2e6f2-128">Zonder de DNS SRV-record probeert de clienttoepassing standaardverbinding te maken met het openbare Cloud exemplaar en mislukt de clienttoepassing.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="2e6f2-129">Daarnaast is het raadzaam dat gebruikers zich aanmelden met een gebruikersnaam op basis van het domein van de Tenant domein (bijvoorbeeld `joe@contoso.cn` ), en niet de `onmschina` gebruikersnaam (bijvoorbeeld `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="2e6f2-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="2e6f2-130">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar het juiste service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="2e6f2-131">De RMS-ID achterhalen:</span><span class="sxs-lookup"><span data-stu-id="2e6f2-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="2e6f2-132">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2e6f2-133">Als de module AIPService niet is geïnstalleerd, voert u deze opdracht uit `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2e6f2-134">Maak verbinding met de service `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="2e6f2-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="2e6f2-135">Uitvoeren `(Get-AipServiceConfiguration).RightsManagementServiceId` om de RMS-id te achterhalen.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="2e6f2-136">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2e6f2-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="2e6f2-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="2e6f2-139">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="2e6f2-140">Target = `[GUID].rms.aadrm.cn` (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="2e6f2-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="2e6f2-141">Prioriteit, gewicht, seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="2e6f2-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="2e6f2-142">Koppel het aangepaste domein aan de Tenant in de [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="2e6f2-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="2e6f2-143">Hiermee voegt u een vermelding toe aan DNS, wat kan enkele minuten duren voordat deze is toegevoegd aan de DNS-instellingen.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="2e6f2-144">Meld u aan bij het Microsoft 365-Beheercentrum met de bijbehorende globale-beheerdersreferenties en voeg het domein toe (bijvoorbeeld `contoso.cn` ) voor het maken van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="2e6f2-145">In het verificatieproces zijn er mogelijk extra DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="2e6f2-146">Wanneer de verificatie is voltooid, kunnen gebruikers maken.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="2e6f2-147">DNS-configuratie voor versleuteling (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="2e6f2-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="2e6f2-148">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="2e6f2-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2e6f2-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="2e6f2-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="2e6f2-151">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="2e6f2-152">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="2e6f2-153">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="2e6f2-153">Port = `80`</span></span>
  - <span data-ttu-id="2e6f2-154">Prioriteit, gewicht, seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="2e6f2-154">Priority, Weight, Seconds, TTL = default values</span></span>
