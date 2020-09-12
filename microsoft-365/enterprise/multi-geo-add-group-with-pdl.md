---
title: Een Microsoft 365-groep met een specifieke PDL maken
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
description: Meer informatie over het maken van een Microsoft 365-groep met een opgegeven voorkeurs gegevenslocatie in een omgeving met meerdere geografische locaties.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5af32827d11289f7a966311080d2c15197786799
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547732"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="99976-103">Een Microsoft 365-groep met een specifieke PDL maken</span><span class="sxs-lookup"><span data-stu-id="99976-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="99976-104">Wanneer gebruikers in een omgeving met meerdere geografische groepen een Microsoft 365-groep maken, wordt de gewenste gegevenslocatie van de groep automatisch ingesteld op die van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="99976-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="99976-105">Globaal, SharePoint-en Exchange-beheerders kunnen groepen maken in elk gebied dat ze selecteren.</span><span class="sxs-lookup"><span data-stu-id="99976-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="99976-106">Als u een groep met een specifieke PDL moet maken, kunt u dat doen via het SharePoint-Beheercentrum of via de Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99976-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="99976-107">Wanneer u dit doet, wordt het postvak van de groep en de SharePoint-site die aan de groep zijn gekoppeld, ingericht in de opgegeven PDL.</span><span class="sxs-lookup"><span data-stu-id="99976-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="99976-108">Als u een Microsoft 365-groep wilt maken met de PDL die u opgeeft, gaat u naar het SharePoint-Beheercentrum op de geografische locatie waar u de groepssite wilt maken.</span><span class="sxs-lookup"><span data-stu-id="99976-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="99976-109">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="99976-109">For example:</span></span>

<span data-ttu-id="99976-110">Als u een groepssite wilt maken op uw Australische locatie, kunt u naar https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="99976-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="99976-111">Selecteer **+ maken**.</span><span class="sxs-lookup"><span data-stu-id="99976-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="99976-112">Volg het proces voor het maken van een groepssite.</span><span class="sxs-lookup"><span data-stu-id="99976-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="99976-113">Uw groepssite wordt ingericht op de geografische locatie van het SharePoint-Beheercentrum waarvan u het maken van sites hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="99976-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="99976-114">Exchange PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="99976-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="99976-115">Maak verbinding met Exchange Online PowerShell en geef de parameter *-MailBoxRegion* door de geo-vestigingscode.</span><span class="sxs-lookup"><span data-stu-id="99976-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="99976-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="99976-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Schermafbeelding van een PowerShell-cmdlet New-UnifiedGroup met syntaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="99976-118">Houd er rekening mee dat het inrichten van SharePoint-groeps sites op aanvraag is.</span><span class="sxs-lookup"><span data-stu-id="99976-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="99976-119">De site wordt ingericht wanneer een groepseigenaar of lid de eerste keer probeert toegang te krijgen tot de site.</span><span class="sxs-lookup"><span data-stu-id="99976-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="99976-120">Geo-vestigingscodes</span><span class="sxs-lookup"><span data-stu-id="99976-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="99976-121">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="99976-121">Related topics</span></span>

[<span data-ttu-id="99976-122">Verbinding maken met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="99976-122">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
