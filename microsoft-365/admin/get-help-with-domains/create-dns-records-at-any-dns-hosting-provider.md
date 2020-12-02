---
title: DNS-records toevoegen om het domein te verbinden
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
description: Lees hier hoe u uw domein kunt verifiëren en DNS-records kunt maken bij een DNS-hostingprovider voor Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: bc22dbd3a050516f518c9ddc9ccf5a3af9c76f12
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519291"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="1a1c0-103">DNS-records toevoegen om het domein te verbinden</span><span class="sxs-lookup"><span data-stu-id="1a1c0-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="1a1c0-104">Als u een domein hebt aangekocht bij een externe hostingprovider, kunt u dit verbinden met Microsoft 365 door de DNS-records bij te werken in het account van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="1a1c0-105">Na het doorlopen van dit stappenproces blijft uw domein geregistreerd bij de host waar u het domein hebt gekocht, maar Microsoft 365 kan het gebruiken voor e-mailadressen (zoals gebruiker@uwdomein.com) en andere services.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="1a1c0-106">Als u geen domein toevoegt, maken de mensen in uw organisatie gebruik van het domein onmicrosoft.com voor hun e-mailadressen totdat u dit wel doet.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="1a1c0-107">Het is belangrijk om een domein toe te voegen voordat u gebruikers toevoegt, zodat u die niet tweemaal hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="1a1c0-108">[Raadpleeg Veelgestelde vragen over domeinen](../setup/domains-faq.md) als u hieronder niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="1a1c0-109">Stap 1: Voeg een TXT- of MX-record toe om te verifiëren dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="1a1c0-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="1a1c0-110">Aanbevolen: verifiëren met een TXT-record</span><span class="sxs-lookup"><span data-stu-id="1a1c0-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="1a1c0-111">Eerst moet u bewijzen dat u de eigenaar bent van het domein dat u wilt toevoegen aan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="1a1c0-112">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en selecteer **Alles weergeven** > **Instellingen** > **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="1a1c0-113">In een nieuw browsertabblad of -venster meldt u zich aan bij uw DNS-hostingprovider en vervolgens gaat u naar de locatie waar u de DNS-instellingen kunt beheren (bijv. Instellingen zonebestand, Beheer domeinen, Domeinbeheer, DNS-beheer).</span><span class="sxs-lookup"><span data-stu-id="1a1c0-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="1a1c0-114">Ga naar de pagina DNS-beheer van uw provider en voeg de TXT-record die in het Beheercentrum wordt weergegeven toe aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="1a1c0-115">Het toevoegen van deze record is niet van invloed op uw bestaande e-mail- of andere services en u kunt deze veilig verwijderen als uw domein eenmaal is verbonden met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="1a1c0-116">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="1a1c0-116">Example:</span></span>
- <span data-ttu-id="1a1c0-117">TXT-naam: `@`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-117">TXT Name: `@`</span></span>
- <span data-ttu-id="1a1c0-118">TXT-waarde: MS=ms######## (unieke ID uit het Beheercentrum)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="1a1c0-119">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="1a1c0-120">Sla de record op, ga terug naar het Beheercentrum en selecteer vervolgens **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="1a1c0-121">Het duurt ongeveer 15 minuten voordat recordwijzigingen zijn doorgevoerd, maar soms kan het langer duren.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="1a1c0-122">Wacht even en probeer het een aantal keer totdat de wijziging is doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="1a1c0-123">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="1a1c0-124">Verifiëren met een MX-record</span><span class="sxs-lookup"><span data-stu-id="1a1c0-124">Verify with an MX record</span></span>

<span data-ttu-id="1a1c0-125">Als het toevoegen van TXT-records niet wordt toegestaan door uw registrar, kunt u verifiëren door een MX-record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="1a1c0-126">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en selecteer **Alles weergeven** > **Instellingen** > **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="1a1c0-127">In een nieuw browsertabblad of -venster meldt u zich aan bij uw DNS-hostingprovider en vervolgens gaat u naar de locatie waar u de DNS-instellingen kunt beheren (bijv. Instellingen zonebestand, Beheer domeinen, Domeinbeheer, DNS-beheer).</span><span class="sxs-lookup"><span data-stu-id="1a1c0-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="1a1c0-128">Ga naar de pagina DNS-beheer van uw provider en voeg de MX-record die in het Beheercentrum wordt weergegeven, toe aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="1a1c0-129">Deze MX-record moet de hoogste **prioriteit** hebben van alle bestaande MX-records voor het domein.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="1a1c0-130">Anders kunnen er problemen optreden bij het verzenden en ontvangen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="1a1c0-131">U moet deze records verwijderen zodra de domeinverificatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="1a1c0-132">Zorg dat de velden zijn ingesteld op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="1a1c0-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="1a1c0-133">Recordtype: `MX`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-133">Record Type: `MX`</span></span>
- <span data-ttu-id="1a1c0-134">Prioriteit: instellen op de hoogst beschikbare waarde, meestal `0`.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="1a1c0-135">Hostnaam: `@`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-135">Host Name: `@`</span></span>
- <span data-ttu-id="1a1c0-136">Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-137">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="1a1c0-138">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="1a1c0-139">Stap 2: DNS-records toevoegen om Microsoft-services te verbinden</span><span class="sxs-lookup"><span data-stu-id="1a1c0-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="1a1c0-140">In een nieuw browsertabblad of -venster meldt u zich aan bij uw DNS-hostingprovider en gaat u naar de locatie waar u de DNS-instellingen kunt beheren (bijv. Instellingen zonebestand, Beheer domeinen, Domeinbeheer, DNS-beheer).</span><span class="sxs-lookup"><span data-stu-id="1a1c0-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="1a1c0-141">Afhankelijk van de services die u wilt inschakelen, kunt u verschillende typen DNS-records toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="1a1c0-142">Een MX-record toevoegen voor e-mail (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="1a1c0-143">**Voordat u begint:** als gebruikers al een e-mailadres hebben met uw domein (zoals user@yourdomain.com), kunt u hun accounts aanmaken in het Beheercentrum voordat u de MX-records instelt.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="1a1c0-144">Op die manier blijven ze e-mail ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="1a1c0-145">Wanneer u de MX-record van uw domein bijwerkt, wordt alle nieuwe e-mail voor iedereen die uw domein gebruikt, verzonden naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="1a1c0-146">Elk e-mailbericht dat u al hebt, blijft bij uw huidige e-mailhost, tenzij u besluit [e-mail en contactpersonen te migreren naar Microsoft 365](../setup/migrate-email-and-contacts-admin.md).</span><span class="sxs-lookup"><span data-stu-id="1a1c0-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="1a1c0-147">U ontvangt de informatie voor de MX-record via de domeininstallatiewizard in Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="1a1c0-148">Voeg een nieuwe MX-record toe op de website van de hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="1a1c0-149">Zorg dat de velden zijn ingesteld op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="1a1c0-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="1a1c0-150">Recordtype: `MX`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-150">Record Type: `MX`</span></span>
- <span data-ttu-id="1a1c0-151">Prioriteit: instellen op de hoogst beschikbare waarde, meestal `0`.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="1a1c0-152">Hostnaam: `@`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-152">Host Name: `@`</span></span>
- <span data-ttu-id="1a1c0-153">Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-154">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="1a1c0-155">Sla de record op en verwijder vervolgens alle andere MX-records.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="1a1c0-156">Voeg CNAME-records toe om andere services te verbinden (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="1a1c0-157">U ontvangt de informatie voor de CNAME-records via de domeininstallatiewizard in Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="1a1c0-158">Voeg op de website van de hostingprovider CNAME-records toe voor elke service die u wilt verbinden.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="1a1c0-159">Zorg dat de velden zijn ingesteld op de volgende waarden voor elk:</span><span class="sxs-lookup"><span data-stu-id="1a1c0-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="1a1c0-160">Recordtype: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="1a1c0-161">Host: plak hier de waarden die u kopieert vanuit Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="1a1c0-162">Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-163">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="1a1c0-164">Een SPF TXT-record toevoegen of bewerken om spam te helpen voorkomen (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="1a1c0-165">**Voordat u begint:** als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 aan te maken.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="1a1c0-166">In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record op de website van de hostingprovider, zodat u beschikt over *één* enkel SPF-record waarin beide waardensets zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="1a1c0-167">Op de website van de hostingprovider bewerkt u de bestaande SPF-record of maakt u een nieuwe SPF-record aan.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="1a1c0-168">Zorg dat de velden zijn ingesteld op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="1a1c0-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="1a1c0-169">Recordtype: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="1a1c0-170">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-170">Host: `@`</span></span>
- <span data-ttu-id="1a1c0-171">TXT-waarde: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="1a1c0-172">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="1a1c0-173">Sla de record op.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-173">Save the record.</span></span>

<span data-ttu-id="1a1c0-174">Voor het valideren van uw SPF-record, gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-174">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="1a1c0-175">SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="1a1c0-176">Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Microsoft 365 configureren.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="1a1c0-177">Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) en [DMARC gebruiken om e-mail te valideren in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1a1c0-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="1a1c0-178">SRV-records toevoegen voor communicatieservices (Teams, Skype voor Bedrijven)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="1a1c0-179">Voeg op de website van de hostingprovider SRV-records toe voor elke service die u wilt verbinden.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="1a1c0-180">Zorg dat de velden zijn ingesteld op de volgende waarden voor elk:</span><span class="sxs-lookup"><span data-stu-id="1a1c0-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="1a1c0-181">Recordtype: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="1a1c0-182">Naam: `@`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-182">Name: `@`</span></span>
- <span data-ttu-id="1a1c0-183">Doel: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-184">Protocol: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-185">Service: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-186">Prioriteit: `100`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-186">Priority: `100`</span></span>
- <span data-ttu-id="1a1c0-187">Gewicht: `1`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-187">Weight: `1`</span></span>
- <span data-ttu-id="1a1c0-188">Poort: kopieer de waarde uit het Beheercentrum en plak deze hier.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="1a1c0-189">TTL: `3600‎` (of de standaardwaarde van uw provider)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="1a1c0-190">Sla de record op.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="1a1c0-191">Veldbeperkingen en tijdelijke oplossingen voor SRV-records</span><span class="sxs-lookup"><span data-stu-id="1a1c0-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="1a1c0-192">Sommige hostingproviders stellen beperkingen in voor veldwaarden binnen SRV-records.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="1a1c0-193">Hier vindt u enkele veelvoorkomende tijdelijke oplossingen voor deze beperkingen.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="1a1c0-194">Naam</span><span class="sxs-lookup"><span data-stu-id="1a1c0-194">Name</span></span>
<span data-ttu-id="1a1c0-195">Als de hostingprovider niet toestaat om dit veld in te stellen op **@**, laat u het veld leeg.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="1a1c0-196">Gebruik deze methode *alleen* wanneer de hostingprovider afzonderlijke velden voor de waarden Service en Protocol heeft.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="1a1c0-197">Raadpleeg anders onderstaande opmerkingen bij Service en Protocol.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="1a1c0-198">Service en Protocol</span><span class="sxs-lookup"><span data-stu-id="1a1c0-198">Service and Protocol</span></span>
<span data-ttu-id="1a1c0-199">Als uw hostingprovider niet in deze velden voor SRV-records voorziet, geeft u de waarden voor **Service** en **Protocol** op in het **Naam**-veld van de record.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="1a1c0-200">(Opmerking: Afhankelijk van de hostingprovider kan het **Naam**-veld anders heten, bijvoorbeeld **Host**, **Hostnaam** of **Subdomein**.) Om deze waarden toe te voegen, maakt u één enkele tekenreeks, waarin de waarden van elkaar zijn gescheiden door een punt.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="1a1c0-201">Voorbeeld: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="1a1c0-202">Prioriteit, Gewicht en Poort</span><span class="sxs-lookup"><span data-stu-id="1a1c0-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="1a1c0-203">Als uw hostingprovider niet in deze velden voor SRV-records voorziet, geeft u ze op in het **Doel**-veld van de record.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="1a1c0-204">(Opmerking: afhankelijk van uw hostingprovider kan het **Doel**-veld anders heten, bijvoorbeeld: **Inhoud**, **IP-adres**, of **Doelhost**.)</span><span class="sxs-lookup"><span data-stu-id="1a1c0-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="1a1c0-205">Als u deze waarden wilt toevoegen, moet u één enkele tekenreeks aanmaken, waarbij de waarden worden gescheiden door spaties en *soms eindigen met een punt* (neem contact op met uw provider als u niet zeker bent).</span><span class="sxs-lookup"><span data-stu-id="1a1c0-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="1a1c0-206">De waarden moeten in de volgende volgorde worden opgenomen: Prioriteit, Gewicht, Poort, Doel.</span><span class="sxs-lookup"><span data-stu-id="1a1c0-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="1a1c0-207">Voorbeeld 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="1a1c0-208">Voorbeeld 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="1a1c0-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
