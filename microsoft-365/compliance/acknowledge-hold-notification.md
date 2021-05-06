---
title: Een bewaringsmelding bevestigen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Informatie over het gebruik van Advanced eDiscovery om meldingen over wettelijke wachtposities te verzenden en op te volgen via e-mail, en hoe u de status van de verplichting kunt controleren.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "52161457"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="eca95-103">Een bewaringsmelding bevestigen</span><span class="sxs-lookup"><span data-stu-id="eca95-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="eca95-104">Wanneer u reageert op een regelgevend verzoek of onderzoek, moet u mogelijk de bewaarders informeren over hun verplichting om elektronisch opgeslagen gegevens (ESI) te bewaren en materiaal dat relevant kan zijn voor een actieve of op handen zijnde juridische kwestie.</span><span class="sxs-lookup"><span data-stu-id="eca95-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="eca95-105">Zodra deze zijn verzonden, moeten juridische teams weten dat elke bewaarder de opgegeven instructies heeft ontvangen, gelezen, begrepen en heeft ingestemd met het volgen van de opgegeven instructies.</span><span class="sxs-lookup"><span data-stu-id="eca95-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="eca95-106">Om de tijd, kosten en moeite van het volgen met uw beheerders te verminderen, kunt u Advanced eDiscovery meldingen over juridische wacht houden verzenden en volgen via e-mail.</span><span class="sxs-lookup"><span data-stu-id="eca95-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="eca95-107">Naast e-mailmeldingen heeft elke bewaarder toegang tot een individuele complianceportal, zodat bewaarders op de hoogte kunnen worden gehouden van wijzigingen in hun verplichtingsstatus.</span><span class="sxs-lookup"><span data-stu-id="eca95-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="eca95-108">E-mailmeldingen</span><span class="sxs-lookup"><span data-stu-id="eca95-108">Email notifications</span></span>

<span data-ttu-id="eca95-109">Nadat een melding voor wettelijke bewaartermijn is uitgegeven, ontvangt elke bewaarder een unieke en persoonlijke e-mail met uw gedefinieerde kennisgeving van wettelijke bewaartermijn en toegevoegde instructies.</span><span class="sxs-lookup"><span data-stu-id="eca95-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="eca95-110">Bekijk hoe u de ingebouwde  [Communicatie-editor](using-communications-editor.md) kunt gebruiken om uw beheerders in staat te stellen hun kennisgeving te bevestigen of rechtstreeks vanuit hun e-mail toegang te krijgen tot hun complianceportal.</span><span class="sxs-lookup"><span data-stu-id="eca95-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="eca95-111">Op basis van de configuratie van uw melding over de wettelijke bewaartermijn kunnen uw bewaarders de volgende kennisgevingen ontvangen:</span><span class="sxs-lookup"><span data-stu-id="eca95-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="eca95-112">**Uitgiftebericht:** De eerste kennisgeving die naar uw voogd is verzonden.</span><span class="sxs-lookup"><span data-stu-id="eca95-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="eca95-113">Deze melding bevat de uitgifte-instructies en de aan het einde van het bericht toegevoegd aan de wachttermijn.</span><span class="sxs-lookup"><span data-stu-id="eca95-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="eca95-114">**Herinneringsbericht:** Als dit is ingeschakeld, wordt er een herinneringsbericht verzonden naar uw beheerders op basis van de opgegeven frequentie en het interval.</span><span class="sxs-lookup"><span data-stu-id="eca95-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="eca95-115">De herinneringen blijven worden verzonden totdat de bewaarder zijn kennisgeving heeft bevestigd of totdat het aantal herinneringen is opgebruikt.</span><span class="sxs-lookup"><span data-stu-id="eca95-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="eca95-116">**Melding escalatie:** Als dit is ingeschakeld, wordt er een escalatiebericht verzonden naar uw voogd en hun manager nadat de herinneringsopzegingen zijn opgebruikt.</span><span class="sxs-lookup"><span data-stu-id="eca95-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="eca95-117">Het systeem verzendt automatisch escalatiemeldingen totdat het opgegeven aantal escalaties is voltooid of totdat de bewaarder de melding van de bewaartermijn heeft bevestigd.</span><span class="sxs-lookup"><span data-stu-id="eca95-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="eca95-118">**Kennisgeving heruitgave:** Als tijdens een onderzoek de inhoud van de bewaartermijn wordt bijgewerkt, wordt de bijgewerkte melding automatisch naar de bewaarder verzonden.</span><span class="sxs-lookup"><span data-stu-id="eca95-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="eca95-119">**Releasebericht:** Wanneer een bewaarder uit de zaak wordt vrijgelaten, wordt deze de releaseverklaring verzonden.</span><span class="sxs-lookup"><span data-stu-id="eca95-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="eca95-120">Complianceportal</span><span class="sxs-lookup"><span data-stu-id="eca95-120">Compliance Portal</span></span>

<span data-ttu-id="eca95-121">Naast de e-mailmeldingen heeft elke bewaarder toegang tot een unieke complianceportal.</span><span class="sxs-lookup"><span data-stu-id="eca95-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="eca95-122">Via de portal kan elke bewaarder meldingen voor actieve wacht houden bekijken, openen en bevestigen.</span><span class="sxs-lookup"><span data-stu-id="eca95-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Complianceportal voor een bewaarder](../media/CustodianPortal.jpg)
