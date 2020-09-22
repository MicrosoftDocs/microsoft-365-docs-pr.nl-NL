---
title: Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hier vindt u antwoorden op de meest gestelde vragen over berichten die in de wachtrij zijn gezet, zijn uitgesteld of gestuiterd tijdens het filterproces van Exchange Online Protection (EOP).
ms.openlocfilehash: 4ae38e871c0d6e4321bd7586c5cfd0bea3aeef81
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202937"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="e576c-103">Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP</span><span class="sxs-lookup"><span data-stu-id="e576c-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e576c-104">In dit onderwerp vindt u antwoorden op veelgestelde vragen over berichten die in de wachtrij zijn gezet, zijn uitgesteld of gestuiterd tijdens het filterproces van Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e576c-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="e576c-105">Waarom is mail Queuing?</span><span class="sxs-lookup"><span data-stu-id="e576c-105">Why is mail queuing?</span></span>

<span data-ttu-id="e576c-106">Berichten worden in de wachtrij geplaatst of uitgesteld als de service geen verbinding kan maken met de ontvanger van de server.</span><span class="sxs-lookup"><span data-stu-id="e576c-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="e576c-107">Berichten worden niet weergegeven als een 500-serie-fout wordt geretourneerd via het netwerk van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="e576c-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="e576c-108">Hoe wordt een bericht uitgesteld?</span><span class="sxs-lookup"><span data-stu-id="e576c-108">How does a message become deferred?</span></span>

<span data-ttu-id="e576c-109">Berichten worden gehouden wanneer een verbinding met de server van de ontvanger niet kan worden doorgevoerd en de server van de ontvanger retourneert een tijdelijke fout, zoals een time-out voor de verbinding, een verbinding met een 400-serie.</span><span class="sxs-lookup"><span data-stu-id="e576c-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="e576c-110">Als er een permanente fout is, zoals een 500-serie-fout, wordt het bericht teruggegeven aan de afzender.</span><span class="sxs-lookup"><span data-stu-id="e576c-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="e576c-111">Hoe lang blijft een bericht in de tekst uitgesteld en wat is het interval voor opnieuw proberen?</span><span class="sxs-lookup"><span data-stu-id="e576c-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="e576c-112">Berichten in uitgesteld blijven gedurende 1 dag in onze wachtrijen.</span><span class="sxs-lookup"><span data-stu-id="e576c-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="e576c-113">De nieuwe pogingen voor het bericht worden weergegeven op basis van de fout die het e-mailsysteem van de ontvanger van de geadresseerde ontvangt.</span><span class="sxs-lookup"><span data-stu-id="e576c-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="e576c-114">De eerste paar van de uitstel tekens zijn 15 minuten of minder, met volgende nieuwe pogingen (meer dan een halve dozijn of zo) het verhogen van het interval voor meerdere pogingen tot een maximum van 60 minuten.</span><span class="sxs-lookup"><span data-stu-id="e576c-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="e576c-115">De expansie van het tijdsinterval is dynamisch, waarbij rekening moet worden gehouden met meerdere variabelen, zoals wachtrij formaten en interne berichtprioriteit.</span><span class="sxs-lookup"><span data-stu-id="e576c-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="e576c-116">In de basis is dit 15 minuten (of minder) om te beginnen en vervolgens uit te breiden tot de volgende paar uur tot 60 minuten.</span><span class="sxs-lookup"><span data-stu-id="e576c-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="e576c-117">Wanneer uw e-mailserver is hersteld, hoe worden berichten in de wachtrij gedistribueerd?</span><span class="sxs-lookup"><span data-stu-id="e576c-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="e576c-118">Nadat de e-mailserver is hersteld, worden alle berichten in de wachtrij automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij geplaatst wanneer de server niet beschikbaar was.</span><span class="sxs-lookup"><span data-stu-id="e576c-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
