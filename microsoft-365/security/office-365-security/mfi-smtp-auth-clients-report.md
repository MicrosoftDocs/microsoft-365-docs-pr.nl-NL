---
title: SMTP-verificatierapport voor clients
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
description: Beheerders kunnen meer te weten komen over het smtp Auth-clientsrapport in het e-mailstroomdashboard in het Security & Compliance Center.
ms.openlocfilehash: 90d008bf775c692431fb5b832652ceb97f9fd760
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818817"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="41d9b-103">SMTP-verificatierapport voor clients</span><span class="sxs-lookup"><span data-stu-id="41d9b-103">SMTP Auth clients report</span></span>

<span data-ttu-id="41d9b-104">Het **SMTP Auth-klantenrapport** belicht het gebruik van het SMTP Auth-client submission protocol door gebruikers of systeemaccounts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="41d9b-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="41d9b-105">Dit verouderde protocol (dat het eindpunt smtp.office365.com) gebruikt, biedt alleen basisverificatie en is gevoelig voor gebruik door gecompromitteerde accounts om e-mail te verzenden.</span><span class="sxs-lookup"><span data-stu-id="41d9b-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="41d9b-106">Met dit rapport u controleren op ongebruikelijke activiteiten.</span><span class="sxs-lookup"><span data-stu-id="41d9b-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="41d9b-107">Het toont ook de TLS-gebruiksgegevens voor clients of apparaten die SMTP Auth gebruiken.</span><span class="sxs-lookup"><span data-stu-id="41d9b-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="41d9b-108">De widget die wordt weergegeven in het dashboard van mailflows geeft het aantal gebruikers of serviceaccounts aan dat het SMTP Auth-protocol in de afgelopen 7 dagen heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="41d9b-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![De KLANTEN VAN SMTP Auth rapporteren in het dashboard van de e-mailstroom in het Security & Compliance Center](../../media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="41d9b-110">Als u op de widget klikt, wordt een flyout geopend die een geaggregeerde weergave biedt van het TLS-gebruik en de volumes van de afgelopen week.</span><span class="sxs-lookup"><span data-stu-id="41d9b-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![De flyout in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-flyout.png)

<span data-ttu-id="41d9b-112">Wanneer u op de koppeling **SMTP Auth-clientsrapport** klikt, ziet u twee hoofdpunten en twee gegevensweergaven.</span><span class="sxs-lookup"><span data-stu-id="41d9b-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="41d9b-113">De gegevensdraaipunten zijn het **verzendvolume** en **TLS-gebruik.**</span><span class="sxs-lookup"><span data-stu-id="41d9b-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="41d9b-114">De gegevensweergaven zijn de grafiek en de detailtabel.</span><span class="sxs-lookup"><span data-stu-id="41d9b-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="41d9b-115">In de weergave **Volume verzenden** wordt het aantal berichten weergegeven dat met SMTP Auth is verzonden voor het opgegeven tijdsbereik.</span><span class="sxs-lookup"><span data-stu-id="41d9b-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="41d9b-116">U het bereik aanpassen door op **Filters**te klikken.</span><span class="sxs-lookup"><span data-stu-id="41d9b-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="41d9b-117">De grafiek wordt georganiseerd door het afzenderdomein.</span><span class="sxs-lookup"><span data-stu-id="41d9b-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="41d9b-118">U afzonderlijke gegevens voor elk domein bekijken door het domein te selecteren in de vervolgkeuzelijst **Gegevens weergeven voor** vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="41d9b-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![Volume verzenden in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="41d9b-120">U gedetailleerde informatie over de afzenders en het aantal berichten bekijken door op **tabel Details weergeven**te klikken.</span><span class="sxs-lookup"><span data-stu-id="41d9b-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="41d9b-121">Als u wilt terugkeren naar de grafiek, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="41d9b-121">To return to the chart, click **View report**.</span></span>

![Detailtabel voor verzenden van volume in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="41d9b-123">De pivot **van TLS-gebruik** is belangrijk vanwege de aanstaande afschaffing van TLS1.0 en TLS1.1 in Office 365.</span><span class="sxs-lookup"><span data-stu-id="41d9b-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="41d9b-124">Veel oudere apparaten en toepassingen kunnen geen e-mail verzenden als ze alleen TLS1.0 kunnen gebruiken met SMTP Auth. Met deze draaifunctie u gebruikers en systeemaccounts identificeren en actie ondernemen die nog oudere versies van TLS gebruiken.</span><span class="sxs-lookup"><span data-stu-id="41d9b-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![TLS-gebruik in het SMTP Auth-klantenrapport](../../media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="41d9b-126">U gedetailleerde informatie bekijken over de afzenders, de versies van TLS die ze gebruiken met SMTP Auth en hun bericht telt door te klikken op **tabel Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="41d9b-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="41d9b-127">Als u wilt terugkeren naar de grafiek, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="41d9b-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="41d9b-128">U ook een meer gedetailleerde versie van het rapport downloaden door op Rapport Aanvragen te klikken.</span><span class="sxs-lookup"><span data-stu-id="41d9b-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![Detailtabel voor TLS-gebruik in het SMTP Auth-clientsrapport](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="related-topics"></a><span data-ttu-id="41d9b-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="41d9b-130">Related topics</span></span>

<span data-ttu-id="41d9b-131">Zie [E-mailstroominzichten in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.</span><span class="sxs-lookup"><span data-stu-id="41d9b-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
