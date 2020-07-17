---
title: Externe e-mail doorsturen configureren en beheren, Automatisch doorsturen, 5.7.520 Access Denied, uitschakelen van extern doorsturen, Uw beheerder heeft extern doorsturen uitgeschakeld, uitgaand antispambeleid
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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080111"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="8951a-103">Externe e-mail doorsturen configureren in Office 365</span><span class="sxs-lookup"><span data-stu-id="8951a-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="8951a-104">Extern doorsturen wordt beheerd door het *uitgaande antispambeleid* en scoped naar gebruikers op basis van de geconfigureerde instelling.</span><span class="sxs-lookup"><span data-stu-id="8951a-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="8951a-105">Momenteel worden 3 instellingen ondersteund:</span><span class="sxs-lookup"><span data-stu-id="8951a-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="8951a-106">**Automatisch** - In deze modus is het systeem verantwoordelijk voor de beslissing of een doorgestuurd bericht is toegestaan of niet.</span><span class="sxs-lookup"><span data-stu-id="8951a-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="8951a-107">Dit is de standaardmodus en in deze modus blokkeert het systeem automatisch extern doorsturen.</span><span class="sxs-lookup"><span data-stu-id="8951a-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="8951a-108">**Aan** – Automatisch extern doorsturen is toegestaan en niet beperkt.</span><span class="sxs-lookup"><span data-stu-id="8951a-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="8951a-109">**Uit** - Automatisch extern doorsturen is uitgeschakeld en resulteert in een Non-delivery report (NDR) aan de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="8951a-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="8951a-110">Zie [Uitgaande spamfiltering configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) voor meer informatie over het configureren van deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="8951a-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="8951a-111">Externe e-mail doorsturen beheren</span><span class="sxs-lookup"><span data-stu-id="8951a-111">Controlling external email forwarding</span></span>

<span data-ttu-id="8951a-112">Als beheerder van een organisatie u bedrijfsvereisten hebben om te beperken of te bepalen wie e-mails automatisch kan doorsturen met behulp van inboxregels of SMTP-doorsturen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8951a-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="8951a-113">E-mail doorsturen kan een nuttige functie zijn, maar kan ook een risico vormen door de mogelijke openbaarmaking van informatie, zelfs door het verstrekken van informatie aan aanvallers die kunnen worden gebruikt om de organisatie of haar partners aan te vallen.</span><span class="sxs-lookup"><span data-stu-id="8951a-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="8951a-114">Office 365 staat geen automatische externe doorschakeling toe via inboxregels of postvakconfiguratie, wat een veilig standaardbeleid biedt.</span><span class="sxs-lookup"><span data-stu-id="8951a-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="8951a-115">De beheerder kan deze instellingen echter wijzigen voor alle of sommige gebruikers in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8951a-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="8951a-116">Het doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door een dergelijke wijziging.</span><span class="sxs-lookup"><span data-stu-id="8951a-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="8951a-117">Het uitschakelen van automatisch doorsturen naar externe adressen in Office 365 wordt gefaseerd uitgerold, waarbij details worden gecommuniceerd via [berichten in het Berichtencentrum.](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="8951a-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="8951a-118">Om beheerders te helpen zich voor te bereiden op deze wijzigingen, moet u het beleid van tevoren wijzigen om ervoor te zorgen dat er geen verstoring is voor hun gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8951a-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="8951a-119">Meer informatie over gebruikers die automatisch doorsturen gebruiken (regels voor inbox of SMTP-doorsturen) in uw organisatie, vindt u in het [rapport automatisch doorgestuurde berichten.](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="8951a-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="8951a-120">Het geblokkeerde e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="8951a-120">The blocked email forwarding message</span></span>

<span data-ttu-id="8951a-121">Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd en het organisatiebeleid *blokkeert* dat de activiteit een **Non-delivery rapport (NDR)** zal worden gegenereerd terug naar de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="8951a-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="8951a-122">Het rapport geeft aan dat het bericht niet is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="8951a-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="8951a-123">De NDR heeft de volgende indeling:</span><span class="sxs-lookup"><span data-stu-id="8951a-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
