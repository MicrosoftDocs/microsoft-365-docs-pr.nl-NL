---
title: Hoe Office 365 het Adres Van valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
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
description: 'Om phishing te voorkomen, vereisen Office 365 en Outlook.com nu RFC-compliance voor From: adressen.'
ms.openlocfilehash: 6459faa22f29017568747b84bbd2935aad6763d1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805694"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="b1e5b-103">Hoe Office 365 het Adres Van valideert om phishing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="b1e5b-104">Office 365 en Outlook.com e-mailaccounts ontvangen een steeds groter aantal phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="b1e5b-105">Een techniek die phishers gebruiken is het verzenden van berichten die waarden hebben voor het Adres dat niet voldoet aan [RFC 5322.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="b1e5b-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="b1e5b-106">Het adres Van: wordt ook wel de 5322.From adres genoemd.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="b1e5b-107">Om dit soort phishing te voorkomen, vereisen Office 365 en Outlook.com berichten die door de service zijn ontvangen om een RFC-compatibel Met: adres zoals beschreven in dit artikel op te nemen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b1e5b-108">De informatie in dit artikel vereist dat u een basiskennis hebt van het algemene formaat van e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="b1e5b-109">Zie Voor meer informatie [rfc 5322](https://tools.ietf.org/html/rfc5322) (met name de punten 3.2.3, 3.4 en 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321)en [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="b1e5b-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="b1e5b-110">Dit artikel gaat over beleidshandhaving voor de 5322.From adres.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="b1e5b-111">Dit artikel gaat niet over de 5321.MailFrom adres.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-111">This article is not about the 5321.MailFrom address.</span></span>

<span data-ttu-id="b1e5b-112">Helaas zijn er nog enkele verouderde e-mailservers op het internet die nog steeds "legitieme" e-mailberichten verzenden die een ontbrekende of misvormde Van: adres hebben.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="b1e5b-113">Als u regelmatig e-mail ontvangt van organisaties die deze verouderde systemen gebruiken, moedigt u deze organisaties aan om hun e-mailservers bij te werken om te voldoen aan moderne beveiligingsnormen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>

<span data-ttu-id="b1e5b-114">Microsoft zal op 9 november 2017 beginnen met de uitrol van de handhaving van het beleid dat in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>

## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="b1e5b-115">Hoe Office 365 het gebruik van een geldige From: adres afdwingt om phishing-aanvallen te voorkomen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="b1e5b-116">Office 365 voert wijzigingen aan in de manier waarop het het gebruik van het From: adres afdwingt in berichten die het ontvangt om u beter te beschermen tegen phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="b1e5b-117">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-117">In this article:</span></span>

- [<span data-ttu-id="b1e5b-118">Alle berichten moeten een geldig Vanaf: adres bevatten</span><span class="sxs-lookup"><span data-stu-id="b1e5b-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)

- [<span data-ttu-id="b1e5b-119">Indeling van het Adres Van als u geen weergavenaam opneemt</span><span class="sxs-lookup"><span data-stu-id="b1e5b-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)

- [<span data-ttu-id="b1e5b-120">Indeling van het Adres Van: als u een weergavenaam opneemt</span><span class="sxs-lookup"><span data-stu-id="b1e5b-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)

- [<span data-ttu-id="b1e5b-121">Aanvullende voorbeelden van geldig en ongeldig Vanaf: adressen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)

- [<span data-ttu-id="b1e5b-122">Automatische antwoorden op uw aangepaste domein onderdrukken zonder het beleid Van:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)

- [<span data-ttu-id="b1e5b-123">Office 365 overschrijven Vanaf: beleid voor adreshandhaving</span><span class="sxs-lookup"><span data-stu-id="b1e5b-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)

- [<span data-ttu-id="b1e5b-124">Andere manieren om cybercriminaliteit in Office 365 te voorkomen en te beschermen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)

<span data-ttu-id="b1e5b-125">Verzenden namens een andere gebruiker wordt niet beïnvloed door deze wijziging, voor meer details, lees Terry Zink's blog "[Wat bedoelen we als we verwijzen naar de 'afzender' van een e-mail?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="b1e5b-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>

### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="b1e5b-126">Alle berichten moeten een geldig Vanaf: adres bevatten</span><span class="sxs-lookup"><span data-stu-id="b1e5b-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="b1e5b-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-127"><a name="MustIncludeFromAddress"> </a></span></span>

<span data-ttu-id="b1e5b-128">Sommige geautomatiseerde berichten bevatten geen Van: adres wanneer ze worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="b1e5b-129">In het verleden, toen Office 365 of Outlook.com een bericht ontvangen zonder een Van: adres, heeft de service de volgende standaard van: adres naar het bericht toegevoegd om het te laten bezorgen:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>

```
From: <>
```

<span data-ttu-id="b1e5b-130">Vanaf 9 november 2017 rolt Office 365 wijzigingen uit in zijn datacenters en e-mailservers, waardoor een nieuwe regel wordt afgedwongen waarbij berichten zonder From: adres niet langer worden geaccepteerd door Office 365 of Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="b1e5b-131">In plaats daarvan moeten alle door Office 365 ontvangen berichten al een geldig Van: adres bevatten.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="b1e5b-132">Anders wordt het bericht verzonden naar de map Ongewenste e-mail of Verwijderde items in Outlook.com en Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span>

### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="b1e5b-133">Syntaxisoverzicht: geldige notatie voor het adres Van voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b1e5b-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="b1e5b-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-134"><a name="SyntaxOverviewFromAddress"> </a></span></span>

<span data-ttu-id="b1e5b-135">De indeling voor de waarde van het Adres Van: wordt in detail gedefinieerd op verschillende RFC's.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="b1e5b-136">Er zijn veel variaties op het aanpakken en wat kan worden beschouwd als geldig of ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="b1e5b-137">Om het eenvoudig te houden, raadt Microsoft u aan de volgende indeling en definities te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>

```
From: "displayname " <emailaddress >
```

<span data-ttu-id="b1e5b-138">Waar:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-138">Where:</span></span>

- <span data-ttu-id="b1e5b-139">(Optioneel)  *displayname* is een woordgroep waarin de eigenaar van het e-mailadres wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="b1e5b-140">Dit kan bijvoorbeeld een gebruiksvriendelijkere naam zijn om de afzender te beschrijven dan de naam van het postvak.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="b1e5b-141">Het gebruik van een weergavenaam is optioneel.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-141">Using a display name is optional.</span></span> <span data-ttu-id="b1e5b-142">Als u er echter voor kiest om een weergavenaam te gebruiken, raadt Microsoft u aan deze altijd in te sluiten binnen aanhalingstekens zoals afgebeeld.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span>

- <span data-ttu-id="b1e5b-143">(Vereist)  *e-mailadres* bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-143">(Required)  *emailaddress*  is made up of:</span></span>

  ```
  local-part @domain
  ```

    <span data-ttu-id="b1e5b-144">Waar:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-144">Where:</span></span>

  - <span data-ttu-id="b1e5b-145">(Vereist)  *lokaal deel* is een tekenreeks die het postvak identificeert dat aan het adres is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="b1e5b-146">Dit is uniek binnen het domein.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-146">This is unique within the domain.</span></span> <span data-ttu-id="b1e5b-147">Vaak wordt de gebruikersnaam of GUID van de postvakeigenaar gebruikt als de waarde voor het lokale gedeelte.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span>

  - <span data-ttu-id="b1e5b-148">(Vereist)  *domein* is de volledig gekwalificeerde domeinnaam (FQDN) van de e-mailserver die het postvak host dat is geïdentificeerd door het lokale deel van het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span>

### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="b1e5b-149">Indeling van het Adres Van als u geen weergavenaam opneemt</span><span class="sxs-lookup"><span data-stu-id="b1e5b-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="b1e5b-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-150"><a name="FormatNoDisplayName"> </a></span></span>

<span data-ttu-id="b1e5b-151">Een goed geformatteerd Van: adres dat geen weergavenaam bevat, bevat slechts één e-mailadres met of zonder hoekhaakjes.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="b1e5b-152">Microsoft raadt u aan de hoekhaakjes niet te scheiden met spaties.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="b1e5b-153">Bovendien, niet iets opnemen na het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-153">In addition, don't include anything after the email address.</span></span>

<span data-ttu-id="b1e5b-154">De volgende voorbeelden zijn geldig:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-154">The following examples are valid:</span></span>

```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="b1e5b-155">Het volgende voorbeeld is geldig, maar wordt niet aanbevolen omdat het spaties bevat tussen de hoekhaakjes en het e-mailadres:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>

```
From: < sender@contoso.com >
```

<span data-ttu-id="b1e5b-156">Het volgende voorbeeld is ongeldig omdat het tekst na het e-mailadres bevat:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-156">The following example is invalid because it contains text after the email address:</span></span>

```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="b1e5b-157">Indeling van het Adres Van: als u een weergavenaam opneemt</span><span class="sxs-lookup"><span data-stu-id="b1e5b-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="b1e5b-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-158"><a name="FormatDisplayName"> </a></span></span>

<span data-ttu-id="b1e5b-159">Voor From: adressen die een waarde voor de weergavenaam bevatten, zijn de volgende regels van toepassing:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>

- <span data-ttu-id="b1e5b-160">Als het afzenderadres een weergavenaam bevat en de weergavenaam een komma bevat, moet de weergavenaam worden ingesloten binnen aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="b1e5b-161">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-161">For example:</span></span>

    <span data-ttu-id="b1e5b-162">Het volgende voorbeeld is geldig:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-162">The following example is valid:</span></span>

  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="b1e5b-163">Het volgende voorbeeld is niet geldig:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-163">The following example is not valid:</span></span>

  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="b1e5b-164">De weergavenaam niet inaanhalingstekens worden bijgesloten als die weergavenaam een komma bevat, is ongeldig volgens RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>

    <span data-ttu-id="b1e5b-165">Als aanbevolen praktijk plaatst u aanhalingstekens rond de weergavenaam, ongeacht of er al dan niet een komma in de weergavenaam is.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>

- <span data-ttu-id="b1e5b-166">Als het afzenderadres een weergavenaam bevat, moet het e-mailadres worden ingesloten binnen hoekhaakjes.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>

    <span data-ttu-id="b1e5b-167">Als aanbevolen praktijk raadt Microsoft u ten zeerste aan een ruimte in te voegen tussen de weergavenaam en het e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="b1e5b-168">Aanvullende voorbeelden van geldig en ongeldig Vanaf: adressen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="b1e5b-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-169"><a name="Examples"> </a></span></span>

- <span data-ttu-id="b1e5b-170">Geldig:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-170">Valid:</span></span>

  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="b1e5b-171">Ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-171">Invalid.</span></span> <span data-ttu-id="b1e5b-172">Het e-mailadres is niet bijgesloten met hoekhaakjes:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-172">The email address is not enclosed with angle brackets:</span></span>

  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="b1e5b-173">Geldig, maar niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-173">Valid, but not recommended.</span></span> <span data-ttu-id="b1e5b-174">De weergavenaam staat niet tussen aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-174">The display name is not in quotes.</span></span> <span data-ttu-id="b1e5b-175">Als beste praktijk, altijd aanhalingstekens rond de weergavenaam:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-175">As a best practice, always put quotation marks around the display name:</span></span>

  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="b1e5b-176">Ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-176">Invalid.</span></span> <span data-ttu-id="b1e5b-177">Alles is ingesloten binnen aanhalingstekens, niet alleen de weergavenaam:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-177">Everything is enclosed within quotation marks, not just the display name:</span></span>

  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="b1e5b-178">Ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-178">Invalid.</span></span> <span data-ttu-id="b1e5b-179">Er zijn geen hoekhaakjes rond het e-mailadres:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-179">There are no angle brackets around the email address:</span></span>

  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="b1e5b-180">Ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-180">Invalid.</span></span> <span data-ttu-id="b1e5b-181">Er is geen ruimte tussen de weergavenaam en de linkerhoek:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-181">There is no space between the display name and left angle bracket:</span></span>

  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="b1e5b-182">Ongeldig.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-182">Invalid.</span></span> <span data-ttu-id="b1e5b-183">Er is geen ruimte tussen het sluitende aanhalingsteken rond de weergavenaam en de linkerhoekbeugel.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>

  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="b1e5b-184">Automatische antwoorden op uw aangepaste domein onderdrukken zonder het beleid Van:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="b1e5b-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-185"><a name="SuppressAutoReply"> </a></span></span>

<span data-ttu-id="b1e5b-186">Met de nieuwe Van: beleidshandhaving kun je \< \> From: niet meer gebruiken om auto-antwoorden te onderdrukken.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="b1e5b-187">In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-187">Instead, you need to set up a null MX record for your custom domain.</span></span>

<span data-ttu-id="b1e5b-188">De MX-record (mail exchanger) is een resourcerecord in DNS die de e-mailserver identificeert die e-mail voor uw domein ontvangt.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="b1e5b-189">Automatische antwoorden (en alle antwoorden) worden natuurlijk onderdrukt omdat er geen gepubliceerd adres is waarop de reagerende server berichten kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>

<span data-ttu-id="b1e5b-190">Wanneer u een null MX-record instelt voor uw aangepaste domein:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-190">When you set up a null MX record for your custom domain:</span></span>

- <span data-ttu-id="b1e5b-191">Kies een domein waaruit u berichten wilt verzenden die geen e-mail accepteren (ontvangen).</span><span class="sxs-lookup"><span data-stu-id="b1e5b-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="b1e5b-192">Als uw primaire domein bijvoorbeeld contoso.com is, u kiezen voor noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="b1e5b-193">Stel de null MX-record voor uw domein in.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="b1e5b-194">Een null MX record bestaat uit een enkele stip, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-194">A null MX record consists of a single dot, for example:</span></span>

  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="b1e5b-195">Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="b1e5b-196">Office 365 overschrijven Vanaf: beleid voor adreshandhaving</span><span class="sxs-lookup"><span data-stu-id="b1e5b-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="b1e5b-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-197"><a name="Override"> </a></span></span>

<span data-ttu-id="b1e5b-198">Nadat de uitrol van het nieuwe beleid is voltooid, u dit beleid alleen omzeilen voor binnenkomende e-mail die u van Office 365 ontvangt met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="b1e5b-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span>

- <span data-ttu-id="b1e5b-199">IP-lijstmet toestaan</span><span class="sxs-lookup"><span data-stu-id="b1e5b-199">IP allow lists</span></span>

- <span data-ttu-id="b1e5b-200">Regels voor de stroomstroom van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1e5b-200">Exchange Online mail flow rules</span></span>

<span data-ttu-id="b1e5b-201">Microsoft raadt ten zeerste aan om de handhaving van het From:-beleid te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="b1e5b-202">Als u dit beleid overschrijft, kan het risico van blootstelling van uw organisatie aan spam, phishing en andere cybercriminaliteit toenemen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>

<span data-ttu-id="b1e5b-203">U dit beleid niet overschrijven voor uitgaande e-mail die u in Office 365 verzendt.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="b1e5b-204">Bovendien staat Outlook.com geen overschrijvingen van welke aard dan ook toe, zelfs niet via ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="b1e5b-205">Andere manieren om cybercriminaliteit in Office 365 te voorkomen en te beschermen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="b1e5b-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="b1e5b-206"><a name="OtherProtection"> </a></span></span>

<span data-ttu-id="b1e5b-207">Zie [Aanbevolen procedures voor beveiliging voor Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)voor meer informatie over hoe u uw organisatie versterken tegen cybercriminaliteit zoals phishing, spam, datalekken en andere bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="b1e5b-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1e5b-208">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b1e5b-208">Related Topics</span></span>

<span data-ttu-id="b1e5b-209">[Backscatter messages and EOP](backscatter-messages-and-eop.md)(Backscatter-berichten en EOP)</span><span class="sxs-lookup"><span data-stu-id="b1e5b-209">[Backscatter messages and EOP](backscatter-messages-and-eop.md)</span></span>
