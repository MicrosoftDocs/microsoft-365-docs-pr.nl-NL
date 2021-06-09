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
description: Wilt u afzonderlijke beheerders configureren voor elke geografische locatie? Meer informatie over het toevoegen of verwijderen van een geobeheerder in Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905598"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="1cb98-104">Een geobeheerder toevoegen of verwijderen in Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="1cb98-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="1cb98-105">U kunt afzonderlijke beheerders configureren voor elke geografische locatie die u in uw tenant hebt.</span><span class="sxs-lookup"><span data-stu-id="1cb98-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="1cb98-106">Deze beheerders hebben toegang tot de SharePoint Online en OneDrive instellingen die specifiek zijn voor hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="1cb98-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="1cb98-107">Sommige services, zoals het termstore, worden vanaf de centrale locatie beheerd en gerepliceerd naar satellietlocaties.</span><span class="sxs-lookup"><span data-stu-id="1cb98-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="1cb98-108">De geobeheerder voor de centrale locatie heeft hier toegang toe, terwijl geobeheerders voor satellietlocaties dat niet doen.</span><span class="sxs-lookup"><span data-stu-id="1cb98-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="1cb98-109">Globale beheerders en SharePoint onlinebeheerders hebben nog steeds toegang tot instellingen op de centrale locatie en alle satellietlocaties.</span><span class="sxs-lookup"><span data-stu-id="1cb98-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="1cb98-110">Geobeheerders configureren</span><span class="sxs-lookup"><span data-stu-id="1cb98-110">Configuring geo administrators</span></span>

<span data-ttu-id="1cb98-111">Voor het configureren van geobeheerders is SharePoint Online PowerShell-module vereist.</span><span class="sxs-lookup"><span data-stu-id="1cb98-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="1cb98-112">Gebruik [Verbinding maken-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) om verbinding te maken met het beheercentrum van de geografische locatie waar u de geobeheerder wilt toevoegen. (Bijvoorbeeld Connect-SPOServicehttps://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="1cb98-112">Use [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="1cb98-113">Als u de bestaande geobeheerders van een locatie wilt weergeven, voer dan `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="1cb98-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="1cb98-114">Een gebruiker toevoegen als geobeheerder</span><span class="sxs-lookup"><span data-stu-id="1cb98-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="1cb98-115">Als u een gebruiker wilt toevoegen als een geobeheerder, moet u `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="1cb98-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="1cb98-116">Als u een gebruiker wilt verwijderen als geobeheerder van een locatie, moet u  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="1cb98-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="1cb98-117">Een groep toevoegen als geobeheerder</span><span class="sxs-lookup"><span data-stu-id="1cb98-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="1cb98-118">U kunt als geobeheerder een beveiligingsgroep of een beveiligingsgroep met e-mail toevoegen. (Distributiegroepen en Microsoft 365 Groepen worden niet ondersteund.)</span><span class="sxs-lookup"><span data-stu-id="1cb98-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="1cb98-119">Als u een groep wilt toevoegen als geobeheerder, voer dan `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="1cb98-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="1cb98-120">Als u een groep als geobeheerder wilt verwijderen, voer dan `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="1cb98-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="1cb98-121">Niet alle beveiligingsgroepen hebben een groepsalias.</span><span class="sxs-lookup"><span data-stu-id="1cb98-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="1cb98-122">Als u een beveiligingsgroep wilt toevoegen die geen alias heeft, kunt u [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) uitvoeren om een lijst met groepen op te halen, de ObjectID van uw beveiligingsgroep te zoeken en vervolgens het volgende uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="1cb98-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="1cb98-123">Als u een groep wilt verwijderen met behulp van de ObjectID, voert u `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="1cb98-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="1cb98-124">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1cb98-124">Related topics</span></span>

[<span data-ttu-id="1cb98-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="1cb98-125">Add-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="1cb98-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="1cb98-126">Get-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="1cb98-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="1cb98-127">Remove-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="1cb98-128">Een alias (MailNickName) instellen voor een beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="1cb98-128">Set an alias (MailNickName) for a security group</span></span>](/powershell/module/azuread/set-azureadgroup)