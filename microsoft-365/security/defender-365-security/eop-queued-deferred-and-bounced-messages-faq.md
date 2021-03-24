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
description: Antwoorden vinden op de meest voorkomende vragen over berichten die in de wachtrij zijn geplaatst, uitgesteld of zijn afgeketst tijdens het EOP-filterproces (Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060346"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="c048d-103">Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP</span><span class="sxs-lookup"><span data-stu-id="c048d-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c048d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c048d-104">**Applies to**</span></span>
- [<span data-ttu-id="c048d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c048d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c048d-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c048d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c048d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c048d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c048d-108">Dit onderwerp bevat antwoorden op veelgestelde vragen over berichten die in de wachtrij zijn geplaatst, uitgesteld of zijn afgeketst tijdens het EOP-filterproces (Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="c048d-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="c048d-109">Waarom staat e-mail in de wachtrij?</span><span class="sxs-lookup"><span data-stu-id="c048d-109">Why is mail queuing?</span></span>

<span data-ttu-id="c048d-110">Berichten worden in de wachtrij geplaatst of uitgesteld als de service geen verbinding kan maken met de geadresseerdeserver voor bezorging.</span><span class="sxs-lookup"><span data-stu-id="c048d-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="c048d-111">Berichten worden niet uitgesteld als er een fout van 500 reeksen wordt geretourneerd vanuit het netwerk van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="c048d-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="c048d-112">Hoe wordt een bericht uitgesteld?</span><span class="sxs-lookup"><span data-stu-id="c048d-112">How does a message become deferred?</span></span>

<span data-ttu-id="c048d-113">Berichten worden opgeslagen wanneer er geen verbinding kan worden gemaakt met de server van de geadresseerde en de server van de geadresseerde een 'tijdelijke fout' retournt, zoals een time-out van de verbinding, geweigerde verbinding of een fout in de 400-reeks.</span><span class="sxs-lookup"><span data-stu-id="c048d-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="c048d-114">Als er een permanente fout is, zoals een fout van 500 reeksen, wordt het bericht geretourneerd aan de afzender.</span><span class="sxs-lookup"><span data-stu-id="c048d-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="c048d-115">Hoe lang blijft een bericht in de uitstelperiode staan en wat is het interval voor het opnieuw proberen?</span><span class="sxs-lookup"><span data-stu-id="c048d-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="c048d-116">Berichten in uitstel blijven 1 dag in onze wachtrijen staan.</span><span class="sxs-lookup"><span data-stu-id="c048d-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="c048d-117">Pogingen voor het opnieuw proberen van berichten zijn gebaseerd op de fout die we krijgen van het e-mailsysteem van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="c048d-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="c048d-118">De eerste paar uitstelperioden zijn 15 minuten of minder, met de volgende wijzigingen (in de komende zes maanden) waardoor het interval over meerdere hervervolgingen wordt oplopende tot maximaal 60 minuten.</span><span class="sxs-lookup"><span data-stu-id="c048d-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="c048d-119">De uitbreiding van de intervalduur is dynamisch, waarbij rekening wordt gehouden met meerdere variabelen, zoals wachtrijgrootten en interne berichtprioriteit.</span><span class="sxs-lookup"><span data-stu-id="c048d-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="c048d-120">In de basis is het 15 minuten (of minder) om te beginnen en vervolgens in de komende uren uit te breiden tot max 60 minuten.</span><span class="sxs-lookup"><span data-stu-id="c048d-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="c048d-121">Hoe worden berichten in de wachtrij verdeeld nadat uw e-mailserver is hersteld?</span><span class="sxs-lookup"><span data-stu-id="c048d-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="c048d-122">Nadat uw e-mailserver is hersteld, worden alle wachtrijberichten automatisch verwerkt in de volgorde waarin ze zijn ontvangen en in de wachtrij staan wanneer de server niet beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="c048d-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
