---
title: Problemen met e-mail oplossen die naar Microsoft 365 is verzonden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u informatie over het oplossen van problemen met het verzenden van e-mail naar inboxen in Microsoft 365 & aanbevolen procedures voor bulkmailingnaar Microsoft 365-klanten.
ms.openlocfilehash: 0d9c1646aa7491b3da458c7cb0ddeb908873153a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208595"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="73c0a-103">Problemen met e-mail oplossen die naar Microsoft 365 is verzonden</span><span class="sxs-lookup"><span data-stu-id="73c0a-103">Troubleshooting mail sent to Microsoft 365</span></span>

<span data-ttu-id="73c0a-104">In dit artikel vindt u informatie over probleemoplossing voor afzenders die problemen ondervinden wanneer ze e-mail naar inboxen in Microsoft 365 proberen te verzenden en aanbevolen procedures voor bulkmailingnaar klanten.</span><span class="sxs-lookup"><span data-stu-id="73c0a-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="73c0a-105">Beheert u de verzendreputatie van uw IP en domein?</span><span class="sxs-lookup"><span data-stu-id="73c0a-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="73c0a-106">EOP-filtertechnologieën zijn ontworpen om antispambescherming te bieden voor Microsoft 365 en andere Microsoft-producten zoals Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="73c0a-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="73c0a-107">We maken ook gebruik van SPF, DKIM en DMARC; e-mailverificatietechnologieën die helpen bij het oplossen van het probleem van spoofing en phishing door te controleren of het domein dat de e-mail verzendt, daartoe is gemachtigd.</span><span class="sxs-lookup"><span data-stu-id="73c0a-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="73c0a-108">EOP-filtering wordt beïnvloed door een aantal factoren die verband houden met het verzenden van IP, domein, authenticatie, lijstnauwkeurigheid, klachtenpercentages, inhoud en meer.</span><span class="sxs-lookup"><span data-stu-id="73c0a-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="73c0a-109">Van deze, een van de belangrijkste factoren in het rijden van de reputatie van een afzender en hun vermogen om e-mail te leveren is hun junk e-mail klacht tarief.</span><span class="sxs-lookup"><span data-stu-id="73c0a-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="73c0a-110">Stuurt u e-mail vanaf nieuwe IP-adressen?</span><span class="sxs-lookup"><span data-stu-id="73c0a-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="73c0a-111">IP-adressen die niet eerder werden gebruikt om e-mail te verzenden, hebben doorgaans geen reputatie opgebouwd in onze systemen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-111">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="73c0a-112">Als gevolg hiervan hebben e-mails van nieuwe IP's meer kans op leveringsproblemen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-112">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="73c0a-113">Zodra het IP een reputatie heeft opgebouwd voor het niet verzenden van spam, zal EOP meestal zorgen voor een betere e-maillevering.</span><span class="sxs-lookup"><span data-stu-id="73c0a-113">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="73c0a-114">Nieuwe IP's die worden toegevoegd voor domeinen die zijn geverifieerd onder bestaande SPF-records, ervaren doorgaans het extra voordeel van het overnemen van een deel van de verzendreputatie van het domein.</span><span class="sxs-lookup"><span data-stu-id="73c0a-114">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="73c0a-115">Als uw domein heeft een goede serverreputatie nieuwe IP's kunnen ervaren een snellere oprit tijd.</span><span class="sxs-lookup"><span data-stu-id="73c0a-115">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="73c0a-116">Een nieuwe IP kan verwachten volledig worden opvoeren binnen een paar weken of eerder, afhankelijk van het volume, lijst nauwkeurigheid, en ongewenste e-mail klachtenpercentages.</span><span class="sxs-lookup"><span data-stu-id="73c0a-116">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="73c0a-117">Controleren of uw DNS correct is ingesteld</span><span class="sxs-lookup"><span data-stu-id="73c0a-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="73c0a-118">Voor instructies over het maken en onderhouden van DNS-records, inclusief de MX-record die vereist is voor e-mailroutering, moet u contact opnemen met uw DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="73c0a-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="73c0a-119">Zorg ervoor dat u niet adverteren jezelf als een niet-routeerbare IP</span><span class="sxs-lookup"><span data-stu-id="73c0a-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="73c0a-120">We accepteren geen e-mail van afzenders die niet op zoek zijn naar reverse-DNS.</span><span class="sxs-lookup"><span data-stu-id="73c0a-120">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="73c0a-121">In sommige gevallen adverteren legitieme afzenders zichzelf verkeerd als een niet-internet routeerbaar IP wanneer ze een verbinding met EOP proberen te openen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-121">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="73c0a-122">IP-adressen die zijn gereserveerd voor privénetwerken (niet-routeerbaar) zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="73c0a-122">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="73c0a-123">192.168.0.0/16 (of 192.168.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="73c0a-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="73c0a-124">10.0.0.0/8 (of 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="73c0a-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="73c0a-125">172.16.0.0/11 (of 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="73c0a-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="73c0a-126">U hebt een NDR (Non-Delivery Report) ontvangen bij het verzenden van e-mail naar een gebruiker in Office 365</span><span class="sxs-lookup"><span data-stu-id="73c0a-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="73c0a-127">Sommige leveringsproblemen zijn het gevolg van het feit dat het IP-adres van de afzender wordt geblokkeerd door Microsoft of omdat het gebruikersaccount is geïdentificeerd als geblokkeerde afzender vanwege eerdere spamactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="73c0a-127">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="73c0a-128">Als u van mening bent dat u de NDR ten onrechte hebt ontvangen, volgt u eerst alle instructies in het NDR-bericht om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-128">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="73c0a-129">Zie de lijst met foutcodes in rapporten zonder [bezorging e-mail in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie over de fout die u hebt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="73c0a-130">Als u bijvoorbeeld de volgende NDR ontvangt, geeft dit aan dat het verzendende IP-adres door Microsoft is geblokkeerd:</span><span class="sxs-lookup"><span data-stu-id="73c0a-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="73c0a-131">Als u verwijdering uit deze lijst wilt aanvragen, u [de lijstmetnaamportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="73c0a-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="73c0a-132">Mijn e-mail is geland in de map Ongewenste e-mail van de ontvanger</span><span class="sxs-lookup"><span data-stu-id="73c0a-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="73c0a-133">Als een bericht door EOP ten onrechte als spam is geïdentificeerd, u samenwerken met de ontvanger om dit fout-positieve bericht in te dienen bij het Microsoft Spam Analysis Team, dat het bericht evalueert en analyseert.</span><span class="sxs-lookup"><span data-stu-id="73c0a-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="73c0a-134">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="73c0a-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="73c0a-135">Verkeer vanaf mijn IP-adres wordt beperkt door EOP</span><span class="sxs-lookup"><span data-stu-id="73c0a-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="73c0a-136">Als u een NDR van EOP ontvangt die aangeeft dat uw IP-adres wordt beperkt door EOP, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="73c0a-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="73c0a-137">U hebt de NDR ontvangen omdat verdachte activiteit is gedetecteerd vanaf het IP-adres en deze tijdelijk is beperkt terwijl deze verder wordt geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="73c0a-137">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="73c0a-138">Als de verdenking wordt opgehelderd door middel van evaluatie, zal deze beperking binnenkort worden opgeheven.</span><span class="sxs-lookup"><span data-stu-id="73c0a-138">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="73c0a-139">Ik kan geen e-mail ontvangen van afzenders in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73c0a-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="73c0a-140">Om berichten van onze gebruikers te ontvangen, moet u ervoor zorgen dat uw netwerk verbindingen toestaat vanaf de IP-adressen die EOP in onze datacenters gebruikt.</span><span class="sxs-lookup"><span data-stu-id="73c0a-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="73c0a-141">Zie [IP-adressen van Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="73c0a-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="73c0a-142">Aanbevolen procedures voor bulke-mailen naar Microsoft 365-gebruikers</span><span class="sxs-lookup"><span data-stu-id="73c0a-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="73c0a-143">Als u vaak bulke-mailcampagnes uitvoert met Microsoft 365-gebruikers en ervoor wilt zorgen dat uw e-mails op een veilige en tijdige manier binnenkomen, volgt u de tips in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="73c0a-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="73c0a-144">Ervoor zorgen dat de naam Van weergeeft wie het bericht verzendt</span><span class="sxs-lookup"><span data-stu-id="73c0a-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="73c0a-145">Het onderwerp moet een korte samenvatting van wat het bericht over gaat, en de bericht lichaam moet duidelijk en beknopt aangeven wat het aanbod, de dienst, of het product over gaat.</span><span class="sxs-lookup"><span data-stu-id="73c0a-145">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="73c0a-146">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="73c0a-146">For example:</span></span>

<span data-ttu-id="73c0a-147">Juiste:</span><span class="sxs-lookup"><span data-stu-id="73c0a-147">Correct:</span></span>

> <span data-ttu-id="73c0a-148">Van: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="73c0a-148">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="73c0a-149">Onderwerp: Updated catalog for the Christmas season!</span><span class="sxs-lookup"><span data-stu-id="73c0a-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="73c0a-150">Onjuiste:</span><span class="sxs-lookup"><span data-stu-id="73c0a-150">Incorrect:</span></span>

> <span data-ttu-id="73c0a-151">Van: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="73c0a-151">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="73c0a-152">Onderwerp: Catalogi</span><span class="sxs-lookup"><span data-stu-id="73c0a-152">Subject: Catalogs</span></span>

<span data-ttu-id="73c0a-153">Hoe makkelijker je het maakt voor mensen om te weten wie je bent en wat je doet, hoe minder moeite je zult hebben leveren door de meeste spamfilters.</span><span class="sxs-lookup"><span data-stu-id="73c0a-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="73c0a-154">Voeg altijd een afmeldoptie toe in campagne-e-mails</span><span class="sxs-lookup"><span data-stu-id="73c0a-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="73c0a-155">Marketing e-mails, met name nieuwsbrieven, moet altijd een manier van afmelden van toekomstige e-mails.</span><span class="sxs-lookup"><span data-stu-id="73c0a-155">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="73c0a-156">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="73c0a-156">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="73c0a-157">Sommige afzenders bevatten deze optie door ontvangers te verplichten een e-mail te sturen naar een bepaalde alias met 'Afmelden' in het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="73c0a-157">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="73c0a-158">Dit is niet te verkiezen boven het bovenstaande voorbeeld met één klik.</span><span class="sxs-lookup"><span data-stu-id="73c0a-158">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="73c0a-159">Als u ervoor kiest dat ontvangers een e-mail verzenden, moet u ervoor zorgen dat wanneer ze op de koppeling klikken, alle vereiste velden vooraf zijn ingevuld.</span><span class="sxs-lookup"><span data-stu-id="73c0a-159">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="73c0a-160">Gebruik de dubbele opt-in optie voor het op de markt brengen van e-mail of nieuwsbriefregistratie</span><span class="sxs-lookup"><span data-stu-id="73c0a-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="73c0a-161">Deze best practice wordt aanbevolen als uw bedrijf gebruikers nodig heeft of aanmoedigt om hun contactgegevens te registreren om toegang te krijgen tot uw product of services.</span><span class="sxs-lookup"><span data-stu-id="73c0a-161">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="73c0a-162">Sommige bedrijven maken het een praktijk om automatisch aanmelden hun gebruikers voor marketing e-mails of e-nieuwsbrieven tijdens het registratieproces, maar dit wordt beschouwd als een twijfelachtige marketing praktijk in de wereld van e-mail filtering.</span><span class="sxs-lookup"><span data-stu-id="73c0a-162">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="73c0a-163">Tijdens het registratieproces, als het "Ja, stuur me uw nieuwsbrief" of "Ja, stuur me speciale aanbiedingen" checkbox is standaard ingeschakeld, gebruikers die niet goed opletten kan onbedoeld aanmelden voor marketing e-mail of nieuwsbrieven die ze niet willen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="73c0a-164">In plaats daarvan raden we de dubbele opt-in-optie aan, wat betekent dat het selectievakje voor marketinge-mails of nieuwsbrieven standaard niet is aangevinkt.</span><span class="sxs-lookup"><span data-stu-id="73c0a-164">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="73c0a-165">Bovendien, zodra het registratieformulier is ingediend, wordt een verificatie-e-mail verzonden naar de gebruiker met een URL die hen in staat stelt om hun beslissing om marketing e-mails te ontvangen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-165">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="73c0a-166">Dit helpt ervoor te zorgen dat alleen gebruikers die marketinge-mail willen ontvangen, worden aangemeld voor de e-mails, en vervolgens het verzendende bedrijf van twijfelachtige e-mailmarketingpraktijken wissen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="73c0a-167">Ervoor zorgen dat de inhoud van e-mailberichten transparant en traceerbaar is</span><span class="sxs-lookup"><span data-stu-id="73c0a-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="73c0a-168">Net zo belangrijk als de manier waarop de e-mails worden verzonden is de inhoud die ze bevatten.</span><span class="sxs-lookup"><span data-stu-id="73c0a-168">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="73c0a-169">Wanneer u e-mailinhoud maakt, gebruikt u de volgende aanbevolen procedures om ervoor te zorgen dat uw e-mails niet worden gemarkeerd door e-mailfilterservices:</span><span class="sxs-lookup"><span data-stu-id="73c0a-169">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="73c0a-170">Wanneer in het e-mailbericht wordt gevraagd dat ontvangers de afzender aan het adresboek toevoegen, moet duidelijk worden vermeld dat een dergelijke actie geen garantie voor levering is.</span><span class="sxs-lookup"><span data-stu-id="73c0a-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="73c0a-171">Omleidingen opgenomen in de hoofdtekst van het bericht moeten vergelijkbaar en consistent zijn, en niet meervoudig en gevarieerd.</span><span class="sxs-lookup"><span data-stu-id="73c0a-171">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="73c0a-172">Een omleiding in deze context is alles wat wijst weg van het bericht, zoals links en documenten.</span><span class="sxs-lookup"><span data-stu-id="73c0a-172">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="73c0a-173">Als je veel advertenties hebt of Links afmelden of De profielkoppelingen bijwerken, moeten ze allemaal naar hetzelfde domein verwijzen.</span><span class="sxs-lookup"><span data-stu-id="73c0a-173">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="73c0a-174">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="73c0a-174">For example:</span></span>

  <span data-ttu-id="73c0a-175">Juiste:</span><span class="sxs-lookup"><span data-stu-id="73c0a-175">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="73c0a-176">Onjuiste:</span><span class="sxs-lookup"><span data-stu-id="73c0a-176">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="73c0a-177">Vermijd inhoud met grote afbeeldingen en bijlagen of berichten die uitsluitend uit een afbeelding zijn samengesteld.</span><span class="sxs-lookup"><span data-stu-id="73c0a-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="73c0a-178">Uw openbare privacy- of P3P-instellingen moeten duidelijk de aanwezigheid van trackingpixels (webbugs of beacons) vermelden.</span><span class="sxs-lookup"><span data-stu-id="73c0a-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="73c0a-179">Onjuiste e-mailaliassen uit uw databases verwijderen</span><span class="sxs-lookup"><span data-stu-id="73c0a-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="73c0a-180">Elke e-mailalias in uw database die een bounce-back creëert, is niet nodig en brengt uw uitgaande e-mails in gevaar voor verdere controle door e-mailfilterservices.</span><span class="sxs-lookup"><span data-stu-id="73c0a-180">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="73c0a-181">Zorg ervoor dat uw e-maildatabase up-to-date is.</span><span class="sxs-lookup"><span data-stu-id="73c0a-181">Ensure that your email database is up-to-date.</span></span>
