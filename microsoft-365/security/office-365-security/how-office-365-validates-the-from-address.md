---
title: Hoe EOP het Van-adres valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over de typen e-mailadressen die worden geaccepteerd of geweigerd door Exchange Online Protection (EOP) en Outlook.com om phishing te voorkomen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167513"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="ea9c0-103">Hoe EOP het Van-adres valideert om phishing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="ea9c0-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ea9c0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ea9c0-104">**Applies to**</span></span>
- [<span data-ttu-id="ea9c0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ea9c0-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ea9c0-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ea9c0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="ea9c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea9c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ea9c0-108">Phishing-aanvallen vormen een constante bedreiging voor elke e-mailorganisatie.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="ea9c0-109">Naast het gebruik van e-mailadressen met vervalste [(vervalste) afzenders](anti-spoofing-protection.md)gebruiken aanvallers vaak waarden in het Van-adres die in strijd zijn met internetstandaarden.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="ea9c0-110">Om dit type phishing te voorkomen, vereisen Exchange Online Protection (EOP) en Outlook.com nu inkomende berichten met een RFC-compatibel Van-adres, zoals beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="ea9c0-111">Dit afdwingen is ingeschakeld in november 2017.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="ea9c0-112">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-112">**Notes**:</span></span>

- <span data-ttu-id="ea9c0-113">Als u regelmatig e-mail ontvangt van organisaties die een verkeerd geadresseerde van een adres hebben gekregen, zoals beschreven in dit artikel, moedigt u deze organisaties aan hun e-mailservers bij te werken zodat ze voldoen aan de moderne beveiligingsstandaarden.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="ea9c0-114">Deze vereisten gelden niet voor het veld gerelateerde afzender (dat wordt gebruikt door Verzenden namens en adressenlijsten).</span><span class="sxs-lookup"><span data-stu-id="ea9c0-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="ea9c0-115">Zie het volgende blogbericht voor meer informatie: Wat betekenen we als we naar de ['afzender'](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)van een e-mailbericht verwijzen?</span><span class="sxs-lookup"><span data-stu-id="ea9c0-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="ea9c0-116">Een overzicht van standaarden voor e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="ea9c0-116">An overview of email message standards</span></span>

<span data-ttu-id="ea9c0-117">Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="ea9c0-118">De envelop met berichten bevat informatie die is vereist voor het verzenden en bezorgen van het bericht tussen SMTP-servers.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="ea9c0-119">De inhoud van het bericht bevat berichtkopvelden (gezamenlijk de berichtkop *genoemd)* en de berichttekst.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="ea9c0-120">De berichtvelop wordt beschreven in [RFC 5321](https://tools.ietf.org/html/rfc5321)en de berichtkop wordt beschreven in [RFC 5322.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="ea9c0-121">Geadresseerden zien de feitelijke berichtvelopop niet, omdat deze wordt gegenereerd door het verzendingsproces voor berichten en niet daadwerkelijk deel uitmaakt van het bericht.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="ea9c0-122">Het adres (ook wel bekend als het `5321.MailFrom` MAIL **FROM-adres,** de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-verzending van het bericht.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="ea9c0-123">Dit e-mailadres wordt  meestal opgenomen in het koptekstveld Retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor het retourpad kan aanwijzen).</span><span class="sxs-lookup"><span data-stu-id="ea9c0-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="ea9c0-124">De afzender (ook wel van-adres of P2-afzender genoemd) is het e-mailadres in het veld Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail clients. </span><span class="sxs-lookup"><span data-stu-id="ea9c0-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="ea9c0-125">Het van-adres heeft de focus op de vereisten in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="ea9c0-126">Het van-adres wordt in detail gedefinieerd voor verschillende RFCs (bijvoorbeeld RFC 5322 secties 3.2.3, 3.4 en 3.4.1 en [RFC 3696).](https://tools.ietf.org/html/rfc3696)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="ea9c0-127">Er zijn veel variaties op adressering en wat wordt beschouwd als geldig of ongeldig.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="ea9c0-128">Om het simpel te houden, raden we de volgende opmaak en definities aan:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="ea9c0-129">**Weergavenaam:** een optionele woordgroep die de eigenaar van het e-mailadres beschrijft.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="ea9c0-130">Het is raadzaam de weergavenaam altijd tussen dubbele aanhalingstekens (") te plaatsen, zoals hier wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="ea9c0-131">Als de weergavenaam een komma bevat, moet u de tekenreeks tussen dubbele aanhalingstekens plaatsen per RFC 5322. </span><span class="sxs-lookup"><span data-stu-id="ea9c0-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="ea9c0-132">Als het Van-adres een weergavenaam bevat, moet de waarde EmailAddress tussen hoekhaken (< >) staan, zoals weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="ea9c0-133">Microsoft raadt u ten zeerste aan om een spatie in te voegen tussen de weergavenaam en het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="ea9c0-134">**EmailAddress:** voor een e-mailadres wordt de notatie `local-part@domain` gebruikt:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="ea9c0-135">**lokaal-onderdeel:** een tekenreeks die het postvak aangeeft dat aan het adres is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="ea9c0-136">Deze waarde is uniek binnen het domein.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-136">This value is unique within the domain.</span></span> <span data-ttu-id="ea9c0-137">Vaak wordt de gebruikersnaam of GUID van de eigenaar van het postvak gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="ea9c0-138">**domein:** de FQDN(Fully Qualified Domain Name) van de e-mailserver die het postvak host dat wordt geïdentificeerd door het lokale gedeelte van het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="ea9c0-139">Dit zijn enkele aanvullende overwegingen voor de waarde van EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="ea9c0-140">Slechts één e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-140">Only one email address.</span></span>
  - <span data-ttu-id="ea9c0-141">Het is raadzaam de haakjes tussen de hoeken niet te scheiden met spaties.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="ea9c0-142">Voeg geen extra tekst na het e-mailadres toe.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="ea9c0-143">Voorbeelden van geldige en ongeldige Van-adressen</span><span class="sxs-lookup"><span data-stu-id="ea9c0-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="ea9c0-144">De volgende Van-e-mailadressen zijn geldig:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="ea9c0-145">`From: < sender@contoso.com >` (Niet aanbevolen omdat er spaties zijn tussen de haakjes en het e-mailadres.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="ea9c0-146">`From: Microsoft 365 <sender@contoso.com>` (Dit wordt niet aanbevolen omdat de weergavenaam niet tussen dubbele aanhalingstekens wordt weergegeven.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="ea9c0-147">De volgende Van-e-mailadressen zijn ongeldig:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="ea9c0-148">**Nee van-adres:** sommige geautomatiseerde berichten bevatten geen Van-adres.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="ea9c0-149">In het verleden, toen Microsoft 365 of Outlook.com een bericht zonder een Van-adres ontving, heeft de service het volgende standaard Van:-adres toegevoegd om het bericht te leveren:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="ea9c0-150">Berichten met een leeg Van-adres worden nu niet meer geaccepteerd.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="ea9c0-151">`From: Microsoft 365 sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres wordt niet tussen haakjes geplaatst.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="ea9c0-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Tekst na het e-mailadres.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="ea9c0-153">`From: Sender, Example <sender.example@contoso.com>` (De weergavenaam bevat een komma, maar staat niet tussen dubbele aanhalingstekens.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="ea9c0-154">`From: "Microsoft 365 <sender@contoso.com>"` (De hele waarde wordt onjuist tussen dubbele aanhalingstekens geplaatst.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="ea9c0-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres wordt niet tussen haakjes geplaatst.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="ea9c0-156">`From: Microsoft 365<sender@contoso.com>` (Geen spatie tussen de weergavenaam en de linkerhoek.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="ea9c0-157">`From: "Microsoft 365"<sender@contoso.com>` (Geen spatie tussen de dubbele aanhalingstekens sluiten en de haak links.)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="ea9c0-158">Automatische antwoorden op uw aangepaste domein onderdrukken</span><span class="sxs-lookup"><span data-stu-id="ea9c0-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="ea9c0-159">U kunt de waarde niet gebruiken om `From: <>` automatische antwoorden te onderdrukken.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="ea9c0-160">In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="ea9c0-161">Automatische antwoorden (en alle antwoorden) worden op natuurlijke wijze onderdrukken omdat er geen gepubliceerd adres is dat de server kan verzenden om berichten naar te verzenden.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="ea9c0-162">Kies een e-maildomein dat geen e-mail kan ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="ea9c0-163">Als uw primaire domein bijvoorbeeld contoso.com is, kunt u noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="ea9c0-164">De Null MX-record voor dit domein bestaat uit één punt.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="ea9c0-165">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ea9c0-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="ea9c0-166">Zie DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het instellen van MX-records.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="ea9c0-167">Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="ea9c0-168">Overschrijven van adres afdwingen</span><span class="sxs-lookup"><span data-stu-id="ea9c0-168">Override From address enforcement</span></span>

<span data-ttu-id="ea9c0-169">Als u de Van-adresvereisten voor inkomende e-mail wilt omzeilen, kunt u de regels voor de toegestane lijst met IP-adressen (verbindingsfilters) of regels voor de e-mailstroom (ook wel transportregels genoemd) gebruiken, zoals wordt beschreven in Lijsten met veilige afzenders maken [in Microsoft 365.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ea9c0-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="ea9c0-170">U kunt de van-adresvereisten niet overschrijven voor uitgaande e-mail die u verzendt vanuit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="ea9c0-171">Daarnaast kan Outlook.com geen enkele vorm van overschrijven toestaan, zelfs niet via ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="ea9c0-172">Andere manieren om cybercriminaliteit te voorkomen en te beschermen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ea9c0-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="ea9c0-173">Zie de tien belangrijkste manieren om microsoft [365](../../admin/security-and-compliance/secure-your-business-data.md)voor bedrijven te beveiligen voor meer informatie over hoe u uw organisatie kunt versterken tegen phishing, spam, gegevensinbreuken en andere bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="ea9c0-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
