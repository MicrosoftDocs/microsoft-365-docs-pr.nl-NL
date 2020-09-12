---
title: Microsoft 365 Cloud-only-identiteit
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Hierin wordt beschreven hoe u gebruikers en groepen maakt wanneer uw Microsoft 365-abonnement gebruikmaakt van Cloud-only-identiteit.
ms.openlocfilehash: 6ec727ea3648f1daa3af42763e5f497715b987a2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547756"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="e5ad0-103">Microsoft 365 Cloud-only-identiteit</span><span class="sxs-lookup"><span data-stu-id="e5ad0-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="e5ad0-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e5ad0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e5ad0-105">Met alleen Cloud identiteit worden al uw gebruikers, groepen en contactpersonen opgeslagen in de Azure AD-Tenant (Azure Active Directory) van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="e5ad0-106">Hier volgen de basisonderdelen van de identiteit van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-106">Here are the basic components of cloud-only identity.</span></span>
 
![De basisonderdelen van de alleen-Cloud identiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="e5ad0-108">Gebruikers en hun gebruikersaccounts in organisaties kunnen op verschillende manieren worden gecategoriseerd.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="e5ad0-109">De werknemers hebben bijvoorbeeld een permanente status.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="e5ad0-110">Sommige zijn leveranciers, contractant of partners met een tijdelijke status.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="e5ad0-111">Sommige externe gebruikers hebben geen gebruikersaccounts, maar moeten nog wel toegang krijgen tot bepaalde services en bronnen voor ondersteuning van interactie en samenwerking.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="e5ad0-112">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e5ad0-112">For example:</span></span>

- <span data-ttu-id="e5ad0-113">Tenant accounts stellen gebruikers binnen uw organisatie voor die u een licentie voor cloudservices geeft</span><span class="sxs-lookup"><span data-stu-id="e5ad0-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="e5ad0-114">Accounts van Business to Business (B2B) vertegenwoordigen gebruikers van buiten uw organisatie die u uitnodigt om deel te nemen aan de samenwerking</span><span class="sxs-lookup"><span data-stu-id="e5ad0-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="e5ad0-115">Neem de voorraad van de soorten gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="e5ad0-116">Wat zijn de groeperingen?</span><span class="sxs-lookup"><span data-stu-id="e5ad0-116">What are the groupings?</span></span> <span data-ttu-id="e5ad0-117">U kunt bijvoorbeeld gebruikers groeperen op een functie op hoog niveau of doel voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="e5ad0-118">Daarnaast kunnen sommige cloudservices worden gedeeld met gebruikers buiten uw organisatie zonder gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-118">Additionally, some cloud services can be shared with users outside your organization without any user accounts.</span></span> <span data-ttu-id="e5ad0-119">U moet deze groepen gebruikers ook identificeren.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-119">You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="e5ad0-120">U kunt groepen in azure AD gebruiken om verschillende doeleinden te gebruiken om het beheer van de cloudomgeving te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="e5ad0-121">Met een Azure AD-groep kunt u bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e5ad0-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="e5ad0-122">Gebruikslicenties voor groepen gebruiken om licenties voor Microsoft 365 automatisch toe te wijzen aan uw gebruikersaccounts zodra ze worden toegevoegd als leden.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="e5ad0-123">Gebruikersaccounts dynamisch toevoegen aan specifieke groepen, op basis van kenmerken van gebruikersaccounts, zoals naam van de afdeling.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="e5ad0-124">Automatisch gebruikers voor software inrichten als een service (SaaS)-toepassing en de toegang tot de toepassingen met multi-factor Authentication (MFA) en andere regels voor voorwaardelijke toegang beschermen.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="e5ad0-125">Het inrichten van machtigingen en toegangsniveaus voor SharePoint Online-team sites.</span><span class="sxs-lookup"><span data-stu-id="e5ad0-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

<span data-ttu-id="e5ad0-126">U maakt nieuwe ***gebruikers*** met:</span><span class="sxs-lookup"><span data-stu-id="e5ad0-126">You create new ***users*** with:</span></span>

- [<span data-ttu-id="e5ad0-127">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e5ad0-127">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [<span data-ttu-id="e5ad0-128">PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5ad0-128">PowerShell for Microsoft 365</span></span>](create-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="e5ad0-129">U maakt nieuwe ***groepen*** met:</span><span class="sxs-lookup"><span data-stu-id="e5ad0-129">You create new ***groups*** with:</span></span>

- [<span data-ttu-id="e5ad0-130">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e5ad0-130">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [<span data-ttu-id="e5ad0-131">PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5ad0-131">PowerShell for Microsoft 365</span></span>](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a><span data-ttu-id="e5ad0-132">Volgende stap voor Cloud-only-identiteit</span><span class="sxs-lookup"><span data-stu-id="e5ad0-132">Next step for cloud-only identity</span></span>

[<span data-ttu-id="e5ad0-133">Licenties aan gebruikersaccounts toewijzen</span><span class="sxs-lookup"><span data-stu-id="e5ad0-133">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
