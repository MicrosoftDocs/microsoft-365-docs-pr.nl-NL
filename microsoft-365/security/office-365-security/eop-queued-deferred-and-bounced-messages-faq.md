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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hier vindt u antwoorden op de meest voorkomende vragen over berichten die in de wachtrij zijn geplaatst, zijn uitgesteld of niet zijn gevonden tijdens het EOP-filterproces (Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 854e954e3ebb995ba23db2afc6f2ca9ab19de508
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165425"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="97c6d-103">Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP</span><span class="sxs-lookup"><span data-stu-id="97c6d-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97c6d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="97c6d-104">**Applies to**</span></span>
- [<span data-ttu-id="97c6d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97c6d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="97c6d-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="97c6d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="97c6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97c6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="97c6d-108">Dit onderwerp bevat antwoorden op veelgestelde vragen over berichten die in de wachtrij zijn geplaatst, uitgesteld of niet zijn bezorgd tijdens het filterproces van Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="97c6d-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="97c6d-109">Waarom staat e-mail in wachtrij?</span><span class="sxs-lookup"><span data-stu-id="97c6d-109">Why is mail queuing?</span></span>

<span data-ttu-id="97c6d-110">Berichten worden in de wachtrij geplaatst of uitgesteld als de service geen verbinding kan maken met de ontvangerserver voor bezorging.</span><span class="sxs-lookup"><span data-stu-id="97c6d-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="97c6d-111">Het stelt berichten niet uit als er een fout van 500 reeksen wordt geretourneerd van het netwerk van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="97c6d-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="97c6d-112">Hoe wordt een bericht uitgesteld?</span><span class="sxs-lookup"><span data-stu-id="97c6d-112">How does a message become deferred?</span></span>

<span data-ttu-id="97c6d-113">Berichten worden opgeslagen wanneer er geen verbinding kan worden gemaakt met de ontvangerserver en de server van de geadresseerde een 'tijdelijke fout' retournt, zoals een time-out van de verbinding, een verbinding geweigerd of een fout van 400 reeksen.</span><span class="sxs-lookup"><span data-stu-id="97c6d-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="97c6d-114">Als er een permanente fout is, zoals een fout van 500 reeksen, wordt het bericht geretourneerd aan de afzender.</span><span class="sxs-lookup"><span data-stu-id="97c6d-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="97c6d-115">Hoe lang blijft een bericht in de uitstelperiode staan en wat is het interval voor opnieuw proberen?</span><span class="sxs-lookup"><span data-stu-id="97c6d-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="97c6d-116">Berichten in de wachtrij blijven 1 dag in onze wachtrijen staan.</span><span class="sxs-lookup"><span data-stu-id="97c6d-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="97c6d-117">Pogingen om berichten opnieuw te proberen, zijn gebaseerd op de fout die wordt weergegeven in het e-mailsysteem van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="97c6d-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="97c6d-118">De eerste paar uitstelperioden zijn 15 minuten of minder, met volgende keren opnieuw proberen (de volgende half uur of zo) het interval over meerdere keren opnieuw tot een maximum van 60 minuten te verhogen.</span><span class="sxs-lookup"><span data-stu-id="97c6d-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="97c6d-119">De uitbreiding van de intervalduur is dynamisch, waarbij rekening wordt gehouden met meerdere variabelen, zoals de grootte van wachtrijen en interne berichtprioriteit.</span><span class="sxs-lookup"><span data-stu-id="97c6d-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="97c6d-120">In het basisprincipe is het 15 minuten (of minder) om te beginnen en vervolgens van hier uit te breiden tot maximaal 60 minuten.</span><span class="sxs-lookup"><span data-stu-id="97c6d-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="97c6d-121">Hoe worden berichten in de wachtrij gedistribueerd nadat de e-mailserver is hersteld?</span><span class="sxs-lookup"><span data-stu-id="97c6d-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="97c6d-122">Nadat de e-mailserver is hersteld, worden alle berichten in de wachtrij automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij werden geplaatst wanneer de server niet meer beschikbaar werd.</span><span class="sxs-lookup"><span data-stu-id="97c6d-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
