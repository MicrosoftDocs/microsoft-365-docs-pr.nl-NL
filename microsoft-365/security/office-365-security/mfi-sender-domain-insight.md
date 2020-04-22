---
title: Inzicht in verzenddomein oplossen
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
description: Beheerders kunnen meer te weten komen over het domeininzicht voor de afzender in het dashboard met e-mailstromen in het Security & Compliance Center.
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635170"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="b609c-103">Inzicht in verzenddomein oplossen</span><span class="sxs-lookup"><span data-stu-id="b609c-103">Fix sender domain insight</span></span>

<span data-ttu-id="b609c-104">Microsoft 365 vereist dat berichten die vanuit interne on-premises e-mailomgevingen naar Microsoft 365 worden verzonden, aan bepaalde beveiligingscriteria voldoen:</span><span class="sxs-lookup"><span data-stu-id="b609c-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="b609c-105">U hebt een binnenkomende connector in Microsoft 365 gemaakt om SMTP-verbindingen te verifiëren vanaf uw on-premises e-mailserver met behulp van het bron-IP-adres of een certificaat.</span><span class="sxs-lookup"><span data-stu-id="b609c-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="b609c-106">U hebt uw on-premises e-mailserver geconfigureerd om e-mail via Microsoft 365 door te sturen naar de buitenwereld.</span><span class="sxs-lookup"><span data-stu-id="b609c-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="b609c-107">In uw configuratie is een van de volgende uitspraken waar:</span><span class="sxs-lookup"><span data-stu-id="b609c-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="b609c-108">Het e-maildomein van de afzender is geregistreerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b609c-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="b609c-109">Zie Domeinen toevoegen in Office 365 voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b609c-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="b609c-110">Uw on-premises e-mailserver is geconfigureerd om een certificaat te gebruiken om e-mail naar Microsoft 365 te verzenden, het certificaat bevat of komt precies overeen met een domeinnaam die u hebt geregistreerd in Microsoft 365 en u hebt een op certificaten gebaseerde connector in Microsoft 365 met dat domein gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b609c-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="b609c-111">Berichten die niet aan de criteria voldoen, worden niet aan de organisatie toegeschreven en kunnen worden afgewezen.</span><span class="sxs-lookup"><span data-stu-id="b609c-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="b609c-112">Het domeininzicht **Voor afzenderen** van de oplossing toont u e-mail vanuit uw on-premises omgeving die niet aan de criteria voldoet, helpt u mogelijk gecompromitteerde machines en gebruikersaccounts te identificeren in uw on-premises e-mailomgeving en helpt u bij het uitvoeren van herstelacties.</span><span class="sxs-lookup"><span data-stu-id="b609c-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![Het domeininzicht van afzenders herstellen in het dashboard met e-mailstroom in het Beveiligings- & Compliance Center](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="b609c-114">Wanneer u op **Details weergeven**klikt, wordt u naar een andere widget geleid met meer details, zoals in het volgende diagram wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b609c-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![De widget Details in het domeininzicht Afzenderoplossen](../../media/sender-domain-view-details.png)

<span data-ttu-id="b609c-116">U ziet de binnenkomende connector die is gebruikt om de berichten naar Office 365 te leveren.</span><span class="sxs-lookup"><span data-stu-id="b609c-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="b609c-117">U ook op **Voorbeeldbericht-id's weergeven** om details te zien voor de berichten die zijn verzonden vanuit uw on-premises e-mailomgeving.</span><span class="sxs-lookup"><span data-stu-id="b609c-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="b609c-118">Omdat deze berichten zijn afgewezen door Office 365, u berichttracering niet gebruiken, maar u de id's van het voorbeeldbericht gebruiken om de berichten in uw on-premises e-mailomgeving bij te houden.</span><span class="sxs-lookup"><span data-stu-id="b609c-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Voorbeeldbericht-id's weergeven in het domeininzicht Van afzenderherstellen](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="b609c-120">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b609c-120">See also</span></span>

<span data-ttu-id="b609c-121">Zie Inzicht in [e-mailstroom in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.</span><span class="sxs-lookup"><span data-stu-id="b609c-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
