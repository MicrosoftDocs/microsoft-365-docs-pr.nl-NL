---
title: Microsoft 365 cloud-only-identiteit
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Hier wordt beschreven hoe u gebruikers en groepen maakt wanneer uw Microsoft 365 cloud-only-identiteit gebruikt.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327925"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="a38fe-103">Microsoft 365 cloud-only-identiteit</span><span class="sxs-lookup"><span data-stu-id="a38fe-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="a38fe-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a38fe-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a38fe-105">Met alleen-cloudidentiteit worden al uw gebruikers, groepen en contactpersonen opgeslagen in de Azure Active Directory (Azure AD) tenant van uw Microsoft 365 abonnement.</span><span class="sxs-lookup"><span data-stu-id="a38fe-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="a38fe-106">Hier zijn de basisonderdelen van alleen-cloudidentiteit.</span><span class="sxs-lookup"><span data-stu-id="a38fe-106">Here are the basic components of cloud-only identity.</span></span>
 
![De basisonderdelen van alleen-cloudidentiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="a38fe-108">Gebruikers en hun gebruikersaccounts in organisaties kunnen op verschillende manieren worden gecategoriseerd.</span><span class="sxs-lookup"><span data-stu-id="a38fe-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="a38fe-109">Sommige zijn bijvoorbeeld werknemers en hebben een permanente status.</span><span class="sxs-lookup"><span data-stu-id="a38fe-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="a38fe-110">Sommige zijn leveranciers, aannemers of partners met een tijdelijke status.</span><span class="sxs-lookup"><span data-stu-id="a38fe-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="a38fe-111">Sommige zijn externe gebruikers die geen gebruikersaccounts hebben, maar toch toegang moeten krijgen tot specifieke services en bronnen ter ondersteuning van interactie en samenwerking.</span><span class="sxs-lookup"><span data-stu-id="a38fe-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="a38fe-112">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a38fe-112">For example:</span></span>

- <span data-ttu-id="a38fe-113">Tenantaccounts vertegenwoordigen gebruikers binnen uw organisatie die u een licentie voor cloudservices hebt</span><span class="sxs-lookup"><span data-stu-id="a38fe-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="a38fe-114">B2B-accounts (Business to Business) vertegenwoordigen gebruikers buiten uw organisatie die u uitnodigt om deel te nemen aan samenwerking</span><span class="sxs-lookup"><span data-stu-id="a38fe-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="a38fe-115">Maak een balans op van de typen gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a38fe-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="a38fe-116">Wat zijn de groeperingen?</span><span class="sxs-lookup"><span data-stu-id="a38fe-116">What are the groupings?</span></span> <span data-ttu-id="a38fe-117">U kunt gebruikers bijvoorbeeld groepeerden op functie of doel op hoog niveau voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a38fe-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="a38fe-118">Daarnaast kunnen sommige cloudservices zonder gebruikersaccounts worden gedeeld met gebruikers buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a38fe-118">Additionally, some cloud services can be shared with users outside your organization without any user accounts.</span></span> <span data-ttu-id="a38fe-119">U moet deze groepen gebruikers ook identificeren.</span><span class="sxs-lookup"><span data-stu-id="a38fe-119">You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="a38fe-120">U kunt groepen in Azure AD gebruiken voor verschillende doeleinden die het beheer van uw cloudomgeving vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="a38fe-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="a38fe-121">Met Azure AD-groepen kunt u bijvoorbeeld het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="a38fe-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="a38fe-122">Gebruik groepslicenties om licenties voor Microsoft 365 automatisch toe te wijzen aan uw gebruikersaccounts zodra ze als leden worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="a38fe-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="a38fe-123">Gebruikersaccounts dynamisch toevoegen aan specifieke groepen op basis van kenmerken van gebruikersaccounts, zoals afdelingsnaam.</span><span class="sxs-lookup"><span data-stu-id="a38fe-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="a38fe-124">Gebruikers automatisch inrichten voor SaaS-toepassingen (Software as a Service) en om de toegang tot deze toepassingen te beschermen met MFA (Multi-Factor Authentication) en andere beleidsregels voor Voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="a38fe-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="a38fe-125">Inrichtingsmachtigingen en toegangsniveaus voor SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="a38fe-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="a38fe-126">Volgende stappen voor alleen-cloudidentiteit</span><span class="sxs-lookup"><span data-stu-id="a38fe-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="a38fe-127">Gebruikersaccounts beheren</span><span class="sxs-lookup"><span data-stu-id="a38fe-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="a38fe-128">Licenties aan gebruikersaccounts toewijzen</span><span class="sxs-lookup"><span data-stu-id="a38fe-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="a38fe-129">Groepen en groepslidmaatschap beheren</span><span class="sxs-lookup"><span data-stu-id="a38fe-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="a38fe-130">Wachtwoorden voor gebruikersaccounts beheren</span><span class="sxs-lookup"><span data-stu-id="a38fe-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
