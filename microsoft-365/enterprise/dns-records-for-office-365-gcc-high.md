---
title: DNS-records voor Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Samenvatting: DNS-records voor Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689152"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="89eec-103">DNS-records voor Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="89eec-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="89eec-104">*Dit artikel is van toepassing op Office 365 GCC Hoog en Microsoft 365 GCC Hoog*</span><span class="sxs-lookup"><span data-stu-id="89eec-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="89eec-105">Als onderdeel van onboarding Office 365 GCC High, moet u uw SMTP- en SIP-domeinen toevoegen aan uw Online Services-tenant.</span><span class="sxs-lookup"><span data-stu-id="89eec-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="89eec-106">U doet dit met de New-MsolDomain cmdlet in Azure AD PowerShell of gebruik de [Azure Government Portal](https://portal.azure.us) om het proces van het toevoegen van het domein te starten en het eigendom te bewijzen.</span><span class="sxs-lookup"><span data-stu-id="89eec-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="89eec-107">Nadat u uw domeinen hebt toegevoegd aan uw tenant en hebt gevalideerd, gebruikt u de volgende richtlijnen om de juiste DNS-records toe te voegen voor de onderstaande services.</span><span class="sxs-lookup"><span data-stu-id="89eec-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="89eec-108">Mogelijk moet u de onderstaande tabel aanpassen aan de behoeften van uw organisatie met betrekking tot de inkomende MX-record(s) en eventuele bestaande Exchange Autodiscover-record(s) die u hebt.</span><span class="sxs-lookup"><span data-stu-id="89eec-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="89eec-109">We raden u ten zeerste aan deze DNS-records te coördineren met uw berichtenteam om uitval of onjuiste bezorging van e-mail te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="89eec-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="89eec-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="89eec-110">Exchange Online</span></span>

| <span data-ttu-id="89eec-111">Type</span><span class="sxs-lookup"><span data-stu-id="89eec-111">Type</span></span> | <span data-ttu-id="89eec-112">Priority</span><span class="sxs-lookup"><span data-stu-id="89eec-112">Priority</span></span> | <span data-ttu-id="89eec-113">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="89eec-113">Host name</span></span> | <span data-ttu-id="89eec-114">Wijst naar adres of waarde</span><span class="sxs-lookup"><span data-stu-id="89eec-114">Points to address or value</span></span> | <span data-ttu-id="89eec-115">TTL</span><span class="sxs-lookup"><span data-stu-id="89eec-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="89eec-116">MX</span><span class="sxs-lookup"><span data-stu-id="89eec-116">MX</span></span> | <span data-ttu-id="89eec-117">0</span><span class="sxs-lookup"><span data-stu-id="89eec-117">0</span></span> | @ | <span data-ttu-id="89eec-118">*tenant*.mail.protection.office365.us (zie hieronder voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="89eec-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="89eec-119">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-119">1 Hour</span></span> |
| <span data-ttu-id="89eec-120">TXT</span><span class="sxs-lookup"><span data-stu-id="89eec-120">TXT</span></span> | - | @ | <span data-ttu-id="89eec-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="89eec-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="89eec-122">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-122">1 Hour</span></span> |
| <span data-ttu-id="89eec-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="89eec-123">CNAME</span></span> | - | <span data-ttu-id="89eec-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="89eec-124">autodiscover</span></span> | <span data-ttu-id="89eec-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="89eec-125">autodiscover.office365.us</span></span> | <span data-ttu-id="89eec-126">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="89eec-127">Exchange Autodiscover-record</span><span class="sxs-lookup"><span data-stu-id="89eec-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="89eec-128">Als u on-premises Exchange Server, raden we u aan uw bestaande record op zijn plaats te laten terwijl u migreert naar Exchange Online en deze record bij te werken nadat u de migratie hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="89eec-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="89eec-129">Exchange Online MX-record</span><span class="sxs-lookup"><span data-stu-id="89eec-129">Exchange Online MX Record</span></span>

<span data-ttu-id="89eec-130">De MX-recordwaarde voor uw geaccepteerde domeinen volgt een standaardnotatie zoals hierboven vermeld: *tenant*.mail.protection.office365.us, die *tenant* vervangt door het eerste deel van de standaardtenatienaam.</span><span class="sxs-lookup"><span data-stu-id="89eec-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="89eec-131">Als de naam van uw tenant bijvoorbeeld contoso.onmicrosoft.us,  gebruikt u contoso.mail.protection.office365.us als de waarde voor uw MX-record.</span><span class="sxs-lookup"><span data-stu-id="89eec-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="89eec-132">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="89eec-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="89eec-133">CNAME-records</span><span class="sxs-lookup"><span data-stu-id="89eec-133">CNAME records</span></span>

| <span data-ttu-id="89eec-134">Type</span><span class="sxs-lookup"><span data-stu-id="89eec-134">Type</span></span> | <span data-ttu-id="89eec-135">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="89eec-135">Host name</span></span> | <span data-ttu-id="89eec-136">Wijst naar adres of waarde</span><span class="sxs-lookup"><span data-stu-id="89eec-136">Points to address or value</span></span> | <span data-ttu-id="89eec-137">TTL</span><span class="sxs-lookup"><span data-stu-id="89eec-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="89eec-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="89eec-138">CNAME</span></span> | <span data-ttu-id="89eec-139">sip</span><span class="sxs-lookup"><span data-stu-id="89eec-139">sip</span></span> | <span data-ttu-id="89eec-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="89eec-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="89eec-141">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-141">1 Hour</span></span> |
| <span data-ttu-id="89eec-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="89eec-142">CNAME</span></span> | <span data-ttu-id="89eec-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="89eec-143">lyncdiscover</span></span> | <span data-ttu-id="89eec-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="89eec-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="89eec-145">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="89eec-146">SRV-records</span><span class="sxs-lookup"><span data-stu-id="89eec-146">SRV records</span></span>

| <span data-ttu-id="89eec-147">Type</span><span class="sxs-lookup"><span data-stu-id="89eec-147">Type</span></span> | <span data-ttu-id="89eec-148">Service</span><span class="sxs-lookup"><span data-stu-id="89eec-148">Service</span></span> | <span data-ttu-id="89eec-149">Protocol</span><span class="sxs-lookup"><span data-stu-id="89eec-149">Protocol</span></span> | <span data-ttu-id="89eec-150">Poort</span><span class="sxs-lookup"><span data-stu-id="89eec-150">Port</span></span> | <span data-ttu-id="89eec-151">Gewicht</span><span class="sxs-lookup"><span data-stu-id="89eec-151">Weight</span></span> | <span data-ttu-id="89eec-152">Priority</span><span class="sxs-lookup"><span data-stu-id="89eec-152">Priority</span></span> | <span data-ttu-id="89eec-153">Naam</span><span class="sxs-lookup"><span data-stu-id="89eec-153">Name</span></span> | <span data-ttu-id="89eec-154">Doel</span><span class="sxs-lookup"><span data-stu-id="89eec-154">Target</span></span> | <span data-ttu-id="89eec-155">TTL</span><span class="sxs-lookup"><span data-stu-id="89eec-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="89eec-156">SRV</span><span class="sxs-lookup"><span data-stu-id="89eec-156">SRV</span></span> | <span data-ttu-id="89eec-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="89eec-157">\_sip</span></span> | <span data-ttu-id="89eec-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="89eec-158">\_tls</span></span> | <span data-ttu-id="89eec-159">443</span><span class="sxs-lookup"><span data-stu-id="89eec-159">443</span></span> | <span data-ttu-id="89eec-160">1</span><span class="sxs-lookup"><span data-stu-id="89eec-160">1</span></span> | <span data-ttu-id="89eec-161">100</span><span class="sxs-lookup"><span data-stu-id="89eec-161">100</span></span> | @ | <span data-ttu-id="89eec-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="89eec-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="89eec-163">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-163">1 Hour</span></span> |
| <span data-ttu-id="89eec-164">SRV</span><span class="sxs-lookup"><span data-stu-id="89eec-164">SRV</span></span> | <span data-ttu-id="89eec-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="89eec-165">\_sipfederationtls</span></span> | <span data-ttu-id="89eec-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="89eec-166">\_tcp</span></span> | <span data-ttu-id="89eec-167">5061</span><span class="sxs-lookup"><span data-stu-id="89eec-167">5061</span></span> | <span data-ttu-id="89eec-168">1</span><span class="sxs-lookup"><span data-stu-id="89eec-168">1</span></span> | <span data-ttu-id="89eec-169">100</span><span class="sxs-lookup"><span data-stu-id="89eec-169">100</span></span> | @ | <span data-ttu-id="89eec-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="89eec-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="89eec-171">1 uur</span><span class="sxs-lookup"><span data-stu-id="89eec-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="89eec-172">Extra DNS-records</span><span class="sxs-lookup"><span data-stu-id="89eec-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89eec-173">Als u een bestaande *msoid* CNAME-record in  uw DNS-zone hebt, moet u de record op dit moment verwijderen uit DNS.</span><span class="sxs-lookup"><span data-stu-id="89eec-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="89eec-174">De msoidrecord is niet compatibel met Microsoft 365 Enterprise Apps *(voorheen Office 365 ProPlus)* en voorkomt dat activering slaagt.</span><span class="sxs-lookup"><span data-stu-id="89eec-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
