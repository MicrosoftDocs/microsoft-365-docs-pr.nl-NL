---
title: Externe e-mailberichten configureren en beheren, automatisch doorsturen, 5.7.520 toegang geweigerd, externe forwarding uitschakelen, de beheerder heeft extern doorsturen uitgeschakeld, beleid voor uitgaand Antispambeleid
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 78ba5183667f4e5c6f713182969338f3ef2e7262
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600527"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="da5d2-103">Externe e-mail forwarding configureren in Office 365</span><span class="sxs-lookup"><span data-stu-id="da5d2-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="da5d2-104">Extern doorsturen wordt bepaald door het *uitgaande Antispambeleid* en de reikwijdte van de gebruikers op basis van de geconfigureerde instelling.</span><span class="sxs-lookup"><span data-stu-id="da5d2-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="da5d2-105">Momenteel worden de instellingen voor 3 weer geboden:</span><span class="sxs-lookup"><span data-stu-id="da5d2-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="da5d2-106">**Automatisch** – automatisch extern doorsturen wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="da5d2-106">**Automatic** – Automatic external forwarding is blocked.</span></span> <span data-ttu-id="da5d2-107">Interne automatisch doorsturen van berichten blijft werken.</span><span class="sxs-lookup"><span data-stu-id="da5d2-107">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="da5d2-108">Dit is de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="da5d2-108">This is the default setting.</span></span>

- <span data-ttu-id="da5d2-109">**On** -automatisch extern doorsturen is toegestaan en niet beperkt.</span><span class="sxs-lookup"><span data-stu-id="da5d2-109">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="da5d2-110">**Uitgeschakeld** – automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-uitgevoerde bezorging (NDR) voor de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="da5d2-110">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="da5d2-111">Zie [uitgaande spamfilters configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) voor meer informatie over het configureren van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="da5d2-111">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="da5d2-112">Als u automatisch doorsturen uitschakelt, worden ook regels voor het postvak in uitgeschakeld waarmee berichten naar externe adressen worden doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="da5d2-112">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="da5d2-113">Externe e-mail doorsturen beheren</span><span class="sxs-lookup"><span data-stu-id="da5d2-113">Controlling external email forwarding</span></span>

<span data-ttu-id="da5d2-114">Als beheerder van een organisatie hebt u mogelijk de mogelijkheid om te bepalen welke e-mailberichten automatisch kunnen worden doorgestuurd met behulp van regels voor Postvak in of het doorsturen van SMTP, buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="da5d2-114">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="da5d2-115">Het doorsturen van e-mail kan een handige functie zijn, maar kan ook een risico vormen via de potentiële informatie informatie, zelfs door informatie te verstrekken aan kwaadwillende gebruikers die kunnen worden gebruikt om de organisatie of haar partners te bezorgen.</span><span class="sxs-lookup"><span data-stu-id="da5d2-115">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="da5d2-116">In Office 365 is automatisch extern doorsturen niet toegestaan door regels voor Postvak in of de configuratie van het e-mailbericht, dat een veilig standaardbeleid biedt.</span><span class="sxs-lookup"><span data-stu-id="da5d2-116">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="da5d2-117">De beheerder kan deze instellingen echter wijzigen voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="da5d2-117">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="da5d2-118">Het doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door een wijziging.</span><span class="sxs-lookup"><span data-stu-id="da5d2-118">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="da5d2-119">Als u automatisch doorsturen naar externe adressen in Office 365 uitschakelt, wordt deze uitgerold in fasen met details die zijn gecommuniceerd via berichten in het [berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="da5d2-119">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="da5d2-120">Om te voorkomen dat deze wijzigingen door de beheerder worden voorgezet, kunnen ze beleidsregels op een juiste moment wijzigen om ervoor te zorgen dat hun gebruikers geen onderbrekingen hebben.</span><span class="sxs-lookup"><span data-stu-id="da5d2-120">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="da5d2-121">Meer informatie over gebruikers die automatisch doorsturen (regels voor Postvak in of het doorsturen van e-mail) in uw organisatie worden gebruikt, vindt u in het [rapport automatisch doorgestuurde berichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="da5d2-121">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="da5d2-122">Hoe werkt dit beleid met andere besturingselementen voor automatisch doorsturen</span><span class="sxs-lookup"><span data-stu-id="da5d2-122">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="da5d2-123">Als beheerder hebt u mogelijk al een ander typebesturingselement ter plaatse, zodat het automatisch doorsturen in [externe domeinen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) en het gebruik van een ETR toe (Exchange-Transport regel) wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="da5d2-123">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="da5d2-124">Beide besturingselementen zijn niet van toepassing op deze specifieke functie, bijvoorbeeld als u automatisch doorsturen wilt toestaan voor een extern domein, maar automatisch doorsturen wilt blokkeren via het uitgaande spam beleid.</span><span class="sxs-lookup"><span data-stu-id="da5d2-124">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="da5d2-125">Ook als u automatisch doorsturen in het beleid voor uitgaande spam toestaat maar dit blokkeert in een ETR toe of een extern domein, wordt het bericht geblokkeerd door een van deze besturingselementen.</span><span class="sxs-lookup"><span data-stu-id="da5d2-125">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="da5d2-126">U kunt bijvoorbeeld automatisch doorsturen in het beleid voor uitgaande spam toestaan en externe domeinen gebruiken om te bepalen met welke domeinen gebruikers automatisch berichten kunnen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="da5d2-126">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="da5d2-127">Bericht met doorsturen van geblokkeerde e-mail</span><span class="sxs-lookup"><span data-stu-id="da5d2-127">The blocked email forwarding message</span></span>

<span data-ttu-id="da5d2-128">Wanneer een bericht wordt weergegeven als automatisch doorgeschakeld en het organisatiebeleid *blokkeert* deze activiteit, wordt een **NDR-rapport (Non-Delivery Report)** weergegeven voor de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="da5d2-128">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="da5d2-129">In het rapport wordt aangegeven dat het bericht niet is afgeleverd.</span><span class="sxs-lookup"><span data-stu-id="da5d2-129">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="da5d2-130">De NDR heeft de volgende indeling:</span><span class="sxs-lookup"><span data-stu-id="da5d2-130">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
