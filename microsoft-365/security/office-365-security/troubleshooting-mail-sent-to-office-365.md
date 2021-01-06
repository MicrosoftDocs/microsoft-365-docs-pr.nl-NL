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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat informatie over het oplossen van problemen met het verzenden van e-mail naar postvakken in Microsoft 365 & best practices voor bulk mailing naar klanten met Microsoft 365.
ms.openlocfilehash: 3504d7518073826f3979c3c837c58d4406886b41
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760480"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="ca38a-103">Problemen met e-mailberichten die worden verzonden naar Microsoft 365 oplossen</span><span class="sxs-lookup"><span data-stu-id="ca38a-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ca38a-104">Dit artikel bevat informatie over het oplossen van problemen met afzenders die problemen ondervinden wanneer u e-mail probeert te verzenden naar postvakken in Microsoft 365 en best practices voor bulk mailing naar klanten.</span><span class="sxs-lookup"><span data-stu-id="ca38a-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="ca38a-105">Beheert u de reputatie van uw IP en domein?</span><span class="sxs-lookup"><span data-stu-id="ca38a-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="ca38a-106">EOP filter technologieën zijn ontworpen om antispam beveiliging voor Microsoft 365 en andere Microsoft-producten zoals Exchange server te bieden.</span><span class="sxs-lookup"><span data-stu-id="ca38a-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="ca38a-107">We kunnen ook gebruikmaken van SPF, DKIM en DMARC; verificatietechnologieën voor e-mail die u helpen bij het oplossen van problemen met spoofing en phishing verifieert het domein dat het e-mailbericht verzendt, is geautoriseerd.</span><span class="sxs-lookup"><span data-stu-id="ca38a-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="ca38a-108">EOP filteren wordt beïnvloed door een aantal factoren die verband houden met het verzenden van IP, domein, authenticatie, nauwkeurigheid van klachten, klachten tarieven, inhoud en meer.</span><span class="sxs-lookup"><span data-stu-id="ca38a-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="ca38a-109">Een van de belangrijkste factoren in het rijden van de reputatie van een afzender en de mogelijkheid om e-mail te bezorgen is hun klachten tarief voor ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ca38a-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="ca38a-110">Verzendt u e-mail van nieuwe IP-adressen?</span><span class="sxs-lookup"><span data-stu-id="ca38a-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="ca38a-111">IP-adressen die u niet eerder hebt gebruikt voor het verzenden van e-mail, hebben doorgaans geen reputatie opgebouwd in onze systemen.</span><span class="sxs-lookup"><span data-stu-id="ca38a-111">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="ca38a-112">Daarom hebben e-mailberichten van nieuwe IPs waarschijnlijker problemen met de bezorging.</span><span class="sxs-lookup"><span data-stu-id="ca38a-112">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="ca38a-113">Wanneer het IP-adres voor het versturen van spam niet via spam is opgebouwd, kan EOP u meestal een betere e-mail bezorgings ervaring bieden.</span><span class="sxs-lookup"><span data-stu-id="ca38a-113">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="ca38a-114">Nieuwe IP-adressen die worden toegevoegd voor domeinen die zijn geverifieerd onder bestaande SPF-records, hebben meestal het extra voordeel van het overnemen van een deel van het domein.</span><span class="sxs-lookup"><span data-stu-id="ca38a-114">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="ca38a-115">Als uw domein een goede vernieuwings ervaring heeft, kunnen de nieuwe IPs sneller worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ca38a-115">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="ca38a-116">Een nieuw IP-adres kan naar verwachting binnen een paar weken of sneller worden afgehandeld, afhankelijk van volume, nauwkeurigheid van de lijst en een spam tarief voor ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ca38a-116">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="ca38a-117">Controleren of uw DNS juist is ingesteld</span><span class="sxs-lookup"><span data-stu-id="ca38a-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="ca38a-118">Als u wilt weten hoe u DNS-records maakt en onderhoudt, waaronder de MX-record die nodig is voor e-mail routering, moet u contact opnemen met uw DNS-hosting provider.</span><span class="sxs-lookup"><span data-stu-id="ca38a-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="ca38a-119">Ervoor zorgen dat u zichzelf niet adverteert als een niet-routeerbaar IP-adres</span><span class="sxs-lookup"><span data-stu-id="ca38a-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="ca38a-120">We accepteren mogelijk geen e-mailberichten van afzenders die een opzoek service voor omkering van de DNS hebben.</span><span class="sxs-lookup"><span data-stu-id="ca38a-120">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="ca38a-121">In sommige gevallen adverteert legitiem afzenders zichzelf onjuist als een niet-Internet routeerbaar IP-adres bij het openen van een verbinding met EOP.</span><span class="sxs-lookup"><span data-stu-id="ca38a-121">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="ca38a-122">IP-adressen die zijn gereserveerd voor privé-netwerken (niet-routeerbaar), zijn:</span><span class="sxs-lookup"><span data-stu-id="ca38a-122">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="ca38a-123">192.168.0.0/16 (of 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="ca38a-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="ca38a-124">10.0.0.0/8 (of 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="ca38a-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="ca38a-125">172.16.0.0/11 (of 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="ca38a-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="ca38a-126">U hebt een NDR van een niet-uitgevoerde bezorging van een e-mailbericht ontvangen voor het verzenden van e-mail naar een gebruiker in Office 365</span><span class="sxs-lookup"><span data-stu-id="ca38a-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="ca38a-127">Sommige bezorgings problemen zijn het gevolg van het IP-adres van de afzender dat door Microsoft wordt geblokkeerd of omdat het gebruikersaccount wordt herkend als niet-geblokkeerde afzender vanwege eerdere spam activiteiten.</span><span class="sxs-lookup"><span data-stu-id="ca38a-127">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="ca38a-128">Als u van mening bent dat u de NDR een foutmelding hebt ontvangen, volgt u eerst de instructies in het NDR-bericht om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="ca38a-128">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="ca38a-129">Als u meer wilt weten over de fout die u hebt ontvangen, raadpleegt u de lijst met foutcodes in [rapporten over niet-uitgevoerde bezorging van e-mail in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="ca38a-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="ca38a-130">Als u bijvoorbeeld de volgende NDR ontvangt, wordt aangegeven dat het verzendende IP-adres door Microsoft is geblokkeerd:</span><span class="sxs-lookup"><span data-stu-id="ca38a-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="ca38a-131">Als u de lijst wilt verwijderen, kunt u deze [uit de lijst met geblokkeerde afzenders verwijderen via de portal delijstte](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="ca38a-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="ca38a-132">Mijn e-mailbericht in de map Ongewenste E-mail van de geadresseerde</span><span class="sxs-lookup"><span data-stu-id="ca38a-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="ca38a-133">Als een bericht onjuist is geïdentificeerd als spam via EOP, kunt u met de ontvanger werken om dit foutbericht te verzenden naar het Microsoft spam Analysis-Team, dat het bericht evalueert en analyseert.</span><span class="sxs-lookup"><span data-stu-id="ca38a-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="ca38a-134">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ca38a-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="ca38a-135">Verkeer van mijn IP-adres wordt vertraagd door EOP</span><span class="sxs-lookup"><span data-stu-id="ca38a-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="ca38a-136">Als u een NDR ontvangt van EOP, wordt aangegeven dat uw IP-adres wordt vertraagd door EOP, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ca38a-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="ca38a-137">U ontving de NDR omdat verdachte activiteiten zijn gedetecteerd van het IP-adres, en het tijdelijk niet is beperkt terwijl de actie wordt voortgezet.</span><span class="sxs-lookup"><span data-stu-id="ca38a-137">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="ca38a-138">Als het vermoeden is opgeheven via evaluatie, wordt deze beperking kort weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ca38a-138">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="ca38a-139">Ik kan geen e-mail ontvangen van afzenders in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca38a-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="ca38a-140">Als u berichten van onze gebruikers wilt ontvangen, moet u ervoor zorgen dat uw netwerkverbindingen toestaat van de IP-adressen die EOP in onze datacenters gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ca38a-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="ca38a-141">Zie [IP-adressen voor Exchange Online Protection](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ca38a-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="ca38a-142">Best practices voor bulksgewijs e-mailen naar Microsoft 365-gebruikers</span><span class="sxs-lookup"><span data-stu-id="ca38a-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="ca38a-143">Als u vaak grote hoeveelheden e-mail campagnes doet voor Microsoft 365-gebruikers en u er zeker van wilt zijn dat uw e-mailberichten op een veilige en tijd uitkomen, volgt u de tips in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="ca38a-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="ca38a-144">Ervoor zorgen dat de van-naam weerspiegelt de persoon die het bericht verzendt</span><span class="sxs-lookup"><span data-stu-id="ca38a-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="ca38a-145">Het onderwerp moet een kort overzicht zijn van de inhoud van het bericht en de hoofdtekst van het bericht moet duidelijk en bondig aangeven wat de aanbieding, de service of het product benadert.</span><span class="sxs-lookup"><span data-stu-id="ca38a-145">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="ca38a-146">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ca38a-146">For example:</span></span>

<span data-ttu-id="ca38a-147">Juist:</span><span class="sxs-lookup"><span data-stu-id="ca38a-147">Correct:</span></span>

> <span data-ttu-id="ca38a-148">Van: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="ca38a-148">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="ca38a-149">Onderwerp: heeft een catalogus voor een kerst seizoen bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="ca38a-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="ca38a-150">Onjuist:</span><span class="sxs-lookup"><span data-stu-id="ca38a-150">Incorrect:</span></span>

> <span data-ttu-id="ca38a-151">Van: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="ca38a-151">From: someone@outlook.com</span></span> <br> <span data-ttu-id="ca38a-152">Onderwerp: catalogi</span><span class="sxs-lookup"><span data-stu-id="ca38a-152">Subject: Catalogs</span></span>

<span data-ttu-id="ca38a-153">Het eenvoudiger maken om te weten wie u bent en wat u aan het doen bent, hoe minder problemen u te bieden via de meeste spamfilters.</span><span class="sxs-lookup"><span data-stu-id="ca38a-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="ca38a-154">De optie voor het afschrijven van een abonnement altijd opnemen in e-mail van een campagne</span><span class="sxs-lookup"><span data-stu-id="ca38a-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="ca38a-155">Marketing e-mailberichten, met name nieuwsbrieven, moeten altijd een e-mailbericht over het afmelden bij toekomstige e-mailberichten bevatten.</span><span class="sxs-lookup"><span data-stu-id="ca38a-155">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="ca38a-156">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ca38a-156">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="ca38a-157">Sommige afzenders bevatten deze optie, omdat geadresseerden een e-mailbericht naar een bepaalde alias moeten verzenden met ' Afmelden ' in het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="ca38a-157">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="ca38a-158">Dit is niet de voorkeur voor één klik hierboven.</span><span class="sxs-lookup"><span data-stu-id="ca38a-158">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="ca38a-159">Als u wilt dat geadresseerden een e-mailbericht moeten verzenden, moet u ervoor zorgen dat de vereiste velden vooraf zijn ingevuld wanneer ze op de koppeling klikken.</span><span class="sxs-lookup"><span data-stu-id="ca38a-159">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="ca38a-160">Gebruik de optie voor dubbele opt-in voor marketing-e-mail of nieuwsbrief registratie</span><span class="sxs-lookup"><span data-stu-id="ca38a-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="ca38a-161">Deze beste gewoonte is raadzaam als uw bedrijf gebruikers informatie wil registreren of aan te moedigen om toegang te krijgen tot uw product of services.</span><span class="sxs-lookup"><span data-stu-id="ca38a-161">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="ca38a-162">Met sommige bedrijven wordt het automatisch om gebruikers voor marketing-e-mailberichten of e-mail nieuwsbrieven automatisch aan te melden voor het registreren van een e-mailbericht, maar dit wordt beschouwd als een dubieuze marketing procedure in de wereld van e-mail filtering.</span><span class="sxs-lookup"><span data-stu-id="ca38a-162">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="ca38a-163">Als u tijdens het registratieproces het selectievakje ' Ja, stuur mij uw nieuwsbrief verzenden ' of ' Ja, kies mij een speciale aanbieding ' is ingeschakeld, kunnen gebruikers die niet kunnen worden ingeschreven, registreren voor marketing-e-mailberichten of nieuwsbrieven die ze niet willen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ca38a-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="ca38a-164">We raden u aan in plaats daarvan de optie voor dubbele opt-in, wat betekent dat het selectievakje voor marketing-e-mails of nieuwsbrief nieuwsbrieven standaard niet wordt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ca38a-164">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="ca38a-165">Wanneer het registratieformulier is ingediend, wordt er een verificatie-e-mailbericht naar de gebruiker verzonden met een URL, zodat ze hun beslissing kunnen bevestigen voor het ontvangen van marketing-e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="ca38a-165">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="ca38a-166">Dit helpt ervoor te zorgen dat alleen gebruikers van marketing via e-mail een e-mailbericht ontvangen voor de e-mailberichten, en dan de verstuurde vennootschap van een willekeurige e-mail marketing procedure.</span><span class="sxs-lookup"><span data-stu-id="ca38a-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="ca38a-167">Zorg ervoor dat de inhoud van het e-mailbericht transparant en vervolgen is</span><span class="sxs-lookup"><span data-stu-id="ca38a-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="ca38a-168">Net zo belangrijk als de manier waarop e-mailberichten worden verzonden, is de inhoud die deze bevat.</span><span class="sxs-lookup"><span data-stu-id="ca38a-168">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="ca38a-169">Wanneer u e-mail inhoud maakt, kunt u de volgende aanbevolen procedures gebruiken om ervoor te zorgen dat uw e-mailberichten niet worden gemarkeerd met een filterservice voor e-mail:</span><span class="sxs-lookup"><span data-stu-id="ca38a-169">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="ca38a-170">Als het e-mailbericht verzoekt dat geadresseerden de afzender toevoegen aan het adresboek, moet u duidelijk aangeven dat deze actie geen garantie biedt.</span><span class="sxs-lookup"><span data-stu-id="ca38a-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="ca38a-171">Omleidingen die in de hoofdtekst van het bericht zijn opgenomen, moeten vergelijkbaar en consistent zijn, en niet meerdere en geen variabele.</span><span class="sxs-lookup"><span data-stu-id="ca38a-171">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="ca38a-172">Een omleiding in deze context is iets dat verwijst naar het bericht, bijvoorbeeld koppelingen en documenten.</span><span class="sxs-lookup"><span data-stu-id="ca38a-172">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="ca38a-173">Als u veel reclame of de koppeling naar het profiel wilt bijwerken of de profielkoppelingen wilt bijwerken, moeten deze allemaal naar hetzelfde domein verwijzen.</span><span class="sxs-lookup"><span data-stu-id="ca38a-173">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="ca38a-174">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ca38a-174">For example:</span></span>

  <span data-ttu-id="ca38a-175">Correct (alle domeinen zijn hetzelfde):</span><span class="sxs-lookup"><span data-stu-id="ca38a-175">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="ca38a-176">Onjuist (alle domeinen verschillen):</span><span class="sxs-lookup"><span data-stu-id="ca38a-176">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="ca38a-177">Vermijd inhoud met grote afbeeldingen en bijlagen, of berichten die uitsluitend uit een afbeelding bestaan.</span><span class="sxs-lookup"><span data-stu-id="ca38a-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="ca38a-178">De aanwezigheid van uw openbare privacy-of P3P-instellingen moet duidelijk duidelijk zijn voor het bijhouden van pixels (web bugs of beacons).</span><span class="sxs-lookup"><span data-stu-id="ca38a-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="ca38a-179">Onjuiste e-mail aliassen verwijderen uit uw databases</span><span class="sxs-lookup"><span data-stu-id="ca38a-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="ca38a-180">Elke e-mail alias in de database die een stuiterende stuiter maakt, is overbodig en zet uw uitgaande e-mailberichten op het risico voor verder onderzoek via e-mail filter Services.</span><span class="sxs-lookup"><span data-stu-id="ca38a-180">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="ca38a-181">Zorg ervoor dat uw e-mail database up-to-date is.</span><span class="sxs-lookup"><span data-stu-id="ca38a-181">Ensure that your email database is up-to-date.</span></span>
