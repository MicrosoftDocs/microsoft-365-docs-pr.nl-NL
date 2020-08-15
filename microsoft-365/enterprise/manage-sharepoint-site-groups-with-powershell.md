---
title: SharePoint Online-sitegroepen beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: In dit artikel vindt u procedures voor het gebruik van PowerShell voor Microsoft 365 voor het beheren van SharePoint Online-sitegroepen.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689408"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="60aad-103">SharePoint Online-sitegroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="60aad-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="60aad-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="60aad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="60aad-105">Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken, kunt u ook PowerShell voor Microsoft 365 gebruiken voor het beheren van uw SharePoint Online-sitegroepen.</span><span class="sxs-lookup"><span data-stu-id="60aad-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="60aad-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="60aad-106">Before you begin</span></span>

<span data-ttu-id="60aad-107">Voor de procedures in dit artikel moet u verbinding maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="60aad-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="60aad-108">Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="60aad-108">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="60aad-109">SharePoint Online weergeven met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60aad-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="60aad-110">Het SharePoint Online-Beheercentrum heeft een aantal handige methoden voor het beheren van sitegroepen.</span><span class="sxs-lookup"><span data-stu-id="60aad-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="60aad-111">Stel dat u de groepen en de groepsleden voor de site wilt bekijken `https://litwareinc.sharepoint.com/sites/finance` .</span><span class="sxs-lookup"><span data-stu-id="60aad-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="60aad-112">U moet het volgende doen om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="60aad-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="60aad-113">Klik in het SharePoint-Beheercentrum op **actieve sites**en klik vervolgens op de URL van de site.</span><span class="sxs-lookup"><span data-stu-id="60aad-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="60aad-114">Klik op de sitepagina op het pictogram **instellingen** (in de rechterbovenhoek van de pagina) en klik vervolgens op **site machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="60aad-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="60aad-115">Herhaal het proces voor de volgende site die u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="60aad-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="60aad-116">Als u een lijst wilt weergeven met de groepen met PowerShell voor Microsoft 365, kunt u de volgende opdrachten gebruiken:</span><span class="sxs-lookup"><span data-stu-id="60aad-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

<span data-ttu-id="60aad-117">Er zijn twee manieren om deze opdracht uit te voeren in de opdrachtprompt van SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="60aad-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="60aad-118">Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **$siteURL** variabele, selecteer de opdrachten en plak deze vervolgens in de SharePoint Online Management Shell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="60aad-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="60aad-119">Wanneer u dat doet, wordt PowerShell beëindigd wanneer u **>>** hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="60aad-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="60aad-120">Druk op ENTER om de opdracht uit te voeren `foreach` .</span><span class="sxs-lookup"><span data-stu-id="60aad-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="60aad-121">Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **$siteURL** variabele en sla het tekstbestand op met een naam en de extensie. ps1 in een geschikte map.</span><span class="sxs-lookup"><span data-stu-id="60aad-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="60aad-122">Voer vervolgens het script uit van de SharePoint Online Management Shell-opdrachtprompt door het pad en de bestandsnaam op te geven.</span><span class="sxs-lookup"><span data-stu-id="60aad-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="60aad-123">Hier ziet u een voorbeeld van een opdracht:</span><span class="sxs-lookup"><span data-stu-id="60aad-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="60aad-124">In beide gevallen ziet u iets dat lijkt op het volgende:</span><span class="sxs-lookup"><span data-stu-id="60aad-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Online-sitegroepen](../media/SPO-site-groups.png)

<span data-ttu-id="60aad-126">Dit zijn alle groepen die zijn gemaakt voor de site `https://litwareinc.sharepoint.com/sites/finance` en alle gebruikers die zijn toegewezen aan deze groepen.</span><span class="sxs-lookup"><span data-stu-id="60aad-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="60aad-127">De namen van de groepen zijn geel, zodat u de namen van de groepsleden kunt onderscheiden.</span><span class="sxs-lookup"><span data-stu-id="60aad-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="60aad-128">Hier ziet u bijvoorbeeld een opdrachtset met de groepen en alle groepslidmaatschappen voor al uw SharePoint Online-sites.</span><span class="sxs-lookup"><span data-stu-id="60aad-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a><span data-ttu-id="60aad-129">Zie ook</span><span class="sxs-lookup"><span data-stu-id="60aad-129">See also</span></span>

[<span data-ttu-id="60aad-130">Verbinding maken met SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="60aad-130">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="60aad-131">SharePoint Online-sites maken en gebruikers toevoegen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="60aad-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="60aad-132">Gebruikers en groepen van SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="60aad-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="60aad-133">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="60aad-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="60aad-134">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60aad-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

