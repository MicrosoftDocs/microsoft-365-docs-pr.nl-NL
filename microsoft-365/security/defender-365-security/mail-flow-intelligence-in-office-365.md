---
title: E-mailstroominformatie
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Beheerders kunnen meer informatie krijgen over de foutcodes die zijn gekoppeld aan berichtbezorging via verbindingslijnen (ook wel bekend als e-mailstroominformatie).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057925"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="6bcda-103">E-mailstroomanalyse in EOP</span><span class="sxs-lookup"><span data-stu-id="6bcda-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6bcda-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="6bcda-104">**Applies to**</span></span>
- [<span data-ttu-id="6bcda-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6bcda-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6bcda-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6bcda-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6bcda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bcda-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6bcda-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken gebruikt u meestal een verbindingslijn om e-mailberichten van EOP naar uw on-premises e-mailomgeving te sturen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="6bcda-109">U kunt ook een verbindingslijn gebruiken om berichten van Microsoft 365 door te sturen naar een partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="6bcda-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="6bcda-110">Wanneer Microsoft 365 deze berichten niet kan bezorgen via de connector, worden ze in de wachtrij geplaatst in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcda-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="6bcda-111">Microsoft 365 blijft de bezorging voor elk bericht 24 uur lang opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="6bcda-112">Na 24 uur verloopt het bericht in de wachtrij en wordt het bericht geretourneerd naar de oorspronkelijke afzender in een rapport zonder bezorging (ook wel een NDR- of bouncebericht genoemd).</span><span class="sxs-lookup"><span data-stu-id="6bcda-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="6bcda-113">Microsoft 365 genereert een fout wanneer een bericht niet kan worden bezorgd via een verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="6bcda-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="6bcda-114">De meest voorkomende fouten en hun oplossingen worden in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="6bcda-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="6bcda-115">In de rij- en meldingsfouten voor niet-besleedbare berichten die via verbindingslijnen worden verzonden, wordt _e-mailstroomintelligentie genoemd._</span><span class="sxs-lookup"><span data-stu-id="6bcda-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="6bcda-116">Foutcode: DNS-query 450 4.4.312 is mislukt</span><span class="sxs-lookup"><span data-stu-id="6bcda-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="6bcda-117">Deze fout betekent meestal dat Microsoft 365 heeft geprobeerd verbinding te maken met de slimme host die is opgegeven in de connector, maar de DNS-query om de IP-adressen van de slimme host te zoeken is mislukt.</span><span class="sxs-lookup"><span data-stu-id="6bcda-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="6bcda-118">De mogelijke oorzaken voor deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="6bcda-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="6bcda-119">Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein onderhoudt).</span><span class="sxs-lookup"><span data-stu-id="6bcda-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="6bcda-120">Uw domein is onlangs verlopen, dus de MX-record kan niet worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="6bcda-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="6bcda-121">De MX-record van uw domein is onlangs gewijzigd en de DNS-servers hebben nog steeds DNS-gegevens in de cache voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="6bcda-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="6bcda-122">Hoe kan ik foutcode 450 4.4.312 oplossen?</span><span class="sxs-lookup"><span data-stu-id="6bcda-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="6bcda-123">Werk samen met uw DNS-hostingservice om het probleem met uw domein te identificeren en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="6bcda-124">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), neem dan contact op met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="6bcda-125">Foutcode: time-out van 450 4.4.315 Connection</span><span class="sxs-lookup"><span data-stu-id="6bcda-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="6bcda-126">Dit betekent meestal dat Microsoft 365 geen verbinding kan maken met de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="6bcda-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="6bcda-127">In de foutdetails wordt het probleem uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="6bcda-127">The error details will explain the problem.</span></span> <span data-ttu-id="6bcda-128">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6bcda-128">For example:</span></span>

- <span data-ttu-id="6bcda-129">Uw on-premises e-mailserver is niet aanwezig.</span><span class="sxs-lookup"><span data-stu-id="6bcda-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="6bcda-130">Er is een fout opgetreden in de instellingen voor slimme host van de connector, dus Microsoft 365 probeert verbinding te maken met het verkeerde IP-adres.</span><span class="sxs-lookup"><span data-stu-id="6bcda-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="6bcda-131">Hoe kan ik foutcode 450 4.4.315 oplossen?</span><span class="sxs-lookup"><span data-stu-id="6bcda-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="6bcda-132">Zoek uit welk scenario op u van toepassing is en maak de benodigde correcties.</span><span class="sxs-lookup"><span data-stu-id="6bcda-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="6bcda-133">Als de e-mailstroom bijvoorbeeld correct werkt en u de connectorinstellingen niet hebt gewijzigd, moet u uw on-premises e-mailomgeving controleren om te zien of de server niet actief is of als er wijzigingen zijn aangebracht in uw netwerkinfrastructuur (u hebt bijvoorbeeld internetproviders gewijzigd, zodat u nu verschillende IP-adressen hebt).</span><span class="sxs-lookup"><span data-stu-id="6bcda-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="6bcda-134">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), neem dan contact op met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="6bcda-135">Foutcode: 450 4.4.316 Verbinding geweigerd</span><span class="sxs-lookup"><span data-stu-id="6bcda-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="6bcda-136">Deze fout betekent meestal dat Microsoft 365 een verbindingsfout heeft ondervonden bij het maken van verbinding met de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="6bcda-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="6bcda-137">Een waarschijnlijke oorzaak voor deze fout is dat uw firewall verbindingen blokkeert via IP-adressen van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcda-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="6bcda-138">Of deze fout kan zijn ontworpen als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Microsoft 365 en uw on-premises e-mailomgeving hebt afgesloten.</span><span class="sxs-lookup"><span data-stu-id="6bcda-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="6bcda-139">Hoe kan ik foutcode 450 4.4.316 oplossen?</span><span class="sxs-lookup"><span data-stu-id="6bcda-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="6bcda-140">Als u postvakken in uw on-premises omgeving hebt, moet u de firewallinstellingen wijzigen om verbindingen van Microsoft 365 IP-adressen op TCP-poort 25 met uw on-premises e-mailservers toe te staan.</span><span class="sxs-lookup"><span data-stu-id="6bcda-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="6bcda-141">Zie URL's en IP-adresbereiken van Microsoft 365 voor een lijst met de IP-adressen van [Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="6bcda-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="6bcda-142">Als er geen berichten meer moeten worden bezorgd in uw on-premises omgeving, klikt u **op** Nu oplossen in de waarschuwing, zodat Microsoft 365 de berichten met ongeldige geadresseerden onmiddellijk kan weigeren.</span><span class="sxs-lookup"><span data-stu-id="6bcda-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="6bcda-143">Hierdoor wordt het risico verkleind dat het quotum van uw organisatie voor ongeldige geadresseerden wordt overschreden, wat van invloed kan zijn op de normale berichtbezorging.</span><span class="sxs-lookup"><span data-stu-id="6bcda-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="6bcda-144">U kunt ook de volgende instructies gebruiken om het probleem handmatig op te lossen:</span><span class="sxs-lookup"><span data-stu-id="6bcda-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="6bcda-145">Schakel in [het Exchange-beheercentrum (EAC)](/Exchange/exchange-admin-center)de connector uit of verwijder deze die e-mail van Microsoft 365 naar uw on-premises e-mailomgeving bezorgt:</span><span class="sxs-lookup"><span data-stu-id="6bcda-145">In the [Exchange admin center (EAC)](/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="6bcda-146">Ga in het EAC naar **E-mailstroomconnectoren.** \> </span><span class="sxs-lookup"><span data-stu-id="6bcda-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="6bcda-147">Selecteer de verbindingslijn **met de waarde Van** Office **365** en **de** e-mailserver van uw organisatie aan waarde en ga op een van de volgende stappen te werk: </span><span class="sxs-lookup"><span data-stu-id="6bcda-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="6bcda-148">De verbindingslijn verwijderen door op **pictogram Verwijderen** ![ te klikken](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="6bcda-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="6bcda-149">Schakel de verbindingslijn uit door op **pictogram Bewerken** ![ bewerken te klikken en Schakel Deze ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **in.**</span><span class="sxs-lookup"><span data-stu-id="6bcda-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="6bcda-150">Wijzig het geaccepteerde domein in Microsoft 365 dat is gekoppeld aan uw on-premises e-mailomgeving van **Interne** doorverteller in **Gezaghebbend.**</span><span class="sxs-lookup"><span data-stu-id="6bcda-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="6bcda-151">Zie Geaccepteerde domeinen beheren in Exchange Online voor [instructies.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="6bcda-151">For instructions, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="6bcda-152">**Opmerking:** Meestal duurt het 30 minuten tot een uur voordat deze wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="6bcda-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="6bcda-153">Controleer na één uur of u de fout niet meer ontvangt.</span><span class="sxs-lookup"><span data-stu-id="6bcda-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="6bcda-154">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="6bcda-155">Foutcode: 450 4.4.317 Kan geen verbinding maken met externe server</span><span class="sxs-lookup"><span data-stu-id="6bcda-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="6bcda-156">Deze fout betekent meestal dat Microsoft 365 is verbonden met de doel-e-mailserver, maar dat de server met een directe fout heeft gereageerd of niet voldoet aan de verbindingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="6bcda-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="6bcda-157">In de foutdetails wordt het probleem uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="6bcda-157">The error details will explain the problem.</span></span> <span data-ttu-id="6bcda-158">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6bcda-158">For example:</span></span>

- <span data-ttu-id="6bcda-159">De doel-e-mailserver heeft gereageerd met een foutmelding 'Service niet beschikbaar', wat aangeeft dat de server de communicatie met Microsoft 365 niet kan onderhouden.</span><span class="sxs-lookup"><span data-stu-id="6bcda-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="6bcda-160">De connector is geconfigureerd om TLS te vereisen, maar de doel-e-mailserver biedt geen ondersteuning voor TLS.</span><span class="sxs-lookup"><span data-stu-id="6bcda-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="6bcda-161">Hoe kan ik foutcode 450 4.4.317 oplossen?</span><span class="sxs-lookup"><span data-stu-id="6bcda-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="6bcda-162">Controleer de TLS-instellingen en -certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.</span><span class="sxs-lookup"><span data-stu-id="6bcda-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="6bcda-163">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="6bcda-164">Foutcode: 450 4.4.318 Verbinding is plotseling gesloten</span><span class="sxs-lookup"><span data-stu-id="6bcda-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="6bcda-165">Deze fout betekent meestal dat Microsoft 365 problemen heeft met de communicatie met uw on-premises e-mailomgeving, zodat de verbinding is gestopt.</span><span class="sxs-lookup"><span data-stu-id="6bcda-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="6bcda-166">De mogelijke oorzaken voor deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="6bcda-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="6bcda-167">Uw firewall gebruikt SMTP-regels voor pakketonderzoek en deze regels werken niet correct.</span><span class="sxs-lookup"><span data-stu-id="6bcda-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="6bcda-168">Uw on-premises e-mailserver werkt niet goed (bijvoorbeeld service loopt vast, loopt vast of er zijn systeembronnen laag), waardoor de server een time-out heeft en de verbinding met Microsoft 365 sluit.</span><span class="sxs-lookup"><span data-stu-id="6bcda-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="6bcda-169">Er zijn netwerkproblemen tussen uw on-premises omgeving en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bcda-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="6bcda-170">Hoe kan ik foutcode 450 4.4.318 oplossen?</span><span class="sxs-lookup"><span data-stu-id="6bcda-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="6bcda-171">Zoek uit welk scenario op u van toepassing is en maak de benodigde correcties.</span><span class="sxs-lookup"><span data-stu-id="6bcda-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="6bcda-172">Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Microsoft 365, neem dan contact op met uw netwerkteam om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="6bcda-173">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="6bcda-174">Foutcode: 450 4.7.320 Certificaatvalidatie is mislukt</span><span class="sxs-lookup"><span data-stu-id="6bcda-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="6bcda-175">Deze fout betekent meestal dat microsoft 365 een fout heeft ondervonden tijdens het valideren van het certificaat van de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="6bcda-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="6bcda-176">De foutdetails verklaren de fout.</span><span class="sxs-lookup"><span data-stu-id="6bcda-176">The error details will explain the error.</span></span> <span data-ttu-id="6bcda-177">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6bcda-177">For example:</span></span>

- <span data-ttu-id="6bcda-178">Certificaat is verlopen</span><span class="sxs-lookup"><span data-stu-id="6bcda-178">Certificate expired</span></span>

- <span data-ttu-id="6bcda-179">Certificaatonderwerp komt niet overeen</span><span class="sxs-lookup"><span data-stu-id="6bcda-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="6bcda-180">Certificaat is niet meer geldig</span><span class="sxs-lookup"><span data-stu-id="6bcda-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="6bcda-181">Hoe kan ik foutcode 450 4.7.320 oplossen?</span><span class="sxs-lookup"><span data-stu-id="6bcda-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="6bcda-182">Herstel het certificaat of de instellingen op de connector, zodat berichten in de wachtrij in Microsoft 365 kunnen worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="6bcda-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="6bcda-183">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="6bcda-184">Andere foutcodes</span><span class="sxs-lookup"><span data-stu-id="6bcda-184">Other error codes</span></span>

<span data-ttu-id="6bcda-185">Microsoft 365 heeft problemen met het verzenden van berichten naar uw on-premises e-mailserver of partner-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="6bcda-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="6bcda-186">Gebruik de **doelservergegevens** in de fout om het probleem in uw omgeving te onderzoeken of wijzig de verbindingslijn als er een configuratiefout is.</span><span class="sxs-lookup"><span data-stu-id="6bcda-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="6bcda-187">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="6bcda-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>