---
title: Mail flow Intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Beheerders kunnen de foutcodes voor de bezorging van berichten achterhalen via connectors (ook wel e-mail stroom informatie genoemd).
ms.openlocfilehash: e8427f3e0341ccb381121b6cdc83d20727713d4c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307915"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="7ab8c-103">E-mailstroomanalyse in EOP</span><span class="sxs-lookup"><span data-stu-id="7ab8c-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="7ab8c-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken gebruikt u meestal een verbindingslijn voor het routeren van e-mailberichten van EOP naar uw on-premises e-mail omgeving.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="7ab8c-105">U kunt ook een connector gebruiken om berichten van Microsoft 365 door te sturen naar een partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="7ab8c-106">Wanneer Microsoft 365 deze berichten niet via de connector bezorgt, worden deze in de wachtrij geplaatst in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="7ab8c-107">Microsoft 365 blijft gedurende 24 uur opnieuw proberen voor elk bericht.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="7ab8c-108">Na 24 uur verloopt het bericht in de wachtrij en wordt het verzonden naar de oorspronkelijke afzender in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of een bericht met een stuiter bericht).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="7ab8c-109">In Microsoft 365 wordt een fout gegenereerd wanneer een bericht niet kan worden afgeleverd via een verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="7ab8c-110">In dit onderwerp worden de meest voorkomende fouten en hun oplossingen beschreven.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="7ab8c-111">Gezamenlijk, Queuing-en meldings fouten voor niet-bezorg bare berichten die via connectors worden verzonden, worden ook wel _e-mail stroom informatie_genoemd.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="7ab8c-112">Foutcode: 450 4.4.312 DNS-query mislukt</span><span class="sxs-lookup"><span data-stu-id="7ab8c-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="7ab8c-113">Deze fout betekent meestal dat Microsoft 365 probeert verbinding te maken met de Smart host die is opgegeven in de connector, maar de DNS-query voor het zoeken van de IP-adressen van de Smart host is mislukt.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="7ab8c-114">De mogelijke oorzaken van deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="7ab8c-115">Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein beheert).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="7ab8c-116">Uw domein is onlangs verlopen, zodat de MX-record niet kan worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="7ab8c-117">De MX-record van uw domein is onlangs gewijzigd en de DNS-servers hebben nog steeds eerder DNS-gegevens in de cache voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="7ab8c-118">Hoe los ik foutcode 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="7ab8c-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="7ab8c-119">Werk samen met uw DNS-hostingservice om het probleem met uw domein op te sporen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="7ab8c-120">Neem contact op met uw partner om dit probleem op te lossen als de fout zich bevindt in uw partnerorganisatie (bijvoorbeeld een derde Cloud serviceprovider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="7ab8c-121">Foutcode: 4.4.315-verbinding voor 450 is verlopen</span><span class="sxs-lookup"><span data-stu-id="7ab8c-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="7ab8c-122">Dit betekent meestal dat Microsoft 365 geen verbinding kan maken met de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="7ab8c-123">Het probleem wordt uitgelegd met de foutgegevens.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-123">The error details will explain the problem.</span></span> <span data-ttu-id="7ab8c-124">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-124">For example:</span></span>

- <span data-ttu-id="7ab8c-125">Uw on-premises e-mailserver is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="7ab8c-126">Er is een fout opgetreden in de instellingen van de Smart host van de connector, dus Microsoft 365 probeert verbinding te maken met het verkeerde IP-adres.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="7ab8c-127">Hoe los ik foutcode 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="7ab8c-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="7ab8c-128">Kijk welke scenario op u van toepassing is en breng de benodigde wijzigingen aan.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="7ab8c-129">Als de e-mail stroom bijvoorbeeld goed werkte en u de instellingen voor de connector niet hebt gewijzigd, moet u uw on-premises e-mail omgeving controleren om te zien of de server offline is, of dat er wijzigingen zijn aangebracht in de netwerkinfrastructuur, zodat u nu verschillende IP-adressen hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="7ab8c-130">Neem contact op met uw partner om dit probleem op te lossen als de fout zich bevindt in uw partnerorganisatie (bijvoorbeeld een derde Cloud serviceprovider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="7ab8c-131">Foutcode: 450 4.4.316 verbinding geweigerd</span><span class="sxs-lookup"><span data-stu-id="7ab8c-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="7ab8c-132">Dit betekent meestal dat er in Microsoft 365 een verbindingsfout is opgetreden bij het proberen verbinding te maken met de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="7ab8c-133">Deze fout is waarschijnlijk veroorzaakt doordat de firewall verbindingen van Microsoft 365 IP-adressen blokkeert.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="7ab8c-134">Of de fout kan door ontwerp zijn als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Microsoft 365 en uw on-premises e-mail omgeving afsluit.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="7ab8c-135">Hoe los ik foutcode 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="7ab8c-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="7ab8c-136">Als u postvakken hebt in uw on-premises omgeving, moet u de firewallinstellingen wijzigen om verbindingen van Microsoft 365 IP-adressen op TCP-poort 25 toe te staan voor uw on-premises e-mailservers.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="7ab8c-137">Zie [url's en IP-adresbereiken voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)voor een lijst met de microsoft 365 IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="7ab8c-138">Als u geen berichten meer wilt ontvangen in uw on-premises omgeving, klikt u op **nu herstellen** in de melding zodat microsoft 365 de berichten met ongeldige geadresseerden direct kan afwijzen.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="7ab8c-139">Hierdoor wordt het risico voor het overschrijden van het quotum van de organisatie voor ongeldige geadresseerden verminderd, wat van invloed kan zijn op de bezorging van normaal berichten.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="7ab8c-140">U kunt ook de volgende instructies gebruiken om het probleem handmatig op te lossen:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="7ab8c-141">In het [Exchange-Beheercentrum](https://docs.microsoft.com/Exchange/exchange-admin-center), schakelt u de connector voor E-mail van microsoft 365 in de on-premises e-mail omgeving uit of verwijdert u deze.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="7ab8c-142">Ga in het Exchange-Beheercentrum naar **e-mail stroom** \> **verbindingslijnen**.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="7ab8c-143">Selecteer de connector met de **From** waarde van **Office 365** en de waarde **voor** de **e-mailserver van uw organisatie** en voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="7ab8c-144">Als u de verbindingslijn wilt verwijderen **, klikt u** op het ![ pictogram verwijderen](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="7ab8c-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="7ab8c-145">Schakel de verbindingslijn uit **Edit** door te klikken op het ![ pictogram bewerken bewerken ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) en **het**selectievakje in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="7ab8c-146">Wijzig het geaccepteerde domein in Microsoft 365 dat is gekoppeld aan uw on-premises e-mail omgeving van **interne** doorgifte naar **gezaghebbend**.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="7ab8c-147">Zie [geaccepteerde domeinen beheren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="7ab8c-148">**Opmerking**: deze wijzigingen treden doorgaans tussen 30 minuten en één uur in werking.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="7ab8c-149">Na één uur controleert u of u de fout niet meer ontvangt.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="7ab8c-150">Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="7ab8c-151">Foutcode: 450 4.4.317 kan geen verbinding maken met de externe server</span><span class="sxs-lookup"><span data-stu-id="7ab8c-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="7ab8c-152">Dit betekent meestal dat Microsoft 365 is verbonden met de doel-e-mailserver, maar de server heeft gereageerd met een onmiddellijke fout of niet aan de verbindings vereisten voldoet.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="7ab8c-153">Het probleem wordt uitgelegd met de foutgegevens.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-153">The error details will explain the problem.</span></span> <span data-ttu-id="7ab8c-154">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-154">For example:</span></span>

- <span data-ttu-id="7ab8c-155">De doel-e-mailserver heeft gereageerd op de fout ' service niet beschikbaar ', wat aangeeft dat de server geen communicatie kan bijhouden met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="7ab8c-156">De connector is geconfigureerd om TLS te vereisen, maar de doel-e-mailserver biedt geen ondersteuning voor TLS.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="7ab8c-157">Hoe los ik foutcode 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="7ab8c-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="7ab8c-158">Controleer de TLS-instellingen en certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="7ab8c-159">Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="7ab8c-160">Foutcode: 450-verbinding voor 4.4.318 is plotseling gesloten</span><span class="sxs-lookup"><span data-stu-id="7ab8c-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="7ab8c-161">Deze fout betekent meestal dat Microsoft 365 geen problemen ondervindt met de on-premises e-mail omgeving, zodat de verbinding is verbroken.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="7ab8c-162">De mogelijke oorzaken van deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="7ab8c-163">De firewall gebruikt regels voor SMTP-pakket onderzoek en deze regels werken niet goed.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="7ab8c-164">Uw on-premises e-mailserver werkt niet goed (bijvoorbeeld de service loopt vast, loopt vast of onvoldoende systeembronnen), waardoor de server een time-out heeft en sluit de verbinding met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="7ab8c-165">Er zijn netwerkproblemen tussen uw on-premises omgeving en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="7ab8c-166">Hoe los ik foutcode 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="7ab8c-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="7ab8c-167">Kijk welke scenario op u van toepassing is en breng de benodigde wijzigingen aan.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="7ab8c-168">Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Microsoft 365, neemt u contact op met uw netwerkteam om dit probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="7ab8c-169">Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="7ab8c-170">Foutcode: certificaatvalidatie 450 4.7.320 is mislukt</span><span class="sxs-lookup"><span data-stu-id="7ab8c-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="7ab8c-171">Dit betekent meestal dat Microsoft 365 een fout heeft ontdekt bij het valideren van het certificaat van de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="7ab8c-172">In de foutdetails wordt de fout uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-172">The error details will explain the error.</span></span> <span data-ttu-id="7ab8c-173">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="7ab8c-173">For example:</span></span>

- <span data-ttu-id="7ab8c-174">Certificaat verlopen</span><span class="sxs-lookup"><span data-stu-id="7ab8c-174">Certificate expired</span></span>

- <span data-ttu-id="7ab8c-175">Certificaatonderwerp komt niet overeen</span><span class="sxs-lookup"><span data-stu-id="7ab8c-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="7ab8c-176">Certificaat is niet langer geldig</span><span class="sxs-lookup"><span data-stu-id="7ab8c-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="7ab8c-177">Hoe los ik foutcode 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="7ab8c-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="7ab8c-178">Los het certificaat of de instellingen op de connector op, zodat berichten in de wachtrij in Microsoft 365 kunnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="7ab8c-179">Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="7ab8c-180">Andere foutcodes</span><span class="sxs-lookup"><span data-stu-id="7ab8c-180">Other error codes</span></span>

<span data-ttu-id="7ab8c-181">Microsoft 365 biedt problemen met het bezorgen van berichten aan uw on-premises e-mailserver of partner.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="7ab8c-182">Gebruik de **doelserver** gegevens in de fout om het probleem in uw omgeving te bekijken, of wijzig de connector als er een configuratiefout is opgetreden.</span><span class="sxs-lookup"><span data-stu-id="7ab8c-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="7ab8c-183">Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).</span><span class="sxs-lookup"><span data-stu-id="7ab8c-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
