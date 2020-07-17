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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over het domeininzicht van de afzender op de correctie in het dashboard van de e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818829"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="c76ed-103">Inzicht in verzenddomein oplossen</span><span class="sxs-lookup"><span data-stu-id="c76ed-103">Fix sender domain insight</span></span>

<span data-ttu-id="c76ed-104">Microsoft 365 vereist berichten die vanuit interne on-premises e-mailomgevingen naar Microsoft 365 worden verzonden om aan bepaalde beveiligingscriteria te voldoen:</span><span class="sxs-lookup"><span data-stu-id="c76ed-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="c76ed-105">U hebt een binnenkomende connector gemaakt in Microsoft 365 om SMTP-verbindingen te verifiëren vanaf uw on-premises e-mailserver met behulp van het bron-IP-adres of een certificaat.</span><span class="sxs-lookup"><span data-stu-id="c76ed-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="c76ed-106">U hebt uw on-premises e-mailserver geconfigureerd om e-mail via Microsoft 365 door te geven aan de buitenwereld.</span><span class="sxs-lookup"><span data-stu-id="c76ed-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="c76ed-107">In uw configuratie is een van de volgende instructies waar:</span><span class="sxs-lookup"><span data-stu-id="c76ed-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="c76ed-108">Het e-maildomein van de afzender is geregistreerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c76ed-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="c76ed-109">Raadpleeg voor meer informatie Domeinen toevoegen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c76ed-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="c76ed-110">Uw on-premises e-mailserver is geconfigureerd om een certificaat te gebruiken om e-mail naar Microsoft 365 te verzenden, het certificaat bevat of komt precies overeen met een domeinnaam die u hebt geregistreerd in Microsoft 365 en u hebt een op certificaten gebaseerde connector in Microsoft 365 met dat domein gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c76ed-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="c76ed-111">Berichten die niet aan de criteria voldoen, worden niet aan de organisatie toegeschreven en kunnen worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="c76ed-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="c76ed-112">Het **domeininzicht voor fix-afzender** toont u e-mail vanuit uw on-premises omgeving die niet aan de criteria voldoet, helpt u mogelijk gecompromitteerde machines en gebruikersaccounts in uw on-premises e-mailomgeving te identificeren en helpt u bij het uitvoeren van herstelacties.</span><span class="sxs-lookup"><span data-stu-id="c76ed-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![Het domeininzicht voor afzender herstellen in het e-mailstroomdashboard in het Security & Compliance Center](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="c76ed-114">Wanneer u op **Details weergeven**klikt, wordt u naar een ander widget gebracht met meer details zoals weergegeven in het volgende diagram:</span><span class="sxs-lookup"><span data-stu-id="c76ed-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Het object Details in het domeininzicht fixer](../../media/sender-domain-view-details.png)

<span data-ttu-id="c76ed-116">U ziet de binnenkomende connector die is gebruikt om de berichten naar Office 365 te brengen.</span><span class="sxs-lookup"><span data-stu-id="c76ed-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="c76ed-117">U ook op **voorbeeld-id's voor voorbeeldberichten** klikken om details te zien voor de berichten die vanuit uw on-premises e-mailomgeving zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="c76ed-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="c76ed-118">Omdat deze berichten zijn geweigerd door Office 365, u geen berichttracering gebruiken, maar u de voorbeeld-bericht-id's gebruiken om de berichten in uw on-premises e-mailomgeving bij te houden.</span><span class="sxs-lookup"><span data-stu-id="c76ed-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Voorbeeld-bericht-id's weergeven in het domeininzicht voor afzender herstellen](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a><span data-ttu-id="c76ed-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c76ed-120">Related topics</span></span>

<span data-ttu-id="c76ed-121">Zie [E-mailstroominzichten in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.</span><span class="sxs-lookup"><span data-stu-id="c76ed-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
