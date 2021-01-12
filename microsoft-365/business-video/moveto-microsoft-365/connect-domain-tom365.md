---
title: Verbind uw domein met Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Leer hoe u uw domein verbindt met Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794602"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="d5b52-103">Uw domein koppelen aan Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="d5b52-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="d5b52-104">Wanneer u Microsoft 365 hebt ingesteld en uw e-mail gegevens uit Google Workspace hebt verplaatst, kunt u uw domein verbinden met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b52-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="d5b52-105">U dient eerst bestaande DNS-records uit Google te verwijderen, dan kunnen we nieuwe DNS-records toevoegen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b52-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="d5b52-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="d5b52-106">Try it!</span></span>

1. <span data-ttu-id="d5b52-107">Meld u aan bij uw Google Workspace-beheerconsole op [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="d5b52-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="d5b52-108">Selecteer **domeinen**, **domeinen beheren**, **Details weergeven**, **domein beheren** en **DNS** in de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="d5b52-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="d5b52-109">Schuif omlaag naar **synthetische records**, open **Google Workspace**, selecteer **verwijderen** en klik vervolgens nogmaals op **verwijderen** .</span><span class="sxs-lookup"><span data-stu-id="d5b52-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="d5b52-110">Schuif omlaag naar **aangepaste resource records** en verwijder eventuele bestaande DNS-records die worden weergegeven, inclusief de gegevens die u eerder hebt gemaakt voor microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b52-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="d5b52-111">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d5b52-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="d5b52-112">Kies in het linkernavigatievenster de optie, **AllesWeergeven**, **instellingen**, **domeinen**.</span><span class="sxs-lookup"><span data-stu-id="d5b52-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="d5b52-113">Kies vervolgens uw standaarddomein.</span><span class="sxs-lookup"><span data-stu-id="d5b52-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="d5b52-114">Selecteer **Doorgaan met instellen** en kies  **Doorgaan** om uw domein te verbinden.</span><span class="sxs-lookup"><span data-stu-id="d5b52-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="d5b52-115">Schuif omlaag om de DNS-records weer te geven die moeten worden gekopieerd naar Google.</span><span class="sxs-lookup"><span data-stu-id="d5b52-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="d5b52-116">Open **MX-records** en kopieer onder **Points to address or value** de record.</span><span class="sxs-lookup"><span data-stu-id="d5b52-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="d5b52-117">Ga terug naar Google en open de vervolgkeuzelijst recordtype in de sectie **Custom resource records** en selecteer **MX**.</span><span class="sxs-lookup"><span data-stu-id="d5b52-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="d5b52-118">Plak de gekopieerde record in het veld **Data** .</span><span class="sxs-lookup"><span data-stu-id="d5b52-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="d5b52-119">Selecteer vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d5b52-119">Then select **Add**.</span></span>
1. <span data-ttu-id="d5b52-120">Herhaal het proces voor CNAME-en TXT-records en voeg de waarden toe op de pagina Google DNS Management.</span><span class="sxs-lookup"><span data-stu-id="d5b52-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="d5b52-121">Ga terug naar het Microsoft 365-Beheercentrum en selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d5b52-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="d5b52-122">Het instellen van uw domein is voltooid.</span><span class="sxs-lookup"><span data-stu-id="d5b52-122">Your domain setup is complete.</span></span>