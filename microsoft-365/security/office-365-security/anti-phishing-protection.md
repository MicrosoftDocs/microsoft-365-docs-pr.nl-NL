---
title: Bescherming tegen phishing
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
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over de anti-phishingbeveiligingsfuncties in Exchange Online Protection (EOP) en Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 2b5d5786e363b0d74e29b1f0c27ab110d2e60b0d
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262281"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="d82dc-103">Bescherming tegen phishing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d82dc-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="d82dc-104">*Phishing* is een e-mailaanval die probeert gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="d82dc-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="d82dc-105">Er zijn specifieke categorieën van phishing.</span><span class="sxs-lookup"><span data-stu-id="d82dc-105">There are specific categories of phishing.</span></span> <span data-ttu-id="d82dc-106">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d82dc-106">For example:</span></span>

- <span data-ttu-id="d82dc-107">**Spear phishing** maakt gebruik van zeer gerichte en aangepaste inhoud die specifiek is afgestemd op de beoogde ontvangers (meestal, na verkenning op de ontvangers door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="d82dc-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="d82dc-108">**Walvisvangst** is gericht op leidinggevenden of andere hoogwaardige doelen binnen een organisatie voor een maximaal effect.</span><span class="sxs-lookup"><span data-stu-id="d82dc-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="d82dc-109">**Business e-mail compromis (BEC)** maakt gebruik van vervalste vertrouwde afzenders (financiële functionarissen, klanten, vertrouwde partners, enz.) in een poging om de ontvanger te verleiden tot het goedkeuren van betalingen, het overbrengen van fondsen, of het vrijgeven van klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="d82dc-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="d82dc-110">**Ransomware** die uw gegevens versleutelt en betaling eist om deze te decoderen, begint bijna altijd in phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="d82dc-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="d82dc-111">Anti-phishing bescherming kan u niet helpen versleutelde bestanden te decoderen, maar het kan helpen bij het detecteren van de eerste phishing-berichten die zijn gekoppeld aan de ransomware campagne.</span><span class="sxs-lookup"><span data-stu-id="d82dc-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="d82dc-112">Voor meer informatie over het herstellen van een ransomware aanval, zie [Herstellen van een ransomware aanval in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="d82dc-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="d82dc-113">Met de toenemende complexiteit van aanvallen, is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishing-berichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="d82dc-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="d82dc-114">Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Office 365 Advanced Threat Protection (Office 365 ATP) helpen.</span><span class="sxs-lookup"><span data-stu-id="d82dc-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="d82dc-115">Bescherming tegen phishing in EOP</span><span class="sxs-lookup"><span data-stu-id="d82dc-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="d82dc-116">EOP (dat wil zeggen Microsoft 365-organisaties zonder ATP) bevat functies die uw organisatie kunnen beschermen tegen phishingbedreigingen:</span><span class="sxs-lookup"><span data-stu-id="d82dc-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="d82dc-117">**Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze.</span><span class="sxs-lookup"><span data-stu-id="d82dc-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="d82dc-118">Zie [Spoofinformatie configureren in EOP](learn-about-spoof-intelligence.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="d82dc-119">**Anti-phishingbeleid in EOP:** Schakel spoofinformatie in of uit, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en geef de actie op voor geblokkeerde vervalste afzenders (ga naar de map Ongewenste e-mail of quarantaine).</span><span class="sxs-lookup"><span data-stu-id="d82dc-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="d82dc-120">Zie [Beleid voor antiphishing configureren in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="d82dc-121">**Impliciete e-mailverificatie:** EOP verbetert standaard e-mailverificatiecontroles voor binnenkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met de reputatie van afzenders, afzendergeschiedenis, ontvangstgeschiedenis, gedragsanalyse en andere geavanceerde technieken om vervalste afzenders te identificeren.</span><span class="sxs-lookup"><span data-stu-id="d82dc-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="d82dc-122">Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="d82dc-123">Aanvullende bescherming tegen phishing in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="d82dc-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="d82dc-124">Office 365 ATP bevat aanvullende en meer geavanceerde antiphishingfuncties:</span><span class="sxs-lookup"><span data-stu-id="d82dc-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="d82dc-125">**ATP-antiphishingbeleid:** maak nieuwe aangepaste beleidsregels, configureer anti-imitatie-instellingen (bescherm gebruikers en domeinen tegen imitatie), instellingen voor postvakintelligentie en aanpasbare geavanceerde phishingdrempels.</span><span class="sxs-lookup"><span data-stu-id="d82dc-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="d82dc-126">Zie [ATP-antiphishingbeleid configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="d82dc-127">Zie [Antiphishingbeleid in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen antiphishingbeleid en ATP-antiphishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="d82dc-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="d82dc-128">**Campagneweergaven:** Machine learning en andere heuristiek identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="d82dc-129">Zie [Campagneweergaven in Office 365 ATP](campaigns.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="d82dc-130">**Aanval simulator:** Beheerders kunnen nep phishing-berichten te maken en stuur ze naar interne gebruikers als een educatieve tool.</span><span class="sxs-lookup"><span data-stu-id="d82dc-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="d82dc-131">Zie [Attack Simulator in Office 365 ATP](attack-simulator.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d82dc-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="d82dc-132">Andere anti-phishing bronnen</span><span class="sxs-lookup"><span data-stu-id="d82dc-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="d82dc-133">Voor eindgebruikers: [Bescherm uzelf tegen phishing-programma's en andere vormen van online fraude.](https://support.office.com/article/protect-yourself-from-phishing-schemes-and-other-forms-of-online-fraud-be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="d82dc-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/protect-yourself-from-phishing-schemes-and-other-forms-of-online-fraud-be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="d82dc-134">[Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen.](how-office-365-validates-the-from-address.md)</span><span class="sxs-lookup"><span data-stu-id="d82dc-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
