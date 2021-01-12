---
title: Uw Google Workspace-domein toevoegen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Meer informatie over het verplaatsen van uw domein van Google Workspace naar Microsoft 365 voor bedrijven.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794674"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="c3f10-103">Uw Google Workspace-domein toevoegen aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3f10-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="c3f10-104">Voeg uw Google Workspace-domein toe aan Microsoft 365 voor bedrijven, zodat u uw zakelijke e-mailadres kunt blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c3f10-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="c3f10-105">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="c3f10-105">Try it!</span></span>

1. <span data-ttu-id="c3f10-106">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c3f10-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="c3f10-107">Selecteer in het Microsoft 365-Beheercentrum in het linkernavigatievenster de optie **AllesWeergeven**, **instellingen** en **domeinen**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="c3f10-108">Kies **domein toevoegen**, voer uw domeinnaam in en selecteer vervolgens **dit domein gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="c3f10-109">Kies **een TXT-record toevoegen aan de DNS-records van het domein**, selecteer **Doorgaan** en kopieer de txt-waarde.</span><span class="sxs-lookup"><span data-stu-id="c3f10-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="c3f10-110">Ga terug naar de [Google-beheer console](https://admin.google.com), kies **domeinen**, **domeinen beheren**, **Details weergeven**, **domeinen beheren**, **DNS** en schuif vervolgens omlaag naar **aangepaste bronrecords**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="c3f10-111">Open de vervolgkeuzelijst recordtype, kies **txt**, plak de txt-waarde die u hebt gekopieerd en selecteer vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="c3f10-112">De update duurt doorgaans binnen enkele minuten, maar kan 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="c3f10-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="c3f10-113">Ga terug naar het Microsoft 365-Beheercentrum, selecteer **verifiëren** en vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="c3f10-114">Als u uw domein wilt instellen als het primaire e-mailadres voor uw gebruikers, selecteert u in het linkernavigatievenster **gebruikers**  >  **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="c3f10-115">Kies een gebruiker, selecteer **gebruikersnaam en E-mail beheren**, **bewerken**, selecteer uw domein in de vervolgkeuzelijst en selecteer vervolgens **gereed** om wijzigingen op te **slaan**.</span><span class="sxs-lookup"><span data-stu-id="c3f10-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="c3f10-116">Herhaal dit proces voor elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c3f10-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="c3f10-117">Wanneer u klaar bent, kunt u Office-apps installeren en uw e-mail-en agenda-items migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3f10-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 