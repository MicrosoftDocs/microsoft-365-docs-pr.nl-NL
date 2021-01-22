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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het verbinden van uw domein met Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925108"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="4c590-103">Uw domein verbinden met Microsoft 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="4c590-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="4c590-104">Nadat u Microsoft 365 hebt ingesteld en uw e-mailgegevens hebt verplaatst van Google Workspace, kunt u uw domein verbinden met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c590-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="4c590-105">Eerst moet u bestaande DNS-records van Google verwijderen, dan kunnen we nieuwe DNS-records van Microsoft 365 toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4c590-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="4c590-106">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="4c590-106">Try it!</span></span>

1. <span data-ttu-id="4c590-107">Meld u aan bij uw Google Workspace-beheerconsole [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="4c590-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="4c590-108">Selecteer **Domeinen,** **Domeinen beheren,** **Details weergeven,** Domein **beheren** en **vervolgens DNS** in het linkernavigatiebalkje.</span><span class="sxs-lookup"><span data-stu-id="4c590-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="4c590-109">Schuif omlaag naar **Recordgegevens,** open **Google Workspace,** selecteer **Verwijderen** en **vervolgens opnieuw** Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4c590-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="4c590-110">Schuif omlaag naar **aangepaste resourcerecords** en verwijder bestaande DNS-records die worden weergegeven, inclusief records die u mogelijk eerder hebt gemaakt voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c590-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="4c590-111">Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4c590-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="4c590-112">Kies in het linkernavigatiemenu de optie **Alles tonen,** **Instellingen,** **Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="4c590-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="4c590-113">Kies vervolgens uw standaarddomein.</span><span class="sxs-lookup"><span data-stu-id="4c590-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="4c590-114">Selecteer **Doorgaan met instellen** en kies Doorgaan om uw domein te **verbinden.**</span><span class="sxs-lookup"><span data-stu-id="4c590-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="4c590-115">Schuif omlaag om de DNS-records te bekijken die naar Google moeten worden gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="4c590-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="4c590-116">Open **MX Records** en kopieer de record onder Adres of **waarde** naar.</span><span class="sxs-lookup"><span data-stu-id="4c590-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="4c590-117">Ga terug naar Google en open in de sectie **Aangepaste resourcerecords** het vervolgkeuzevak recordtype en selecteer **MX.**</span><span class="sxs-lookup"><span data-stu-id="4c590-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="4c590-118">Plak de **gekopieerde** record in het veld Gegevens.</span><span class="sxs-lookup"><span data-stu-id="4c590-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="4c590-119">Selecteer vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="4c590-119">Then select **Add**.</span></span>
1. <span data-ttu-id="4c590-120">Herhaal het proces voor CNAME- en TXT-records en voeg de waarden toe aan de pagina voor dns-beheer van Google.</span><span class="sxs-lookup"><span data-stu-id="4c590-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="4c590-121">Ga terug naar het Microsoft 365-beheercentrum en selecteer **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="4c590-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="4c590-122">Het instellen van uw domein is voltooid.</span><span class="sxs-lookup"><span data-stu-id="4c590-122">Your domain setup is complete.</span></span>