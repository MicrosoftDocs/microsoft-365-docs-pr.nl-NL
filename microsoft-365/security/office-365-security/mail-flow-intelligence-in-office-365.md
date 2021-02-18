---
title: Informatie over e-mailstroom
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
description: Beheerders kunnen meer informatie krijgen over de foutcodes die zijn gekoppeld aan berichtbezorging via connectors (ook wel bekend als mail flow intelligence).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32a98459ce3d3494e576b10d5c5b097393ee2335
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289661"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="d98cc-103">E-mailstroomanalyse in EOP</span><span class="sxs-lookup"><span data-stu-id="d98cc-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d98cc-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d98cc-104">**Applies to**</span></span>
- [<span data-ttu-id="d98cc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d98cc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d98cc-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d98cc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d98cc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d98cc-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d98cc-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken gebruikt u meestal een connector om e-mailberichten vanuit EOP door te sturen naar uw on-premises e-mailomgeving.</span><span class="sxs-lookup"><span data-stu-id="d98cc-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="d98cc-109">U kunt ook een connector gebruiken om berichten van Microsoft 365 door te sturen naar een partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="d98cc-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="d98cc-110">Als Microsoft 365 deze berichten niet via de connector kan bezorgen, worden deze in de wachtrij geplaatst in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d98cc-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="d98cc-111">Microsoft 365 blijft de bezorging voor elk bericht 24 uur lang opnieuw proberen uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="d98cc-112">Na 24 uur verloopt het bericht in de wachtrij en wordt het bericht geretourneerd aan de oorspronkelijke afzender in een rapport over niet-bezorging (ook wel een NDR- of niet-bezorgdbericht genoemd).</span><span class="sxs-lookup"><span data-stu-id="d98cc-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="d98cc-113">Microsoft 365 genereert een fout wanneer een bericht niet kan worden bezorgd via een connector.</span><span class="sxs-lookup"><span data-stu-id="d98cc-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="d98cc-114">De meest voorkomende fouten en hun oplossingen worden in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="d98cc-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="d98cc-115">Wachtrij- en meldingsfouten voor niet-af te sluiten berichten die via connectors worden verzonden, worden ook wel informatie over _de e-mailstroom genoemd._</span><span class="sxs-lookup"><span data-stu-id="d98cc-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="d98cc-116">Foutcode: 450 4.4.312 DNS-query is mislukt</span><span class="sxs-lookup"><span data-stu-id="d98cc-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="d98cc-117">Deze fout betekent meestal dat Microsoft 365 heeft geprobeerd verbinding te maken met de smart host die is opgegeven in de connector, maar dat de DNS-query om de IP-adressen van de smart host te vinden is mislukt.</span><span class="sxs-lookup"><span data-stu-id="d98cc-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="d98cc-118">De mogelijke oorzaken voor deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="d98cc-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="d98cc-119">Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein onderhoudt).</span><span class="sxs-lookup"><span data-stu-id="d98cc-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="d98cc-120">Uw domein is onlangs verlopen, dus de MX-record kan niet worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="d98cc-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="d98cc-121">De MX-record van uw domein is onlangs gewijzigd en de DNS-servers hebben nog steeds DNS-gegevens in de cache opgeslagen voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="d98cc-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="d98cc-122">Hoe kan ik foutcode 450 4.4.312 oplossen?</span><span class="sxs-lookup"><span data-stu-id="d98cc-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="d98cc-123">Werk samen met uw DNS-hostingservice om het probleem met uw domein te identificeren en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="d98cc-124">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neem dan contact op met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="d98cc-125">Foutcode: 450 4.4.315 Connection time-out</span><span class="sxs-lookup"><span data-stu-id="d98cc-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="d98cc-126">Dit betekent meestal dat Microsoft 365 geen verbinding kan maken met de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="d98cc-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="d98cc-127">Aan de hand van de details van de fout wordt het probleem uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="d98cc-127">The error details will explain the problem.</span></span> <span data-ttu-id="d98cc-128">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d98cc-128">For example:</span></span>

- <span data-ttu-id="d98cc-129">Uw on-premises e-mailserver is niet meer aanwezig.</span><span class="sxs-lookup"><span data-stu-id="d98cc-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="d98cc-130">Er is een fout opgetreden in de smart host-instellingen van de connector, dus Microsoft 365 probeert verbinding te maken met het verkeerde IP-adres.</span><span class="sxs-lookup"><span data-stu-id="d98cc-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="d98cc-131">Hoe kan ik foutcode 450 4.4.315 oplossen?</span><span class="sxs-lookup"><span data-stu-id="d98cc-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="d98cc-132">Zoek uit welk scenario op u van toepassing is en brengt de benodigde correcties aan.</span><span class="sxs-lookup"><span data-stu-id="d98cc-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="d98cc-133">Als de e-mailstroom bijvoorbeeld goed werkt en u de instellingen van de connector niet hebt gewijzigd, moet u de on-premises e-mailomgeving controleren om te zien of de server niet is ingesteld of dat er wijzigingen zijn aangebracht in uw netwerkinfrastructuur (u hebt bijvoorbeeld internetproviders gewijzigd, zodat u nu verschillende IP-adressen hebt).</span><span class="sxs-lookup"><span data-stu-id="d98cc-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="d98cc-134">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neem dan contact op met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="d98cc-135">Foutcode: 450 4.4.316 Verbinding geweigerd</span><span class="sxs-lookup"><span data-stu-id="d98cc-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="d98cc-136">Deze fout betekent meestal dat er een verbindingsfout is opgetreden in Microsoft 365 toen werd geprobeerd verbinding te maken met de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="d98cc-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="d98cc-137">Een mogelijke oorzaak voor deze fout is dat uw firewall verbindingen vanaf IP-adressen van Microsoft 365 blokkeert.</span><span class="sxs-lookup"><span data-stu-id="d98cc-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="d98cc-138">Of deze fout kan komen als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Microsoft 365 en de on-premises e-mailomgeving hebt afgesloten.</span><span class="sxs-lookup"><span data-stu-id="d98cc-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="d98cc-139">Hoe kan ik foutcode 450 4.4.316 oplossen?</span><span class="sxs-lookup"><span data-stu-id="d98cc-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="d98cc-140">Als uw on-premises omgeving postvakken heeft, moet u uw firewallinstellingen wijzigen om verbindingen van IP-adressen van Microsoft 365 op TCP-poort 25 met uw on-premises e-mailservers toe te staan.</span><span class="sxs-lookup"><span data-stu-id="d98cc-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="d98cc-141">Zie DE URL's en IP-adresbereiken van Microsoft 365 voor een lijst met De IP-adressen [van Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="d98cc-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="d98cc-142">Als er geen berichten meer moeten worden bezorgd in uw on-premises omgeving, klikt u **in** de waarschuwing op Nu herstellen, zodat Microsoft 365 de berichten met ongeldige geadresseerden direct kan weigeren.</span><span class="sxs-lookup"><span data-stu-id="d98cc-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="d98cc-143">Hierdoor wordt het risico verkleind dat het quotum van uw organisatie voor ongeldige geadresseerden wordt overschreden, wat gevolgen kan hebben voor de normale bezorging van berichten.</span><span class="sxs-lookup"><span data-stu-id="d98cc-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="d98cc-144">U kunt ook de volgende instructies gebruiken om het probleem handmatig op te lossen:</span><span class="sxs-lookup"><span data-stu-id="d98cc-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="d98cc-145">Schakel in [het Exchange-beheercentrum (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)de connector uit die e-mail van Microsoft 365 naar uw on-premises e-mailomgeving bezorgt of verwijder deze:</span><span class="sxs-lookup"><span data-stu-id="d98cc-145">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="d98cc-146">Ga in het EAC naar **Connectors voor de e-mailstroom.** \> </span><span class="sxs-lookup"><span data-stu-id="d98cc-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="d98cc-147">Selecteer de connector met de **Van-waarde** Office  **365** en de waarde **Aan** van de e-mailserver van uw organisatie en ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="d98cc-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="d98cc-148">De verbindingslijn verwijderen door op het **pictogram Verwijderen** ![ te klikken](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="d98cc-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="d98cc-149">Schakel de connector uit door op het **pictogram** Bewerken ![ te klikken en De connector in te ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **schakelen.**</span><span class="sxs-lookup"><span data-stu-id="d98cc-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="d98cc-150">Wijzig het geaccepteerde domein in Microsoft 365 dat is  gekoppeld aan uw on-premises e-mailomgeving van Interne door te sturen in **Gezaghebbend.**</span><span class="sxs-lookup"><span data-stu-id="d98cc-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="d98cc-151">Zie Geaccepteerde [domeinen beheren in Exchange Online voor instructies.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="d98cc-151">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="d98cc-152">**Opmerking:** Het duurt meestal 30 minuten tot een uur voordat deze wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="d98cc-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="d98cc-153">Controleer na een uur of de fout niet meer wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d98cc-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="d98cc-154">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="d98cc-155">Foutcode: 450 4.4.317 Kan geen verbinding maken met een externe server</span><span class="sxs-lookup"><span data-stu-id="d98cc-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="d98cc-156">Deze fout betekent meestal dat Microsoft 365 is verbonden met de doel-e-mailserver, maar dat de server direct heeft gereageerd of niet voldoet aan de verbindingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="d98cc-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="d98cc-157">Aan de hand van de details van de fout wordt het probleem uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="d98cc-157">The error details will explain the problem.</span></span> <span data-ttu-id="d98cc-158">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d98cc-158">For example:</span></span>

- <span data-ttu-id="d98cc-159">De doel-e-mailserver heeft gereageerd met de fout 'Service niet beschikbaar', wat aangeeft dat de server de communicatie met Microsoft 365 niet kan onderhouden.</span><span class="sxs-lookup"><span data-stu-id="d98cc-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="d98cc-160">De connector is geconfigureerd voor het vereisen van TLS, maar de doel-e-mailserver biedt geen ondersteuning voor TLS.</span><span class="sxs-lookup"><span data-stu-id="d98cc-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="d98cc-161">Hoe kan ik foutcode 450 4.4.317 oplossen?</span><span class="sxs-lookup"><span data-stu-id="d98cc-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="d98cc-162">Controleer de TLS-instellingen en -certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.</span><span class="sxs-lookup"><span data-stu-id="d98cc-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="d98cc-163">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="d98cc-164">Foutcode: 450 4.4.318 Connection was closedly</span><span class="sxs-lookup"><span data-stu-id="d98cc-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="d98cc-165">Deze fout betekent meestal dat Microsoft 365 problemen heeft met de communicatie met uw on-premises e-mailomgeving, zodat de verbinding is weggevallen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="d98cc-166">De mogelijke oorzaken voor deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="d98cc-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="d98cc-167">Uw firewall gebruikt SMTP-pakkettestregels en die regels werken niet goed.</span><span class="sxs-lookup"><span data-stu-id="d98cc-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="d98cc-168">Uw on-premises e-mailserver werkt niet goed (bijvoorbeeld service loopt vast, crasht of lage systeembronnen), waardoor de server een time-out veroorzaakt en de verbinding met Microsoft 365 wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="d98cc-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="d98cc-169">Er zijn netwerkproblemen tussen uw on-premises omgeving en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d98cc-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="d98cc-170">Hoe kan ik foutcode 450 4.4.318 oplossen?</span><span class="sxs-lookup"><span data-stu-id="d98cc-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="d98cc-171">Zoek uit welk scenario op u van toepassing is en brengt de benodigde correcties aan.</span><span class="sxs-lookup"><span data-stu-id="d98cc-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="d98cc-172">Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Microsoft 365, neem dan contact op met uw netwerkteam om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="d98cc-173">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="d98cc-174">Foutcode: 450 4.7.320 Certificaatvalidatie is mislukt</span><span class="sxs-lookup"><span data-stu-id="d98cc-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="d98cc-175">Deze fout betekent meestal dat er in Microsoft 365 een fout is opgetreden tijdens het valideren van het certificaat van de doel-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="d98cc-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="d98cc-176">In de details van de fout wordt de fout uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="d98cc-176">The error details will explain the error.</span></span> <span data-ttu-id="d98cc-177">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d98cc-177">For example:</span></span>

- <span data-ttu-id="d98cc-178">Certificaat verlopen</span><span class="sxs-lookup"><span data-stu-id="d98cc-178">Certificate expired</span></span>

- <span data-ttu-id="d98cc-179">Certificaatonderwerpen komen niet overeen</span><span class="sxs-lookup"><span data-stu-id="d98cc-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="d98cc-180">Certificaat is niet meer geldig</span><span class="sxs-lookup"><span data-stu-id="d98cc-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="d98cc-181">Hoe kan ik foutcode 450 4.7.320 oplossen?</span><span class="sxs-lookup"><span data-stu-id="d98cc-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="d98cc-182">Herstel het certificaat of de instellingen van de connector, zodat berichten in de wachtrij in Microsoft 365 kunnen worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="d98cc-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="d98cc-183">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="d98cc-184">Andere foutcodes</span><span class="sxs-lookup"><span data-stu-id="d98cc-184">Other error codes</span></span>

<span data-ttu-id="d98cc-185">Microsoft 365 heeft problemen met het bezorgen van berichten op de on-premises server of de e-mailserver van uw partner.</span><span class="sxs-lookup"><span data-stu-id="d98cc-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="d98cc-186">Gebruik de **gegevens van de** doelserver in de fout om het probleem in uw omgeving te onderzoeken of wijzig de connector als er een configuratiefout is.</span><span class="sxs-lookup"><span data-stu-id="d98cc-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="d98cc-187">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="d98cc-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
