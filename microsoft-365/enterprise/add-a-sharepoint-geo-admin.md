---
title: Een geo-beheerder toevoegen of verwijderen
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Wilt u afzonderlijke beheerders voor elke geografische locatie configureren? Meer informatie over het toevoegen of verwijderen van een geo-beheerder in Microsoft 365 multi-geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689525"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="8d8a3-104">Een geo-beheerder toevoegen of verwijderen in Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="8d8a3-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="8d8a3-105">U kunt afzonderlijke beheerders configureren voor elke geografische locatie in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="8d8a3-106">Deze beheerders hebben toegang tot de instellingen van SharePoint Online en OneDrive die specifiek zijn voor de geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="8d8a3-107">Sommige services, zoals het termenarchief, worden beheerd vanaf de centrale locatie en worden gerepliceerd naar satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="8d8a3-108">De geo-beheerder voor de centrale locatie heeft toegang tot deze, terwijl geo-beheerders voor satelliet locaties niet.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="8d8a3-109">Globale beheerders en SharePoint Online-beheerders blijven toegang hebben tot de instellingen op de centrale locatie en alle satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="8d8a3-110">Geo-beheerders configureren</span><span class="sxs-lookup"><span data-stu-id="8d8a3-110">Configuring geo administrators</span></span>

<span data-ttu-id="8d8a3-111">Voor het configureren van geografische beheerders is PowerShell-module van SharePoint Online vereist.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="8d8a3-112">Gebruik [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) om verbinding te maken met het Beheercentrum van de geografische locatie waar u de geo-beheerder wilt toevoegen. (Bijvoorbeeld Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="8d8a3-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="8d8a3-113">Als u de bestaande geo-beheerders van een locatie wilt weergeven, voert u `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="8d8a3-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="8d8a3-114">Een gebruiker toevoegen als een geo-beheerder</span><span class="sxs-lookup"><span data-stu-id="8d8a3-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="8d8a3-115">Als u een gebruiker wilt toevoegen als een geo-beheerder, voert u `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="8d8a3-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="8d8a3-116">Als u een gebruiker wilt verwijderen als een geo-beheerder van een locatie, voert u  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="8d8a3-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="8d8a3-117">Een groep als een geo-beheerder toevoegen</span><span class="sxs-lookup"><span data-stu-id="8d8a3-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="8d8a3-118">U kunt een beveiligingsgroep of een beveiligingsgroep met e-mail als een geo-beheerder toevoegen. (Distributiegroepen en Microsoft 365 groepen worden niet ondersteund.)</span><span class="sxs-lookup"><span data-stu-id="8d8a3-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="8d8a3-119">Als u een groep wilt toevoegen als een geo-beheerder, voert u `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="8d8a3-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="8d8a3-120">Als u een groep wilt verwijderen als een geo-beheerder, voert u `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="8d8a3-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="8d8a3-121">Houd er rekening mee dat niet alle beveiligingsgroepen een groepsalias hebben.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="8d8a3-122">Als u een beveiligingsgroep zonder alias wilt toevoegen, voert u [Get-Remove msolgroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) uit om een lijst met groepen op te halen, zoekt u de ObjectID van uw beveiligingsgroep en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="8d8a3-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="8d8a3-123">Als u een groep wilt verwijderen met de ObjectID, voert u `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="8d8a3-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d8a3-124">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8d8a3-124">Related topics</span></span>

[<span data-ttu-id="8d8a3-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="8d8a3-125">Add-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="8d8a3-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="8d8a3-126">Get-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="8d8a3-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="8d8a3-127">Remove-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="8d8a3-128">Een alias (mailnickname) voor een beveiligingsgroep instellen</span><span class="sxs-lookup"><span data-stu-id="8d8a3-128">Set an alias (MailNickName) for a security group</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)