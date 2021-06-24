---
title: Bericht traceren in de Microsoft 365 Defender portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen de koppeling Bericht traceren gebruiken in de Microsoft 365 Defender portal om erachter te komen wat er met berichten is gebeurd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108125"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="45267-103">Bericht traceren in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="45267-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="45267-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="45267-104">**Applies to**</span></span>
- [<span data-ttu-id="45267-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="45267-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="45267-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="45267-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="45267-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45267-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="45267-108">Berichtspoor in de Microsoft 365 Defender portal volgt e-mailberichten terwijl ze door uw Exchange Online reizen.</span><span class="sxs-lookup"><span data-stu-id="45267-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="45267-109">U kunt bepalen of een bericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service.</span><span class="sxs-lookup"><span data-stu-id="45267-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="45267-110">Ook wordt weergegeven welke acties zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="45267-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="45267-111">U kunt de informatie uit bericht traceren gebruiken om gebruikersvragen efficiënt te beantwoorden over wat er met berichten is gebeurd, problemen met de e-mailstroom op te lossen en beleidswijzigingen te valideren.</span><span class="sxs-lookup"><span data-stu-id="45267-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="45267-112">Berichtspoor in de Microsoft 365 Defender portal is slechts een doorspoort naar Bericht traceren in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="45267-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="45267-113">Zie Bericht traceren in het moderne Exchange [beheercentrum voor meer informatie.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="45267-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45267-114">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="45267-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45267-115">U moet lid zijn van de rollengroepen **Organisatiebeheer,** **Compliancebeheer** of **Helpdesk** **in** Exchange Online om bericht traceren te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="45267-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="45267-116">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="45267-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="45267-117">**Opmerkingen:** Lidmaatschap van de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft  gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45267-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="45267-118">Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="45267-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="45267-119">Het maximum aantal berichten dat wordt weergegeven in de resultaten van een berichtspoor, is afhankelijk van het rapporttype dat u hebt geselecteerd (zie de sectie [Rapporttype](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) kiezen voor meer informatie).</span><span class="sxs-lookup"><span data-stu-id="45267-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="45267-120">De [cmdlet Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell of zelfstandige EOP PowerShell retourneert alle berichten in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="45267-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="45267-121">Bericht traceren openen</span><span class="sxs-lookup"><span data-stu-id="45267-121">Open message trace</span></span>

<span data-ttu-id="45267-122">Ga in Microsoft 365 Defender portal ( ) naar <https://security.microsoft.com> **E-mail & samenwerking** \> **Exchange bericht traceren.**</span><span class="sxs-lookup"><span data-stu-id="45267-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="45267-123">Of als u rechtstreeks naar de pagina bericht traceren wilt gaan, gebruikt <https://admin.exchange.microsoft.com/#/messagetrace> u .</span><span class="sxs-lookup"><span data-stu-id="45267-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="45267-124">Op dit moment wordt berichtspoor in het EAC geopend.</span><span class="sxs-lookup"><span data-stu-id="45267-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="45267-125">Zie Bericht traceren in het moderne Exchange [beheercentrum voor meer informatie.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="45267-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
