---
title: Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat informatie over het oplossen van problemen met het verzenden van e-mail naar Postvak IN in Microsoft 365 & voor het bulksgewijs verzenden van e-mail naar klanten van Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286379"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="b3aec-103">Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen</span><span class="sxs-lookup"><span data-stu-id="b3aec-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b3aec-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b3aec-104">**Applies to**</span></span>
- [<span data-ttu-id="b3aec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b3aec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b3aec-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b3aec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="b3aec-107">Dit artikel bevat informatie over het oplossen van problemen met afzenders die problemen ondervinden bij het verzenden van e-mail naar Postvak IN in Microsoft 365 en met de beste procedures voor bulkmailing naar klanten.</span><span class="sxs-lookup"><span data-stu-id="b3aec-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="b3aec-108">Beheert u uw IP- en domeinreputatie?</span><span class="sxs-lookup"><span data-stu-id="b3aec-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="b3aec-109">EOP-filtertechnologieën zijn ontworpen om bescherming tegen spam te bieden voor Microsoft 365 en andere Microsoft-producten, zoals Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b3aec-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="b3aec-110">We maken ook gebruik van SPF, DKIM en DMARC; Technologieën voor e-mailverificatie die helpen het probleem van spoofing en phishing op te lossen door te controleren of het domein dat het e-mailbericht verstuurt, gemachtigd is om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="b3aec-111">EOP-filtering wordt beïnvloed door een aantal factoren die te maken hebben met het verzenden van IP, domein, verificatie, lijstnauwkeurigheid, klachttarieven, inhoud en meer.</span><span class="sxs-lookup"><span data-stu-id="b3aec-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="b3aec-112">Een van deze factoren is een van de belangrijkste factoren voor het verbeteren van de reputatie van een afzender en de mogelijkheid om e-mail te leveren is de klacht over ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3aec-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="b3aec-113">Verstuurt u e-mail vanaf nieuwe IP-adressen?</span><span class="sxs-lookup"><span data-stu-id="b3aec-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="b3aec-114">IP-adressen die voorheen niet werden gebruikt voor het verzenden van e-mail, hebben meestal geen goede reputatie die in onze systemen is opgebouwd.</span><span class="sxs-lookup"><span data-stu-id="b3aec-114">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="b3aec-115">Hierdoor is de kans groter dat e-mails van nieuwe IP's problemen met de bezorging ervaren.</span><span class="sxs-lookup"><span data-stu-id="b3aec-115">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="b3aec-116">Nadat het IP-adres een goede reputatie heeft gekregen voor het niet verzenden van spam, zal EOP meestal zorgen voor een betere ervaring met de bezorging van e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3aec-116">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="b3aec-117">Nieuwe IPs die worden toegevoegd voor domeinen die worden geverifieerd onder bestaande SPF-records, hebben meestal het extra voordeel van het overnemen van een deel van de verzendende reputatie van het domein.</span><span class="sxs-lookup"><span data-stu-id="b3aec-117">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="b3aec-118">Als uw domein een goede reputatie heeft voor het verzenden van nieuwe IP's, kan het sneller verlopen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-118">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="b3aec-119">Een nieuw IP-adres kan naar verwachting binnen enkele weken of sneller volledig worden ge ramped, afhankelijk van het volume, de nauwkeurigheid van de lijst en de tarieven van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3aec-119">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="b3aec-120">Controleer of uw DNS correct is ingesteld</span><span class="sxs-lookup"><span data-stu-id="b3aec-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="b3aec-121">Neem contact op met uw DNS-hostingprovider voor instructies over het maken en onderhouden van DNS-records, inclusief de MX-record die is vereist voor het routeren van e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3aec-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="b3aec-122">Zorg ervoor dat u uzelf niet als een niet-routeerbaar IP-adres aanseert</span><span class="sxs-lookup"><span data-stu-id="b3aec-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="b3aec-123">Het is mogelijk dat er geen e-mail wordt geaccepteerd van afzenders die een reverse-DNS-zoekactie mislukt.</span><span class="sxs-lookup"><span data-stu-id="b3aec-123">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="b3aec-124">In sommige gevallen worden legitieme afzenders onjuist aangekondigd als een niet-internet routeerbaar IP wanneer ze proberen een verbinding met EOP te openen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-124">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="b3aec-125">Ip-adressen die zijn gereserveerd voor privénetwerken (niet-routeerbaar), zijn:</span><span class="sxs-lookup"><span data-stu-id="b3aec-125">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="b3aec-126">192.168.0.0/16 (of 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="b3aec-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="b3aec-127">10.0.0.0/8 (of 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="b3aec-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="b3aec-128">172.16.0.0/11 (of 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="b3aec-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="b3aec-129">U hebt een rapport over niet-bezorging (NDR) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365</span><span class="sxs-lookup"><span data-stu-id="b3aec-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="b3aec-130">Sommige bezorgingsproblemen worden veroorzaakt doordat het IP-adres van de afzender wordt geblokkeerd door Microsoft of omdat het gebruikersaccount is geïdentificeerd als geblokkeerde afzender vanwege eerdere spamactiviteit.</span><span class="sxs-lookup"><span data-stu-id="b3aec-130">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="b3aec-131">Als u denkt dat u de NDR ten fout hebt ontvangen, volgt u eerst de instructies in het NDR-bericht om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-131">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="b3aec-132">Zie de lijst met foutcodes in rapporten over niet-bezorging van [e-mail in Exchange Online voor meer](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)informatie over de fout die u hebt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="b3aec-133">Als u bijvoorbeeld de volgende NDR ontvangt, betekent dit dat het verzendende IP-adres is geblokkeerd door Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b3aec-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="b3aec-134">Als u een verwijdering uit deze lijst wilt aanvragen, kunt u de portal Delist gebruiken om uzelf uit de [lijst met geblokkeerde afzenders te verwijderen.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="b3aec-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="b3aec-135">Mijn e-mail komt terecht in de map Ongewenste e-mail van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="b3aec-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="b3aec-136">Als een bericht door EOP ten onrechte is geïdentificeerd als spam, kunt u samen met de geadresseerde dit fout-positieve bericht verzenden naar het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert.</span><span class="sxs-lookup"><span data-stu-id="b3aec-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="b3aec-137">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b3aec-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="b3aec-138">Verkeer van mijn IP-adres wordt beperkt door EOP</span><span class="sxs-lookup"><span data-stu-id="b3aec-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="b3aec-139">Als u een NDR van EOP ontvangt om aan te geven dat uw IP-adres wordt beperkt door EOP, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b3aec-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="b3aec-140">U hebt de NDR ontvangen omdat er verdachte activiteiten zijn gedetecteerd vanaf het IP-adres en het adres tijdelijk is beperkt terwijl het verder wordt geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="b3aec-140">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="b3aec-141">Als de verdenking via evaluatie wordt opgeheven, wordt deze beperking binnenkort opgeheven.</span><span class="sxs-lookup"><span data-stu-id="b3aec-141">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="b3aec-142">Ik kan geen e-mail ontvangen van afzenders in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3aec-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="b3aec-143">Als u berichten van onze gebruikers wilt ontvangen, moet u ervoor zorgen dat uw netwerk verbindingen toestaat van de IP-adressen die door EOP in onze datacenters worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3aec-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="b3aec-144">Zie IP-adressen van [Exchange Online Protection voor meer informatie.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="b3aec-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="b3aec-145">Best practices voor bulksgewijs e-mailen naar Gebruikers van Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3aec-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="b3aec-146">Als u vaak bulkmailcampagnes voert voor Microsoft 365-gebruikers en er zeker van wilt zijn dat uw e-mailberichten op een veilige en tijdige manier worden ontvangen, volgt u de tips in dit gedeelte.</span><span class="sxs-lookup"><span data-stu-id="b3aec-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="b3aec-147">Zorg ervoor dat de Van-naam weerspiegelt wie het bericht verstuurt</span><span class="sxs-lookup"><span data-stu-id="b3aec-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="b3aec-148">Het onderwerp moet een kort overzicht zijn van waar het bericht over gaat en de bericht zelf moet duidelijk en bondig aangeven waar het aanbod, de service of het product over gaat.</span><span class="sxs-lookup"><span data-stu-id="b3aec-148">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="b3aec-149">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b3aec-149">For example:</span></span>

<span data-ttu-id="b3aec-150">Juist:</span><span class="sxs-lookup"><span data-stu-id="b3aec-150">Correct:</span></span>

> <span data-ttu-id="b3aec-151">Van: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="b3aec-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="b3aec-152">Onderwerp: Bijgewerkte catalogus voor de kerstperiode!</span><span class="sxs-lookup"><span data-stu-id="b3aec-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="b3aec-153">Onjuist:</span><span class="sxs-lookup"><span data-stu-id="b3aec-153">Incorrect:</span></span>

> <span data-ttu-id="b3aec-154">Van: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="b3aec-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="b3aec-155">Onderwerp: Catalogi</span><span class="sxs-lookup"><span data-stu-id="b3aec-155">Subject: Catalogs</span></span>

<span data-ttu-id="b3aec-156">Hoe gemakkelijker u het mensen maakt om te weten wie u bent en wat u doet, hoe minder problemen u krijgt door de meeste spamfilters.</span><span class="sxs-lookup"><span data-stu-id="b3aec-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="b3aec-157">Altijd een optie voor afmelden opnemen in e-mails in campagne</span><span class="sxs-lookup"><span data-stu-id="b3aec-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="b3aec-158">Marketing-e-mails, met name nieuwsbrieven, moeten altijd een manier bevatten om u af te schrijven van toekomstige e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="b3aec-158">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="b3aec-159">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b3aec-159">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="b3aec-160">Sommige afzenders nemen deze optie op door te vereisen dat geadresseerden een e-mailbericht verzenden naar een bepaalde alias met 'Afmelden' in het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b3aec-160">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="b3aec-161">Dit heeft niet de voorkeur boven het voorbeeld met één klik hierboven.</span><span class="sxs-lookup"><span data-stu-id="b3aec-161">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="b3aec-162">Als u wilt dat geadresseerden een e-mailbericht moeten verzenden, controleert u of alle vereiste velden al zijn ingevuld wanneer ze op de koppeling klikken.</span><span class="sxs-lookup"><span data-stu-id="b3aec-162">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="b3aec-163">De optie voor dubbele aanmelding gebruiken voor registratie van marketing-e-mail of nieuwsbrief</span><span class="sxs-lookup"><span data-stu-id="b3aec-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="b3aec-164">Deze aanbevolen praktijk wordt aanbevolen als uw bedrijf vereist of stimuleert gebruikers hun contactgegevens te registreren om toegang te krijgen tot uw product of services.</span><span class="sxs-lookup"><span data-stu-id="b3aec-164">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="b3aec-165">Sommige bedrijven maken het een gewoonte om hun gebruikers automatisch te registreren voor marketing-e-mails of e-nieuwsbrieven tijdens het registratieproces, maar dit wordt gezien als een twijfelachtige marketingprocedure in de wereld van het filteren van e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3aec-165">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="b3aec-166">Als tijdens het registratieproces het selectievakje 'Ja, graag uw nieuwsbrief verzenden' of 'Ja, graag me speciale aanbiedingen sturen' is ingeschakeld, is het mogelijk dat gebruikers die niet zo goed op de hoogte zijn, zich onbedoeld registreren voor marketing-e-mail of nieuwsbrieven die ze niet willen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="b3aec-167">U wordt aangeraden de optie voor dubbele opt-in te gebruiken, wat betekent dat het selectievakje voor marketinge-mailberichten of nieuwsbrieven standaard niet is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b3aec-167">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="b3aec-168">Wanneer het registratieformulier is ingediend, wordt er bovendien een verificatie-e-mail naar de gebruiker verzonden met een URL waarmee hij of zij kan bevestigen dat hij of zij marketinge-mailberichten wil ontvangen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-168">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="b3aec-169">Dit zorgt ervoor dat alleen gebruikers die marketinge-mail willen ontvangen, zijn aangemeld voor de e-mailberichten, waardoor het verzendende bedrijf wordt leeg gemaakt van twijfelachtige marketingpraktijken voor e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3aec-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="b3aec-170">Controleer of de inhoud van e-mailberichten transparant en traceerbaar is</span><span class="sxs-lookup"><span data-stu-id="b3aec-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="b3aec-171">Net zo belangrijk als de manier waarop de e-mailberichten worden verzonden, is de inhoud die ze bevatten.</span><span class="sxs-lookup"><span data-stu-id="b3aec-171">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="b3aec-172">Wanneer u e-mailinhoud maakt, gebruikt u de volgende best practices om ervoor te zorgen dat uw e-mailberichten niet worden gemarkeerd door e-mailfilterservices:</span><span class="sxs-lookup"><span data-stu-id="b3aec-172">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="b3aec-173">Wanneer geadresseerden in het e-mailbericht worden gevraagd de afzender aan het adresboek toe te voegen, moet duidelijk worden aangegeven dat een dergelijke actie geen garantie is voor bezorging.</span><span class="sxs-lookup"><span data-stu-id="b3aec-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="b3aec-174">Omleidingen in de bericht zelf moeten gelijk en consistent zijn en mogen niet veelvoud en gevarieerd zijn.</span><span class="sxs-lookup"><span data-stu-id="b3aec-174">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="b3aec-175">Een omleiding in deze context is alles wat van het bericht af wijst, zoals koppelingen en documenten.</span><span class="sxs-lookup"><span data-stu-id="b3aec-175">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="b3aec-176">Als u veel advertenties ziet of u zich afmeldt of de profielkoppelingen bijwerkt, moeten ze allemaal naar hetzelfde domein wijzen.</span><span class="sxs-lookup"><span data-stu-id="b3aec-176">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="b3aec-177">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b3aec-177">For example:</span></span>

  <span data-ttu-id="b3aec-178">Juist (alle domeinen zijn hetzelfde):</span><span class="sxs-lookup"><span data-stu-id="b3aec-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="b3aec-179">Onjuist (alle domeinen verschillen):</span><span class="sxs-lookup"><span data-stu-id="b3aec-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="b3aec-180">Vermijd inhoud met grote afbeeldingen en bijlagen of berichten die uitsluitend uit een afbeelding bestaan.</span><span class="sxs-lookup"><span data-stu-id="b3aec-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="b3aec-181">Uw openbare privacy- of P3P-instellingen moeten duidelijk de aanwezigheid van tracerings pixels (web bugs ofbakens) melden.</span><span class="sxs-lookup"><span data-stu-id="b3aec-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="b3aec-182">Onjuiste e-mailaliassen verwijderen uit uw databases</span><span class="sxs-lookup"><span data-stu-id="b3aec-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="b3aec-183">Elke e-mailalias in uw database die een niet-uitgaande e-mail maakt, is niet nodig en hiermee worden uw uitgaande e-mailberichten in gevaar gebracht zodat u deze nader kunt onderzoeken door e-mailfilterservices.</span><span class="sxs-lookup"><span data-stu-id="b3aec-183">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="b3aec-184">Controleer of uw e-maildatabase is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="b3aec-184">Ensure that your email database is up-to-date.</span></span>
