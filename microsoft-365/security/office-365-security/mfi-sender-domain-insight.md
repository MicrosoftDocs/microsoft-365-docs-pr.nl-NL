---
title: Inzicht in verzenddomein herstellen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen meer te weten komen over het inzicht in het domeinvan de afzender in het dashboard voor e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: 2db1b971ef39f8b207b349ca53237ff87cc9193e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810226"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="b3652-103">Inzicht in verzenddomein herstellen</span><span class="sxs-lookup"><span data-stu-id="b3652-103">Fix sender domain insight</span></span>

<span data-ttu-id="b3652-104">Office 365 vereist dat berichten die vanuit interne on-premises e-mailomgevingen naar Office 365 worden verzonden, voldoen aan bepaalde beveiligingscriteria:</span><span class="sxs-lookup"><span data-stu-id="b3652-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="b3652-105">U hebt een binnenkomende connector in Office 365 gemaakt om SMTP-verbindingen vanaf uw on-premises e-mailserver te verifiëren met behulp van het bron-IP-adres of een certificaat.</span><span class="sxs-lookup"><span data-stu-id="b3652-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="b3652-106">U hebt uw on-premises e-mailserver geconfigureerd om e-mail via Office 365 door te sturen naar de buitenwereld.</span><span class="sxs-lookup"><span data-stu-id="b3652-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="b3652-107">In uw configuratie geldt een van de volgende uitspraken:</span><span class="sxs-lookup"><span data-stu-id="b3652-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="b3652-108">Het e-maildomein van de afzender is geregistreerd in uw Office 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="b3652-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="b3652-109">Zie Domeinen toevoegen in Office 365 voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3652-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="b3652-110">Uw on-premises e-mailserver is geconfigureerd om een certificaat te gebruiken om e-mail naar Office 365 te verzenden, het certificaat bevat of komt precies overeen met een domeinnaam die u hebt geregistreerd in Office 365 en u hebt daarmee een op certificaten gebaseerde connector in Office 365 gemaakt Domein.</span><span class="sxs-lookup"><span data-stu-id="b3652-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="b3652-111">Berichten die niet aan de criteria voldoen, worden niet aan de organisatie toegeschreven en kunnen worden afgewezen.</span><span class="sxs-lookup"><span data-stu-id="b3652-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="b3652-112">Het inzicht in het domein van **de afzender fix** toont u e-mail vanuit uw on-premises omgeving die niet aan de criteria voldoet, helpt u om mogelijk gecompromitteerde machines en gebruikersaccounts in uw on-premises e-mailomgeving te identificeren en helpt u bij het uitvoeren van herstelacties.</span><span class="sxs-lookup"><span data-stu-id="b3652-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![Het inzicht van het verzenddomein oplossen in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="b3652-114">Wanneer u op **Details weergeven**klikt, wordt u naar een andere widget geleid met meer details zoals weergegeven in het volgende diagram:</span><span class="sxs-lookup"><span data-stu-id="b3652-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![De widget Details in het inzicht van het afzenderdomein herstellen](../../media/sender-domain-view-details.png)

<span data-ttu-id="b3652-116">U ziet de binnenkomende connector die is gebruikt om de berichten naar Office 365 te leveren.</span><span class="sxs-lookup"><span data-stu-id="b3652-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="b3652-117">U ook op **voorbeeldbericht-id's weergeven** klikken om details te zien voor de berichten die vanuit uw e-mailomgeving ter plaatse zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="b3652-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="b3652-118">Omdat deze berichten zijn geweigerd door Office 365, u geen berichttracering gebruiken, maar u de voorbeeldbericht-id's gebruiken om de berichten in uw on-premises e-mailomgeving bij te houden.</span><span class="sxs-lookup"><span data-stu-id="b3652-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Voorbeeldbericht-id's weergeven in het inzicht van het afzenderdomein herstellen](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="b3652-120">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b3652-120">See also</span></span>

<span data-ttu-id="b3652-121">Zie Inzichten in de [stroomstromen in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroom-inzichten in het dashboard voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="b3652-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
