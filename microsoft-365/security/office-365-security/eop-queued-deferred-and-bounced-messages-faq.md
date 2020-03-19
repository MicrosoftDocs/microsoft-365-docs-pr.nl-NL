---
title: Veelgestelde vragen over eop-wachtrijen, uitgestelde en teruggestuurde berichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: In dit onderwerp vindt u antwoorden op veelgestelde vragen over berichten die in de wachtrij staan, uitgesteld of teruggestuurd zijn tijdens het EOP-filterproces (Microsoft Exchange Online Protection).
ms.openlocfilehash: 05993e8d0e9af69dd1ac35b588c4e8ec731642f7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810217"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="682b4-103">Veelgestelde vragen over eop-wachtrijen, uitgestelde en teruggestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="682b4-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="682b4-104">In dit onderwerp vindt u antwoorden op veelgestelde vragen over berichten die in de wachtrij staan, uitgesteld of teruggestuurd zijn tijdens het EOP-filterproces (Microsoft Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="682b4-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>

<span data-ttu-id="682b4-105">**V. Waarom staat post in de rij?**</span><span class="sxs-lookup"><span data-stu-id="682b4-105">**Q. Why is mail queuing?**</span></span>

<span data-ttu-id="682b4-106">A.</span><span class="sxs-lookup"><span data-stu-id="682b4-106">A.</span></span> <span data-ttu-id="682b4-107">Berichten worden in de wachtrij of uitgesteld als de service geen verbinding kan maken met de server met de geadresseerde voor levering.</span><span class="sxs-lookup"><span data-stu-id="682b4-107">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="682b4-108">Het zal berichten niet uitstellen als een 500-serie fout wordt geretourneerd van het netwerk van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="682b4-108">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

<span data-ttu-id="682b4-109">**V. Hoe wordt een bericht uitgesteld?**</span><span class="sxs-lookup"><span data-stu-id="682b4-109">**Q. How does a message become deferred?**</span></span>

<span data-ttu-id="682b4-110">A.</span><span class="sxs-lookup"><span data-stu-id="682b4-110">A.</span></span> <span data-ttu-id="682b4-111">Berichten worden bewaard wanneer een verbinding met de server met de ontvanger niet kan worden gemaakt en de server van de ontvanger een "tijdelijke fout" retoureert, zoals een time-out van de verbinding, geweigerde verbinding of een fout van 400-serie.</span><span class="sxs-lookup"><span data-stu-id="682b4-111">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="682b4-112">Als er een permanente fout optreedt, zoals een fout van 500-reeksen, wordt het bericht teruggestuurd naar de afzender.</span><span class="sxs-lookup"><span data-stu-id="682b4-112">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

<span data-ttu-id="682b4-113">**V. Hoe lang blijft een bericht in uitstel en wat is het interval voor het opnieuw proberen?**</span><span class="sxs-lookup"><span data-stu-id="682b4-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>

<span data-ttu-id="682b4-114">A.</span><span class="sxs-lookup"><span data-stu-id="682b4-114">A.</span></span> <span data-ttu-id="682b4-115">Berichten in uitstel blijven 1 dag in onze wachtrijen staan.</span><span class="sxs-lookup"><span data-stu-id="682b4-115">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="682b4-116">Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we terugkrijgen van het e-mailsysteem van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="682b4-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="682b4-117">De eerste paar uitstel zijn 15 minuten of minder, met latere pogingen (in de komende half dozijn of zo) het verhogen van het interval over meerdere pogingen tot een maximum van 60 minuten.</span><span class="sxs-lookup"><span data-stu-id="682b4-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="682b4-118">De uitbreiding van de intervalduur is dynamisch, rekening houdend met meerdere variabelen, zoals wachtrijformaten en interne berichtprioriteit.</span><span class="sxs-lookup"><span data-stu-id="682b4-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="682b4-119">In principe is het 15 minuten (of minder) om te beginnen, dan uit te breiden vanaf daar in de komende uren tot 60 minuten max.</span><span class="sxs-lookup"><span data-stu-id="682b4-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

<span data-ttu-id="682b4-120">**V. Hoe worden berichten in de wachtrij gedistribueerd nadat uw e-mailserver is hersteld?**</span><span class="sxs-lookup"><span data-stu-id="682b4-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>

<span data-ttu-id="682b4-121">A.</span><span class="sxs-lookup"><span data-stu-id="682b4-121">A.</span></span> <span data-ttu-id="682b4-122">Nadat uw e-mailserver is hersteld, worden alle in de wachtrij staande berichten automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij stonden toen de server niet beschikbaar was.</span><span class="sxs-lookup"><span data-stu-id="682b4-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
