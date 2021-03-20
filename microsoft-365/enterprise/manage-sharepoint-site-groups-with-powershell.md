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
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909536"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="093aa-103">SharePoint Online-sitegroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="093aa-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="093aa-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="093aa-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="093aa-105">Hoewel u het Microsoft 365-beheercentrum kunt gebruiken, kunt u ook PowerShell voor Microsoft 365 gebruiken om uw SharePoint Online-sitegroepen te beheren.</span><span class="sxs-lookup"><span data-stu-id="093aa-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="093aa-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="093aa-106">Before you begin</span></span>

<span data-ttu-id="093aa-107">Voor de procedures in dit artikel moet u verbinding maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="093aa-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="093aa-108">Zie Verbinding maken [met SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="093aa-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="093aa-109">SharePoint Online weergeven met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="093aa-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="093aa-110">Het SharePoint Online-beheercentrum beschikt over een aantal eenvoudig te gebruiken methoden voor het beheren van sitegroepen.</span><span class="sxs-lookup"><span data-stu-id="093aa-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="093aa-111">Stel dat u de groepen en de groepsleden wilt bekijken voor de `https://litwareinc.sharepoint.com/sites/finance` site.</span><span class="sxs-lookup"><span data-stu-id="093aa-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="093aa-112">U moet het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="093aa-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="093aa-113">Klik in het SharePoint-beheercentrum op **Actieve sites** en klik vervolgens op de URL van de site.</span><span class="sxs-lookup"><span data-stu-id="093aa-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="093aa-114">Klik op de sitepagina op **het** pictogram Instellingen (rechtsboven op de pagina) en klik vervolgens op **Sitemachtigingen.**</span><span class="sxs-lookup"><span data-stu-id="093aa-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="093aa-115">Herhaal vervolgens het proces voor de volgende site die u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="093aa-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="093aa-116">Als u een lijst met de groepen wilt weergeven met PowerShell voor Microsoft 365, kunt u de volgende opdrachten gebruiken:</span><span class="sxs-lookup"><span data-stu-id="093aa-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="093aa-117">U kunt deze opdrachtset op twee manieren uitvoeren in de opdrachtprompt SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="093aa-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="093aa-118">Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **variabele $siteURL,** selecteer de opdrachten en plak ze vervolgens in de opdrachtprompt SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="093aa-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="093aa-119">Wanneer u dit doet, stopt PowerShell bij een **>>** prompt.</span><span class="sxs-lookup"><span data-stu-id="093aa-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="093aa-120">Druk op Enter om de opdracht uit te `foreach` voeren.</span><span class="sxs-lookup"><span data-stu-id="093aa-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="093aa-121">Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **variabele $siteURL** en sla dit tekstbestand op met een naam en de PS1-extensie in een geschikte map.</span><span class="sxs-lookup"><span data-stu-id="093aa-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="093aa-122">Voer vervolgens het script uit vanuit de opdrachtprompt SharePoint Online Management Shell door het pad en de bestandsnaam op te geven.</span><span class="sxs-lookup"><span data-stu-id="093aa-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="093aa-123">Hier is een voorbeeldopdracht:</span><span class="sxs-lookup"><span data-stu-id="093aa-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="093aa-124">In beide gevallen ziet u zoiets als dit:</span><span class="sxs-lookup"><span data-stu-id="093aa-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Online-sitegroepen](../media/SPO-site-groups.png)

<span data-ttu-id="093aa-126">Dit zijn alle groepen die zijn gemaakt voor de site `https://litwareinc.sharepoint.com/sites/finance` en alle gebruikers die aan deze groepen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="093aa-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="093aa-127">De groepsnamen zijn geel om u te helpen groepsnamen van hun leden te scheiden.</span><span class="sxs-lookup"><span data-stu-id="093aa-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="093aa-128">Als een ander voorbeeld is hier een opdrachtset met de groepen en alle groepslidmaatschap voor al uw SharePoint Online-sites.</span><span class="sxs-lookup"><span data-stu-id="093aa-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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
    
## <a name="see-also"></a><span data-ttu-id="093aa-129">Zie ook</span><span class="sxs-lookup"><span data-stu-id="093aa-129">See also</span></span>

[<span data-ttu-id="093aa-130">Verbinding maken met SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="093aa-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="093aa-131">SharePoint Online-sites maken en gebruikers toevoegen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="093aa-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="093aa-132">SharePoint Online-gebruikers en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="093aa-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="093aa-133">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="093aa-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="093aa-134">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="093aa-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)