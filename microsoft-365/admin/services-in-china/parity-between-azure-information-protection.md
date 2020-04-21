---
title: Office 365, beheerd door 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Meer informatie over Azure Information Protection voor Office 365 wordt beheerd door 21Vianet en hoe u deze configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627652"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="62fba-103">Pariteit tussen Azure Information Protection voor Office 365 die wordt beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="62fba-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="62fba-104">Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze Azure Information Protection for Office 365 die wordt beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.</span><span class="sxs-lookup"><span data-stu-id="62fba-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="62fba-105">Dit zijn de bestaande hiaten tussen Azure Information Protection voor Office 365 die worden beheerd door 21Vianet en ons commerciële aanbod vanaf juli 2019:</span><span class="sxs-lookup"><span data-stu-id="62fba-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="62fba-106">Information Rights Management (IRM) wordt alleen ondersteund voor Microsoft 365 Apps for enterprise (build 11731.10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="62fba-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="62fba-107">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="62fba-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="62fba-108">Migratie van Active Directory Rights Management Services (AD RMS) naar Azure Information Protection is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="62fba-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="62fba-109">Het delen van beveiligde e-mails met gebruikers in de commerciële cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="62fba-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="62fba-110">Het delen van documenten en e-mailbijlagen aan gebruikers in de commerciële cloud is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="62fba-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="62fba-111">Dit omvat Office 365 dat wordt beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS for Individuals-licentie.</span><span class="sxs-lookup"><span data-stu-id="62fba-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="62fba-112">IRM met SharePoint (IRM-beschermde sites en bibliotheken) is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="62fba-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="62fba-113">De Rights Management Connector is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="62fba-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="62fba-114">De extensie Voor mobiele apparaten voor AD RMS is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="62fba-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="62fba-115">Azure-informatiebeveiliging configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="62fba-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="62fba-116">Rechtenbeheer inschakelen voor de tenant</span><span class="sxs-lookup"><span data-stu-id="62fba-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="62fba-117">Om de versleuteling correct te laten werken, moet de RMS zijn ingeschakeld voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="62fba-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="62fba-118">Controleer of het RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="62fba-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="62fba-119">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="62fba-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="62fba-120">Als de AIPService-module niet `Install-Module AipService`is geïnstalleerd, voert u uit .</span><span class="sxs-lookup"><span data-stu-id="62fba-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="62fba-121">Importeer de `Import-Module AipService`module met behulp van .</span><span class="sxs-lookup"><span data-stu-id="62fba-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="62fba-122">Maak verbinding met `Connect-AipService -environmentname azurechinacloud`de service via .</span><span class="sxs-lookup"><span data-stu-id="62fba-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="62fba-123">Uitvoeren `(Get-AipServiceConfiguration).FunctionalState` en controleren of `Enabled`de status is.</span><span class="sxs-lookup"><span data-stu-id="62fba-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="62fba-124">Als de functionele `Disabled`status `Enable-AipService`is, voert u uit .</span><span class="sxs-lookup"><span data-stu-id="62fba-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="62fba-125">DNS-configuratie voor versleuteling (Windows)</span><span class="sxs-lookup"><span data-stu-id="62fba-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="62fba-126">Om versleuteling correct te laten werken, moeten Office-clienttoepassingen verbinding maken met het China-exemplaar van de service en bootstrap van daaruit.</span><span class="sxs-lookup"><span data-stu-id="62fba-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="62fba-127">Als u clienttoepassingen wilt omleiden naar de juiste service-instantie, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de AZURE RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="62fba-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="62fba-128">Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met de openbare cloud-instantie en mislukt deze.</span><span class="sxs-lookup"><span data-stu-id="62fba-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="62fba-129">Ook is de veronderstelling dat gebruikers zullen inloggen met een gebruikersnaam op `joe@contoso.cn`basis van `onmschina` de tenant-eigendom `joe@contoso.onmschina.cn`domein (bijvoorbeeld), en niet de gebruikersnaam (bijvoorbeeld, ).</span><span class="sxs-lookup"><span data-stu-id="62fba-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="62fba-130">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar de juiste serviceinstantie.</span><span class="sxs-lookup"><span data-stu-id="62fba-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="62fba-131">Haal de RMS-id op:</span><span class="sxs-lookup"><span data-stu-id="62fba-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="62fba-132">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="62fba-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="62fba-133">Als de AIPService-module niet `Install-Module AipService`is geïnstalleerd, voert u uit .</span><span class="sxs-lookup"><span data-stu-id="62fba-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="62fba-134">Maak verbinding met `Connect-AipService -environmentname azurechinacloud`de service via .</span><span class="sxs-lookup"><span data-stu-id="62fba-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="62fba-135">Ren `(Get-AipServiceConfiguration).RightsManagementServiceId` om de RMS-id te krijgen.</span><span class="sxs-lookup"><span data-stu-id="62fba-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="62fba-136">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="62fba-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="62fba-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="62fba-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="62fba-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="62fba-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="62fba-139">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="62fba-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="62fba-140">Doel `[GUID].rms.aadrm.cn` = (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="62fba-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="62fba-141">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="62fba-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="62fba-142">Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="62fba-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="62fba-143">Dit voegt een vermelding in DNS toe, wat enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde aan de DNS-instellingen hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="62fba-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="62fba-144">Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende `contoso.cn`globale beheerdersreferenties en voeg het domein (bijvoorbeeld ) toe voor het maken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="62fba-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="62fba-145">In het verificatieproces zijn mogelijk aanvullende DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="62fba-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="62fba-146">Zodra de verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="62fba-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="62fba-147">DNS-configuratie voor versleuteling (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="62fba-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="62fba-148">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="62fba-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="62fba-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="62fba-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="62fba-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="62fba-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="62fba-151">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="62fba-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="62fba-152">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="62fba-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="62fba-153">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="62fba-153">Port = `80`</span></span>
  - <span data-ttu-id="62fba-154">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="62fba-154">Priority, Weight, Seconds, TTL = default values</span></span>
