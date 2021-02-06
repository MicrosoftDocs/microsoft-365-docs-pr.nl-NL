---
title: Verbind uw domein met Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Lees hier hoe u uw domein kunt verifiëren en DNS-records kunt maken met Microsoft 365.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: c5c33af8a5635d1092aec2f1bffdfc942f2e4851
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126333"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="08a1b-103">Verbind uw domein met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08a1b-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="08a1b-104">Als u geen domein toevoegt, maken de mensen in uw organisatie gebruik van het domein onmicrosoft.com voor hun e-mailadressen, totdat u dit wel doet.</span><span class="sxs-lookup"><span data-stu-id="08a1b-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="08a1b-105">Het is belangrijk om een domein toe te voegen voordat u gebruikers toevoegt, zodat u die niet tweemaal hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="08a1b-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="08a1b-106">[Raadpleeg Veelgestelde vragen over domeinen](../setup/domains-faq.yml) als u hieronder niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="08a1b-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="08a1b-107">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="08a1b-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="08a1b-108">U ontvangt de informatie voor de MX-record via de domeininstallatiewizard in Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="08a1b-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="08a1b-109">Voeg een nieuwe MX-record toe op de website van de hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="08a1b-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="08a1b-110">Zorg dat de velden zijn ingesteld op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="08a1b-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="08a1b-111">Recordtype: `MX`</span><span class="sxs-lookup"><span data-stu-id="08a1b-111">Record Type: `MX`</span></span>
- <span data-ttu-id="08a1b-112">Prioriteit: instellen op de hoogst beschikbare waarde, meestal `0`.</span><span class="sxs-lookup"><span data-stu-id="08a1b-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="08a1b-113">Hostnaam: `@`</span><span class="sxs-lookup"><span data-stu-id="08a1b-113">Host Name: `@`</span></span>
- <span data-ttu-id="08a1b-114">Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="08a1b-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="08a1b-115">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="08a1b-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="08a1b-116">Sla de record op en verwijder vervolgens alle andere MX-records.</span><span class="sxs-lookup"><span data-stu-id="08a1b-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="08a1b-117">Voeg een CNAME-record toe om gebruikers met hun mailbox verbinding te laten maken</span><span class="sxs-lookup"><span data-stu-id="08a1b-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="08a1b-118">U ontvangt de informatie voor de CNAME-records via de domeininstallatiewizard in Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="08a1b-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="08a1b-119">Voeg de volgende CNAME-record toe op de website van de hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="08a1b-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="08a1b-120">Zorg dat de velden zijn ingesteld op de volgende waarden voor elk:</span><span class="sxs-lookup"><span data-stu-id="08a1b-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="08a1b-121">Recordtype: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="08a1b-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="08a1b-122">Host: plak hier de waarden die u kopieert vanuit Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="08a1b-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="08a1b-123">Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="08a1b-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="08a1b-124">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="08a1b-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="08a1b-125">Voeg een TXT-record toe om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="08a1b-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="08a1b-126">**Voordat u begint:** als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 aan te maken.</span><span class="sxs-lookup"><span data-stu-id="08a1b-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="08a1b-127">In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record op de website van de hostingprovider, zodat u beschikt over *één* enkel SPF-record waarin beide waardensets zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="08a1b-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="08a1b-128">Op de website van de hostingprovider bewerkt u de bestaande SPF-record of maakt u een nieuwe SPF-record aan.</span><span class="sxs-lookup"><span data-stu-id="08a1b-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="08a1b-129">Zorg dat de velden zijn ingesteld op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="08a1b-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="08a1b-130">Recordtype: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="08a1b-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="08a1b-131">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="08a1b-131">Host: `@`</span></span>
- <span data-ttu-id="08a1b-132">TXT-waarde: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="08a1b-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="08a1b-133">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="08a1b-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="08a1b-134">Sla de record op.</span><span class="sxs-lookup"><span data-stu-id="08a1b-134">Save the record.</span></span>

<span data-ttu-id="08a1b-135">Voor het valideren van uw SPF-record, gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span><span class="sxs-lookup"><span data-stu-id="08a1b-135">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="08a1b-136">SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden.</span><span class="sxs-lookup"><span data-stu-id="08a1b-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="08a1b-137">Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Microsoft 365 configureren.</span><span class="sxs-lookup"><span data-stu-id="08a1b-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="08a1b-138">Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) en [DMARC gebruiken om e-mail te valideren in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="08a1b-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="08a1b-139">Ga ten slotte terug naar de domeinconfiguratiewizard van het beheercentrum om uw installatie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="08a1b-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>
