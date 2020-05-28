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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Meer informatie over Azure Information Protection voor Office 365 wordt beheerd door 21Vianet en hoe u deze configureert voor klanten in China.
monikerRange: o365-21vianet
ms.openlocfilehash: 1f5d73f5c421a545ea0085f018a2c2a703b0b374
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399036"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="1d8d2-103">Pariteit tussen Azure Information Protection voor Office 365 die wordt beheerd door 21Vianet en commerciële aanbiedingen</span><span class="sxs-lookup"><span data-stu-id="1d8d2-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="1d8d2-104">Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan klanten in China met onze Azure Information Protection for Office 365 die wordt beheerd door 21Vianet-aanbieding, is er een aantal ontbrekende functionaliteit die we willen benadrukken.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="1d8d2-105">Dit zijn de bestaande hiaten tussen Azure Information Protection voor Office 365 die worden beheerd door 21Vianet en ons commerciële aanbod vanaf juli 2019:</span><span class="sxs-lookup"><span data-stu-id="1d8d2-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="1d8d2-106">Information Rights Management (IRM) wordt alleen ondersteund voor Microsoft 365 Apps for enterprise (build 11731.10000 of hoger).</span><span class="sxs-lookup"><span data-stu-id="1d8d2-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="1d8d2-107">Office 2010, Office 2013 en andere Office 2016-versies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="1d8d2-108">Migratie van Active Directory Rights Management Services (AD RMS) naar Azure Information Protection is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="1d8d2-109">Het delen van beveiligde e-mails met gebruikers in de commerciële cloud wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="1d8d2-110">Het delen van documenten en e-mailbijlagen aan gebruikers in de commerciële cloud is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="1d8d2-111">Dit omvat Office 365 dat wordt beheerd door 21Vianet-gebruikers in de commerciële cloud, niet-Office 365 die wordt beheerd door 21Vianet-gebruikers in de commerciële cloud en gebruikers met een RMS for Individuals-licentie.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="1d8d2-112">IRM met SharePoint (IRM-beschermde sites en bibliotheken) is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="1d8d2-113">De Rights Management Connector is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="1d8d2-114">De extensie Voor mobiele apparaten voor AD RMS is momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="1d8d2-115">Azure-informatiebeveiliging configureren voor klanten in China</span><span class="sxs-lookup"><span data-stu-id="1d8d2-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="1d8d2-116">Rechtenbeheer inschakelen voor de tenant</span><span class="sxs-lookup"><span data-stu-id="1d8d2-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="1d8d2-117">Om de versleuteling correct te laten werken, moet de RMS zijn ingeschakeld voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="1d8d2-118">Controleer of het RMS is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="1d8d2-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="1d8d2-119">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="1d8d2-120">Als de AIPService-module niet is geïnstalleerd, voert u uit  `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="1d8d2-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="1d8d2-121">Importeer de module met behulp van `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="1d8d2-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="1d8d2-122">Maak verbinding met de service via  `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="1d8d2-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="1d8d2-123">Uitvoeren  `(Get-AipServiceConfiguration).FunctionalState`   en controleren of de status  `Enabled` is.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="1d8d2-124">Als de functionele status  `Disabled` is, voert u uit  `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="1d8d2-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="1d8d2-125">DNS-configuratie voor versleuteling (Windows)</span><span class="sxs-lookup"><span data-stu-id="1d8d2-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="1d8d2-126">Om versleuteling correct te laten werken, moeten Office-clienttoepassingen verbinding maken met het China-exemplaar van de service en bootstrap van daaruit.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="1d8d2-127">Als u clienttoepassingen wilt omleiden naar de juiste service-instantie, moet de tenantbeheerder een DNS SRV-record configureren met informatie over de AZURE RMS-URL.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="1d8d2-128">Zonder de DNS SRV-record probeert de clienttoepassing standaard verbinding te maken met de openbare cloud-instantie en mislukt deze.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="1d8d2-129">Ook is de veronderstelling dat gebruikers zullen inloggen met een gebruikersnaam op basis van de tenant-eigendom domein `joe@contoso.cn` (bijvoorbeeld), en niet de gebruikersnaam `onmschina` (bijvoorbeeld, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="1d8d2-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="1d8d2-130">De domeinnaam van de gebruikersnaam wordt gebruikt voor DNS-omleiding naar de juiste serviceinstantie.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="1d8d2-131">Haal de RMS-id op:</span><span class="sxs-lookup"><span data-stu-id="1d8d2-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="1d8d2-132">Start PowerShell als beheerder.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="1d8d2-133">Als de AIPService-module niet is geïnstalleerd, voert u uit  `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="1d8d2-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="1d8d2-134">Maak verbinding met de service via  `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="1d8d2-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="1d8d2-135">Ren  `(Get-AipServiceConfiguration).RightsManagementServiceId`   om de RMS-id te krijgen.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="1d8d2-136">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="1d8d2-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="1d8d2-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="1d8d2-139">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="1d8d2-140">Doel =  `[GUID].rms.aadrm.cn`   (waarbij GUID de RMS-id is)</span><span class="sxs-lookup"><span data-stu-id="1d8d2-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="1d8d2-141">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="1d8d2-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="1d8d2-142">Koppel het aangepaste domein aan de tenant in de [Azure-portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="1d8d2-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="1d8d2-143">Dit voegt een vermelding in DNS toe, wat enkele minuten kan duren voordat u wordt geverifieerd nadat u de waarde aan de DNS-instellingen hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="1d8d2-144">Meld u aan bij het Microsoft 365-beheercentrum met de bijbehorende globale beheerdersreferenties en voeg het domein (bijvoorbeeld ) toe `contoso.cn` voor het maken van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="1d8d2-145">In het verificatieproces zijn mogelijk aanvullende DNS-wijzigingen vereist.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="1d8d2-146">Zodra de verificatie is uitgevoerd, kunnen gebruikers worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="1d8d2-147">DNS-configuratie voor versleuteling (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="1d8d2-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="1d8d2-148">Meld u aan bij uw DNS-provider, navigeer naar de DNS-instellingen voor het domein en voeg vervolgens een nieuwe SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="1d8d2-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="1d8d2-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="1d8d2-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="1d8d2-151">Naam = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="1d8d2-152">Doel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="1d8d2-153">Poort = `80`</span><span class="sxs-lookup"><span data-stu-id="1d8d2-153">Port = `80`</span></span>
  - <span data-ttu-id="1d8d2-154">Prioriteit, Gewicht, Seconden, TTL = standaardwaarden</span><span class="sxs-lookup"><span data-stu-id="1d8d2-154">Priority, Weight, Seconds, TTL = default values</span></span>
