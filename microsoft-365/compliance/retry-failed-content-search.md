---
title: Een inhoudszoekactie opnieuw proberen om een inhoudslocatiefout op te lossen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Tijdens een onderzoek kunt u de knop Opnieuw proberen gebruiken om inhoudszoekingen met inhoudslocatiefouten op te lossen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311818"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="2f584-103">Een inhoudszoekactie opnieuw proberen om een inhoudslocatiefout op te lossen</span><span class="sxs-lookup"><span data-stu-id="2f584-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="2f584-104">Wanneer u Inhoud zoeken in het beveiligings- en compliancecentrum gebruikt om een groot aantal postvakken te doorzoeken, kunt u zoekfouten krijgen die vergelijkbaar zijn met de fout:</span><span class="sxs-lookup"><span data-stu-id="2f584-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="2f584-105">Deze fouten (met foutcodes van CS001-002, CS003-002, CS008-009, CS012-002 en andere fouten van het formulier CS0XX-0XX) geven aan dat Inhoud zoeken niet naar specifieke inhoudslocaties kan zoeken; in dit voorbeeld zijn twee postvakken niet doorzocht.</span><span class="sxs-lookup"><span data-stu-id="2f584-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="2f584-106">Deze fouten worden weergegeven op de flyoutpagina met statusdetails van de inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="2f584-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="2f584-107">Oorzaak van fouten in inhoudslocatie</span><span class="sxs-lookup"><span data-stu-id="2f584-107">Cause of content location errors</span></span>

<span data-ttu-id="2f584-108">Wanneer u een groot aantal postvakken zoekt, wordt de zoekopdracht verdeeld over duizenden servers in een Microsoft-datacenter.</span><span class="sxs-lookup"><span data-stu-id="2f584-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="2f584-109">Op een bepaald moment kunnen specifieke servers opnieuw worden opgestart of worden overgeslagen naar redundante exemplaren.</span><span class="sxs-lookup"><span data-stu-id="2f584-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="2f584-110">In een van deze gevallen wordt een time-out uitgevoerd van het verzoek van de inhoudszoekfunctie om gegevens op te halen. In het vorige voorbeeld zijn de fouten voor de postvakken die zijn mislukt, het resultaat van de zoektijd.</span><span class="sxs-lookup"><span data-stu-id="2f584-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="2f584-111">Fouten met inhoudslocatie oplossen</span><span class="sxs-lookup"><span data-stu-id="2f584-111">Resolving content location errors</span></span>

<span data-ttu-id="2f584-112">Het opnieuw starten van de zoekopdracht resulteert vaak in soortgelijke fouten op verschillende servers.</span><span class="sxs-lookup"><span data-stu-id="2f584-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="2f584-113">In plaats van de zoekopdracht  opnieuw te starten, klikt u op de knop Opnieuw proberen die boven aan de pagina met zoekresultaten wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2f584-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Klik op de knop Opnieuw proberen om fouten in inhoudslocatie op te lossen](../media/retrycontentsearch3.png)

<span data-ttu-id="2f584-115">Dit resulteert in het opnieuw zoeken naar alleen de postvakken die zijn mislukt.</span><span class="sxs-lookup"><span data-stu-id="2f584-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="2f584-116">Wanneer u de zoekopdracht opnieuw uitwerkt, blijven de andere resultaten die zijn geretourneerd, behouden.</span><span class="sxs-lookup"><span data-stu-id="2f584-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="2f584-117">Tips om fouten met inhoudslocatie te voorkomen</span><span class="sxs-lookup"><span data-stu-id="2f584-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="2f584-118">Hier vindt u enkele extra oorzaken van fouten in inhoudslocatie en enkele tips om deze te voorkomen bij het zoeken naar grote aantallen postvakken.</span><span class="sxs-lookup"><span data-stu-id="2f584-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="2f584-119">Het postvak dat wordt doorzocht, is mogelijk bezet vanwege gebruikersactiviteit.</span><span class="sxs-lookup"><span data-stu-id="2f584-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="2f584-120">In dit geval beperkt de zoekservice zich mogelijk om te voorkomen dat het postvak niet beschikbaar wordt.</span><span class="sxs-lookup"><span data-stu-id="2f584-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="2f584-121">Als u dit wilt voorkomen, kunt u zoekopdrachten uitvoeren tijdens niet-zakelijke uren.</span><span class="sxs-lookup"><span data-stu-id="2f584-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="2f584-122">De zoekquery haalt mogelijk te veel inhoud op uit het postvak.</span><span class="sxs-lookup"><span data-stu-id="2f584-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="2f584-123">Probeer indien mogelijk het bereik van de zoekopdracht te beperken met behulp van trefwoorden, datumbereiken en zoekvoorwaarden.</span><span class="sxs-lookup"><span data-stu-id="2f584-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="2f584-124">Te veel trefwoorden of trefwoordzinnen wanneer u een zoekquery maakt met behulp van [de lijst met trefwoorden.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)</span><span class="sxs-lookup"><span data-stu-id="2f584-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span> <span data-ttu-id="2f584-125">Wanneer u een zoekquery uitvoert waarin de lijst met trefwoorden wordt gebruikt, wordt met de service in feite een afzonderlijke zoekopdracht uitgevoerd voor elke rij in de lijst met trefwoorden, zodat statistieken kunnen worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="2f584-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="2f584-126">Als u de lijst met trefwoorden gebruikt in zoekquery's, minimaliseert u het aantal rijen in de lijst met trefwoorden of verdeelt u het aantal trefwoorden in kleinere lijsten en maakt u een andere zoekopdracht voor elke lijst met trefwoorden.</span><span class="sxs-lookup"><span data-stu-id="2f584-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2f584-127">Als u problemen wilt beperken die worden veroorzaakt door grote trefwoordlijsten, bent u nu beperkt tot maximaal 20 rijen in de trefwoordlijst van een zoekquery.</span><span class="sxs-lookup"><span data-stu-id="2f584-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="2f584-128">Er worden te veel zoekopdrachten tegelijk uitgevoerd in hetzelfde postvak.</span><span class="sxs-lookup"><span data-stu-id="2f584-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="2f584-129">Probeer indien mogelijk één zoekopdracht tegelijk uit te voeren op elk postvak.</span><span class="sxs-lookup"><span data-stu-id="2f584-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="2f584-130">Te veel postvakken zoeken in één zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="2f584-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="2f584-131">De kans op fouten in inhoudslocatie neemt toe bij het zoeken naar een groot aantal postvakken.</span><span class="sxs-lookup"><span data-stu-id="2f584-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="2f584-132">Probeer indien mogelijk meerdere zoekopdrachten uit te voeren, zodat elke zoekopdracht een subset met postvakken in uw organisatie bevat.</span><span class="sxs-lookup"><span data-stu-id="2f584-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="2f584-133">Vereist onderhoud wordt uitgevoerd in het postvak.</span><span class="sxs-lookup"><span data-stu-id="2f584-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="2f584-134">Hoewel deze oorzaak waarschijnlijk zelden voorkomt, wacht u even na ontvangst van de inhoudslocatiefout en doet u de zoekopdracht opnieuw.</span><span class="sxs-lookup"><span data-stu-id="2f584-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
