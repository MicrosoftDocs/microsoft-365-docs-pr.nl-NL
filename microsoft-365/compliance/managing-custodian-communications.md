---
title: Werken met communicatie in Advanced eDiscovery
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
description: Advanced eDiscovery maakt het gemakkelijk om de werkstroom voor meldingen over juridische in- en uit te stellen over het informeren van voogden in juridische onderzoeken.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/17/2020
ms.locfileid: "52161445"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="e7c0c-103">Werken met communicatie in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e7c0c-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="e7c0c-104">Advanced eDiscovery juridische afdelingen in staat stelt om hun processen rond het bijhouden en distribueren van meldingen over juridische wacht houden te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="e7c0c-105">Met het hulpprogramma voor beheerderscommunicatie kunnen juridische afdelingen het hele proces voor juridische wacht houden beheren en automatiseren, van eerste meldingen tot herinneringen en escalaties, allemaal op één locatie.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="e7c0c-106">Wat is een melding over een wettelijke wacht houden?</span><span class="sxs-lookup"><span data-stu-id="e7c0c-106">What is a legal hold notification?</span></span>

<span data-ttu-id="e7c0c-107">Een juridische bewaartermijn (ook wel een procesrechtelijke bewaartermijn *genoemd)* is een melding die van de juridische afdeling van een organisatie wordt verzonden naar werknemers, voorwaardelijke personeelsleden of bewaarders van gegevens die relevant kunnen zijn voor een juridisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="e7c0c-108">Deze meldingen geven beheerders instructies om elektronisch opgeslagen informatie te bewaren, evenals inhoud die relevant kan zijn voor een actieve of op handen zijnde juridische kwestie.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="e7c0c-109">Juridische teams moeten weten dat elke bewaarder de opgegeven instructies heeft ontvangen, gelezen, begrepen en heeft ingestemd met het naleven van de opgegeven instructies.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="e7c0c-110">Het proces voor het in de wacht houden van de wettelijke wacht</span><span class="sxs-lookup"><span data-stu-id="e7c0c-110">The legal hold notification process</span></span>

<span data-ttu-id="e7c0c-111">Een organisatie heeft de plicht om relevante informatie te bewaren wanneer ze meer te weten komt over een naderend proces of regelgevingsonderzoek.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="e7c0c-112">Om te voldoen aan de bewaarvereisten van een onderzoek, moet de organisatie potentiële bewaarders onmiddellijk informeren over hun plicht om relevante informatie te bewaren.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="e7c0c-113">Met Advanced eDiscovery kunnen juridische teams hun meldingswerkstroom voor wettelijke wachtstatus maken en aanpassen.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="e7c0c-114">Met het hulpprogramma voor beheerderscommunicatie kunnen juridische teams de volgende kennisgevingen en werkstromen configureren:</span><span class="sxs-lookup"><span data-stu-id="e7c0c-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="e7c0c-115">**Uitgiftebericht:** Een kennisgeving van een wettelijke bewaartermijn wordt uitgegeven (of gestart) door een melding van de juridische afdeling aan bewaarders die mogelijk relevante informatie over de zaak hebben.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="e7c0c-116">In deze mededeling wordt de bewaarder in staat om alle informatie te bewaren die mogelijk nodig is voor de detectie.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="e7c0c-117">**Bericht over heruitgifte:** Tijdens een zaak kan het nodig zijn om extra inhoud (of minder inhoud) te behouden dan eerder is gevraagd.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="e7c0c-118">In dit scenario kunt u de bestaande bewaartermijn bijwerken en deze opnieuw uitgeven aan bewaarders.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="e7c0c-119">**Releasebericht:** Wanneer een zaak is opgelost en de bewaarder niet langer is onderworpen aan een bewaringsvereiste, kan de bewaarder worden vrijgegeven uit de zaak.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="e7c0c-120">Daarnaast kunt u de bewaarder laten weten dat deze niet langer verplicht is om inhoud te bewaren en instructies te geven over het hervatten van hun normale werkactiviteit met betrekking tot hun gegevens.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="e7c0c-121">**Herinneringen en escalaties:** In sommige gevallen is het niet voldoende om alleen een kennisgeving uit te geven om te voldoen aan wettelijke detectievereisten.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="e7c0c-122">Met elke melding kunnen juridische teams een set herinnerings- en escalatiewerkstromen plannen om automatisch op te volgen bij niet-reagerende bewaarders.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="e7c0c-123">**Herinneringen:** Nadat een wettelijke bewaartermijn is uitgegeven of opnieuw is uitgegeven aan een set bewaarders, kan een organisatie herinneringen instellen om niet-reagerende voogden te waarschuwen.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="e7c0c-124">**Escalaties:** In sommige gevallen kan het juridische team een escalatiewerkstroom instellen om niet-reagerende beheerders en hun manager op de hoogte te stellen als een voogd niet reageert, zelfs na een reeks herinneringen gedurende een bepaalde periode.</span><span class="sxs-lookup"><span data-stu-id="e7c0c-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="e7c0c-125">Zie het volgende voor meer informatie over het beheren van het communicatieproces voor beheerders:</span><span class="sxs-lookup"><span data-stu-id="e7c0c-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="e7c0c-126">Een kennisgeving voor een wettelijke wachttermijn maken</span><span class="sxs-lookup"><span data-stu-id="e7c0c-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="e7c0c-127">De communicatie editor gebruiken</span><span class="sxs-lookup"><span data-stu-id="e7c0c-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="e7c0c-128">Bewaringsmeldingen beheren</span><span class="sxs-lookup"><span data-stu-id="e7c0c-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="e7c0c-129">Een bewaringsmelding bevestigen</span><span class="sxs-lookup"><span data-stu-id="e7c0c-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)