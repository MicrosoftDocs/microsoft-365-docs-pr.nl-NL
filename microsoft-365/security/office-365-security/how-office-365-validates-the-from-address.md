---
title: Hoe EOP het van-adres valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie vinden over de typen e-mailadressen die worden geaccepteerd of geweigerd door Exchange Online Protection (EOP) en Outlook.com om phishing te voorkomen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25fbca8fa5d264a212ac25e2035bffde0819383d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659652"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="9de11-103">Hoe EOP het van-adres valideert om phishing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="9de11-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9de11-104">Phishing-aanvallen vormen een constante bedreiging voor elke e-mail organisatie.</span><span class="sxs-lookup"><span data-stu-id="9de11-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="9de11-105">Naast het gebruik van [valse vervalste e-mailadressen van e-mailadressen](anti-spoofing-protection.md), kunnen aanvallers ook waarden gebruiken in het van-adres dat schendt voor internetstandaarden.</span><span class="sxs-lookup"><span data-stu-id="9de11-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="9de11-106">Om dit type phishing te helpen voorkomen, hebben inkomende berichten via Exchange Online Protection (EOP) en Outlook.com voortaan inkomende berichten opgenomen, zodat een RFC-compatibel adres wordt opgenomen in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="9de11-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="9de11-107">Dit executie is ingeschakeld in november 2017.</span><span class="sxs-lookup"><span data-stu-id="9de11-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="9de11-108">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="9de11-108">**Notes**:</span></span>

- <span data-ttu-id="9de11-109">Als u regelmatig e-mailberichten ontvangt van organisaties die een verkeerd gespelde fout hebben op basis van adressen zoals in dit artikel wordt beschreven, raden we u aan deze organisaties te laten bijwerken dat hun e-mailservers voldoen aan de moderne beveiligings normen</span><span class="sxs-lookup"><span data-stu-id="9de11-109">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="9de11-110">Het veld voor de bijbehorende afzender (voor verzenden namens en adressenlijsten) wordt niet beïnvloed door deze vereisten.</span><span class="sxs-lookup"><span data-stu-id="9de11-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="9de11-111">Voor meer informatie raadpleegt u het volgende blogbericht: [Wat betekenen we wanneer we naar de afzender van een e-mailbericht verwijzen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="9de11-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="9de11-112">Een overzicht van de standaarden voor e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="9de11-112">An overview of email message standards</span></span>

<span data-ttu-id="9de11-113">Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en de inhoud van het bericht.</span><span class="sxs-lookup"><span data-stu-id="9de11-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="9de11-114">De envelop bericht bevat informatie die nodig is voor het verzenden en het verzenden van het bericht tussen SMTP-servers.</span><span class="sxs-lookup"><span data-stu-id="9de11-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="9de11-115">De inhoud van het bericht bevat berichtkop velden (gezamenlijk de kop van het *e-mailbericht* genoemd) en de berichttekst.</span><span class="sxs-lookup"><span data-stu-id="9de11-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="9de11-116">De envelop van het bericht wordt beschreven in [rfc 5321](https://tools.ietf.org/html/rfc5321)en de kop van het e-mailbericht wordt beschreven in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="9de11-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="9de11-117">Geadresseerden zien de envelop met het werkelijke bericht niet omdat deze wordt gegenereerd door het proces voor het verzenden van berichten en het maakt niet uit van het bericht.</span><span class="sxs-lookup"><span data-stu-id="9de11-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="9de11-118">Het `5321.MailFrom` adres (ook wel **e-mail adres van** de afzender, de afzender van P1 of de afzender) is het e-mailadres dat wordt gebruikt in de SMTP-overdracht van het bericht.</span><span class="sxs-lookup"><span data-stu-id="9de11-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="9de11-119">Dit e-mailadres wordt meestal opgenomen in het veld voor **de veldnamenrij in de kop van** het bericht (hoewel het mogelijk is dat de afzender een ander e-mailadres voor het **retour traject** aanwijst).</span><span class="sxs-lookup"><span data-stu-id="9de11-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="9de11-120">De `5322.From` (ook bekend als de afzender van address of P2) is het e-mailadres in het veld **van** koptekst en het e-mailadres van de afzender dat wordt weergegeven in e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="9de11-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="9de11-121">Het van-adres is de focus van de vereisten in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="9de11-121">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="9de11-122">Het van-adres wordt uitvoerig beschreven in diverse Rfc's (bijvoorbeeld RFC 5322, punt 3.2.3, 3,4 en 3.4.1, en [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="9de11-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="9de11-123">Er zijn veel variaties op de adressering en wat wordt als geldig of ongeldig beschouwd.</span><span class="sxs-lookup"><span data-stu-id="9de11-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="9de11-124">Om de sjabloon eenvoudig te houden, raden we de volgende opmaak en definities aan:</span><span class="sxs-lookup"><span data-stu-id="9de11-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="9de11-125">**Weergavenaam**: een optionele woordgroep waarmee de eigenaar van het e-mailadres wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="9de11-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="9de11-126">U wordt aangeraden de weergavenaam altijd tussen dubbele aanhalingstekens (") te plaatsen, zoals getoond.</span><span class="sxs-lookup"><span data-stu-id="9de11-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="9de11-127">Als de weergavenaam een komma bevat, _moet_ u de tekenreeks tussen dubbele aanhalingstekens plaatsen per RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="9de11-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="9de11-128">Als het van-adres een weergavenaam bevat, moet de waarde van EmailAddress tussen punthaken (< >) worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9de11-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="9de11-129">U wordt ten zeerste aangeraden een spatie in te voegen tussen de weergavenaam en het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="9de11-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="9de11-130">**EmailAddress**: voor een e-mailadres wordt de volgende indeling gebruikt `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="9de11-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="9de11-131">**local-part**: een tekenreeks die het postvak identificeert dat is gekoppeld aan het adres.</span><span class="sxs-lookup"><span data-stu-id="9de11-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="9de11-132">Deze waarde is uniek binnen het domein.</span><span class="sxs-lookup"><span data-stu-id="9de11-132">This value is unique within the domain.</span></span> <span data-ttu-id="9de11-133">Vaak wordt de gebruikersnaam of GUID van het postvak van de eigenaar gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9de11-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="9de11-134">**Domain**: de FQDN-naam (Fully Qualified Domain Name) van de e-mailserver waarop het postvak wordt gehost dat wordt aangeduid door het lokale deel van het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="9de11-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="9de11-135">Hier volgen enkele aanvullende aandachtspunten voor de waarde van EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="9de11-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="9de11-136">Slechts één e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="9de11-136">Only one email address.</span></span>
  - <span data-ttu-id="9de11-137">We raden u aan dat u de haken met spaties niet scheidt.</span><span class="sxs-lookup"><span data-stu-id="9de11-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="9de11-138">Neem geen aanvullende tekst onder het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="9de11-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="9de11-139">Voorbeelden van geldige en ongeldige adressen van adressen</span><span class="sxs-lookup"><span data-stu-id="9de11-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="9de11-140">De volgende e-mailadressen zijn geldig:</span><span class="sxs-lookup"><span data-stu-id="9de11-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="9de11-141">`From: < sender@contoso.com >` (Niet aanbevolen omdat er spaties tussen de punthaken en het e-mailadres staan.)</span><span class="sxs-lookup"><span data-stu-id="9de11-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="9de11-142">`From: Microsoft 365 <sender@contoso.com>` (Wordt niet aanbevolen, omdat de weergavenaam niet tussen dubbele aanhalingstekens is geplaatst.)</span><span class="sxs-lookup"><span data-stu-id="9de11-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="9de11-143">De volgende e-mailadressen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="9de11-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="9de11-144">**Nee van-adres**: sommige geautomatiseerde berichten bevatten geen van-adres.</span><span class="sxs-lookup"><span data-stu-id="9de11-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="9de11-145">Wanneer Microsoft 365 of Outlook.com in het verleden een bericht heeft ontvangen zonder een van-adres, heeft de service het volgende standaard van-adres toegevoegd aan het bericht product:</span><span class="sxs-lookup"><span data-stu-id="9de11-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="9de11-146">Berichten met een leeg van-adres worden nu niet meer geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="9de11-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="9de11-147">`From: Microsoft 365 sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres staat niet tussen punthaken.)</span><span class="sxs-lookup"><span data-stu-id="9de11-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="9de11-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Tekst na het e-mailadres)</span><span class="sxs-lookup"><span data-stu-id="9de11-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="9de11-149">`From: Sender, Example <sender.example@contoso.com>` (De weergavenaam bevat een komma, maar staat niet tussen dubbele aanhalingstekens).</span><span class="sxs-lookup"><span data-stu-id="9de11-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="9de11-150">`From: "Microsoft 365 <sender@contoso.com>"` (De volledige waarde is een onjuiste waarde tussen dubbele aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="9de11-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="9de11-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres staat niet tussen punthaken.)</span><span class="sxs-lookup"><span data-stu-id="9de11-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="9de11-152">`From: Microsoft 365<sender@contoso.com>` (Geen spatie tussen de naam van de weergave en de punthaak links.)</span><span class="sxs-lookup"><span data-stu-id="9de11-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="9de11-153">`From: "Microsoft 365"<sender@contoso.com>` (Geen spatie tussen de dubbele aanhalingstekens en de punthaak links</span><span class="sxs-lookup"><span data-stu-id="9de11-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="9de11-154">Automatisch beantwoorden met uw aangepaste domein onderdrukken</span><span class="sxs-lookup"><span data-stu-id="9de11-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="9de11-155">U kunt de waarde niet gebruiken `From: <>` om automatisch antwoord te onderdrukken.</span><span class="sxs-lookup"><span data-stu-id="9de11-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="9de11-156">In plaats daarvan moet u een lege MX-record voor uw aangepaste domein instellen.</span><span class="sxs-lookup"><span data-stu-id="9de11-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="9de11-157">Automatisch beantwoorden (en alle antwoorden) worden natuurlijk niet doorgeslagen omdat er geen gepubliceerd adres is waarop de antwoord server berichten kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="9de11-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="9de11-158">Kies een e-mail domein dat geen e-mail kan ontvangen.</span><span class="sxs-lookup"><span data-stu-id="9de11-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="9de11-159">Als uw primaire domein bijvoorbeeld contoso.com is, kunt u noreply.contoso.com kiezen.</span><span class="sxs-lookup"><span data-stu-id="9de11-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="9de11-160">De lege MX-record voor dit domein bevat één periode.</span><span class="sxs-lookup"><span data-stu-id="9de11-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="9de11-161">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9de11-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="9de11-162">Zie [DNS-records maken bij een DNS-hosting provider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het instellen van MX-records.</span><span class="sxs-lookup"><span data-stu-id="9de11-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="9de11-163">Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null-waarde (null).</span><span class="sxs-lookup"><span data-stu-id="9de11-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="9de11-164">Opheffen van adres afdwingen</span><span class="sxs-lookup"><span data-stu-id="9de11-164">Override From address enforcement</span></span>

<span data-ttu-id="9de11-165">Als u niet wilt dat de van toepassing zijnde adressen voor inkomende e-mail wordt gebruikt, kunt u in de lijst met veilige afzenders (ook wel een verbinding maken met behulp van de lijst met [veilige afzenders](create-safe-sender-lists-in-office-365.md)) of e-mail stroom regels (ook wel de gebruikte transportregels) in microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de11-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="9de11-166">U kunt de van-adres vereisten voor uitgaande e-mail die u vanuit Microsoft 365 verzendt niet overschrijven.</span><span class="sxs-lookup"><span data-stu-id="9de11-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="9de11-167">Daarnaast mag Outlook.com geen overschrijvingen van welke aard dan ook ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="9de11-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="9de11-168">Andere manieren om te voorkomen dat u cybercrimes in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9de11-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="9de11-169">Zie de [tien beste manieren om uw abonnement op Microsoft 365 voor bedrijven te beveiligen](../../admin/security-and-compliance/secure-your-business-data.md)voor meer informatie over hoe u uw organisatie kunt versterken tegen phishing en spam, de schending van gegevens en andere bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="9de11-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
