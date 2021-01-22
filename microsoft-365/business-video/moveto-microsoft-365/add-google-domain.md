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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lees hoe u uw domein kunt verplaatsen van Google Workspace naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925000"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="14d29-103">Uw Google Workspace-domein toevoegen aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14d29-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="14d29-104">Voeg uw Google Workspace-domein toe aan Microsoft 365 voor Bedrijven, zodat u uw zakelijke e-mailadres kunt blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="14d29-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="14d29-105">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="14d29-105">Try it!</span></span>

1. <span data-ttu-id="14d29-106">Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="14d29-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="14d29-107">Selecteer in het Microsoft 365-beheercentrum in **het** linkernavigatiemenu Alles **tonen,** Instellingen en vervolgens **Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="14d29-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="14d29-108">Kies **Domein toevoegen,** voer uw domeinnaam in en selecteer **Dit domein gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="14d29-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="14d29-109">Kies, **Voeg een TXT-record toe** aan de DNS-records van de domeinen, selecteer **Doorgaan** en kopieer de TXT-waarde.</span><span class="sxs-lookup"><span data-stu-id="14d29-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="14d29-110">Ga terug naar de [Google-beheerconsole,](https://admin.google.com)kies Domeinen **beheren,** **Details weergeven,** Domein **beheren,** **DNS** en schuif omlaag naar **aangepaste resourcerecords.** </span><span class="sxs-lookup"><span data-stu-id="14d29-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="14d29-111">Open de vervolgkeuze van het recordtype, kies **TXT,** plak de TXT-waarde die u hebt gekopieerd en selecteer **Vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="14d29-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="14d29-112">De update duurt meestal binnen enkele minuten, maar kan tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="14d29-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="14d29-113">Ga terug naar het Microsoft 365-beheercentrum, selecteer **Verifiëren** en vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="14d29-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="14d29-114">Als u uw domein wilt instellen als het primaire e-mailadres voor uw gebruikers, selecteert u gebruikers **actieve** gebruikers in het  >  **linkernavigatienavigatiebalkje.**</span><span class="sxs-lookup"><span data-stu-id="14d29-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="14d29-115">Kies een gebruiker, selecteer Gebruikersnaam en **e-mailadres beheren,** **Bewerken,** selecteer uw domein in de vervolgkeuze en selecteer vervolgens **Wijzigingen** **opslaan en Klaar.**</span><span class="sxs-lookup"><span data-stu-id="14d29-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="14d29-116">Herhaal deze procedure voor elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="14d29-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="14d29-117">Wanneer u klaar bent, kunt u Office-apps installeren en uw e-mail- en agenda-items migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14d29-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 