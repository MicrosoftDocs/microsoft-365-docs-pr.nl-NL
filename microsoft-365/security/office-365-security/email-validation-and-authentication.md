---
title: E-mailverificatie in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Beheerders kunnen meer informatie krijgen over hoe Exchange Online Protection (EOP) e-mailverificatie (SPF, DKIM en DMARC) gebruikt om adresvervalsing, phishing en spam te helpen voorkomen.
ms.openlocfilehash: c79a75f1ae520a0c4f885c923b4a56cdb0f7fb87
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209497"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="0657d-103">E-mailverificatie in EOP</span><span class="sxs-lookup"><span data-stu-id="0657d-103">Email authentication in EOP</span></span>

<span data-ttu-id="0657d-104">E-mailverificatie (ook wel e-mailvalidatie genoemd) is een groep standaarden die probeert om spoofing (e-mailberichten van vervalste afzenders) te stoppen.</span><span class="sxs-lookup"><span data-stu-id="0657d-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="0657d-105">In Microsoft 365-organisaties met postvakken in Exchange Online en zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken worden deze standaarden gebruikt om binnenkomende e-mail te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="0657d-105">In Microsoft 365 organizations with mailboxes in Exchange Online, and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="0657d-106">SPF</span><span class="sxs-lookup"><span data-stu-id="0657d-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="0657d-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="0657d-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="0657d-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="0657d-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="0657d-109">E-mailverificatie verifieert dat e-mailberichten van een afzender (bijvoorbeeld laura@contoso.com) legitiem zijn en afkomstig zijn van verwachte bronnen voor dat e-maildomein (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0657d-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="0657d-110">In de rest van dit artikel wordt uitgelegd hoe deze technologieën werken en hoe EOP ze gebruikt om binnenkomende e-mail te controleren.</span><span class="sxs-lookup"><span data-stu-id="0657d-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="0657d-111">E-mailverificatie gebruiken om spoofing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="0657d-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="0657d-112">DMARC voorkomt spoofing door het **Van**-adres te onderzoeken in berichten (het e-mailadres van de afzender dat gebruikers zien in de e-mailclient).</span><span class="sxs-lookup"><span data-stu-id="0657d-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="0657d-113">Ontvangende e-mailorganisaties kunnen ook controleren of het e-maildomein door SPF of DKIM is geverifieerd, wat betekent dat het domein is geverifieerd en dus niet is vervalst.</span><span class="sxs-lookup"><span data-stu-id="0657d-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span> 

<span data-ttu-id="0657d-114">Het probleem is echter dat SPF-, DKIM- en DMARC-records in DNS voor e-mailverificatie (gezamenlijk bekend als e-mailverificatiebeleid) volledig optioneel zijn.</span><span class="sxs-lookup"><span data-stu-id="0657d-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="0657d-115">Daarom zijn domeinen met een sterk verificatiebeleid zoals microsoft.com en skype.com beschermd tegen adresvervalsing, maar domeinen die een zwakker verificatiebeleid hanteren, of helemaal geen beleid, zijn doelen om te worden vervalst.</span><span class="sxs-lookup"><span data-stu-id="0657d-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="0657d-116">Slechts 9% van de domeinen van bedrijven in de Fortune 500 hanteerde in maart 2018 een sterk e-mailverificatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="0657d-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="0657d-117">De resterende 91% van de bedrijven kan door een kwaadwillende worden gespooft.</span><span class="sxs-lookup"><span data-stu-id="0657d-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="0657d-118">Tenzij er een ander filtermechanisme voor e-mail aanwezig is, kan e-mail van vervalste afzenders in deze domeinen aan gebruikers worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="0657d-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![DMARC-beleid van Fortune 500-bedrijven](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="0657d-120">Het aandeel kleine tot middelgrote bedrijven die niet in de Fortune 500 zitten en die een sterk e-mailverificatiebeleid hanteren is klein en nog kleiner voor domeinen buiten Noord-Amerika en West-Europa.</span><span class="sxs-lookup"><span data-stu-id="0657d-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="0657d-121">Dit is een groot probleem, want hoewel bedrijven zich misschien niet bewust zijn van hoe e-mailverificatie werkt, begrijpen aanvallers het volledig en profiteren ze ervan.</span><span class="sxs-lookup"><span data-stu-id="0657d-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="0657d-122">Omdat phishing zo'n probleem is en vanwege de beperkte acceptatie van een sterk e-mailverificatiebeleid, gebruikt Microsoft *impliciete e-mailverificatie* om inkomende e-mail te controleren.</span><span class="sxs-lookup"><span data-stu-id="0657d-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="0657d-123">Impliciete e-mailverificatie is gebaseerd op een groot aantal uitbreidingen van het reguliere e-mailbeleid.</span><span class="sxs-lookup"><span data-stu-id="0657d-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="0657d-124">Deze extensies bevatten de reputatie van de afzender, de geschiedenis van de afzender, de geschiedenis van de ontvanger, gedragsanalyse en andere geavanceerde technieken.</span><span class="sxs-lookup"><span data-stu-id="0657d-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="0657d-125">Een bericht dat wordt verzonden vanaf een domein dat geen e-mailverificatie hanteert, wordt gemarkeerd als spoof, tenzij het andere kenmerken bevat die aangeven dat het legitiem is.</span><span class="sxs-lookup"><span data-stu-id="0657d-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="0657d-126">Zie [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209) om de algemene aankondiging van Microsoft te lezen.</span><span class="sxs-lookup"><span data-stu-id="0657d-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="0657d-127">Samengestelde verificatie</span><span class="sxs-lookup"><span data-stu-id="0657d-127">Composite authentication</span></span>

<span data-ttu-id="0657d-128">Hoewel SPF, DKIM en DMARC op zichzelf allemaal nuttig zijn, geven ze niet genoeg verificatie-informatie wanneer een bericht geen expliciete verificatierecords heeft.</span><span class="sxs-lookup"><span data-stu-id="0657d-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="0657d-129">Microsoft heeft een algoritme voor impliciete e-mailverificatie ontwikkeld waarin meerdere signalen worden gecombineerd tot één waarde met de naam _samengestelde verificatie_, of compauth.</span><span class="sxs-lookup"><span data-stu-id="0657d-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="0657d-130">De compauth-waarde wordt in de koptekst **verificatie-resultaten** in de berichtkoppen gestempeld.</span><span class="sxs-lookup"><span data-stu-id="0657d-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="0657d-131">Verificatie-resultaten:</span><span class="sxs-lookup"><span data-stu-id="0657d-131">Authentication-Results:</span></span><br/><span data-ttu-id="0657d-132">&nbsp;&nbsp;&nbsp;compauth=\<mislukt | geslaagd | softpass | geen\> reden=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="0657d-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="0657d-133">Deze waarden worden uitgelegd in de [berichtkop Verificatie-resultaten](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="0657d-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="0657d-134">Door de berichtkoppen te bekijken, kunnen beheerders of zelfs eindgebruikers nagaan hoe in Microsoft 365 is vastgesteld dat de afzender is vervalst.</span><span class="sxs-lookup"><span data-stu-id="0657d-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="0657d-135">Waarom e-mailverificatie niet altijd voldoende is om adresvervalsing te stoppen</span><span class="sxs-lookup"><span data-stu-id="0657d-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="0657d-136">Alleen vertrouwen op records voor e-mailverificatie om te bepalen of een inkomend bericht vervalst is, heeft de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="0657d-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="0657d-137">Het verzendende domein heeft mogelijk niet de vereiste DNS-records of de records zijn onjuist geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="0657d-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="0657d-138">Het brondomein heeft correct geconfigureerde DNS-records, maar dat domein komt niet overeen met het domein in het Van-adres.</span><span class="sxs-lookup"><span data-stu-id="0657d-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="0657d-139">SPF en DKIM vereisen niet dat het domein wordt gebruikt in het Van-adres.</span><span class="sxs-lookup"><span data-stu-id="0657d-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="0657d-140">Hackers of legitieme services kunnen een domein registreren, SPF en DKIM configureren voor het domein, een geheel ander domein gebruiken in het Van-adres en dat bericht zal SPF en DKIM passeren.</span><span class="sxs-lookup"><span data-stu-id="0657d-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="0657d-141">Samengestelde verificatie kan deze beperkingen verhelpen door berichten door te geven die anders niet door de e-mailverificatie zouden komen.</span><span class="sxs-lookup"><span data-stu-id="0657d-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="0657d-142">Zoals eerder beschreven, gebruikt impliciete e-mailverificatie meerdere signalen om te bepalen of een bericht legitiem is.</span><span class="sxs-lookup"><span data-stu-id="0657d-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="0657d-143">Voor de eenvoud zijn de volgende voorbeelden gericht op resultaten van e-mailverificatie.</span><span class="sxs-lookup"><span data-stu-id="0657d-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="0657d-144">Andere intelligentiefactoren in de back-end kunnen berichten die e-mailverificatie doorstaan identificeren als vervalst, of berichten die e-mailverificatie niet doorstaan identificeren als legitiem.</span><span class="sxs-lookup"><span data-stu-id="0657d-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="0657d-145">Het domein fabrikam.com heeft bijvoorbeeld geen SPF-, DKIM- of DMARC-records.</span><span class="sxs-lookup"><span data-stu-id="0657d-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="0657d-146">Berichten van afzenders van het fabrikam.com-domein kunnen samengestelde verificatie niet doorstaan (noteer de `compauth`waarde en reden):</span><span class="sxs-lookup"><span data-stu-id="0657d-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="0657d-147">Als fabrikam.com een SPF-record configureert zonder een DKIM-record, kan het bericht samengestelde verificatie doorstaan, omdat het domein dat de SPF heeft doorgegeven, overeenkomt met het domein in het Van-adres:</span><span class="sxs-lookup"><span data-stu-id="0657d-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="0657d-148">Als fabrikam.com een DKIM-record zonder een SPF-record configureert, kan het bericht samengestelde verificatie doorgeven, omdat het domein in de doorgegeven DKIM-handtekening overeenkomt met het domein in het Van-adres:</span><span class="sxs-lookup"><span data-stu-id="0657d-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="0657d-149">Als het domein in SPF of de DKIM-handtekening niet overeenkomt met het domein in het Van-adres, kan het bericht door samengestelde verificatie worden tegengehouden:</span><span class="sxs-lookup"><span data-stu-id="0657d-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="0657d-150">Oplossingen voor legitieme afzenders die niet-geverifieerde e-mail verzenden</span><span class="sxs-lookup"><span data-stu-id="0657d-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="0657d-151">In Microsoft 365 wordt bijgehouden wie niet-geverifieerde e-mail naar uw organisatie verzendt.</span><span class="sxs-lookup"><span data-stu-id="0657d-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="0657d-152">Als de service denkt dat de afzender niet legitiem is, wordt deze gemarkeerd als een samengestelde verificatiefout.</span><span class="sxs-lookup"><span data-stu-id="0657d-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="0657d-153">U kunt dit voorkomen door de aanbevelingen in deze sectie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0657d-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="0657d-154">Configureer e-mailverificatie voor uw domeinen</span><span class="sxs-lookup"><span data-stu-id="0657d-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="0657d-155">U kunt deze methode gebruiken om spoofing binnen organisaties en spoofing tussen domeinen op te lossen in gevallen waarbij u eigenaar bent van of interactie heeft met meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="0657d-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="0657d-156">Het helpt ook adresvervalsing tussen domeinen op te lossen wanneer u naar andere klanten binnen Microsoft 365 verzendt of naar derden die worden gehost door andere providers.</span><span class="sxs-lookup"><span data-stu-id="0657d-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="0657d-157">[SPF-records configureren](set-up-spf-in-office-365-to-help-prevent-spoofing.md) voor uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="0657d-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="0657d-158">[DKIM-records configureren](use-dkim-to-validate-outbound-email.md) voor uw primaire domeinen.</span><span class="sxs-lookup"><span data-stu-id="0657d-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="0657d-159">[U kunt overwegen om DMARC-records in te stellen](use-dmarc-to-validate-email.md) voor uw domein om te bepalen wie uw legitieme afzenders zijn.</span><span class="sxs-lookup"><span data-stu-id="0657d-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="0657d-160">Microsoft biedt geen gedetailleerde implementatierichtlijnen voor SPF-, DKIM-en DMARC-records.</span><span class="sxs-lookup"><span data-stu-id="0657d-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="0657d-161">Er is echter veel informatie online beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0657d-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="0657d-162">Er zijn ook andere bedrijven die uw organisatie kunnen helpen bij het opzetten van e-mailverificatierecords.</span><span class="sxs-lookup"><span data-stu-id="0657d-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="0657d-163">U kent niet alle bronnen voor uw e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="0657d-163">You don't know all sources for your email</span></span>

<span data-ttu-id="0657d-164">Veel domeinen publiceren geen SPF-records omdat ze niet alle e-mailbronnen kennen voor berichten in hun domein.</span><span class="sxs-lookup"><span data-stu-id="0657d-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="0657d-165">Begin met het publiceren van een SPF-record met alle e-mailbronnen die u kent (vooral waar uw zakelijke verkeer zich bevindt) en publiceer het neutrale SPF-beleid `?all`.</span><span class="sxs-lookup"><span data-stu-id="0657d-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="0657d-166">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0657d-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="0657d-167">Dit voorbeeld betekent dat e-mail van uw bedrijfsinfrastructuur e-mailverificatie doorstaat, maar e-mail van onbekende bronnen wordt gemarkeerd als neutraal.</span><span class="sxs-lookup"><span data-stu-id="0657d-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="0657d-168">Microsoft 365 behandelt inkomende e-mail van uw bedrijfsinfrastructuur als geverifieerd, maar e-mail van niet-geïdentificeerde bronnen kan nog steeds als spoof worden gemarkeerd (afhankelijk van of Microsoft 365 het impliciet kan verifiëren).</span><span class="sxs-lookup"><span data-stu-id="0657d-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="0657d-169">Dit is echter nog steeds een verbetering in plaats van dat alle e-mail door Microsoft 365 als spoof wordt gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="0657d-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="0657d-170">Als u eenmaal bent begonnen met een SPF-terugvalbeleid van `?all`, kunt u geleidelijk meer e-mailbronnen voor uw berichten ontdekken en opnemen en vervolgens uw SPF-record bijwerken met een strikter beleid.</span><span class="sxs-lookup"><span data-stu-id="0657d-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="0657d-171">Spoof Intelligence gebruiken om toegestane afzenders van niet-geverifieerde e-mail te configureren</span><span class="sxs-lookup"><span data-stu-id="0657d-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="0657d-172">U kunt [Spoof Intelligence](learn-about-spoof-intelligence.md) ook gebruiken om afzenders toe te staan niet-geverifieerde berichten naar uw organisatie te verzenden.</span><span class="sxs-lookup"><span data-stu-id="0657d-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="0657d-173">Voor externe domeinen is de vervalste gebruiker het domein in het Van-adres, terwijl de verzendende infrastructuur het bron-IP-adres is (onderverdeeld in 24 CIDR-bereiken) of het organisatiedomein van het omgekeerde DNS(PTR)-record.</span><span class="sxs-lookup"><span data-stu-id="0657d-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="0657d-174">In de onderstaande schermafbeelding is het bron-IP-adres mogelijk 131.107.18.4 met het PTR-record outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0657d-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="0657d-175">Dit wordt weergegeven als outlook.com voor de verzendende infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="0657d-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="0657d-176">Om deze afzender toe te staan niet-geverifieerde e-mail te verzenden, wijzigt u **Nee** in **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0657d-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Anti-adresvervalsing instellen voor toegestane afzenders](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="0657d-178">Een vermelding met toestemming maken voor het afzender/geadresseerde-paar</span><span class="sxs-lookup"><span data-stu-id="0657d-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="0657d-179">Zie [Lijsten met veilige afzenders maken in Microsoft 365](create-safe-sender-lists-in-office-365.md) om spamfilters, sommige onderdelen van phish-filters, maar niet malwarefilters voor specifieke afzenders te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="0657d-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="0657d-180">Vraag de afzender om e-mailverificatie te configureren voor domeinen waarvan u niet de eigenaar bent</span><span class="sxs-lookup"><span data-stu-id="0657d-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="0657d-181">Vanwege het probleem van spam en phishing raadt Microsoft e-mailverificatie aan voor alle e-mailorganisaties.</span><span class="sxs-lookup"><span data-stu-id="0657d-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="0657d-182">In plaats van handmatige overschrijvingen in uw organisatie te configureren, kunt u een beheerder in het verzendende domein vragen om hun e-mailverificatierecords te configureren.</span><span class="sxs-lookup"><span data-stu-id="0657d-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="0657d-183">Zelfs als ze in het verleden geen e-mailverificatierecords hoefden te publiceren, zouden ze dit wel moeten doen als ze e-mail naar Microsoft sturen.</span><span class="sxs-lookup"><span data-stu-id="0657d-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="0657d-184">U moet SPF instellen om de verzend-IP-adressen van het domein te publiceren en DKIM (indien beschikbaar) instellen om berichten digitaal te ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="0657d-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="0657d-185">Ze moeten ook overwegen om DMARC-records in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0657d-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="0657d-186">Als ze bulkmailers gebruiken om namens hen e-mail te verzenden, controleer dan of het domein in het Van-adres (als het van hen is) overeenkomt met het domein dat SPF of DMARC doorgeeft.</span><span class="sxs-lookup"><span data-stu-id="0657d-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="0657d-187">Controleer of de volgende locaties (als ze deze gebruiken) zijn opgenomen in het SPF-record:</span><span class="sxs-lookup"><span data-stu-id="0657d-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="0657d-188">On-premises e-mailservers.</span><span class="sxs-lookup"><span data-stu-id="0657d-188">On-premises email servers.</span></span>
  - <span data-ttu-id="0657d-189">E-mail die is verzonden via een software-als-een-service (SaaS)-provider.</span><span class="sxs-lookup"><span data-stu-id="0657d-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="0657d-190">E-mail die is verzonden via een cloudservice (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, enz).</span><span class="sxs-lookup"><span data-stu-id="0657d-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="0657d-191">Voor kleine domeinen die worden gehost door een internetprovider, configureert u de SPF-record volgens hun instructies.</span><span class="sxs-lookup"><span data-stu-id="0657d-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="0657d-192">Hoewel het in het begin misschien moeilijk is om zendende domeinen zo ver te krijgen dat ze verifiëren, zullen ze na verloop van tijd, als er meer en meer e-mailfilters hun e-mail als ongewenst markeren of zelfs afwijzen, de juiste records instellen voor betere aflevering.</span><span class="sxs-lookup"><span data-stu-id="0657d-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="0657d-193">Bovendien kan hun deelname helpen bij het bestrijden van phishing en kan het de mogelijkheid van phishing in hun organisatie of organisaties waarnaar ze e-mail sturen, verminderen.</span><span class="sxs-lookup"><span data-stu-id="0657d-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="0657d-194">Informatie voor infrastructuurproviders (ISP's, ESP's of cloudhostingservices)</span><span class="sxs-lookup"><span data-stu-id="0657d-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="0657d-195">Als u de e-mail van een domein host of een hosting-infrastructuur biedt die e-mail kan verzenden, moet u de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0657d-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="0657d-196">Zorg ervoor dat uw klanten beschikken over de documentatie waarin wordt uitgelegd hoe zij hun SPF-records moeten configureren</span><span class="sxs-lookup"><span data-stu-id="0657d-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="0657d-197">U kunt DKIM-handtekeningen ondertekenen voor uitgaande e-mail, zelfs als de klant deze niet expliciet instelt (met een standaarddomein).</span><span class="sxs-lookup"><span data-stu-id="0657d-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="0657d-198">U kunt zelfs het e-mailbericht met DKIM-handtekeningen dubbel ondertekenen (eenmaal met het domein van de klant als ze het hebben ingesteld, en een tweede keer met de handtekening van de DKIM van uw organisatie).</span><span class="sxs-lookup"><span data-stu-id="0657d-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="0657d-199">Bezorging aan Microsoft is niet gegarandeerd, zelfs niet als u e-mail verifieert die afkomstig is van uw platform, maar het zorgt er in ieder geval voor dat Microsoft uw e-mail niet als spam markeert, omdat deze niet is geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="0657d-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="0657d-200">Zie voor meer informatie over aanbevolen procedures voor serviceproviders [M3AAWG aanbevolen procedures voor mobiele berichten voor serviceproviders](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span><span class="sxs-lookup"><span data-stu-id="0657d-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
