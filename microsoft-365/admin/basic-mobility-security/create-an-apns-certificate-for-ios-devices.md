---
title: Een APNs-certificaat voor iOS-apparaten maken
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: IOS-apparaten beheren in Basismobiliteit en Beveiliging.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228241"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="fd519-103">Een APNs-certificaat voor iOS-apparaten maken</span><span class="sxs-lookup"><span data-stu-id="fd519-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="fd519-104">Als u iOS-apparaten, zoals iPads en iPhones in Basismobiliteit en Beveiliging, wilt beheren, maakt u een APN-certificaat.</span><span class="sxs-lookup"><span data-stu-id="fd519-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="fd519-105">Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="fd519-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="fd519-106">Typ in uw browser  <https://protection.office.com/> .</span><span class="sxs-lookup"><span data-stu-id="fd519-106">In your browser, type <https://protection.office.com/>.</span></span>

3. <span data-ttu-id="fd519-107">Selecteer  **Preventie van gegevensverlies**   >  **Apparaatbeheer** en kies **APN's-certificaat voor iOS-apparaten.**</span><span class="sxs-lookup"><span data-stu-id="fd519-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="fd519-108">Kies op de pagina Apple Push Notification Certificate Instellingen de optie **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fd519-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="fd519-109">Selecteer Uw MVO-bestand downloaden en sla het certificaat ondertekeningsverzoek op ergens op uw computer op dat u zich zult herinneren.</span><span class="sxs-lookup"><span data-stu-id="fd519-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="fd519-110">Selecteer  **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fd519-110">Select  **Next**.</span></span>

6. <span data-ttu-id="fd519-111">Op de pagina Een APN-certificaat maken:</span><span class="sxs-lookup"><span data-stu-id="fd519-111">On the Create an APNs certificate page:</span></span>

    1. <span data-ttu-id="fd519-112">Selecteer Apple APNS Portal om de Apple Push Certificates Portal te openen.</span><span class="sxs-lookup"><span data-stu-id="fd519-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="fd519-113">Meld u aan met een Apple ID.</span><span class="sxs-lookup"><span data-stu-id="fd519-113">Sign in with an Apple ID.</span></span>

       > [!IMPORTANT]
       > <span data-ttu-id="fd519-114">Gebruik een Apple-id van het bedrijf die is gekoppeld aan een e-mailaccount dat bij uw organisatie blijft, zelfs als de gebruiker die het account beheert, weggaat.</span><span class="sxs-lookup"><span data-stu-id="fd519-114">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves.</span></span> <span data-ttu-id="fd519-115">Sla deze id op omdat u dezelfde id moet gebruiken wanneer het tijd is om het certificaat te verlengen.</span><span class="sxs-lookup"><span data-stu-id="fd519-115">Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="fd519-116">Selecteer  **Een certificaat maken** en accepteer de   gebruiksvoorwaarden.</span><span class="sxs-lookup"><span data-stu-id="fd519-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="fd519-117">Blader naar het certificaat ondertekeningsverzoek dat u hebt gedownload naar uw computer Microsoft 365 en selecteer **Upload.**</span><span class="sxs-lookup"><span data-stu-id="fd519-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

       <span data-ttu-id="fd519-118">Download het APN-certificaat dat is gemaakt door de Apple Push Certificate Portal naar uw computer.</span><span class="sxs-lookup"><span data-stu-id="fd519-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       > [!TIP]
       > <span data-ttu-id="fd519-119">Als u problemen hebt met het downloaden van het certificaat, vernieuwt u de browser.</span><span class="sxs-lookup"><span data-stu-id="fd519-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="fd519-120">Ga terug naar Microsoft 365 en selecteer **Volgende** om naar de pagina Upload     **APNS-certificaat te**   gaan.</span><span class="sxs-lookup"><span data-stu-id="fd519-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="fd519-121">Blader naar het APN-certificaat dat u hebt gedownload van de Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="fd519-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="fd519-122">Selecteer  **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="fd519-122">Select  **Finish**.</span></span>

<span data-ttu-id="fd519-123">Als u de installatie wilt voltooien, gaat u terug naar het Beveiligings- & compliancecentrum > **Beveiligingsbeleid** Instellingen voor   >  \*\*\*\*   >  **apparaatbeheer beheren.**</span><span class="sxs-lookup"><span data-stu-id="fd519-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
