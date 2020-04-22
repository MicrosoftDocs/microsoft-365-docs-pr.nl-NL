---
title: Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Lear over de vereisten voor Van e-mailadressen voor binnenkomende berichten in Microsoft 365. Vanaf november 2017 vereist de service nu RFC-compatibele From-adressen om spoofing te voorkomen.
ms.openlocfilehash: 876ede087b37c381b9e9b557268057122e0987c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633976"
---
# <a name="how-microsoft-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="b09c3-104">Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="b09c3-104">How Microsoft 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="b09c3-105">Microsoft 365 e-mailaccounts ontvangen een steeds groter aantal phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-105">Microsoft 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="b09c3-106">Naast het gebruik van [vervalste (vervalste) afzender e-mailadressen](anti-spoofing-protection.md), aanvallers gebruiken vaak waarden in de Van adres die internet normen schenden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-106">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="b09c3-107">Om dit soort phishing te voorkomen, vereisen Microsoft 365 en Outlook.com nu binnenkomende berichten om een RFC-compatibel Adres op te nemen zoals beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b09c3-107">To help prevent this type of phishing, Microsoft 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="b09c3-108">Deze handhaving werd in november 2017 mogelijk gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-108">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="b09c3-109">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b09c3-109">**Notes**:</span></span>

- <span data-ttu-id="b09c3-110">Als u regelmatig e-mail ontvangt van organisaties die verkeerd zijn vervormd van adressen zoals beschreven in dit onderwerp, moedigt u deze organisaties aan om hun e-mailservers bij te werken om te voldoen aan moderne beveiligingsstandaarden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-110">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="b09c3-111">Het veld gerelateerde afzender (gebruikt door Verzenden namens en mailinglijsten) wordt niet beïnvloed door deze vereisten.</span><span class="sxs-lookup"><span data-stu-id="b09c3-111">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="b09c3-112">Zie voor meer informatie de volgende blogpost: [Wat bedoelen we als we verwijzen naar de 'afzender' van een e-mail?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="b09c3-112">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="b09c3-113">Een overzicht van de normen voor e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="b09c3-113">An overview of email message standards</span></span>

<span data-ttu-id="b09c3-114">Een standaard SMTP-e-mailbericht bestaat uit een *berichtenvelop* en berichtinhoud.</span><span class="sxs-lookup"><span data-stu-id="b09c3-114">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="b09c3-115">De berichtenvelop bevat informatie die nodig is voor het verzenden en leveren van het bericht tussen SMTP-servers.</span><span class="sxs-lookup"><span data-stu-id="b09c3-115">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="b09c3-116">De inhoud van het bericht bevat teksttekstvelden (gezamenlijk de *berichtkop genoemd)* en de berichttekst.</span><span class="sxs-lookup"><span data-stu-id="b09c3-116">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="b09c3-117">De berichtenvelop wordt beschreven in [RFC 5321](https://tools.ietf.org/html/rfc5321)en de berichtkop wordt beschreven in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="b09c3-117">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="b09c3-118">Ontvangers zien nooit de werkelijke berichtenvelop omdat deze wordt gegenereerd door het berichtoverdrachtsproces en het is eigenlijk geen onderdeel van het bericht.</span><span class="sxs-lookup"><span data-stu-id="b09c3-118">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="b09c3-119">Het `5321.MailFrom` adres (ook bekend als het **e-mailadres van** het adres, de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-transmissie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="b09c3-119">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="b09c3-120">Dit e-mailadres wordt meestal opgenomen in het koptekstveld **Return-Path** in de berichtkop (hoewel het mogelijk is dat de afzender een ander **e-mailadres van het retourpad** aanwijst).</span><span class="sxs-lookup"><span data-stu-id="b09c3-120">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="b09c3-121">Het `5322.From` (ook wel bekend als de Afzender Van of P2) is het e-mailadres in het veld **Van** koptekst en is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="b09c3-121">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="b09c3-122">Het Adres van Het is de nadruk van de vereisten in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b09c3-122">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="b09c3-123">Het Adres Van wordt in detail gedefinieerd over verschillende RFC's (bijvoorbeeld RFC 5322-secties 3.2.3, 3.4 en 3.4.1 en [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="b09c3-123">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="b09c3-124">Er zijn veel variaties op het adresseren en wat wordt beschouwd als geldig of ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b09c3-124">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="b09c3-125">Om het simpel te houden, raden we de volgende indeling en definities aan:</span><span class="sxs-lookup"><span data-stu-id="b09c3-125">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="b09c3-126">**Weergavenaam:** een optionele woordgroep die de eigenaar van het e-mailadres beschrijft.</span><span class="sxs-lookup"><span data-stu-id="b09c3-126">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="b09c3-127">We raden u aan de weergavenaam altijd in dubbele aanhalingstekens (") zoals weergegeven, in te sluiten.</span><span class="sxs-lookup"><span data-stu-id="b09c3-127">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="b09c3-128">Als de weergavenaam een komma bevat, _moet_ u de tekenreeks in dubbele aanhalingstekens per RFC 5322 bijsluiten.</span><span class="sxs-lookup"><span data-stu-id="b09c3-128">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="b09c3-129">Als het Van-adres een weergavenaam bevat, moet de waarde Van Mailadres worden ingesloten in hoekhaakjes (< >) zoals weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b09c3-129">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="b09c3-130">Microsoft raadt u ten zeerste aan een spatie in te voegen tussen de weergavenaam en het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b09c3-130">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="b09c3-131">**E-mailadres:** Een e-mailadres maakt gebruik van de indeling: `local-part@domain`</span><span class="sxs-lookup"><span data-stu-id="b09c3-131">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="b09c3-132">**lokaal deel**: een tekenreeks die het postvak identificeert dat aan het adres is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="b09c3-132">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="b09c3-133">Deze waarde is uniek binnen het domein.</span><span class="sxs-lookup"><span data-stu-id="b09c3-133">This value is unique within the domain.</span></span> <span data-ttu-id="b09c3-134">Vaak wordt de gebruikersnaam of GUID van de eigenaar van het postvak gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-134">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="b09c3-135">**domein:** de volledig gekwalificeerde domeinnaam (FQDN) van de e-mailserver die het postvak host dat is geïdentificeerd door het lokale deel van het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b09c3-135">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="b09c3-136">Dit zijn enkele aanvullende overwegingen voor de waarde Van E-mailadres:</span><span class="sxs-lookup"><span data-stu-id="b09c3-136">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="b09c3-137">Slechts één e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b09c3-137">Only one email address.</span></span>
  - <span data-ttu-id="b09c3-138">Wij raden u aan de hoekbeugels niet te scheiden van spaties.</span><span class="sxs-lookup"><span data-stu-id="b09c3-138">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="b09c3-139">Voeg geen extra tekst toe na het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b09c3-139">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="b09c3-140">Voorbeelden van geldig en ongeldig van adressen</span><span class="sxs-lookup"><span data-stu-id="b09c3-140">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="b09c3-141">Het volgende Van e-mailadressen zijn geldig:</span><span class="sxs-lookup"><span data-stu-id="b09c3-141">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="b09c3-142">`From: < sender@contoso.com >`(Niet aanbevolen omdat er spaties zijn tussen de hoekhaakjes en het e-mailadres.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-142">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="b09c3-143">`From: Microsoft 365 <sender@contoso.com>`(Niet aanbevolen omdat de weergavenaam niet is ingesloten met dubbele aanhalingstekens.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-143">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="b09c3-144">Het volgende Van e-mailadressen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="b09c3-144">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="b09c3-145">**Geen adres:** Sommige geautomatiseerde berichten bevatten geen Van-adres.</span><span class="sxs-lookup"><span data-stu-id="b09c3-145">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="b09c3-146">In het verleden, toen Microsoft 365 of Outlook.com een bericht zonder adres van Het Adres ontving, voegde de service de volgende standaardvan: adres toe om het bericht deliverable te maken:</span><span class="sxs-lookup"><span data-stu-id="b09c3-146">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="b09c3-147">Nu worden berichten met een leeg Van-adres niet meer geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="b09c3-147">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="b09c3-148">`From: Microsoft 365 sender@contoso.com`(De weergavenaam is aanwezig, maar het e-mailadres is niet in gesloten in hoekhaakjes.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-148">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="b09c3-149">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Tekst na het e-mailadres.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-149">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="b09c3-150">`From: Sender, Example <sender.example@contoso.com>`(De weergavenaam bevat een komma, maar is niet ingesloten met dubbele aanhalingstekens.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-150">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="b09c3-151">`From: "Microsoft 365 <sender@contoso.com>"`(De hele waarde is onjuist ingesloten in dubbele aanhalingstekens.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-151">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="b09c3-152">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(De weergavenaam is aanwezig, maar het e-mailadres is niet in gesloten in hoekhaakjes.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-152">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="b09c3-153">`From: Microsoft 365<sender@contoso.com>`(Geen ruimte tussen de weergavenaam en de linkerhoekbeugel.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-153">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="b09c3-154">`From: "Microsoft 365"<sender@contoso.com>`(Geen ruimte tussen het afsluitende dubbele aanhalingsteken en de linkerhoekhaak.)</span><span class="sxs-lookup"><span data-stu-id="b09c3-154">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="b09c3-155">Automatische antwoorden op uw aangepaste domein onderdrukken</span><span class="sxs-lookup"><span data-stu-id="b09c3-155">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="b09c3-156">U de waarde `From: <>` niet gebruiken om automatische antwoorden te onderdrukken.</span><span class="sxs-lookup"><span data-stu-id="b09c3-156">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="b09c3-157">In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein.</span><span class="sxs-lookup"><span data-stu-id="b09c3-157">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="b09c3-158">Automatische antwoorden (en alle antwoorden) worden natuurlijk onderdrukt omdat er geen gepubliceerd adres is waar naar de reagerende server berichten kan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-158">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="b09c3-159">Kies een e-maildomein dat geen e-mail kan ontvangen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-159">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="b09c3-160">Als uw primaire domein bijvoorbeeld contoso.com is, u noreply.contoso.com kiezen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-160">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="b09c3-161">De null MX-record voor dit domein bestaat uit één periode.</span><span class="sxs-lookup"><span data-stu-id="b09c3-161">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="b09c3-162">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b09c3-162">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="b09c3-163">Zie [DNS-records maken bij elke DNS-hostingprovider voor Microsoft 365 voor](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)meer informatie over het instellen van MX-records.</span><span class="sxs-lookup"><span data-stu-id="b09c3-163">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="b09c3-164">Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.</span><span class="sxs-lookup"><span data-stu-id="b09c3-164">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="b09c3-165">Overschrijven van adreshandhaving</span><span class="sxs-lookup"><span data-stu-id="b09c3-165">Override From address enforcement</span></span>

<span data-ttu-id="b09c3-166">Als u de vereisten voor binnenkomende e-mail wilt omzeilen, u de IP-lijst met toegestane verbindingen (verbindingsfilter) of e-mailstroomregels (ook wel transportregels genoemd) gebruiken, zoals beschreven in [Lijsten met veilige afzendermaken in Microsoft 365.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="b09c3-166">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="b09c3-167">U de vereisten voor het adres van De u niet overschrijven voor uitgaande e-mail die u vanuit Microsoft 365 verzendt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-167">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="b09c3-168">Bovendien zal Outlook.com geen overschrijvingen van welke aard dan ook toestaan, zelfs niet via ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="b09c3-168">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="b09c3-169">Andere manieren om cybercriminaliteit te voorkomen en te beschermen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b09c3-169">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="b09c3-170">Zie [Top 10 manieren om Microsoft 365 voor bedrijfsabonnementen te beveiligen](../../admin/security-and-compliance/secure-your-business-data.md)voor meer informatie over hoe u uw organisatie versterken tegen phishing, spam, datalekken en andere bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-170">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>