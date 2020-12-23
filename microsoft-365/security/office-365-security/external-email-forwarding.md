---
title: Externe e-mailberichten configureren en beheren, automatisch doorsturen, 5.7.520 toegang geweigerd, externe forwarding uitschakelen, de beheerder heeft extern doorsturen uitgeschakeld, beleid voor uitgaand Antispambeleid
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f75504941e8481d35458ad2ae6b5e8a72c5e8c8c
ms.sourcegitcommit: a49338bde6923b13132c7b9e4c6bb75c14163c72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/23/2020
ms.locfileid: "49728186"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="097cf-103">Automatische doorsturen van e-mail instellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="097cf-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="097cf-104">Als beheerder hebt u mogelijk een bedrijf nodig om automatisch doorgestuurde berichten te beperken of te beheren voor externe geadresseerden (geadresseerden buiten uw organisatie).</span><span class="sxs-lookup"><span data-stu-id="097cf-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="097cf-105">Het doorsturen van e-mail kan een handige functie zijn, maar kan ook een beveiligingsrisico vormen als gevolg van potentiële informatie over de potentiële informatie.</span><span class="sxs-lookup"><span data-stu-id="097cf-105">Email forwarding can be a useful feature, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="097cf-106">Kwaadwillenden kunnen deze gegevens gebruiken om uw organisatie of partners te vermoeden.</span><span class="sxs-lookup"><span data-stu-id="097cf-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="097cf-107">De volgende typen automatisch doorsturen zijn beschikbaar in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="097cf-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="097cf-108">Gebruikers kunnen [regels voor Postvak in](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) instellen om berichten automatisch door te sturen naar externe afzenders (een onopzettelijke of als gevolg van een gemanipuleerd account).</span><span class="sxs-lookup"><span data-stu-id="097cf-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="097cf-109">Beheerders kunnen [Postvak doorsturen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="097cf-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="097cf-110">De beheerder kan kiezen of u berichten gewoon wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="097cf-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="097cf-111">U kunt uitgaande spamfilter beleidsregels gebruiken om automatisch doorsturen naar externe geadresseerden te beheren.</span><span class="sxs-lookup"><span data-stu-id="097cf-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="097cf-112">Drie instellingen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="097cf-112">Three settings are available:</span></span>

- <span data-ttu-id="097cf-113">**Automatisch**: automatisch extern doorsturen wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="097cf-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="097cf-114">Interne automatisch doorsturen van berichten blijft werken.</span><span class="sxs-lookup"><span data-stu-id="097cf-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="097cf-115">Dit is de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="097cf-115">This is the default setting.</span></span>
- <span data-ttu-id="097cf-116">**Aan**: automatisch extern doorsturen is toegestaan en niet beperkt.</span><span class="sxs-lookup"><span data-stu-id="097cf-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="097cf-117">**Off**: automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-uitgevoerde bezorging (ook wel een NDR-of stuiter bericht) voor de afzender.</span><span class="sxs-lookup"><span data-stu-id="097cf-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="097cf-118">Zie [uitgaande spamfilters in EOP](configure-the-outbound-spam-policy.md)voor instructies voor het configureren van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="097cf-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="097cf-119">Als u automatisch doorsturen uitschakelt, worden regels voor Postvak in (gebruikers) of postvak doorsturen (beheerders) uitgeschakeld waarmee berichten naar externe adressen worden doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="097cf-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="097cf-120">Het automatisch doorsturen van berichten tussen interne gebruikers heeft geen invloed op de instellingen in het filter beleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="097cf-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="097cf-121">U vindt informatie over gebruikers die berichten automatisch doorsturen naar externe geadresseerden in het [rapport met automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="097cf-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="097cf-122">Hoe de beleidsinstellingen voor het uitgaande spamfilter werken met andere besturingselementen voor automatisch doorsturen van e-mail</span><span class="sxs-lookup"><span data-stu-id="097cf-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="097cf-123">Als beheerder hebt u mogelijk al andere besturingselementen geconfigureerd, zodat u het automatisch doorsturen van e-mail toestaat of blokkeert.</span><span class="sxs-lookup"><span data-stu-id="097cf-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="097cf-124">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="097cf-124">For example:</span></span>

- <span data-ttu-id="097cf-125">[Externe domeinen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) voor het toestaan of blokkeren van automatische e-mail doorsturen naar bepaalde of alle externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="097cf-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="097cf-126">Voorwaarden en acties in Exchange [-e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel een zogenaamde transportregels genoemd) voor het detecteren en blokkeren van automatisch doorgestuurde berichten naar externe geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="097cf-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="097cf-127">De instellingen voor extern domein en de e-mail stroom regels zijn onafhankelijk van de instellingen in het filter beleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="097cf-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="097cf-128">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="097cf-128">For example:</span></span>

- <span data-ttu-id="097cf-129">U kunt het automatisch doorsturen van een extern domein toestaan, maar u blokkeert automatisch doorsturen in het filter beleid voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="097cf-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="097cf-130">In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="097cf-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="097cf-131">U kunt automatisch doorsturen in het beleid voor uitgaande spam filteren, maar u kunt de e-mail stroom regels of de externe Domeininstellingen gebruiken om automatisch doorgestuurde e-mail te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="097cf-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="097cf-132">In dit voorbeeld wordt de instelling voor de e-mail stroom regels of het externe domein voor het automatisch doorsturen van berichten blokkeren.</span><span class="sxs-lookup"><span data-stu-id="097cf-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="097cf-133">Deze functie onafhankelijkheid biedt u de mogelijkheid om automatisch doorsturen in te schakelen in een uitgaand spamfilter beleid, maar externe domeinen gebruiken voor het beheren van de externe domeinen waarnaar gebruikers berichten kunnen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="097cf-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="097cf-134">Bericht met doorsturen van geblokkeerde e-mail</span><span class="sxs-lookup"><span data-stu-id="097cf-134">The blocked email forwarding message</span></span>

<span data-ttu-id="097cf-135">Wanneer een bericht wordt weergegeven als automatisch doorgeschakeld, en het organisatiebeleid deze activiteit *blokkeert* , wordt het bericht geretourneerd aan de afzender in een NDR met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="097cf-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
