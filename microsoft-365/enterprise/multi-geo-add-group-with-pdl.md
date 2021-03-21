---
title: Een Microsoft 365-groep maken met een specifieke PDL
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Meer informatie over het maken van een Microsoft 365-groep met een opgegeven voorkeursgegevenslocatie in een multi-geoomgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923742"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="e7619-103">Een Microsoft 365-groep maken met een specifieke PDL</span><span class="sxs-lookup"><span data-stu-id="e7619-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="e7619-104">Wanneer gebruikers in een multi-geo-omgeving een Microsoft 365-groep maken, wordt de gewenste gegevenslocatie van de groep automatisch ingesteld op die van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e7619-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="e7619-105">Globale, SharePoint- en Exchange-beheerders kunnen groepen maken in elke regio die ze selecteren.</span><span class="sxs-lookup"><span data-stu-id="e7619-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="e7619-106">Als u een groep met een specifieke PDL wilt maken, kunt u dat doen via het SharePoint-beheercentrum of via de Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7619-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="e7619-107">Wanneer u dit doet, worden zowel het groepspostvak als de SharePoint-site die aan de groep is gekoppeld, ingericht in het opgegeven PDL.</span><span class="sxs-lookup"><span data-stu-id="e7619-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="e7619-108">Als u een Microsoft 365-groep wilt maken met de PDL die u opgeeft, gaat u naar het SharePoint-beheercentrum op de geografische locatie waar u de groepssite wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e7619-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="e7619-109">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7619-109">For example:</span></span>

<span data-ttu-id="e7619-110">Als u een groepssite wilt maken op uw locatie in Australië, kunt u naar https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="e7619-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="e7619-111">Selecteer **+ Maken.**</span><span class="sxs-lookup"><span data-stu-id="e7619-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="e7619-112">Volg het proces om een groepssite te maken.</span><span class="sxs-lookup"><span data-stu-id="e7619-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="e7619-113">Uw groepssite wordt ingericht op de geografische locatie die overeenkomt met het SharePoint-beheercentrum waaruit u de aanvraag voor het maken van de site hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="e7619-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="e7619-114">Exchange PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="e7619-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="e7619-115">Maak verbinding met Exchange Online PowerShell en passeert de parameter *-MailBoxRegion* met de geolocatiecode.</span><span class="sxs-lookup"><span data-stu-id="e7619-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="e7619-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7619-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Schermafbeelding van New-UnifiedGroup PowerShell-cmdlet met syntaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="e7619-118">SharePoint group site provisioning is on-demand.</span><span class="sxs-lookup"><span data-stu-id="e7619-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="e7619-119">De site wordt ingericht de eerste keer dat een groepseigenaar of lid toegang tot de site probeert te krijgen.</span><span class="sxs-lookup"><span data-stu-id="e7619-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="e7619-120">Geolocatiecodes</span><span class="sxs-lookup"><span data-stu-id="e7619-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="e7619-121">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e7619-121">Related topics</span></span>

[<span data-ttu-id="e7619-122">Verbinding maken met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7619-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)