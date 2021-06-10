---
title: Het eDiscovery-exporthulpmiddel gebruiken in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: U moet ondersteuning ClickOnce om de nieuwste versie van Microsoft Edge te kunnen gebruiken om zoekresultaten te downloaden van Inhoud zoeken en eDiscovery in het beveiligings- en compliancecentrum.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "52161519"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="c9899-103">Het eDiscovery-exporthulpmiddel gebruiken in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c9899-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="c9899-104">Als gevolg van recente wijzigingen in de nieuwste versie van Microsoft Edge is ClickOnce standaard niet meer ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c9899-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="c9899-105">Als u het hulpprogramma voor eDiscovery-export wilt blijven gebruiken om zoekresultaten voor Inhoud zoeken of eDiscovery te downloaden, moet u [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) gebruiken of ClickOnce-ondersteuning inschakelen in de nieuwste versie van Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="c9899-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="c9899-106">Ondersteuning ClickOnce inschakelen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c9899-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="c9899-107">Ga Microsoft Edge naar **edge://flags/#edge-click-once.**</span><span class="sxs-lookup"><span data-stu-id="c9899-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="c9899-108">Als de bestaande waarde is ingesteld op **Standaard of** **Uitgeschakeld** in de vervolgkeuzelijst, wijzigt u deze in **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="c9899-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Selecteer Ingeschakeld in vervolgkeuzelijst](../media/ClickOnceimage1.png)

3. <span data-ttu-id="c9899-110">Schuif omlaag naar de onderkant van het browservenster en klik op Opnieuw starten **om** Edge opnieuw te starten.</span><span class="sxs-lookup"><span data-stu-id="c9899-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Klik op Opnieuw starten](../media/ClickOnceimage2.png)

<span data-ttu-id="c9899-112">**Opmerking:** Organisaties kunnen groepsbeleid gebruiken om de ondersteuning ClickOnce uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="c9899-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="c9899-113">Als u wilt controleren of er een organisatiebeleid is voor ClickOnce ondersteuning, gaat u naar **edge://policy.**</span><span class="sxs-lookup"><span data-stu-id="c9899-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="c9899-114">In de volgende schermafbeelding ziet u ClickOnce is ingeschakeld in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="c9899-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="c9899-115">Als deze beleidswaarde is ingesteld op **onwaar,** moet u contact opnemen met een beheerder in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c9899-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Lijst met edge-organisatiebeleid](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="c9899-117">Het hulpprogramma voor eDiscovery-export installeren en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="c9899-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="c9899-118">Klik **op Resultaten downloaden** op de flyoutpagina van een export in Inhoud zoeken of een eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="c9899-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Klik op Resultaten downloaden op de flyoutpagina om zoekresultaten te downloaden](../media/ClickOnceExport1.png)

2. <span data-ttu-id="c9899-120">U wordt gevraagd of u het hulpprogramma wilt starten, klik op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="c9899-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Klik op Openen om het eDiscovery-exporthulpmiddel te starten](../media/ClickOnceimage4.png)

   <span data-ttu-id="c9899-122">Als het eDiscovery-exportprogramma niet is geïnstalleerd, wordt u gevraagd om een beveiligingswaarschuwing,</span><span class="sxs-lookup"><span data-stu-id="c9899-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Klik op Installeren om het hulpprogramma voor eDiscovery-export te installeren](../media/ClickOnceimage5.png)

3. <span data-ttu-id="c9899-124">Klik op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="c9899-124">Click **Install**.</span></span> <span data-ttu-id="c9899-125">Nadat het hulpprogramma is geïnstalleerd, wordt het exportprogramma automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c9899-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="c9899-126">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="c9899-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="c9899-127">Inhoudszoekresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="c9899-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="c9899-128">Experimentvlaggen inschakelen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c9899-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
