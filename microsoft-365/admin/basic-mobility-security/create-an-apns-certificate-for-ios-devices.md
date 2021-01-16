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
description: IOS-apparaten beheren in eenvoudige mobiliteit en beveiliging.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877078"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="8c0a5-103">Een APNs-certificaat voor iOS-apparaten maken</span><span class="sxs-lookup"><span data-stu-id="8c0a5-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="8c0a5-104">Als u iOS-apparaten zoals iPads en iPhones wilt beheren in basis mobiliteit en beveiliging, maakt u een APNs-certificaat.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="8c0a5-105">Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="8c0a5-106">Typ in uw browser  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="8c0a5-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="8c0a5-107">Selecteer  **preventie van gegevensverlies**   > in  **Apparaatbeheer** en kies **APNs-certificaat voor IOS-apparaten**.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="8c0a5-108">Kies **volgende** op de pagina Apple Push Notification Certificate Settings.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="8c0a5-109">Selecteer Download Your CSR file en sla de aanvraag voor certificaatondertekening op uw computer op een locatie op die u kunt onthouden.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="8c0a5-110">Selecteer  **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-110">Select  **Next**.</span></span>

6. <span data-ttu-id="8c0a5-111">Op de pagina Create a APNs Certificate:</span><span class="sxs-lookup"><span data-stu-id="8c0a5-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="8c0a5-112">Selecteer Apple APNS-Portal om de Apple Push Certificate-portal te openen.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="8c0a5-113">Meld u aan met een Apple-ID.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="8c0a5-114">Gebruik een netwerkapple-ID die is gekoppeld aan een e-mailaccount dat bij uw organisatie hoort, zelfs als de gebruiker die het account beheert de account blad houdt.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-114">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves.</span></span> <span data-ttu-id="8c0a5-115">Sla deze ID op omdat u de ID van het certificaat moet verlengen wanneer u dit tijdstip moet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-115">Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="8c0a5-116">Selecteer  **een certificaat maken**   en accepteer de gebruiksvoorwaarden.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="8c0a5-117">Blader naar de aanvraag voor certificaatondertekening die u naar uw computer hebt gedownload vanuit Microsoft 365 en selecteer **uploaden**.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="8c0a5-118">Download het APNs-certificaat dat met de Apple Push Certificate-Portal is gemaakt naar uw computer.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="8c0a5-119">Als u problemen ondervindt bij het downloaden van het certificaat, vernieuwt u de browser.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="8c0a5-120">Ga terug naar Microsoft 365 en selecteer **volgende**   om naar de pagina   **Upload APNS Certificate** te gaan   .</span><span class="sxs-lookup"><span data-stu-id="8c0a5-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="8c0a5-121">Blader naar het APN-certificaat dat u hebt gedownload van de Apple Push Certificate-Portal.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="8c0a5-122">Selecteer  **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-122">Select  **Finish**.</span></span>

<span data-ttu-id="8c0a5-123">Om de installatie te voltooien, gaat u terug naar het beveiligings  \*\*\*\*& compliance >  >  **beleids**   >  **instellingen** voor het beheren van beveiligingsbeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="8c0a5-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
