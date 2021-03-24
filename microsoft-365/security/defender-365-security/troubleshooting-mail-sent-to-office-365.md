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
description: Dit artikel bevat informatie over het oplossen van problemen met het verzenden van e-mail naar Postvak IN in Microsoft 365 & procedures voor bulkmailing naar Microsoft 365-klanten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c3017b0e7d0c583c9038f695f9f47010ff92c18a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060285"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="293ba-103">Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen</span><span class="sxs-lookup"><span data-stu-id="293ba-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="293ba-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="293ba-104">**Applies to**</span></span>
- [<span data-ttu-id="293ba-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="293ba-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="293ba-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="293ba-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="293ba-107">Dit artikel bevat informatie over probleemoplossing voor afzenders die problemen ondervinden bij het verzenden van e-mail naar Postvak IN in Microsoft 365 en beste procedures voor bulkmailing naar klanten.</span><span class="sxs-lookup"><span data-stu-id="293ba-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="293ba-108">Beheert u de verzendende reputatie van uw IP en domein?</span><span class="sxs-lookup"><span data-stu-id="293ba-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="293ba-109">EOP-filtertechnologieën zijn ontworpen om bescherming tegen spam te bieden voor Microsoft 365 en andere Microsoft-producten, zoals Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="293ba-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="293ba-110">We maken ook gebruik van SPF, DKIM en DMARC; E-mailverificatietechnologieën die helpen bij het oplossen van het probleem van spoofing en phishing door te controleren of het domein dat de e-mail verstuurt, gemachtigd is om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="293ba-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="293ba-111">EOP-filtering wordt beïnvloed door een aantal factoren met betrekking tot het verzenden van IP, domein, verificatie, lijstnauwkeurigheid, klachttarieven, inhoud en meer.</span><span class="sxs-lookup"><span data-stu-id="293ba-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="293ba-112">Een van deze factoren is een van de belangrijkste factoren bij het in de weg zitten van de reputatie van een afzender en hun mogelijkheid om e-mail te leveren, is het percentage ongewenste e-mail dat wordt geklaagd.</span><span class="sxs-lookup"><span data-stu-id="293ba-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="293ba-113">Verstuurt u e-mail van nieuwe IP-adressen?</span><span class="sxs-lookup"><span data-stu-id="293ba-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="293ba-114">IP-adressen die voorheen niet werden gebruikt om e-mail te verzenden, hebben meestal geen reputatie opgebouwd in onze systemen.</span><span class="sxs-lookup"><span data-stu-id="293ba-114">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="293ba-115">Hierdoor hebben e-mailberichten van nieuwe IPs meer kans op bezorgingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="293ba-115">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="293ba-116">Zodra het IP een reputatie heeft opgebouwd voor het niet verzenden van spam, zal EOP meestal zorgen voor een betere e-mailbezorgingservaring.</span><span class="sxs-lookup"><span data-stu-id="293ba-116">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="293ba-117">Nieuwe IPs die worden toegevoegd voor domeinen die zijn geverifieerd onder bestaande SPF-records, hebben meestal het extra voordeel van het overnemen van een deel van de verzendende reputatie van het domein.</span><span class="sxs-lookup"><span data-stu-id="293ba-117">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="293ba-118">Als uw domein een goede verzendende reputatie heeft, kunnen nieuwe IP's een snellere oprijtijd ervaren.</span><span class="sxs-lookup"><span data-stu-id="293ba-118">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="293ba-119">Een nieuw IP-adres kan binnen een paar weken of eerder volledig worden uitgevoerd, afhankelijk van het volume, de nauwkeurigheid van de lijst en de tarieven voor ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="293ba-119">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="293ba-120">Controleren of uw DNS correct is ingesteld</span><span class="sxs-lookup"><span data-stu-id="293ba-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="293ba-121">Voor instructies over het maken en onderhouden van DNS-records, inclusief de MX-record die vereist is voor het routeren van e-mail, moet u contact opnemen met uw DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="293ba-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="293ba-122">Zorg ervoor dat u geen reclame maakt als een niet-routable IP</span><span class="sxs-lookup"><span data-stu-id="293ba-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="293ba-123">Het is mogelijk dat we geen e-mail accepteren van afzenders die een reverse-DNS-zoekactie mislukken.</span><span class="sxs-lookup"><span data-stu-id="293ba-123">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="293ba-124">In sommige gevallen geven legitieme afzenders zich onjuist aan als een ip-adres dat niet via internet kan worden gebruikt bij het openen van een verbinding met EOP.</span><span class="sxs-lookup"><span data-stu-id="293ba-124">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="293ba-125">IP-adressen die zijn gereserveerd voor privénetwerken (niet-routeerbaar) zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="293ba-125">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="293ba-126">192.168.0.0/16 (of 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="293ba-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="293ba-127">10.0.0.0/8 (of 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="293ba-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="293ba-128">172.16.0.0/11 (of 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="293ba-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="293ba-129">U hebt een rapport over niet-bezorging (NDR) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365</span><span class="sxs-lookup"><span data-stu-id="293ba-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="293ba-130">Sommige bezorgingsproblemen zijn het gevolg van het blokkeren van het IP-adres van de afzender door Microsoft of omdat het gebruikersaccount is geïdentificeerd als geblokkeerde afzender vanwege eerdere spamactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="293ba-130">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="293ba-131">Als u denkt dat u de NDR fout hebt ontvangen, volgt u eerst de instructies in het NDR-bericht om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="293ba-131">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="293ba-132">Zie de lijst met foutcodes in rapporten over [niet-bezorgde e-mail in Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie over de fout die u hebt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="293ba-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="293ba-133">Als u bijvoorbeeld de volgende NDR ontvangt, geeft dit aan dat het verzendende IP-adres is geblokkeerd door Microsoft:</span><span class="sxs-lookup"><span data-stu-id="293ba-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="293ba-134">Als u verwijdering uit deze lijst wilt aanvragen, kunt u de portal voor het verwijderen van de lijst met geblokkeerde [afzenders gebruiken.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="293ba-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="293ba-135">Mijn e-mail is geland in de map Ongewenste e-mail van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="293ba-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="293ba-136">Als een bericht onjuist is geïdentificeerd als spam door EOP, kunt u samen met de geadresseerde dit onwaar positieve bericht indienen bij het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert.</span><span class="sxs-lookup"><span data-stu-id="293ba-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="293ba-137">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="293ba-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="293ba-138">Verkeer van mijn IP-adres wordt beperkt door EOP</span><span class="sxs-lookup"><span data-stu-id="293ba-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="293ba-139">Als u een NDR van EOP ontvangt die aangeeft dat uw IP-adres wordt beperkt door EOP, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="293ba-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="293ba-140">U hebt de NDR ontvangen omdat verdachte activiteit is gedetecteerd vanaf het IP-adres en tijdelijk is beperkt terwijl deze verder wordt geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="293ba-140">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="293ba-141">Als de verdenking wordt geweend door evaluatie, wordt deze beperking binnenkort opgeheven.</span><span class="sxs-lookup"><span data-stu-id="293ba-141">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="293ba-142">Ik kan geen e-mail ontvangen van afzenders in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="293ba-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="293ba-143">Als u berichten van onze gebruikers wilt ontvangen, moet u ervoor zorgen dat uw netwerk verbindingen toestaat van de IP-adressen die door EOP in onze datacenters worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="293ba-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="293ba-144">Zie IP-adressen [voor Exchange Online Protection voor meer informatie.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="293ba-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="293ba-145">Best practices voor bulksgewijs e-mailen naar Microsoft 365-gebruikers</span><span class="sxs-lookup"><span data-stu-id="293ba-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="293ba-146">Als u vaak bulk-e-mailcampagnes voert naar Microsoft 365-gebruikers en ervoor wilt zorgen dat uw e-mailberichten op een veilige en tijdige manier binnenkomen, volgt u de tips in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="293ba-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="293ba-147">Controleer of de van-naam weerspiegelt wie het bericht verstuurt</span><span class="sxs-lookup"><span data-stu-id="293ba-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="293ba-148">Het onderwerp moet een korte samenvatting zijn van waar het bericht over gaat, en de berichtin body moet duidelijk en beknopt aangeven waar het aanbod, de service of het product over gaat.</span><span class="sxs-lookup"><span data-stu-id="293ba-148">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="293ba-149">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="293ba-149">For example:</span></span>

<span data-ttu-id="293ba-150">Juist:</span><span class="sxs-lookup"><span data-stu-id="293ba-150">Correct:</span></span>

> <span data-ttu-id="293ba-151">Van: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="293ba-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="293ba-152">Onderwerp: Bijgewerkte catalogus voor het kerstseizoen!</span><span class="sxs-lookup"><span data-stu-id="293ba-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="293ba-153">Onjuist:</span><span class="sxs-lookup"><span data-stu-id="293ba-153">Incorrect:</span></span>

> <span data-ttu-id="293ba-154">Van: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="293ba-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="293ba-155">Onderwerp: Catalogi</span><span class="sxs-lookup"><span data-stu-id="293ba-155">Subject: Catalogs</span></span>

<span data-ttu-id="293ba-156">Hoe gemakkelijker u het voor mensen maakt om te weten wie u bent en wat u doet, hoe minder problemen u hebt met het leveren van spamfilters.</span><span class="sxs-lookup"><span data-stu-id="293ba-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="293ba-157">Altijd een optie voor afmelden opnemen in campagne-e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="293ba-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="293ba-158">Marketing-e-mailberichten, met name nieuwsbrieven, moeten altijd een manier bevatten om zich af te schrijven van toekomstige e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="293ba-158">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="293ba-159">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="293ba-159">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="293ba-160">Sommige afzenders bevatten deze optie door geadresseerden te verplichten een e-mail te verzenden naar een bepaalde alias met 'Afmelden' in het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="293ba-160">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="293ba-161">Dit is niet de voorkeur boven het bovenstaande voorbeeld met één klik.</span><span class="sxs-lookup"><span data-stu-id="293ba-161">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="293ba-162">Als u ervoor kiest om geadresseerden te verplichten een e-mailbericht te verzenden, moet u ervoor zorgen dat wanneer ze op de koppeling klikken, alle vereiste velden vooraf zijn ingevuld.</span><span class="sxs-lookup"><span data-stu-id="293ba-162">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="293ba-163">Gebruik de optie dubbele aanmelding voor marketing-e-mail of nieuwsbriefregistratie</span><span class="sxs-lookup"><span data-stu-id="293ba-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="293ba-164">Deze aanbevolen praktijk wordt aanbevolen als uw bedrijf gebruikers vereist of aanmoedigt om hun contactgegevens te registreren om toegang te krijgen tot uw product of services.</span><span class="sxs-lookup"><span data-stu-id="293ba-164">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="293ba-165">Sommige bedrijven maken het een gewoonte om hun gebruikers automatisch te registreren voor marketing-e-mailberichten of e-nieuwsbrieven tijdens het registratieproces, maar dit wordt beschouwd als een twijfelachtige marketingpraktijk in de wereld van het filteren van e-mail.</span><span class="sxs-lookup"><span data-stu-id="293ba-165">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="293ba-166">Als tijdens het registratieproces het selectievakje 'Ja, stuur mij uw nieuwsbrief' of 'Ja, stuur mij speciale aanbiedingen' standaard is ingeschakeld, kunnen gebruikers die niet goed opletten zich onbedoeld registreren voor marketing-e-mail of nieuwsbrieven die ze niet willen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="293ba-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="293ba-167">In plaats daarvan raden we de optie dubbele opt-in aan, wat betekent dat het selectievakje voor marketing-e-mailberichten of nieuwsbrieven standaard niet is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="293ba-167">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="293ba-168">Wanneer het registratieformulier is ingediend, wordt er bovendien een verificatie-e-mail naar de gebruiker verzonden met een URL waarmee ze kunnen bevestigen dat ze besluiten marketing-e-mailberichten te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="293ba-168">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="293ba-169">Dit helpt ervoor te zorgen dat alleen gebruikers die marketing-e-mail willen ontvangen, zijn aangemeld voor de e-mailberichten, zodat het verzendende bedrijf vervolgens wordt vrij gesteld van twijfelachtige e-mailmarketingpraktijken.</span><span class="sxs-lookup"><span data-stu-id="293ba-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="293ba-170">Controleer of de inhoud van e-mailberichten transparant en traceerbaar is</span><span class="sxs-lookup"><span data-stu-id="293ba-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="293ba-171">Net zo belangrijk als de manier waarop de e-mailberichten worden verzonden, is de inhoud die ze bevatten.</span><span class="sxs-lookup"><span data-stu-id="293ba-171">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="293ba-172">Gebruik bij het maken van e-mailinhoud de volgende best practices om ervoor te zorgen dat uw e-mailberichten niet worden gemarkeerd door e-mailfilterservices:</span><span class="sxs-lookup"><span data-stu-id="293ba-172">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="293ba-173">Wanneer in het e-mailbericht wordt gevraagd of geadresseerden de afzender aan het adresboek moeten toevoegen, moet duidelijk worden aangegeven dat een dergelijke actie geen garantie voor bezorging is.</span><span class="sxs-lookup"><span data-stu-id="293ba-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="293ba-174">Omleidingen die in de tekst van het bericht zijn opgenomen, moeten vergelijkbaar en consistent zijn, en niet veelvoudig en gevarieerd.</span><span class="sxs-lookup"><span data-stu-id="293ba-174">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="293ba-175">Een omleiding in deze context is alles wat weg wijst van het bericht, zoals koppelingen en documenten.</span><span class="sxs-lookup"><span data-stu-id="293ba-175">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="293ba-176">Als u veel reclame- of afmeldkoppelingen hebt of De profielkoppelingen bijwerken, moeten ze allemaal naar hetzelfde domein wijzen.</span><span class="sxs-lookup"><span data-stu-id="293ba-176">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="293ba-177">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="293ba-177">For example:</span></span>

  <span data-ttu-id="293ba-178">Correct (alle domeinen zijn hetzelfde):</span><span class="sxs-lookup"><span data-stu-id="293ba-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="293ba-179">Onjuist (alle domeinen zijn verschillend):</span><span class="sxs-lookup"><span data-stu-id="293ba-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="293ba-180">Vermijd inhoud met grote afbeeldingen en bijlagen of berichten die uitsluitend uit een afbeelding zijn samengesteld.</span><span class="sxs-lookup"><span data-stu-id="293ba-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="293ba-181">In uw openbare privacy- of P3P-instellingen moet de aanwezigheid van trackingpixels (web bugs of beacons) duidelijk worden aangegeven.</span><span class="sxs-lookup"><span data-stu-id="293ba-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="293ba-182">Onjuiste e-mailalias verwijderen uit uw databases</span><span class="sxs-lookup"><span data-stu-id="293ba-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="293ba-183">Elke e-mailalias in uw database die een bounce-back maakt, is overbodig en brengt uw uitgaande e-mailberichten in gevaar voor nader onderzoek door e-mailfilterservices.</span><span class="sxs-lookup"><span data-stu-id="293ba-183">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="293ba-184">Zorg ervoor dat uw e-maildatabase up-to-date is.</span><span class="sxs-lookup"><span data-stu-id="293ba-184">Ensure that your email database is up-to-date.</span></span>