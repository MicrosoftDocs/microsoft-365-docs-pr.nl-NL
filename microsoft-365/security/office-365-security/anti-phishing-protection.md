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
description: Beheerders kunnen meer informatie krijgen over de functies voor beveiliging tegen phishing in Exchange Online Protection (EOP) en Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4fef8aa30f2b41c0ba84a6535969b12448e80562
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289051"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="5cf85-103">Beveiliging tegen phishing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cf85-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5cf85-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="5cf85-104">**Applies to**</span></span>
- [<span data-ttu-id="5cf85-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5cf85-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5cf85-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5cf85-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="5cf85-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cf85-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="5cf85-108">*Phishing* is een e-mailaanvallen die probeert gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="5cf85-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="5cf85-109">Er zijn specifieke categorieën phishing.</span><span class="sxs-lookup"><span data-stu-id="5cf85-109">There are specific categories of phishing.</span></span> <span data-ttu-id="5cf85-110">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5cf85-110">For example:</span></span>

- <span data-ttu-id="5cf85-111">**Bij phishing** wordt gerichte, aangepaste inhoud gebruikt die specifiek is afgestemd op de specifieke geadresseerden (meestal nadat de aanvaller de ontvangers heeft aangevallen).</span><span class="sxs-lookup"><span data-stu-id="5cf85-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="5cf85-112">**De organisatie is** gericht op leidinggevenden of andere doelen voor hoge waarden binnen een organisatie voor een maximumeffect.</span><span class="sxs-lookup"><span data-stu-id="5cf85-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="5cf85-113">In **BEC (Business Email Compromise)** wordt gebruikgemaakt van vervalste vertrouwde afzenders (financiële officers, klanten, vertrouwde partners, enzovoort) om ontvangers te verleiden tot het goedkeuren van betalingen, het overmaken van tegoeden of het onthullen van klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="5cf85-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="5cf85-114">**Ransomware** die uw gegevens versleutelt en betaling vereist om deze te ontsleutelen, begint vrijwel altijd in phishing-berichten.</span><span class="sxs-lookup"><span data-stu-id="5cf85-114">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="5cf85-115">Bescherming tegen phishing kan u niet helpen versleutelde bestanden te ontsleutelen, maar kan wel helpen bij het detecteren van de eerste phishingberichten die zijn gekoppeld aan de ransomware-campagne.</span><span class="sxs-lookup"><span data-stu-id="5cf85-115">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="5cf85-116">Zie Herstel van een [ransomware-aanval in Microsoft 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een ransomware-aanval.</span><span class="sxs-lookup"><span data-stu-id="5cf85-116">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="5cf85-117">Door de groeiende complexiteit van aanvallen is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishing-berichten te identificeren.</span><span class="sxs-lookup"><span data-stu-id="5cf85-117">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="5cf85-118">Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Microsoft Defender voor Office 365 u helpen.</span><span class="sxs-lookup"><span data-stu-id="5cf85-118">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="5cf85-119">Beveiliging tegen phishing in EOP</span><span class="sxs-lookup"><span data-stu-id="5cf85-119">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="5cf85-120">EOP (dat wil zeggen Microsoft 365-organisaties zonder Microsoft Defender voor Office 365) bevat functies die uw organisatie kunnen beschermen tegen phishing-bedreigingen:</span><span class="sxs-lookup"><span data-stu-id="5cf85-120">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="5cf85-121">**Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze.</span><span class="sxs-lookup"><span data-stu-id="5cf85-121">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="5cf85-122">Zie Spoof Intelligence configureren in EOP voor [meer informatie.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="5cf85-122">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="5cf85-123">**Anti-phishingbeleid in EOP:** spoof intelligence in- of uitschakelen, afzender-id's met niet-geauteerde afzender in Outlook in- of uitschakelen en de actie opgeven voor geblokkeerde vervalste afzenders (verplaatsen naar map Ongewenste e-mail of quarantaine).</span><span class="sxs-lookup"><span data-stu-id="5cf85-123">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="5cf85-124">Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf85-124">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="5cf85-125">Impliciete e-mailverificatie: EOP verbetert standaard-e-mailverificatiecontroles op inkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met reputatie van afzenders, afzendergeschiedenis, geschiedenis van geadresseerden, analyse van analyses en andere geavanceerde technieken om vervalste afzenders te identificeren.</span><span class="sxs-lookup"><span data-stu-id="5cf85-125">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="5cf85-126">Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf85-126">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5cf85-127">Aanvullende beveiliging tegen phishing in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5cf85-127">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="5cf85-128">Microsoft Defender voor Office 365 bevat aanvullende en geavanceerdere anti-phishingfuncties:</span><span class="sxs-lookup"><span data-stu-id="5cf85-128">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="5cf85-129">**Anti-phishingbeleid in Microsoft Defender voor Office 365:** nieuw aangepast beleid maken, instellingen voor anti-imitatie configureren (gebruikers en domeinen beschermen tegen imitatie), instellingen voor postvakinformatie en aanpasbare geavanceerde drempelwaarden voor phishing.</span><span class="sxs-lookup"><span data-stu-id="5cf85-129">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="5cf85-130">Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5cf85-130">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="5cf85-131">Zie [Anti-phishingbeleidsregels in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in EOP en anti-phishingbeleid in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="5cf85-131">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="5cf85-132">**Campagneweergaven:** machine learning en andere heuristics identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf85-132">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="5cf85-133">Zie Campagneweergaven [in Microsoft Defender voor Office 365 voor meer informatie.](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="5cf85-133">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="5cf85-134">**Aanvals simulator:** beheerders kunnen valse phishingberichten maken en deze als onderwijshulpmiddel naar interne gebruikers verzenden.</span><span class="sxs-lookup"><span data-stu-id="5cf85-134">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="5cf85-135">Zie Attack [Simulator in Microsoft Defender voor Office 365 voor meer informatie.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="5cf85-135">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="5cf85-136">Andere anti-phishing-informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="5cf85-136">Other anti-phishing resources</span></span>

- <span data-ttu-id="5cf85-137">Voor eindgebruikers: [bescherm uzelf tegen phishingpogingen en andere vormen van onlinefraude.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="5cf85-137">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="5cf85-138">[Hoe Microsoft 365 het Van-adres valideert](how-office-365-validates-the-from-address.md)om phishing te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="5cf85-138">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
