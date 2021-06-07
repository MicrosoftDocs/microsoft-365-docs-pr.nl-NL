---
title: Externe e-mail doorsturen configureren en beheren, Automatisch doorsturen, 5.7.520 Toegang geweigerd, extern doorsturen uitschakelen, Uw beheerder heeft extern doorsturen, uitgaand antispambeleid uitgeschakeld
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b96d3d656a89e7102550d09a2f5052fdb5ae818
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/07/2021
ms.locfileid: "52792954"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="866d3-103">Automatische externe e-mail doorsturen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="866d3-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="866d3-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="866d3-104">**Applies to**</span></span>
- [<span data-ttu-id="866d3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="866d3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="866d3-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="866d3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="866d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="866d3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="866d3-108">Als beheerder hebt u mogelijk bedrijfsvereisten voor het beperken of beheren van automatisch doorgestuurde berichten naar externe geadresseerden (geadresseerden buiten uw organisatie).</span><span class="sxs-lookup"><span data-stu-id="866d3-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="866d3-109">E-mail doorsturen kan handig zijn, maar kan ook een beveiligingsrisico opleveren vanwege de mogelijke openbaarmaking van informatie.</span><span class="sxs-lookup"><span data-stu-id="866d3-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="866d3-110">Aanvallers kunnen deze informatie gebruiken om uw organisatie of partners aan te vallen.</span><span class="sxs-lookup"><span data-stu-id="866d3-110">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="866d3-111">De volgende typen automatische doorsturen zijn beschikbaar in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="866d3-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="866d3-112">Gebruikers kunnen regels [voor Postvak IN zo](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) configureren dat berichten automatisch worden doorgestuurd naar externe afzenders (bewust of als gevolg van een gekromd account).</span><span class="sxs-lookup"><span data-stu-id="866d3-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>
- <span data-ttu-id="866d3-113">Beheerders kunnen het [doorsturen van postvakken](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="866d3-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="866d3-114">De beheerder kan kiezen of u alleen berichten wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="866d3-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="866d3-115">U kunt beleidsregels voor uitgaand spamfilter gebruiken om automatische doorsturen naar externe geadresseerden te controleren.</span><span class="sxs-lookup"><span data-stu-id="866d3-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="866d3-116">Er zijn drie instellingen beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="866d3-116">Three settings are available:</span></span>

- <span data-ttu-id="866d3-117">**Automatisch - Systeemgestuurd:** Automatisch extern doorsturen wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="866d3-117">**Automatic - System-controlled**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="866d3-118">Interne automatische doorsturen van berichten blijft werken.</span><span class="sxs-lookup"><span data-stu-id="866d3-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="866d3-119">Dit is de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="866d3-119">This is the default setting.</span></span>
- <span data-ttu-id="866d3-120">**Op**: Automatisch extern doorsturen is toegestaan en niet beperkt.</span><span class="sxs-lookup"><span data-stu-id="866d3-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="866d3-121">**Uit:** Automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) naar de afzender.</span><span class="sxs-lookup"><span data-stu-id="866d3-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="866d3-122">Zie Uitgaande [spamfilters](configure-the-outbound-spam-policy.md)configureren in EOP voor instructies over het configureren van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="866d3-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="866d3-123">Als u automatisch doorsturen uit schakelt u regels voor Postvak IN (gebruikers) of postvak doorsturen (beheerders) uit die berichten omleiden naar externe adressen.</span><span class="sxs-lookup"><span data-stu-id="866d3-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="866d3-124">Het automatisch doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door de instellingen in beleidsregels voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="866d3-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="866d3-125">U kunt informatie zien over gebruikers die berichten automatisch doorsturen naar externe geadresseerden in het [rapport Automatisch doorgestuurde berichten.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="866d3-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="866d3-126">Hoe de beleidsinstellingen voor uitgaand spamfilter werken met andere besturingselementen voor automatisch doorsturen van e-mail</span><span class="sxs-lookup"><span data-stu-id="866d3-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="866d3-127">Als beheerder hebt u mogelijk al andere besturingselementen geconfigureerd om automatisch doorsturen van e-mail toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="866d3-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="866d3-128">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="866d3-128">For example:</span></span>

- <span data-ttu-id="866d3-129">[Externe domeinen om](/exchange/mail-flow-best-practices/remote-domains/remote-domains) automatische doorsturen van e-mail naar bepaalde of alle externe domeinen toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="866d3-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>
- <span data-ttu-id="866d3-130">Voorwaarden en acties in Exchange [regels](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor e-mailstroom (ook wel transportregels genoemd) om automatisch doorgestuurde berichten naar externe geadresseerden te detecteren en te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="866d3-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="866d3-131">Externe domeininstellingen en e-mailstroomregels zijn onafhankelijk van de instellingen in beleidsregels voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="866d3-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="866d3-132">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="866d3-132">For example:</span></span>

- <span data-ttu-id="866d3-133">U staat automatisch doorsturen voor een extern domein toe, maar u blokkeert automatisch doorsturen in beleidsregels voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="866d3-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="866d3-134">In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="866d3-134">In this example, automatically forwarded messages are blocked.</span></span>
- <span data-ttu-id="866d3-135">U staat automatisch doorsturen toe in beleidsregels voor uitgaand spamfilter, maar u gebruikt regels voor e-mailstroom of externe domeininstellingen om automatisch doorgestuurde e-mail te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="866d3-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="866d3-136">In dit voorbeeld blokkeren de regels voor e-mailstroom of externe domeininstellingen automatisch doorgestuurde berichten.</span><span class="sxs-lookup"><span data-stu-id="866d3-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="866d3-137">Met deze functieafhankelijkheid kunt u (bijvoorbeeld) automatisch doorsturen toestaan in beleidsregels voor uitgaand spamfilter, maar externe domeinen gebruiken om de externe domeinen te beheren waar gebruikers berichten naar kunnen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="866d3-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="866d3-138">Geblokkeerde e-mailberichten doorsturen</span><span class="sxs-lookup"><span data-stu-id="866d3-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="866d3-139">Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd en  het beleid voor uitgaand [spamfilter](configure-the-outbound-spam-policy.md) deze activiteit blokkeert, wordt het bericht geretourneerd aan de afzender in een NDR die de volgende informatie bevat:</span><span class="sxs-lookup"><span data-stu-id="866d3-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
