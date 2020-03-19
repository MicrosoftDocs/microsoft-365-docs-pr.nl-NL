---
title: Niet-geverifieerde afzender
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Om te voorkomen dat phishingberichten uw postvak bereiken, controleren Outlook.com en Outlook op het web of de afzender is wie ze zeggen dat ze zijn en markeren ze verdachte berichten als ongewenste e-mail.
ms.openlocfilehash: 513a45594dd41db56abe143ea6edca7074539d2f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806302"
---
# <a name="unverified-sender"></a><span data-ttu-id="533f5-103">Niet-geverifieerde afzender</span><span class="sxs-lookup"><span data-stu-id="533f5-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="533f5-104">Deze updates worden nu uitgerold en zijn mogelijk niet voor alle gebruikers beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="533f5-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="533f5-105">Deze functie wordt ondersteund voor Enterprise Outlook.com- en Enterprise Outlook Win32-desktopgebruikers.</span><span class="sxs-lookup"><span data-stu-id="533f5-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="533f5-106">Het is momenteel niet beschikbaar voor gebruikers van Office 365 voor consumenten.</span><span class="sxs-lookup"><span data-stu-id="533f5-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="533f5-107">Om te voorkomen dat phishingberichten uw postvak bereiken, controleert Office 365 of de afzenders zijn wie ze zeggen dat ze zijn en markeert het verdachte berichten als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="533f5-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="533f5-108">Wanneer een bericht is gemarkeerd als een phishing-scam, geeft Outlook een waarschuwing boven aan de pagina weer, maar alle koppelingen in het bericht kunnen nog steeds worden geopend.</span><span class="sxs-lookup"><span data-stu-id="533f5-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="533f5-109">Hoe kan ik een verdacht bericht in mijn postvak IN identificeren?</span><span class="sxs-lookup"><span data-stu-id="533f5-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="533f5-110">In Outlook worden indicatoren weergegeven wanneer de afzender van een bericht niet kan worden geïdentificeerd of hun identiteit verschilt van wat u ziet in het Van-adres.</span><span class="sxs-lookup"><span data-stu-id="533f5-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="533f5-111">U ziet een '?' in de afzenderafbeelding</span><span class="sxs-lookup"><span data-stu-id="533f5-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="533f5-112">Wanneer Office 365 de identiteit van de afzender niet kan verifiëren met behulp van e-mailverificatietechnieken, wordt er een '?' weergegeven in de afzenderafbeelding.</span><span class="sxs-lookup"><span data-stu-id="533f5-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![Bericht is niet geslaagd voor verificatie](../../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="533f5-114">Niet elk bericht dat niet te verifiëren is kwaadaardig.</span><span class="sxs-lookup"><span data-stu-id="533f5-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="533f5-115">U moet echter voorzichtig zijn met de interactie met berichten die niet verifiëren als u de afzender niet herkent.</span><span class="sxs-lookup"><span data-stu-id="533f5-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="533f5-116">Of, als u een afzender herkent die normaal gesproken geen '?' in de afzenderafbeelding heeft, maar u plotseling begint te zien, kan dat een teken zijn dat de afzender wordt vervalst.</span><span class="sxs-lookup"><span data-stu-id="533f5-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="533f5-117">Hoe te beheren welke berichten de niet-geverifieerde afzenderbehandeling ontvangen</span><span class="sxs-lookup"><span data-stu-id="533f5-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="533f5-118">Als u een Office 365-klant bent, u deze functie beheren via het Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="533f5-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="533f5-119">In het Security & Compliance Center kunnen globale of beveiligingsbeheerders de functie in- of uitschakelen, via anti-spoofing bescherming onder het Anti-Phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="533f5-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="533f5-120">Daarnaast u de **cmdlet Set-AntiPhishPolicy** gebruiken in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="533f5-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="533f5-121">Zie Bescherming [tegen phishing in Office 365](anti-phishing-protection.md) en [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="533f5-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![Niet-geverifieerde afzenders bewerken in de grafische interface.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="533f5-123">Als een beheerder een fout-positief heeft geïdentificeerd en een afzender niet de niet-geverifieerde afzenderbehandeling mag ontvangen, kan een van de volgende acties worden ondernomen om de afzender toe te voegen aan de lijst spoofinformatie voor spoofinformatie:</span><span class="sxs-lookup"><span data-stu-id="533f5-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="533f5-124">Voeg het domeinpaar toe via de Spoof Intelligence Insight.</span><span class="sxs-lookup"><span data-stu-id="533f5-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="533f5-125">Zie [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="533f5-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="533f5-126">Voeg het domeinpaar toe via de **cmdlet Set-PhishFilterPolicy** in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="533f5-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="533f5-127">Zie [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) en [Office 365 ATP anti-phishing- en antiphishingbeleid instellen](set-up-anti-phishing-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="533f5-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="533f5-128">Bovendien passen we de niet-geverifieerde afzenderbehandeling niet toe als het bericht via e-mailstroomregels (ook wel transportregels) of de veilige domeinlijst (antispambeleid) in het Postvak IN is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="533f5-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="533f5-129">Hoe de 'via' tag te beheren</span><span class="sxs-lookup"><span data-stu-id="533f5-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="533f5-130">Als u een Office 365-klant bent, u deze functie beheren via het Office 365-beveiligingscentrum & Compliance, op dezelfde manier dat u de niet-geverifieerde afzenderbehandeling beheert.</span><span class="sxs-lookup"><span data-stu-id="533f5-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="533f5-131">Als u de afzender toevoegt aan de lijst met spoofinformatie voor spoof, wordt de 'via'-behandeling niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="533f5-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="533f5-132">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="533f5-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="533f5-133">Welke criteria gebruikt Outlook.com en Outlook Win32-bureaublad om de eigenschappen '?' en de 'via'toe te voegen?</span><span class="sxs-lookup"><span data-stu-id="533f5-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="533f5-134">Voor de '?' in de afzenderafbeelding: Outlook.com vereist dat het bericht spf- of DKIM-verificatie doorstaat en een dmarc-pas of een samengestelde verificatiepas van Office 365 Spoof Intelligence ontvangt.</span><span class="sxs-lookup"><span data-stu-id="533f5-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="533f5-135">Zie [SPF instellen in Office 365 voor](set-up-spf-in-office-365-to-help-prevent-spoofing.md) meer informatie om spoofing te voorkomen en [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Office 365 wordt verzonden, te valideren.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="533f5-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="533f5-136">Voor de via-tag: Als het domein in het Van-adres verschilt van het domein in de DKIM-handtekening of de SMTP-mail VAN, geeft Outlook.com het domein weer in een van deze twee velden (liever de DKIM-handtekening).</span><span class="sxs-lookup"><span data-stu-id="533f5-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="533f5-137">Hoe verwijder ik de '?' zonder gebruik te maken van de Spoof Intelligence spoof lijst?</span><span class="sxs-lookup"><span data-stu-id="533f5-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="533f5-138">Voor de '?' in de afzenderafbeelding: Als afzender moet u uw bericht verifiëren met SPF of DKIM.</span><span class="sxs-lookup"><span data-stu-id="533f5-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="533f5-139">Voor de via-tag: Als afzender moet u ervoor zorgen dat het domein in de DKIM-handtekening of de SMTP-mail VAN hetzelfde is als, of een subdomein is van het domein in het Adres van.</span><span class="sxs-lookup"><span data-stu-id="533f5-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="533f5-140">Laten Outlook.com en Outlook Win32-bureaublad dit zien voor elk bericht dat niet door verificatie wordt geslaagd?</span><span class="sxs-lookup"><span data-stu-id="533f5-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="533f5-141">Niet per se.</span><span class="sxs-lookup"><span data-stu-id="533f5-141">Not necessarily.</span></span> <span data-ttu-id="533f5-142">Office 365 heeft mogelijk andere eigenschappen in het bericht om de afzender te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="533f5-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="533f5-143">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="533f5-143">Related topics</span></span>

[<span data-ttu-id="533f5-144">Uw Outlook.com e-mailaccount beschermen</span><span class="sxs-lookup"><span data-stu-id="533f5-144">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="533f5-145">Omgaan met phishing of spoofing in Outlook.com</span><span class="sxs-lookup"><span data-stu-id="533f5-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="533f5-146">Ongewenste e-mail en spam filteren in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="533f5-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
