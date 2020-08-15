---
title: DNS-records voor Office 365 DoD
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
description: 'Overzicht: DNS-records voor Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689163"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="3f672-103">DNS-records voor Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="3f672-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="3f672-104">*Dit artikel is van toepassing op Office 365 DoD en Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="3f672-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="3f672-105">Als onderdeel van de onboarding van Office 365 DoD, moet u uw SMTP-en SIP-domeinen toevoegen aan uw online services-Tenant.</span><span class="sxs-lookup"><span data-stu-id="3f672-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="3f672-106">U doet dit met behulp van de New-MsolDomain-cmdlet in azure AD PowerShell of de [Azure Government Portal](https://portal.azure.us) gebruiken om het proces voor het toevoegen van een domein en het eigendom ervan te starten.</span><span class="sxs-lookup"><span data-stu-id="3f672-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="3f672-107">Wanneer u uw domein hebt toegevoegd aan de Tenant en gevalideerd, gebruikt u de volgende richtlijnen om de juiste DNS-records voor de services toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="3f672-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="3f672-108">Mogelijk moet u de onderstaande tabel aanpassen aan de behoeften van uw organisatie met betrekking tot de inkomende MX-record (s) en eventuele bestaande Exchange Autodiscover-record (s) die u hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="3f672-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="3f672-109">We raden u ten zeerste aan om deze DNS-records met uw berichten team te coördineren om te voorkomen dat u een e-mailbericht veroudert of niet.</span><span class="sxs-lookup"><span data-stu-id="3f672-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="3f672-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f672-110">Exchange Online</span></span>

| <span data-ttu-id="3f672-111">Type</span><span class="sxs-lookup"><span data-stu-id="3f672-111">Type</span></span> | <span data-ttu-id="3f672-112">Priority</span><span class="sxs-lookup"><span data-stu-id="3f672-112">Priority</span></span> | <span data-ttu-id="3f672-113">Host name</span><span class="sxs-lookup"><span data-stu-id="3f672-113">Host name</span></span> | <span data-ttu-id="3f672-114">Verwijst naar het adres of de waarde</span><span class="sxs-lookup"><span data-stu-id="3f672-114">Points to address or value</span></span> | <span data-ttu-id="3f672-115">TTL</span><span class="sxs-lookup"><span data-stu-id="3f672-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="3f672-116">MX</span><span class="sxs-lookup"><span data-stu-id="3f672-116">MX</span></span> | <span data-ttu-id="3f672-117">0</span><span class="sxs-lookup"><span data-stu-id="3f672-117">0</span></span> | @ | <span data-ttu-id="3f672-118">*Tenant*. mail.Protection.office365.us (zie hieronder voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="3f672-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="3f672-119">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-119">1 Hour</span></span> |
| <span data-ttu-id="3f672-120">TXT</span><span class="sxs-lookup"><span data-stu-id="3f672-120">TXT</span></span> | - | @ | <span data-ttu-id="3f672-121">v = spf1 include:SPF. Protection. office365. us-all</span><span class="sxs-lookup"><span data-stu-id="3f672-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="3f672-122">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-122">1 Hour</span></span> |
| <span data-ttu-id="3f672-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="3f672-123">CNAME</span></span> | - | <span data-ttu-id="3f672-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3f672-124">autodiscover</span></span> | <span data-ttu-id="3f672-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="3f672-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="3f672-126">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="3f672-127">Record Exchange automatisch opsporen</span><span class="sxs-lookup"><span data-stu-id="3f672-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="3f672-128">Als u Exchange Server on-premises hebt, wordt u aangeraden uw bestaande record te verlaten terwijl u migreert naar Exchange Online en de record bij te werken wanneer u de migratie hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="3f672-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="3f672-129">MX-record voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f672-129">Exchange Online MX Record</span></span>

<span data-ttu-id="3f672-130">De MX-recordwaarde voor uw geaccepteerde domeinen volgt een standaardindeling zoals hierboven aangegeven: *Tenant*. mail.Protection.office365.us, waarbij de *Tenant* wordt vervangen door het eerste deel van de standaardnaam van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="3f672-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="3f672-131">Als de naam van de Tenant bijvoorbeeld contoso.onmicrosoft.us is, gebruikt u **contoso.mail.Protection.office365.us** als de waarde voor uw MX-record.</span><span class="sxs-lookup"><span data-stu-id="3f672-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="3f672-132">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="3f672-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="3f672-133">CNAME-records</span><span class="sxs-lookup"><span data-stu-id="3f672-133">CNAME records</span></span>

| <span data-ttu-id="3f672-134">Type</span><span class="sxs-lookup"><span data-stu-id="3f672-134">Type</span></span> | <span data-ttu-id="3f672-135">Host name</span><span class="sxs-lookup"><span data-stu-id="3f672-135">Host name</span></span> | <span data-ttu-id="3f672-136">Verwijst naar het adres of de waarde</span><span class="sxs-lookup"><span data-stu-id="3f672-136">Points to address or value</span></span> | <span data-ttu-id="3f672-137">TTL</span><span class="sxs-lookup"><span data-stu-id="3f672-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="3f672-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="3f672-138">CNAME</span></span> | <span data-ttu-id="3f672-139">sip</span><span class="sxs-lookup"><span data-stu-id="3f672-139">sip</span></span> | <span data-ttu-id="3f672-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="3f672-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="3f672-141">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-141">1 Hour</span></span> |
| <span data-ttu-id="3f672-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="3f672-142">CNAME</span></span> | <span data-ttu-id="3f672-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3f672-143">lyncdiscover</span></span> | <span data-ttu-id="3f672-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="3f672-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="3f672-145">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="3f672-146">SRV-records</span><span class="sxs-lookup"><span data-stu-id="3f672-146">SRV records</span></span>

| <span data-ttu-id="3f672-147">Type</span><span class="sxs-lookup"><span data-stu-id="3f672-147">Type</span></span> | <span data-ttu-id="3f672-148">Service</span><span class="sxs-lookup"><span data-stu-id="3f672-148">Service</span></span> | <span data-ttu-id="3f672-149">Protocol</span><span class="sxs-lookup"><span data-stu-id="3f672-149">Protocol</span></span> | <span data-ttu-id="3f672-150">Poort</span><span class="sxs-lookup"><span data-stu-id="3f672-150">Port</span></span> | <span data-ttu-id="3f672-151">Dikte</span><span class="sxs-lookup"><span data-stu-id="3f672-151">Weight</span></span> | <span data-ttu-id="3f672-152">Priority</span><span class="sxs-lookup"><span data-stu-id="3f672-152">Priority</span></span> | <span data-ttu-id="3f672-153">Naam</span><span class="sxs-lookup"><span data-stu-id="3f672-153">Name</span></span> | <span data-ttu-id="3f672-154">Doel</span><span class="sxs-lookup"><span data-stu-id="3f672-154">Target</span></span> | <span data-ttu-id="3f672-155">TTL</span><span class="sxs-lookup"><span data-stu-id="3f672-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="3f672-156">SRV</span><span class="sxs-lookup"><span data-stu-id="3f672-156">SRV</span></span> | <span data-ttu-id="3f672-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="3f672-157">\_sip</span></span> | <span data-ttu-id="3f672-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="3f672-158">\_tls</span></span> | <span data-ttu-id="3f672-159">443</span><span class="sxs-lookup"><span data-stu-id="3f672-159">443</span></span> | <span data-ttu-id="3f672-160">1</span><span class="sxs-lookup"><span data-stu-id="3f672-160">1</span></span> | <span data-ttu-id="3f672-161">100</span><span class="sxs-lookup"><span data-stu-id="3f672-161">100</span></span> | @ | <span data-ttu-id="3f672-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="3f672-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="3f672-163">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-163">1 Hour</span></span> |
| <span data-ttu-id="3f672-164">SRV</span><span class="sxs-lookup"><span data-stu-id="3f672-164">SRV</span></span> | <span data-ttu-id="3f672-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3f672-165">\_sipfederationtls</span></span> | <span data-ttu-id="3f672-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="3f672-166">\_tcp</span></span> | <span data-ttu-id="3f672-167">5061</span><span class="sxs-lookup"><span data-stu-id="3f672-167">5061</span></span> | <span data-ttu-id="3f672-168">1</span><span class="sxs-lookup"><span data-stu-id="3f672-168">1</span></span> | <span data-ttu-id="3f672-169">100</span><span class="sxs-lookup"><span data-stu-id="3f672-169">100</span></span> | @ | <span data-ttu-id="3f672-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="3f672-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="3f672-171">1 uur</span><span class="sxs-lookup"><span data-stu-id="3f672-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="3f672-172">Extra DNS-records</span><span class="sxs-lookup"><span data-stu-id="3f672-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f672-173">Als u een bestaande *msoid* CNAME-record hebt in uw DNS-zone, moet u de record op dit moment **verwijderen** uit DNS.</span><span class="sxs-lookup"><span data-stu-id="3f672-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="3f672-174">De msoid-record is niet compatibel met Microsoft 365 Enterprise *-apps (voorheen Office 365 ProPlus)* en kan de activering van de Cloud verhinderen.</span><span class="sxs-lookup"><span data-stu-id="3f672-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
