---
title: Informatie over e-mailstroom in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Beheerders kunnen meer te weten komen over de foutcodes die zijn gekoppeld aan het bezorgen van berichten met behulp van connectors in Office 365 (ook wel mailflow intelligence genoemd).
ms.openlocfilehash: 849493cefecb3344eaf7b6db73be3930138c236c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806298"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="0590e-103">Informatie over e-mailstroom in Office 365</span><span class="sxs-lookup"><span data-stu-id="0590e-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="0590e-104">Normaal gesproken gebruikt u een connector om e-mailberichten van uw Office 365-organisatie door te sturen naar uw on-premises e-mailomgeving.</span><span class="sxs-lookup"><span data-stu-id="0590e-104">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment.</span></span> <span data-ttu-id="0590e-105">U ook een connector gebruiken om berichten van Office 365 naar een partnerorganisatie te routeren.</span><span class="sxs-lookup"><span data-stu-id="0590e-105">You might also use a connector to route messages from Office 365 to a partner organization.</span></span> <span data-ttu-id="0590e-106">Wanneer Office 365 deze berichten niet via de connector kan verzenden, staan ze in de wachtrij in Office 365.</span><span class="sxs-lookup"><span data-stu-id="0590e-106">When Office 365 can't deliver these messages via the connector, they're queued in Office 365.</span></span> <span data-ttu-id="0590e-107">Office 365 blijft de bezorging voor elk bericht 24 uur opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="0590e-107">Office 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="0590e-108">Na 24 uur verloopt het bericht in de wachtrij en wordt het bericht teruggestuurd naar de oorspronkelijke afzender in een rapport zonder levering (ook wel een NDR- of bouncebericht genoemd).</span><span class="sxs-lookup"><span data-stu-id="0590e-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="0590e-109">Office 365 genereert een fout wanneer een bericht niet kan worden geleverd met behulp van een connector.</span><span class="sxs-lookup"><span data-stu-id="0590e-109">Office 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="0590e-110">De meest voorkomende fouten en hun oplossingen worden beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="0590e-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="0590e-111">Gezamenlijk staan wachtrij- en meldingsfouten voor niet-leverbare berichten die via connectors worden verzonden, bekend als _mailflow intelligence._</span><span class="sxs-lookup"><span data-stu-id="0590e-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="0590e-112">Foutcode: DNS-query 450 4.4.312 is mislukt</span><span class="sxs-lookup"><span data-stu-id="0590e-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="0590e-113">Deze fout betekent doorgaans dat Office 365 heeft geprobeerd verbinding te maken met de slimme host die is opgegeven in de connector, maar de DNS-query om de IP-adressen van de slimme host te vinden, is mislukt.</span><span class="sxs-lookup"><span data-stu-id="0590e-113">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="0590e-114">De mogelijke oorzaken voor deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="0590e-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="0590e-115">Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein onderhoudt).</span><span class="sxs-lookup"><span data-stu-id="0590e-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="0590e-116">Uw domein is onlangs verlopen, zodat de MX-record niet kan worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="0590e-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="0590e-117">De MX-record van uw domein is onlangs gewijzigd en de DNS-servers van Office 365 hebben nog steeds eerder DNS-gegevens voor uw domein in de cache opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0590e-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="0590e-118">Hoe los ik foutcode 450 4.4.312 op?</span><span class="sxs-lookup"><span data-stu-id="0590e-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="0590e-119">Werk samen met uw DNS-hostingservice om het probleem met uw domein te identificeren en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="0590e-120">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neemt u contact op met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="0590e-121">Foutcode: er is een time-out van de verbindingscode 450 4.4.315</span><span class="sxs-lookup"><span data-stu-id="0590e-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="0590e-122">Dit betekent doorgaans dat Office 365 geen verbinding kan maken met de e-mailserver van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="0590e-122">Typically, this means Office 365 can't connect to the destination email server.</span></span> <span data-ttu-id="0590e-123">De foutdetails verklaren het probleem.</span><span class="sxs-lookup"><span data-stu-id="0590e-123">The error details will explain the problem.</span></span> <span data-ttu-id="0590e-124">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0590e-124">For example:</span></span>

- <span data-ttu-id="0590e-125">Uw on-premises e-mailserver is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0590e-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="0590e-126">Er is een fout in de slimme hostinstellingen van de connector, dus Office 365 probeert verbinding te maken met het verkeerde IP-adres.</span><span class="sxs-lookup"><span data-stu-id="0590e-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="0590e-127">Hoe los ik foutcode 450 4.4.315 op?</span><span class="sxs-lookup"><span data-stu-id="0590e-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="0590e-128">Ontdek welk scenario op u van toepassing is en breng de nodige correcties aan.</span><span class="sxs-lookup"><span data-stu-id="0590e-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="0590e-129">Als de e-mailstroom bijvoorbeeld correct heeft gewerkt en u de verbindingsinstellingen niet hebt gewijzigd, moet u uw on-premises e-mailomgeving controleren om te zien of de server is uitgeschakeld of als er wijzigingen zijn aangebracht in uw netwerkinfrastructuur (bijvoorbeeld u van internetprovider veranderd bent, dus u hebt nu verschillende IP-adressen).</span><span class="sxs-lookup"><span data-stu-id="0590e-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="0590e-130">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neemt u contact op met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="0590e-131">Foutcode: 450 4.4.316 Verbinding geweigerd</span><span class="sxs-lookup"><span data-stu-id="0590e-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="0590e-132">Deze fout betekent doorgaans dat Office 365 een verbindingsfout heeft ondervonden toen het verbinding probeerde te maken met de e-mailserver van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="0590e-132">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="0590e-133">Een waarschijnlijke oorzaak van deze fout is dat uw firewall verbindingen blokkeert van IP-adressen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="0590e-133">A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses.</span></span> <span data-ttu-id="0590e-134">Deze fout kan ook worden gemaakt als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Office 365 en uw on-premises e-mailomgeving hebt afgesloten.</span><span class="sxs-lookup"><span data-stu-id="0590e-134">Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="0590e-135">Hoe los ik foutcode 450 4.4.316 op?</span><span class="sxs-lookup"><span data-stu-id="0590e-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="0590e-136">Als u postvakken in uw on-premises omgeving hebt, moet u uw firewall-instellingen wijzigen om verbindingen van Office 365 IP-adressen op TCP-poort 25 toe te staan met uw on-premises e-mailservers.</span><span class="sxs-lookup"><span data-stu-id="0590e-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="0590e-137">Zie [URL's en IP-adresbereiken van Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)voor een lijst met de IP-adressen van Office 365.</span><span class="sxs-lookup"><span data-stu-id="0590e-137">For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="0590e-138">Als er geen berichten meer naar uw on-premises omgeving worden verzonden, klikt u nu in de waarschuwing op **Fix,** zodat Office 365 de berichten met ongeldige ontvangers onmiddellijk kan weigeren.</span><span class="sxs-lookup"><span data-stu-id="0590e-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="0590e-139">Dit vermindert het risico van overschrijding van het quotum van uw organisatie voor ongeldige ontvangers, wat van invloed kan zijn op de normale berichtbezorging.</span><span class="sxs-lookup"><span data-stu-id="0590e-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="0590e-140">U ook de volgende instructies gebruiken om het probleem handmatig op te lossen:</span><span class="sxs-lookup"><span data-stu-id="0590e-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="0590e-141">Schakel in het [Exchange-beheercentrum (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365 de connector uit die e-mail van Office 365 naar uw on-premises e-mailomgeving levert uit of verwijder deze:</span><span class="sxs-lookup"><span data-stu-id="0590e-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="0590e-142">Ga in de EAC naar **Mail flow** \> **Connectors**.</span><span class="sxs-lookup"><span data-stu-id="0590e-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="0590e-143">Selecteer de connector met **de** **Van-waarde Office 365** en **de** **e-mailserver** van uw organisatie en doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="0590e-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="0590e-144">De connector verwijderen door op pictogram **Verwijderen** ![te klikken](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="0590e-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="0590e-145">Schakel de connector **Edit** ![uit door op](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) het pictogram Bewerken bewerken te klikken en schakel **het uitschakeling in .**</span><span class="sxs-lookup"><span data-stu-id="0590e-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="0590e-146">Wijzig het geaccepteerde domein in Office 365 dat is gekoppeld aan uw on-premises e-mailomgeving van **Intern relay** naar **gezaghebbend**.</span><span class="sxs-lookup"><span data-stu-id="0590e-146">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="0590e-147">Zie [Geaccepteerde domeinen beheren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)voor instructies .</span><span class="sxs-lookup"><span data-stu-id="0590e-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="0590e-148">**Opmerking:** Deze wijzigingen duren doorgaans tussen de 30 minuten en een uur.</span><span class="sxs-lookup"><span data-stu-id="0590e-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="0590e-149">Controleer na een uur of u de fout niet meer ontvangt.</span><span class="sxs-lookup"><span data-stu-id="0590e-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="0590e-150">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="0590e-151">Foutcode: 450 4.4.317 Kan geen verbinding maken met externe server</span><span class="sxs-lookup"><span data-stu-id="0590e-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="0590e-152">Deze fout betekent doorgaans dat Office 365 is verbonden met de e-mailserver van de bestemming, maar de server heeft onmiddellijk gereageerd op een fout of niet voldoet aan de verbindingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="0590e-152">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="0590e-153">De foutdetails verklaren het probleem.</span><span class="sxs-lookup"><span data-stu-id="0590e-153">The error details will explain the problem.</span></span> <span data-ttu-id="0590e-154">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0590e-154">For example:</span></span>

- <span data-ttu-id="0590e-155">De e-mailserver van de bestemming heeft gereageerd met een fout 'Service niet beschikbaar', wat aangeeft dat de server de communicatie met Office 365 niet kan onderhouden.</span><span class="sxs-lookup"><span data-stu-id="0590e-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="0590e-156">De connector is geconfigureerd om TLS te vereisen, maar de e-mailserver van de bestemming ondersteunt TLS niet.</span><span class="sxs-lookup"><span data-stu-id="0590e-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="0590e-157">Hoe los ik foutcode 450 4.4.317 op?</span><span class="sxs-lookup"><span data-stu-id="0590e-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="0590e-158">Controleer de TLS-instellingen en -certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.</span><span class="sxs-lookup"><span data-stu-id="0590e-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="0590e-159">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="0590e-160">Foutcode: 450 4.4.318 Verbinding werd abrupt gesloten</span><span class="sxs-lookup"><span data-stu-id="0590e-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="0590e-161">Deze fout betekent doorgaans dat Office 365 moeite heeft met het communiceren met uw on-premises e-mailomgeving, zodat de verbinding is verbroken.</span><span class="sxs-lookup"><span data-stu-id="0590e-161">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="0590e-162">De mogelijke oorzaken voor deze fout zijn:</span><span class="sxs-lookup"><span data-stu-id="0590e-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="0590e-163">Uw firewall maakt gebruik van SMTP-regels voor pakketonderzoek en deze regels werken niet goed.</span><span class="sxs-lookup"><span data-stu-id="0590e-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="0590e-164">Uw on-premises e-mailserver werkt niet correct (bijvoorbeeld serviceloopt, loopt vast of systeembronnen is laag), waardoor de server een time-out krijgt en de verbinding met Office 365 wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="0590e-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="0590e-165">Er zijn netwerkproblemen tussen uw on-premises omgeving en Office 365.</span><span class="sxs-lookup"><span data-stu-id="0590e-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="0590e-166">Hoe los ik foutcode 450 4.4.318 op?</span><span class="sxs-lookup"><span data-stu-id="0590e-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="0590e-167">Ontdek welk scenario op u van toepassing is en breng de nodige correcties aan.</span><span class="sxs-lookup"><span data-stu-id="0590e-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="0590e-168">Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Office 365, neemt u contact op met uw netwerkteam om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="0590e-169">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="0590e-170">Foutcode: validatie 450 4.7.320 certificaat is mislukt</span><span class="sxs-lookup"><span data-stu-id="0590e-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="0590e-171">Deze fout betekent doorgaans dat er een fout is opgetreden in Office 365 tijdens het valideren van het certificaat van de e-mailserver van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="0590e-171">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="0590e-172">De foutdetails verklaren de fout.</span><span class="sxs-lookup"><span data-stu-id="0590e-172">The error details will explain the error.</span></span> <span data-ttu-id="0590e-173">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0590e-173">For example:</span></span>

- <span data-ttu-id="0590e-174">Certificaat verlopen</span><span class="sxs-lookup"><span data-stu-id="0590e-174">Certificate expired</span></span>

- <span data-ttu-id="0590e-175">Mismatch certificaatonderwerp</span><span class="sxs-lookup"><span data-stu-id="0590e-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="0590e-176">Certificaat is niet langer geldig</span><span class="sxs-lookup"><span data-stu-id="0590e-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="0590e-177">Hoe los ik foutcode 450 4.7.320 op?</span><span class="sxs-lookup"><span data-stu-id="0590e-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="0590e-178">Bevestig het certificaat of de instellingen op de connector, zodat berichten in de wachtrij in Office 365 kunnen worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="0590e-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="0590e-179">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="0590e-180">Andere foutcodes</span><span class="sxs-lookup"><span data-stu-id="0590e-180">Other error codes</span></span>

<span data-ttu-id="0590e-181">Office 365 heeft moeite met het bezorgen van berichten op uw on-premises of partnere-mailserver.</span><span class="sxs-lookup"><span data-stu-id="0590e-181">Office 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="0590e-182">Gebruik de **doelservergegevens** in de fout om het probleem in uw omgeving te onderzoeken of de connector te wijzigen als er een configuratiefout optreedt.</span><span class="sxs-lookup"><span data-stu-id="0590e-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="0590e-183">Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0590e-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
