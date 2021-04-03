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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de anti-phishingbeveiligingsfuncties in Exchange Online Protection (EOP) en Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a100e28ddee1629b2fe35e28742a43b891d13e57
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570610"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="826f4-103">Anti-phishingbeveiliging in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="826f4-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="826f4-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="826f4-104">**Applies to**</span></span>
- [<span data-ttu-id="826f4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="826f4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="826f4-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="826f4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="826f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="826f4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="826f4-108">*Phishing* is een e-mailaanval die gevoelige informatie probeert te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="826f4-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="826f4-109">Er zijn specifieke categorieën van phishing.</span><span class="sxs-lookup"><span data-stu-id="826f4-109">There are specific categories of phishing.</span></span> <span data-ttu-id="826f4-110">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="826f4-110">For example:</span></span>

- <span data-ttu-id="826f4-111">**Bij phishing** met speerpunten wordt gerichte, aangepaste inhoud gebruikt die specifiek is afgestemd op de beoogde geadresseerden (meestal na verkenning van de geadresseerden door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="826f4-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="826f4-112">**Whaling** is gericht op leidinggevenden of andere doelen met een hoge waarde binnen een organisatie voor een maximaal effect.</span><span class="sxs-lookup"><span data-stu-id="826f4-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="826f4-113">Zakelijke e-mailcompromitteerden **(BEC)** gebruikt vervalste vertrouwde afzenders (financiële verantwoordelijken, klanten, vertrouwde partners, enzovoort) om geadresseerden te verleiden tot het goedkeuren van betalingen, het overmaken van tegoeden of het onthullen van klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="826f4-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span> <span data-ttu-id="826f4-114">Bekijk deze [video voor meer informatie.](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)</span><span class="sxs-lookup"><span data-stu-id="826f4-114">Learn more by watching [this video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span></span>

- <span data-ttu-id="826f4-115">**Ransomware** die uw gegevens versleutelt en betaling vereist om deze te ontsleutelen, begint bijna altijd in phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="826f4-115">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="826f4-116">Anti-phishingbeveiliging kan u niet helpen versleutelde bestanden te ontsleutelen, maar kan wel helpen bij het opsporen van de eerste phishingberichten die zijn gekoppeld aan de ransomware-campagne.</span><span class="sxs-lookup"><span data-stu-id="826f4-116">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="826f4-117">Zie Herstellen van een [ransomware-aanval in Microsoft 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een ransomware-aanval.</span><span class="sxs-lookup"><span data-stu-id="826f4-117">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="826f4-118">Met de toenemende complexiteit van aanvallen is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishingberichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="826f4-118">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="826f4-119">Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Microsoft Defender voor Office 365 u helpen.</span><span class="sxs-lookup"><span data-stu-id="826f4-119">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="826f4-120">Anti-phishingbeveiliging in EOP</span><span class="sxs-lookup"><span data-stu-id="826f4-120">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="826f4-121">EOP (dat wil zeggen Microsoft 365-organisaties zonder Microsoft Defender voor Office 365) bevat functies die uw organisatie kunnen beschermen tegen phishing-bedreigingen:</span><span class="sxs-lookup"><span data-stu-id="826f4-121">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="826f4-122">**Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze.</span><span class="sxs-lookup"><span data-stu-id="826f4-122">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="826f4-123">Zie Spoof [intelligence configureren in EOP voor meer informatie.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="826f4-123">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="826f4-124">**Anti-phishingbeleid in EOP:** Schakel spoofinformatie in of uit, schakel niet-genauteerde afzender-identificatie in Outlook in of uit en geef de actie op voor geblokkeerde vervalste afzenders (ga naar map Ongewenste e-mail of quarantaine).</span><span class="sxs-lookup"><span data-stu-id="826f4-124">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="826f4-125">Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="826f4-125">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="826f4-126">Impliciete e-mailverificatie: EOP verbetert standaardcontroles voor e-mailverificatie voor binnenkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met de reputatie van afzenders, afzendergeschiedenis, geschiedenis van geadresseerden, gedragsanalyse en andere geavanceerde technieken om vervalste afzenders te identificeren.</span><span class="sxs-lookup"><span data-stu-id="826f4-126">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="826f4-127">Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="826f4-127">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="826f4-128">Aanvullende bescherming tegen phishing in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="826f4-128">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="826f4-129">Microsoft Defender voor Office 365 bevat extra en geavanceerdere anti-phishingfuncties:</span><span class="sxs-lookup"><span data-stu-id="826f4-129">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="826f4-130">**Anti-phishingbeleid in Microsoft Defender voor Office 365:** Nieuwe aangepaste beleidsregels maken, instellingen voor anti-imitatie configureren (gebruikers en domeinen beschermen tegen imitatie), instellingen voor postvakinformatie en aanpasbare geavanceerde phishingdrempels.</span><span class="sxs-lookup"><span data-stu-id="826f4-130">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="826f4-131">Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="826f4-131">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="826f4-132">Zie [Anti-phishingbeleid in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in EOP en anti-phishingbeleid in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="826f4-132">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="826f4-133">**Campagneweergaven:** Machine learning en andere heuristische acties identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishingaanvallen tegen de hele service en uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="826f4-133">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="826f4-134">Zie Campagneweergaven [in Microsoft Defender voor Office 365](campaigns.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="826f4-134">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="826f4-135">**Aanvalssimulator:** beheerders kunnen nep-phishingberichten maken en deze als onderwijshulpmiddel naar interne gebruikers verzenden.</span><span class="sxs-lookup"><span data-stu-id="826f4-135">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="826f4-136">Zie Attack [Simulator in Microsoft Defender voor Office 365 voor meer informatie.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="826f4-136">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="826f4-137">Andere anti-phishingbronnen</span><span class="sxs-lookup"><span data-stu-id="826f4-137">Other anti-phishing resources</span></span>

- <span data-ttu-id="826f4-138">Voor eindgebruikers: [Bescherm uzelf tegen phishingschema's en andere vormen van onlinefraude.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="826f4-138">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="826f4-139">[Hoe Microsoft 365 het Van-adres](how-office-365-validates-the-from-address.md)valideert om phishing te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="826f4-139">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
