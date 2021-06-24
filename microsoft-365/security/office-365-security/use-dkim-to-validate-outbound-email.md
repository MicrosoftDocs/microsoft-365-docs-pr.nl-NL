---
title: DKIM gebruiken voor e-mail in uw aangepaste domein
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u DKIM (DomainKeys Identified Mail) gebruikt in Microsoft 365 om ervoor te zorgen dat berichten die worden verzonden vanuit uw aangepaste domein worden vertrouwd door de ontvangende e-mailsystemen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9aa3a72a36a146d121c9302a4b6cb126e765671
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082778"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="ac129-103">DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein</span><span class="sxs-lookup"><span data-stu-id="ac129-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ac129-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ac129-104">**Applies to**</span></span>
- [<span data-ttu-id="ac129-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ac129-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ac129-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ac129-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ac129-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac129-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="ac129-108">In dit artikel wordt beschreven hoe u DKIM (DomainKeys Identified Mail) gebruikt in Microsoft 365 om ervoor te zorgen dat de ontvangende e-mailsystemen uitgaande berichten vertrouwen die worden verzonden vanuit uw aangepaste domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-108">This article lists the steps to use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="ac129-109">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="ac129-109">In this article:</span></span>

- [<span data-ttu-id="ac129-110">Hoe DKIM beter werkt dan alleen SPF om schadelijke spoofing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="ac129-110">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [<span data-ttu-id="ac129-111">Stappen om uw 1024-bits sleutels handmatig te upgraden naar 2048-bits DKIM-versleutelingssleutels</span><span class="sxs-lookup"><span data-stu-id="ac129-111">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [<span data-ttu-id="ac129-112">Stappen om handmatig DKIM in te stellen</span><span class="sxs-lookup"><span data-stu-id="ac129-112">Steps to manually set up DKIM</span></span>](#steps-to-manually-set-up-dkim)
- [<span data-ttu-id="ac129-113">Stappen om DKIM te configureren voor meer dan één aangepast domein</span><span class="sxs-lookup"><span data-stu-id="ac129-113">Steps to configure DKIM for more than one custom domain</span></span>](#to-configure-dkim-for-more-than-one-custom-domain)
- [<span data-ttu-id="ac129-114">Het DKIM-handtekeningenbeleid uitschakelen voor een aangepast domein</span><span class="sxs-lookup"><span data-stu-id="ac129-114">Disabling the DKIM signing policy for a custom domain</span></span>](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [<span data-ttu-id="ac129-115">Standaardgedrag voor DKIM en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac129-115">Default behavior for DKIM and Microsoft 365</span></span>](#default-behavior-for-dkim-and-microsoft-365)
- [<span data-ttu-id="ac129-116">DKIM instellen zodat een externe service namens uw aangepaste domein e-mails kan verzenden of spoofen</span><span class="sxs-lookup"><span data-stu-id="ac129-116">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [<span data-ttu-id="ac129-117">Volgende stappen: nadat u DKIM hebt ingesteld voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac129-117">Next steps: After you set up DKIM for Microsoft 365</span></span>](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> <span data-ttu-id="ac129-118">In Microsoft 365 wordt DKIM automatisch ingesteld voor de oorspronkelijke 'onmicrosoft.com'-domeinen.</span><span class="sxs-lookup"><span data-stu-id="ac129-118">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="ac129-119">Dat betekent dat u niets hoeft te doen om DKIM in te stellen voor enige oorspronkelijke domeinnaam (bijvoorbeeld litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="ac129-119">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="ac129-120">Zie [Veelgestelde vragen over domeinen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain) voor meer informatie over domeinen.</span><span class="sxs-lookup"><span data-stu-id="ac129-120">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="ac129-121">DKIM is een van de drie verschillende verificatiemethoden (SPF, DKIM en DMARC) die helpen voorkomen dat spoofers berichten verzenden die afkomstig lijken te zijn van uw domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-121">DKIM is one of the trio of Authentication methods (SPF, DKIM and DMARC) that help prevent attackers from sending messages that look like they come from your domain.</span></span>

<span data-ttu-id="ac129-122">Met DKIM kunt u een digitale handtekening toevoegen aan uitgaande e-mailberichten in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="ac129-122">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="ac129-123">Wanneer u DKIM configureert, geeft u uw domein toestemming om de domeinnaam aan een e-mailbericht te koppelen met behulp van cryptografische verificatie. Een soort handtekening van uw domein dus.</span><span class="sxs-lookup"><span data-stu-id="ac129-123">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message using cryptographic authentication.</span></span> <span data-ttu-id="ac129-124">E-mailsystemen die e-mail vanaf uw domein ontvangen, kunnen deze digitale handtekening gebruiken om te bepalen of de inkomende e-mail echt is.</span><span class="sxs-lookup"><span data-stu-id="ac129-124">Email systems that get email from your domain can use this digital signature to help verify whether incoming email is legitimate.</span></span>

<span data-ttu-id="ac129-125">In de basis wordt met een persoonlijke sleutel de kop in de uitgaande e-mail van een domein versleuteld.</span><span class="sxs-lookup"><span data-stu-id="ac129-125">In basic, a private key encrypts the header in a domain's outgoing email.</span></span> <span data-ttu-id="ac129-126">De openbare sleutel wordt gepubliceerd naar de DNS-records van het domein die vervolgens door ontvangende servers wordt gebruikt om de handtekening te decoderen.</span><span class="sxs-lookup"><span data-stu-id="ac129-126">The public key is published in the domain's DNS records, and receiving servers can use that key to decode the signature.</span></span> <span data-ttu-id="ac129-127">Met DKIM-verificatie kunnen de ontvangende servers controleren of de e-mail echt afkomstig is van uw domein en niet van iemand die aan *adresvervalsing* van uw domein doet (spoofing).</span><span class="sxs-lookup"><span data-stu-id="ac129-127">DKIM verification helps the receiving servers confirm the mail is really coming from your domain and not someone *spoofing* your domain.</span></span>

> [!TIP]
><span data-ttu-id="ac129-p104">U kunt er ook voor kiezen om niets te doen met DKIM voor uw aangepaste domein. Als u geen DKIM voor uw aangepaste domein instelt, maakt Microsoft 365 een persoonlijk en openbare sleutelpaar en wordt DKIM-ondertekening ingeschakeld. Vervolgens wordt het standaardbeleid van Microsoft 365 voor uw aangepaste domein geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="ac129-p104">You can choose to do nothing about DKIM for your custom domain too. If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span>

 <span data-ttu-id="ac129-p105">De ingebouwde DKIM-configuratie van Microsoft 365 is voldoende voor de meeste klanten. U moet echter de DKIM voor uw aangepaste domein handmatig configureren in de volgende gevallen:</span><span class="sxs-lookup"><span data-stu-id="ac129-p105">Microsoft-365's built-in DKIM configuration is sufficient coverage for most customers. However, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="ac129-132">U hebt meer dan één aangepast domein in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac129-132">You have more than one custom domain in Microsoft 365</span></span>
- <span data-ttu-id="ac129-133">U wilt ook DMARC instellen (**aanbevolen**)</span><span class="sxs-lookup"><span data-stu-id="ac129-133">You're going to set up DMARC too (**recommended**)</span></span>
- <span data-ttu-id="ac129-134">U wilt controle over uw persoonlijke sleutel</span><span class="sxs-lookup"><span data-stu-id="ac129-134">You want control over your private key</span></span>
- <span data-ttu-id="ac129-135">U wilt de CNAME-records aanpassen</span><span class="sxs-lookup"><span data-stu-id="ac129-135">You want to customize your CNAME records</span></span>
- <span data-ttu-id="ac129-136">U wilt DKIM-sleutels instellen voor e-mail die afkomstig is van een extern domein, bijvoorbeeld als u bulkmails via een derde verzendt.</span><span class="sxs-lookup"><span data-stu-id="ac129-136">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="ac129-137">Hoe DKIM beter werkt dan alleen SPF om schadelijke spoofing te voorkomen</span><span class="sxs-lookup"><span data-stu-id="ac129-137">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="ac129-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-138"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="ac129-139">Met SPF worden er gegevens aan een berichtenenvelop toegevoegd, maar met DKIM wordt een handtekening in de berichtkop *versleuteld*.</span><span class="sxs-lookup"><span data-stu-id="ac129-139">SPF adds information to a message envelope but DKIM *encrypts* a signature within the message header.</span></span> <span data-ttu-id="ac129-140">Wanneer u een bericht doorstuurt, kunnen gedeelten van die berichtenenvelop door de doorsturende server worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ac129-140">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="ac129-141">Aangezien de digitale handtekening bij het e-mailbericht blijft, omdat deze namelijk deel uitmaakt van de e-mailberichtkop, werkt DKIM zelfs als een bericht is doorgestuurd, zoals weergegeven in het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ac129-141">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagram met een doorgestuurde bericht waarbij de DKIM-verificatie lukt terwijl de SPF-controle mislukt](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="ac129-143">Als u in dit voorbeeld slechts een TXT-record voor SPF had gepubliceerd voor uw domein kon de ontvangende e-mailserver uw e-mail als spam hebben gemarkeerd en een fout-positief resultaat hebben gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="ac129-143">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="ac129-144">**Met het toevoegen van DKIM in dit scenario wordt het aantal *fout-positieve* spammeldingen beperkt.**</span><span class="sxs-lookup"><span data-stu-id="ac129-144">**The addition of DKIM in this scenario reduces *false positive* spam reporting.**</span></span> <span data-ttu-id="ac129-145">Omdat DKIM gebruikmaakt van de cryptografie van een openbare sleutel om te verifiëren en niet alleen van IP-adressen, wordt DKIM als een veel sterkere verificatievorm dan SPF beschouwd.</span><span class="sxs-lookup"><span data-stu-id="ac129-145">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="ac129-146">Wij raden u aan om in uw implementatie SPF en DKIM te gebruiken, evenals DMARC.</span><span class="sxs-lookup"><span data-stu-id="ac129-146">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

> [!TIP]
> <span data-ttu-id="ac129-147">DKIM gebruikt een persoonlijke sleutel om een versleutelde handtekening in de berichtkoppen in te voegen.</span><span class="sxs-lookup"><span data-stu-id="ac129-147">DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="ac129-148">Het ondertekenende of uitgaande domein wordt in de kop ingevoegd als de waarde van het veld **d=**.</span><span class="sxs-lookup"><span data-stu-id="ac129-148">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="ac129-149">Het verifiërende of ontvangende domein gebruikt vervolgens het veld **d=** om de openbare sleutel uit DNS te zoeken en het bericht te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="ac129-149">The verifying domain, or recipient's domain, then uses the **d=** field to look up the public key from DNS, and authenticate the message.</span></span> <span data-ttu-id="ac129-150">Als het bericht is geverifieerd, is de DKIM-controle gelukt.</span><span class="sxs-lookup"><span data-stu-id="ac129-150">If the message is verified, the DKIM check passes.</span></span>


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="ac129-151">Uw 1024-bits sleutels handmatig upgraden naar 2048-bits DKIM-versleutelingssleutels</span><span class="sxs-lookup"><span data-stu-id="ac129-151">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="ac129-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-152"><a name="1024to2048DKIM"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="ac129-153">In Microsoft 365 wordt DKIM automatisch ingesteld voor *onmicrosoft.com*-domeinen.</span><span class="sxs-lookup"><span data-stu-id="ac129-153">Microsoft 365 automatically sets up DKIM for *onmicrosoft.com* domains.</span></span> <span data-ttu-id="ac129-154">Er zijn geen stappen nodig om DKIM te gebruiken voor initiële domeinnamen (zoals litware.*onmicrosoft.com*).</span><span class="sxs-lookup"><span data-stu-id="ac129-154">No steps are needed to use DKIM for any initial domain names (like litware.*onmicrosoft.com*).</span></span> <span data-ttu-id="ac129-155">Zie [Veelgestelde vragen over domeinen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain) voor meer informatie over domeinen.</span><span class="sxs-lookup"><span data-stu-id="ac129-155">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="ac129-156">Aangezien zowel 1024- als 2048-bits voor DKIM-sleutels worden ondersteund, wordt in deze instructies uitgelegd hoe je de 1024-bits sleutel upgradet naar 2048-bits in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac129-156">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048 in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ac129-157">De onderstaande stappen zijn voor twee gebruikscases: kies de optie die het geschiktst is voor jouw configuratie.</span><span class="sxs-lookup"><span data-stu-id="ac129-157">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

- <span data-ttu-id="ac129-158">Wanneer je **DKIM al hebt geconfigureerd**, wijzig je de hoeveelheid bits als volgt:</span><span class="sxs-lookup"><span data-stu-id="ac129-158">When you **already have DKIM configured**, you rotate bitness by running the following command:</span></span>

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  <span data-ttu-id="ac129-159">**of**</span><span class="sxs-lookup"><span data-stu-id="ac129-159">**or**</span></span>

- <span data-ttu-id="ac129-160">Voer voor een **nieuwe implementatie van DKIM** de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="ac129-160">For a **new implementation of DKIM**, run the following command:</span></span>

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

<span data-ttu-id="ac129-161">Blijf verbonden met Exchange Online PowerShell om de configuratie te *controleren* door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="ac129-161">Stay connected to Exchange Online PowerShell to *verify* the configuration by running the following command:</span></span>

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> <span data-ttu-id="ac129-162">Deze nieuwe 2048-bits sleutel wordt gebruikt vanaf RotateOnDate en verzendt in de tussentijd e-mails met de 1024-bits sleutel.</span><span class="sxs-lookup"><span data-stu-id="ac129-162">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="ac129-163">Na vier dagen kunt u opnieuw testen met de 2048-bits sleutel (dat wil zeggen, wanneer de wijziging wordt toegepast op de tweede kiezer).</span><span class="sxs-lookup"><span data-stu-id="ac129-163">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="ac129-164">Als u de tweede kiezer wilt wijzigen, kunt u kiezen uit a) de Microsoft 365-service de kiezer laten wijzigen en upgraden naar 2048-bits binnen de komende zes maanden of b) na 4 dagen en bevestigen dat 2048-bits wordt gebruikt, de tweede kiezer handmatig wijzigen met gebruik van de geschikte hierboven vermelde cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ac129-164">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

<span data-ttu-id="ac129-165">Zie de volgende artikelen voor gedetailleerde syntaxis- en parameterinformatie: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) en [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span><span class="sxs-lookup"><span data-stu-id="ac129-165">For detailed syntax and parameter information, see the following articles: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig), and [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span></span>

## <a name="steps-to-manually-set-up-dkim"></a><span data-ttu-id="ac129-166">Stappen die u moet uitvoeren om DKIM handmatig in te stellen</span><span class="sxs-lookup"><span data-stu-id="ac129-166">Steps to manually set up DKIM</span></span>
<span data-ttu-id="ac129-167"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-167"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="ac129-168">Als u DKIM wilt configureren, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ac129-168">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="ac129-169">Twee CNAME-records voor uw aangepaste domein in DNS publiceren</span><span class="sxs-lookup"><span data-stu-id="ac129-169">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [<span data-ttu-id="ac129-170">DKIM-ondertekening voor uw aangepaste domein inschakelen</span><span class="sxs-lookup"><span data-stu-id="ac129-170">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="ac129-171">Twee CNAME-records voor uw aangepaste domein in DNS publiceren</span><span class="sxs-lookup"><span data-stu-id="ac129-171">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="ac129-172"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-172"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="ac129-173">U moet twee CNAME-records publiceren voor elk domein waarvoor u een DKIM-handtekening wilt toevoegen in DNS.</span><span class="sxs-lookup"><span data-stu-id="ac129-173">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="ac129-174">Als je nog niet het hele artikel hebt gelezen, heb je deze tijdbesparende PowerShell-verbindingsinformatie misschien gemist: [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac129-174">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="ac129-175">Voer de volgende opdrachten uit in Exchange Online PowerShell om de selectorrecords te maken:</span><span class="sxs-lookup"><span data-stu-id="ac129-175">Run the following commands in Exchange Online PowerShell to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="ac129-176">Als u behalve het oorspronkelijke domein in Microsoft 365 ook aangepaste domeinen hebt ingericht, moet u twee CNAME-records publiceren voor elk extra domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-176">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="ac129-177">Als u dus twee domeinen hebt, moet u twee extra CNAME-records publiceren, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="ac129-177">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="ac129-178">Gebruik de volgende notatie voor de CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="ac129-178">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac129-179">Als u een van onze GCC High-klanten bent, wordt _domainGuid_ anders berekend!</span><span class="sxs-lookup"><span data-stu-id="ac129-179">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="ac129-180">In plaats van de MX-record voor uw _initialDomain_ te zoeken, kunt u de _domainGuid_ berekenen. In plaats daarvan berekenen wij dit rechtstreeks vanuit het aangepaste domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-180">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="ac129-181">Als uw aangepaste domein bijvoorbeeld 'contoso.com' is, wordt de domainGuid 'contoso-com': alle punten worden vervangen door een streepje.</span><span class="sxs-lookup"><span data-stu-id="ac129-181">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="ac129-182">Ongeacht de MX-record waarnaar uw initialDomain wijst, gebruikt u altijd de bovenstaande methode om de domainGuid te berekenen die u wilt gebruiken in de CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="ac129-182">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="ac129-183">Waarbij:</span><span class="sxs-lookup"><span data-stu-id="ac129-183">Where:</span></span>

- <span data-ttu-id="ac129-184">Voor Microsoft 365 de kiezers altijd 'kiezer1' of 'kiezer2' is.</span><span class="sxs-lookup"><span data-stu-id="ac129-184">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>
- <span data-ttu-id="ac129-185">_domainGUID_ is dezelfde als de _domainGUID_ in de aangepaste MX-record voor uw aangepaste domein dat vóór mail.protection.outlook.com wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ac129-185">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="ac129-186">In de volgende MX-record voor het domein contoso.com, is de _domainGUID_ bijvoorbeeld contoso-com:</span><span class="sxs-lookup"><span data-stu-id="ac129-186">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="ac129-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac129-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="ac129-189">_initialDomain_ is het domein dat u hebt gebruikt toen u zich aanmeldde voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac129-189">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="ac129-190">Oorspronkelijke domeinen moeten altijd eindigen op onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ac129-190">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="ac129-191">Zie [Veelgestelde vragen over domeinen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain)voor meer informatie over het bepalen van uw oorspronkelijke domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-191">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="ac129-192">Als u bijvoorbeeld het oorspronkelijk domein cohovineyardandwinery.onmicrosoft.com hebt en twee aangepaste domeinen cohovineyard.com en cohowinery.com, moet u twee CNAME-records instellen voor elk extra domein: dus een totaal van vier CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="ac129-192">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="ac129-193">Het is belangrijk om de tweede record te maken, maar mogelijk is slechts één van de kiezers beschikbaar op het moment dat het bestand wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ac129-193">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="ac129-194">In wezen kan de tweede kiezer verwijzen naar een adres dat nog niet is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ac129-194">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="ac129-195">We raden u niettemin aan om de tweede CNAME-record te maken, omdat de sleutelrotatie dan probleemloos zal verlopen.</span><span class="sxs-lookup"><span data-stu-id="ac129-195">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="ac129-196">Stappen om DKIM-ondertekening voor uw aangepaste domein in te schakelen</span><span class="sxs-lookup"><span data-stu-id="ac129-196">Steps to enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="ac129-197"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-197"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="ac129-198">Als u de CNAME-records in DNS hebt gepubliceerd, kunt u DKIM-ondertekening inschakelen via Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac129-198">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="ac129-199">U kunt dit doen via het Microsoft 365-beheercentrum of met behulp van Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac129-199">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="ac129-200">DKIM-ondertekening inschakelen voor uw aangepaste domein in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="ac129-200">To enable DKIM signing for your custom domain in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="ac129-201">Open de Microsoft 365 Defender-portal [met uw werk- of schoolaccount](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="ac129-201">Open the Microsoft 365 Defender portal [using your work or school account](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ac129-202">Ga naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> **de sectie Regels** \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="ac129-202">Go to **Email & Collaboration** \> **Policies & rules** \> **Threat policies** \> **Rules** section \> **DKIM**.</span></span> <span data-ttu-id="ac129-203">Of gebruik <https://security.microsoft.com/dkimv2> om rechtstreeks naar de DKIM-pagina te gaan.</span><span class="sxs-lookup"><span data-stu-id="ac129-203">Or, to go directly to the DKIM page, use <https://security.microsoft.com/dkimv2>.</span></span>

3. <span data-ttu-id="ac129-204">Selecteer op de pagina **DKIM** het domein door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="ac129-204">On the **DKIM** page, select the domain by clicking on the name.</span></span>

4. <span data-ttu-id="ac129-205">In de flyout met details die wordt weergegeven, wijzigt u de instelling **Berichten voor dit domein ondertekenen met DKIM-handtekeningen** in **Ingeschakeld** (![Wisselknop aan](../../media/scc-toggle-on.png))</span><span class="sxs-lookup"><span data-stu-id="ac129-205">In the details flyout that appears, chang the **Sign messages for this domain with DKIM signatures** setting to **Enabled** (![Toggle on](../../media/scc-toggle-on.png))</span></span>

   <span data-ttu-id="ac129-206">Wanneer u klaar bent, klikt u op **DKIM-sleutels draaien**.</span><span class="sxs-lookup"><span data-stu-id="ac129-206">When you're finished, click **Rotate DKIM keys**.</span></span>

5. <span data-ttu-id="ac129-207">Herhaal deze stap voor elk aangepast domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-207">Repeat these step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="ac129-208">DKIM-ondertekening voor uw aangepaste domein inschakelen met behulp van Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac129-208">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="De 'geen DKIM-sleutels opgeslagen voor dit domein'-fout.":::
> <span data-ttu-id="ac129-210">Als u DKIM voor de eerste keer configureert en de fout 'Geen DKIM-sleutels opgeslagen voor dit domein' ziet, voltooit u de opdracht in stap 2 hieronder (bijvoorbeeld `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) om de sleutel te zien.</span><span class="sxs-lookup"><span data-stu-id="ac129-210">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain' complete the command in step 2 below (for example, `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) to see the key.</span></span>

1. <span data-ttu-id="ac129-211">[Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac129-211">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ac129-212">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac129-212">Use the following syntax:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   <span data-ttu-id="ac129-213">\<Domain\> is de naam van het aangepaste domein waarvoor u DKIM-ondertekening wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="ac129-213">\<Domain\> is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="ac129-214">In dit voorbeeld wordt DKIM-ondertekening ingeschakeld voor het domein contoso.com:</span><span class="sxs-lookup"><span data-stu-id="ac129-214">This example enables DKIM signing for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="ac129-215">Om te bevestigen dat DKIM-ondertekening correct is geconfigureerd voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac129-215">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="ac129-216">Wacht een paar minuten voordat u deze stappen uitvoert om te bevestigen dat u de DKIM correct hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="ac129-216">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="ac129-217">Dit zorgt ervoor dat de DKIM-informatie over het domein wordt verspreid in het hele netwerk.</span><span class="sxs-lookup"><span data-stu-id="ac129-217">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="ac129-218">Verzend een bericht vanuit een account in uw Microsoft 365-domein met ingeschakelde DKIM naar een ander e-mailaccount, zoals outlook.com of Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="ac129-218">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
- <span data-ttu-id="ac129-219">Gebruik geen aol.com-account voor testdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="ac129-219">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="ac129-220">AOL kan de DKIM-controle overslaan als de SPF-controle slaagt.</span><span class="sxs-lookup"><span data-stu-id="ac129-220">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="ac129-221">De test wordt hierdoor zinloos.</span><span class="sxs-lookup"><span data-stu-id="ac129-221">This will nullify your test.</span></span>
- <span data-ttu-id="ac129-222">Open het bericht en bekijk de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="ac129-222">Open the message and look at the header.</span></span> <span data-ttu-id="ac129-223">De instructies voor het bekijken van berichtkop tekst kan variëren afhankelijk van uw e-mailclient.</span><span class="sxs-lookup"><span data-stu-id="ac129-223">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="ac129-224">Voor instructies over het bekijken van berichtkoppen in Outlook, raadpleegt u [Internetberichtkoppen bekijken in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="ac129-224">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="ac129-p123">Het DKIM-ondertekend bericht bevat de host- en domeinnaam die u hebt gedefinieerd toen u de CNAME-gegevens publiceerde. Het bericht ziet er ongeveer uit zoals dit voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ac129-p123">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="ac129-227">Zoek naar de berichtkop Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="ac129-227">Look for the Authentication-Results header.</span></span> <span data-ttu-id="ac129-228">Hoewel elke ontvangende service een iets andere notatie gebruikt om de binnenkomende e-mail te stempelen, moet het resultaat iets bevatten zoals **DKIM = Pass** of **DKIM = OK**.</span><span class="sxs-lookup"><span data-stu-id="ac129-228">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="ac129-229">DKIM configureren voor meer dan één aangepast domein</span><span class="sxs-lookup"><span data-stu-id="ac129-229">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="ac129-230"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-230"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="ac129-231">Als u in de toekomst besluit om een ander aangepast domein toe te voegen en u wilt DKIM inschakelen voor het nieuwe domein, moet u de stappen in dit artikel voor elk domein voltooien.</span><span class="sxs-lookup"><span data-stu-id="ac129-231">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="ac129-232">Voer met name alle stappen uit in [Wat u moet doen om DKIM handmatig in te stellen](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="ac129-232">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="ac129-233">Het DKIM-handtekeningenbeleid uitschakelen voor een aangepast domein</span><span class="sxs-lookup"><span data-stu-id="ac129-233">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="ac129-234"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-234"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="ac129-235">Als u het handtekeningenbeleid uitschakelt, wordt DKIM niet volledig uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac129-235">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="ac129-236">Na een bepaalde tijd zal Microsoft 365 automatisch het standaardbeleid toepassen op uw domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-236">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="ac129-237">Zie [Standaardgedrag voor DKIM en Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ac129-237">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="ac129-238">Het DKIM-handtekeningenbeleid uitschakelen met behulp van Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac129-238">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="ac129-239">[Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac129-239">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ac129-240">Voer een van de volgende opdrachten uit voor elk domein waarvoor u DKIM-ondertekening wilt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ac129-240">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="ac129-241">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ac129-241">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="ac129-242">Of</span><span class="sxs-lookup"><span data-stu-id="ac129-242">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="ac129-243">Hierbij is _nummer_ de index van het beleid.</span><span class="sxs-lookup"><span data-stu-id="ac129-243">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="ac129-244">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ac129-244">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="ac129-245">Standaardgedrag voor DKIM en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac129-245">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="ac129-246"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-246"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="ac129-247">Als u DKIM niet inschakelt, maakt Microsoft 365 automatisch een 1024-bits openbare sleutel voor uw standaarddomein en de bijbehorende persoonlijke sleutel die we intern opslaan in ons datacenter.</span><span class="sxs-lookup"><span data-stu-id="ac129-247">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="ac129-248">In Microsoft 365 wordt een standaardconfiguratie voor handtekeningen gebruikt voor domeinen die geen beleid hebben.</span><span class="sxs-lookup"><span data-stu-id="ac129-248">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="ac129-249">Dit betekent dat als u DKIM niet zelf instelt, Microsoft 365 gebruikmaakt van het standaardbeleid en de bijbehorende sleutels die daarvoor worden gemaakt, zodat DKIM voor uw domein wordt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac129-249">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="ac129-250">Als u bovendien DKIM-ondertekening uitschakelt nadat u deze hebt ingeschakeld, wordt er in Microsoft 365 na een bepaalde periode automatisch het standaardbeleid toegepast op uw domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-250">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="ac129-251">Stel dat in het volgende voorbeeld DKIM voor fabrikam.com is ingeschakeld door Microsoft 365 en niet door de beheerder van het domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-251">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="ac129-252">Dit betekent dat de vereiste CNAME's niet aanwezig zijn in DNS.</span><span class="sxs-lookup"><span data-stu-id="ac129-252">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="ac129-253">DKIM-handtekeningen voor e-mail van dit domein zullen er ongeveer zo uitzien:</span><span class="sxs-lookup"><span data-stu-id="ac129-253">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="ac129-254">In dit voorbeeld bevatten de hostnaam en het domein de waarden waarnaar de CNAME zou wijzen als DKIM-ondertekening voor fabrikam.com door de domeinbeheerder was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac129-254">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="ac129-255">Uiteindelijk wordt elk bericht dat wordt verzonden vanuit Microsoft 365 DKIM-ondertekend.</span><span class="sxs-lookup"><span data-stu-id="ac129-255">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="ac129-256">Als u DKIM zelf inschakelt, is het domein hetzelfde als het domein in het Van:-adres, in dit geval fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ac129-256">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="ac129-257">Als u dit niet doet, wordt het niet afgestemd en wordt in plaats daarvan het oorspronkelijke domein van uw organisatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ac129-257">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="ac129-258">Zie [Veelgestelde vragen over domeinen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain)voor meer informatie over het bepalen van uw oorspronkelijke domein.</span><span class="sxs-lookup"><span data-stu-id="ac129-258">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="ac129-259">DKIM instellen zodat een externe service namens uw aangepaste domein e-mails kan verzenden of spoofen</span><span class="sxs-lookup"><span data-stu-id="ac129-259">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="ac129-260"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-260"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="ac129-261">Bij sommige providers voor bulkmail, of providers van software-als-een-service, kunt u DKIM-sleutels instellen voor e-mail die afkomstig is van hun service.</span><span class="sxs-lookup"><span data-stu-id="ac129-261">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="ac129-262">Hiervoor is coördinatie tussen uzelf en de derde partij nodig om de vereiste DNS-records in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ac129-262">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="ac129-263">Sommige servers van derden kunnen eigen CNAME-records met verschillende Select-records hebben.</span><span class="sxs-lookup"><span data-stu-id="ac129-263">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="ac129-264">Er zijn er geen twee organisaties die dit op precies dezelfde manier doen.</span><span class="sxs-lookup"><span data-stu-id="ac129-264">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="ac129-265">In plaats daarvan hangt het proces volledig af van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="ac129-265">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="ac129-266">Een voorbeeldbericht met een correct geconfigureerde DKIM voor contoso.com en bulkemailprovider.com kan er als volgt uitzien:</span><span class="sxs-lookup"><span data-stu-id="ac129-266">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="ac129-267">In dit voorbeeld, om dit resultaat te bereiken, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="ac129-267">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="ac129-268">De Provider voor bulkmail heeft Contoso een openbare DKIM-sleutel gegeven.</span><span class="sxs-lookup"><span data-stu-id="ac129-268">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="ac129-269">Contoso heeft de DKIM-sleutel gepubliceerd naar de bijbehorende DNS-record.</span><span class="sxs-lookup"><span data-stu-id="ac129-269">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="ac129-270">Bij het verzenden van e-mail ondertekent de provider voor bulkmail met de bijbehorende persoonlijke sleutel.</span><span class="sxs-lookup"><span data-stu-id="ac129-270">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="ac129-271">Hiermee heeft de provider voor bulkmail de DKIM-handtekening toegevoegd aan de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="ac129-271">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="ac129-272">Bij de ontvangende e-mailsystemen wordt een DKIM-controle uitgevoerd door de waarde d =\<domain\> van de DKIM-handtekening te verifiëren ten opzichte van het domein in het Van:-adres (5322.From) van het bericht.</span><span class="sxs-lookup"><span data-stu-id="ac129-272">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="ac129-273">In dit voorbeeld komen de waarden overeen:</span><span class="sxs-lookup"><span data-stu-id="ac129-273">In this example, the values match:</span></span>

   > <span data-ttu-id="ac129-274">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="ac129-274">sender@**contoso.com**</span></span>

   > <span data-ttu-id="ac129-275">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="ac129-275">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="ac129-276">Domeinen identificeren die geen e-mail verzenden</span><span class="sxs-lookup"><span data-stu-id="ac129-276">Identify domains that do not send email</span></span>

<span data-ttu-id="ac129-277">Organisaties moeten het duidelijk aangeven als een domein geen e-mail verzendt, door `v=DKIM1; p=` op te geven in de DKIM-record voor die domeinen.</span><span class="sxs-lookup"><span data-stu-id="ac129-277">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="ac129-278">Dit geeft aan ontvangende e-mailservers aan dat er geen geldige openbare sleutels zijn voor het domein en e-mails die beweren van dat domein afkomstig te zijn, moeten worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="ac129-278">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="ac129-279">U moet dit voor elk domein en subdomein doen met een DKIM met jokerteken.</span><span class="sxs-lookup"><span data-stu-id="ac129-279">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="ac129-280">De DKIM-record zou er bijvoorbeeld als volgt uitzien:</span><span class="sxs-lookup"><span data-stu-id="ac129-280">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="ac129-281">Volgende stappen: nadat u DKIM hebt ingesteld voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac129-281">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="ac129-282"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="ac129-282"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="ac129-283">Hoewel DKIM is bedoeld om spoofing te voorkomen, werkt DKIM beter met SPF en DMARC.</span><span class="sxs-lookup"><span data-stu-id="ac129-283">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="ac129-284">Als u DKIM hebt ingesteld, maar u hebt SPF nog niet ingesteld, moet u dat zeker doen.</span><span class="sxs-lookup"><span data-stu-id="ac129-284">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="ac129-285">Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ac129-285">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="ac129-286">Voor een beter begrip van hoe Microsoft 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ac129-286">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="ac129-287">Zie vervolgens [DMARC gebruiken om e-mail te valideren](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="ac129-287">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="ac129-288">[Antispamberichtkoppen](anti-spam-message-headers.md) bevatten de syntaxis en koptekstvelden die door Microsoft 365 worden gebruikt voor DKIM-controles.</span><span class="sxs-lookup"><span data-stu-id="ac129-288">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="ac129-289">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="ac129-289">More information</span></span>

<span data-ttu-id="ac129-290">Sleutelrotatie via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span><span class="sxs-lookup"><span data-stu-id="ac129-290">Key rotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
