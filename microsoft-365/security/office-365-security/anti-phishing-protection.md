---
title: Bescherming tegen phishing
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
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Beheerders kunnen leren werken met de functies van bescherming tegen phishing in Exchange Online Protection (EOP) en Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: f6d864a7f9995de64f3714dffcd1838b2480a627
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867173"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="58ec2-103">Bescherming tegen phishing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58ec2-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="58ec2-104">*Phishing* is een aanval via een e-mailbericht dat probeert gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="58ec2-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="58ec2-105">Phishing bevat specifieke soorten phishing.</span><span class="sxs-lookup"><span data-stu-id="58ec2-105">There are specific categories of phishing.</span></span> <span data-ttu-id="58ec2-106">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="58ec2-106">For example:</span></span>

- <span data-ttu-id="58ec2-107">Met **Spear Phishingfilter** gerichte inhoud die speciaal is afgestemd op de gerichte geadresseerden (meestal na Reconnaissance van de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="58ec2-107">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="58ec2-108">**Whaling** wordt op de werknemers of andere high-value-doelen binnen een organisatie omgeleid voor de maximale kracht.</span><span class="sxs-lookup"><span data-stu-id="58ec2-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="58ec2-109">**Misbruik van zakelijke e-mail (BEC)** maakt gebruik van vertrouwde vertrouwde afzenders (financiële medewerkers, klanten, vertrouwde partners, etc.) om geadresseerden te laten overgaan op betaling, het overdragen van bedragen of het onthullen van klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="58ec2-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="58ec2-110">**Ransomware** waarmee u uw gegevens kunt versleutelen en betaling hoeft te decoderen om te voorkomen dat u in phishingberichten begint.</span><span class="sxs-lookup"><span data-stu-id="58ec2-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="58ec2-111">Met anti malafide bescherming kunt u versleutelde bestanden niet ontsleutelen, maar u kunt wel de eerste Phishingberichten detecteren die aan de campagne van Ransomware zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="58ec2-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="58ec2-112">Zie [herstel van een Ransomware aanval in Microsoft 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een Ransomware-aanval.</span><span class="sxs-lookup"><span data-stu-id="58ec2-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="58ec2-113">Met de toenemende complexiteit van aanvallen is het zelfs moeilijk voor gebruikers met een opgeleid, zodat ze een verfijnde malafide bericht kunnen vinden.</span><span class="sxs-lookup"><span data-stu-id="58ec2-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="58ec2-114">Gelukkig kan Exchange Online Protection (EOP) en de extra functies in Office 365 Advanced Threat Protection (Office 365 ATP) helpen.</span><span class="sxs-lookup"><span data-stu-id="58ec2-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="58ec2-115">Bescherming tegen phishing in EOP</span><span class="sxs-lookup"><span data-stu-id="58ec2-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="58ec2-116">EOP (dat wil zeggen Microsoft 365-organisaties zonder ATP) bevat functies waarmee u uw organisatie tegen phishing kunt beschermen:</span><span class="sxs-lookup"><span data-stu-id="58ec2-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="58ec2-117">**Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze.</span><span class="sxs-lookup"><span data-stu-id="58ec2-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="58ec2-118">Zie voor meer informatie [spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="58ec2-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="58ec2-119">**Anti-phishingfilter in EOP**: Schakel spoof Intelligence in of uit, schakel de id van niet-geverifieerde afzenders in Outlook in of uit en geef de actie op voor geblokkeerde spoof afzenders (verplaatsen naar map Ongewenste e-mail of Quarantine).</span><span class="sxs-lookup"><span data-stu-id="58ec2-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="58ec2-120">Zie [anti-phishings beleid in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="58ec2-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="58ec2-121">**Impliciete e-mail verificatie**: EOP verbetert standaardverificatie van e-mail verificatie voor inkomende E-mail ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)) met de reputatie van de afzender, de geschiedenis van de afzender, de geschiedenis van de ontvanger, de gedrags analyse en andere geavanceerde technieken om vervalste afzenders te helpen identificeren.</span><span class="sxs-lookup"><span data-stu-id="58ec2-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="58ec2-122">Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="58ec2-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="58ec2-123">Extra bescherming tegen phishing in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="58ec2-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="58ec2-124">Office 365 ATP bevat extra en meer geavanceerde functies voor het anti-phishing van Office:</span><span class="sxs-lookup"><span data-stu-id="58ec2-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="58ec2-125">**ATP anti-phishingfilter**: Maak nieuwe aangepaste beleidsregels en Configureer instellingen voor de anti-personele instellingen (gebruikers en domeinen beschermen tegen imitatie), Postvak informatie-instellingen en instelbare geavanceerde phishing.</span><span class="sxs-lookup"><span data-stu-id="58ec2-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="58ec2-126">Zie voor meer informatie [het artikel ATP anti-phishing configureren in Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58ec2-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="58ec2-127">Zie [anti phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen een anti-phishings beleid en een anti-phishingfilter.</span><span class="sxs-lookup"><span data-stu-id="58ec2-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="58ec2-128">**Campagne weergaven**: machine learning en andere heuristische analyses identificeren en analyseren van berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="58ec2-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="58ec2-129">Zie voor meer informatie [campagne weergaven in Office 365 ATP](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="58ec2-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="58ec2-130">**Aanvals Simulator**: beheerders kunnen valse phishingberichten maken en ze verzenden naar interne gebruikers als een Education-programma.</span><span class="sxs-lookup"><span data-stu-id="58ec2-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="58ec2-131">Zie [aanvals Simulator in Office 365 ATP](attack-simulator.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="58ec2-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="58ec2-132">Andere anti malafide bronnen</span><span class="sxs-lookup"><span data-stu-id="58ec2-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="58ec2-133">Voor eindgebruikers: [Bescherm uzelf tegen phishing en andere vormen van online fraude](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span><span class="sxs-lookup"><span data-stu-id="58ec2-133">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="58ec2-134">[Hoe Microsoft 365 het van-adres valideert om phishing te voorkomen](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="58ec2-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
