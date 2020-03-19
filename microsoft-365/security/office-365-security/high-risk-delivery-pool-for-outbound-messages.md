---
title: Een risicovolle leveringsgroep voor uitgaande berichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Wanneer het e-mailsysteem van een klant is gecompromitteerd door malware of een kwaadaardige spamaanval en het uitgaande spam verzendt via de gehoste filterservice, kan dit ertoe leiden dat de IP-adressen van de Office 365-datacenterservers worden vermeld op blok van derden Lijsten.
ms.openlocfilehash: 19987ae74b9c78a796ddb5f13cf8291a5ed269ad
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805479"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="f08e4-103">Een risicovolle leveringsgroep voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="f08e4-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="f08e4-104">Wanneer het e-mailsysteem van een klant is gecompromitteerd door malware of een kwaadaardige spamaanval en het uitgaande spam verzendt via de gehoste filterservice, kan dit ertoe leiden dat de IP-adressen van de Office 365-datacenterservers worden vermeld op blok van derden Lijsten.</span><span class="sxs-lookup"><span data-stu-id="f08e4-104">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists.</span></span> <span data-ttu-id="f08e4-105">Doelservers die de gehoste filterservice niet gebruiken, maar deze bloklijsten wel gebruiken, weigeren alle e-mail die is verzonden vanaf een van de gehoste filterIP-adressen die aan die lijsten zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="f08e4-105">Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists.</span></span> <span data-ttu-id="f08e4-106">Om dit te voorkomen, worden alle uitgaande berichten die de spamdrempel overschrijden, verzonden via een groep met een hoog risico.To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool.</span><span class="sxs-lookup"><span data-stu-id="f08e4-106">To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool.</span></span> <span data-ttu-id="f08e4-107">Deze secundaire uitgaande e-mailgroep wordt alleen gebruikt om berichten te verzenden die van lage kwaliteit kunnen zijn.</span><span class="sxs-lookup"><span data-stu-id="f08e4-107">This secondary outbound email pool is only used to send messages that may be of low quality.</span></span> <span data-ttu-id="f08e4-108">Dit helpt om de rest van het netwerk te beschermen tegen het verzenden van berichten die waarschijnlijk ertoe leiden dat het verzenden van IP-adres wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="f08e4-108">This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="f08e4-109">Het gebruik van een speciale groep met een hoog risico zorgt ervoor dat de normale uitgaande pool alleen berichten verzendt waarvan bekend is dat ze van hoge kwaliteit zijn.</span><span class="sxs-lookup"><span data-stu-id="f08e4-109">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality.</span></span> <span data-ttu-id="f08e4-110">Het gebruik van deze secundaire IP-pool helpt om de kans te verkleinen dat de normale uitgaande IP-groep wordt toegevoegd aan een geblokkeerde lijst.</span><span class="sxs-lookup"><span data-stu-id="f08e4-110">Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list.</span></span> <span data-ttu-id="f08e4-111">De mogelijkheid dat de risicovolle bezorgpool op een geblokkeerde lijst wordt geplaatst, blijft een risico.</span><span class="sxs-lookup"><span data-stu-id="f08e4-111">The possibility of the high-risk delivery pool being placed on a blocked list remains a risk.</span></span> <span data-ttu-id="f08e4-112">Dit is normaal.</span><span class="sxs-lookup"><span data-stu-id="f08e4-112">This is by design.</span></span>
  
<span data-ttu-id="f08e4-113">Berichten waarin het verzendende domein geen adresrecord (A-record) heeft, waardoor u het IP-adres van het domein krijgt en geen MX-record, waarmee direct mail wordt verzonden naar de servers die de e-mail moeten ontvangen voor een bepaald domein in de DNS, worden altijd door de een risicovolle bezorgpool, ongeacht hun spampositie.</span><span class="sxs-lookup"><span data-stu-id="f08e4-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="f08e4-114">DSN-berichten (Delivery Status Notification) begrijpen</span><span class="sxs-lookup"><span data-stu-id="f08e4-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="f08e4-115">De uitgaande groep met een hoog risico beheert de levering voor alle "bounced" of "failed" (DSN) berichten.</span><span class="sxs-lookup"><span data-stu-id="f08e4-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="f08e4-116">Mogelijke oorzaken voor een piek in DSN-berichten zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="f08e4-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="f08e4-117">Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken</span><span class="sxs-lookup"><span data-stu-id="f08e4-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="f08e4-118">Een directory oogst aanval</span><span class="sxs-lookup"><span data-stu-id="f08e4-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="f08e4-119">Een spamaanval</span><span class="sxs-lookup"><span data-stu-id="f08e4-119">A spam attack</span></span>
    
- <span data-ttu-id="f08e4-120">Een malafide SMTP-server</span><span class="sxs-lookup"><span data-stu-id="f08e4-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="f08e4-121">Al deze problemen kunnen leiden tot een plotselinge toename van het aantal DSN-berichten dat door de service wordt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="f08e4-121">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service.</span></span> <span data-ttu-id="f08e4-122">Vaak lijken deze DSN-berichten spam te zijn voor andere e-mailservers en -services.</span><span class="sxs-lookup"><span data-stu-id="f08e4-122">Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="f08e4-123">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="f08e4-123">For more information</span></span>

[<span data-ttu-id="f08e4-124">Het uitgaande spambeleid configureren</span><span class="sxs-lookup"><span data-stu-id="f08e4-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="f08e4-125">Veelgestelde vragen over antispambescherming</span><span class="sxs-lookup"><span data-stu-id="f08e4-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

