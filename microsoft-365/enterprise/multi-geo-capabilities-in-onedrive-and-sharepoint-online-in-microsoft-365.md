---
title: Mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online
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
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Breid uw Microsoft 365-aanwezigheid uit naar meerdere geografische regio's met mogelijkheden voor meervoudige geo-mogelijkheden in OneDrive online.
ms.openlocfilehash: 73561e8420d12687474e3cd69eb389fc69c2038e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689118"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="2ae4a-103">Mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ae4a-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="2ae4a-104">Met mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online kunt u de besturing van het land of de regio met gedeelde bronnen zoals SharePoint-Team sites en Microsoft 365-groeps postvakken bewaren.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of the country or region where shared resources like SharePoint team sites and Microsoft 365 Group mailboxes are stored at rest.</span></span>

<span data-ttu-id="2ae4a-105">Voor elke gebruiker, groeps postvak en SharePoint-site is een voorkeurs gegevenslocatie (PDL) beschikbaar waarmee de geografische locatie wordt aangegeven waar gerelateerde gegevens moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="2ae4a-106">De persoonsgegevens (Exchange-postvak en OneDrive) van gebruikers en de Microsoft 365-groepen of SharePoint-sites die ze maken, kunnen op de opgegeven geo-locatie worden opgeslagen om te voldoen aan de vereisten voor data-woonplaats.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="2ae4a-107">U kunt [verschillende beheerders opgeven voor elke geografische locatie](add-a-sharepoint-geo-admin.md).</span><span class="sxs-lookup"><span data-stu-id="2ae4a-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="2ae4a-108">Gebruikers krijgen een naadloze ervaring wanneer ze Microsoft 365-Services gebruiken, waaronder Office-toepassingen, OneDrive en Search.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="2ae4a-109">Zie [de gebruikerservaring in een omgeving met meerdere geografische gebruikers](multi-geo-user-experience.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="2ae4a-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2ae4a-110">OneDrive</span></span>

<span data-ttu-id="2ae4a-111">U kunt de OneDrive van elke gebruiker op de site van een beheerder richten of [verplaatsen](move-onedrive-between-geo-locations.md) naar een locatie op de locatie van de gebruiker op basis van de PDL van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="2ae4a-112">Persoonlijke bestanden worden vervolgens bewaard op die geografische locatie, maar ze kunnen worden gedeeld met gebruikers in andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="2ae4a-113">SharePoint-sites en-groepen</span><span class="sxs-lookup"><span data-stu-id="2ae4a-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="2ae4a-114">Het beheer van de functie voor meervoudige geo is beschikbaar via het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="2ae4a-115">Meer informatie vindt u in het [bijbehorende blogbericht](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span><span class="sxs-lookup"><span data-stu-id="2ae4a-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="2ae4a-116">Wanneer een gebruiker een SharePoint-groepssite maakt die is verbonden met een SharePoint-site in een omgeving met meerdere geo-geografische omgevingen, wordt de persoonlijke locatie gebruikt om de locatie te bepalen waar de site en het bijbehorende groeps postvak worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="2ae4a-117">(Als de waarde voor PDL PDL van de gebruiker niet is ingesteld of is ingesteld op geo-locatie die niet is geconfigureerd als een satelliet locatie, worden de site en het postvak in de centrale locatie gemaakt.)</span><span class="sxs-lookup"><span data-stu-id="2ae4a-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="2ae4a-118">Microsoft 365-Services, behalve Exchange, OneDrive en SharePoint, zijn niet meerdere geo.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-118">Microsoft 365 services other than Exchange, OneDrive, and SharePoint are not Multi-Geo.</span></span> <span data-ttu-id="2ae4a-119">Microsoft 365-groepen die zijn gemaakt door deze services, worden echter vastgelegd met de PDL van de auteur en via hun Exchange-groeps postvak en de site van de Office 365-groep die is ingericht in de bijbehorende geo.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-119">However, Microsoft 365 Groups that are created by these services will be stamped with the PDL of the creator and their Exchange Group mailbox and SharePoint O365 Group Site provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="2ae4a-120">De omgeving voor meerdere geografische gebieden beheren</span><span class="sxs-lookup"><span data-stu-id="2ae4a-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="2ae4a-121">Het instellen en beheren van uw omgeving met meerdere geografische omgevingen doet u door het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2ae4a-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Schermafbeelding van de pagina geografische locaties in het SharePoint-Beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="2ae4a-123">(Voor sommige acties, zoals het verplaatsen van een SharePoint-site of een OneDrive-site is Microsoft PowerShell vereist.)</span><span class="sxs-lookup"><span data-stu-id="2ae4a-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="2ae4a-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2ae4a-124">See also</span></span>

[<span data-ttu-id="2ae4a-125">Meerdere geografische groepen in SharePoint-en Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="2ae4a-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="2ae4a-126">Een omgeving met meerdere geografische gebieden beheren</span><span class="sxs-lookup"><span data-stu-id="2ae4a-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="2ae4a-127">SharePoint-opslag quota's in meerdere geografische omgevingen</span><span class="sxs-lookup"><span data-stu-id="2ae4a-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="2ae4a-128">Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren</span><span class="sxs-lookup"><span data-stu-id="2ae4a-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
