---
title: Een groep Microsoft 365 maken met een specifieke voorkeursgegevenslocatie
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
description: Meer informatie over het maken Microsoft 365 groep met een opgegeven voorkeursgegevenslocatie in een multi-geo-omgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086821"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a><span data-ttu-id="ed036-103">Een groep Microsoft 365 maken met een specifieke voorkeursgegevenslocatie</span><span class="sxs-lookup"><span data-stu-id="ed036-103">Create a Microsoft 365 Group with a specific preferred data location</span></span>

<span data-ttu-id="ed036-104">Wanneer gebruikers in een multi-geo-omgeving een Microsoft 365 Groep maken, wordt de voorkeurslocatie voor gegevens van de groep automatisch ingesteld op die van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ed036-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location (PDL) is automatically set to that of the user.</span></span> <span data-ttu-id="ed036-105">Globale, SharePoint en Exchange Beheerders kunnen groepen maken in elke regio die ze selecteren.</span><span class="sxs-lookup"><span data-stu-id="ed036-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="ed036-106">Als u een groep met een specifiek PDF-programma wilt maken, kunt u dat doen via het SharePoint-beheercentrum of via de microsoft PowerShell Exchange Online New-UnifiedGroup-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed036-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="ed036-107">Wanneer u dit doet, worden zowel het groepspostvak als de SharePoint gekoppeld aan de groep ingericht in het opgegeven PDL.</span><span class="sxs-lookup"><span data-stu-id="ed036-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="ed036-108">Als u een Microsoft 365 groep wilt maken met de PDL die u opgeeft, gaat u naar het SharePoint-beheercentrum op de geografische locatie waar u de groepssite wilt maken.</span><span class="sxs-lookup"><span data-stu-id="ed036-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="ed036-109">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ed036-109">For example:</span></span>

<span data-ttu-id="ed036-110">Als u een groepssite wilt maken op uw locatie in Australië, kunt u naar https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="ed036-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="ed036-111">Selecteer **+ Maken.**</span><span class="sxs-lookup"><span data-stu-id="ed036-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="ed036-112">Volg het proces om een groepssite te maken.</span><span class="sxs-lookup"><span data-stu-id="ed036-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="ed036-113">Uw groepssite wordt ingericht op de geografische locatie die overeenkomt met het SharePoint beheercentrum waaruit u de aanvraag voor het maken van de site hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="ed036-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="ed036-114">PowerShell Exchange gebruiken</span><span class="sxs-lookup"><span data-stu-id="ed036-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="ed036-115">Verbinding maken powershell Exchange Online en passeert u de parameter *-MailBoxRegion* met de geolocatiecode.</span><span class="sxs-lookup"><span data-stu-id="ed036-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="ed036-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ed036-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Schermafbeelding van New-UnifiedGroup PowerShell-cmdlet met syntaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="ed036-118">Houd er rekening SharePoint groepssite-inrichting op aanvraag is.</span><span class="sxs-lookup"><span data-stu-id="ed036-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="ed036-119">De site wordt ingericht de eerste keer dat een groepseigenaar of lid toegang tot de site probeert te krijgen.</span><span class="sxs-lookup"><span data-stu-id="ed036-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="ed036-120">Geolocatiecodes</span><span class="sxs-lookup"><span data-stu-id="ed036-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="ed036-121">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ed036-121">Related topics</span></span>

[<span data-ttu-id="ed036-122">Verbinding maken powershell Exchange Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="ed036-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
