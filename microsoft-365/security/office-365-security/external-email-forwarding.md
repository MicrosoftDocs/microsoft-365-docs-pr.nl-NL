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
ms.openlocfilehash: f729aa816caf8fb07499037ee27fbfc37b7205b3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202877"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="8b048-103">Externe e-mail forwarding configureren in Office 365</span><span class="sxs-lookup"><span data-stu-id="8b048-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8b048-104">Extern doorsturen wordt bepaald door het *uitgaande Antispambeleid* en de reikwijdte van de gebruikers op basis van de geconfigureerde instelling.</span><span class="sxs-lookup"><span data-stu-id="8b048-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="8b048-105">Momenteel worden de instellingen voor 3 weer geboden:</span><span class="sxs-lookup"><span data-stu-id="8b048-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="8b048-106">**Automatisch** : in deze modus is het systeem verantwoordelijk voor het bepalen of een doorgestuurd bericht wel of niet is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="8b048-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="8b048-107">Dit is de standaardmodus en in deze modus wordt het automatisch extern doorsturen van het systeem blokkeren.</span><span class="sxs-lookup"><span data-stu-id="8b048-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="8b048-108">**On** -automatisch extern doorsturen is toegestaan en niet beperkt.</span><span class="sxs-lookup"><span data-stu-id="8b048-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="8b048-109">**Uitgeschakeld** – automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-uitgevoerde bezorging (NDR) voor de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="8b048-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="8b048-110">Zie [uitgaande spamfilters configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) voor meer informatie over het configureren van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="8b048-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="8b048-111">Als u automatisch doorsturen uitschakelt, worden ook regels voor het postvak in van berichten naar externe adressen dsable.</span><span class="sxs-lookup"><span data-stu-id="8b048-111">Disabling automatic forwarding will also dsable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="8b048-112">Externe e-mail doorsturen beheren</span><span class="sxs-lookup"><span data-stu-id="8b048-112">Controlling external email forwarding</span></span>

<span data-ttu-id="8b048-113">Als beheerder van een organisatie hebt u mogelijk de mogelijkheid om te bepalen welke e-mailberichten automatisch kunnen worden doorgestuurd met behulp van regels voor Postvak in of het doorsturen van SMTP, buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8b048-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="8b048-114">Het doorsturen van e-mail kan een handige functie zijn, maar kan ook een risico vormen via de potentiële informatie informatie, zelfs door informatie te verstrekken aan kwaadwillende gebruikers die kunnen worden gebruikt om de organisatie of haar partners te bezorgen.</span><span class="sxs-lookup"><span data-stu-id="8b048-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="8b048-115">In Office 365 is automatisch extern doorsturen niet toegestaan door regels voor Postvak in of de configuratie van het e-mailbericht, dat een veilig standaardbeleid biedt.</span><span class="sxs-lookup"><span data-stu-id="8b048-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="8b048-116">De beheerder kan deze instellingen echter wijzigen voor alle gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8b048-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="8b048-117">Het doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door een wijziging.</span><span class="sxs-lookup"><span data-stu-id="8b048-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="8b048-118">Als u automatisch doorsturen naar externe adressen in Office 365 uitschakelt, wordt deze uitgerold in fasen met details die zijn gecommuniceerd via berichten in het [berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="8b048-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="8b048-119">Om te voorkomen dat deze wijzigingen door de beheerder worden voorgezet, kunnen ze beleidsregels op een juiste moment wijzigen om ervoor te zorgen dat hun gebruikers geen onderbrekingen hebben.</span><span class="sxs-lookup"><span data-stu-id="8b048-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="8b048-120">Meer informatie over gebruikers die automatisch doorsturen (regels voor Postvak in of het doorsturen van e-mail) in uw organisatie worden gebruikt, vindt u in het [rapport automatisch doorgestuurde berichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="8b048-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="8b048-121">Hoe werkt dit beleid met andere besturingselementen voor automatisch doorsturen</span><span class="sxs-lookup"><span data-stu-id="8b048-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="8b048-122">Als beheerder hebt u mogelijk al een ander typebesturingselement ter plaatse, zodat het automatisch doorsturen in [externe domeinen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) en het gebruik van een ETR toe (Exchange-Transport regel) wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="8b048-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="8b048-123">Beide besturingselementen zijn niet van toepassing op deze specifieke functie, bijvoorbeeld als u automatisch doorsturen wilt toestaan voor een extern domein, maar automatisch doorsturen wilt blokkeren via het uitgaande spam beleid.</span><span class="sxs-lookup"><span data-stu-id="8b048-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="8b048-124">Ook als u automatisch doorsturen in het beleid voor uitgaande spam toestaat maar dit blokkeert in een ETR toe of een extern domein, wordt het bericht geblokkeerd door een van deze besturingselementen.</span><span class="sxs-lookup"><span data-stu-id="8b048-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="8b048-125">U kunt bijvoorbeeld automatisch doorsturen in het beleid voor uitgaande spam toestaan en externe domeinen gebruiken om te bepalen met welke domeinen gebruikers automatisch berichten kunnen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="8b048-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="8b048-126">Bericht met doorsturen van geblokkeerde e-mail</span><span class="sxs-lookup"><span data-stu-id="8b048-126">The blocked email forwarding message</span></span>

<span data-ttu-id="8b048-127">Wanneer een bericht wordt weergegeven als automatisch doorgeschakeld en het organisatiebeleid *blokkeert* deze activiteit, wordt een **NDR-rapport (Non-Delivery Report)** weergegeven voor de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="8b048-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="8b048-128">In het rapport wordt aangegeven dat het bericht niet is afgeleverd.</span><span class="sxs-lookup"><span data-stu-id="8b048-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="8b048-129">De NDR heeft de volgende indeling:</span><span class="sxs-lookup"><span data-stu-id="8b048-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
