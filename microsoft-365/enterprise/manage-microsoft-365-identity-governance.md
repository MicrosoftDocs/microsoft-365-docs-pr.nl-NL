---
title: Microsoft 365 Identity governance beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Lees meer over het gebruik van functies voor Microsoft 365 Identity governance.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370344"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="cfadb-103">Microsoft 365 Identity governance beheren</span><span class="sxs-lookup"><span data-stu-id="cfadb-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="cfadb-104">Identiteitsbeheer draait om het beschermen, bewaken en controleren van toegang tot kritieke bedrijfsmiddelen en tegelijkertijd de productiviteit van medewerkers waarborgen.</span><span class="sxs-lookup"><span data-stu-id="cfadb-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="cfadb-105">Met identiteitsbeheer kunt u er bijvoorbeeld voor zorgen dat de juiste gebruikers toegang hebben tot de juiste resources en bepalen of de toegang mettertijd wordt aangepast.</span><span class="sxs-lookup"><span data-stu-id="cfadb-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="cfadb-106">Zie dit artikel voor meer informatie over [Identity governance voor Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="cfadb-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="cfadb-107">Azure Active Directory toegangsbeoordelingen instellen</span><span class="sxs-lookup"><span data-stu-id="cfadb-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="cfadb-108">Via Azure AD Access kunt u de toegang van een gebruiker controleren om ervoor te zorgen dat alleen de juiste personen toegang hebben.</span><span class="sxs-lookup"><span data-stu-id="cfadb-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="cfadb-109">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="cfadb-109">For example:</span></span>

- <span data-ttu-id="cfadb-110">Wanneer een nieuwe medewerker aan uw organisatie wordt toegevoegd, moet u er zeker van zijn dat ze over de juiste machtiging beschikken om productief te zijn.</span><span class="sxs-lookup"><span data-stu-id="cfadb-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="cfadb-111">Als deze werknemer naar andere teams, locaties of afdelingen gaat, moet u ervoor zorgen dat de toegang tot vorige teams, locaties of afdelingen zo nodig wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cfadb-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="cfadb-112">Wanneer deze werknemer of gast uw organisatie verlaat, moet u ervoor zorgen dat de toegang wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cfadb-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="cfadb-113">Dit is met name belangrijk als uw organisatie afhankelijk is van beveiligingscontroles om te bepalen of gebruikersaccounts te veel toegang hebben. Dit kan leiden tot geldboeten in strijd met de bedrijfstak of regionale voorschriften.</span><span class="sxs-lookup"><span data-stu-id="cfadb-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="cfadb-114">Zie het [overzicht van beoordelingen over Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cfadb-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="cfadb-115">Zie de volgende artikelen voor meer informatie over het configureren van toegangsbeoordelingen:</span><span class="sxs-lookup"><span data-stu-id="cfadb-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="cfadb-116">Groepen en apps</span><span class="sxs-lookup"><span data-stu-id="cfadb-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="cfadb-117">Azure AD-rollen</span><span class="sxs-lookup"><span data-stu-id="cfadb-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="cfadb-118">Azure-resourcerollen</span><span class="sxs-lookup"><span data-stu-id="cfadb-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="cfadb-119">Rechtenbeheer voor Azure AD instellen</span><span class="sxs-lookup"><span data-stu-id="cfadb-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="cfadb-120">Wiht Azure AD beleggings beheer kunt u de identiteit en de toegang tot uw identiteit beheren via de werkstroom voor toegangsaanvragen, Access-opdrachten, recensies en verloop.</span><span class="sxs-lookup"><span data-stu-id="cfadb-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="cfadb-121">Uw werknemers moeten toegang hebben tot diverse groepen, toepassingen en sites om hun taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cfadb-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="cfadb-122">Het beheren van deze toegang kan lastig zijn omdat de vereisten zijn gewijzigd, nieuwe toepassingen worden toegevoegd of gebruikers hebben extra toegangsrechten nodig.</span><span class="sxs-lookup"><span data-stu-id="cfadb-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="cfadb-123">Wanneer u samenwerkt met andere organisaties, weet u mogelijk niet welke personen in de andere organisatie toegang nodig hebben tot de bronnen van uw organisatie en kunnen gebruikers van buiten gebruikers weten welke toepassingen, groepen of sites door uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="cfadb-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="cfadb-124">Azure AD begrenzend beheer kan u helpen om de toegang tot groepen, toepassingen en SharePoint-sites efficiënt te beheren voor interne en externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cfadb-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="cfadb-125">Voor meer informatie raadpleegt u het [overzicht van het beheer van rechten van Azure AD](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="cfadb-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
