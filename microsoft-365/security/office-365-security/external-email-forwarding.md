---
title: Extern doorsturen, Automatisch doorsturen, 5.7.520 Toegang geweigerd, extern doorsturen uitschakelen, uw beheerder heeft extern doorsturen en uitgaand antispambeleid uitgeschakeld
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
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286862"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="bef12-103">Automatische doorsturen van externe e-mail in Microsoft 365 instellen</span><span class="sxs-lookup"><span data-stu-id="bef12-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bef12-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="bef12-104">**Applies to**</span></span>
- [<span data-ttu-id="bef12-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bef12-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bef12-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="bef12-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bef12-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bef12-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bef12-108">Als beheerder hebt u misschien te maken met bedrijfsvereisten om automatisch doorgestuurde berichten te beperken of te beheren voor externe geadresseerden (geadresseerden buiten uw organisatie).</span><span class="sxs-lookup"><span data-stu-id="bef12-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="bef12-109">Het doorsturen van e-mail kan nuttig zijn, maar kan ook een beveiligingsrisico vormen vanwege de mogelijke openbaarmaking van gegevens.</span><span class="sxs-lookup"><span data-stu-id="bef12-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="bef12-110">Aanvallers kunnen deze gegevens gebruiken om uw organisatie of partners aan te vallen.</span><span class="sxs-lookup"><span data-stu-id="bef12-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="bef12-111">De volgende typen automatische doorsturen zijn beschikbaar in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="bef12-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="bef12-112">Gebruikers kunnen regels [voor Postvak](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) IN zo configureren dat berichten automatisch worden doorgestuurd naar externe afzenders (opzettelijk of als gevolg van een gekromd account).</span><span class="sxs-lookup"><span data-stu-id="bef12-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="bef12-113">Beheerders kunnen het doorsturen [van postvakken](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="bef12-113">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="bef12-114">De beheerder kan kiezen of u alleen berichten wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.</span><span class="sxs-lookup"><span data-stu-id="bef12-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="bef12-115">U kunt uitgaand spamfilterbeleid gebruiken om automatische doorsturen naar externe geadresseerden te bepalen.</span><span class="sxs-lookup"><span data-stu-id="bef12-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="bef12-116">Er zijn drie instellingen beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="bef12-116">Three settings are available:</span></span>

- <span data-ttu-id="bef12-117">**Automatisch:** automatisch extern doorsturen wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="bef12-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="bef12-118">Het intern automatisch doorsturen van berichten blijft werken.</span><span class="sxs-lookup"><span data-stu-id="bef12-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="bef12-119">Dit is de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="bef12-119">This is the default setting.</span></span>
- <span data-ttu-id="bef12-120">**Aan:** Automatisch extern doorsturen is toegestaan en niet beperkt.</span><span class="sxs-lookup"><span data-stu-id="bef12-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="bef12-121">**Uit:** automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-bezorging (ook wel een NDR of niet-bezorgdbericht genoemd) voor de afzender.</span><span class="sxs-lookup"><span data-stu-id="bef12-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="bef12-122">Zie Uitgaande spamfilters configureren in EOP voor instructies over het configureren van [deze instellingen.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="bef12-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bef12-123">Als u automatisch doorsturen uit schakelen, worden regels voor Postvak IN (gebruikers) of postvak doorsturen (beheerders) uitgeschakeld die berichten omleiden naar externe adressen.</span><span class="sxs-lookup"><span data-stu-id="bef12-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="bef12-124">Het automatisch doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door de instellingen van het beleid voor het filteren van uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="bef12-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="bef12-125">In het rapport Met automatisch doorgestuurde berichten kunt u informatie zien over gebruikers die berichten automatisch doorsturen naar [externe geadresseerden.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="bef12-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="bef12-126">De manier waarop de beleidsinstellingen voor uitgaande spamfilters werken met andere besturingselementen voor het automatisch doorsturen van e-mail</span><span class="sxs-lookup"><span data-stu-id="bef12-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="bef12-127">Als beheerder hebt u mogelijk andere besturingselementen geconfigureerd om het automatisch doorsturen van e-mail toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="bef12-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="bef12-128">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="bef12-128">For example:</span></span>

- <span data-ttu-id="bef12-129">[Externe domeinen om](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) het automatisch doorsturen van e-mail naar bepaalde of alle externe domeinen toe te staan of te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="bef12-129">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="bef12-130">Voorwaarden en acties in [Exchange-regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor de e-mailstroom (ook wel transportregels genoemd) om automatisch doorgestuurde berichten naar externe geadresseerden te detecteren en te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="bef12-130">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="bef12-131">Instellingen voor externe domeinen en regels voor de e-mailstroom zijn onafhankelijk van het beleid voor het filteren van uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="bef12-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="bef12-132">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="bef12-132">For example:</span></span>

- <span data-ttu-id="bef12-133">U staat automatisch doorsturen toe voor een extern domein, maar u blokkeert automatisch doorsturen in beleidsregels voor uitgaande spamfilters.</span><span class="sxs-lookup"><span data-stu-id="bef12-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="bef12-134">In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="bef12-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="bef12-135">U staat automatisch doorsturen van uitgaande spamfilterbeleid toe, maar u gebruikt regels voor de e-mailstroom of instellingen van externe domeinen om automatisch doorgestuurde e-mail te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="bef12-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="bef12-136">In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd door de regels voor de e-mailstroom of externe domeininstellingen.</span><span class="sxs-lookup"><span data-stu-id="bef12-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="bef12-137">Met deze functie onafhankelijkheid kunt u (bijvoorbeeld) automatisch doorsturen toestaan in beleidsregels voor uitgaande spamfilters, maar externe domeinen gebruiken om de externe domeinen te beheren naar wie gebruikers berichten kunnen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="bef12-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="bef12-138">Geblokkeerde doorsturen van e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="bef12-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="bef12-139">Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd en  het uitgaande [spamfilterbeleid](configure-the-outbound-spam-policy.md) die activiteit blokkeert, wordt het bericht geretourneerd aan de afzender in een NDR die de volgende informatie bevat:</span><span class="sxs-lookup"><span data-stu-id="bef12-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
