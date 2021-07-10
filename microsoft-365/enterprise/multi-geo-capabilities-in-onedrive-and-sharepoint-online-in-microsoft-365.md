---
title: Multi-Geo-mogelijkheden in OneDrive en SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Vouw uw Microsoft 365 uit naar meerdere geografische regio's met multi-geomogelijkheden in OneDrive Online.
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362280"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="af452-103">Multi-Geo Capabilities in OneDrive en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="af452-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="af452-104">Met multi-geo-mogelijkheden in OneDrive en SharePoint Online kunt u gedeelde resources beheren, zoals SharePoint teamsites en Microsoft 365 Groepspostvakken die in rust zijn opgeslagen op een opgegeven geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="af452-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a specified geo location.</span></span>

<span data-ttu-id="af452-105">Elke gebruiker, groeppostvak en SharePoint site heeft een VOORKEURsgegevenslocatie (PDL) die de geografische locatie aan wijst waar gerelateerde gegevens moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="af452-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="af452-106">De persoonlijke gegevens van gebruikers (Exchange postvak en OneDrive) samen met alle Microsoft 365 Groepen of SharePoint-sites die ze maken, kunnen worden opgeslagen op de opgegeven geografische locatie om te voldoen aan de vereisten voor gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="af452-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="af452-107">U kunt [verschillende beheerders opgeven voor elke geografische locatie.](add-a-sharepoint-geo-admin.md)</span><span class="sxs-lookup"><span data-stu-id="af452-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="af452-108">Gebruikers krijgen een naadloze ervaring bij het gebruik Microsoft 365 services, Office toepassingen, OneDrive en Zoeken.</span><span class="sxs-lookup"><span data-stu-id="af452-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="af452-109">Zie [Gebruikerservaring in een multi-geo-omgeving voor](multi-geo-user-experience.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="af452-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="af452-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="af452-110">OneDrive</span></span>

<span data-ttu-id="af452-111">De OneDrive gebruikers kunnen worden ingericht in of verplaatst door een [beheerder](move-onedrive-between-geo-locations.md) naar een satellietlocatie in overeenstemming met de PDL van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="af452-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="af452-112">Persoonlijke bestanden worden vervolgens op die geografische locatie bewaard, maar ze kunnen worden gedeeld met gebruikers op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="af452-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="af452-113">SharePoint Sites en groepen</span><span class="sxs-lookup"><span data-stu-id="af452-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="af452-114">Het beheer van de functie Multi-Geo is beschikbaar via het SharePoint beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="af452-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="af452-115">Gedetailleerde informatie vindt u in het [bijbehorende blogbericht.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)</span><span class="sxs-lookup"><span data-stu-id="af452-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="af452-116">Wanneer een gebruiker een SharePoint met een groep verbonden site maakt in een multi-geo-omgeving, wordt de PDL ervan gebruikt om de geografische locatie te bepalen waar de site en het bijbehorende groepspostvak worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="af452-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="af452-117">(Als de PDL-waarde van de gebruiker niet is ingesteld of is ingesteld op een geografische locatie die niet is geconfigureerd als satellietlocatie, worden de site en het postvak op de centrale locatie gemaakt.)</span><span class="sxs-lookup"><span data-stu-id="af452-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="af452-118">Microsoft 365 andere services dan Exchange, OneDrive, SharePoint en Teams zijn niet Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="af452-118">Microsoft 365 services other than Exchange, OneDrive, SharePoint, and Teams are not Multi-Geo.</span></span> <span data-ttu-id="af452-119">De Microsoft 365 groepen die door deze services worden gemaakt, worden echter geconfigureerd met de PDL van de maker en het Exchange Groepspostvak, SharePoint-site zijn ingericht in de bijbehorende geo.</span><span class="sxs-lookup"><span data-stu-id="af452-119">However, Microsoft 365 Groups that are created by these services will be configured with the PDL of the creator and their Exchange Group mailbox, SharePoint site are provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="af452-120">De multi-geo-omgeving beheren</span><span class="sxs-lookup"><span data-stu-id="af452-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="af452-121">Het instellen en beheren van uw multi-geo-omgeving gebeurt via het SharePoint beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="af452-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Schermafbeelding van de pagina geografische locaties in het SharePoint beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="af452-123">(Voor sommige acties, zoals het verplaatsen van een SharePoint site of een OneDrive microsoft PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="af452-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="af452-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="af452-124">See also</span></span>

[<span data-ttu-id="af452-125">Multi-Geo in SharePoint en Microsoft 365 Groepen</span><span class="sxs-lookup"><span data-stu-id="af452-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="af452-126">Een multi-geo-omgeving beheren</span><span class="sxs-lookup"><span data-stu-id="af452-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="af452-127">SharePoint opslagquota in multi-geo-omgevingen</span><span class="sxs-lookup"><span data-stu-id="af452-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="af452-128">Postvakken Exchange Online in een multi-geo-omgeving beheren</span><span class="sxs-lookup"><span data-stu-id="af452-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
