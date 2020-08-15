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
description: 'Overzicht: DNS-records voor Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689152"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="dfb30-103">DNS-records voor Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="dfb30-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="dfb30-104">*Dit artikel is van toepassing op Office 365 GCC High en Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="dfb30-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="dfb30-105">Als onderdeel van de onboarding van Office 365 GCC, moet u uw SMTP-en SIP-domeinen toevoegen aan uw online services-Tenant.</span><span class="sxs-lookup"><span data-stu-id="dfb30-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="dfb30-106">U doet dit met behulp van de New-MsolDomain-cmdlet in azure AD PowerShell of de [Azure Government Portal](https://portal.azure.us) gebruiken om het proces voor het toevoegen van een domein en het eigendom ervan te starten.</span><span class="sxs-lookup"><span data-stu-id="dfb30-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="dfb30-107">Wanneer u uw domein hebt toegevoegd aan de Tenant en gevalideerd, gebruikt u de volgende richtlijnen om de juiste DNS-records voor de services toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="dfb30-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="dfb30-108">Mogelijk moet u de onderstaande tabel aanpassen aan de behoeften van uw organisatie met betrekking tot de inkomende MX-record (s) en eventuele bestaande Exchange Autodiscover-record (s) die u hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="dfb30-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="dfb30-109">We raden u ten zeerste aan om deze DNS-records met uw berichten team te coördineren om te voorkomen dat u een e-mailbericht veroudert of niet.</span><span class="sxs-lookup"><span data-stu-id="dfb30-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="dfb30-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dfb30-110">Exchange Online</span></span>

| <span data-ttu-id="dfb30-111">Type</span><span class="sxs-lookup"><span data-stu-id="dfb30-111">Type</span></span> | <span data-ttu-id="dfb30-112">Priority</span><span class="sxs-lookup"><span data-stu-id="dfb30-112">Priority</span></span> | <span data-ttu-id="dfb30-113">Host name</span><span class="sxs-lookup"><span data-stu-id="dfb30-113">Host name</span></span> | <span data-ttu-id="dfb30-114">Verwijst naar het adres of de waarde</span><span class="sxs-lookup"><span data-stu-id="dfb30-114">Points to address or value</span></span> | <span data-ttu-id="dfb30-115">TTL</span><span class="sxs-lookup"><span data-stu-id="dfb30-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="dfb30-116">MX</span><span class="sxs-lookup"><span data-stu-id="dfb30-116">MX</span></span> | <span data-ttu-id="dfb30-117">0</span><span class="sxs-lookup"><span data-stu-id="dfb30-117">0</span></span> | @ | <span data-ttu-id="dfb30-118">*Tenant*. mail.Protection.office365.us (zie hieronder voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="dfb30-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="dfb30-119">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-119">1 Hour</span></span> |
| <span data-ttu-id="dfb30-120">TXT</span><span class="sxs-lookup"><span data-stu-id="dfb30-120">TXT</span></span> | - | @ | <span data-ttu-id="dfb30-121">v = spf1 include:SPF. Protection. office365. us-all</span><span class="sxs-lookup"><span data-stu-id="dfb30-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="dfb30-122">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-122">1 Hour</span></span> |
| <span data-ttu-id="dfb30-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="dfb30-123">CNAME</span></span> | - | <span data-ttu-id="dfb30-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dfb30-124">autodiscover</span></span> | <span data-ttu-id="dfb30-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="dfb30-125">autodiscover.office365.us</span></span> | <span data-ttu-id="dfb30-126">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="dfb30-127">Record Exchange automatisch opsporen</span><span class="sxs-lookup"><span data-stu-id="dfb30-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="dfb30-128">Als u Exchange Server on-premises hebt, wordt u aangeraden uw bestaande record te verlaten terwijl u migreert naar Exchange Online en de record bij te werken wanneer u de migratie hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="dfb30-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="dfb30-129">MX-record voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dfb30-129">Exchange Online MX Record</span></span>

<span data-ttu-id="dfb30-130">De MX-recordwaarde voor uw geaccepteerde domeinen volgt een standaardindeling zoals hierboven aangegeven: *Tenant*. mail.Protection.office365.us, waarbij de *Tenant* wordt vervangen door het eerste deel van de standaardnaam van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="dfb30-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="dfb30-131">Als de naam van de Tenant bijvoorbeeld contoso.onmicrosoft.us is, gebruikt u **contoso.mail.Protection.office365.us** als de waarde voor uw MX-record.</span><span class="sxs-lookup"><span data-stu-id="dfb30-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="dfb30-132">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="dfb30-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="dfb30-133">CNAME-records</span><span class="sxs-lookup"><span data-stu-id="dfb30-133">CNAME records</span></span>

| <span data-ttu-id="dfb30-134">Type</span><span class="sxs-lookup"><span data-stu-id="dfb30-134">Type</span></span> | <span data-ttu-id="dfb30-135">Host name</span><span class="sxs-lookup"><span data-stu-id="dfb30-135">Host name</span></span> | <span data-ttu-id="dfb30-136">Verwijst naar het adres of de waarde</span><span class="sxs-lookup"><span data-stu-id="dfb30-136">Points to address or value</span></span> | <span data-ttu-id="dfb30-137">TTL</span><span class="sxs-lookup"><span data-stu-id="dfb30-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="dfb30-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="dfb30-138">CNAME</span></span> | <span data-ttu-id="dfb30-139">sip</span><span class="sxs-lookup"><span data-stu-id="dfb30-139">sip</span></span> | <span data-ttu-id="dfb30-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="dfb30-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="dfb30-141">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-141">1 Hour</span></span> |
| <span data-ttu-id="dfb30-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="dfb30-142">CNAME</span></span> | <span data-ttu-id="dfb30-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dfb30-143">lyncdiscover</span></span> | <span data-ttu-id="dfb30-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="dfb30-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="dfb30-145">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="dfb30-146">SRV-records</span><span class="sxs-lookup"><span data-stu-id="dfb30-146">SRV records</span></span>

| <span data-ttu-id="dfb30-147">Type</span><span class="sxs-lookup"><span data-stu-id="dfb30-147">Type</span></span> | <span data-ttu-id="dfb30-148">Service</span><span class="sxs-lookup"><span data-stu-id="dfb30-148">Service</span></span> | <span data-ttu-id="dfb30-149">Protocol</span><span class="sxs-lookup"><span data-stu-id="dfb30-149">Protocol</span></span> | <span data-ttu-id="dfb30-150">Poort</span><span class="sxs-lookup"><span data-stu-id="dfb30-150">Port</span></span> | <span data-ttu-id="dfb30-151">Dikte</span><span class="sxs-lookup"><span data-stu-id="dfb30-151">Weight</span></span> | <span data-ttu-id="dfb30-152">Priority</span><span class="sxs-lookup"><span data-stu-id="dfb30-152">Priority</span></span> | <span data-ttu-id="dfb30-153">Naam</span><span class="sxs-lookup"><span data-stu-id="dfb30-153">Name</span></span> | <span data-ttu-id="dfb30-154">Doel</span><span class="sxs-lookup"><span data-stu-id="dfb30-154">Target</span></span> | <span data-ttu-id="dfb30-155">TTL</span><span class="sxs-lookup"><span data-stu-id="dfb30-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="dfb30-156">SRV</span><span class="sxs-lookup"><span data-stu-id="dfb30-156">SRV</span></span> | <span data-ttu-id="dfb30-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="dfb30-157">\_sip</span></span> | <span data-ttu-id="dfb30-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="dfb30-158">\_tls</span></span> | <span data-ttu-id="dfb30-159">443</span><span class="sxs-lookup"><span data-stu-id="dfb30-159">443</span></span> | <span data-ttu-id="dfb30-160">1</span><span class="sxs-lookup"><span data-stu-id="dfb30-160">1</span></span> | <span data-ttu-id="dfb30-161">100</span><span class="sxs-lookup"><span data-stu-id="dfb30-161">100</span></span> | @ | <span data-ttu-id="dfb30-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="dfb30-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="dfb30-163">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-163">1 Hour</span></span> |
| <span data-ttu-id="dfb30-164">SRV</span><span class="sxs-lookup"><span data-stu-id="dfb30-164">SRV</span></span> | <span data-ttu-id="dfb30-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="dfb30-165">\_sipfederationtls</span></span> | <span data-ttu-id="dfb30-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="dfb30-166">\_tcp</span></span> | <span data-ttu-id="dfb30-167">5061</span><span class="sxs-lookup"><span data-stu-id="dfb30-167">5061</span></span> | <span data-ttu-id="dfb30-168">1</span><span class="sxs-lookup"><span data-stu-id="dfb30-168">1</span></span> | <span data-ttu-id="dfb30-169">100</span><span class="sxs-lookup"><span data-stu-id="dfb30-169">100</span></span> | @ | <span data-ttu-id="dfb30-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="dfb30-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="dfb30-171">1 uur</span><span class="sxs-lookup"><span data-stu-id="dfb30-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="dfb30-172">Extra DNS-records</span><span class="sxs-lookup"><span data-stu-id="dfb30-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfb30-173">Als u een bestaande *msoid* CNAME-record hebt in uw DNS-zone, moet u de record op dit moment **verwijderen** uit DNS.</span><span class="sxs-lookup"><span data-stu-id="dfb30-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="dfb30-174">De msoid-record is niet compatibel met Microsoft 365 Enterprise *-apps (voorheen Office 365 ProPlus)* en kan de activering van de Cloud verhinderen.</span><span class="sxs-lookup"><span data-stu-id="dfb30-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
