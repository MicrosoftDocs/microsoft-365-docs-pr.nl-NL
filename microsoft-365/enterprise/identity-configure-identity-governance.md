---
title: 'Stap 7: Identiteitsbeheer configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Identiteitsbeheer voor uw Azure Active Directory-tenant begrijpen en configureren.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806630"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="d4998-103">Stap 6: Identiteitsbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="d4998-103">Step 6: Configure identity governance</span></span>

![Fase 2-identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d4998-105">Identiteitsbeheer draait om het beschermen, bewaken en controleren van toegang tot kritieke bedrijfsmiddelen en tegelijkertijd de productiviteit van medewerkers waarborgen.</span><span class="sxs-lookup"><span data-stu-id="d4998-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="d4998-106">Met identiteitsbeheer kunt u er bijvoorbeeld voor zorgen dat de juiste gebruikers toegang hebben tot de juiste resources en bepalen of de toegang mettertijd wordt aangepast.</span><span class="sxs-lookup"><span data-stu-id="d4998-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="d4998-107">Zie [dit artikel](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) voor meer informatie over identiteitsbeheer voor Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d4998-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="d4998-108">*Dit is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d4998-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="d4998-109">Azure Active Directory toegangsbeoordelingen instellen</span><span class="sxs-lookup"><span data-stu-id="d4998-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="d4998-110">*Dit is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d4998-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d4998-111">In deze stap stelt u de Azure Active Directory toegangsbeoordelingen in, waarmee u de toegang van een gebruiker kunt controleren om ervoor te zorgen dat alleen de juiste personen doorlopend toegang hebben.</span><span class="sxs-lookup"><span data-stu-id="d4998-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="d4998-112">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d4998-112">For example:</span></span>

- <span data-ttu-id="d4998-113">Wanneer een nieuwe medewerker aan uw organisatie wordt toegevoegd, moet u er zeker van zijn dat ze over de juiste machtiging beschikken om productief te zijn.</span><span class="sxs-lookup"><span data-stu-id="d4998-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="d4998-114">Als deze werknemer naar andere teams, locaties of afdelingen gaat, moet u ervoor zorgen dat de toegang tot vorige teams, locaties of afdelingen zo nodig wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d4998-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="d4998-115">Wanneer deze werknemer of gast uw organisatie verlaat, moet u ervoor zorgen dat de toegang wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d4998-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="d4998-116">Dit is met name belangrijk als uw organisatie afhankelijk is van beveiligingscontroles om te bepalen of gebruikersaccounts te veel toegang hebben. Dit kan leiden tot geldboeten in strijd met de bedrijfstak of regionale voorschriften.</span><span class="sxs-lookup"><span data-stu-id="d4998-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="d4998-117">Zie [dit artikel](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) voor meer informatie over Azure Active Directory toegangsbeoordelingen.</span><span class="sxs-lookup"><span data-stu-id="d4998-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="d4998-118">Azure Active Directory Privileged Identity Management (PIM) biedt aanvullende besturingselementen die zijn afgestemd op het beveiligen van toegangsrechten voor resources in Azure Active Directory, Azure en andere Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="d4998-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="d4998-119">Azure Active Directory PIM biedt een uitgebreide set beheerfuncties voor het beveiligen van de resources van uw bedrijf, zoals Directory-, Office 365- en Azure-resourcerollen.</span><span class="sxs-lookup"><span data-stu-id="d4998-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="d4998-120">Net als bij andere vormen van toegang kunnen organisaties via toegangscontrole terugkerende toegang voor alle gebruikers in de beheerdersrollen configureren.</span><span class="sxs-lookup"><span data-stu-id="d4998-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="d4998-121">Azure Active Directory PIM is alleen beschikbaar in de E5-versie van Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d4998-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d4998-122">Zie de volgende artikelen voor meer informatie over het configureren van toegangsbeoordelingen:</span><span class="sxs-lookup"><span data-stu-id="d4998-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="d4998-123">Groepen en apps</span><span class="sxs-lookup"><span data-stu-id="d4998-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="d4998-124">Azure AD-rollen</span><span class="sxs-lookup"><span data-stu-id="d4998-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="d4998-125">Azure-resourcerollen</span><span class="sxs-lookup"><span data-stu-id="d4998-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="d4998-126">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-access-reviews) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="d4998-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4998-127">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d4998-127">Next step</span></span>

[<span data-ttu-id="d4998-128">Afsluitcriterium voor identiteitsinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="d4998-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

